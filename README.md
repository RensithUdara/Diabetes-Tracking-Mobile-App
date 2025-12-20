# 🏥 Diabetes Tracking Mobile App

A comprehensive Flutter mobile application designed to help diabetes patients manage their blood sugar levels, track medication intake, and monitor dietary habits. The app provides detailed analytics, reporting capabilities, and secure cloud storage of health records.

## ✨ Features

### 📊 Health Tracking
- **Blood Sugar Monitoring**: Record and track blood sugar levels throughout the day
- **Insulin Dose Tracking**: Log insulin injections and doses
- **Meal Logging**: Track food intake for each meal with detailed notes
- **Time-stamped Records**: Automatic timestamps for all entries

### 📈 Analytics & Reporting
- **Visual Charts**: Interactive charts powered by fl_chart for visualizing trends
- **Daily Reports**: Generate reports for specific dates
- **Data Export**: Export data to PDF format for sharing with healthcare providers
- **Statistical Analysis**: View patterns and trends in blood sugar levels

### 🔐 Authentication & Security
- **Firebase Authentication**: Secure user login and registration
- **Google Sign-In**: Easy authentication using Google accounts
- **Cloud Sync**: All data securely stored in Firebase Firestore
- **User-specific Data**: Each user's records are private and encrypted

### 📱 User Interface
- **Intuitive Design**: Clean, user-friendly interface with purple and pink theme
- **Multi-screen Navigation**: Easy navigation between different screens
- **Real-time Updates**: Live data synchronization across devices
- **Responsive Layout**: Works seamlessly on various screen sizes

### 🎯 Record Management
- **Sweet Entry**: Quick entry for blood sugar readings
- **Record Entry**: Detailed entry form with all medical parameters
- **Record History**: View all past records with filtering options
- **Edit & Delete**: Modify or remove records as needed

## 🚀 Getting Started

### Prerequisites
- Flutter SDK (>=3.6.0 <4.0.0)
- Dart SDK
- Firebase project setup
- Android emulator/device or iOS simulator/device
- Google Play Services (for Android)

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/diabetes-tracking-app.git
   cd diabetes-tracking-app
   ```

2. **Install Dependencies**
   ```bash
   flutter pub get
   ```

3. **Firebase Setup**
   - Create a Firebase project at [Firebase Console](https://console.firebase.google.com)
   - Download `google-services.json` and place it in `android/app/`
   - Download `GoogleService-Info.plist` and add it to iOS project (if building for iOS)
   - Enable Authentication methods:
     - Email/Password
     - Google Sign-In
   - Create Firestore Database in test mode

4. **Configure Google Sign-In**
   - Go to Firebase Project Settings
   - Download the configuration file
   - Ensure OAuth consent screen is configured in Google Cloud Console

5. **Build and Run**
   ```bash
   flutter run
   ```

## 📁 Project Structure

```
lib/
├── main.dart                    # App entry point & theme configuration
├── firebase_options.dart        # Firebase configuration
├── models/
│   ├── record_model.dart       # Data model for health records
│   └── record_provider.dart    # State management using Provider
├── screens/
│   ├── welcome_page.dart       # Welcome/landing screen
│   ├── auth_screen.dart        # Login and registration
│   ├── sweet_entry.dart        # Quick blood sugar entry
│   ├── sweet_list.dart         # View blood sugar history
│   ├── sweet_report.dart       # Blood sugar analytics
│   ├── record_entry.dart       # Detailed record entry
│   ├── record_list.dart        # Full record history
│   ├── record_report.dart      # Detailed analytics
│   └── generate_report.dart    # PDF report generation
└── services/
    ├── auth_service.dart       # Firebase authentication
    └── firebase_service.dart   # Firestore database operations
