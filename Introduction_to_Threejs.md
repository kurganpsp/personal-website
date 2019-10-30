---
layout: default
---

# JavaScript in 3D: an Introduction to Three.js

How to bring three dimensions to your next web app

1_yyd14XiZBbvCbkN3v4ipbQ.png

Photo by Kari Shea on Unsplash, featuring a Three.js render.

Three.js is a powerful tool. It helps bring 3D design and animation to the browser in a performant and adaptable way. But it can be tricky to get started if you’ve never delved into the world of 3D programming before.
I had some basic experience playing with the Unity Game Engine and C#, but otherwise many of the concepts were new to me. I realised there weren’t many beginner-friendly resources out there, and so I decided to write this article. In it, we’ll look at the main elements of a Three.js scene, from meshes and material to geometries, loaders and more.
By the end of the article, you should have a solid understanding of the basic building blocks necessary to add an extra dimension to your next web project.

1_7P2rZnsMdUR9HBP9bmFptA.png

1_Am4hORAtVGahN-1Ipo13TQ.png

1_gvX17esnMr8NiT5AtMyT3Q.png

Three.js examples by Ben Houston, Thomas Diewald and StrykerDoesAnimation.

# Vectors and boxes — the fundamental building blocks
Often, the two most important classes in Three.js are Vector3 and Box3 . If you’re new to 3D, this stuff might sound a little abstract, but you’ll encounter them a lot!

# Vector3
The most basic 3D class, containing three numbers x , y and z . This can be used to represent a point in 3D space or a direction and length. For example:

    const vect = new THREE.Vector3(1, 1, 1);

1_mDGah9z-0f-ph-_suSIQBA.png

1_KCU6U3S2dtp6IRBMiUdDFQ.png

Points are locations in space. Vectors are displacements in space.

Lots of Three.js constructors take Vector3 objects as arguments, including the Box3 below.

# Box3
This class represents a cuboid (3D box). Its main purpose is to get the bounding box of other objects — that is, the smallest possible cuboid that a 3D object could fit in. Every Box3 is aligned to the world x , y and z axes.

Here’s how to create a box using a Vector3:

    const vect = new THREE.Vector3(1, 1, 1);
    const box = new THREE.Box3(vect);

And here’s how to create a box based on an existing 3D object:
