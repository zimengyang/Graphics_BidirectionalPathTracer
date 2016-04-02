# Graphics_BidirectionalPathTracer

The final porject of CIS 560 Computer Graphics.<br>
Major features include **BDPT**,  **Progressive Rendering**, **Depth of Field** and **heuristic BVH acceleration**.

## Bidirectional Path Tracer Implementation
|Didirectional path tracer|Naive Multiple Importance Sampling|
|---------------------|----------------------------|
|![cube_bdpt](Rendering/BidirectionalPathTracer/cube_bdpt.bmp)|![cubeMIS](Rendering/BidirectionalPathTracer/cube_indirectLighting.bmp)|
|![disc_bdpt](Rendering/BidirectionalPathTracer/disc_bdpt.bmp)|![discMIS](Rendering/BidirectionalPathTracer/disc_indirect.bmp)|
|![spheres_bdpt](Rendering/BidirectionalPathTracer/spheres_bdpt_10samples.bmp)|![spheresMIS](Rendering/BidirectionalPathTracer/spheres_indirectlighitn_2samples.bmp)|

From the obove pictures, bidirectional path tracer performs better in dealing with the influences between adjacent geometries. And also have a better rendering in scenes where lights are obstructed by geometry.
<br>

## Heuristic BVH Acceleraiton
Some test scenes are rendered with acceleration structure-bvh tree.
BVH took 3221ms to render a scene with 33K triangles and 1 sample per pixel.<br><br>
<em>Fig. Heuristic BVH test - building.</em><br>
<img src="Rendering/BVHTest/building1.bmp">
<br><br>
<em>Fig. Heuristic BVH test - wahoo &amp; building.</em><br>
<img src="Rendering/BVHTest/wahoo.bmp">
<br>

## Progressive Rendering
Implemented a new OpenGL shader to render the texture grabed from frame buffer to screen. And update the rendered texture in each render thread.<br><br>
<em>Screenshot of <b>progressive rendering</b>.</em><br>
<img src="Rendering/ProgressiveRender/ScreenShot.jpg">
<br>

## Depth of Field
Add *lensRadius* and *focalLength* variables to Camera class, sample camera.eye within a disc with radius: *lensRadius*. Then modify the reference point to focal plane. Cast a newRay by variablesabove.<br>

|long focal length|short focal lenth|
|-----------------|------------------|
|![](Rendering/DepthOfField/focalLength16.bmp)|![](Rendering/DepthOfField/focalLength12.bmp)|

|small lens radius|medium lens radius|large lens radius|
|-----------------|------------------|----------------|
|![](Rendering/DepthOfField/lensradius_1.bmp)|![](Rendering/DepthOfField/lensradius_2.bmp)|![](Rendering/DepthOfField/lensradius_3.bmp)|

## Transmissive material
<em>Transmissive and reflective material renderer.</em><br>
<img src="Rendering/Transmissive/cube_ball.bmp">
<br>