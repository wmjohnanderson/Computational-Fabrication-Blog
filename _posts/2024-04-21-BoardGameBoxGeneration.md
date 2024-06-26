---
title: "Board Game Box Generation"
layout: post
---
For this final project of my work through Computational Fabrication at CU Boulder I will continue to work with Grasshopper and Rhino 8 to make a script that can generate an entire board game box based on paramaters. The script will take in information about the type of inserts required, number of inserts, number of pieces, and then piece dimension in order to create unique inserts for different types of pieces. After creating the inserts required for the box, the script will run a bin staking alogrithm that will find the best possible orientation within a box for all the inserts. With all the inserts and box dimension figured out, the script will create a box to house the inserts with finger joints to connect the walls. In order to fabricate this project, I plan on using 3D printing for the inserts, and laser cutting for the box. Board games a passion of mine as I run a board game club at CU Boulder, so this project feels like a good combination of passion and challenge for me.

At my club here at CU Boulder, one of the biggest problems we have is with board game boxes being both unnecessarily large and also breaking down quickly because they are usually made with cheap cardboard. This project will unlock the ability to create a new box for a board game that is both smaller and more structurally made so that it can last a longer time. The one downside it will have is being heavier than other board game boxes.

# Materials Used
### Software & Machines
- **Rhino 8:** Utilized in conjunction with grasshopper to great 3D designs, and a 3D to 2D slicer. Program also used in order to print to laser cutter.
    - **Grasshopper:** Visual programming language and environment within Rhino 8, used to generate unique 3D designs.

- **Prusa Slicer:** Program used to slice test cylinder and generate g-code.
- **MK3S+ 3D Printer:** Used this printer located in the BTU (Blow Things Up) lab at CU Boulder for fabrication of the inserts.
- **Laser Cutter:** Also utilized laser cutters located in the BTU (Blow Things Up) lab at CU Boulder for laser cutting the box.

### Fabrication Materials
- **PLA Filament:** The type of filament used with the MKS3+ Printer.
- **1/4" Thick Birch Plywood:** The material used for laser cutting out the board game box.
- **Gorilla Glue:** Used to ensure board game box is constructed well.

# Part 1: Planning and Designs
For the first part of this project I am planning how I can achieve the vision that I layed out above. This part of the blog will show my thought process for what I am trying to achieve and what it will look like. Below you will see images of both what I expect the box to look like at the end of the project, and what I expect the different inserts to look like.

### Board Game Box
<img src="../assets/box-inspiration.jpg" alt="board game box inspiration photo" width="350" height="350" style = "border: 5px solid black;">
 
The image you see above is from a creator "Laser Bun" on a website called <a href = "https://designbundles.net/laser-bun/2044831-box-laser-cut-files-svg-cutting-files-dxf-cnc-cut-">designbundles.net</a>. This is what I am striving to do with the box that will encase the inserts for this project. This can be achieved through finger joinst as you can see from the project photo. You may notice the barrier slots in the photo of the box which uphold the lid from falling into the box. Because I am doing the project with inserts of different sizes with the goal of maximizing space efficienct, I can not have the same support structures for my box. To counteract this, I plan to make the box a little bit larger in its width in order to allow me to put two beam structures on either wall of the box to hold up the lid.

### Board Game Inserts
<img src="../assets/insert-drawings.jpg" alt="board game insert sketches" width="350" height="350" style = "border: 5px solid black;">
 
This image that you see above is the sketches I did to show you what I expect and want the each of the inserts to look like for the board game box. They are designed to fit each of the pieces snuggly to maximize space efficiency while also giving the user a way to easily retrieve whatever piece it is from the insert. that is why there are the half-sphere cutouts on the dice insert, missing walls of the card insert, and extra margin for the miniature insert.

# Part 2: Board Game Insert Script
In this part of the project I will start working with Grasshoper in Rhino 8 to create a script that will take in paramaters and then 3D model inserts that meet the requirements. The parameters include: *type of piece, width of piece, length of piece, height of piece, and quantity of piece*. The script is also made to take in a list of parameters so that it can produce multiple inserts at the same time as board games tend to have many inserts. below I will show you screenshots of the different insert models and give you a look at the code for this script.

## Code

