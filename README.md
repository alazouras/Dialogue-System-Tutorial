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
First, create a C# script in the scripts folder and name it DialogueUI, and open it up. This script will be the main component in having text appear in the text box at all:

![image](https://user-images.githubusercontent.com/91538155/136946094-bbd7c9d4-81fc-4a88-9047-e31c7d7d1fa2.png)

Then, add the script to the Canvas:

![image](https://user-images.githubusercontent.com/91538155/136946360-a287be08-a89e-4a38-a0fd-ce300f635640.png)

Next, open up the script and delete everything that has been highlighted so that you're left with a mostly blank script:

![image](https://user-images.githubusercontent.com/91538155/136946743-007ddcb7-6f78-4b4d-9cae-7b95cb16eeb1.png)
![image](https://user-images.githubusercontent.com/91538155/136946835-3255e97b-6055-475f-b812-0c48864de74a.png)

Add TMPro to the using list:

![image](https://user-images.githubusercontent.com/91538155/136946945-672e7956-5c46-47b5-8709-832ddef45b49.png)

Then, reference the Text Mesh Pro with the following code underneath public class:

![image](https://user-images.githubusercontent.com/91538155/136947279-6a0643ec-4b05-438b-b654-56bbddc850ac.png)

You should now have an empty TMPro section in the script under Canvas components:

![image](https://user-images.githubusercontent.com/91538155/136947460-f85c3b34-8ed4-4136-8d3b-38ab7949b28f.png)

Drag your Text from the Dialogue Box drop down into the empty section:

![image](https://user-images.githubusercontent.com/91538155/136947620-c1aef376-e5f6-4e31-a3e4-461054920119.png)

Next, go back to the script so that we can write a method that draws some text to make sure that it works. To do that, write out a Start void, and in it write out the code as follows. After writing out your text, test out whether having a second line works by adding a \n for new line, and write out your second line:

![image](https://user-images.githubusercontent.com/91538155/136949511-ae0b607c-40f3-4bdf-ab84-cd8c6de7f51d.png)

Once you go back into Unity and press play, you should have something like this:

![image](https://user-images.githubusercontent.com/91538155/136949639-e02df291-0d7b-42f4-b9b2-2b36e8fef3dc.png)

