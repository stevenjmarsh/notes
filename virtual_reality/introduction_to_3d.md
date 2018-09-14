# 3D Modeling

## 3D Space
wireframe - 3d view of a modal, in line format
bounding box - rough box, outline of a modal
shading / shaded view
can add color, texture

navigation controls
orbit, rotate - rotate camera around scene
truck - truck in / out, zoom in / out
focal length - zoom in or zoom out 
orthographic view - parallel projection
top view
perspective view
view ports
angle of view
origin  0,0,0    (arbitrary point in space - starting point)
world space - origin at center of world
object space - space in relation to the object
pivot point - center
    center can be adjusted moved on an object

transforming objects: move, rotate, scale
    each can be done along just one axis, or all at once
grid
snapping, snap to  (support precisely place objects)

hierarchy - connecting objects together (in a parent child relationship)
    when moving an object, its child objects move along with it

## Modeling and 3D Geometry
triangle - fundamental unit of surface in 3D
triangles are used to define object shapes, because triangles always remain flat and retain their shape 

the normal - flat surface to define which direction an object is facing
    normal is perpendicular to the plane of the triangle

all other shapes (polygons, patches) can resolve to triangles

tessellation - using shapes to map a surface (polygons, triangles)
    ultimate result will be triangles

primitives - collection of base shapes (e.g. sphere, box, cube, cylinder)
    used to create more complex shapes

polygonal surface
    *vertices* (points)
    *edges*   (lines connecting vertices)
    *faces*    (surfaces defined by vertices and edges)

can change vertices, edges, faces, to change the shape of an object 
    each could be moved or rotated or scaled



sculpting  - use brush, to push or pull detail
    converse is smooth or relax tool
modeling
extrude
edge loop - add edges, to allow for more shape manipulation
    provide surface with which to model
bevel - round off corners
union   (add)
subtract   (remove)
intersection  (difference)
smoothing
subdivide   (cuts each polygon in to 4, which smooths, or creates curvature)
    cage - is the original model

TIP when creating a model, only add detail (edges) where more detail is needed (e.g. where you wish to curve / bend something)

## Patch Based Surfaces
using curves, patch modeling
build surface out of curves
    they still resolve to triangles
two types of curves: nerbs?  bezier
patch based surfaces are defined by curves
revolve
lathe    - can create a bell shape 
loft - stretch a surface along curves
extrude - extrude a surface too (similar to polygonal extrude)
trim - trim surface, draw a shape, then trim the outer (or inner) away, like crop 
    the patch still remains, like a cage, to allow for more manipulation of the remaining / trimmed surface

## Textures & Materials
material tells rendered how the surface interacts with light
    matte finish
    shiny, reflects
    transparent

shader, apply matte or shine
    color
    ambient color / glow
    transparency

diffuse channel - overall color  (underlying color)
specularity layer - bright highlight, shine (reflective)
    highlight / reflectivity of a surface 
    has roll off
anisotropic - non circular specularity

specularity can help you see the texture, shape, curvature of a surface 

combine diffuse channel and specularity to create surfaces that look more realistic

bump   map 
displacement   map
normal mapping

mapping texture, like a label on a can
    wrapping
    opposite is an unfolded version of the object

UV editing
    mapping a 2d flat image to a 3d object
    like an image around a cube
unwrap your objects (mentally)
square maps of color texture of the object

## Rendering Images
Renderers
* scanline
* raycasting
* raytracing

starts with lighting
ambient lighting (light in the room, bounced or secondary)
    can change color of lighting
    can move the light 
    point light
    spot light  (has a cone)
    penumbra, soft edge on a light
    can place light
    directional light
    area light 

shadows   (can change color of shadow)
shading

indirect lighting
bounce lighting
caustics
reflections
refractions    refractive index  (bend in / out)

cameras,  virtual cameras
    zoom (lens)   trucking is moving the camera
    depth of field  (blur)

once lights and cameras setup, do final render 

can render portions of a scene (to get a preview of a portion)

# 3D Applications

## Blender


