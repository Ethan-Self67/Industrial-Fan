Industrial Test Fan Setup

Project Overview:
This project tests airflow efficiency across different fan blade geometries for Athule clients, similar in concept to a common computer fan but scaled up for real testing data. The setup is built around a 5-foot-long cylinder with 3D-printed flow straighteners inside, along with openings that let air flow in and get measured by sensors both before and after passing through the blade. This lets us compare how different blade geometries affect airflow efficiency under consistent conditions.
![Schematic](

My Role:
I independently designed the full circuit schematic for the sensor and microcontroller setup, then worked alongside two coworkers on the physical build and mechanical design of the test cylinder itself. My part covered wiring the sensors, setting up the I2C communication between multiple microcontrollers, and making sure everything read data on the same clock and data line without conflicts.

Design Process:
We had a tight budget of about $100 for materials and a two-week timeline to get the whole thing built and working. That meant being deliberate about every part we used, since there wasn't room to over-order or waste anything. The 3D-printed flow straighteners took a good amount of trial and error to get right, since there were a lot of fine details to render correctly for the print to actually straighten the airflow the way it needed to.

Challenges & Solutions:
The biggest issue came from a wrong assumption. We thought the microcontrollers had pull-up resistors built in for I2C, so we didn't add any externally at first. Once we realized that wasn't the case, we had to go back and figure out where pull-up resistors were actually needed to get reliable communication across all the microcontrollers on the shared I2C bus. That single misunderstanding taught me a lot about how I2C actually works at the hardware level, not just in code.

Outcome:
The final setup turned out well and was straightforward to test once you were familiar with all the individual components. I came out of this project with a much better understanding of I2C connections, specifically how to get multiple microcontrollers talking reliably on the same bus, which is something I hadn't had to solve at that level before.
