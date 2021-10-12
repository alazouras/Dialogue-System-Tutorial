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

# 4) Adding a Typing Effect
Start by creating a new script called TypewriterEffect

![image](https://user-images.githubusercontent.com/91538155/136950195-5aeae258-d93f-4366-8396-87218dc29958.png)

Open up the script and delete the default Unity methods:

![image](https://user-images.githubusercontent.com/91538155/136950321-1c52efdc-180c-4ad1-b7ec-6608e437271f.png)

This public class will contain two methods:

a Driver method, responsible for running the Coroutine:

![image](https://user-images.githubusercontent.com/91538155/136950638-4279a88d-e42d-4c5c-9d6d-0d366e4d2dce.png)

And the Coroutine, responsible for drawing the text on screen:

![image](https://user-images.githubusercontent.com/91538155/136950858-c40812da-ea3e-4f12-8327-99360ad5389f.png)

First, add the Coroutine into the Driver methid like so:

![image](https://user-images.githubusercontent.com/91538155/136951297-12b8ddc0-952e-4d89-827d-af4304a36594.png)

Then, import Text Mesh Pro like in the previous script:

![image](https://user-images.githubusercontent.com/91538155/136951498-5c79512b-5175-4129-9481-58a465496f0c.png)

Next, fill in the Driver method as follows, with textToType being the string we want to type and textLabel being what we want to type that on:

![image](https://user-images.githubusercontent.com/91538155/136951762-8f0382e6-9d78-4ad2-8912-d4ffe48dc65a.png)

Cope the same parameters for the Coroutine so that you have this:

![image](https://user-images.githubusercontent.com/91538155/136951843-462ceaff-a018-4674-9953-0fce5c89a391.png)

Then fill in the textToType and textLabel here:

![image](https://user-images.githubusercontent.com/91538155/136951967-f05467dd-6019-441a-a0b6-af612d6eb86a.png)

Then, in the Coroutine, ad a float t which is, for now, equal to 0:

![image](https://user-images.githubusercontent.com/91538155/136952085-f7fd7e09-8a46-46bf-bff0-0af59846b3c0.png)

The, add a Character Index, which will also equal 0:

![image](https://user-images.githubusercontent.com/91538155/136952275-cb12c3d6-72f6-4b1d-91bb-9c376f522810.png)

The Character Index will measure how many characters we want to appear on screen at a given time, and so to measure that we type out as follows, beneath the other two lines in the Coroutine:

![image](https://user-images.githubusercontent.com/91538155/136952563-b2343573-1c92-4a5a-a592-fdc4c9e2b1f0.png)

And in there write out:

![image](https://user-images.githubusercontent.com/91538155/136952665-dadaa1d6-9324-4693-81f3-b11fe836d586.png)

Then above that write out the following so that it comes after one second:

![image](https://user-images.githubusercontent.com/91538155/136952808-02e6cfa0-57bf-4dab-9e68-9c19a7243373.png)

Below that, write out the following:

![image](https://user-images.githubusercontent.com/91538155/136953025-78c83b21-c554-48a9-b3e3-b92562428200.png)

The first line here will increment the time, and the line below that we just did will store the floored value of the line above.

We have to make sure that FloorToInt is never higher than textToType, and so to do that we add this third line here to limit the range of the charIndex:

![image](https://user-images.githubusercontent.com/91538155/136953484-52081760-8319-4404-8016-5a75d65f1392.png)

Now, we have to write the text. For that we write in this line here:

![image](https://user-images.githubusercontent.com/91538155/136953680-b6ff9fc2-0193-4d7d-af59-76617cbd3e13.png)

And then, outside of the while void, make sure that the textLabel.text is equal to textToType in the first place:

![image](https://user-images.githubusercontent.com/91538155/136953838-162260a8-98dc-4e6c-aca5-589716e93c40.png)


# 5) Testing if the code works
Now, to test, pop into the DialogueUI script, and get rid of the part of the script here:

![image](https://user-images.githubusercontent.com/91538155/136954292-874d46b7-e9ac-4692-8c20-823c78c93e24.png)

And bring in the TypewriterEffect script by using GetComponent and write out the following, including something for the code to type out:

![image](https://user-images.githubusercontent.com/91538155/136954685-adb5ba2d-624f-4e1e-a673-4d7e08d7dd57.png)

Go into Unity and add your TypewriterEffect script to the Canvas:

![image](https://user-images.githubusercontent.com/91538155/136954880-38171f2e-2aec-43d5-b94e-9c32567068cc.png)

And hopefully that should work, though rather slowly. To control the speed, we now have to go back into the TypewriterEffect script and add a new variable called typewriterSpeed and make it a serialised field:

![image](https://user-images.githubusercontent.com/91538155/136955415-be746055-ad9b-4be0-bc15-093492b4c288.png)

Scroll down to the reference to deltaTime and add the following to that line

![image](https://user-images.githubusercontent.com/91538155/136955687-e9e440bb-b421-4eee-987b-c77e72148419.png)

Now, save that and go back to Unity, where under the TypewriterEffect script we can now adjust the speed of the text typing in the Unity editor, and the text should type much faster now.

To give us a much clearer picture of the speed, in the TypewriterEffect script under the IEnumerator and add this, which will make the text wait for 2 seconds before starting to type:

![image](https://user-images.githubusercontent.com/91538155/136956063-d69dd767-cdae-4f20-ae6e-14372dfa1599.png)

And finally, to make sure New Text doesn't show up in the final thing before the script starts typing, add in this line:

![image](https://user-images.githubusercontent.com/91538155/136956521-953367d0-4bbc-4c55-94f5-384ad95e8605.png)

# 6) Making text appear when you click
To have multiple, clickable lines of dialogue, store each line of dialogue in a public array that can be changed in the inspector in Unity and make an integer variable to sort through each item in the array.

![image](https://user-images.githubusercontent.com/91538155/136961109-22669c9b-8aa2-4a56-a1d3-6a2adff06810.png)

Change out the "text" for the following to paste the first line of text in the array:

![image](https://user-images.githubusercontent.com/91538155/136961319-d82b80e4-941b-4c3d-80f6-676973d4b71c.png)

Then, put this into an if statement to trigger on Space:

![image](https://user-images.githubusercontent.com/91538155/136961697-0283a9fe-96fb-4c37-a2b8-4a7031b38472.png)

Then, add Index++ to allow for moving onto the next line in the array:

![image](https://user-images.githubusercontent.com/91538155/136961796-9d6f6b89-18b1-404f-bdf8-e32797ac9dc4.png)

Finally, add a check to prevent an error when running out of dialogue:

![image](https://user-images.githubusercontent.com/91538155/136962242-93debf9d-62d7-4194-893d-f51aab204a79.png)
