.. _changelog-label:

Change Log
==========

.. note::

    This documentation, and the code it documents, is the original SixAxis controller code from my PiWars_ 2015 robot,
    Triangula. It has subsequently been extensively modified, and now supports the PS4 and XBox One controllers in
    addition to the original support for PS3 controllers.

    A newer version was used for my PiWars_ 2017 entry, this time using a PS4 controller. Several other robots in that
    year also used the library, and my aim is to make this the definitive library for connecting game controllers to
    Python code, especially for robots (but it'll work elsewhere if needed!)

Version 2.3.0
-------------

Significant refactorying and reworking of the controller discovery process. Can now bind to multiple controllers in a
single call or resource, and can be more specific about exactly what capabilities are required when discovering
controllers. See :ref:`discovery-reference-label` for more details. Updated examples to match. Added support for the
3dConnexion SpaceMouse Pro (wired), although I suspect I'm the only person who'll use it...

Version 2.2.0
-------------

Added support for device LEDs where applicable. If your controller supports setting LEDs, these can be accessed through
controller-class-specific methods, i.e. :meth:`approxeng.input.dualshock4.DualShock4.set_leds` for the DualShock4.
There's no general way to do this as all controllers are different. See :ref:`sys`

Version 2.1.0
-------------

Updated evdev dependency to 8.1.0, required for newer kernels. Added support from Tom Broughton for 8BitDo SF30 Pro
controllers. Added support for multi-node controllers under latest kernels, tested with 4.15. I strongly suggest using
this kernel version. Sony controllers now both support motion sense, with the PS3 supporting pitch and roll and the PS4
supporting pitch, roll and yaw rate. In addition, the PS4 now exposes two extra axes, 'tx' and 'ty' representing the
most recent contact point on the touchpad, normalised to be zero in the centre of the pad and -1 to 1 at the edges.

Note that with the more recent linux kernels some of the event codes have changed. I've updated those used by the Sony
controllers but not others, it's likely that they'll need fixing. Conversely, this release will not work with older
kernels. If you are using a 4.9 kernel (i.e. the default for the Raspberry Pi) you should either freeze on the previous
release of this library, or upgrade your kernel.

Logging is now debug level by default, so shouldn't spam the console with messages about unknown axes unless you ask
it to do so.

Version 2.0.3, 2.0.4
--------------------

Updated evdev dependency to 0.7.0, added logzero 1.3.0 and moved print() statements to use logging instead. This should
make cases where the previous version was printing reams of messages about missing axes on certain controllers more
sane. Also updated the show_controls.py script to handle out-of-range axis codes without blowing up. Fixed default log
levels in 2.0.4 to inherit properly unless explicitly set.

Version 2.0.2
-------------

Minor change to allow recognition of newer DS4 controllers with a different product ID

Version 2.0.1
-------------

Added support for the PiHut own brand controller, code from Mike Horne (see :ref:`api_pihut`)

Version 2.0.0
-------------

Simplified API, breaks compatibility with previous versions but allows for more pythonic access via property accessors
and overridden attribute access. The API described at :ref:`simple_api` should now be all you need!

Version 1.0.7
-------------

Added support (pending documentation!) for the WiiMote controller, contributed once again by Keith Ellis! It also adds
controller disconnection detection, enabling :ref:`example_failover` .

Version 1.0.6
-------------

Minor tweak to fix some of the internals

Version 1.0.5
-------------

Added support for the Wii Remote Pro from Nintendo - I'd have added the WiiMote at this point as well but my cheap
clone was dead on arrival...

Version 1.0.4
-------------

Added support for the Steam Controller from Valve, although it needs an extra third party user space driver
(see :ref:`api_steamcontroller`)

Version 1.0.2
-------------

Added support for the Rock Candy PS3 clones thanks to Keith Ellis.

.. _PiWars: http://piwars.org
