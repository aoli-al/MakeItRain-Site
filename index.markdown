
# People

Ao Li, MSc, Computer Science, University of Toronto \\
Mingqi Zhu, MScAC, Computer Science, University of Toronto \\
Cole Zemel, Undergraduate, Computer Science & Drama, University of Toronto \\
Shel Sun, Graduate Student, Drama, University of Toronto 

# How To

Download the source code.

```
git clone https://github.com/Leeleo3x/MakeItRain
```

Install [Unity](https://docs.unity3d.com/Manual/GettingStartedInstallingHub.html) (supported version 2018.4.12f1).


# Requirement

- OS: Windows 10
- GPU: NVidia GTX 960+
- VR Headset, e.g. VIVE Pro


# Coordinate Alignment Algorithm

We only consider one coordinate frame in our algorithm, which is the VR device 
coordinate frame $I$.
The calibration process of VIVE Pro device aligns the y-axis of $I$ with the 
gravity vector.
The scale of the $I$ is the same as the real world corrdinate frame. Therefore, the 
coordinate alignment problem can be simplified as moving the virtual objects so that 
the positions of the objects in virtual world match the positions of the objects in 
real world.
We utilize the VIVE Pro device to capture the position of real world objects w.r.t $I$.


## Camera Location

The positions of the cameras in virtual world match the positions of projectors in real word.
Given a camera $c$, we first use VIVE Pro to capture the location of the four corners of the 
screen $(x_1, y_1, z_1),\dots, (x_4, y_4, z_4)$. The position of the camera $p_c$ is the center 
of the screen plus hight $h$, which is a constant: 

$$p_c=(\frac{x_1+x_3}{2}, h, \frac{z_1+z_3}{2})$$


## Camera Rotation

Since the y-axis of $I$ is aligned with the gravity vector, we only need to compute yaw of the 
camera.

$$
yaw = \mathrm{arctan}(\frac{z_2-z_1}{x_2-x_1})
$$


## Camera View Size

The size of the camera view is the same as the size of the screen. 

$$
S = \sqrt{(x_1-x_2)^2+(z_1-z_2)^2}
$$


# Model

![](/assets/img/graph.png)

# Script 

Come Good Rain by George B. Seremba

COLE and SHEL take positions

SHEL (to COLE):  Excuse me, could you please not shoot me through the back?  I would prefer to look at you while you are shooting.  Thank you.

PROJECTION:  The first bullet had hit the right leg.  

COLE fires (right leg)

SHEL falls to knees
	
PROJECTION:  Before he knew it, the left arm was grazed.

COLE fires (left arm)

PROJECTION:  Another got a bit of skin just above the forehead

COLE fires again (grazes forehead)

PROJECTION:  Never still, and unwilling to give them a clean shot at the chest or the stomach.

PROJECTION:  The next one found his right hand at an angle just over his heart.

COLE fires (right hand, SHEL has hand over heart)

PROJECTION:  Then another through the right thigh.

COLE fires (right thigh)

PROJECTION:  A solid bullet went through his left ankle.

COLE fires (left ankle)

SHEL rolls over

Cue sound of multiple AK 47’s firing (5-7 seconds) then silence

PROJECTION:  It is quiet.  Frighteningly quiet.

Cue rain projection as COLE gets into position to lead the audience in the “snap/slap” soundscape.  



# Show

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/7ITKncfdfjI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
