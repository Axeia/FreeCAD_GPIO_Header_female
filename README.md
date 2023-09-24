# FreeCAD GPIO Header (female)
I'm currently learning EasyEDA and couldn't find a 22 GPIO header model so I decided to model it myself in FreeCAD.
The exact GPIO header I modelled can be found here:
https://vi.aliexpress.com/item/10000000838267.html

To be more exact I followed the dimensions provided in this image:

![Header height: 3mm | 2.54mm spacing | Top till start of the thin pin: 4.7mm | Total height: 7.43](https://ae01.alicdn.com/kf/HTB123ngCv5TBuNjSspmq6yDRVXaq.jpg)

Assumptions had to be made for:
 * The angle of the 'breakpoint notch' between segments*
 * The point at which the thicker part of the protusion starts getting bevelled**

*The angle of the 'break off' notches between the different segments wasn't provided but I used the Gimps angle tool to calculate it to be about 32 degrees. 
** I used a value of 0.5mm because if it's symmetrical then it leaves another 0.5mm as a flat surface which matches the diameter of the thinner part of the protrusion

# Altering it?
This is under the unlicense so do whatever and credit or don't credit whoever you'd like.
The way I made it is for good reason. The plastic bracket and metal pin are seperate elements so they can be converted to seperate meshes so the meshes can both be colored differently. 
That way if you select both meshes and do File>Export>.obj in FreeCAD the colors are preserved.

Just have a look at how I did the arrays and how I positioned them with formulas and it should be easy enough to make any kind of length of header with any kind of position you'd like.

# EasyEDA caveats
If you want to use this with EasyEDA as I have done:
  1) Convert your 2 arrays to a mesh in the Mesh workbench.
  2) Select both meshes and export them to .obj in FreeCAD
  3) FreeCAD generates a .obj and a matching .mtl file. Zip up both
  4) In EasyEDA File>New>3D Model>Add File and select the zip
If you literally want the same 2x22pin with a 10 pin layout spacing I have used feel free to download the BPI-Leaf-S3.zip it can be directly imported into EasyEDA.
I made this layout to match my BPI-Leaf-S3 ESP32-S3 board.
