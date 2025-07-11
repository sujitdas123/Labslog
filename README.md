# Lab Log and Issue Reporting System

A comprehensive web application for managing programming lab resources, tracking student usage, and handling technical issues. Built with modern web technologies and designed for educational institutions.

## 🚀 Features

### Core Functionality
- **Issue Reporting**: Students can report technical problems and bugs
- **Lab Usage Tracking**: Log and monitor lab session activities
- **Role-Based Access**: Separate interfaces for students and technicians
- **Real-time Updates**: Live data synchronization across all users

### Advanced Features
- **Analytics Dashboard**: Comprehensive data visualization and insights
- **Advanced Search**: Multi-criteria filtering with date ranges
- **Bulk Actions**: Mass operations for issue management
- **Export Tools**: CSV/JSON data export capabilities
- **System Monitoring**: Real-time performance tracking
- **Notifications Center**: Alert system for important updates

### User Roles
- **Students**: Report issues, log lab usage, view personal statistics
- **Technicians**: Manage all issues, access analytics, system administration
- **Technical Assistants**: First-level support and daily operations
- **Junior Technicians**: Training and basic system management

## 🛠️ Technology Stack

### Frontend
- **React** with TypeScript
- **Tailwind CSS** for styling
- **Radix UI** components
- **TanStack Query** for state management
- **React Hook Form** for form handling
- **Wouter** for routing

### Backend
- **Node.js** with Express
- **PostgreSQL** with Drizzle ORM
- **Firebase Authentication**
- **RESTful API** architecture

### Build Tools
- **Vite** for development and build
- **ESBuild** for production bundling
- **TypeScript** for type safety

## 📦 Installation

### Prerequisites
- Node.js 18+ 
- npm or yarn
- PostgreSQL database (optional for development)

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/lab-management-system.git
   cd lab-management-system
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   
   Fill in your environment variables:
   ```env
   DATABASE_URL=postgresql://username:password@localhost:5432/labmanagement
   VITE_FIREBASE_API_KEY=your_firebase_api_key
   VITE_FIREBASE_PROJECT_ID=your_firebase_project_id
   VITE_FIREBASE_APP_ID=your_firebase_app_id
   ```

4. **Run the development server**
   ```bash
   npm run dev
   ```

5. **Open your browser**
   Navigate to `http://localhost:5000`

## 🔧 Configuration

### Firebase Setup
1. Create a new Firebase project at [Firebase Console](https://console.firebase.google.com/)
2. Enable Authentication with Anonymous sign-in
3. Copy your Firebase configuration keys to `.env`

### Database Setup
- **Development**: Uses in-memory storage (no setup required)
- **Production**: Requires PostgreSQL database
- **Migrations**: Run `npm run db:push` to apply schema changes

## 🚀 Deployment

### Free Hosting Options

#### Vercel (Recommended)
1. Connect your GitHub repository to Vercel
2. Add environment variables in Vercel dashboard
3. Deploy automatically on git push

#### Netlify
1. Connect repository to Netlify
2. Build command: `npm run build`
3. Publish directory: `dist`

#### Railway
1. Connect GitHub repository
2. Add environment variables
3. Railway will auto-deploy on push

#### Render
1. Connect GitHub repository
2. Configure build and start commands
3. Add environment variables

### Production Build
```bash
npm run build
npm start
```

## 📊 Usage

### For Students
1. **Report Issues**: Fill out the issue form with problem details
2. **Log Lab Usage**: Record your lab sessions and activities
3. **View Dashboard**: Check your usage statistics and history

### For Technicians
1. **Manage Issues**: View, filter, and update all reported issues
2. **Analytics**: Access detailed reports and performance metrics
3. **System Monitoring**: Track system health and performance
4. **Bulk Operations**: Perform mass actions on issues and logs

## 🔒 Security

- Role-based access control
- Input validation and sanitization
- Secure authentication with Firebase
- Environment variable protection
- CSRF protection

## 📈 Performance

- Optimized bundle size with tree shaking
- Lazy loading for improved initial load time
- Efficient caching with TanStack Query
- Responsive design for all devices

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Documentation**: Check the [docs](docs/) folder for detailed guides
- **Issues**: Report bugs and request features in [GitHub Issues](https://github.com/yourusername/lab-management-system/issues)
- **Discussions**: Join the community in [GitHub Discussions](https://github.com/yourusername/lab-management-system/discussions)

## 🎯 Roadmap

- [ ] Mobile app development
- [ ] Advanced reporting features
- [ ] Integration with learning management systems
- [ ] Multi-language support
- [ ] Dark mode theme
- [ ] Email notifications
- [ ] API documentation
- [ ] Docker containerization

## 🙏 Acknowledgments

- Built with love for educational institutions
- Inspired by modern web development practices
- Community feedback and contributions welcome

---

**Made with ❤️ for better lab management**