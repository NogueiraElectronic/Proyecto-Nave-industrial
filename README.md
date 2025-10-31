File > New > Project
- Template: Architectural Template - Metric
- Location: Vigo, Spain (Latitude: 42.2406°N, Longitude: 8.7207°W)
- Project Units: Metric (mm)
- North: True North orientation
```

**Project Information Setup:**
- Project Name: Industrial Warehouse - Vigo Tech Park
- Project Number: 2023-VIGO-IND-001
- Client: Consorcio Zona Franca Vigo
- Author: Jesús Torres Nogueira
- Issue Date: 2023

#### 2. Levels and Grids

**Levels Created:**
```
- Level 0 (±0.00): Ground floor slab
- Level 1 (+0.20): Industrial floor finish
- Level 2 (+3.50): First floor offices
- Level 3 (+7.00): Second floor offices
- Roof Level (+10.50): Roof structure
- Parapet (+11.00): Roof edge
```

**Grid System:**
```
- Longitudinal: A-F (6 grids at 5.0m spacing)
- Transverse: 1-8 (8 grids at 6.0m spacing)
- Total footprint: 30m x 48m
```

#### 3. Architectural Modeling Steps

**A. Site and Topography**
```
Massing & Site tab > Toposolid
- Import topographic survey data
- Create site boundary
- Define building pad elevation
- Model access roads and parking
- Add landscaping elements
```

**B. Walls and Partitions**

Industrial Area Exterior Walls:
```
Structure:
- Exterior: Metal sheet (1mm)
- Insulation: Mineral wool (80mm)
- Air cavity: (40mm)
- Vapor barrier: PE membrane
- Interior: Metal liner panel (0.6mm)

Total thickness: 125mm
Thermal transmittance (U): 0.38 W/m²K
```

Office Building Walls:
```
Exterior Walls:
- Ventilated facade: Composite panels (4mm)
- Air cavity: (50mm)
- Insulation: EPS (60mm)
- Block wall: Concrete block (150mm)
- Plaster interior: (15mm)

Total thickness: 279mm
U-value: 0.33 W/m²K

Interior Partitions:
- Metal studs: 70mm
- Plasterboard: 2x 15mm each side
- Acoustic insulation: 60mm
Total: 100mm
```

**C. Floors and Roofs**

Industrial Floor:
```
Structure (bottom to top):
- Compacted fill
- Lean concrete: 100mm
- Waterproofing membrane
- XPS insulation: 60mm
- Polyethylene sheet (damp proof)
- Reinforced concrete slab: 200mm
- Hardener surface treatment

Total: 360mm + fill
```

Office Floors:
```
Ground Floor:
- Reinforced concrete slab: 250mm
- Acoustic insulation: 40mm
- Leveling mortar: 50mm
- Technical raised floor system: 150mm
- Carpet tiles: 10mm

Upper Floors:
- One-way joist slab: 25+5cm
- Impact insulation: 40mm
- Screed: 50mm
- Ceramic tiles / Raised floor
```

Roof System:
```
- Metal deck
- Vapor barrier
- Thermal insulation: PIR 100mm
- Waterproofing membrane (2 layers)
- Gravel ballast (where accessible)

