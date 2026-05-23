## Project Page Editing
Photos are automatically sized to fit the width of the text area:
    ![ETRB 2025 Team Path]({{ 'assets/images/etrb-2025-team.jpg' | relative_url }})

If you want custom sizing, do either of these:
    <img src="{{ 'assets/images/etrb-2025-team.jpg' | relative_url }}" alt="Team Picture" style="width: 50%;">
    <img src="{{ 'assets/images/etrb-2025-team.jpg' | relative_url }}" alt="Team Picture" style="width: 450px;">

To add captions, do this:
    <figure>
    <img src="{{ 'assets/images/etrb-2025-team.jpg' | relative_url }}" alt="2025 Team Photo">
    <figcaption>2025 Team Photo</figcaption>
    </figure>