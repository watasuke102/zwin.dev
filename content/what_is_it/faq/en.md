# FAQ

## Zwin
### What is Zwin?
Zwin is a XR windowing system, which displays multiple XR / 2D apps on VR headset / 2D screen. It is named as a "win"dowing system with "Z" axis!
The word "Zwin" also refers to the protocol used in the system.
See [What is Zwin?](/en/what_is_it/what_is_zwin).


### Is Zwin an operating system?
No. Zwin is a windowing system, which works on operating systems and coordinate the application windows.

### Is it difficult to install Zwin?
Not at all! See [Installation](/en/getting_started/installation) for the detailed installation instruction.

### What device is required to use Zwin?
See [System requirements](/en/getting_started/system_requirements).

### What is the difference between Zwin and VR workplace solutions (Virtual Desktop, Immersed, Horizon Workrooms, etc.)?
In other VR systems, the entire field of view is dedicated to one app, so it is not possible to use multiple 3D apps. Zwin is a windowing system coordinating 3D windows, so in Zwin you can use multiple 3D apps side-by-side in one environment. Moreover, Zwin is open-sourced, and anyone can freely develop small 3D apps, allowing even small-scale developers to participate in VR app development.

### What is the difference between normal VR apps on Quest and Zwin?
Normal VR apps work standalone. For example, if you play a VR game, the contents you see are generated by the VR game application. On the other hand, in Zwin, the contents are generated by the multiple applications connected to it. Zwin coordinates them and show the contents in one screen to the users.

### Do Zwin support AR?
Not yet, but we would like to support AR sometime soon!!

### Can I throw away my laptop and use only VR with Zwin?
Currently you have to run Zwin on your laptop and connect VR headset to it.
However, in the future it might become possible with Linux standalone headsets such as SimulaVR One, Lynx R1.

### Can I collaborate with other users in Zwin?
No you can't, but we would like to add support for it. 


## Zen
### What is Zen? How is it different from Zwin?
Zen is our reference compositor for Zwin. A compositor is a program that communicates with client apps listens for the content the apps want to show, and displays them into screens as overlapping windows. "Zwin" is the name of the protocol Zen uses. The word "Zwin" is also used to for the windowing system realized with Zwin protocol.

### Why isn't it called Zwin-xx?
Zen is just our reference compositor for Zwin. Zwin is an open-source protocol, so anyone can develop a compositor following the protocol. We avoided the naming of Zwin-xx to show that it is possible to develop other Zwin compositors.


## Zen Mirror
### What is Zen Mirror?
Zen Mirror is an application working on Oculus Quest headsets. It works as a remote display of Zen. Connected to PC, it receives the contents from Zen on PC and shows them to the users with the headset.

### Can I connect headset wirelessly?
Yes, but it is not recommended because of the unstable behavior. We are trying to solve the problems and support the wireless connection offcially in the next release.

### Can I use Quest 1/2/Pro?
Quest 2/Pro are officially supported. You can also use Quest 1, but the processing power is insuffcient so not recommended.

### Can I use the other VR headsets?
#### Standalone Headset
Zen Mirror is developed as an Android app, so if the headset can run an Android app (such as Vive Focus, Pico, Magic Leap ... etc), it will be supported in the near future!!
Support of the other VR headsets (such as Hololens) and be later than them.

#### PCVR Headset
If the headset works with OpenVR (Vive, Valve Index), it can be supported soon.


## Apps
### What kind of apps can I use on Zwin?

#### 2D apps
As long as the app is compatible with the Wayland protocol (such as Google Chrome), you can run the 2D app on Zen. We are also planning to support X11 apps with [XWayland](https://wayland.freedesktop.org/xserver.html).

#### Windows apps
So far they are not supported, but it might be possible to run Windows apps with some tools like [Wine](https://gitlab.winehq.org/wine/wine) or [Virtual Box](https://www.virtualbox.org/).

#### Exising VR apps (such as OpenXR apps)
You cannot run these apps on Zwin because our rendering method is different from theirs. See [Rendering Scheme](/en/what_is_it/rendering_scheme) for details.

### I want to develop an 3D app for Zwin!
You are more than welcomed!! Check [3D App Development](/en/getting_started/3d_app_development).


## Troubleshooting

### I can't connect my headset

There are some possible causes:
- If you run `adb devices` command on the PC, is your headset shown in the list? If not, check
  - Is developer mode enabled?
  - Have you allowed the USB debug access?
- Have you run the `adb forward` command? See [Using Zen in 2D Screen](/en/getting_started/zen_walkthrough#using-zen-in-2d-screen) for details.
- Are you using the latest Zen Mirror? Version mismatch between `zen-desktop `and Zen Mirror can cause the problem.

See also: [Installation](/en/getting_started/installation), [Zen walkthrough](/en/getting_started/zen_walkthrough).

### I can't run zen-desktop on terminal
You can't if you run the command on top of another windowing system. Exit your current session as shown in [Zen walkthrough](/en/getting_started/zen_walkthrough#using-zen-in-2d-screen)

### I can't do copy & paste, drag & drop, etc.
There are some Wayland features not supported by Zen yet. See [Roadmap](/en/roadmap) for future releases.

