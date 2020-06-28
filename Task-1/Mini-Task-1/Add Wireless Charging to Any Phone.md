# Add Wireless Charging to Any Phone

## Description
If one plans to use a phone for more than 2 years then, the phone must have the following features in it:
A replaceable battery, because the battery only lasts about 2 years, and
And wireless charging so you don't wear out the charging port.
 
But nowadays most of the manufacturers don’t give out replaceable batteries in phones. So, we must have wireless charging to it. Wireless charging is not yet popular in all phones.So, the easy solution is to add a charging receiver to the back of the phone that just plugs into the USB port. However, that option gets in the way of using the USB port. There may be times when a wireless charging pad is not available or you want to connect the phone to your computer. So we prefer to wire the receiver into the inside of the phone to keep the USB port open.
 
The first step in it is to get a charging transmitter and receiver. There is a variety of charging options to use, we need to choose them wisely. The preferable one is that which has copper coils in it and is also reputable. Following this, we disassemble the phone and locate the charging socket’s pin-out, the pin diagram for most of the charging sockets are available online. There won’t be any explicit print of +Vbus or gnd as in Arduino. One must be careful while soldering the wires from +Vbus and gnd. Now put a small notch in the plastic cover and take these two wires out of the cover and connect them to the charging transmitter and receiver that is placed at the back of the phone. That’s it we have added wireless charging to our phone. The charging through it will be a bit slower than compared to wired charging.
 
## Charging Types
Qi ("chi") charging is currently the charging standard. There is the regular (5 watts & 1 amp) and now there is a "Fast" option (15 watts & 3 amps). For fast charging, you need both a Fast receiver and transmitter. I opted for the standard since I find that it is adequate for overnight charging and the battery on most phones will last the day under normal use. Wireless charging is nothing but a split transformer, where one half transmits power via a high-frequency magnetic field to the receiver side that then rectifies and smooths it to 5 volts DC.
 
## Operation and Considerations of Wireless Charging
* Wireless charging is nothing but a split transformer, where one half transmits power via a high-frequency magnetic field to the receiver side that then rectifies and smooths it to 5 volts DC.

* Many phenomena (like light) fall off in strength via a squared distance function (Strength / DxD). However, magnetic field strength is a cubed function (Strength / DxDxD). What this means is that the power transfer capability drops off very fast. Therefore, separation between the Transmitter and Receiver must be kept to a minimum, less than about 4 mm. Therefore, large fat and thick cases can make charging next to impossible unless you consider how to get the receiver closer to the transmitter. Receivers built into a phone prevent the use of thick protective cases. Also, metal cases prevent the use of a receiver inside the case due to excessive currents in the case that use up the power and overheat the circuits.

* Note that charging receivers have a special magnetic shield on the backside. This shield helps to keep the material behind the coils from interfering with the magnetic field and thus improving performance. if you decide to expose the receiver coil, do not remove this shield. You also want to make sure the receiver is mounted face out. The outside face will be marked in some way, perhaps as illustrated.

* On the charging receiver if the positive and negative terminals are not obvious or marked then you may have to place it on a charging pad and use your voltmeter to identify the positive and negative points to wire to.



## Project Image

**Charging Port:**

![](https://cdn.instructables.com/FD7/4PK7/JA8JFQZZ/FD74PK7JA8JFQZZ.LARGE.jpg?auto=webp&frame=1&width=1024&height=1024&fit=bounds)
**Final product:**

![](https://cdn.instructables.com/FAK/XS0X/JA8JFR0D/FAKXS0XJA8JFR0D.LARGE.jpg?auto=webp&frame=1&width=393&height=1024&fit=bounds)


