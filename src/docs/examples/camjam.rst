.. _example_camjam:

CamJam Edukit 3 Robot
=====================

This example drives the `\CamJam EduKit 3 <https://camjam.me/?page_id=1035>`__ robot and is based on
:ref:`example_tiny4wd` with some modifications by Mike Horne to support the different motor driver board that kit uses.

The code below shows, with a few extra bits and pieces needed in case you're running without the robot libraries, how to
use this library to drive it around. The left analogue stick controls the robot, and the HOME button exits.

.. image:: edukit3.jpg

.. literalinclude:: ../../../scripts/camjamedukit3.py
    :language: python
    :linenos:
