# **LogicalRedstone**
**// Copyright (c) 2026 LogicalRedstone. Licensed under the MIT License.**

LogicalRedstone is a modular standard of components that can be assembled dynamicly and perform logical operations. The appearance and feature of each component is inspired from the game [Minecraft](https://www.minecraft.net/).

*This project is made for the hackathon event [Fallout](https://fallout.hackclub.com) hosted by [Hackclub](https://www.hackclub.com).*

![ZinePage](https://github.com/TXWD1234/LogicalRedstone/raw/main/docs/zine-page/ZinePage.png)

# Project Usage
*See detailed usage documentation of each component below in `Project Documentation/Components`.*

## What it does
LogicalRedstone provides the user a collection of modular components (so called "redstone"). These components can be combined to create logic gates, and even further: logical circuits.

## How to use it
Move around the components, connect them, create circuits, express your imagination and talent.
The user has total freedom over the components. The components can be assembled in any form, and is theoretically possible to create any logical circuit.

There are intruded gaps, or extruded bodies on each side of each component. One component either has all their sides have intruded gaps to accept the extruded bodies from other component, or extruded bodies to be accepted by other component.
The components can be connected by creating an occlusion between the intruded gaps and the extruded bodies.

## How to build it
There are 2 portion of manufacturing the LogicalRedstone.
- Print the 3D shell
- Solder the circuit inside

### 3D Shell
*The exported 3d stl files can be found for each component here: `/components/<component-name>/CAD/`.*
*The onshape link of everything is: `https://cad.onshape.com/documents/205be14658acf1e2d17db0f8/w/b440bc3b616cb68e740a4578/e/6cf53d2f83e9f1d85365554f`.*

The 3d shell is deisgned via onshape for the user to download and print on a FDM or similar addative manufacturing service. Our reccomended method would be to use FDM 3d printing. Upload the desired file into a slicer service ensuring no additional supports need to be generated. Print with less than 15% infill and a rectilinear profile. If using clear or unique material besides PLA ensure to adjust parameters accordingly. If your printer's tolerance is poor adjust for the difference using the stl files. 

There are 2 parts to the 3D shell: Base and Cap.
The base contains the circuits, and the cap has the minecraft appearance.
There are 2 variation of the base, and are universal for all components. The 2 variations are:
- Male (With 2 extruding bodies on each side)
- Female (With 2 intruding gaps on eahc side)
*The universal base models are located in `/components/general/CAD/`.*

For each component there is one cap model. They all have a universal connection part with the base, and unique top appearance matching their Minecraft characteristics.

### Circuit
The circuits are soldered on cutted perf-board, attached with a coin battery and several photo transistors and lazer emitter.
The circuit schematics of each component is provided in `/components/<component-name>/<component-name>.kicad_sch` if applicable.
*There's a special case: RedstoneDust-StraightLine variation don't have a circuit, because it's just a hollow box letting the light go through it.*

### Assembly
After the shell and the circuit is completed, the assembly can be done according to the following procedure:
1. Place the circuit in the base part of the shell
2. Fasten the circuit in the base to prevent movement
   - Make sure that the photo transistors and lasers are aligned with the hole
3. Place the top part of the shell on the base
   - Brute force may be applied to push the top part into the base.

# Project Story (Why it exists)

## Build It All From Scratch - TX_Jerry's Story
### My Programming Obsession
From the first day I started programming, I found myself constantly pursuing a direction involuntarily.
And that direction is **low level**.
Where I first started was already pretty low: C++ is almost everyone think the lowest.
But I am not satisfied with that.
Exploring more lower level things such as Windows API and OpenGL, while making my own library and creating data structures, considering architecture, building complex systems and engines... I am on the way toward the lowest level.

### TXCompute - My Fallout 60hr Project
My initial idea of TXCompute was exactly: "Make a calculator with logic gates.".
Even at last I choosed to use microcontroler instead of logic gates, I was back to low level by learning how to use transistors and implementing a NOT gate with NPN transistors.
It is that final unexpected portion of TXCompute gave me the ability to build this project.

### The Badge Project
On the first day of Fallout, when I was asked to make a PCB, just any cool PCB, I instantly have my idea: A half adder, made with logic gates, which are made with transistors.
When I started making it, I pushed the logic gates implementation further from TXCompute. From one NOT gate, to a whole set of AND, OR, NOR, NAND and XOR.

### The Real Project
When my two team mates explained their project idea of *"Make Minecraft redstone and make logic gates with them."*, I was immediately interested.
That means my knowledge of transistors and logic gates can be expressed and utilized, and I might be able to complete the calculater that I was trying to make, at the very beginning.
I soons started analyzing how Minecraft redstone works, and simplified them into 2 basic gates: AND (Redstone Repeater) and NOT (Redstone Torch).
With those 2 basic gates, I started to implement those more advanced gates: NAND, NOR, OR, XOR, XNOR...
And finally, I recreated half adder in the Badge Project.
But I am not satisfied with that.
I proceeded to making the MUX and DEMUX gate, and then by combining half adders, I made a 8-bit full adder.
And that, concludes this logic gate adventure. Even it's not yet a full calculator, I achieved the concept, of **making things with logic gates.**

# Demo
*See detailed documentation in `/demo/README.md`.*

The demo is a half adder circuit made with LogicalRedstone components. It consists the implementation of XOR gate, combining with an AND gate, result the capability to perform the addition operation of 2 1-bit integer.

![picture](https://github.com/TXWD1234/LogicalRedstone/raw/main/docs/readme-assets/demo-circuit/half-adder.png)

# Credits
**Contributers:**
- [TX_Jerry](https://github.com/TXWD1234)
- [Coolerzanu](https://github.com/coolerzanu)
- [nathab32](https://github.com/nathab32)

# Project Documentation
LogicalRedstone standard consists of the specification of 6 modular components. Each component can be manufactured according to the specification.
The components are listed below:
- Redstone Dust
- Redstone Repeater
- Redstone Block
- Redstone Button
- Redstone Torch
- Redstone Lamp

## Terminology
- **"component" / "block":** a modular piece of product of this project, mimics the redstone related blocks in Minecraft.

## The Modular Design
Each type of modular component consisted in this project can vary in quantity, dependent on the user. According to the specification, each component can be produced in any quantity.
These components are designed to be a fundational piece of logical expression that can be used to create and program logical circuits.

## Signal Transfer Between Blocks
*Unlike Minecraft, the signal in this project are merely binary signals, varying only between 0 and 1 instead of 1 to 15.*  
Binary signals are transfered between components *("blocks")* via **light**.
At one side of each component *except redstone dust*, a laser emitter is placed inside the component. It sends light out of the component.
At the opposite side of the each component, a light sensor is also placed inside the component, which detects the light emitted by the lazer emitter of other components, and forward the information (0 or 1) contained in that light into the component.
The redstone dust, however, is a special component that is designed to forward the light signal, or change the direction of the light. It is used to connect components.+

## Symbol Library
A symbol library in KiCad is provided along with the specification. It's purpose is to make the development of circuits made with redstone components easier.
The symbol library includes all components in the specification expect redstone dust, as they are just wires.
The appearance and registered name are showed below:

![picture](https://github.com/TXWD1234/LogicalRedstone/raw/main/docs/readme-assets/component-circuit/symbols.png)

Library file path: */library/component-symbols.kicad_sym*

## Components

### Redstone Dust
*There's no algorithm automaticly changing the dust type in real life, you have to do it yourself.*  
The redstone dust acts like wires, who connects other components together.
It is the most versatile component in the specification. There are 6 variation of this component, including:
- straight (3 variations)
  - one in one out
  - both in
  - both out
- corner
- T junction
- cross junction

Inside a redstone dust block the light signal is transfered via fibre optic cables. They also glows, making the redstone dust also glow.

### Redstone Repeater
*This is not how actually repeaters in minecraft behaves...*  
A redstone repeater acts like a transistor.
It has 2 input side and 1 output side:
- Input: Source
  The power input of the repeater
- Input: Gate
  Control the on/off state of the repeater. If Gate is low then the repeater will be disabled: the Drain is set to be low in this case
- Output: Drain
  The power output of the repeater

*Since in this case we don't need to worry about voltage like MOSFET, this "transistor" is basically an AND gate.*

### Redstone Block
*A redstone block is made out of 9 redstone dust, and the redstone dust is made out of fiber optics, ~~so fiber optics magically generate power.~~*  
A redstone block provides a constant signal of 1 (High).
It can be used as a constant, or a quick testing parameter of a circuit.

*Why does this thing even exist? It just burning battery constantly.*

### Redstone Button
*Or a pressure plate? They have no difference.*  
A redstone button outputs signal of 1 (High) when pressed.
It can be used for a user interface.

### Redstone Torch
*I wonder why power can turn a torch off. Maybe the torch is hiding a NOT gate inside of it? You never know~*  
A redstone torch outputs a constant signal of 1 (High) when nothing is powering it.
But if it received a signal of 1, it will be turned "off" and output a signal of 0.

*I wonder if you can use this as a NOT gate?*

### Redstone Lamp
*It's so funny that a lamp exists while the redstone itself already glows.*  
A redstone lamp glows when it receives a signal of 1 (High).
It can be used to make user interface, or even display graphics when stacked in array.

# Gallery
***Logic gates made with redstone components:***

![picture](https://github.com/TXWD1234/LogicalRedstone/raw/main/docs/readme-assets/demo-circuit/logic-gates.png)

***Minecraft block diagram for the half adder:***

![picture](https://github.com/TXWD1234/LogicalRedstone/raw/main/docs/readme-assets/demo-diagram/demo-diagram.png)