U-value: 0.32 W/m²K
```

**D. Windows and Doors**

Create Custom Families:

Industrial Doors:
```
- Overhead sectional doors: 5.0m x 5.0m
- Personnel doors: 1.0m x 2.1m (steel)
- Fire-rated doors: 1.2m x 2.1m (EI-60)
```

Office Windows:
```
- Curtain wall system: Mullion spacing 1.5m
- Vision panels: 6+16+6mm Low-E
- Spandrel panels: Insulated aluminum composite
- Window walls: Casement windows
- Skylight: Double polycarbonate panels
```

#### 4. Structural Model

**Linking Structural Model:**
```
Insert tab > Link Revit
- Link: Structural Model.rvt
- Positioning: Auto - Origin to Origin
- Display: By Host View
```

**Structural Elements Modeled:**

Foundations:
```
- Strip footings: 1.2m x 0.8m
- Pad foundations: 2.5m x 2.5m x 1.0m
- Ground beams: 0.4m x 0.6m
- Reinforcement details
```

Steel Frame:
```
- Columns: HEB 300 (height: 8.5m)
- Main beams: IPE 450
- Secondary beams: IPE 160
- Bracing: L 120x120x12
- Connections: Welded and bolted details
```

Concrete Structure (Offices):
```
- Columns: 40x40cm
- Beams: 40x60cm
- Slabs: One-way joists
- Stairs: Reinforced concrete
```

### MEP Systems Modeling

#### 1. Mechanical Systems

**HVAC Design:**

Industrial Zone:
```
System Type: Destratification fans + radiant heating
- Ceiling fans: 6 units (Ø 7.0m, 1.5kW each)
- Radiant tubes: Gas-fired (150kW total)
- Natural ventilation: Roof vents + louvers
- Exhaust fans: Local extraction (production areas)
```

Office Areas:
```
System Type: VRF (Variable Refrigerant Flow)
- Outdoor units: 2 x 28kW
- Indoor units: 14 cassettes (ceiling mounted)
- Heat recovery ventilation: 2,500 m³/h
- Ductwork: Insulated galvanized steel
- Zones: 8 independent zones
```

**Revit MEP Workflow:**

1. Create mechanical zones
```
Analyze tab > Spaces & Zones
- Define thermal zones
- Assign space types
- Calculate heating/cooling loads
```

2. Place equipment
```
Systems tab > Mechanical Equipment
- Select equipment families
- Connect to zones
- Route ductwork
- Size ducts automatically
```

3. Ductwork routing
```
- Main supply ducts: Rectangular 600x400mm
- Return ducts: Rectangular 500x300mm
- Branch ducts: Circular Ø200-300mm
- Insulation: 25mm thickness
- Fire dampers at penetrations
```

#### 2. Electrical Systems

**Power Distribution:**

Main Installation:
```
- Service voltage: 400V / 230V, 50Hz
- Main switchboard: 400A
- Sub-distribution boards: 4 units
- Backup generator: 150kVA (optional)
- UPS system: 20kVA (IT loads)
```

**Lighting Design:**

Industrial Area:
```
- High-bay LED luminaires: 150W, 5000K
- Mounting height: 8.0m
- Illuminance: 300 lux (average)
- Layout: 6m x 6m grid
- Emergency lighting: LED, 3h autonomy
- Daylight harvesting: Photocell control
```

Office Areas:
```
- LED panel lights: 40W, 4000K, 600x600mm
- Illuminance: 500 lux (desks)
- Emergency lighting: Maintained/Non-maintained
- Occupancy sensors: All spaces
- Dimming control: DALI system
```

**Revit Electrical Workflow:**

1. Electrical panel placement
```
Systems tab > Electrical Equipment
- Main panel at electrical room
- Sub-panels at each floor
- Define voltage and phase
```

2. Lighting layout
```
Systems tab > Lighting Fixtures
- Place fixtures on reflected ceiling plans
- Create lighting circuits
- Calculate lighting loads
- Generate lighting schedules
```

3. Power and data
```
- Power outlets: Every 3m on walls
- Data outlets: Co-located with power
- Cable trays: Main distribution routes
- Conduits: Branch circuits
```

#### 3. Plumbing Systems

**Domestic Water:**
```
- Supply: Municipal connection Ø100mm
- Distribution: Copper pipe network
- Hot water: Heat pump system, 300L tank
- Fixtures: Low-flow faucets and toilets
- Pressure: 2.5 bar (reduced from mains)
```

**Sanitary Drainage:**
```
- Gravity drainage system
- Soil stacks: PVC Ø110mm
- Branch lines: PVC Ø50-75mm
- Floor drains: Industrial area
- Sewage connection: Municipal system
- Grease trap: Kitchen/break room
```

**Rainwater Drainage:**
```
- Roof drainage: Internal system
- Primary drains: PVC Ø110mm
- Emergency overflow: Separate system
- Collection: 10,000L underground tank (irrigation)
```

**Revit Plumbing Workflow:**

1. System creation
```
Systems tab > Piping > Plumbing Fixtures
- Define systems (cold, hot, drainage)
- Place fixtures
- Connect to systems
```

2. Pipe routing
```
- Automatically route pipes
- Adjust routing preferences
- Add pipe accessories
- Size pipes based on flow
```

#### 4. Fire Protection

**Fire Detection:**
```
- Addressable fire alarm system
- Smoke detectors: Offices and warehouses
- Heat detectors: Kitchen
- Manual call points: At exits
- Sounders/visual alarms: All areas
- Control panel: Main entrance
```

**Fire Suppression:**
```
- Sprinkler system: Wet pipe
- Coverage: ESFR (Early Suppression Fast Response)
- Sprinkler spacing: 3.0m x 3.0m
- Design density: 12 mm/min
- Water supply: Municipal + tank (50m³)
- Fire pump: 500 L/min at 10 bar
```

### Coordination and Clash Detection

#### Navisworks Coordination

**Export from Revit:**
```
File > Export > NWC
- Export each discipline separately
- Architecture.nwc
- Structure.nwc
- MEP.nwc
```

**Clash Detection in Navisworks:**

1. Import all models
2. Run clash tests:
   - Structure vs MEP
   - Architecture vs Structure
   - MEP vs MEP (inter-discipline)
3. Generate clash reports
4. Assign clashes to team members
5. Track resolution in BIM 360

**Common Clashes Resolved:**
- Ductwork conflicts with steel beams (38 clashes)
- Electrical conduits through structural columns (12 clashes)
- Plumbing pipes conflicting with HVAC (8 clashes)
- Sprinkler heads below ceiling lights (15 clashes)

#### BIM Collaboration

**Autodesk BIM 360:**
- Central model hosting
- Real-time collaboration
- Issue tracking
- Document management
- Mobile access for site team

## Structural Analysis

### CYPE 3D Analysis

#### 1. Model Import and Setup

**Import from Revit:**
```
File > Import > IFC
- Select structural elements only
- Verify material properties
- Check section assignments
- Validate supports and connections
```

**Define Load Cases:**

Permanent Loads (G):
```
- Self-weight: Automatic calculation
- Dead load (finishes): 1.5 kN/m²
- Partition walls: 1.0 kN/m²
- MEP services: 0.5 kN/m²
```

Variable Loads (Q):
```
- Office use: 3.0 kN/m²
- Industrial area: 5.0 kN/m²
- Roof (maintenance): 1.0 kN/m²
- Snow load: 0.4 kN/m² (Vigo climate zone)
```

Wind Loads (W):
```
- Basic wind velocity: 26 m/s (CTE DB SE-AE)
- Terrain category: III (Industrial area)
- Building height: 10.5m
- Pressure coefficients: Per CTE
```

Seismic Loads (S):
```
- Peak ground acceleration: 0.04g (Low seismic zone)
- Importance factor: 1.0 (Normal importance)
- Ductility class: DCM (Medium)
- Response spectrum: Type 1, Soil C
```

Crane Loads:
```
- Crane capacity: 10 tons
- Runway beam: HEB 400
- Vertical load: 125 kN
- Horizontal load: 12.5 kN (lateral)
- Impact factor: 1.15
```

#### 2. Load Combinations

**Ultimate Limit States (ULS):**

Per CTE DB SE (Spanish Building Code):
```
1.35G + 1.50Q
1.35G + 1.50Q₁ + 1.05Q₂
1.35G + 1.50W
1.35G + 1.05Q + 1.50W
1.00G + 1.00S
1.00G + 0.50Q + 1.00S
```

**Serviceability Limit States (SLS):**
```
G + Q (Characteristic combination)
G + 0.7Q (Frequent combination)
G + 0.5Q (Quasi-permanent combination)
```

#### 3. Analysis Results

**Global Behavior:**

Maximum Displacements:
```
- Horizontal (wind): 45mm (< L/300 = 35m/300 = 116mm) ✓
- Vertical (roof): 28mm (< L/250 = 30m/250 = 120mm) ✓
- Crane beam: 15mm (< L/500 = 20m/500 = 40mm) ✓
```

Inter-story Drift:
```
- Office Level 1-2: 8mm (< 12mm limit) ✓
- Office Level 2-Roof: 6mm (< 12mm limit) ✓
```

Natural Frequencies:
```
- Mode 1 (X-direction): 2.85 Hz
- Mode 2 (Y-direction): 3.12 Hz
- Mode 3 (Torsion): 4.47 Hz
```

**Member Verification:**

Main Portal Frame:
```
Columns (HEB 300):
- Axial compression: 485 kN
- Bending moment: 125 kNm
- Utilization ratio: 0.78 (< 1.0) ✓
- Buckling check: λ = 0.65 (< 1.0) ✓

Rafters (IPE 450):
- Bending moment: 185 kNm
- Shear force: 95 kN
- Deflection: L/425 ✓
- Utilization: 0.82 (< 1.0) ✓
```

Crane Beam (HEB 400):
```
- Maximum moment: 245 kNm
- Fatigue check: Passed (detail category 71)
- Deflection: 12mm (< L/500) ✓
- Utilization: 0.91 (< 1.0) ✓
```

#### 4. Foundation Design

**CYPECAD Foundation Module:**

Pad Foundations:
```
Typical column foundation (400kN load):
- Size: 2.5m x 2.5m x 1.0m
- Reinforcement top: Ø16@200mm each way
- Reinforcement bottom: Ø20@150mm each way
- Concrete: HA-25/B/20/IIa
- Bearing pressure: 185 kPa (< 250 kPa allow able) ✓
```

Strip Footings (perimeter):
```
- Width: 1.2m
- Depth: 0.8m
- Reinforcement: Ø16@200mm longitudinal
- Stirrups: Ø10@250mm
```

Ground Beams:
```
- Section: 40cm x 60cm
- Top reinforcement: 4Ø20
- Bottom reinforcement: 4Ø16
- Stirrups: Ø10@150mm in support zones
```

#### 5. Connection Design

**CYPE Steel Connections:**

Base Plate Connections:
```
- Plate size: 600mm x 600mm x 30mm
- Anchor bolts: 4 x M30 (grade 8.8)
- Embedment: 500mm
- Grout thickness: 50mm
- Stiffeners: 4 x 200x200x15mm
- Utilization: 0.85 ✓
```

Beam-to-Column Connections:
```
Type: Bolted end plate
- End plate: 350mm x 350mm x 20mm
- Bolts: 8 x M20 (grade 10.9)
- Moment capacity: 275 kNm ✓
- Shear capacity: 450 kN ✓
```

Splice Connections:
```
- Location: Mid-span (roof beams)
- Splice plates: 2 x 400x20mm
- Bolts: 12 x M20
- Moment capacity: 200 kNm ✓
```

## MEP Engineering with CYPECAD MEP

### Electrical Installation Design

#### 1. Power Distribution System

**Main Distribution Board (MDB):**
```
Location: Electrical room (ground floor)
Incoming supply: 400V, 3-phase + N + PE
Main circuit breaker: 400A, 4-pole
Rated short-circuit capacity: 50kA