> **For the rest of the blog you can refer to this Grasshopper script to follow along and see the code for yourself**
> **Link:** <a href = "https://drive.google.com/file/d/15JBxmAZyFNDYBRlxuIcrUX-ronKhtIuE/view?usp=sharing"> Grasshopper Script</a>
 
<script src="https://gist.github.com/Wian9699/a0f5e14857360bd08e45f8d0185bd2ca.js"></script>

This is the first important piece of code for this assignment. Take a look at the code above and you can see that the purpose of this code is to take in parameters for the type of piece, width, length, height and quantity of board game pieces in order to calculate the size for the inserts. All the parameters are given to the program as lists to enable generating multiple inserts at the same time, and as you can tell from the code it determines the sizes of the insert based upon the parameters, but most importantly the type of piece that is needed for the insert since there will be multiple insert designs with different sizes depending on the type of piece the insert is needed for. You can see how each insert is unique from eachother below with images of a generated insert.
 
The only other python scripts we used in this project so far are for packing insert information into tuples and also a filter to ensure that the correct insert is built. Since these files are not very exciting or complicated/long I decided to leave them out, but you can still find them in the Grasshopper file.
 
## Output

>Here are screenshots of the script for each of the created inserts
 
### Card Insert
The parameters for this card insert where:
- type 1 insert
- 30 mm width
- 50 mm length
- 1 mm height
- 30 quantity
 
<img src="../assets/cardInsert-1.png" alt="photo of card insert script (1)" width="350" height="150" style = "border: 5px solid black;">
<img src="../assets/cardInsert-2.png" alt="photo of card insert script (2)" width="350" height="150" style = "border: 5px solid black;">
 
<img src="../assets/card3D.png" alt="photo of generated card insert" width="350" height="350" style = "border: 5px solid black;">


### Dice Insert
The parameters for this dice insert where:
- type 2 insert
- 20 mm width
- 20 mm length
- 20 mm height
- 5 quantity
 
<img src="../assets/diceInsert-1.png" alt="photo of dice insert script (1)" width="350" height="150" style = "border: 5px solid black;">
<img src="../assets/diceInsert-2.png" alt="photo of dice insert script (2)" width="350" height="150" style = "border: 5px solid black;">
 
<img src="../assets/dice3D.png" alt="photo of generated dice insert" width="350" height="350" style = "border: 5px solid black;">


### Miniature Insert
The parameters for this miniature insert where:
- type 3 insert
- 25 mm width
- 25 mm length
- 40 mm height
- 5 quantity
 
<img src="../assets/MiniInsert.png" alt="photo of miniature insert script" width="350" height="350" style = "border: 5px solid black;">
  
<img src="../assets/Mini3D.png" alt="photo of generated miniature insert" width="350" height="350" style = "border: 5px solid black;">

### Default Insert
The paramaters for this default insert where: 
- Type 4 insert
- 22 mm width
- 22 mm length
- 1.5 mm height
- 50 quantity

<img src="../assets/default-code.png" alt="photo of default insert script" width="350" height="350" style = "border: 5px solid black;">
  
<img src="../assets/default-model.png" alt="photo of generated default insert" width="350" height="350" style = "border: 5px solid black;">

# Part 3: Insert Packing
At this point in the assignment I have been able to generate all of the inserts through grasshopper, and this part of the project I worked on developing an algorithm that will take all of the inserts and their dimensions to find the best possible arrangement for the inserts in order to get the board games box dimensions to laser cut the box. I will give you the python script below that calculates the position for each insert, show you a 3D model of all the inserts laid out for a Bang! Dice Game box and some screenshots of the grasshopper code.

### Python Script
> In the script below you will see how I am able to arrange the inserts into a box formation. The algorithm takes in the inserts, sorts them based off of largest volume to smallest volume and give the largest insert the location of (0,0,0). From there the algorithm will move on to the next insert checking all possible positions to place it which is based on the corners of all already placed inserts. It will make sure that at each location if the insert where placed there that it won't collide with any inserts. For all the possible positions with no collisions the algorithm will check which position affects the volume of the entire box the least and also promotes a squarer arrangement. The algorthim outputs the points for all inserts, the dimensions of the box, and also the inserts arranged from highest volume to leaset volume
 
<script src="https://gist.github.com/Wian9699/84d93c337baad843526175070996c616.js"></script>

### Code
> This is the script that takes the points from the packing algorithm and moves the inserts to there designated locations.
 
