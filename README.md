# 🌍 Wanderlust

A full-stack web application for browsing and managing travel listings. Wanderlust allows users to explore various vacation destinations, view detailed property information, and manage listings through a clean and intuitive interface.

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![EJS](https://img.shields.io/badge/EJS-B4CA65?style=for-the-badge&logo=ejs&logoColor=black)

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Installation](#-installation)
- [Usage](#-usage)
- [API Routes](#-api-routes)
- [Database Schema](#-database-schema)
- [Error Handling](#-error-handling)
- [Contributing](#-contributing)
- [License](#-license)

## ✨ Features

- **Browse Listings**: View a comprehensive collection of travel destinations and vacation properties
- **Detailed Views**: Access detailed information about each listing including images, descriptions, pricing, and location
- **Create Listings**: Add new travel destinations with complete details
- **Edit Listings**: Update existing listing information
- **Delete Listings**: Remove listings from the database
- **Responsive Design**: Mobile-friendly interface with modern UI/UX
- **Error Handling**: Robust error handling with custom error pages
- **Data Validation**: Server-side validation for all listing operations

## 🛠️ Tech Stack

### Backend
- **Node.js** - JavaScript runtime environment
- **Express.js** (v5.1.0) - Web application framework
- **MongoDB** - NoSQL database for data persistence
- **Mongoose** (v8.20.0) - MongoDB object modeling tool

### Frontend
- **EJS** (v3.1.10) - Embedded JavaScript templating
- **EJS-Mate** (v4.0.0) - Layout and partial support for EJS
- **CSS** - Custom styling

### Utilities
- **Method-Override** (v3.0.0) - HTTP verb support (PUT, DELETE) in forms

## 📁 Project Structure

```
MajorProject/
├── models/
│   └── listing.js          # Mongoose schema for listings
├── views/
│   ├── listings/
│   │   ├── index.ejs       # All listings page
│   │   ├── show.ejs        # Individual listing details
│   │   ├── new.ejs         # Create new listing form
│   │   └── edit.ejs        # Edit listing form
│   ├── includes/
│   │   ├── navbar.ejs      # Navigation bar component
│   │   └── footer.ejs      # Footer component
│   ├── layouts/
│   │   └── boilerplate.ejs # Main layout template
│   └── error.ejs           # Error page template
├── public/
│   ├── css/
│   │   └── style.css       # Application styles
│   └── js/                 # Client-side JavaScript
├── utils/
│   ├── wrapAsync.js        # Async error wrapper
│   └── ExpressError.js     # Custom error class
├── init/
│   ├── data.js             # Sample listing data
│   └── index.js            # Database initialization script
├── app.js                  # Main application file
└── package.json            # Project dependencies
```

## 🚀 Installation

### Prerequisites

- Node.js (v14 or higher)
- MongoDB (v4.4 or higher)
- npm or yarn package manager

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/AchalRaj0709/wanderlust.git
   cd MajorProject
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start MongoDB**
   ```bash
   # Make sure MongoDB is running on localhost:27017
   mongod
   ```

4. **Initialize the database (Optional)**
   ```bash
   # Populate the database with sample data
   node init/index.js
   ```

5. **Start the application**
   ```bash
   node app.js
   ```

6. **Access the application**
   ```
   Open your browser and navigate to: http://localhost:8080/listings
   ```

## 💻 Usage

### Viewing Listings
Navigate to `/listings` to see all available travel destinations.

### Creating a New Listing
1. Click on "Create New Listing" or navigate to `/listings/new`
2. Fill in the required information:
   - Title
   - Description
   - Image URL
   - Price
   - Location
   - Country
3. Submit the form to add the listing

### Viewing Listing Details
Click on any listing card to view detailed information about that property.

### Editing a Listing
1. Navigate to a listing's detail page
2. Click "Edit" button
3. Update the information
4. Submit to save changes

### Deleting a Listing
1. Navigate to a listing's detail page
2. Click "Delete" button
3. Confirm deletion

## 🔌 API Routes

| Method | Route | Description |
|--------|-------|-------------|
| GET | `/` | Root route (welcome message) |
| GET | `/listings` | Display all listings |
| GET | `/listings/new` | Show form to create new listing |
| POST | `/listings` | Create a new listing |
| GET | `/listings/:id` | Show specific listing details |
| GET | `/listings/:id/edit` | Show form to edit listing |
| PUT | `/listings/:id` | Update a specific listing |
| DELETE | `/listings/:id` | Delete a specific listing |

## 🗄️ Database Schema

### Listing Model

```javascript
{
  title: {
    type: String,
    required: true
  },
  description: String,
  image: {
    filename: {
      type: String,
      default: "listingimage"
    },
    url: {
      type: String,
      default: "default-image-url"
    }
  },
  price: Number,
  location: String,
  country: String
}
```

## ⚠️ Error Handling

The application implements comprehensive error handling:

- **Custom Error Class**: `ExpressError` for structured error messages
- **Async Wrapper**: `wrapAsync` utility to catch async errors
- **404 Handler**: Catches all undefined routes
- **Global Error Handler**: Centralized error handling middleware
- **User-Friendly Error Pages**: Custom error templates with status codes and messages

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the ISC License.

## 👨‍💻 Author

**AchalRaj0709**

## 🙏 Acknowledgments

- Sample listing data includes destinations from around the world
- Images sourced from Unsplash
- Built as a learning project to demonstrate full-stack web development skills

---

**Note**: This application is configured to run with MongoDB on `localhost:27017`. Make sure MongoDB is running before starting the application. For production deployment, update the database connection string with appropriate credentials and hosting details.
