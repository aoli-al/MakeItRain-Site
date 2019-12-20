---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
---

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

$$
S = \sqrt{(x_1-x_2)^2+(z_1-z_2)^2}
$$
