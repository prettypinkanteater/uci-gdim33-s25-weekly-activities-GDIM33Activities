# GDIM 33 In-Class Activities
## W1

### Activity 1
[Inspo Board](https://www.pinterest.com/cordonxrose/gdim33inspo/)

1. The aesthetics I'm interested in are sketching/drawing, modern + gothic architectural styles, varying natural topography, beautiful women with beautiful hair 😊😊😊 (my lovely art muses) = the human form, and water!!!

	The mechanics/game genres that I am most interested in are point-and-clicks and open-world exploration in nostalgic, urban, fantastical, and natural environments!

2. Bryant Dai also likes a variety of game genres that are similar to me (story, fps, RPGS). He also likes Genshin and draws stylized work like me! Furthermore, he appreciates the details in game aesthetics.

3. We have some overlap for FPS games and though I've never played Beat Saber, I think rhythm games are interesting.

### Activity 2
<img width="960" height="720" alt="GDIM 33 Break-down (1)" src="https://github.com/user-attachments/assets/e6fe024c-86f1-4e80-a2e2-31916bbcd4d9" />

## W2

### Activity 1
<img width="1292" height="1131" alt="image" src="https://github.com/user-attachments/assets/1e094c6d-b39a-4c99-83d0-a5305e82ab84" />

### Activity 2
1. It is advantageous to save the event name as a scene variable so that other graphs, not only the state machine, can access it to trigger it.
2. I used one Debug.Log() to test if the transition from the explore to dialogue state occured.

3 and 4 because they're pretty similar: 

The Set Cursor Lock State is relevant to my Vertical Slice because I have a Papers, please-like game that will have two primary game states. Specifically, this means the body examination stage to identify anomalies on NPCs and the dialogue stage. Both stages will allow for different behaviors, like the cursor being locked during dialogue and it being unlocked during examination so that the player can click on body parts to investigate. An additional example to state-dependant behaviors includes certain UI being visible, like the dialogue box in the dialogue state and the rotate body buttons during the examination stage.

## W3

### Activity 1
What is playable in my build right now is dialogue with the patient NPC and change of game state indication. Although I omitted the initial dialogue in my breakdown, I added it just to quickly test state transitions.

My goals are to see if the dialogue advance properly.

Team Members: Me, Lawrence Li, Bryant Dai

#### Playtesting Notes

- name tag not resizing properly
- start game less suddenly

### Activity 2
1. Yes a writer could add more dialogue to this setup by creating more dialogue node scriptable objects.
2. The limit that there is to the number of dialogue nodes that the writer could create would possibly be any new features that require more information based on displayed dialogue. An example would be the name of the current character talking as a member variable of the Dialogue Node class that could be accessed and displayed as it changes.
3. The purpose of the "Regenerate Nodes" button is to refresh the nodes avaliable/visible in Graphs, particularly user created ones.

## W4

### Activity 1
1. Animate Nail and play Particle System (reaction)
	1. Create a Timeline GameObject with Playable Director Component, a new Timeline, and the corresponding Timeline Asset/Playable that will be attached to the component.
	2. Attach nail gameobject to new Animation Track and record animation, play Timeline to proview.
	3. Attach blood particle system gameobject to Activation Track and place it so that it starts playing at the end of the above animation, preview again to ensure it also works.
2. Update total attributes marked at end of cutscene by communicating with the GameController using Timeline signals.
	1. Add Signal Marker/Emitter to the end of the particle system track, create a corresponding new Signal Asset called "Nail Inserted", and a Signal Reciever component to the GameController gameobject. 
	2. Create a new public method to Debug.Log that shit!!! in the GameController script and add it as the reaction method to test if the Signal is successfully set-up, this should Debug.Log a message if it works.
	3. Change the reaction method to the method in the GameController that updates the amount of attributes marked and the UI showing this, if it works it should do just that.

### Activity 2
I mostly tried to accomplish clicking and dragging of the nail :)
Wasn't the most fruitful attempt but I learned some things about mouse position!
	

## W6

