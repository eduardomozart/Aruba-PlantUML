# Aruba-PlantUML

This repository uses Aruba Networking symbolic shapes ([HPE-Aruba-Symbols.zip](https://www.visiocafe.com/hpe.htm)) Visio Stencils package from VisioCafe.

The following projects were used to generate the images available in this repository:

* [libvisio2svg](https://github.com/kakwa/libvisio2svg) to convert Visio Stencils (*.vss) to SVG.
* Inkscape to convert SVG to PNG.
* ImageMagick to remove background alpha transparency from PNG files.
* PlantUML to convert white background PNGs to Sprites (.puml files). 

The scripts used to generate the images available in this repository are available in the post "[Instalação do libvisio2svg no macOS](https://eduardomozartdeoliveira.wordpress.com/2023/01/30/instalacao-do-libvisio2svg-no-macos/)" (in Portuguese).

## Getting Started

### VSF

![Basic usage - VSF](https://www.plantuml.com/plantuml/proxy?idx=0&src=https%3A%2F%2Fraw.githubusercontent.com%2Feduardomozart%2FAruba-PlantUML%2Fmain%2FSamples%2FVSF.puml)

```csharp
@startuml
left to right direction

skinparam {
    ArrowColor Black
    DefaultTextAlignment center
    Shadowing false
}

skinparam rectangle {
    BackgroundColor transparent
    BorderColor #FFFFFF
}

!define ArubaPuml https://raw.githubusercontent.com/eduardomozart/Aruba-PlantUML/main
!include ArubaPuml/HPE-Aruba_Symbols-Generic-Client_Buildings_Infrastructure/layer3-switch.puml

rectangle "<$layer3_switch>\n**Access-1 (Master)**" as SW_ACCESS_1
rectangle "<$layer3_switch>\n**Access-2 (Standby)**" as SW_ACCESS_2

SW_ACCESS_1 " 1/1/27" 0-down---0 "1/1/27 " SW_ACCESS_2
@enduml
```

### VLANs

![Basic usage - VLANs](https://www.plantuml.com/plantuml/proxy?idx=0&src=https://raw.githubusercontent.com/eduardomozart/Aruba-PlantUML/8eb75c35b10d36cd7933d6a50578f1523c0ee0fb/Samples/VLANs.puml)

```csharp
@startuml
left to right direction

skinparam {
    ArrowColor Black
    DefaultTextAlignment center
    Shadowing false
}

skinparam rectangle {
    BackgroundColor transparent
    BorderColor #FFFFFF
}

!define ArubaPuml https://raw.githubusercontent.com/eduardomozart/Aruba-PlantUML/main
!include ArubaPuml/HPE-Aruba_Symbols-Generic-Client_Buildings_Infrastructure/computer-monitor-outline.puml
!include ArubaPuml/HPE-Aruba_Symbols-Generic-Client_Buildings_Infrastructure/layer2-switch-A.puml
!include ArubaPuml/HPE-Aruba_Symbols-Generic-Client_Buildings_Infrastructure/server-PBX.puml

rectangle "**VLAN 2**\n\n<$computer_monitor_outline>" as PC
rectangle "<$layer2_switch_A>" as SW
rectangle "**VLAN 2**\n\n<$server_PBX>" as SRV

PC 0-down-0 SW : G1/0/1
SW 0-down-0 SRV : G1/0/2
@enduml
```

## License

Copyright© VSD Grafx Inc. All Rights Reserved.

If you require any more information or have any questions about VSD Grafx Inc. licensing, please feel free to contact them by email at info@visiocafe.com.
