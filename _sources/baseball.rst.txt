=============================================================
UAVBaseball: Simulating Baseball Pathing with the CoDrone EDU
=============================================================

.. image:: _static/__baseball/baseball.png
    :align: center

**Videos**:

    - `Learning the CoDrone EDU <https://youtu.be/gT2dIVrDKJQ>`_
    - `Writing a Context Manager for the Codrone EDU <https://youtu.be/8owxnUHKqYI>`_
    - `Traversing a Base <https://youtu.be/n5RHxK8Ozew>`_
    - `Multiple Bases <https://youtu.be/xHTBC7PvPYI>`_

**Reports**: Download the :download:`concatenated reports <_static/pdfs/baseball_reports.pdf>`.

**Code**: View the code repository `on GitHub <https://github.com/tjdwill/UAVBaseball>`_.


**Robot(s) Used**:

- CoDrone EDU (Robolink)

Synopsis
========

In this project, I aimed to use a quadrotor UAV (Robolink's CoDrone EDU) to simulate the base-rounding motion behavior seen in the game of baseball. To simplify the task a bit, the bases were arranged in a rectangular grid rather than a diamond, allowing direct translational movements along the ``x`` and ``y`` axes of the drone's motion frame.

Through this project, I was able to:

- Gain familiarity with aerial robots
- Extend the programming functionality of a programming library
- Simulate a real-world game by distilling defining characteristics
- Learn to utilize logging for debugging and general status recording

One fun challenge in this project was determining how to detect the bases given the drone's lack of visual peripherals. The CoDrone EDU has color detection, but it requires the drone to be grounded to work properly, meaning it was not a viable option for detecting a base mid-flight. Instead, I used the drone's bottom-range sensor to detect significant changes in relative height between each base. Detailed information can be found in both the reports and the latter two videos linked above.

Reflection
==========

This project, unfortunately, did not pan out as desired. While each individual
subsystem performed well (identifying bases, setting waypoints, color
detection, flight directions, and determining the number of bases to "run"),
unidentified errors would occur after the drone rounded the second base
consecutively. Navigating from base-to-base as singles worked well, but going
beyond a double resulting in error. Nothing in the code stood out as logically
incorrect after many debugging sessions, so it is possible that there is a hardware malfunction (especially given a small number of flight collisions
when gaining familiarity with flight).