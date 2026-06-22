---
layout: project-detail
title: "E-Town Rocket Bureau"
description: "Co-founding, organizing, and leading a High School rocketry team."
# image_path: "assets/images/full assembly render 1.png"
tags: ["Leadership", "Aerospace"]
---

## Summary
I co-founded the E-Town Rocket Bureau---my High School's active-control rocketry team---in August of 2024, along with Founder Eli Corr and Co-Founders Tristan Schultz and Peter Elbakian.

I've since served as Chief Engineer, with my tenure ending in May of 2026. Having had the privilege to serve for two years, I've learned a great deal about leadership in engineering contexts. I built our organizational structure from the ground up and created our broader school rocketry website. The website showcases our work, and---crucially---stores our knowledge, allowing future generations of engineers to gain a headstart. 

Starting out completely new to rocketry, I've had the opportunity to absorb a massive amount of technical material. I've since gained proficiency and hands-on experience with Python, C++, active control systems, software-in-the-loop (SIL) PID optimization, embedded systems, and a whole host of supporting software.

<figure>
<img src="{{ 'assets/images/etrb-2025-team.jpg' | relative_url }}" alt="2025 Team Photo">
<figcaption>2025 Team Photo</figcaption>
</figure>

## Recruitment and Onboarding Bottlenecks
Our first year was primarily focused on gaining basic technical experience and defining our long-term goals: competing in the American Rocketry Challenge (ARC) and pioneering actively-controlled model rocketry at our school. However, graduation hit us hard at the end of that first year, claiming half of our core membership. 

To rebuild, I spearheaded an outreach and recruitment campaign heading into the fall. By leveraging the Freshman Activity Fair, presenting to incoming students, and engaging directly with parents, we achieved a 75% YoY club growth rate, ultimately scaling our roster by 250%. 

This massive influx of new members brought an unexpected leadership bottleneck: we suddenly had a highly enthusiastic but entirely inexperienced freshman cohort. Balancing college applications, school, and rocket development left little room to design a formal training pipeline on the fly. I chose to have newer members learn CAD and core aerospace concepts "on the go" to keep our production schedule alive. 

This decision proved to be a major learning experience. Learning on the fly drastically reduced our delegation efficiency and forced me to shoulder complex, technical tasks entirely on my own while trying to self-learn embedded systems simultaneously. Looking back, this constraint taught me that upfront structural training is non-negotiable. For future generations of the team, I have institutionalized a strict strategy playbook: a maximum of 3 weeks of public outreach followed immediately by 1 to 2 months of dedicated, rigorous onboarding to ensure the team operates at peak efficiency.

## Hardware Failure and Next Steps
The culmination of our technical efforts was a prototype vehicle equipped with custom active-control airbrakes and an ESP32-based avionics stack. We managed to get the vehicle flight-ready just in time for the competition. 

Unfortunately, due to a single mechanical component failure, the rocket’s recovery deployment system failed to trigger, and the vehicle suffered a catastrophic crash into the ground upon descent. Because of the impact, we didn't recover any flight data from the launch, and we were instantly disqualified from continuing in the official competition bracket. 

Instead of letting the team fold in defeat, I rallied the members back into the workshop to salvage the wreckage and pivot our objectives. While the hardware was lost, the engineering goals weren't. I cheered the team into shifting our focus toward building and flying a second vehicle. We are currently using this second program to properly validate the core systems that went untested during the initial crash, ensuring our custom airbrake loops and avionics get the real-world flight validation they need.

## Building the Institutional Repository
To permanently bridge our experience gap and ensure the freshmen wouldn't face the same resource bottlenecks I did, I spent significant time building out our comprehensive team website. 

The site serves as a secure, centralized digital repository designed for long-term organizational continuity. I structured it to house all of our internal technical and organizational knowledge, including our proprietary CAD files, custom C++ firmware for the avionics stack, Python code used for our software-in-the-loop control simulations, and full club history. By documenting our structural post-mortems, design files, and code repositories in a clean, accessible framework, we've turned a temporary club into a sustainable engineering pipeline. Future generations of high school engineers can now bypass basic logistical hurdles and build directly on top of our existing technical foundation.

Beyond the purely technical data, I heavily documented our internal organizational structure to serve as a blueprint for future student leadership. This includes the division of labor between sub-teams, tracking tools for milestone deadlines, and template documentation for managing club finances and inventory. I also included a dedicated section for administrative and outreach playbooks, mapping out exactly how to interface with school administration, manage public relations, and coordinate parent engagement based on what worked during our recruitment drives.

Crucially, the repository serves as a medium for program recommendations and final reflections. I wrote extensive post-mortems detailing our recruitment strategies, the exact timeline constraints of the competition calendar, and the hard lessons learned from skipping a structured onboarding process. By leaving a transparent record of our operational failures—and outlining clear solutions like my 3-week recruitment and 2-month training rule—the platform balances technical theory with practical leadership guidance. It ensures that future club members don't just inherit a box of rocket parts, but a functional, adaptive organization.
