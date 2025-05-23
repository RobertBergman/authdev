# AuthDev - Flask OAuth Authentication

A secure Flask web application demonstrating OAuth 2.0 authentication with Google, built with modern security practices and comprehensive dependency management.

## 🚀 Features

- **Google OAuth 2.0 Integration**: Secure authentication using Google's OAuth service
- **Session Management**: Secure user session handling with Flask sessions
- **Security Hardened**: All dependencies updated to address security vulnerabilities
- **Production Ready**: Configured with Gunicorn for production deployment
- **Comprehensive Security**: Zero known vulnerabilities with up-to-date dependencies

## 🛡️ Security

This project maintains high security standards:
- ✅ **All Dependabot alerts resolved** (8 vulnerabilities fixed)
- ✅ **Latest secure dependency versions**
- ✅ **Comprehensive .gitignore** protecting sensitive files
- ✅ **Security documentation** with update history

See [SECURITY_UPDATES.md](SECURITY_UPDATES.md) for detailed security information.

## 📋 Prerequisites

- Python 3.7+
- Google OAuth 2.0 credentials
- Git

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/RobertBergman/authdev.git
   cd authdev
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv .venv
   # On Windows:
   .venv\Scripts\activate
   # On macOS/Linux:
   source .venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## ⚙️ Configuration

### 1. Google OAuth Setup

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing one
3. Enable the Google+ API
4. Create OAuth 2.0 credentials:
   - Application type: Web application
   - Authorized redirect URIs: `http://localhost:5000/authorize`

### 2. Environment Variables

Create a `.env` file in the project root:

```env
GOOGLE_CLIENT_ID=your_google_client_id_here
GOOGLE_CLIENT_SECRET=your_google_client_secret_here
FLASK_SECRET_KEY=your_secure_secret_key_here
```

**Note**: The `.env` file is automatically ignored by Git for security.

### 3. Alternative: Environment Variables (Windows)

```cmd
set GOOGLE_CLIENT_ID=your_google_client_id_here
set GOOGLE_CLIENT_SECRET=your_google_client_secret_here
```

## 🚀 Usage

### Development Server

```bash
python app.py
```

The application will be available at `http://localhost:5000`

### Production Deployment

```bash
gunicorn -w 4 -b 0.0.0.0:8000 app:app
```

## 📁 Project Structure

```
authdev/
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── .gitignore            # Git ignore rules
├── SECURITY_UPDATES.md   # Security update documentation
├── README.md             # Project documentation
└── templates/            # HTML templates
    ├── authorize.html    # OAuth authorization page
    ├── hello.html        # Welcome page
    ├── login.html        # Login page
    └── oauth_error.html  # Error handling page
```

## 🔐 Security Features

- **OAuth 2.0**: Secure authentication without storing passwords
- **Session Security**: Secure session management with strong secret keys
- **Dependency Security**: All packages updated to latest secure versions
- **Environment Protection**: Sensitive configuration via environment variables
- **HTTPS Ready**: Configurable for production HTTPS deployment

## 🛠️ Development

### Running Tests

```bash
# Install development dependencies
pip install pytest pytest-flask

# Run tests
pytest
```

### Code Quality

```bash
# Install development tools
pip install black flake8 mypy

# Format code
black .

# Lint code
flake8 .

# Type checking
mypy .
```

## 📝 API Endpoints

| Endpoint | Method | Description |
|----------|---------|-------------|
| `/` | GET | Home page with login option |
| `/login` | GET | Initiate Google OAuth flow |
| `/authorize` | GET | OAuth callback endpoint |
| `/logout` | GET | Clear session and logout |
| `/hello` | GET | Protected route showing user info |

## 🔄 Dependency Management

Dependencies are actively maintained and regularly updated for security:

- **Flask 3.1.1**: Web framework
- **Authlib 1.6.0**: OAuth client library
- **Gunicorn 23.0.0**: WSGI HTTP server
- **Jinja2 3.1.6**: Template engine
- **Werkzeug 3.1.3**: WSGI utility library

See [requirements.txt](requirements.txt) for complete dependency list.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Security Contributions

- Report security vulnerabilities via GitHub Security Advisories
- Security updates should be tested thoroughly
- Follow responsible disclosure practices

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Authlib](https://authlib.org/) for excellent OAuth implementation
- [Flask](https://flask.palletsprojects.com/) for the lightweight web framework
- [Google OAuth 2.0](https://developers.google.com/identity/protocols/oauth2) for secure authentication

## 📞 Support

If you have any questions or issues:

1. Check existing [GitHub Issues](https://github.com/RobertBergman/authdev/issues)
2. Create a new issue with detailed description
3. For security issues, use GitHub Security Advisories

---

**Note**: This application is for demonstration purposes. For production use, implement additional security measures such as CSRF protection, rate limiting, and comprehensive logging.
