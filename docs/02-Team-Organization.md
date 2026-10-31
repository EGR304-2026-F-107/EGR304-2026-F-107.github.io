---
title: Team Organization
---

## Team Charter
> Our team is committed to designing and building a robotic arm system mock up (temporary) that actually works. We value clear communication, shared accountability, and treating this project as more than just an assignment: it's a chance to build real engineering skills and something worth putting in our portfolios.<br>
> We agree to show up prepared, communicate honestly when something isn't working, and support each other so that every member leaves this project having learned something real and having contributed meaningfully to the final result.<br>

## Product Mission Statement
 > Our mission is to design a low-cost, modular desktop robotic arm system mock up that enables to achieve precise, repeatable automated pick-and-place tasks at a much lower barrier to entry, freeing up human effort for higher-value work.

## Team Members and Roles

| Team Member | Subsystem | Responsibilities |
|---|---|---|
| Yixiang Ren | Arm Motion Control | Arm joint motor and H-bridge, 6 V / 5 V power for the arm board, ARM_IN_POS and GRIP_CMD outputs |
| Canyon Miller | Gripper & Object Handling | Servo gripper, FSR 402 force sensing, OBJ_HELD and GRIP_FORCE outputs |
| Dunyue Yang | User Controls & Safety | Emergency stop, start/pause and speed inputs, status LEDs and buzzer, SAFE_OK / RUN_REQ / SPEED_SET outputs |

Each member owns one board end to end (block diagram, component selection, schematic, BOM and power budget, documented in their individual datasheet). Team-level work, including the ribbon pin map, the team block diagram, the software proposal and this website, is shared by all three. More detail on team goals and communication is in the [Appendix](Appendix/App-Team-Org.md).