```

## 🛠️ Tech Stack

### Framework & Language
- **Flutter**: Cross-platform mobile development
- **Dart**: Programming language
- **Material Design**: UI design system

### Backend & Data
- **Firebase Core**: Backend services
- **Firebase Authentication**: User management
- **Cloud Firestore**: Real-time database
- **Google Sign-In**: OAuth authentication

### UI & UX
- **fl_chart**: Interactive charts and graphs
- **Provider**: State management
- **Material Components**: UI widgets

### Utilities
- **intl**: Internationalization and date formatting
- **path_provider**: File system access
- **permission_handler**: App permissions management
- **pdf**: PDF generation
- **open_file**: File opening capability

## 📊 Data Model

### Record Structure
Each health record contains:
- **userId**: User identifier
- **date**: Date of entry (YYYY-MM-DD format)
- **time**: Time of entry (HH:MM format)
- **mealTime**: When the measurement was taken (Breakfast, Lunch, Dinner, etc.)
- **sugar**: Blood sugar level (in mg/dL)
- **insulinDose**: Insulin dose administered (in units)
- **food**: Food consumed
- **remarks**: Additional notes or observations
- **timestamp**: Automatic server timestamp

## 🔒 Security Features

- **User Authentication**: Secure login with Firebase
- **Cloud Storage**: Data stored in encrypted Firestore
- **Privacy**: Each user can only access their own records
- **Permission Handling**: Proper permission requests for file access

## 📱 Screens Overview

| Screen | Purpose |
|--------|---------|
| Welcome Page | App introduction and navigation |
| Auth Screen | Login and user registration |
| Sweet Entry | Quick blood sugar logging |
| Sweet List | Browse blood sugar history |
| Sweet Report | Analytics for blood sugar |
| Record Entry | Comprehensive health data entry |
| Record List | Full medical record history |
| Record Report | Detailed medical analytics |
| Generate Report | Export data to PDF |

## 🎨 Theming

The app uses a purple and pink color scheme:
- **Primary Color**: Purple
- **Secondary Color**: Pink
- **Background**: White
- **Font**: Material Design typography

## 📊 Analytics Capabilities

- **Trend Analysis**: Visualize blood sugar patterns over time
- **Daily Statistics**: Average readings per day
- **Meal-based Analysis**: Compare readings across different meal times
- **PDF Reports**: Generate shareable reports for doctors

## 🔄 State Management

The app uses **Provider** package for efficient state management:
- `RecordProvider`: Manages all health records
- `AuthService`: Handles user authentication
- `FirebaseService`: Database operations

## 📥 Data Persistence

- **Cloud Storage**: All records are synced to Firebase Firestore
- **Real-time Sync**: Changes reflect immediately across devices
- **Offline Support**: App loads cached data when offline
- **Automatic Backup**: Firebase provides automatic daily backups

## 🚀 Building for Production

### Android
```bash
flutter build apk --release
```

### iOS
```bash
flutter build ios --release
```

### Web
```bash
flutter build web --release
```

## 🐛 Troubleshooting

### Firebase Connection Issues
- Ensure `google-services.json` is in `android/app/`
- Check Firebase project configuration
- Verify internet connectivity

### Google Sign-In Not Working
- Confirm Google OAuth consent screen is configured
- Check Google Sign-In setup in Firebase Console
- Verify SHA-1 fingerprint in Firebase

### Permission Errors
- Grant necessary permissions when prompted
- Check app settings in device settings
- Verify `permission_handler` configuration in AndroidManifest

### PDF Generation Issues
- Ensure write permission is granted
- Check available storage space
- Verify pdf package is properly installed

## 📝 Usage Guide

1. **First Launch**
   - Download and install the app
   - Create account with email or Google Sign-In
   - Grant necessary permissions

2. **Logging Records**
   - Tap "New Entry" to log blood sugar and insulin
   - Fill in all required fields
   - Add food and remarks if needed
   - Tap "Save"

3. **Viewing History**
   - Navigate to "Records" tab
   - View all past entries with timestamps
   - Tap any record to view details

4. **Analyzing Data**
   - Go to "Reports" tab
   - View interactive charts and statistics
   - Identify trends and patterns

5. **Exporting Data**
   - Use "Generate Report" option
   - Select date range
   - Export as PDF
   - Share with healthcare provider

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Support

For support, email support@diabetestracker.com or open an issue in the repository.

## 🙏 Acknowledgments

- Flutter team for the amazing framework
- Firebase for backend services
- fl_chart for visualization capabilities
- All contributors and testers

## 📚 Resources

- [Flutter Documentation](https://flutter.dev/docs)
- [Firebase Documentation](https://firebase.google.com/docs)
- [Provider Package](https://pub.dev/packages/provider)
- [Material Design](https://material.io/design)

## ⚕️ Medical Disclaimer

This app is designed as a personal health tracking tool and should not be used as a substitute for professional medical advice, diagnosis, or treatment. Always consult with qualified healthcare providers regarding your diabetes management. The creators assume no responsibility for any health outcomes related to the use of this application.

---

**Version**: 1.0.0  
**Last Updated**: December 2025  
**Developed with ❤️ using Flutter**
