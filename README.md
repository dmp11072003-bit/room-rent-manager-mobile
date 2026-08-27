# Room Rent Manager Mobile App

A comprehensive React Native mobile application for managing room rentals, tracking payments, and generating reports with PDF and WhatsApp sharing capabilities.

## Features

✨ **Key Features:**

- 📱 **Room Management** - Add and manage multiple rooms with tenant information
- 💰 **Rent Tracking** - Track monthly rent, utilities, and payment status
- 📊 **Dashboard** - View overall statistics and building summary at a glance
- 📄 **PDF Reports** - Generate detailed rent reports for each room
- 💬 **WhatsApp Integration** - Share payment summaries directly via WhatsApp
- 🏢 **Building Settings** - Configure building details and owner information
- 📝 **Payment History** - Complete payment history for each room with status tracking

## Tech Stack

- **React Native** with Expo - Cross-platform mobile development
- **TypeScript** - Type-safe JavaScript
- **React Navigation** - Seamless navigation experience
- **AsyncStorage** - Local data persistence
- **Expo File System** - File handling
- **Expo Sharing** - PDF and WhatsApp sharing

## Getting Started

### Prerequisites

- Node.js 14+ and npm installed
- Expo CLI: `npm install -g expo-cli`
- Android emulator or iOS simulator (or physical device with Expo Go app)

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/dmp11072003-bit/room-rent-manager-mobile.git
cd room-rent-manager-mobile
```

2. **Install dependencies:**
```bash
npm install
```

3. **Start the development server:**
```bash
expo start
```

4. **Run on your device:**
```bash
# For Android
expo start --android

# For iOS
expo start --ios

# Or scan QR code with Expo Go app
```

## Project Structure

```
room-rent-manager-mobile/
├── screens/                    # React Native screens
│   ├── DashboardScreen.tsx    # Overview and statistics
│   ├── RoomsScreen.tsx        # List of all rooms
│   ├── RoomDetailScreen.tsx   # Room details and payment history
│   ├── AddRoomScreen.tsx      # Add new room form
│   ├── ReportsScreen.tsx      # Generate and view reports
│   └── SettingsScreen.tsx     # Building configuration
├── src/
│   ├── types/                 # TypeScript interfaces
│   │   └── index.ts
│   ├── database/              # Local storage logic
│   │   └── storage.ts
│   └── services/              # Business logic
│       └── pdfService.ts
├── App.tsx                    # Main app component & navigation
├── app.json                   # Expo configuration
├── package.json               # Dependencies
└── README.md                  # This file
```

## Usage Guide

### Adding a Room

1. Navigate to the **Rooms** tab
2. Tap the **"Add Room"** button
3. Fill in the tenant details:
   - Room Number
   - Tenant Name
   - Mobile Number
   - Deposit Amount (optional)
   - Deposit Date
4. Tap **"Add Room"** to save

### Recording Rent Payments

1. Select a room from the rooms list
2. Tap on the room card to view details
3. Entry form to add monthly entries:
   - Month and Year
   - Rent amount
   - Light/Utility bills
   - Payment amount
   - Payment status

### Generating Reports

1. Go to the **Reports** tab
2. Select desired month/year using navigation buttons
3. Tap **"Generate All Reports"** to create PDFs for all rooms
4. Share reports as needed

### Sharing via WhatsApp

1. Open room details
2. Tap the **WhatsApp** button
3. Message with payment summary will be prepared
4. Confirm and send to the tenant

### Building Configuration

1. Go to **Settings** tab
2. Enter building details:
   - Building name
   - Address
   - Contact number
   - Owner name
3. Tap **"Save Settings"**

## Data Structure

### Room
```typescript
interface Room {
  id: string;              // Unique identifier
  roomNumber: string;      // Room identifier
  tenantName: string;      // Tenant's full name
  mobileNumber: string;    // Contact number
  depositAmount: number;   // Security deposit
  depositDate: string;     // Deposit payment date
}
```

### Rent Entry
```typescript
interface RentEntry {
  id: string;
  roomId: string;
  month: string;           // Month name
  year: number;           // Year
  rent: number;           // Base rent amount
  lightBill: number;      // Electricity charges
  totalAmount: number;    // Total charges
  amountPaid: number;     // Amount received
  balance: number;        // Remaining balance
  paymentStatus: 'PAID' | 'PENDING' | 'PARTIAL';
}
```

## Data Storage

- All data is stored **locally** on your device using AsyncStorage
- No internet connection required for basic operations
- Data persists between app sessions
- Future versions will include cloud backup options

## Features in Detail

### Dashboard
- Total rooms count
- Total amount collected
- Total pending balance
- Occupancy statistics

### Room Management
- Add unlimited rooms
- Edit room details
- View tenant information
- Track deposit amounts

### Payment Tracking
- Monthly payment entries
- Multiple charge types (rent, utilities)
- Payment status tracking
- Balance calculations

### PDF Reports
- Professional formatted reports
- Building information
- Room and tenant details
- Complete payment history
- Summary statistics

### WhatsApp Integration
- Quick payment notifications
- Balance information sharing
- Direct messaging to tenants

## Future Enhancements

- ☁️ Cloud backup and sync
- 🌐 Multi-language support (including Nepali)
- 📊 Advanced analytics and charts
- 💸 Expense tracking
- 📱 SMS notifications
- 📧 Email reports
- 🌙 Dark mode
- 💪 Offline mode improvements
- 🔒 Data encryption
- 📤 Import/Export functionality

## Known Limitations

- Reports generated as HTML (can be converted to PDF via printer)
- Requires Expo Go app for testing on physical devices
- Local storage limited to device capacity

## Troubleshooting

### App won't start
```bash
# Clear cache and reinstall
expo start --clear
npm install
```

### Data not saving
- Check device storage space
- Verify AsyncStorage permissions
- Clear app cache and data

### WhatsApp sharing not working
- Ensure WhatsApp is installed
- Verify phone number format
- Check device internet connection

## Performance Tips

- Keep number of rooms under 100 for optimal performance
- Archive old payment records periodically
- Clear app cache regularly
- Update to latest Expo version

## License

MIT License - Free to use for personal or commercial projects

## Support & Contribution

- 🐛 **Report bugs**: Create an issue on GitHub
- 💡 **Feature requests**: Open a discussion
- 🤝 **Contribute**: Submit pull requests

## Contact

**Developer**: dmp11072003-bit  
**Repository**: [GitHub](https://github.com/dmp11072003-bit/room-rent-manager-mobile)

---

**Made with ❤️ for property managers and landlords**
