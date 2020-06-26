# Ring Lantern

## Project Idea

The idea of the project is to make a ring with LED so that it will glow only when somebody wears it in their finger.

## Constraints

The constraints here are :

1. Size, the whole circuit must be compact and must fit within the size of a ring.
2. Battery source, due to the small size of the ring the power source must be in a small size.
3. Design, the material that we choose to make the outer body of the ring must be soft and smooth, it must not harm the user if it’s worn for a long while.

## Proposed Idea

### Design:
For the design, we could use a rubber material as the outer surface and the circuit must be fitted within the rubber. For the switch we could use a metal strip at one side of the ring in the interior and within some gap, another metal strip can be placed, when the ring is worn the outer placed is pushed in and it comes in contact with the inner plate and the circuit is completed and the light glows up.

The choice of the light can be a strip of LEDs that will be made into a circle and can be used as the light source instead of using a normal LED. If we use a single LED then it would point out, but if we use a strip LED and cover it with a transparent rubber cover then it would be more pleasing and aesthetic. 

### Battery:
For the power source, a small button cell can be used which will fit into the circuit easily as the size of the complete circuit is small. For commercial purposes, we could use the small button cell as the choice. But we do have another technology of 3D printing to make batteries in any shape(Check it out [here](https://www.printedelectronicsworld.com/articles/16197/shape-conformable-batteries-based-on-3d-printing-technology)). But it isn’t commercially feasible as of now and so we could just give it a try.

### Circuit:
The circuit starts with a button cell in which the one end goes to the strip LED and the other goes to the inner metal plate (bent). From the other terminal of the LED strip, the connection is made to the outer metal plate (bent). If the ring is worn then as the ring compresses, the outer and inner metal comes in contact with each other and the circuit is and so the LED’s glow up.

### Size:
In order to reduce the size of the whole setup, we don’t use any new wires and just use all the components directly by soldering them. Also, the LED strip will be the outermost one, following it the outer metal plate and in some gap, the inner plate is placed. In the remaining gap other than the two metal plates and the space between them the battery is placed. In this way, the size can be reduced to a maximum extent. 

## Specifications of components used

### LED Strip: ([Datasheet](https://robu.in/wp-content/uploads/2018/01/WS2812B_datasheet-1.pdf))
Number of LED used: 3cm (number of led’s equivalent of it will be used)

Voltage Supply: 5V

Width: 12 mm

Thickness: 4.6 mm

### Battery: (SR416SW - [Datasheet](https://media.digikey.com/pdf/Data%20Sheets/Seiko%20Instruments%20PDFs/SR416SW_DS.pdf))
Voltage: 1.5V

No of cell used: 3 

Diameter(width): 12 mm

Thickness: 4.6 mm


### Dimensions of the product (Ring Lantern):
Ring width: 13mm 

Thickness: 7 mm

Perimeter: 5-6 cm (average ring size of a human is around 6 cm) 

## Design Specs:
### Outermost component:
On the top of the ring facing outside the strip LED is placed and in the interior side three button cells are placed, these form the outermost part of the ring.

### Other components:
Following the strip led we place the outer metal strip, and then with a small gap of 0.4 mm, the inner metal strip is placed. When the ring is worn at the maximum tight then the two metal strips will touch each other and the circuit gets complete and the led glows up. 

## Image of the idea proposed

A bit Clumsy image, but I hope the idea is pretty clear.

![Project Image](path)





## References
1. https://www.flexfireleds.com/what-are-led-strip-lights/ - A guide on strip LED’s working
2. https://robu.in/product/5m-ws2812b-5v-addressable-rgb-waterproof-led-strip-light-60leds-m/?gclid=EAIaIQobChMI0LvA8bCt6QIVSw4rCh3JbwyxEAYYBiABEgJQpvD_BwE -Link for the LED strip.
3. https://media.digikey.com/pdf/Data%20Sheets/Seiko%20Instruments%20PDFs/SR416SW_DS.pdf - Button battery cell
4. https://electronics.stackexchange.com/questions/384622/ws2813-led-strip-without-controller - Controlling Led strip without a controller.
