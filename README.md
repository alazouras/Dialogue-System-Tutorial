# Dialogue-System-Tutorial
This shows how to implement a simple dialogue system in 2D



# Pre: Settings
Make sure the game project is in 1920x1080 pixel measurements, rather than just 16:9 (default setting) in order to allow for specific measurements for the sizes of the text box etc to be down to the pixel.



# 1) Creating the dialogue box
Start by creating a canvas in the hierarchy of your project, as follows:

![image](https://user-images.githubusercontent.com/91538155/136015187-666a61d9-f32d-4de6-b130-e51f7ad93854.png)


Then, add an empty game object within the canvas as a child, and name is DialogueBox:

![image](https://user-images.githubusercontent.com/91538155/136016178-f531284d-b2cb-4cd4-9ab4-3eaeaae39c3e.png)


After creating that, click on the button for orientation, then Shift+Alt to have the option to put the box at the bottom middle of the canvas, then proceed to make the object 1400 pixels wide and 250 pixels tall:

![image](https://user-images.githubusercontent.com/91538155/136016944-6244792c-bc12-4185-8a54-439fd7fa702d.png)


Then, add some graphics to the text box so that it can be seen in the Canvas, and to do that you right click on DialogueBox, UI, Image and fill the box by clicking the same orientation button, Shift+Alt and clicking the fill button:

![image](https://user-images.githubusercontent.com/91538155/136017368-8bae038b-396f-4c4b-b250-142d7feb06db.png)
![image](https://user-images.githubusercontent.com/91538155/136019360-e5265072-8588-4638-bbef-0bb3db8596dc.png)


# 2) Adding Your Text
For text, clock on the DialogueBox in the hierarchy and add TextMeshPro as follows and click Import when prompted (not on Extras, just on Essentials):

![image](https://user-images.githubusercontent.com/91538155/136020197-efdcd214-d22c-4eda-84dc-154135d23648.png)

Then, make the text actually visable against the white background by changing the colour to black in the Vertex Colour box, then make the text box fill out the DialogueBox the same way as before with the orientation option pop-up:

![image](https://user-images.githubusercontent.com/91538155/136020531-88263a64-f728-4800-ab20-afd560bb6c10.png)

Having about 3 lines in the box is recommended size and fit wise, so to do that copy+paste the New Text text in the right Text Input option box so that you can see how big 3 lines is, then scale up the font size to about 60:

![image](https://user-images.githubusercontent.com/91538155/136020990-a6722e9d-8f2e-43cc-9352-9f00cb7ee9f2.png)
![image](https://user-images.githubusercontent.com/91538155/136021109-473204f7-1bec-4c62-bc04-7df12312bd81.png)

Finally, have a slight offset for the text just so that it's not directly against the edge of the box by changing the offset next to the orientation box, with about 20 pixels of line spacing:

![image](https://user-images.githubusercontent.com/91538155/136021388-429c21db-c92a-472f-8c60-11d20d40f4b0.png)
![image](https://user-images.githubusercontent.com/91538155/136021625-f16579f8-fef7-400d-a96e-12a0e84b4115.png)


# 3) The Actual Code
