# KN BOOK - Book Discovery Platform

A modern web application for discovering and exploring millions of books using Google Books API, built with Laravel and Vue.js.

## Preview

<table align="center">
  <tr>
    <td align="center">
      <img src="public/images/homepage.png" width="300">
      <p>🏠 Home Page</p>
    </td>
    <td align="center">
      <img src="public/images/details.png" width="300">
      <p>📖 Book Details Page</p>
    </td>
  </tr>
  <tr>
    <td colspan="2" align="center">
      <img src="public/images/about.png" width="300">
      <p>ℹ️ About Page</p>
    </td>
  </tr>
</table>

## Features

- 🔍 **Advanced Book Search** - Search millions of books with powerful filters (subject, print type, order)
- 📚 **Detailed Book Information** - View comprehensive details including descriptions, ratings, publisher info, and preview links
- 👤 **User Authentication** - Secure registration and login system with Laravel Fortify
- 📱 **Responsive Design** - Works seamlessly on desktop, tablet, and mobile devices
- 🎨 **Modern UI** - Clean book-themed interface with custom Tailwind CSS design system
- 📧 **Contact Form** - Get in touch with inquiries and feedback

## Tech Stack

- **Backend**: Laravel 11, PHP 8.2+
- **Frontend**: Vue 3 (Composition API), TypeScript, Inertia.js
- **Styling**: Tailwind CSS v4 with custom book theme
- **UI Components**: shadcn-vue
- **API**: Google Books API v1
- **Database**: SQLite (development) / MySQL (production ready)
- **Authentication**: Laravel Fortify
- **Testing**: Pest PHP

## Installation

### Prerequisites

- PHP 8.2 or higher
- Composer
- Node.js 18+ and npm
- SQLite or MySQL database

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd KNBOOK
   ```

2. **Install dependencies**
   ```bash
   composer install
   npm install
   ```

3. **Configure environment**
   ```bash
   copy .env.example .env
   php artisan key:generate
   ```

4. **Set up database**
   
   For SQLite (default):
   ```bash
   # Create empty database file
   type nul > database\database.sqlite
   ```
   
   For MySQL, update `.env`:
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=laravel_app
   DB_USERNAME=root
   DB_PASSWORD=
   ```

5. **Run migrations**
   ```bash
   php artisan migrate
   ```

