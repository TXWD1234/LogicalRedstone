# **LogicalRedstone**
**// Copyright (c) 2026 LogicalRedstone. Licensed under the MIT License.**

LogicalRedstone is a modular standard of components that can be assembled dynamicly and perform logical operations. The appearance and feature of each component is inspired from the game [Minecraft](https://www.minecraft.net/).

*This project is made for the hackathon event [Fallout](https://fallout.hackclub.com) hosted by [Hackclub](https://www.hackclub.com).*

![ZinePage](https://github.com/TXWD1234/FalloutProject/raw/main/docs/zine-page/ZinePage.png)

# Demo




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

![picture](https://github.com/TXWD1234/LogicalRedstone/docs/readme-assets/component-circuit/symbols.png)

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
![picture](https://github.com/TXWD1234/LogicalRedstone/docs/readme-assets/demo-circuit/logic-gates.png)

***Minecraft block diagram for the half adder:***
![picture](https://github.com/TXWD1234/LogicalRedstone/docs/readme-assets/demo-diagram/demo-diagram.png)