Outgoing circuits:
- Industrial sub-board: 250A
- Office sub-board 1: 100A
- Office sub-board 2: 100A
- HVAC equipment: 125A
- Lighting distribution: 80A
- Power outlets: 100A
- Emergency systems: 63A
```

**Cable Sizing:**

CYPECAD MEP automatic calculation based on:
- Load current
- Installation method (conduit, tray, buried)
- Ambient temperature (40°C industrial, 25°C office)
- Voltage drop limit (3% to sub-boards, 5% total)
- Protection coordination

Main Feeder Cable:
```
From: External transformer
To: MDB
Cable: 4x185mm² + 95mm² (Cu)
Voltage drop: 1.2% ✓
Installation: Underground duct
Protection: 400A MCCB
```

Industrial Sub-board Feeder:
```
Cable: 4x120mm² + 70mm² (Cu)
Length: 45m
Voltage drop: 1.8% (cumulative: 3.0%) ✓
Installation: Cable tray
Protection: 250A MCCB
```

#### 2. Lighting System Design

**Industrial Area Lighting:**

CYPECAD MEP Lighting Calculation:
```
Input Parameters:
- Room dimensions: 30m x 48m x 8.5m high
- Reflectances: Ceiling 50%, Walls 30%, Floor 20%
- Required illuminance: 300 lux
- Uniformity: > 0.7
- Maintenance factor: 0.8

Selected Luminaire:
- Type: LED High-bay
- Power: 150W
- Luminous flux: 21,000 lm
- Efficacy: 140 lm/W
- Color temperature: 5000K (daylight)
- CRI: >80
- IP rating: IP65
- Mounting height: 8.0m

Results:
- Number of luminaires: 42 units
- Layout: 6 rows x 7 columns
- Spacing: 5.0m x 6.0m
- Average illuminance: 315 lux ✓
- Minimum illuminance: 235 lux
- Uniformity: 0.75 ✓
- Installed power: 6.3 kW
- Power density: 4.4 W/m²
```

**Office Lighting:**
```
LED Panel Lights (600x600mm):
- Power: 40W
- Luminous flux: 4,400 lm
- Color temperature: 4000K (neutral white)
- CRI: >90
- UGR: <19 (anti-glare)
- Dimmable: 0-10V / DALI

Office Areas (Open plan):
- Average illuminance: 520 lux ✓
- Uniformity: 0.82 ✓
- Power density: 8.5 W/m²

Meeting Rooms:
- Average illuminance: 480 lux ✓
- Dimming zones: Individual room control
- Power density: 9.2 W/m²
```

**Emergency Lighting:**
```
Escape route lighting:
- Minimum: 1 lux horizontal
- Uniformity: > 40:1
- Duration: 3 hours
- LED technology (maintained/non-maintained)

Exit signs:
- Pictogram: ISO 7010 standard
- Viewing distance: 30m
- LED, 3h battery backup
```

#### 3. Grounding and Lightning Protection

**Grounding System:**

CYPECAD MEP Calculation:
```
Grounding method: Ring electrode
Conductor: Cu 50mm² bare
Configuration: Perimeter ring + vertical rods
Rod specifications: 2.0m length, Ø14mm
Number of rods: 12
Estimated resistance: 8 Ω (< 20 Ω required) ✓

Equipotential bonding:
- Main bonding: All structural steel
- Supplementary bonding: Bathrooms, kitchen
- Conductor size: 6-16mm² Cu
```

**Lightning Protection:**

Risk assessment per IEC 62305:
```
Risk factor R: 1.8 x 10⁻⁵ (< 10⁻⁴ acceptable) ✓
Protection required: Yes (Class III)

System design:
- Air terminals: Franklin rods + mesh
- Down conductors: 4 paths minimum
- Earth electrode: Integrated with grounding
- Separation distance: > 0.5m maintained
- SPD devices: Type 1+2 at main board
```

### HVAC System Design

#### 1. Thermal Load Calculation

**CYPETHERM Load Calculation Module:**

Industrial Area:
```
Winter Design Conditions:
- Outdoor: -2°C (97.5% heating design temp)
- Indoor setpoint: 16°C
- Relative humidity: Not controlled

Heating loads:
- Transmission losses: 45 kW
- Infiltration: 18 kW
- Ventilation: Not required (natural)
- Total heating load: 63 kW

Heating system sizing:
- Selected capacity: 75 kW (20% margin)
- System: Radiant tube heaters (gas)
- Number of units: 5 x 15kW
- Fuel: Natural gas
```

Office Areas:
```
Summer Design Conditions:
- Outdoor: 32°C DB / 23°C WB
- Indoor setpoint: 24°C / 50% RH
- Internal gains: 15 W/m² (equipment + occupancy)

Cooling loads:
- Sensible: 42 kW
- Latent: 8 kW
- Total cooling: 50 kW

Winter Heating:
- Heat loss: 35 kW
- Heating capacity: 45 kW

VRF System Sizing:
- Cooling capacity: 56 kW (selected)
- Heating capacity: 63 kW (selected)
- Number of outdoor units: 2 x 28kW
- Indoor units: 14 cassettes (2-6kW each)
- Piping: Refrigerant copper pipes
```

#### 2. Ventilation Design

**Office Ventilation:**

Per CTE DB-HS3 (Indoor Air Quality):
```
Category: IDA 2 (Office quality)
Required outdoor air: 12.5 L/s per person

Occupancy:
- Total occupants: 45 persons
- Outdoor air flow: 562 L/s (2,025 m³/h)

Mechanical Ventilation with Heat Recovery:
- Supply airflow: 2,500 m³/h
- Extract airflow: 2,500 m³/h
- Heat recovery efficiency: 75%
- Pressure drop: 250 Pa
- Fan power: 2 x 1.5 kW
- Filters: F7 (supply), F5 (extract)

Ductwork Design (CYPECAD MEP):
- Calculation method: Equal friction
- Velocity limit: 6 m/s main ducts, 3 m/s branches
- Pressure drop: 0.8 Pa/m
- Main duct: 600x400mm
- Material: Galvanized steel
- Insulation: 25mm (thermal + acoustic)
```

**Industrial Area Ventilation:**
```
Natural ventilation strategy:
- Roof ventilators: 4 units (extract)
- Motorized louvers: Supply air (lower walls)
- Control: Temperature sensors
- Airflow capacity: 15,000 m³/h (total)

Destratification:
- Ceiling fans: 6 units, Ø7.0m
- Airflow: 250,000 m³/h each
- Speed control: Variable
- Operation: Winter heating period
```

#### 3. Ductwork and Diffusers

**Supply Air Distribution:**
```
Diffuser selection (Offices):
- Type: 4-way square ceiling diffusers
- Sizes: 600x600mm (matching ceiling grid)
- Throw: 3.5m at 0.25 m/s terminal velocity
- Noise level: NC 30 (< NC 35 limit) ✓
- Quantity: 24 diffusers
- Airflow per diffuser: 80-120 m³/h

Return Air Grilles:
- Type: Egg-crate grilles
- Sizes: 600x600mm
- Location: Corridors (centralized return)
- Quantity: 12 grilles
```

### Plumbing System Design

#### 1. Domestic Water Supply

**CYPECAD MEP Water Calculation:**
```
Design population: 60 persons
Simultaneity factor: 0.35

Total demand:
- Cold water: 3.2 L/s (11.5 m³/h)
- Hot water: 1.8 L/s (6.5 m³/h)

Pipe sizing (method: Hunter):
Main distribution (copper):
- Service connection: Ø50mm
- Horizontal mains: Ø40mm
- Risers: Ø32mm
- Branches: Ø20-25mm
- Velocity: < 2.0 m/s ✓
- Pressure: 2.0-3.0 bar (PRV installed)

