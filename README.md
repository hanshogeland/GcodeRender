# GcodeRender on layer images
Experimental Gcode render and CNN repo to use for Duet3

This is not ready code, just a start

Overall purpose and kind of goal (this will probably change):

Preparation on SBC:
1.	User runs a dummy gcode -the printer will move the desired layer height and a picture is taken along with the angle of the camera (I have a Intel D435 + a MPU-6050 chip connected to a Arduino Uno to get the angle) (If you had a D435i the angle would be given directly) in this step I´d like to have a nice way of running Python script in the Gcode on the SBC (future improvements)
2.	All empty layer pictures are added on the host machine – where the training of the model are run
 
Execution:
1.	User slices the model – get Gcode
2.	Save the Gcode in a folder/area – (or send to a cloud solution)
3.	A Python script renders out each layer images – using the previously created layer images with the given angle and a +- angle difference
4.	A following script creates a CNN model of all the images (one for each layer or one for all layers)
5.	The CNN model are saved and sent back to the SBC
6.	While printing a picture is taken of each layer and a script/service on the SBC are continously predicting the % correctnes of the print
a.	If under a certain % send a notification via email or other
