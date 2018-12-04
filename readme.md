# SFML 2D Light (WIP)
![Demo](https://raw.githubusercontent.com/FoFabien/SFML-2D-Light/master/output.gif)  
Use C++11.  
Two functions in the demo:  
- closestPoint(), called by drawLight()  
- drawLight()  
Parameters are: the origin of the light, the radius, the color, the angle (in a sf::Vector3f: starting angle, end angle, step), the light intensity (0 to 1), the tile size, the map size (in tile), the render texture.  
  
Starting from the starting angle, it fires a ray. This one stops once it reaches a solid tile on the 2D map, reaches the max radius or goes out of bound.  
The lower the angle step is, the more rays are fired and the best the light source will look but the worst the performance cost will be.  
Each end point of each ray are stored and used to draw a sf::VertexArray. "mask.png" is applied on top to make the effect looks a bit nicer.  

Two sf::RenderTexture are used in main().  
The first one is the 2D scene.  
The second one is a pretty much a black screen where the lights are drawn, so we can use it as a mask with the first texture. sf::BlendMultiply is used.  