6. **(Optional) Configure Google Books API**
   
   Get an API key from [Google Cloud Console](https://console.cloud.google.com/)
   
   Add to `.env`:
   ```env
   GOOGLE_BOOKS_API_KEY=your_api_key_here
   ```

7. **Build frontend assets**
   ```bash
   npm run build
   ```

8. **Start development servers**
   ```bash
   # Terminal 1 - Laravel backend
   php artisan serve
   
   # Terminal 2 - Vite frontend
   npm run dev
   ```

9. **Visit the application**
   
   Open `http://localhost:8000` in your browser

## Usage

### For Users

1. **Browse Books** - Visit the Books page to explore the collection
2. **Search & Filter** - Use the search bar and filters to find specific books
3. **View Details** - Click any book to see detailed information
4. **Register/Login** - Create an account to access personalized features
5. **Contact** - Use the contact form for inquiries

### For Developers

Run tests:
```bash
php artisan test
```

Watch mode for frontend development:
```bash
npm run dev
```

Build for production:
```bash
npm run build
```

## Project Structure

```
laravel_app/
├── app/
│   ├── Http/
│   │   └── Controllers/
│   │       └── BookController.php      # Book search and display logic
│   └── Models/
│       └── User.php                    # User model with authentication
├── config/
│   ├── books.php                       # Google Books API configuration
│   └── fortify.php                     # Authentication settings
├── database/
│   ├── migrations/                     # Database schema
│   └── factories/                      # Test data factories
├── public/
│   ├── images/
│   │   └── dev.jpg                    # Images
│   └── build/                         # Compiled assets
├── resources/
│   ├── js/
│   │   ├── pages/
│   │   │   ├── Books.vue              # Main book listing page
│   │   │   ├── Show.vue               # Individual book details
│   │   │   ├── Home.vue               # Landing page
│   │   │   ├── Services.vue           # Services showcase
│   │   │   ├── About.vue              # About page
│   │   │   ├── Contact.vue            # Contact form
│   │   │   └── auth/                  # Login & registration pages
│   │   ├── layouts/
│   │   │   ├── GuestLayout.vue        # Main layout with navigation
│   │   │   └── AppLayout.vue          # Authenticated user layout
│   │   ├── components/                # Reusable Vue components
│   │   ├── types/
│   │   │   └── book.d.ts              # TypeScript type definitions
│   │   └── constants/
│   │       └── bookFilters.ts         # Filter options constants
│   └── css/
│       └── app.css                    # Tailwind configuration & custom styles
├── routes/
│   └── web.php                        # Application routes
└── tests/
    └── Feature/
        └── BookSearchTest.php         # API integration tests
```

## API Integration

The application integrates with Google Books API to fetch book data:

- **Base URL**: `https://www.googleapis.com/books/v1`
- **Configuration**: See `config/books.php`
- **Endpoints Used**:
  - `/volumes` - Search and list books
  - `/volumes/{id}` - Get specific book details

## Design System

### Color Palette

Custom book-themed colors defined in `resources/css/app.css`:

| Color | Hex | Usage |
|-------|-----|-------|
| book-primary | `#8b5e3c` | Primary brown - buttons, links |
| book-secondary | `#6e472b` | Darker brown - hover states |
| book-accent | `#d4a574` | Light brown - accents |
| book-bg | `#f8f4f0` | Cream - page background |
| book-surface | `#fefcfa` | Off-white - cards, header |
| book-border | `#e8ddd0` | Subtle borders |
| book-text-primary | `#3f2f23` | Dark brown - main text |
| book-text-secondary | `#6b5c52` | Medium brown - secondary text |

### Typography

- **Headings**: System font stack with bold weights
- **Body**: Clean, readable sans-serif
- **Logo**: "Bebas Neue" (uppercase display font)

## Features Breakdown

### Book Search
- Real-time search with 500ms debounce
- Advanced filters: Subject, Print Type, Order By
- Pagination support
- Loading states and error handling

### Authentication
- User registration with validation
- Secure login system
- Password hashing with bcrypt
- Session-based authentication
- Remember me functionality
- Protected routes with middleware

### Responsive Design
- Mobile-first approach
- Hamburger menu for mobile navigation
- Adaptive grid layouts
- Touch-friendly interactive elements

### User Experience
- Smooth transitions and hover effects
- Loading indicators
- Empty states
- Error messages
- Success notifications

## Testing

The application includes feature tests for core functionality:

```bash
# Run all tests
php artisan test

# Run specific test file
php artisan test --filter=BookSearchTest

# Run with coverage
php artisan test --coverage
```

## Configuration Files

- `.env` - Environment variables (database, API keys, app settings)
- `config/books.php` - Google Books API configuration
- `config/fortify.php` - Authentication features and settings
- `tailwind.config.js` - Tailwind CSS customization
- `vite.config.ts` - Frontend build configuration

## Security

- CSRF protection on all forms
- Password hashing with bcrypt
- SQL injection protection via Eloquent ORM
- XSS protection in Vue templates
- Environment variables for sensitive data
- Secure session management

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Deployment

For production deployment:

1. Set `APP_ENV=production` in `.env`
2. Set `APP_DEBUG=false`
3. Configure production database
4. Run `php artisan config:cache`
5. Run `php artisan route:cache`
6. Run `npm run build`
7. Set proper file permissions
8. Configure web server (Apache/Nginx)

## Known Limitations

- Google Books API has rate limits (1000 requests/day without API key)
- Some books may have limited preview or no cover images
- Search results limited to what's available in Google Books

## Future Enhancements

- [ ] User book collections/favorites
- [ ] Reading lists and bookmarks
- [ ] Book reviews and ratings
- [ ] Social sharing features
- [ ] Email notifications
- [ ] Advanced search filters
- [ ] Multi-language support
