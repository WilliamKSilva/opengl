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
