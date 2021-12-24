Spaceball (0x0)
===============

Spaceball is the first game engine, with the ID 0. It has several ``0x100`` series operations, which are used for cues,
but no subs that would be useful in remixes.

Commands
---------

0x100 - Input
~~~~~~~~~~~~~
:: 

    0x100 0xXX, Y

An object is spawned (shot out of the pipe).

* ``X``: Time in ticks before input (Used: 0x30, 0x60)
* ``Y``: Object type
    * 0: Baseball
    * 1: Rice ball
    * 2: Alien

If ``X`` is equal to ``0x30`` (one beat), the low ball animation is used. Otherwise, the high ball animation is used.

0x101 - Batter costume
~~~~~~~~~~~~~~~~~~~~~~
::

    0x101 X

The batter's costume is changed depending on ``X``: 

* 0: Default
* 1: Red head
* 2: Bunny

0x102 - Camera zoom
~~~~~~~~~~~~~~~~~~~
::

    0x102<X> Y, Z

The camera zooms in or out.

* ``X``: Interpolation
    * 0: None, instant zoom
    * 1: Linear interpolation ("rough zoom")
    * 2: Cubic interpolation ("smooth zoom")
* ``Y``: Ending position of the camera
    - Ranges between 0 and 0xA (10) ticks. If the value gotten is 0xB or higher, it defaults to 4.
* ``Z``: Duration of the zoom in ticks (Used: 0x18, 0x30, 0x60, 0x90, 0xC0, 0x120, 0x180, 0x240, 0x2A0)

0x103 - Alien animation
~~~~~~~~~~~~~~~~~~~~~~~
::

    0x103<X>

Changes the animation of the alien in the middle of the screen.

* ``0``: Open UFO
* ``1``: Closed UFO
* ``2``: No alien

0x104 - Unused animations
~~~~~~~~~~~~~~~~~~~~~~~~~
::

    0x104 X

TODO: fill this in

* 0: Animation ``dance00``
* 1: Animation ``dance01``

Subroutines
------------

* ``0x56`` - nothing, unused
* ``0x57`` - Spaceball (practice)
* ``0x57`` - Spaceball (game)
* ``0x57`` - Spaceball (game + practice skipped)