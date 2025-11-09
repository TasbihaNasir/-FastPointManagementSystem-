# 🚌 FPMS - FAST Point Management System

A comprehensive console-based Bus Route Management System built in C, designed to streamline university transportation operations including route management, student registration, driver assignments, and real-time bus tracking.

---

## ⚛️ Built With

- **C (ANSI C)** — Procedural programming with standard libraries
- **File I/O** — Text file-based data persistence
- **String Manipulation** — Advanced tokenization and parsing
- **ANSI Color Codes** — Enhanced terminal user interface

---

## 👨‍💻 Developers

| Name | Role | Institution |
|------|------|-------------|
| Tasbiha Nasir | Developer | FAST University |
| Sofia Ayaz | Developer | FAST University |
| Zain Saqib | Developer | FAST University |

---

## 🧩 System Overview

FPMS is a university bus transportation management system that handles route planning, student registrations, driver assignments, and real-time bus location tracking. The system provides role-based access for management and students, ensuring efficient operation of university transport services.

---

## 🗄️ Core Features & Modules

### 🔐 Authentication System
- **PIN-Based Access**: Management access protected by PIN (1234)
- **Role-Based Menus**: Separate interfaces for Management and Students
- **Password Validation**: Retry mechanism with exit option

---

### 🗺️ Route Management
**Add New Routes**:
- Create custom bus routes with multiple stops
- Assign pickup locations with specific timings
- Automatic route numbering system
- Format: `RouteNumber*Location1*Time1*Location2*Time2*...*FAST`

**Check Routes by Location**:
- Search available routes by pickup point
- Display route number and pickup time
- Quick location-based route finder

---

### 👥 Student Management
**Register Students**:
- Student ID (7 characters)
- Student Name
- Route Number
- Pickup Location
- Automatic data persistence

**Check Student Status**:
- Verify student registration by ID
- View student route information
- Display name, location, and route number

**Change Student Route**:
- Update route assignments
- Modify pickup locations
- Maintain student records

---

### 🚗 Driver Management
**Register Drivers**:
- Driver ID assignment
- Driver Name
- Route Number allocation
- Driver-Route mapping

---

### 📍 GPS Tracking System
**Real-Time Bus Location**:
- Route-based tracking URLs
- Driver contact numbers
- Emergency contact information
- Format: `RouteNumber*CellNumber*TrackingURL*EmergencyContact`

**Location Services**:
- Check bus location by route number
- Access tracking links
- View driver contact details

---

## 📁 File Structure

```
FPMS/
│
├── akhri.c                    # Main program with ANSI colors
├── nocolor.c                  # Alternative version without colors
│
├── Data Files/
│   ├── Studentfile.txt        # Student records
│   ├── Driver.txt             # Driver information
│   ├── RouteFile.txt          # Route and stop details
│   └── TrackerInfo.txt        # GPS tracking data
│
└── README.md
```

---

## 🎯 Role-Based Features

### 🏢 Management Access
**Full System Control**:
1. Add New Route
2. Change Student Route
3. Register Student
4. Register Driver
5. Check Student Database

### 🎓 Student Access
**Information Services**:
1. Check Route Through Student ID
2. Search Routes by Pickup Location
3. Track Bus Location by Route Number

---

## ⚙️ Data Format Examples

### Studentfile.txt
```
23k0588*Zain*def*3
24K3830*Kashif*MadrasChowk*12
26K7507*Omar*G3Stop*8
```
Format: `StudentID*Name*PickupLocation*RouteNumber`

### Driver.txt
```
1001*2*Muhammad
1002*3*Ahmed
1003*4*Ali
```
Format: `DriverID*RouteNumber*DriverName`

### RouteFile.txt
```
2*KhatneNabuwotChowk*0625*KaneezFatima*0630*MadrasChowk*0632*G3Stop*0637*FAST
```
Format: `RouteNumber*Stop1*Time1*Stop2*Time2*...*FAST`

### TrackerInfo.txt
```
2*0317-1279801*https://www.location-link-service.com/bus-tracking/route-2*+92 3XX-XXXXXXX
```
Format: `RouteNumber*CellNumber*TrackingURL*EmergencyContact`

---

## 🚀 Setup Instructions

### Compilation

```bash
# With ANSI colors (Linux/macOS/Modern Windows Terminal)
gcc akhri.c -o fpms

# Without colors (Legacy systems)
gcc nocolor.c -o fpms

# Run
./fpms
```

### First Time Setup

1. **Ensure data files exist** in the same directory:
   - Studentfile.txt
   - Driver.txt
   - RouteFile.txt
   - TrackerInfo.txt

2. **Default Management PIN**: `1234`

3. **Run the program**:
   ```bash
   ./fpms
   ```

---

## 💡 Key Functions

### Student Operations
- `RegisterStudent()` - Add new student to system
- `CheckStudent()` - Verify student registration
- `checkroute()` - Display student's route info
- `ChangeRoute()` - Update student route/location

### Route Operations
- `AddRoute()` - Create new bus route
- `CheckPickup()` - Search routes by location
- `AddLocation()` - Add GPS tracking info

### Driver Operations
- `RegisterDriver()` - Register new driver
- `CheckLocation()` - Get bus tracking information

### Utility Functions
- `removeNewLineFromString()` - Clean input strings

---

## 🎨 User Experience

### ANSI Color Scheme (akhri.c)
- **Blue** (Cyan): Welcome messages
- **Green**: Management options
- **Yellow**: Menu options
- **Red**: Exit/Warning messages

### Menu Navigation
- Intuitive numbered menus
- Back/Exit options at each level
- Clear error messages
- Input validation

---

## 🔒 Security Features

- PIN-based management access
- Password retry mechanism
- Role-based access control
- Data validation on all inputs
- File operation error handling

---

## 📊 System Workflow

### Adding a New Route
```
1. Management logs in with PIN
2. Select "Add New Route"
3. Enter route number
4. Add stops with timings
5. End with "FAST"
6. System prompts for GPS tracking info
7. Data saved to RouteFile.txt and TrackerInfo.txt
```

### Student Registration
```
1. Management access required
2. Enter student details
3. Assign route and pickup location
4. Data saved to Studentfile.txt
5. Confirmation message displayed
```

### Checking Bus Location
```
1. Student selects tracking option
2. Enter route number
3. System displays:
   - Tracking URL
   - Driver contact number
   - Emergency contact
```

---

## 🔮 Future Enhancements

- [ ] SMS notifications for bus arrival
- [ ] Mobile app integration
- [ ] Real-time GPS tracking visualization
- [ ] Automated route optimization
- [ ] Student attendance tracking
- [ ] Multi-university support
- [ ] Database integration (SQLite)
- [ ] Web dashboard interface
- [ ] Payment integration for bus fees
- [ ] Emergency alert system

---

## 🐛 Known Limitations

- Fixed buffer sizes for input
- No multi-user concurrent access
- Manual PIN management
- Limited to text-based interface
- No data backup mechanism
- Single management PIN for all users

---



## 📄 License

Educational project created for FAST University coursework.

---

## 🙏 Acknowledgments

- FAST University for project guidance
- C Standard Library documentation
- University transport department for requirements
- Students for feedback and testing

---

## 🏁 Conclusion

FPMS provides an efficient solution for managing university bus transportation, offering route planning, student management, driver assignments, and real-time tracking—all essential features for modern campus mobility.

---

**💡 Developed By**

Tasbiha Nasir, Sofia Ayaz, and Zain Saqib  
*FAST Point Management System Team*  
*FAST University Transportation Project*
