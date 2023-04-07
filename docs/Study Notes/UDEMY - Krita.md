circle and rectangle tool
- Shift will make it perfect circle or perfect square
- ctrl will make the pivot point the starting mouse location rather than the top corner of shape
- alt will let you drag shape around while creating

ambient light: type of environment lighting where lights are coming from all directions uniformly
	(ex: sun)

back light: special light source placed on dark areas to help communicate object's shape
	or silhouette or to convey certain mood
	(ex: campfire near tree)

rimlight: special light sources places on edges of object's silhouette to help
	depict its shape or gain viewers attention
	using excessively will make illustration look fake
	

reference images
rough sketch + corrections -> blue
final sketch + corrections -> black

layer sorting
 - main groups (background, middle ground, foreground)
 - sub groups, ex middle ground -> 
	cliff/grass/tree(everything) 
        or cliff/tree and grass(keep touching color layers seperate)

base colors: try to avoid colors too close to black, white, or fully saturated 
	(i,e pick more near center of color square)

local shading: small detailed shadows inside the drawing (ambient occlusion), 
	subtle shadows exist in crevasses, corners, holes, etc
	essential on areas occluded from ambient lighting
	call it local shading because adding small sized shadows and AO is just one kind
	local shading layer -> 
		- turn on alpha inheritance so it wont go outside of base color layer
		- switch layer blending mode to multiply(since its for shadow color)
		- use outline tool to select an area to add shadow to
		- use airbrush tool with around 50% opacity
		- use black or a darker shade of color
		- contact with other layer like tree contacting grass should be darker
		- use smear brush to soften out the shadow

global shading: 
	- large sized shadows
	- casted shadows(shadows emitted from objects that fall onto other objects or areas)
	- turn on alpha inheritance and switch blending mode to multiply
	- use airbrush tool
	- ex: top of tree branches/trunk getting shadow from leaves in canopy 
	- ex: tree with light coming from top right would have left side darker
	- ex: grass around tree opposite of main light
	- select areas to darken, use airbrush with 50% opacity and darken

highlights: 
	- create highlight layer, turn on alpha inheritance, switch blending mode to screen
	- select area, use air brush, select color, go to brighter color, switch opacity to like 50%
	- smooth out color

details: 
	- create layer on top of base layer and below local shading
	- turn on alpha inheritance
	- select color to use
	- use selection and brush tool or use special brushes
	- color variation, select area, use air brush tool and different color, use smear tool to blend



recoloring and creating variation:
	- example creating a winter version of tree
	- alpha lock your base layer
	- shift + bksp to fill alpha locked layer or brush over area
	- whitish for winter, less saturated for winter trunk, etc
	- backlight, top layer, alpha inheritance on, blending mode as screen


layer order
group: 
  - backlight/rimlight
  - highlight
  - global shading
  - custom detail(opt, like snow covering wood cracks)
  - local shading
  - details
  - base



Modifying Selection
- hold shift and drag and you will add to selection instead of replacing it

- hold alt and drag and you will subtract from the selection

- hold shift and alt and drag and you get the intersection 
	of the two selections which is the area that contains both selections

- to combine with perfect proportion shortcut, hold shift and drag to create selection, 
   then let go of shift and press shift again and as you drag you will be in proportion

- in tool option docker, there are also action options which are buttons that will do what the above
   keyboard shortcuts do

- invert selection with ctrl+shift+i or from selection menu -> invert selection


- to grow a selection, you can go to selection menu and press grow selection and use that menu

- same with shrink


- feathering = a process of adding soft opactiy transition at the edges of the selection region

- border selection = convert the current selection into a 
	path selection surrounding the border of your intitial selection
	(choose border size and then selection gives that much border and you can draw or fill that border area)

- stroke selection command = draw a border color and or add fill color on the canvas based on 
	the active selection region.  This command will not create a new selection	
	- line = border color
	- width = border width
	- fill = color to fill inner selection with(can choose none)

- selection transformation methods:
  1. Simple movement
  2. Edit selection
  3. Vector editing

 - Simple movement, move cursor over the border of the selection and you will see it
     change to a different cursor that moves the selection without moving inner image

Global selection mask = a temporary mask that will show up whenever we have a selection.	
	It stores the selection information and can be used for a lot of different purposes


- Edit selection mode: Selection menu -> edit selection or Right click and press edit selection
  	Will open global selection mask and surround your selection with a transform box
        where you can scale, rotate, skew, flip, etc



