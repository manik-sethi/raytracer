# RayTracer
This repository follows the guide ["Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html#overview) by Peter Shirley, aiming to create a simple yet effective ray tracer from scratch using C++.

## Overview
This project is an implementation of a basic ray tracing algorithm. Ray tracing is a rendering technique for generating realistic images by simulating the way rays of light interact with objects in a scene.

I found these videos to be quite helpful:

[How Ray Tracing (Modern CGI) Works And How To Do It 600x Faster](https://www.youtube.com/watch?v=gsZiJeaMO48)  
[Raytracing Explained](https://www.youtube.com/watch?v=oCsgTrGLDiI)  
[Ray Tracing in 5 minutes](https://www.youtube.com/watch?v=H5TB2l7zq6s)  


# Before:
![Normals Sphere Ground](https://raytracing.github.io/images/img-1.05-normals-sphere-ground.png)

# After:
![Final Rendered Scene](https://raytracing.github.io/images/img-1.23-book1-final.jpg)

# Procedure
Here's how I built the Ray Tracer.

## Ray Generation
Ray-Tracing involves rendering an environment by shooting rays of light from the camera to the environment. Each ray is then tested for ray-object interactions to see how it's intensity, color, etc. changes based on the nature of the interaction. Any ray that eventually bounces back to the camera is then rendered visually. Rays, and their corresponding colors were modeled with their own respective vectors which belong to the same class. The corresponding header file includes comprehensive operations that may need to be performed on vectors, such as normalization, dot products, and also generating random vectors.

## Ray-Object interaction
When light strikes an object, the nature of its reflectance depends on the properties of the material. This is modeled in our simulation by taking advantage of surface-normal vectors. The surface normal vector is calculated by taking the vector that travels from the center of the sphere, to the surface. To make computation easier, a normalizing function is applied. With these surface normal vectors, the relationship between the inbound light ray, and surface-normal vector can be calculated to determine reflectance properties. Which relationship we choose to look at depends on the material we are working with. One example are diffuse materials, which looks at the cosine relationship between the two vectors.

Anti-Aliasing

## Diffuse Materials
Diffuse surfaces reflect light in a mostly randomized direction. The concept of ***Lambertian Distribution*** was crucial for modeling diffuse (matte) materials in the simulation. Lambertian distribution is the property that reflected rays will tend to scatter in directions near the surface-normal vector. This can be modeled by adding a random unit vector to the surface-normal vector, which very elegantly skews the probability of outbound rays to be in a similar direction to the normal.

## Metallic Materials

## Dielectric Materials




# Acknowledgments
Peter Shirley for the fantastic guide: "Ray Tracing in One Weekend"
@LudwigABAP on twitter for introducing me to the project

This project is licensed under the MIT License - see the LICENSE file for details.
