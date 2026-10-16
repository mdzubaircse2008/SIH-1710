# Smart India Hackathon Workshop
# Date: 16/10/2026
## Register Number: 212225040252
## Name: Mohammed Zubair R
## Problem Title
SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations
## Problem Description
Background: Railway stations are complex environments with numerous facilities and locations such as ticket counters, platforms, restrooms, food courts, and waiting areas. Passengers often face difficulties in navigating these spaces, especially in large or unfamiliar stations. Efficient and user-friendly navigation systems are crucial for improving passenger experience, reducing congestion, and ensuring timely travel connections. Description: The problem involves developing a comprehensive navigation solution for railway stations that assists passengers in locating various facilities and destinations within the station premises. This includes creating detailed maps, providing real-time directions, and integrating features such as accessibility options for individuals with disabilities. The solution should be intuitive, easy to use, and accessible via multiple platforms, including mobile devices and digital kiosks. Key challenges include updating navigation information in real-time, ensuring accuracy, and accommodating the diverse needs of all passengers. Expected Solution: The expected solution is a multi-platform navigation system that provides detailed, real-time directions to all facilities and locations within a railway station. This system should include: A mobile application with 3D interactive maps and step-by-step navigation. Digital kiosks located throughout the station with touch-screen interfaces. Voice-guided navigation for visually impaired passengers. Regular updates to reflect changes in station layout and facility locations. Integration with existing railway apps and services for seamless user experience. The solution should enhance the overall passenger experience by reducing confusion, saving time, and improving accessibility within the station.

## Problem Creater's Organization
Ministry of Railway

## Idea
RailNav AI is an intelligent indoor railway station navigation platform designed to guide passengers seamlessly through large and crowded station environments. Unlike generic map tools, RailNav AI is purpose-built for indoor station layouts to help users locate platforms, ticket counters, food courts, waiting halls, restrooms, elevators, escalators, and exits. The system uses an AI-driven engine that evaluates live station data to recommend the most efficient path based on walking distance, crowd density, physical accessibility needs, and platform changes.

## Proposed Solution / Architecture Diagram
```
┌────────────────────────────────────────────────────────────────────────┐
│                        PASSENGER TOUCHPOINT LAYER                      │
│  ┌───────────────────────┐  ┌───────────────────┐  ┌────────────────┐  │
│  │Mobile App(iOS/Android)│  │Web App (QR Scan)  │  │ Station Kiosk  │  │
│  └───────────────────────┘  └───────────────────┘  └────────────────┘  │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                            USER INPUT LAYER                            │
│  • Current Location                   • Destination                    │
│  • Travel Preferences                 • Accessibility Requirements     │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                                AI ENGINE                               │
│  • Crowd Density Analysis             • Route Optimization             │
│  • Facility Detection                 • Accessibility Checks           │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                               DATA LAYER                               │
│  ┌─────────────────────────────────┐   ┌────────────────────────────┐  │
│  │      Indoor Map Database        │   │   Real-Time Data Service   │  │
│  │ • Floor Plans & Node Connections│   │ • Platform Updates         │  │
│  │                                 │   │ • Maintenance Closures     │  │
│  │                                 │   │ • Live Crowding Levels     │  │
│  └─────────────────────────────────┘   └────────────────────────────┘  │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                           NAVIGATION ENGINE                            │
│                  Calculates Optimal & Accessible Route                 │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
                                    ▼
┌────────────────────────────────────────────────────────────────────────┐
│                              OUTPUT LAYER                              │
│  🗺 Interactive 3D Maps               🧭 Turn-by-Turn Directions      │
│  🔊 Audio-Guided Prompts              🖥 Digital Kiosk Displays        │
└────────────────────────────────────────────────────────────────────────┘

```
## Use Cases
### 1. Passenger & Facility Navigation
* **Scenario:** A passenger enters the station and needs to locate "Platform 7" or a specific facility like a "Restroom" or "Food Court".
* **Action & Output:** The system identifies the passenger's current position via QR scan or beacon signal and generates a turn-by-turn route directly to the target facility.

### 2. Accessibility Navigation (Wheelchair / Elderly Mode)
* **Scenario:** A mobility-impaired passenger or elderly traveler requires step-free access throughout the station.
* **Action & Output:** The passenger toggles "Accessible Mode." The routing engine filters out staircases, escalators, and narrow paths, guiding the user exclusively through operational lifts, ramps, and wide corridors.

### 3. Voice-Guided Navigation for Visually Impaired Passengers
* **Scenario:** A visually impaired passenger needs to navigate safely without looking at a screen.
* **Action & Output:** The app activates screen-reader audio prompts (e.g., *"Walk straight 15 meters, then take the lift on your left"*) paired with tactile vibration cues at key turn points.

### 4. Inter-Platform Transfer Guidance
* **Scenario:** A passenger arriving on Platform 2 needs to transfer to Platform 8 to catch a connecting train.
* **Action & Output:** RailNav AI calculates an internal station transfer path using overbridges and elevators, keeping the user inside the station premises without sending them out toward entrance gates.

### 5. AI-Based Adaptive Route Selection
* **Scenario:** Multiple walkways lead to the destination, but some are heavily crowded or blocked.
* **Action & Output:** The AI engine analyzes live crowd density and facility status to automatically pick the fastest, least congested, or physically easiest route for the passenger.
 
## Technology Stack


| Layer | Component | Technology Used |
| :--- | :--- | :--- |
| **Frontend** | Mobile Application | Flutter / React Native |
| **Frontend** | Kiosk & Web App | React.js / HTML / CSS |
| **Backend** | API & Core Logic | Python (FastAPI) |
| **Intelligence** | AI & Pathfinding | Dijkstra / A* Algorithm, Scikit-learn |
| **Data & Storage** | Database | PostgreSQL + PostGIS, Firebase |
| **Positioning** | Location Tracking | QR Codes, BLE Beacons, Wi-Fi |
| **Accessibility** | Voice & Guidance | Web Speech API (Text-to-Speech) |
| **Communication**| Real-Time Updates | WebSockets, Firebase Realtime DB |
| **Deployment** | Cloud & Hosting | AWS / Render / Docker |

## Dependencies
The project requires core software tools including Python 3.x, Node.js, React Native, FastAPI, PostgreSQL, Firebase, Leaflet, and NetworkX. For hardware deployment during the prototype phase, the system depends on a standard laptop or PC server, Android smartphones for application testing, and printed QR codes for station entrance anchoring. Optional hardware dependencies for full-scale deployment include industrial Bluetooth Low Energy (BLE) beacons and interactive touch-screen display terminals for station kiosks.
