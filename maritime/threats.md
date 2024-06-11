# Target of Evaluation: Modern Ship

| Identifier | System Name                                    | Function                                                                                               | Type | Network Reference  |
|------------|------------------------------------------------|--------------------------------------------------------------------------------------------------------|------|--------------------|
| 1          | Automatic Identification System (AIS)          | Monitors vessel traffic, prevents collisions, notifies ports and authorities of ship location.         | OT   | Production OT      |
| 2          | Electronic Chart Display and Information System (ECDIS) | Integrates and displays navigation data from various sensors.                                         | OT   | Production OT      |
| 3          | Global Positioning System (GPS) and Global Navigation Satellite System (GNSS) | Provides real-time ship positioning, speed, and route information.                                    | OT   | Production OT      |
| 4          | Radar                                           | Detects objects and provides information about ship surroundings.                                      | OT   | Production OT      |
| 5          | Global Maritime Distress System (GMDSS)         | Broadcasts distress messages and safety alerts.                                                        | OT   | Production OT      |
| 6          | Industrial Control Systems (ICSs)               | Controls and monitors various parameters and equipment on board.                                       | OT   | Production OT      |
| 7          | Very Small Aperture Terminal (VSAT)             | Enables satellite communication for data transmission and reception.                                   | IT   | Admin Network      |
| 8          | Propulsion and Machinery Management Systems     | Monitors and controls propulsion and machinery systems.                                                | OT   | Production OT      |
| 9          | Video Surveillance Systems (VSSs)               | Monitors ship operations and security.                                                                 | OT   | Management Network |
| 10         | IT Network Systems                              | Facilitates internal/external data processes, crew welfare, and personal device connectivity.           | IT   | Admin Network      |
| 11         | Integrated Bridge System (IBS)                  | Centralizes access to navigation and control systems on the bridge.                                    | OT   | Production OT      |
| 12         | Access Control Systems                          | Manages physical security and safety through digital surveillance and alarm systems.                    | Both | Management Network |
| 13         | Passenger Servicing and Management Systems      | Manages passenger-related data and services.                                                           | IT   | User Network       |
| 14         | Crew Welfare Systems                            | Provides internet and email access for crew, enhancing their welfare.                                  | IT   | User Network       |
| 15         | Communication Systems                           | Ensures ship connectivity through satellite, VHF, and other wireless communication means.              | IT   | Admin Network      |
| 16         | Dynamic Positioning Systems (DPS)               | Maintains the vessel's position using its own propellers and thrusters.                                 | OT   | Production OT      |
| 17         | Engine Monitoring and Control Systems           | Monitors and controls engine performance.                                                              | OT   | Production OT      |
| 18         | Safety and Security Networks                    | Monitors safety and security through CCTV and other networks.                                          | OT   | Management Network |




| Identifier | Name               | Description                                                  | Type of System |
|------------|--------------------|--------------------------------------------------------------|----------------|
| 1          | Admin Network      | Used for administrative tasks and access to sensitive data.  | IT             |
| 2          | User Network       | General access for employees to use business applications.   | IT             |
| 3          | Guest Network      | Isolated network for guest users with internet access only.  | IT             |
| 4          | Production OT      | Critical network for operational technology systems.         | OT             |
| 5          | Development OT     | Network for development and testing of OT systems.           | OT             |
| 6          | IoT Network        | Dedicated network for Internet of Things devices.            | OT             |
| 7          | DMZ                | Demilitarized zone for external-facing services.             | IT             |
| 8          | Backup Network     | Network dedicated for backup operations and data storage.    | IT             |
| 9          | Management Network | For management and monitoring of network infrastructure.     | IT             |


## Architecture Diagrams

## Threats

id| vulnerability | threat scenario| countermeasure
|--|--|--|--|
 1| insufficient authentication of pilots| Given any person can pretend to be a pilot, when they board the ship, the media they bring onboard can compromise the onboard systems| Validate credentials with the port authorities|
 2|media brought onboard may be contaminated| Given crew and externals might bring media with them, when they plug it in, then it can compromise onboard systems|Use a data sluice (hardened system, CDR of files, isolation network and compute environment)<br/>Port authority needs to wipe usb sticks after every use|
 3| unauthenticated and unsigned communication between ECDIS and GPS system| Given the communication inside the ECDIS network can be tampered with, when a bad actor is in that network, then the ECDIS will show incorrect information and the crew will steer badly| |
 4| GPS communication can be altered on the air| given GPS signals can be jammed and faked, then the system will represent the location at a wrong point in space| redundant satellite systems and detect contradictions <BR/> consider the physics of the signal when processing|
