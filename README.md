# 2018-01-18-webgl-shaders
An introduction and overview to using graphics shaders on the web.

To follow along on your computer there is somewhat of a system requirement. You computer and web browser need to be able to run WebGL. You can visit [get.webgl.org](https://get.webgl.org/) to see your WebGl compatibility. Or if you see fun graphics on this [three.js example](https://threejs.org/examples/webgl_shader), then you should be good. If neither of those work in your browser, I have found Firefox to work when other browser don't. If that still doesn't work I will be sharing my screen during the presentation.

## What is a shader?
Shaders get their name from doing just that, shading! More specifically in computer graphics a shader was a computer program that was used to calculate the changes in light and color in a generated scene. But really a shader can do so much more than just the shading. You can do all sorts of effects, multi-pass filtering, plus a shader can be used to draw 3D objects based on vertices. The thing that is special about a shader vs any other computer program is that they are designed to run on the GPU(Graphics Processing Unit). GPUs are made to run many calculations in parallel in order to handle all of the pixels in our displays. Because of that we can send a shader to the GPU and create effects and simulations that a CPU would normally struggle with.

## Web Shader
GPUs are programmed with the OpenGL(Open Graphics Library) and modern web browsers us a Javascript API called WebGl to speak to the graphics card. Here is the cool part, modern shaders are written in GLSL(OpenGL Shader Language). So you can really use the same shader you would use in a C++ application as you would in Javascript on the web. So usually a web shader is justs an inline snippet of GLSL code.

## three.js
There are many ways to work with the WebGL API including from raw javascript. But to make our life a bit easier and less confusing, we will be using [three.js](https://threejs.org/).