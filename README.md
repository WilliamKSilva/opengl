# LearnOpenGl

## First topic: Draw an triangle
- A bunch of stuff about vertex, buffers and shaders (Graphics pipeline).
- The GPU dont have default Vertex Shader (Called for all vertex and is responsible to deal with 3D coordinates) and Fragment Shader (Defines the color of things), so we have to build this.
- Everything in OpenGL is built using triangles. To build an rectangle for example we just need two triangles on top of each other.

![image](https://github.com/WilliamKSilva/opengl/assets/75429175/fd5b1f94-91ea-4cc6-9179-38dfe410a051)

## Second topic: Shaders and GLSL
- Shaders are programs that are stored on the GPU, they are used on all the steps of the Graphics Pipeline.
- Shaders are basically a bunch of input and outputs.
- The language GLSL is used to write shaders, it looks a lot with C.

Shader example:
```
#version 330 core
out vec4 FragColor;
  
in vec4 vertexColor; // the input variable from the vertex shader (same name and same type)  

void main()
{
    FragColor = vertexColor;
}
```
## Third topic: Textures
- Textures are literally plain images that we map to render on top of each model/shape. It would be expensive if we
had to use multiple vertex with colours attributes to build textures.
- Textures have a bunch of settings to optmize and define the way they should be displayed (Texture filtering, Texture wrapping, etc).
  - Texture wrapping: Texture coordinates go from (0,0) to (1, 1), texture wrapping deal with when we specify coordinates outside of this range.
  - Texture Filtering: OpenGL has to define which texture pixel (texel) map to the texture coordinate.
- Mipmaps are texture images of all different sizes to deal with optimization, why would we use an high quality texture on an far way object that
produces small fragments?
"To solve this issue OpenGL uses a concept called mipmaps that is basically a collection of texture images where each subsequent texture is twice as small compared to the previous one."

Rectangle with an wooden texture:

![image](https://github.com/WilliamKSilva/opengl/assets/75429175/75a6418c-0c35-438d-81a1-636895799a88)

## Fourth topic: Transformation
- Everything is vectors and matrixes. We use transformation matrixes to manipulate our vectors and move/transform things on the screen, very fun.
- I think the first line already described all we need to know about this topic, vectors and matrixes values change = things moving on the screen.
- GLM is an math library made specially for OpenGL.

https://github.com/WilliamKSilva/opengl/assets/75429175/a919a146-1c61-4b33-91ba-e620934abdba

## Fifth topic: Coordinate Systems
- An game camera is definitely more complex that it seems.
- OpenGL render all the things on the screen using an 2D coordinate system that goes from 0 to 1 and 0 to -1 on X and Y axis. But for we get to this points we
have to travel a long distance.
- We have to do some transformations on the objects before achieve the final screen position, passing through some other coordinate systems:
  - Local Space
  - World Space
  - View Space
  - Clip Space

Its hard to explain all of this, so here is the link describing all of them: https://learnopengl.com/Getting-started/Coordinate-Systems

https://github.com/WilliamKSilva/opengl/assets/75429175/3025f257-1d3a-454b-ae41-621041bba840

## Sixth topic: Camera
- A lot of math to control the camera.
- A "look at" matrix helps a lot with the camera positioning
- I learned how the "right" direction vector of an object is defined (cross products everywhere).
