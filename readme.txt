This is a plugin for the Phaser framework that enables camera shaking.

To include this feature in your Phaser game, you will need to include the cameraShaker.js file in your HTML document.

Within the game, in your create function, add the following text: this.game.cameraShaker = this.game.plugins.add(Phaser.Plugin.cameraShaker);

When you want to call the cameraShaker,  you can do so with the default settings by calling: this.game.cameraShaker.setupShake(50);

This will cause the camera to shake for 50 frames. 

*** Features ***

This implementation has several options for controlling the shaking. These are set by passing additional arguments to the setupShake() function.

At minimum, it expects 1 parameter, which is the number of frames to shake. It can accept up to 5 parameters. They must be used in the order outlined below.

The full syntax is as follows:

this.game.cameraShaker.setupShake(shakeFrameCount, shakeAmplitude, shakeMode, shakeVolume, shakeVolFactor)

shakeFrameCount: required - this is the number of frames to shake the screen

shakeAmplitude: optional (default: 20) - this is the displacement of the camera during each frame. Larger numbers make the shaking effect more dramatic

shakeMode: optional (default: xandy) - this controls the motion of the camera. 
           Modes are: 
	   'xandy' - this shakes both x and y axes
	   'lefttoright' - this shakes only the x axis
           'uptodown' - this shakes only the y axis
           'rand' - this shakes both x and y axes by a random amount, up to +/- shakeAmplitude

shakeVolume: optional (default: 'constant') - this controls how the amplitude evolves frame to frame. 
	     Modes are:
	     'constant' - shakeAmplitude does not change frame to frame.
             'crescendo' - shakeAmplitude increases each frame, by the amount shakeVolFactor
             'diminuendo' - shakeAmplitude decreases each frame, by the amount shakeVolFactor. It will stop decreasing at 0.
shakeVolFactor: optional (default: 0) - this controls the amount by which shakeAmplitude increases or decreases in 'crescendo' or 'diminuendo' mode

