# IIT Kanpur Design and Animation Club Website

A modern, responsive single-page application for the IIT Kanpur Design and Animation Club that allows students to learn from curated YouTube videos and track their progress across four main domains: Photoshop, Illustrator, Digital Painting, and After Effects.

## Features

### ✨ Core Features
- **📱 Responsive Design**: Fully optimized for desktop, tablet, and mobile devices
- **🎨 Modern UI**: Beautiful interface built with Tailwind CSS and custom animations
- **🔐 User Authentication**: Login/signup with email/password or mock Google OAuth
- **📊 Progress Tracking**: Track watched videos and completion percentage for each domain
- **🎥 Video Integration**: Embedded YouTube videos with custom player modal
- **🔍 Search Functionality**: Search videos across all domains
- **📚 Resources Section**: Downloadable guides, templates, and external links
- **📞 Contact Form**: Contact form for reaching out to the club

### 🎯 Learning Domains
1. **Adobe Photoshop**: Photo editing, digital art, and image manipulation
2. **Adobe Illustrator**: Vector graphics, logo design, and illustrations
3. **Digital Painting**: Digital art techniques, color theory, and creative expression
4. **Adobe After Effects**: Motion graphics, animations, and visual effects

### 💾 Data Persistence
- User authentication data stored in localStorage
- Video watch progress tracked per user
- Cross-session persistence of learning progress

## Quick Start

### 🚀 Running Locally

1. **Download the website**:
   ```bash
   # Clone or download the project files
   # Ensure you have index.html in your project directory
   ```

2. **Open in browser**:
   - Simply double-click `index.html` to open in your default browser
   - Or right-click → "Open with" → choose your preferred browser
   - Or use a local server (recommended for development):

3. **Using a local server** (recommended):
   ```bash
   # Option 1: Python (if installed)
   python -m http.server 8000
   # Then visit http://localhost:8000

   # Option 2: Node.js (if installed)
   npx http-server
   # Then visit http://localhost:8080

   # Option 3: VS Code Live Server extension
   # Install Live Server extension and click "Go Live"
   ```

### 🌐 Deployment Options

#### Option 1: GitHub Pages
1. Create a new GitHub repository
2. Upload `index.html` to the repository
3. Go to Settings → Pages → Select source branch
4. Your site will be available at `https://yourusername.github.io/repository-name`

#### Option 2: Netlify
1. Visit [netlify.com](https://netlify.com)
2. Drag and drop your `index.html` file
3. Get instant deployment with a custom URL

#### Option 3: Vercel
1. Visit [vercel.com](https://vercel.com)
2. Import your GitHub repository or upload files
3. Automatic deployment with custom domain support

#### Option 4: Traditional Web Hosting
1. Upload `index.html` to your web hosting provider
2. Access via your domain name

## 🔧 Customization

### Adding Real YouTube Videos

Replace the placeholder video IDs in the `videoData` object (around line 40):

```javascript
const videoData = {
    photoshop: [
        {
            id: 'YOUR_YOUTUBE_VIDEO_ID', // Replace with actual YouTube video ID
            title: 'Your Video Title',
            thumbnail: 'https://img.youtube.com/vi/YOUR_YOUTUBE_VIDEO_ID/mqdefault.jpg',
            duration: '15:30' // Video duration
        },
        // Add more videos...
    ],
    // Repeat for other domains...
};
```

### Adding Resources

Update the `resourcesData` object (around line 85) to add downloadable resources:

```javascript
const resourcesData = {
    photoshop: [
        { 
            title: 'Your Resource Title', 
            type: 'PDF', // or 'Link', 'ZIP'
            url: 'https://your-resource-url.com' 
        },
        // Add more resources...
    ],
    // Repeat for other domains...
};
```

### Styling Customization

The website uses Tailwind CSS. You can modify:
- **Colors**: Change the primary color scheme by replacing `purple` classes
- **Fonts**: Modify font families in the Tailwind configuration
- **Custom CSS**: Add custom styles in the `<style>` section

### Backend Integration

To connect with a real backend:

1. **Replace localStorage functions** in the `Storage` object (around line 155)
2. **Add API calls** for user authentication
3. **Implement database storage** for progress tracking
4. **Add Firebase or similar** for real-time data sync

Example Firebase integration:
```javascript
// Replace localStorage with Firebase calls
const Storage = {
    getUser: async () => await firebase.auth().currentUser,
    setProgress: async (progress) => await firebase.firestore()
        .doc(`users/${userId}/progress`)
        .set(progress),
    // ... other methods
};
```

## 🛠️ Technical Stack

- **Frontend Framework**: React 18 (via CDN)
- **Styling**: Tailwind CSS
- **Icons**: Font Awesome 6
- **Build Tool**: Babel Standalone (for JSX compilation)
- **State Management**: React hooks (useState, useEffect)
- **Data Storage**: localStorage (easily replaceable with backend)
- **Video Player**: YouTube embedded iframe

## 📁 Project Structure

```
├── index.html          # Single-page application with all code
└── README.md          # This file
```

## 🔐 Authentication

The website includes a mock authentication system:

- **Email/Password Login**: Basic form validation
- **Google OAuth**: Mock implementation (replace with real OAuth)
- **Session Management**: Stored in localStorage
- **Progress Association**: Linked to user accounts

## 📱 Mobile Responsive Features

- **Collapsible Navigation**: Hamburger menu for mobile devices
- **Touch-Friendly**: Large buttons and touch targets
- **Optimized Layout**: Responsive grid systems
- **Fast Loading**: Optimized images and minimal dependencies

## 🔧 Browser Compatibility

- **Chrome**: Full support
- **Firefox**: Full support
- **Safari**: Full support
- **Edge**: Full support
- **Mobile Browsers**: Optimized for mobile viewing

## 📊 Analytics Integration

To add analytics, include tracking code before the closing `</body>` tag:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## 🚀 Performance Optimization

The website is already optimized for performance:

- **CDN Resources**: All libraries loaded from fast CDNs
- **Minimal Dependencies**: Only essential libraries included
- **Lazy Loading**: Images load efficiently
- **Compressed Assets**: Optimized file sizes

## 🤝 Contributing

To contribute to this project:

1. **Fork the repository**
2. **Make your changes** to index.html
3. **Test thoroughly** across different devices
4. **Submit a pull request** with detailed description

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 📞 Support

For support or questions:
- **Email**: designclub@iitk.ac.in
- **Club Hours**: Mon-Fri, 6:00 PM - 9:00 PM
- **Location**: IIT Kanpur, Uttar Pradesh, India

## 🔗 Useful Links

- [Adobe Photoshop Tutorials](https://helpx.adobe.com/photoshop/tutorials.html)
- [Adobe Illustrator User Guide](https://helpx.adobe.com/illustrator/user-guide.html)
- [Adobe After Effects Help](https://helpx.adobe.com/after-effects/user-guide.html)
- [React Documentation](https://reactjs.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)

---

**Made with ❤️ by IIT Kanpur Design and Animation Club**
