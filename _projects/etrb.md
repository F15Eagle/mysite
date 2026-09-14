---

layout: project-detail
title: "E-Town Rocket Bureau: Two Years of Active Control"
description: "A complete overview of my time engineering active-control model rockets, SITL simulators, and building an aerospace team from the ground up."
image_path: "assets/images/full assembly render 1.png"
tags: ["Rocketry", "Aerospace", "Active Controls", "Leadership", "Python", "C++"]
home_display: true
home_order: 1
---
[[image: /assets/images/full assembly render 1.png, Render of Lil' Willy]]

When Eli, Tristan, Peter, and I started the E-Town Rocket Bureau in August 2024, we didn't just want to launch standard model rockets. We wanted to make a rocket that could **control where it went**. Our goal was the American Rocketry Challenge (ARC), where success depends on hitting a precise target altitude. That requirement turned what started as a high school rocketry club into a two-year systems engineering project spanning aerodynamics, mechanical design, embedded programming, simulation, manufacturing, and team management.

Our 2026 rocket, EML26, grew directly out of the much simpler rocket we built during our 2024–25 rookie season.

[[image: /assets/images/etrb-2025-team.jpg, The E-Town Rocket Bureau team during our first year.]]

The first year gave us a foundation, but EML26 was a completely different level of complexity. We added active-control airbrakes, a custom avionics system, more sophisticated flight software, and a mechanical deployment system. That ambition taught me one of the most important lessons of the entire project: **manufacturing is not a joke.**

We originally planned to build two rockets for the 2026 season. Instead, the complexity of the CAD, 3D printing, electronics, assembly, and testing consumed far more time than we expected. We barely finished one. That lesson was reinforced by my experience at Ward Manufacturing, where I saw firsthand how much engineering depends on whether something can actually be manufactured accurately, repeatedly, and on schedule.

For EML26, I designed a linkage-based airbrake mechanism capable of deploying during ascent while surviving roughly 12G loads. Using Autodesk Inventor and Autodesk CFD, I iterated on the mechanism, simulated its behavior, and rapidly prototyped components through 3D printing and laser cutting. I went through roughly three or four full iterations of the airbrake assembly, along with many more iterations of individual components as I worked out clearances and manufacturing tolerances. The objective wasn't simply to make an airbrake that moved; it had to integrate with the airframe, survive launch, and provide enough aerodynamic authority to precisely control apogee.

[[image: /assets/images/Airbrake Render1.png, CAD assembly of the linkage-based active-control airbrake mechanism.]]
[[video: /assets/images/Airbrake Control Test (Numerical Input).mp4, Ground Testing Airbrake Electronic Actuation]]

Designing the mechanism was only half the problem. To control it, I engineered a custom avionics stack around an ESP32-S3 microcontroller, integrating a BMP180 barometer and BNO085 IMU for real-time flight data. The electronics required more than simply connecting a few sensors: I soldered over 50 points across the MCU, sensors, boost circuitry, and a capacitor intended to handle the servo's sudden current spikes. On the software side, we used a 1D Kalman filter and exponential smoothing to reduce sensor noise and obtain altitude measurements accurate to roughly 1.5 meters.

[[image: /assets/images/Fully_Assembled_AV_Bay_2.jpg, Assembled Avionics Stack]]

I also wanted to understand the control system mathematically rather than treating the PID controller as a collection of numbers to tune until something worked. I derived the proportional term from the rocket's altitude error and the aerodynamic response of the airbrakes, working through the relationship between the desired control response and the resulting proportional gain.

[[pdf: /assets/ARC 2026 PID P-Term Derivation with Handwritten.pdf, Derivation of the PID Proportional Term, true]]

While I was deep in the avionics and airbrake work, another problem emerged: our exhaust plume was going to completely char the wooden launch pad. Rather than taking on another project myself, I delegated the launch-tower upgrade to two or three other team members. They designed and implemented a stainless-steel V-deflector layered with carbon-fiber blankets to protect the launch infrastructure.

That delegation mattered. The rocket was already becoming too large of a project for one person to own every subsystem, and I needed to learn when engineering meant building something myself and when it meant trusting someone else to build it.

That same systems mindset shaped how I approached the control software. Before risking another rocket, I wanted a way to tune the PID controller without repeatedly destroying hardware. I built **[[link: https://github.com/ETHS-Rocketry/airbrake-active-control, ATOS — the Active Targeting and Optimization Suite]] —**, a Software-in-the-Loop simulator in Google Colab designed to model our flight-control system and test parameters virtually. The core Python suite was built and operational by the end of January 2026.

ATOS could run repeated virtual flights and automatically search for PID parameters that brought the simulated rocket toward a target apogee. I implemented a binary-search-based optimization process for the controller gains, allowing dozens of virtual flight iterations to be performed without burning through physical rockets. The simulator modeled not just the controller, but the interaction between the flight trajectory, avionics, airbrakes, and servo behavior.

With the core simulator operational, we were finally ready to put the system to a physical test. By the time we reached our first test flight, the complexity of the rocket had caught up with us. I stayed up building until 6:30 AM the morning of the launch, slept for roughly 90 minutes, and then headed to the field. On March 26, 2026, we launched Lil' Willy 001.

The ascent itself was nominal, but tube separation did not go well. Excess friction from adhesive tape prevented the rocket from decoupling, and the roughly 1530°C ejection gases melted through the upper avionics and airbrake plastics. The rocket ultimately descended ballistically at approximately Mach 0.2.

[[youtube: DBYvCB82rY4, Launch 1]]

It was a brutal failure, but it exposed problems that CAD and simulations had not. We immediately planned to redesign the deployment system, add wooden bulkheads to absorb the ejection blast, and replace MicroSD storage with soldered flash memory so that a crash would no longer mean losing our flight data. The failure forced us to think about the rocket not as a collection of individual components, but as a system whose mechanical, electrical, and software decisions could all affect one another.

In June, as my time with the Rocket Bureau was coming to an end, I pushed ATOS into its final form by integrating OpenRocket kinematic data directly into the simulation environment. Around the same time, I built a beta web interface with the help of an LLM, making the simulator much easier to operate and allowing rapid testing without manually interacting with the underlying Python environment.

[[image: /assets/images/binary_search_loop_diagram.png, The binary-search loop used by ATOS to automatically tune the PID controller.]]

[[link: https://eths-rocketry.github.io/airbrake-active-control/, ATOS Web Interface (Beta)]]

The result was a development environment that could take an OpenRocket flight export, simulate our active-control system, and systematically search for controller gains before putting hardware on a launch rail.

Between the end of our first school year in spring 2025 and the start of our second year in fall 2025, I was facing a different engineering problem: **how do you keep a team alive after its experienced members leave?**

Half of our core group was graduating. We pushed recruitment, mentored more than five teammates on Autodesk Inventor, and grew the team by 75% year-over-year. But recruiting people was only part of the problem. If the knowledge stayed in our heads, then it would graduate with us.

I started tackling that problem in the fall of 2025. I built a Python-based tracking system that processed hours logged in Google Sheets and generated attendance and effort reports, giving us a better picture of participation and helping us understand where members were contributing.

[[image: /assets/images/group_hours_over_time.png, Python-generated report tracking team member hours and participation.]]

As the 2026 season progressed, I took the idea further by building a central team website using LLMs. It became both a public project showcase and a digital repository for our CAD models, C++ and Python code, technical documentation, and advice for future members. The goal was simple: **make sure the team's knowledge didn't disappear when the people who created it did.**

[[link: https://eths-rocketry.github.io/site/Layouts/home.html, The ETHS Rocketry team website and technical repository I built with LLMs.]]

By the time I finished my tenure at the end of the 2025–26 school year, the E-Town Rocket Bureau had become much more than the club we started in 2024. I had learned that designing an aerospace system means balancing aerodynamic theory with manufacturing constraints, software with hardware limitations, and individual engineering ability with the capabilities of an entire team.

A mechanism can work perfectly in CAD and still fail on the launchpad. A controller can be mathematically sound and still require hundreds of simulations before it is trustworthy. And an engineering team can build something impressive one year only to lose the knowledge necessary to recreate it the next.

Treating the Rocket Bureau as one continuous systems-engineering project taught me how to move between all of those problems instead of looking at them in isolation. From designing the airbrakes and avionics, to deriving and tuning the control system, to building ATOS, recovering from our first major failure, and finally creating systems that could outlast my own involvement, the project became my first real experience with the complexity—and the satisfaction—of aerospace engineering.
