# Max/MSP Abstractions for Space / Coordinates / Channel Manipulation

Heavily Depended on SPAT5 Library, as well as some math helpers (sin/cos)

## Panning

### Quad Channel Setup

#### Pan4Ch
Quad Channel Pannning (Control Rate) (Sine Cosine)

#### Vertical Sweep
Cycling on a straight line horizontally, while moving vertically. Normalized Square Plane Output. (Control Rate, Line Ramp Driven) (Slightly Broken)

#### Cross Sweep
Emulates an acceleration towards the center and bounces to another corner decelerating.

#### Wiggle
Random Movement of Source for an interval. Smoothing can be toggled.

---
### Channel Based

#### Channel Expander
Expands channels by a multiple X from Y Channels to Z Channels  

#### Channel Increment Fader
Used to activate a certain number of channels, use with a line~ object fading the channels in and out

#### Channel Crossfader
#### MC Panner Poly
---
### Coordinate Based

#### Boids 3D (Obsolete, Replaced by spat5.boids)
Using Boids3D for a swarm of sources and sending them to SPAT5

#### Circular
Simple Circular Output (in Cartesian Coordinates)

#### Linear Movements
Movement towards two points on a line with ease or

Random Points on a Line, given by two points

#### MC Spat Trajectories

#### Coriolis Force
Coordinate Movement between two points, possibility of adding rotations to the movement (Which will deviate away from the destination point)

#### Box Panning (Box Wiggle)
Cubic 8 Point Panning

#### Orthogonal Panning (Box-Linear-Panning)
Creates a XYZ Matrix, fix source movement orthogonally, or move towards grid points

#### Matrix-XY
Creates a (Speaker/Source) matrix based on a bunch numbers
e.g. 1 3 >>> (1,3) (1,1) (3,1) (3,3)

#### XYZ to Pitch
Numeric Transformation (Multiple Patches with different approaches)

#### Rotate Chance
Rotation Probability

#### Random Multi
XYZ Random, based on center and range, with resolution

---

## Helpers

#### Coordinate Corrector
Set a global coordinate to local coordinate, relative to a certain point. Useful for multiple overlapping systems.

#### Coordinate Setter
Preset SPAT5 Speakers and Source Locations with a text file.

#### IR-Loader
Loads IR with a text file. (Unknown Usage)

#### Listener Unity to SPAT
Collects the listener location from Unity to SPAT

#### XYZ SPAT to Unity
Changes the format of SPAT coordinates to Unity Coordinates and send to Unity

#### Voice Collector
(mc.poly) Used to pack separate channels into 1 MC Chain, useful in legacy patches

#### OSC Tools
OSC Route Poly

OSC Clock Limiter

OSC to Number (For Rhino Intergration) 

OSC Route Shift

OSC Channel Shift

OSC Coordinate Shift (In fact is a ratio based channel shift, unsure what it is used in)

---
## Obsolete

#### Channel Crossfader (Depreciated, please mc.matrix/mcs.matrix)
(Used for mc.poly) Routing and Crossfading MC Sound Sources to different MC channels

i.e. Sound Source 1 can be routed and crossfaded from Channel Output 2 to 6

#### Wingpan (Depreciated, Please use ease library)
Linedrive based exponential Panning, based on CMak's wingpan. Emulates an acceleration of source to destination 

#### Linedrive (Depreciated, Please use ease library)
Concave / Convex curve Panning (Obsolete)

#### mc-xfader mc-linedriver (Depreciated, Please use ease library)
Same with Channel Crossfader but with Linedriver included, enabling exponential source manipulation 

#### Angular Movement
Implementing (?)

#### Line Intersection Taking Off
Implementing (?)

---
Distance

#### Distance Based Delay
The name says it all, scale adjustable

#### ParaS-Prob
Distance calculator between an array of points, for markov chain probability settings

---

## Examples

#### Motion Generation
Using a master clock and a coll object (I think using a dict would be better) to control all sources in a SPAT5 Renderer to reduce computation

#### Spat Binaural Template
Binaural Setup Example

#### Messages
QList or Message box example for scene control

#### SPAT to SN3D
Guide for conversion of formats