<img src="../assets/packing-code.png" alt="photo of grasshopper packing script" width="350" height="350" style = "border: 5px solid black;">

### Output
> Below is the packed model for the Bang! Dice Game.
 
<img src="../assets/box-packed.png" alt="photo of inserts layed out in box" width="350" height="350" style = "border: 5px solid black;">


# Part 4: Box Generation & Cutouts
This is the final step of the project before fabrication needs to be done. From the last part I was able to generate the dimensions of the box that I plan on putting the inserts into. In this part I take those dimensions and I create a 3D model of the board game box with finger joints based on the dimensions and then I project each side of the box onto the xy plane to give me a cutout of the box for laser cutting. The process of generating the cutouts consists of two parts: the cutout of the finger jointed sides, and the cutout of the lid and support walls.
**All models will be based on the needs for "Bang! The Dice Game."**

## Code

### 3D Model Code
<img src="../assets/box-script.png" alt="photo of 3D box model script" width="350" height="350" style = "border: 5px solid black;">

### Cutout Code
<img src="../assets/cutout-script.png" alt="photo of box cutout script" width="350" height="350" style = "border: 5px solid black;">

## Output

### 3D Model

<img src="../assets/box-model.png" alt="photo of finger jointed box model" width="350" height="350" style = "border: 5px solid black;">

### Cutout

# Part 5: Fabrication
This is my final step in this project and it involves fabricating both the inserts and the box which uses the inserts above. Here I will describe how I was able to fabricate both the box and the inserts and the different methods I used to do it.

### Box Fabrication
For this part, I took the generated outlines from the Grasshopper program and loaded it into Rhino at the BTU Lab in CU Boulder. From there I was able to specify that outlines as "hairline" and also adjusted print settings to ensure that when I started the laser cutting job that it would cut through the entire 1/4" plywood.

### Insert Fabrication
For this part, I took each insert individually and uploaded it into Prusa Slicer to generate g-code that would work with an MK3S+ printer that was located in the BTU lab. Each insert I found took roughly 4 hours to fabricate, and at the end I was able to arrange all the inserts like the model from an above section in the box to finally create the fully fabricated board game box.

## Output
The game that the box below represents is a dice game called "Bang!" It is a social deduction game where cops and outlaws go toe to toe to take eachother out by rolling dice with yahtzee rules. For this project I required three insert that include a dice insert for the five dice, card insert for the role and character cards, and a token insert for the bullet and arrow tokens. Below is the final fabrication with all the pieces.
 
<img src="../assets/game-side.jpg" alt="Fabricated photo of game (side angle)" width="350" height="350" style = "border: 5px solid black;">
<img src="../assets/game-top.jpg" alt="Fabricated photo of game (top angle)" width="350" height="350" style = "border: 5px solid black;">
<img src="../assets/game-lid.jpg" alt="Fabricated photo of game (lid on)" width="350" height="350" style = "border: 5px solid black;">

# Reflection

At the end of this project, I am defenitely happy with the product I was able to end up with. For the most part, everything I wanted to achieve was achieved and I was able to create a script that can generate any board box I want. Obviously though, this did not come without its problems or issues, and this project was defenitely a lot harder than I had initially thought. 
 
The biggest problem I had with this project had to be with the box packing algorithm. I wanted this project to be fully automated from the point of entering parameters which meant that when it came time to figure out the size of the board game box I need to formulate a bin packing algorithm that can generate positions for each of inserts in a way that maximizes space and creates a box. This was extremely difficult and took a lot of time to come to the solution of tracking potential postions and tracking for collisions. If I had more time on this project, I would also edit this algorithm to check for rotation, and vertical stacking.

The second biggest problem I would run into with this project involved with the fabrication. I made it so that each insert would be the same height in the end as the tallest insert so that the levels looked even in the box. In doing so I also made it so that the height extensions for the inserts had an empty bottom. In Prusa Slicer I ran into the problem of the inserts not being structurally stable for printing and relying on build plate supports which in turn did the thing I was trying to avoid which was filling in the bottom.
 
Other things I would add with more time on the project includes: 
- More insert customization
- Tabs on inserts to help retrieve from box
- Make the filler inserts hollow from the bottom
- Decal Generation for top of box (board game title)
- Make default insert have higher length and width instead of equal dimensions for width, lenght, height
- many more...