Hot Water System:
- Heat pump water heater: 8 kW
- Storage tank: 300L (stratified)
- Distribution: Recirculation loop
- Temperature: 60°C (storage), 45°C (use)
- Insulation: 30mm closed-cell foam
- Legionella control: Thermal disinfection 70°C weekly
```

#### 2. Sanitary Drainage

**Drainage System Sizing:**
```
Method: Unit discharge method (CTE HS-5)

Soil stacks:
- Main stacks: Ø110mm PVC
- Branch connections: Ø50-75mm
- Vent pipes: Ø75mm (extend to roof)

Floor drains:
- Industrial area: Ø110mm @ 10m spacing
- Gully traps: Ø110mm with sieves
- Slope: 2% minimum

Horizontal drains:
- Building drain: Ø160mm
- Connection to sewer: Ø200mm
- Slope: 2%
- Cleanouts: Every 15m maximum

Special installations:
- Grease trap: 150L capacity (kitchen)
- Pump station: Toilet below grade (if required)
```

#### 3. Rainwater Drainage

**Roof Drainage Design:**
```
Rainfall intensity: 125 mm/h (50-year return period, Vigo)
Roof area: 1,500 m²

Drainage capacity required:
Q = (I x A) / 3,600 = (125 x 1,500) / 3,600 = 52 L/s

Primary system:
- Roof drains: 8 units, Ø110mm
- Down pipes: Ø110mm PVC
- Capacity per drain: 7 L/s
- Total capacity: 56 L/s ✓

Emergency overflow:
- Separate drainage system
- Scuppers through parapet
- Capacity: 100% of primary
```

**Rainwater Harvesting (Optional):**
```
Collection system:
- First flush diverter: 200L
- Underground storage tank: 10,000L
- Submersible pump: 3.0 kW
- Treatment: Filtration + UV
- Use: Landscape irrigation
- Payback period: 8 years
```

### Fire Protection Systems

#### 1. Fire Detection and Alarm

**System Design (CYPECAD MEP):**
```
System type: Addressable analog
Standard: EN 54

Devices:
- Control panel: 2-loop, 250 devices
- Smoke detectors: 48 units (optical)
- Heat detectors: 12 units (rate-of-rise, 60°C)
- Manual call points: 8 units
- Sounders: 12 units (85 dB @ 3m)
- Visual alarms: 8 units (for accessibility)

Coverage:
- Detector spacing: 7.5m x 7.5m (offices)
- Detector spacing: 10.0m x 10.0m (warehouse)
- Height limit: 12m ✓

Zones:
- Office ground floor: Zone 1
- Office first floor: Zone 2
- Industrial area: Zone 3
- Electrical room: Zone 4
```

#### 2. Automatic Sprinkler System

**CYPECAD MEP Hydraulic Calculation:**
```
Design standard: UNE-EN 12845
Hazard classification: OH2 (Ordinary Hazard, Group 2)

Design parameters:
- Design area: 216 m² (most remote)
- Design density: 7.5 mm/min
- Required flow: 27 L/s (1,620 L/min)
- Duration: 60 minutes

Sprinkler head specifications:
- Type: Pendent, K=80 (standard response)
- Temperature rating: 68°C (ordinary)
- Spacing: 3.0m x 3.0m
- Coverage per head: 9 m²
- Total heads: 180 units