3 methods of creating selection based on color information
  1. Contiguous selection tool
  2. Similar color selection tool
  3. Select from color range command


1. Contiguous selection tool is the magic want to the right of the selection tools
 - go to tool options and set fuizziness to a low value, and set grow/shrink and feathering to 0
   - fuzziness is how much color range krita will consider to be similar for neighboring pixels


Layer encapsulation = no matter how complex the compoosition inside a group layer, from outside, 
	the group layer is considered as a single layer

2. Similar color selection which is the xy line with diagnoal magic want
 - Selects area you click and any other area with similar color on layer

3. Select from color range command you can select from select menu
 - Choose from small selection of color types or brightness layers and selects everything similar


Anti-aliasing = a process of adding semi transparent pixels at the broder of images to give it more 
  smoother looks and to avoid pixel jaggies. Pretty obvious on rounded lines and turning it off gives jagged
   and pixelated looks.


Free transform tool: 
 - if no selection, it will outline the whole layer and let you move around the content
 - if you have a selection, the transform tool will move just the selection
 - press enter to apply changes or escape to cancel
 - has 5 modes.  Free transform is default
 - Free transform: 
    - Can drag using center of selection
    - can rotate using the corners just outside of node
    - Can scale using square nodes
    - Edges can be used to skew or sheer
    - Can hold shift while rotating to rotate in 7.5 degree increments
    - Can hold control and move around to apply 3D transformation 
    - Tool options contains options to change pivot point, mirror image, etc

 - Perspective Transform: 
    - Distort selection using handles
    - Can use vanishing point handle to change vanishing point
 - Warp Mode:
    - Adds control points to the image that you can move around to distort selection
    - Can use grid control points or custom layout of control points
    - Spikey
 - Cage Mode:
    - A lot like warp mode.  
    - Smoother and Rounder
 - Liquify Distortion: 
    - Uses brush like tools instead of anchor points to distort images

Mask: Additional information that can be applied to a parent layer

Transform mask: allows us to do non-destructive transformations.
 - mask requires a parent layer
 - if you duplicate a mask layer, it will create a layer with the transforms performed again 
 - can copy transform mask to a different layer and the transform will be performed on that layer as well

Transparency Mask: Mask that holds transparency information:
  - Black = transparent and White = Opaque
  - Example you could choose a brush and select black and it would make image appear to be erased
  - You could then switch to white and then draw and it would look like the image is coming back
  - Could be a cool effect to do 


Gradient: Transition of colors
  - Krita has three types of gradient colors: Special, Stopp, and Segmented
  - Special Gradients: Used dynamic colors, ie foreground to transparent the color changes 
         based on foreground color selection
  - Stop Gradients: Has triangles in color gradient where each stop has color 
         and opacity which is used to create whole gradient
  - Segmented Gradients: Has three nodes, the two black ones are color nodes. 
        - White node controls the center point of the transition
        - Linear transforms from left to right without any easing function
        - Can transition using rgb(each rgb value updates), or 
             HSV which moves along the color wheel either clockwise or counter clockwise
        - Can flip the gradient strip by right clicking and pressing 'mirror segment'
        - Can duplicate which turns the strip into two segments each using the same UI as the previous
           only you have to click on a segment to make that one active for changes 
        - Can split the segment which will happpen at the location of the white node

Gradient Tool: 
  - Shaped will apply gradient based on shape of selection
  - Can use shift key after starting to drag to create perfectly straight gradient direction

Wrap around mode / Tileable image: 
  - Tileable images are used in many design related disciplines:
  - web designers user for backgrounds, 3D artists use for texturing 3D models, 
     graphic designers use them for patterns
  - Tileable pattern: Cover large area with small image by repeating it (really awesome)
    - Create small image and create a curve from left to right that wouldn't line up
    - Turn on wrap around mode and it will create tiles of your image where you can  then draw on one and 
       it will be reflected in each tile which would let you connect them and kind of create infinite repeating
       patterns for an image
  - tileable texture (seamless texture): Created from photograph
     - textures.com
     - Seams erasing: Turn on wrap around mode, you will notice seams 
         - view -> show grid to see original image location
         - duplicate layer
         - move second layer so it's seams are center of the grid
         - erase seams using eraser or transparency mask
     - Clone brush tool
        - Select area and press control to move clone tool which is where duplicated images will be drawn
     - Manual patching: Select areas, copy selection to new layer, move new layer over seam

Filter: Applying some graphical operation to alter an image
  - 