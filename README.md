# 2018-01-18-webgl-shaders
An introduction and overview to using graphics shaders on the web.

To follow along on your computer there is somewhat of a system requirement. You computer and web browser need to be able to run WebGL. You can visit [get.webgl.org](https://get.webgl.org/) to see your WebGl compatibility. Or if you see fun graphics on this [three.js example](https://threejs.org/examples/webgl_shader), then you should be good. If neither of those work in your browser, I have found Firefox to work when other browser don't. If that still doesn't work I will be sharing my screen during the presentation.

### What is a shader?
Shaders get their name from doing just that, shading! More specifically in computer graphics a shader was a computer program that was used to calculate the changes in light and color in a generated scene. But really a shader can do so much more than just the shading. You can do all sorts of effects, multi-pass filtering, plus a shader can be used to draw 3D objects based on vertices. The thing that is special about a shader vs any other computer program is that they are designed to run on the GPU(Graphics Processing Unit). GPUs are made to run many calculations in parallel in order to handle all of the pixels in our displays. Because of that we can send a shader to the GPU and create effects and simulations that a CPU would normally struggle with.

### Web Shader
GPUs are programmed with the OpenGL(Open Graphics Library) and modern web browsers us a Javascript API called WebGl to speak to the graphics card. Here is the cool part, modern shaders are written in GLSL(OpenGL Shader Language). So you can really use the same shader you would use in a C++ application as you would in Javascript on the web. So usually a web shader is justs an inline snippet of GLSL code.

### Libraries
There are many ways to work with the WebGL API including from raw javascript. The most popular seem to be [three.js](https://threejs.org/) for 3D and [PixiJS](http://www.pixijs.com/) for 2D. My plan is to have an example of each. Though I still need to clean up the three.js example. I do have a raw example which is long, but super informative.

## Things to Know
Vertex Shader: Takes lists of 3D points or vertices and converts them to a position on the 2D screen.
Fragment Shader: Now with our 2D points the GPU makes triangles from every three points(fragments) and files them in with the instructions from the fragment shader. Because we have to fill in every pixel, the GPU handles interpolating between all the points ie. fading between colors.

#### Variables
Uniforms: Set for both the vertex and fragment shader and remain unchanged. You might pass a screen resolution or light position along this way.
Attributes: Set for the vertex shader and remain unchangeds. Typically vertex info is passed in this way.
Varying: Set and altered by the vertex shader but not the fragment shader. You would use this to pass information to the fragment shader from the vertex shader.

## Good Tutorials and Info
**[TheBookOfShaders.com](https://thebookofshaders.com/)** -- This is an awesome online book with working examples that is my #1 recommendation for shaders.

**ThreeJS shader intro [part 1](https://aerotwist.com/tutorials/an-introduction-to-shaders-part-1/)[part 2](https://aerotwist.com/tutorials/an-introduction-to-shaders-part-2/)** -- This is a great tutorial for implementing ThreeJS, though I think the version of ThreeJS maybe a bit dated.

**[PhiloGL shader intro](https://dev.opera.com/articles/introduction-to-webgl-part-1/)** -- This tutorial uses PhiloGL, but what I like is the illustrations and explanations to help explain how the GPU works.

**MotherLoad: [Mozilla WebGL Docs](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API)** -- If you got the time their tutorials and examples along with the entire API are excellent for using WebGL from scratch. I find this approach helps to learn what WebGL is actually doing in the previous libraries.