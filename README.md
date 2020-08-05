![Aviation Hacking Banner](./aviationbanner.png)

# hack-aviation-library
A collection of learning resources for budding aviation security researchers (aka hackers). Learn so we can secure aviation from design to implementation!

*Note: This is an evolving resource, so please [contribute](./aviationlibrary-contribute-instrxns.md) with a pull request*

**Jump To**: [Web sites](#web-sites) | [Articles and Op-Eds](#articles-and-op-eds) | [Tools and Projects](#tools-and-projects) | [Videos](#videos) | [Books and White Papers](#books-and-white-papers) | [Programming Libraries](#programming-libraries) | [Oh and Drones!](#Oh-and-Drones!) | [Miscellaneous](#miscellaneous) | [Contacts](#contacts)

## BACKGROUND
In order to encourage more people to become interested in investigating aircraft vulnerabilities as well as understand the problems aircraft face, Bricks in the Air attempts to represent this problem in a simple and jargon free manner. By replacing the complex and unfamiliar 1553/429 buses with the more well known I2C data bus, we remove a lot of the jargon and confusion of the problem while allowing attendees to understand the core problem: Aircraft data buses are old and unsecure, and someone should fix that. 

## RESOURCES

### Aviation Hacking Challenges
Called Bricks in the Air, in this series of four workshops, you will attempt to send messages to a mock LEGO® technic aircraft over I2C to experiment with direct injection attacks on a data bus. This year, we’ve integrated the newly released Spike Prime robot from LEGO® Education.

For 2020, the workshops will be held in Safemode at Def Con via Twitch streams.  Checkout [dds-virtual.com](https://dds-virtual.com/) to access the workshops, otherwise, see the [github repo](https://github.com/deptofdefense/dds-at-DEFCON/blob/master/README.md) for the deets on game play for each of the work shops!

### Articles and Op-Eds
- How To Hack an Aircraft by Kate O-Flaherty (https://www.forbes.com/sites/kateoflahertyuk/2018/08/22/how-to-hack-an-aircraft)

- In-Flight Airplanes Can Now Be Hacked from the Ground, Cyber Expert Warns by Jason Murdock (https://www.newsweek.com/flight-airplanes-can-now-be-hacked-ground-cyber-expert-warns-962420)

- The Air Force Will Let Hackers Try to Hijack an Orbiting Satellite by Brian Barrett (https://www.wired.com/story/air-force-defcon-satellite-hacking)

- GAO Warns of Cyber Risks In-Flight by Paul Roberts (https://www.securityledger.com/2015/04/gao-warns-of-cyber-risks-in-flight)

- Coming Cybersecurity Mandates May Have Implications for Military Aircraft by Frank Wolfe (https://www.defensedaily.com/coming-cybersecurity-mandates-may-implications-military-aircraft/cyber/)

- The F-35's Greatest Vulnerability Isn't Enemy Weapons. It's Being Hacked. by Kyle Mizokami (https://www.popularmechanics.com/military/aviation/a25100725/f-35-vulnerability-hacked/)

### Web Sites
- **DDS Workshops at Aerospace Village**  (https://github.com/deptofdefense/dds-at-DEFCON)

- **Aerospace Village Website** (https://aerospacevillage.org/defcon-28/)

- **Flight Control Systems Research** (https://www.sciencedirect.com/topics/engineering/flight-control-systems)


### Tools and Projects
- **LEGO Raspberry Pi Project:** Replace Lego’s $190 Intelligent Brick with MIT’s Scratch and a $40 Raspberry Pi (https://spectrum.ieee.org/geek-life/hands-on/replace-legos-190-intelligent-brick-with-mits-scratch-and-a-40-raspberry-pi)

- **ATmega328 Project:** Learn about the microcontroller onboard the Lego Crafts and use it to create a music box (https://dronebotworkshop.com/arduino-uno-atmega328/)

- **Understanding the Embedded Controls in Aviation:** An overview of the control systems used to control components of aircrafts (https://en.wikibooks.org/wiki/Embedded_Control_Systems_Design/Aviation)

### Videos
- MIL-STD-1553 Avionics Bus Overview (https://www.youtube.com/watch?v=36dj_hPDGHM)

- DEF CON 20: Hackers + Airplanes (https://www.youtube.com/watch?v=CXv1j3GbgLk)

- DEF CON 27: Behind the scenes of hacking airplanes (https://www.youtube.com/watch?v=IgKsH6BzQWY)

- Can Aircraft Be Hacked?! This pilot explains various attack surfaces in commercial aircraft (https://www.youtube.com/watch?v=rVs8RSA8UMs)

- Spacecraft Technology: Data Busses (https://www.youtube.com/watch?v=dD7VwwlGRw8)


### Books and White Papers
- Cybersecurity in Civilian Aviation:  Insights for Advanced Nuclear Technologies (http://fhr.nuc.berkeley.edu/wp-content/uploads/2017/04/UCB-TH-17-001-Cybersecurity-in-Civilian-Aviation.pdf)

- Aircraft Cybersecurity: The Pilot's Perspective (https://www.rtca.org/sites/default/files/symposium_2017_cybersecurity_white_paper_digital.pdf)

- F-35 Lightning II Technology Overview (https://www.lockheedmartin.com/content/dam/lockheed-martin/eo/documents/webt/F-35_Air_Vehicle_Technology_Overview.pdf)

### Oh and Drones!
- Drone hacking is much like any other embedded device hacking, with the exceptions that when things go bad, the propellers can actually cut you or amputate limbs. The typical setup is an ARM or MIPS SOC, running Linux or a RTOS, or sometimes both on the same SOC at the same time. For most drones, they are quite literally an Android device with some propellers attached. Many drones have multiple systems running on them.  Some can run two different versions of android on two different SOCs on the same board, while also running a RTOS for the flight controller on a single core of one of those SOCs. Drone hacking can be weird.
- Drones will have a vast mismatch of mitigations and security technologies, which makes them an excellent (but expensive) educational target. These range from platforms with zero memory corruption mitigations, to platforms making extensive use of ARM Trustzones, SELinux and advanced RF security measures. With many drone companies are still back in the 90s on security, they are an excellent way to build up your skillset from the ground up.
- First thing we do is check and see if the device is vulnerable to exploits on similar models.  Often they are, and sometimes the exploits need a few tweaks to work right, or need to be chained with another exploit to defeat some new mitigation. Is always nice to get a quick win because the work is already done, isn't it?
- The next thing we do is an overview for the attack surface. First checking physical entry ways, do we have UART, JTAG or other debug ports? Where are all the usb ports?   Sometimes they have no header or are otherwise hidden. Then we move more towards the software level. What kind of interfaces are up on USB? Is there a serial port open over USB? Is TCP over usb up? What services are running on the network if one is up? FTP? Telnet? Is the RC Wifi based? If so can we get on that wifi network? How does the app communicate through the RC? Is the app obfuscated or packed at all? The attack surfaces on many drones are huge, and varied. Lots of room to have some fun.
- Then I move to firmware. Do they have the firmware on their website? Has anyone dumped the firmware? Can we just reverse engineer the update software? Does the update system have any hidden engineering software? Is the update package encrypted? If we can't get the firmware trivially, then we pull the storage and manually extract the firmware. Probably should have bought two drones, but thankfully Amazon Prime exists.
- Once firmware is in hand, we can treat this like any other embedded device. Since the drone world really hasn't caught up with security, a quick overview looking for low hanging fruit like simple command injections, hard coded credentials, weakly generated passwords or debugging interfaces (cough backdoors cough) often leads to a quick and easy win. No luck with the low hanging fruit? Then the painstaking task of auditing every exposed interface and service.

- Check out these other resources:
  - Counter-Drone SWAT Teams (https://breakingdefense.com/2020/02/defense-digital-service-builds-counter-drone-swat-team-asap/)

  - DEF CON 23: Knocking my neighbors kids cruddy drone offline (https://www.youtube.com/watch?v=5CzURm7OpAA)

  - Drone Hacking - A Cybersecurity Nightmare (https://www.dronesinsite.com/drone-news/drone-hacking-a-cybersecurity-nightmare/)

  - Hack Your Own Drone (https://drone-hacks.com/)

  - You Can Hijack Nearly Any Drone Using This Tiny Gadget by Wang Wei (https://thehackernews.com/2016/10/how-to-hack-drone.html)

- Happy Drone Hacking!

### Miscellaneous
- MIL-STD-1553 Publication (https://snebulos.mit.edu/projects/reference/MIL-STD/MIL-STD-1553B.pdf)

## CONTACTS
### Aviation Security Contacts
- Daniel Allen (dan@dds.mil)
- Nick Ashworth (nick.ashworth@dds.mil)

### Defense Digital Service Library Custodians
- Clair Koroma (clair@dds.mil)
- Daniel Allen (dan@dds.mil)
- Nick Ashworth (nick.ashworth@dds.mil)

## *Also check out our [Satellite Hacking Resource Library](https://github.com/deptofdefense/hack-a-sat-library)*

[<<<Back to Top](#hack-aviation-library)
