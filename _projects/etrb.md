---
layout: project-detail
title: "E-Town Rocket Bureau"
description: "Co-founding, organizing, and leading a High School rocketry team."
# image_path: "assets/images/full assembly render 1.png"
tags: ["Leadership", "Aerospace"]
---

## Summary
I co-founded the E-Town Rocket Bureau---my High School's active-control rocketry team---in August of 2024, along with Founder [Eli Corr](https://www.linkedin.com/in/eli-corr-486847392/) and Co-Founders [Tristan Schultz](https://www.linkedin.com/in/tristan-schultz-54930428a/) and [Peter Elbakian](https://www.linkedin.com/in/peter-elbakian-2a66453b0/).

I've since served as Chief Engineer, with my tenure ending in May of 2026. Having had the privilege to serve for two years, I've learned a great deal about leadership in engineering contexts. I built our organizational structure from the ground up and created our broader school rocketry website. The [website](https://ethsrocketry.github.io/site/home.html) showcases our work, and---crucially---stores our knowledge, allowing future generations of engineers to gain a headstart. 

Starting out completely new to rocketry, I've had the opportunity to absorb a massive amount of technical material. I've since gained proficiency and hands-on experience with Python, C++, active control systems, software-in-the-loop (SIL) PID optimization, embedded systems, and a whole host of supporting software.

<figure>
<img src="{{ 'assets/images/etrb-2025-team.jpg' | relative_url }}" alt="2025 Team Photo">
<figcaption>2025 Team Photo</figcaption>
</figure>

## Scaling the Roster & Onboarding Realizations
Our first year was primarily focused on gaining basic technical experience and defining our long-term goals: competing in the American Rocketry Challenge (ARC) and pioneering actively-controlled model rocketry at our school. However, graduation hit us hard at the end of that first year, claiming half of our core membership. 

To rebuild, I spearheaded an aggressive outreach and recruitment campaign heading into the fall. By leveraging the Freshman Activity Fair, presenting to incoming students, and engaging directly with parents, we achieved a 75% YoY club growth rate, ultimately scaling our roster by 250%. 

This massive influx of new members brought an unexpected leadership bottleneck: we suddenly had a highly enthusiastic but entirely inexperienced freshman cohort. Balancing college applications, rowing, and rocket development left little room to design a formal training pipeline on the fly. I chose to have newer members learn CAD and core aerospace concepts "on the go" to keep our production schedule alive. 

This decision proved to be a major learning experience. Learning on the fly drastically reduced our delegation efficiency and forced me to shoulder complex, technical tasks entirely on my own while trying to self-learn embedded systems simultaneously. Looking back, this constraint taught me that upfront structural training is non-negotiable. For future generations of the bureau, I have institutionalized a strict strategy playbook: a maximum of 3 weeks of public outreach followed immediately by 1 to 2 months of dedicated, rigorous onboarding to ensure the team operates at peak efficiency.

## The Reality of Hardware: Managing Failure
The culmination of our technical efforts was a prototype vehicle equipped with custom active-control airbrakes and an ESP32-based avionics stack. We managed to get the vehicle flight-ready just in time for the competition. 

Unfortunately, hardware is unforgiving. Due to a single mechanical component failure, the rocket’s recovery deployment system failed to trigger, and the vehicle suffered a catastrophic crash into the ground upon descent. While the crash instantly disqualified us from continuing in the official competition bracket, I refused to let the team's momentum die in the field. 

True engineering leadership means finding value in a failure. I rallied the team back into the workshop to salvage the wreckage and pivot our objectives. We spent the remaining time analyzing the flight data and testing the internal electronics that survived the impact. Through this, we successfully validated our untested active-control airbrake loops and telemetry logs, turning a total hardware loss into a major diagnostic victory for the freshmen. 

To permanently bridge our experience gap and protect the investments of the team, I built out our comprehensive digital knowledge repository. By safeguarding our proprietary CAD, C++/Python flight code, and structural post-mortems online, the next generation of engineers won't have to start from scratch.
