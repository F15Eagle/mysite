---
layout: project-detail
title: "E-Town Rocket Bureau: Two Years of Active Control"
description: "A complete overview of my time engineering active-control model rockets, SITL simulators, and building an aerospace team from the ground up."
image_path: "assets/images/full assembly render 1.png"
tags: ["Rocketry", "Aerospace", "Active Controls", "Leadership", "Python", "C++"]
---

When Eli, Tristan, Peter, and I started the E-Town Rocket Bureau in August 2024, we didn't just want to launch standard model rockets. We wanted to make a rocket that could **control where it went**. Our goal was the American Rocketry Challenge (ARC), where success depends on hitting a precise target altitude. That requirement turned what started as a high school rocketry club into a two-year systems engineering project spanning aerodynamics, mechanical design, embedded programming, simulation, manufacturing, and team management.

Our 2026 rocket, EML26, grew directly out of the much simpler rocket we built during our 2024–25 rookie season. Each year, we pushed the design further, adding active control, more sophisticated avionics, and increasingly complex mechanical systems. That ambition came with an important lesson: **manufacturing is not a joke.** We originally planned to build two rockets for the 2026 season. As the design grew more complicated, however, CAD, 3D printing, machining, assembly, and avionics consumed far more time than we anticipated. In the end, we barely managed to finish one. That lesson was reinforced by my experience at Ward Manufacturing, where I saw firsthand how much engineering depends on actually being able to manufacture something reliably and precisely.

For EML26, I designed a linkage-based airbrake mechanism capable of deploying during ascent while surviving the roughly 12G loads of flight. Using Autodesk Inventor and Autodesk CFD, I iterated on the mechanism, simulated its behavior, and rapidly prototyped components through 3D printing and laser cutting. The objective wasn't simply to make an airbrake that moved; it had to integrate mechanically with the airframe, survive launch, and provide enough aerodynamic authority to precisely control apogee.

<figure>
<img src="{{ 'assets/images/full assembly render 1.png' | relative_url }}" alt="Airbrake Full Assembly Render">
<figcaption>My CAD assembly for the linkage-based active-control airbrake mechanism.</figcaption>
</figure>

Designing the mechanism was only half the problem. To control it, I engineered a custom avionics stack around an ESP32-S3 microcontroller, integrating a BMP180 barometer and BNO085 IMU for real-time flight data. The electronics required more than simply connecting a few sensors: I soldered over 50 points across the MCU, sensors, boost circuitry, and a capacitor intended to handle the servo's sudden current spikes. On the software side, we used a 1D Kalman filter and exponential smoothing to reduce sensor noise and obtain altitude measurements accurate to roughly 1.5 meters.

I also derived the proportional term of the PID controller mathematically rather than treating the controller as a collection of numbers to tune experimentally. The derivation connected the rocket's altitude error and the aerodynamic response of the airbrakes to the proportional control behavior we ultimately implemented.

<!-- INSERT LINK TO P-TERM PID DERIVATION PDF HERE -->

<figure>
<img src="{{ 'assets/images/binary_search_loop_diagram.png' | relative_url }}" alt="Binary Search Loop Diagram">
<figcaption>The binary search loop I wrote to automatically tune the PID controller.</figcaption>
</figure>

While I was deep in the avionics and airbrake work, another problem emerged: our exhaust plume was going to completely char the wooden launch pad. Rather than taking on another project myself, I delegated the launch-tower upgrade to two or three other team members. They designed and implemented a stainless-steel V-deflector layered with carbon-fiber blankets to protect the launch infrastructure. It was one of the first times I had to recognize that building a complicated aerospace system wasn't something I could do alone; the project would only move forward if I trusted other people with meaningful engineering responsibilities.

By the time we reached our first test flight, the complexity of the rocket had caught up with us. I stayed up until 6:30 AM the morning of the launch, slept for roughly 90 minutes, and then headed to the field. On March 29, 2026, we launched Lil' Willy 001. The ascent itself was nominal, but the ejection charge fired early. Excess friction from adhesive tape prevented the rocket from decoupling, and the roughly 1530°C ejection gases melted through the upper avionics and airbrake plastics. The rocket ultimately descended ballistically at approximately Mach 0.2.

It was a brutal failure, but it was also exactly the kind of failure that exposed problems we couldn't have fully appreciated in CAD. We immediately redesigned the deployment system, added wooden bulkheads to absorb the ejection blast, and replaced MicroSD storage with soldered flash memory so that a crash would no longer mean losing our flight data. The failure forced us to think about the rocket not as a collection of individual components, but as a system whose mechanical, electrical, and software decisions could all affect one another.

That same systems mindset shaped how I approached the control software. Before risking another rocket, I wanted a way to tune the PID controller without repeatedly destroying hardware. I built ATOS, a Software-in-the-Loop (SITL) simulator in Google Colab, to model the flight and test control parameters virtually. The core Python suite was built and operational by the end of January 2026. I implemented a binary-search-based tuning algorithm that could run hundreds of virtual flight iterations and systematically converge on Kp, Ki, and Kd values for a desired apogee instead of relying entirely on trial and error.

In June, I took ATOS further by integrating OpenRocket kinematic data directly into the simulation environment. Around the same time, I built a beta web interface generated with the help of an LLM, making it easier to run and compare simulations without interacting directly with the underlying Python code.

<figure>
<img src="{{ 'assets/images/binary_search_loop_diagram.png' | relative_url }}" alt="Binary Search Loop Diagram">
<figcaption>The binary-search loop used by ATOS to automatically tune the PID controller.</figcaption>
</figure>

By the end of my tenure as Chief Engineer in June 2026, however, the hardest engineering problem was no longer the rocket itself. Half of our core team was graduating, and I realized that a successful engineering organization had to survive beyond the people who originally built it. We pushed recruitment, mentored more than five teammates on Autodesk Inventor, and grew the team by 75% year-over-year despite losing half of our experienced members to graduation.

As the team expanded, I also began treating knowledge as another engineering resource that needed to be managed. I wrote a Python script to generate attendance and effort reports from hours logged in Google Sheets, giving us a way to understand participation and identify where newer members needed support. More importantly, I built a central team website using LLMs to preserve our institutional knowledge. It serves as both a public project showcase and a technical repository containing CAD models, C++ and Python code, documentation, and advice that future members can build upon rather than rediscovering everything from scratch.

<figure>
<img src="{{ 'assets/images/group_hours_over_time.png' | relative_url }}" alt="Organizational Tracking Program Graph">
<figcaption>Python-generated report tracking team member hours and team participation.</figcaption>
</figure>

Over two years, the E-Town Rocket Bureau became much more than a rocketry club. I learned that designing an aerospace system means balancing aerodynamic theory with manufacturing constraints, software with hardware limitations, and individual engineering ability with the capabilities of an entire team. A mechanism can work perfectly in CAD and still fail on the launchpad. A controller can be mathematically sound and still need hundreds of simulated flights before it is trustworthy. And an engineering team can build something impressive one year only to lose the knowledge necessary to recreate it the next.

Treating the Rocket Bureau as one continuous systems-engineering project taught me how to move between those problems instead of looking at them in isolation. From designing the airbrakes and avionics, to building ATOS, to recovering from our first major failure, and finally to building systems that could outlast my own involvement, the project became my first real experience with the complexity—and the satisfaction—of aerospace engineering.
