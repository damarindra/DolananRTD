.. _doc_intro:

Structure of Dolanan
====================

Dolanan is just an extension of MonoGame Framework, I recommend to learn from `MonoGame Documentation <https://docs.monogame.net/articles/getting_started/getting_started.html>`_, it is just a bit, not much reading and it will help you in the future! Dolanan using EC, not pure ECS. 
Entity and Component, and allow OOP (with limitation). 

Done reading `MonoGame Documentation <https://docs.monogame.net/articles/getting_started/getting_started.html>`_? Okay, you are ready then.
First, let see class :code:`Dolanan.GameMin`

GameMin
-------

:code:`Dolanan.GameMin` derived from :code:`Microsoft.Xna.Framework.Game`, which is provide all the core methods.

Update & Draw
~~~~~~~~~~~~~

:code:`GameMin` already used some methods such :code:`Update` and :code:`Draw`. You can't just override that function because Dolanan already take care some basic functionality, but Dolanan provide other similar function, you can override :code:`Process` and :code:`DrawProcess`. With this approach, you still have access for :code:`Update` and :code:`Draw` whenever you need to access that function. To be honest, it is rare case if you need that function.

:code:`BackDraw` is a function to draw directly in front of your game. :code:`BackDraw` usually used to draw UI and debugging stuff.

Initialize & LoadContent
~~~~~~~~~~~~~~~~~~~~~~~~

Is still the same as MonoGame function, you can override it in case you need it.

.. code-block:: csharp

	protected override void Initialize()
	{
		// Add your initialization logic here
		GameMgr.Init(this);

		//Some code
	}

BackBufferRender
~~~~~~~~~~~~~~~~

BackBufferRender take care window / resolution change, also this function draw the final Game World (exclude Window UI, etc).

Debugging Shortcut
~~~~~~~~~~~~~~~~~~

+------------+----------------------------------------------------------------+
| Shortcut   | Functions                                                      |
+============+================================================================+
| ESC        | Close Window                                                   |
+------------+----------------------------------------------------------------+
| F3         | Show FPS                                                       |
+------------+----------------------------------------------------------------+
| F4         | Show Collision                                                 |
+------------+----------------------------------------------------------------+

Useful Method and Member
~~~~~~~~~~~~~~~~~~~~~~~~


GameMgr
-------

:code:`Dolanan.Controller.GameMgr` is a manager, this class rule anything and provide you ability to access to :code:`Dolanan.GameMin` and :code:`Microsoft.Xna.Framework.Graphics.SpriteBatch` instance.