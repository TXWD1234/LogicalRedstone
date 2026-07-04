# **LogicalRedstone**
**// Copyright (c) 2026 LogicalRedstone. Licensed under the MIT License.**

LogicalRedstone is a modular standard of components that can be assembled dynamicly and perform logical operations. The appearance and feature of each component is inspired from the game [Minecraft](https://www.minecraft.net/).

*This project is made for the hackathon event [Fallout](https://fallout.hackclub.com) hosted by [Hackclub](https://www.hackclub.com).*

![ZinePage](https://github.com/TXWD1234/FalloutProject/raw/main/docs/zine-page/ZinePage.png)

# Credits
**Contributers:**
- [TX_Jerry](https://github.com/TXWD1234)
- [\<Name\>](https://github.com/<github-username>)
- [\<Name\>](https://github.com/<github-username>)

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

## Redstone Dust
*The most versatile component in the specification.*

## Redstone Repeater
## Redstone Block
## Redstone Button
## Redstone Torch
## Redstone Lamp










DevNote:
Name Idea:
- Logical Redstone (Proposed by Jerry)