### Activity 1
1. The basic gameplay is more fully implemented. You can change to the examination state and consequently click on the patient to investigate suspicious attributes, rotate their body, "end" the exam, and identify them.
1. [Link](https://pinkanteateraj.itch.io/gdim-33-vertical-slice-playtest-2)
1. Do the buttons function appropriately. 

#### Playtesting Notes
- Disable attribute buttons once the end of examination occurs
- Bring Galatea's body higher up to make the second attribute more visible

### Activity 2
1. The multiply setting of the blend node makes the resulting color darker + less saturated because the RGB values are floats and when floats are multipled, it results in lower floats.
Because each float represents color channel's saturation, if the resulting color has lower RGB values, it will be less saturated. 
1. If we use Multiply to combine Alpha values, the resulting value will be more transparent because, similarily to above, float multipication results in a lower number and in regards to the value of alpha, a more transparent look.
1. The shader gets these UV values from the vertices on the Shiba mesh.
1. Manipulating colors with math sounds ??? I am tired so not a large reaction. I already kind of knew about alpha/opacity because I've used image manipulation software before. At least math will be useful in the case I want to darken a color.

## W7

### teehee

1. The data for the vertex color node comes from the Shiba mesh.
2. The color on the shiba in step 3 is blended because of vertex interpolation blending the RGB values of each vertice in a polygon together together.
3. The shiba is less detailed than the shiba rendered last week because the vertex color is more like a base color rather than painted details for a mesh. It can be useful for more simple meshes.
4. There is a spot on the back leg that looks wrong compared to the surrounding vertex normals.
5. Another piece of data I could imagine testing with the debug shader is whether or not the UV coordinates in vertices are accurate in relation to mesh texture. This would be helpful to see if the texture needs to be edited.
6. There is an error in the lighting in step 5 because surface normals, in this case the ones on the Shiba's mesh and the light, are opposite facing angles. Getting the dot product would result in a negative product, which means the light logic essentially is rendered backwards because each vertex surface normal/direction is seen as its opposite.
7. I think we set the blending mode to Additive because it adds RGBA values together to make colors more opaque with a higher alpha value and colorful with higher RGB values.

## W8

### Activity 1:
1. I added a UI panel that appears once the shift ends. I plan to make this change colors with visual scripting based on shift quality asseessment!
2. [Link](https://pinkanteateraj.itch.io/vertical-slice-playtest-2)
3. Is the core loop smooth?

#### Notes:
- uh resize ui / emphasize neeed to fullscreen 1 (<- bryant hijacked my devlog and he forcibly the numerical characteer "1". this is without my permission and on MY property.)
- remove button text on nail pile button lol
- if investigating first attribute and dragging nail to second one (uninvestigated), can skip investigation phase
- add differentation of dialogue speaker
- add visual/textual cues to guide player to understand what to do - a "tutorial" patient 

### Activity 2A:
Sorry I'm still tired even submitting this late and I was busy again so I can't be confident all of these are correct...
1. We are utilizing the stencil buffer to determine when to render the Outline and Cel shading.
2. I didn't really answer this while working on it so hopefully it's ok to answer after I've finished all the steps. Anyways, from my point of progression, I think the object that is being drawn twice is the Shiba. It is being drawn twice because the stencil buffer is keeping the shiba's drawing and the DrawOpaqueObjects pass is also keeping it.
3. Sorry I cannot think probably but likely something with the Stencil Buffer pass!
4. Anything that is not greater than 1.
5. We add instead of multiply to get the colored cel shading by adding the color to the light logic.
6. Changing the layer the Shiba is on enables/disables the outline effect because the Renderer feature only draws for objects with that specific layer.
7. Setting the shadow color to white removes the lighting because there is genuinely no "darkness" in the shade, white.
8. Maybe? Because the material is a project asset so the Instance, the copy, may lead to having to run more logic the next frame rendered.

#### Notes:
-  Instance - copy!
	- Reference value changes property with vs at runtime
- Variable - og!
- Modifying original settings during runtime
- Runtime is when game is playing