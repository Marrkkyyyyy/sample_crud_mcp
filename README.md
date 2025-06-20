# Simple Notes App with Firebase

A clean, responsive note-taking web application built with vanilla HTML, CSS, and JavaScript that connects to Firebase Firestore for data storage.

## Features

- ✅ **Create** new notes with title and content
- ✅ **Read** and display all notes in a grid layout
- ✅ **Update** existing notes with inline editing
- ✅ **Delete** notes with confirmation
- 📱 Responsive design that works on mobile and desktop
- 🔄 Real-time data synchronization with Firebase
- ⌨️ Keyboard shortcuts (Enter to save, Ctrl+Enter for new line)

## Setup Instructions

### 1. Set up Firebase

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project or select an existing one
3. Enable Firestore Database:
   - Go to "Firestore Database" in the left sidebar
   - Click "Create database"
   - Choose "Start in test mode" for development
   - Select a location for your database
4. Get your Firebase configuration:
   - Go to Project Settings (gear icon)
   - Scroll down to "Your apps" section
   - Click "Web" icon to add a web app
   - Register your app and copy the configuration object

### 2. Configure the Application

1. Open `index.html` in a text editor
2. Find the Firebase configuration section:
   ```javascript
   window.firebaseConfig = {
       // Replace with your Firebase configuration
       apiKey: "your-api-key",
       authDomain: "your-project.firebaseapp.com",
       projectId: "your-project-id",
       storageBucket: "your-project.appspot.com",
       messagingSenderId: "123456789",
       appId: "your-app-id"
   };
   ```
3. Replace the placeholder values with your actual Firebase configuration

### 3. Run the Application

1. Open `index.html` in a web browser
2. Start creating notes!

**Note:** Due to CORS restrictions, you may need to serve the files through a local server rather than opening the HTML file directly. You can use:
- Python: `python -m http.server 8000`
- Node.js: `npx serve .`
- VS Code Live Server extension

## File Structure

```
notes-app/
├── index.html      # Main HTML structure
├── styles.css      # CSS styling and responsive design
├── script.js       # JavaScript functionality and Firebase integration
└── README.md       # This file
```

## Firebase Security Rules

For production use, update your Firestore security rules. Here's a basic example:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /notes/{document} {
      allow read, write: if true; // Replace with proper authentication rules
    }
  }
}
```

## Browser Compatibility

This app uses modern JavaScript features including:
- ES6 Modules
- Async/await
- Firebase v9+ modular SDK

Supported browsers:
- Chrome 61+
- Firefox 60+
- Safari 10.1+
- Edge 16+

## Customization

- **Colors**: Modify the CSS custom properties in `styles.css`
- **Layout**: Adjust the grid layout in the `.notes-grid` class
- **Functionality**: Extend the `NotesApp` class in `script.js`

## Troubleshooting

1. **Firebase not connecting**: Check your configuration and ensure Firestore is enabled
2. **CORS errors**: Serve the files through a local server
3. **Notes not saving**: Check browser console for errors and verify Firestore permissions
4. **Styling issues**: Ensure `styles.css` is properly linked in the HTML