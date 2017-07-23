


Overview
--------------------------

* Primary Radar in the good old days
* Secondary Radar idea
* Outlook: the move to ADS-B

In this episode: secondary

Secondary
--------------------------

* History: 
  - When was primary invented?
  - Secondary invented how long after primary?
  - IFF

* How does it work in principle?
  - Sending "something else" actively, not just echo
  - Assumes cooperative targets
  
* Modern Transponder
  - Mode A: squak
  - Mode C: + alt
  - Mode S
  
* Mode A/C
  - is there technical integration (except colocated antennas) with prim?
  - Primary radar sends signal 1030 and a/c creates an echo: 
    - Direction
    - (Diagonal) range, through time measurement
      (is this done on echo or on active 1090 reply)
  - Replies at sep freq: contains data ident based on assigned squawk
  - How is IFF different?
  - "Interrogation" 
    - how encoded?
    - different replies, different interrogations? 
  - (this is all analog tech, right?)
  - Reply: 
    - bandwidth and data encoding?
    - how is data encoded?
    - not self-describing => need to know mode
    - what can be encoded? Is Squawk Ident special?
  - Problem of overlap and garbling. 
    - No Parity Flag.
    - What is done to de-garble?
  - Pulse Repetition Frequency and Interlace (17)
  - Precise Bearing (18)
    - Sliding Window Azimuth
    - Monopulse Azimuth
  - Plot Extraction (22)
  - Side Lobe Suppression (23)
  
-> All kinds of limitations... (28)
    -> Mode S
    
* Mode S
  - Core benefits (30)
  - Timeline (30 years!!!!!)
  - 24 bit unique Address - like MAC Address :-) (33f)
  - Interrogation modes: All, Roll, + A/C (34)
    how often which?
  - Interrogation (Message) Structure
    Encoding (Phase Shift)
    Interop with Mode A/C (37)
  - Interrogation formats
  - Replies are Manchester Encoded. Meaning? (40ff)
    different message types encoded at beginning 
  - Actually Sessions/Protocol with several steps
    1) Acquire: identify. No output.
    2) Roll Call Start (no selectivity here!)
    3) Maintain
    4) Lock out (still safe??)
  - What kinds of identifiers and why?
    - Interrogator identifier
    - Surveillance Identifier
  - What is the lockout, and why is it useful?
    Selectivity!
    Area?
  - Active Coordination of multiple radars, data exchange.
  - Error Correction in Mode S - different from earlier modes!
    - Analytic
    - Brute Force
    - What is the confidence bitmap?
  - Side Lobe Suppression for Mode S
    - How?
    - Why different?
  - How is backward compatibility of Mode S transponders to old
    Mode A/C interrogators achieved? 
  - What about general datalink in Mode S?
    - Weather, Routing information, ATC clearances 
    - Why not really used in practice?
  - Elementary Surveillance 
    - Enhanced Surveillance
  - GICB, BDS registers
  - why are there problems when too many stations interrogate a transponder?
  - what about the integration of other aerial systems like gliders, paragliders, drones. How do you process and filter all relevant data? Possibility to even go to higher accuracy for drone flight control?
  
* Bigger Picture
  - Do we still need primary? Or everything ADS-B?  
    - Inmarsat's global ADS-B coverage idea. Enough power?
  - What is (wide area) MLAT?
    - what are the differences between SSR and MLAT?
    - what are the differences between ADS-B and MLAT?
    - will MLAT replace SSR (secondary surveillance radar)?
  - What kind of systems (e.g. autopilot) can be queried by the secondary radar ?  
  - What is the power range of those radars?
  - What impact does weather have on properties like range, accuracy, ...
    - what about wind turbines? I hear about "windfarm mitigation" radars in the UK.
  - Redundancy in radar systems?
  - Thoughts on Amateur tracking
    - It is amazing how anybody today can build ADS-B In station for less than 80 USD using SDR DVB-T dongle and 
	Raspberry Pi. Does this accessibility change anything on the original idea on how the technology is used?
    - e.g. https://www.flightradar24.com
    - Privacy/security issues?
	- Authentication of ADS-B Out and spoofing [DEF CON 20 - Hacking Airplanes - Brad Haines](https://www.youtube.com/watch?v=Pk1hjIMR3ro&t=1326s)
  - Impact of amateur tracking
    - Are there known cases of amateur dump1090 feeds (like to flightaware or flightradar24) being used 
	for "official" tracking of air planes, especially in areas where no "official" ADS-B In stations are 
	installed?


Stuff for the Shownotes
--------------------------------------

* http://www.radartutorial.eu/index.en.html
* https://www.skybrary.aero/index.php/Transponder
* https://www.skybrary.aero/index.php/Mode_S
* https://www.skybrary.aero/index.php/ADS-B
* http://www.eurocontrol.int/publications/ads-b-wam-implementation-europe

Contributors
-----------------------------------
* Committers of this file
* Richard Goiser
* Alex Wemmer