Piping network:
- Material: Sch40 black steel
- Main: DN100 (4")
- Branches: DN32-50 (1¼"-2")
- Installation method: Wet pipe
- Hose connections: DN65 every 50m

Water supply:
- Source: Municipal + underground tank
- Tank capacity: 100 m³
- Fire pump: 50 L/s @ 10 bar
- Backup: Electric + diesel
- Jockey pump: 5 L/s @ 12 bar (pressure maintenance)
```

## Energy Efficiency Analysis

### CYPETHERM HE Plus - Thermal Analysis

#### 1. Thermal Envelope Characterization

**Building Geometry Input:**
```
Total conditioned area: 2,150 m²
- Offices: 650 m²
- Industrial (heated): 1,500 m²

Compactness: 0.95 m (Volume/Surface area)
Orientation: Main facade facing South
```

**U-Values Summary:**
```
Component                 | U-value  | Regulation | Status
--------------------------|----------|------------|-------
Exterior walls (offices)  | 0.33     | ≤ 0.50     | ✓
Exterior walls (indust.)  | 0.38     | ≤ 0.50     | ✓
Roof                      | 0.32     | ≤ 0.38     | ✓
Ground floor slab         | 0.35     | ≤ 0.50     | ✓
Windows                   | 1.20     | ≤ 1.80     | ✓
Thermal bridges          | ψ<0.5    | Control    | ✓
```

**Solar Control:**
```
Solar factor (g-value):
- South windows: 0.40 (Low-E glazing)
- North windows: 0.55 (Standard double glazing)
- Skylights: 0.35 (with shading)

Shading devices:
- External blinds: South facade offices
- Overhangs: 0.8m projection
- Internal blinds: All windows
```

**Airtightness:**
```
Target: n50 ≤ 6 h⁻¹ (at 50Pa)
Measures:
- Membrane/barriers at joints
- Sealed window installations
- Service penetrations sealed
- Testing: Blower door test during construction
```

#### 2. Energy Demand Calculation

**Heating Demand:**
```
Calculation method: Hourly dynamic simulation
Climate file: Vigo (Spain) - Zone C1

Office Areas:
- Specific demand: 32 kWh/m²·year
- Total demand: 20,800 kWh/year
- Peak load: 45 kW

Industrial Area (16°C setpoint):
- Specific demand: 18 kWh/m²·year
- Total demand: 27,000 kWh/year
- Peak load: 63 kW

Total heating demand: 47,800 kWh/year
CTE DB-HE1 limit: 55 kWh/m²·year ✓
Performance: 13% better than regulation
```

**Cooling Demand:**
```
Office Areas (24°C setpoint):
- Specific demand: 28 kWh/m²·year
- Total demand: 18,200 kWh/year
- Peak load: 50 kW (sensible + latent)

Industrial Area:
- Not cooled (natural ventilation)

Total cooling demand: 18,200 kWh/year
CTE limit: Not exceeded ✓
```

**Domestic Hot Water (DHW):**
```
Daily consumption: 45 persons x 3 L/day/person = 135 L/day
Annual consumption: 49,275 L/year

Energy demand:
- Temperature rise: 45°C (from 10°C to 55°C)
- Specific energy: 0.058 kWh/L
- Annual demand: 2,858 kWh/year

CTE DB-HE4 requirement:
- Minimum solar contribution: 30%
- Alternative: Heat pump with COP > 2.5 ✓
- Selected: Air-to-water heat pump (COP 3.2)
```

#### 3. Primary Energy Consumption

**System Efficiencies:**
```
Heating:
- Gas radiant tubes: η = 0.90
- VRF heat pump: SPF = 3.5 (seasonal)

Cooling:
- VRF system: SEER = 5.2

DHW:
- Heat pump water heater: COP = 3.2

Ventilation:
- Fans with heat recovery: SFP = 1.8 W/(L/s)
- Heat recovery efficiency: 75%
```

**Primary Energy Calculation:**
```
Energy carrier conversion factors (Spain):
- Electricity: 1.954 kWhp/kWhe
- Natural gas: 1.082 kWhp/kWhf

Electricity consumption:
- Cooling: 18,200 / 5.2 = 3,500 kWhe
- Heating (offices): 20,800 / 3.5 = 5,943 kWhe
- DHW: 2,858 / 3.2 = 893 kWhe
- Fans: 4,500 kWhe
- Lighting: 15,000 kWhe
- Equipment: 22,000 kWhe
Total electricity: 51,836 kWhe/year

Gas consumption (heating industrial):
- 27,000 / 0.90 = 30,000 kWhf/year

Primary energy:
- Electricity: 51,836 x 1.954 = 101,287 kWhp
- Gas: 30,000 x 1.082 = 32,460 kWhp
Total: 133,747 kWhp/year

Specific primary energy: 62.2 kWhp/m²·year

CTE DB-HE0 limit: 85 kWhp/m²·year (Zone C1) ✓
Performance: 27% better than regulation
```

#### 4. CO₂ Emissions
```
Emission factors (Spain):
- Electricity: 0.331 kgCO₂/kWhe (2023 grid mix)
- Natural gas: 0.252 kgCO₂/kWhf

Annual emissions:
- Electricity: 51,836 x 0.331 = 17,158 kgCO₂
- Gas: 30,000 x 0.252 = 7,560 kgCO₂
Total: 24,718 kgCO₂/year

Specific emissions: 11.5 kgCO₂/m²·year
```

#### 5. Energy Efficiency Rating

**Spanish Energy Certificate:**
```
Rating scale: A (best) to G (worst)

This building:
- Primary energy: 62.2 kWhp/m²·year
- CO₂ emissions: 11.5 kgCO₂/m²·year

Final rating: B (High efficiency)

Comparison to reference building:
- Energy savings: 27%
- Emission reduction: 29%
```

### Energy Improvement Measures

#### Implemented Measures:

1. **Enhanced Insulation**
   - Cost: €45,000
   - Savings: 8,500 kWh/year
   - Payback: 8.5 years

2. **High-Efficiency Glazing**
   - Cost: €28,000
   - Savings: 5,200 kWh/year
   - Payback: 9.2 years

3. **LED Lighting with Controls**
   - Cost: €35,000
   - Savings: 12,000 kWh/year
   - Payback: 4.9 years

4. **VRF System (vs. conventional)**
   - Extra cost: €18,000
   - Savings: 7,800 kWh/year
   - Payback: 3.8 years

5. **Heat Recovery Ventilation**
   - Cost: €22,000
   - Savings: 9,500 kWh/year
   - Payback: 3.9 years

**Total Investment in Efficiency:** €148,000
**Total Annual Savings:** €7,600 (electricity + gas)
**Overall Payback:** 19.5 years
**Lifecycle (30 years) Savings:** €78,000 net

## Budget and Cost Estimation

### Bill of Quantities - CYPE Presto

#### Budget Breakdown by Chapter
```
MATERIAL EXECUTION BUDGET

Chapter                                    | Amount (€)    | %
------------------------------------------|---------------|-------
1. SITE PREPARATION                        | 38,588.43     | 5.1%
2. STRUCTURE                               | 203,741.37    | 27.1%
3. FACADES AND PARTITIONS                  | 111,700.89    | 14.8%
4. CARPENTRY, IRONWORK, GLAZING            | 71,131.32     | 9.5%
5. INSTALLATIONS (MEP)                     | 84,784.01     | 11.3%
6. INSULATION AND WATERPROOFING            | 70,572.93     | 9.4%
7. FINISHES AND FLOORING                   | 171,888.75    | 22.8%
------------------------------------------|---------------|-------
MATERIAL EXECUTION BUDGET                  | 752,407.70    | 100%

Total budget amount: SEVEN HUNDRED FIFTY-TWO THOUSAND FOUR HUNDRED SEVEN EUROS AND SEVENTY CENTS
```

### Detailed Budget Chapters

#### Chapter 1: Site Preparation (38,588.43 €)
```
1.1 Site Clearance and Demolition
    - Vegetation removal: 2,500 m² @ 1.20 €/m² = 3,000.00 €
    - Topsoil excavation: 500 m³ @ 3.50 €/m³ = 1,750.00 €
    - Debris removal: 75 ton @ 15.00 €/ton = 1,125.00 €

1.2 Earthworks
    - Bulk excavation: 850 m³ @ 8.50 €/m³ = 7,225.00 €
    - Foundation trenches: 320 m³ @ 12.00 €/m³ = 3,840.00 €
    - Backfill compacted: 280 m³ @ 6.50 €/m³ = 1,820.00 €
    - Soil disposal: 600 m³ @ 9.00 €/m³ = 5,400.00 €

1.3 Services and Infrastructure
    - Water connection: 1 unit @ 3,200.00 € = 3,200.00 €
    - Sewer connection: 1 unit @ 4,500.00 € = 4,500.00 €
    - Electric supply: 1 unit @ 5,800.00 € = 5,800.00 €
    - Telecom ducts: 85 m @ 12.50 €/m = 1,062.50 €

Subtotal: 38,722.50 €
```

#### Chapter 2: Structure (203,741.37 €)
```
2.1 Foundations
    - Pad foundations: 18 units @ 850.00 € = 15,300.00 €
    - Strip footings: 145 m @ 125.00 €/m = 18,125.00 €
    - Ground beams: 85 m @ 180.00 €/m = 15,300.00 €
    - Foundation waterproofing: 485 m² @ 18.50 €/m² = 8,972.50 €

2.2 Steel Structure (Industrial)
    - Main columns HEB 300: 8.5 ton @ 1,850.00 €/ton = 15,725.00 €
    - Portal frame beams IPE 450: 12.2 ton @ 1,750.00 €/ton = 21,350.00 €
    - Purlins and bracing: 18.5 ton @ 1,650.00 €/ton = 30,525.00 €
    - Crane beam HEB 400: 3.8 ton @ 2,100.00 €/ton = 7,980.00 €
    - Base plates and anchors: 24 units @ 280.00 € = 6,720.00 €
    - Connections and bolts: 1 lot @ 8,500.00 € = 8,500.00 €
    - Surface treatment and painting: 48 ton @ 420.00 €/ton = 20,160.00 €

2.3 Concrete Structure (Offices)
    - Columns 40x40: 28 m³ @ 385.00 €/m³ = 10,780.00 €
    - Beams 40x60: 18 m³ @ 395.00 €/m³ = 7,110.00 €
    - One-way joist slabs: 385 m² @ 95.00 €/m² = 36,575.00 €

2.4 Concrete Works
    - Industrial floor slab: 1,500 m² @ 55.00 €/m² = 82,500.00 €

Subtotal: 305,622.50 €
(Adjusted with indirect costs to chapter total)
```

#### Chapter 3: Facades and Partitions (111,700.89 €)
```
3.1 Industrial Envelope
    - Sandwich wall panels: 850 m² @ 75.00 €/m² = 63,750.00 €
    - Roof sandwich panels: 1,550 m² @ 68.00 €/m² = 105,400.00 €
    - Flashings and trims: 285 m @ 25.00 €/m = 7,125.00 €
    - Skylights polycarbonate: 95 m² @ 145.00 €/m² = 13,775.00 €

3.2 Office Facades
    - Ventilated facade system: 420 m² @ 185.00 €/m² = 77,700.00 €
    - Composite cladding panels: 420 m² @ (included above)

3.3 Interior Partitions
    - Metal stud + plasterboard: 285 m² @ 45.00 €/m² = 12,825.00 €
    - Acoustic insulation: 285 m² @ 8.50 €/m² = 2,422.50 €

Subtotal: 282,997.50 €
(Proportional adjustment applied)
```

#### Chapter 4: Carpentry, Ironwork, Glazing (71,131.32 €)
```
4.1 Exterior Carpentry
    - Curtain wall system: 185 m² @ 285.00 €/m² = 52,725.00 €
    - Office windows aluminum: 95 m² @ 195.00 €/m² = 18,525.00 €
    - Overhead sectional doors: 4 units @ 3,800.00 € = 15,200.00 €
    - Personnel doors (steel): 6 units @ 450.00 € = 2,700.00 €
    - Fire doors EI-60: 4 units @ 1,250.00 € = 5,000.00 €

4.2 Interior Carpentry
    - Interior doors: 18 units @ 285.00 € = 5,130.00 €
    - Toilet partitions: 12 units @ 350.00 € = 4,200.00 €
    - Built-in wardrobes: 8 m @ 450.00 €/m = 3,600.00 €

4.3 Ironwork
    - Steel stairs: 2 flights @ 4,500.00 € = 9,000.00 €
    - Handrails and railings: 85 m @ 125.00 €/m = 10,625.00 €
    - Metal catwalks: 45 m @ 380.00 €/m = 17,100.00 €

Subtotal: 143,805.00 €
(Proportional to chapter)
```

#### Chapter 5: Installations - MEP (84,784.01 €)
```
5.1 Electrical Installation
    - Main switchboard 400A: 1 unit @ 8,500.00 € = 8,500.00 €
    - Sub-distribution boards: 4 units @ 2,200.00 € = 8,800.00 €
    - Wiring and conduits: 1 lot @ 18,500.00 € = 18,500.00 €
    - LED lighting fixtures: 68 units @ 285.00 € = 19,380.00 €
    - Emergency lighting: 24 units @ 185.00 € = 4,440.00 €
    - Power outlets: 120 units @ 45.00 € = 5,400.00 €
    - Grounding system: 1 lot @ 3,800.00 € = 3,800.00 €

5.2 HVAC System
    - VRF outdoor units: 2 units @ 9,500.00 € = 19,000.00 €
    - Indoor cassettes: 14 units @ 1,450.00 € = 20,300.00 €
    - Ductwork and insulation: 1 lot @ 12,000.00 € = 12,000.00 €
    - Radiant tube heaters: 5 units @ 2,200.00 € = 11,000.00 €
    - Ventilation fans: 8 units @ 1,250.00 € = 10,000.00 €
    - Heat recovery unit: 1 unit @ 8,500.00 € = 8,500.00 €

5.3 Plumbing
    - Water distribution: 1 lot @ 8,500.00 € = 8,500.00 €
    - Sanitary drainage: 1 lot @ 6,500.00 € = 6,500.00 €
    - Rainwater drainage: 1 lot @ 5,200.00 € = 5,200.00 €
    - Fixtures and fittings: 1 lot @ 4,800.00 € = 4,800.00 €
    - Hot water system: 1 unit @ 5,500.00 € = 5,500.00 €

5.4 Fire Protection
    - Fire alarm system: 1 lot @ 9,500.00 € = 9,500.00 €
    - Sprinkler system: 1 lot @ 28,500.00 € = 28,500.00 €
    - Fire extinguishers: 18 units @ 85.00 € = 1,530.00 €

Subtotal: 219,650.00 €
(Adjusted proportionally)
```

#### Chapter 6: Insulation and Waterproofing (70,572.93 €)
```
6.1 Thermal Insulation
    - Roof insulation PIR: 1,550 m² @ 28.00 €/m² = 43,400.00 €
    - Wall insulation mineral wool: 850 m² @ 18.00 €/m² = 15,300.00 €
    - Floor insulation XPS: 1,500 m² @ 12.00 €/m² = 18,000.00 €
    - Pipe insulation: 1 lot @ 3,800.00 € = 3,800.00 €

6.2 Waterproofing
    - Roof membrane (2-layer): 1,550 m² @ 35.00 €/m² = 54,250.00 €
    - Foundation waterproofing: 485 m² @ 22.00 €/m² = 10,670.00 €
    - Flashings and seals: 1 lot @ 4,500.00 € = 4,500.00 €

Subtotal: 149,920.00 €
(Adjusted to chapter)
```

#### Chapter 7: Finishes and Flooring (171,888.75 €)
```
7.1 Floor Finishes
    - Industrial epoxy coating: 1,500 m² @ 35.00 €/m² = 52,500.00 €
    - Raised technical floor: 450 m² @ 85.00 €/m² = 38,250.00 €
    - Ceramic tile flooring: 200 m² @ 45.00 €/m² = 9,000.00 €
    - Carpet tiles: 250 m² @ 32.00 €/m² = 8,000.00 €

7.2 Wall Finishes
    - Plasterboard finishing: 850 m² @ 18.00 €/m² = 15,300.00 €
    - Painting walls: 1,200 m² @ 8.50 €/m² = 10,200.00 €
    - Ceramic wall tiles: 85 m² @ 38.00 €/m² = 3,230.00 €

7.3 Ceiling Finishes
    - Suspended ceiling acoustic: 650 m² @ 42.00 €/m² = 27,300.00 €
    - Industrial ceiling: 1,500 m² @ 12.00 €/m² = 18,000.00 €

7.4 Exterior Works
    - Paving and sidewalks: 380 m² @ 45.00 €/m² = 17,100.00 €
    - Asphalt parking: 520 m² @ 28.00 €/m² = 14,560.00 €
    - Landscaping: 1 lot @ 8,500.00 € = 8,500.00 €
    - Fencing: 185 m @ 85.00 €/m = 15,725.00 €
    - Signage and marking: 1 lot @ 3,200.00 € = 3,200.00 €

Subtotal: 240,865.00 €
(Adjusted)
```

### Total Project Budget Summary
```
================================================================
TOTAL PROJECT BUDGET - INDUSTRIAL WAREHOUSE VIGO
================================================================

Material Execution Budget (PEM):           752,407.70 €

General expenses (13%):                     97,813.00 €
Industrial profit (6%):                     45,144.46 €
                                           -----------
Subtotal:                                  895,365.16 €

VAT (21%):                                 188,026.68 €
                                           -----------
TOTAL CONTRACT AMOUNT:                   1,083,391.84 €

================================================================
Total amount: ONE MILLION EIGHTY-THREE THOUSAND THREE HUNDRED 
NINETY-ONE EUROS AND EIGHTY-FOUR CENTS
================================================================

Unit costs:
- Per m² (built area):        433.36 €/m²
- Per m² (usable area):        469.25 €/m²
- Per m³:                      103.18 €/m³
```

## Technical Documentation

### Deliverables Package

#### BIM Models
- Architecture model (Revit): 245 MB
- Structure model (Revit): 128 MB
- MEP model (Revit): 187 MB
- Federated model (Navisworks): 520 MB
- IFC exports: 3 files

#### Drawing Sheets (PDF)
1. **General drawings** (5 sheets)
   - Site plan 1:500
   - Floor plans 1:100
   - Sections and elevations 1:100

2. **Architectural drawings** (15 sheets)
   - Detailed floor plans
   - Reflected ceiling plans
   - Facade details
   - Interior elevations
   - Door and window schedules

3. **Structural drawings** (12 sheets)
   - Foundation plan
   - Steel framing plans
   - Connection details
   - Reinforcement details
   - Structural sections

4. **MEP drawings** (18 sheets)
   - Electrical single-line diagrams
   - Power and lighting layouts
   - HVAC plans and details
   - Plumbing risers and plans
   - Fire protection layouts

#### Calculations and Reports
- Structural calculations: 145 pages
- Energy analysis report: 58 pages
- MEP calculations: 92 pages
- Fire safety report: 35 pages
- Acoustics report: 28 pages

#### Specifications
- General specifications: 85 pages
- Technical specifications by trade: 320 pages
- Material data sheets: 150+ documents

#### Cost Documentation
- Bill of quantities: Excel (2,500+ items)
- Budget breakdown: PDF (45 pages)
- Cost estimate summary: PDF (12 pages)

## Regulatory Compliance

### Spanish Building Code (CTE)

**DB-SE (Structural Safety):**
- SE-AE: Actions in building - Compliant
- SE-C: Concrete foundations - Compliant
- SE-A: Steel structures - Compliant
- SE-F: Masonry structures - N/A

**DB-SI (Fire Safety):**
- Fire resistance: EI-60 structure
- Escape routes: < 50m to exit
- Fire sectors: Properly compartmented
- Detection and alarm: Addressable system
- Suppression: Automatic sprinklers

**DB-SUA (Safety in Use and Accessibility):**
- Fall protection: Railings h=1.10m
- Slip resistance: Class 2 floors
- Accessibility: Zero barriers, elevator
- Lighting: Emergency + evacuation

**DB-HS (Health and Hygiene):**
- Damp protection: Membranes + drainage
- Waste collection: Dedicated areas
- Indoor air quality: Mechanical ventilation
- Water supply: Potable system
- Wastewater: Proper drainage

**DB-HR (Noise Protection):**
- Airborne insulation: Rw ≥ 50 dB
- Impact insulation: Ln,w ≤ 65 dB
- Facade insulation: D2,m,nT,Atr ≥ 30 dB

**DB-HE (Energy Efficiency):**
- HE0: Primary energy limitation - Rating B
- HE1: Energy demand limitation - Compliant
- HE2: Solar contribution DHW - Alternative heat pump
- HE3: Efficient lighting - LED + controls
- HE4: Minimum solar contribution - Compliant
- HE5: Renewable energy generation - Not required

### Additional Regulations

**REBT (Low Voltage Electrotechnical Regulation):**
- Electrical installation compliant
- Grounding system verified
- Protection devices coordinated

**RITE (Thermal Installations Regulation):**
- HVAC system efficiency verified
- Indoor comfort conditions met
- Maintenance plan established

**Industrial Regulations:**
- Overhead crane certification
- Pressure equipment (if applicable)
- Industrial safety signage

## Implementation Guide

### How to Replicate This Project

#### Phase 1: Initial Setup (Week 1)

**1.1 Site Analysis**
```
Tasks:
1. Obtain topographic survey
2. Review zoning regulations
3. Identify site constraints
4. Analyze access and utilities
5. Document existing conditions

Tools:
- AutoCAD for survey processing
- Google Earth for context
- Local planning department resources
```

**1.2 Project Brief Development**
```
Define:
- Functional requirements
- Space program (areas needed)
- Budget constraints
- Timeline requirements
- Client preferences

Create:
- Adjacency diagrams
- Preliminary space allocation
- Conceptual budget
```

**1.3 Software Setup**
```
Install and configure:
1. Autodesk Revit 2023
   - Download from Autodesk website
   - Install with architecture + MEP + structure
   - Configure project template

2. CYPE Software
   - CYPECAD for structures
   - CYPECAD MEP for installations
   - CYPETHERM HE Plus for energy
   - Register and activate licenses

3. Supporting Software
   - Lumion or Enscape for rendering
   - Navisworks for coordination
   - Bluebeam for PDF markup
```

#### Phase 2: BIM Modeling (Weeks 2-6)

**2.1 Revit Project Setup**

Step 1: Create Project
```
File > New > Project
- Select metric template
- Set project location (Vigo coordinates)
- Configure units (mm)
- Set up shared coordinates
```

Step 2: Establish Levels and Grids
```
Architecture tab > Level
- Create all vertical levels
- Adjust level names and elevations
- Set up structural grids (6m x 5m typical)
- Name grid lines (A-F, 1-8)
```

Step 3: Load Required Families
```
Insert tab > Load Family
Download from:
- Autodesk Family Library
- BIMobject.com
- Manufacturer websites (windows, doors, MEP equipment)

Custom families to create:
- Corporate door/window types
- Specific steel connections
- Custom light fixtures
```

**2.2 Architectural Model Development**

Week 2-3: Basic Model
```
Day 1-2: Exterior Walls
- Create wall types with correct layering
- Model perimeter walls
- Add openings for doors/windows

Day 3-4: Interior Layout
- Model interior partitions
- Create rooms and spaces
- Tag and schedule spaces

Day 5-6: Floors and Roofs
- Model floor assemblies
- Create roof structure
- Add skylights

Day 7-8: Vertical Circulation
- Model stairs (component vs. sketch)
- Add elevator shaft
- Create ramps if needed

Day 9-10: Curtain Walls and Glazing
- Define curtain wall types
- Apply to facades
- Customize mullion patterns
- Add doors in curtain walls
```

Week 4: Detailing
```
- Develop wall sections
- Create detail callouts
- Add annotations
- Refine door/window families
- Model casework and fixtures
```

**2.3 Structural Model**

Step 1: Link Architectural Model
```
Insert tab > Link Revit
- Link architecture model
- Display as underlay in structural views
```

Step 2: Foundation Design (CYPECAD)
```
1. Start new project in CYPECAD
2. Import DXF grid layout from Revit
3. Define load hypotheses
4. Input soil properties:
   - Allowable bearing capacity: 250 kPa
   - Coefficient of subgrade reaction
5. Place columns at grid intersections
6. Design foundation system:
   - Pad foundations for columns
   - Strip footings for perimeter
7. Run calculations
8. Export to DWG for Revit import
```

Step 3: Steel Structure (CYPE 3D)
```
1. Create 3D structural model
2. Define member sections:
   - Columns: HEB 300
   - Beams: IPE 450
   - Purlins: IPE 160
3. Input loads:
   - Dead loads
   - Live loads
   - Wind (automatic generation)
   - Crane loads
4. Run analysis:
   - Linear elastic analysis
   - Code checks per Eurocode 3
5. Optimize sections if needed
6. Design connections
7. Export to IFC for Revit
```

Step 4: Concrete Structure (Offices)
```
In Revit Structure:
1. Model concrete columns (40x40cm)
2. Model beams (40x60cm)
3. Create one-way joist floor families
4. Structural framing tool for reinforcement
5. Rebar placement and detailing
6. Generate schedules
```

**2.4 MEP Systems Modeling**

Electrical (Week 5):
```
Day 1: Equipment placement
- Main switchboard in electrical room
- Sub-boards at each level/zone
- Define voltage and phases

Day 2-3: Lighting layout
- Place fixtures on RCP
- Create circuits (max 10 fixtures per circuit)
- Add switches and controls
- Generate lighting schedules

Day 4: Power distribution
- Place power outlets
- Create power circuits
- Cable tray routing
- Emergency power circuits

Day 5: Systems analysis
- Load calculations (automatic)
- Voltage drop verification
- Short circuit calculations in CYPECAD MEP
```

Mechanical (Week 5):
```
Day 1: HVAC equipment
- Place VRF outdoor units
- Place indoor cassettes in office spaces
- Define mechanical spaces

Day 2-3: Ductwork
- Create supply air system
- Route main ducts
- Add branches to diffusers
- Create return air system
- Size ducts automatically

Day 4: Ventilation
- Heat recovery unit placement
- Fresh air distribution
- Exhaust systems

Day 5: Controls
- Thermostats
- Sensors
- Control wiring (symbolic)
```

Plumbing (Week 6):
```
Day 1-2: Domestic water
- Water service entry
- Distribution risers
- Branch piping to fixtures
- Hot water system

Day 3-4: Drainage
- Sanitary drainage
- Vent piping
- Floor drains
- Connection to sewer

Day 5: Special systems
- Rainwater drainage
- Fire protection (sprinklers)
- Grease trap
```

**2.5 Coordination and Clash Detection**

Week 6:
```
1. Export all models to NWC
2. Open in Navisworks
3. Run clash detection:
   - Hard clashes (intersections)
   - Soft clashes (clearance violations)
4. Generate clash report
5. Assign clashes to disciplines
6. Hold coordination meeting
7. Resolve clashes in native models
8. Re-check in Navisworks
9. Document resolutions
```

#### Phase 3: Energy Analysis (Week 7)

**3.1 CYPETHERM HE Plus Workflow**

Step 1: Project Setup
```
1. Launch CYPETHERM HE Plus
2. New project: Industrial Warehouse
3. Location: Vigo (select from database)
4. Building type: Mixed (industrial + office)
5. Climate zone: C1 (automatic)
```

Step 2: Geometry Input
```
Option A: Import from IFC (Revit)
- File > Import > IFC
- Select architectural model
- Verify geometry import

Option B: Manual modeling
- Define building orientation
- Input floor by floor
- Draw thermal envelope
- Define spaces and uses
```

Step 3: Thermal Properties
```
For each construction element:
1. Exterior walls
   - Layers from inside to outside
   - Material properties (λ, ρ, cp)
   - Calculate U-value
   - Verify against limits

2. Roof
   - Assembly definition
   - Insulation thickness
   - U-value verification

3. Ground floor
   - Slab construction
   - Perimeter insulation
   - U-value calculation

4. Windows
   - Frame type
   - Glazing specification
   - U-value and g-value

5. Thermal bridges
   - Perimeter slab
   - Corners
   - Window frames
   - ψ-values from library or calculation
```

Step 4: Systems Definition
```
Heating:
- Gas radiant tubes (industrial)
  * Efficiency: 90%
  * Fuel: Natural gas
- VRF heat pump (offices)
  * COP: 3.5
  * Power source: Electricity

Cooling:
- VRF system
  * EER: 5.2
  * Power: Electricity

DHW:
- Heat pump water heater
  * COP: 3.2
  * Storage: 300L

Ventilation:
- Mechanical with heat recovery
  * Flow rate: 2,500 m³/h
  * Heat recovery: 75%
  * SFP: 1.8 W/(L/s)
```

Step 5: Run Simulations
```
1. Click "Calculate"
2. Wait for hourly simulation (5-10 minutes)
3. Review results:
   - Heating demand
   - Cooling demand
   - DHW demand
   - Primary energy consumption
   - CO₂ emissions
   - Energy rating
4. Check compliance with CTE DB-HE
5. Generate official certificate
```

Step 6: Optimization (if needed)
```
If not compliant:
1. Increase insulation thickness
2. Improve window U-values
3. Reduce thermal bridges
4. Improve system efficiencies
5. Add renewable energy
6. Re-run simulation
7. Compare results
```

#### Phase 4: Documentation (Weeks 8-10)

**4.1 Drawing Production**

Week 8: Architectural Drawings
```
In Revit:
1. Create sheets
   - File > New > Sheet
   - Use title block template
   - Set up sheet list

2. Place views on sheets
   - Drag from Project Browser
   - Adjust scale (1:100, 1:50, 1:20)
   - Add annotations
   - Add dimensions
   - Add keynotes

3. Drawing types to create:
   - A0.0: Cover sheet
   - A1.x: Site and context plans
   - A2.x: Floor plans
   - A3.x: Elevations
   - A4.x: Sections
   - A5.x: Detailed plans
   - A6.x: Details (1:5, 1:1)
   - A7.x: Schedules

4. Export to PDF
   - File > Export > PDF
   - Settings: High quality
   - Combine into single file
```

Week 9: Structural and MEP Drawings
```
Similar process for:
- S-series: Structural drawings
- E-series: Electrical drawings
- M-series: Mechanical drawings
- P-series: Plumbing drawings
- FP-series: Fire protection drawings
```

**4.2 Specifications Writing**
```
Structure (example):
===================
03 30 00 CAST-IN-PLACE CONCRETE

1. GENERAL
   1.1 Related Documents
   1.2 Summary
   1.3 References
   1.4 Submittals
   1.5 Quality Assurance

2. PRODUCTS
   2.1 Concrete Materials
       - Cement: CEM II/A-L 42.5 R
       - Aggregate: Per EHE-08
       - Water: Potable
   2.2 Concrete Mixes
       - Foundations: HA-25/B/20/IIa
       - Columns/beams: HA-25/B/20/IIa
       - Slabs: HA-25/B/20/IIa
   2.3 Reinforcing Steel
       - Type: B 500 S
       - Finish: As delivered

3. EXECUTION
   3.1 Formwork
   3.2 Reinforcement Placement
   3.3 Concrete Placement
   3.4 Finishing
   3.5 Curing
   3.6 Quality Control

Repeat for all trades...
```

**4.3 Budget Extraction**

Using CYPE Presto:
```
1. Import quantities from Revit
   - Export schedules to Excel
   - Import into Presto

2. Assign unit prices
   - Use regional cost database
   - Input custom prices
   - Apply subcontractor quotes

3. Organize by chapter
   - Chapter 1: Site preparation
   - Chapter 2: Structure
   - Chapter 3: Facades
   - etc.

4. Calculate totals
   - Material + labor
   - General expenses (13%)
   - Profit (6%)
   - VAT (21%)

5. Generate budget report
   - Summary by chapter
   - Detailed bill of quantities
   - Unit price breakdown
   - Export to PDF/Excel
```

#### Phase 5: Coordination and Final Review (Week 11-12)

**5.1 Quality Control Checklist**
```
☐ BIM Model Checks:
  ☐ All views updated
  ☐ No warnings (or documented)
  ☐ Families loaded correctly
  ☐ Correct phasing
  ☐ Clash detection complete
  ☐ All spaces enclosed

☐ Drawing Checks:
  ☐ Title blocks complete
  ☐ Scales correct
  ☐ Dimensions consistent
  ☐ Details referenced
  ☐ North arrows present
  ☐ Legends complete

☐ Calculation Checks:
  ☐ Structural calcs signed
  ☐ Load paths verified
  ☐ Energy analysis approved
  ☐ MEP sizing confirmed
  ☐ Code compliance documented

☐ Budget Checks:
  ☐ All items priced
  ☐ Quantities verified
  ☐ Totals accurate
  ☐ Allowances noted
  ☐ Exclusions listed

☐ Specifications:
  ☐ Complete for all trades
  ☐ Cross-referenced with drawings
  ☐ Product selections confirmed
  ☐ Performance criteria clear
```

**5.2 Final Deliverables Assembly**
```
Create delivery package:

1. BIM_Models/
   - Architecture.rvt
   - Structure.rvt
   - MEP.rvt
   - Federated.nwf
   - IFC_exports/

2. Drawings/
   - 00_Cover_and_Index.pdf
   - 01_Architectural.pdf (50 sheets)
   - 02_Structural.pdf (35 sheets)
   - 03_MEP.pdf (45 sheets)
   - 04_Details.pdf (28 sheets)

3. Specifications/
   - General_Conditions.pdf
   - Technical_Specifications_by_Trade.pdf

4. Calculations/
   - Structural_Calculations.pdf
   - Energy_Analysis_Report.pdf
   - MEP_Calculations.pdf

5. Budget/
   - Bill_of_Quantities.xlsx
   - Budget_Summary.pdf
   - Cost_Estimate_Breakdown.pdf

6. Reports/
   - Energy_Certificate.pdf
   - Fire_Safety_Report.pdf
   - Accessibility_Report.pdf

7. 3D_Visualizations/
   - Renderings/ (12 images)
   - Animation.mp4
   - VR_model.exe
