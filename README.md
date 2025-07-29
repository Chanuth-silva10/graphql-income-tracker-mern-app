# 💰 GraphQL Income Tracker MERN App

A full-stack financial management application built with the MERN stack and Apollo GraphQL for tracking income, expenses, and investments. Features real-time data visualization, secure authentication, and comprehensive transaction management.


## 🌟 Features

### Core Functionality
- 📊 **Transaction Management**: Create, read, update, and delete financial transactions
- 💳 **Multiple Payment Types**: Support for cash and card payments
- 📈 **Category-based Tracking**: Organize transactions by savings, expenses, and investments
- 📍 **Location Tracking**: Optional location data for transactions
- 📅 **Date Management**: Track transactions with precise date information

### Technical Features
- 🔐 **Secure Authentication**: Passport.js with session-based authentication
- 🚀 **Real-time Data**: Apollo GraphQL for efficient data fetching and caching
- 📱 **Responsive Design**: Mobile-first design with Tailwind CSS
- 🎨 **Modern UI**: Beautiful interface with Framer Motion animations
- 📊 **Data Visualization**: Charts and statistics using Chart.js
- � **Global State Management**: Apollo Client for state management
- 🛡️ **Error Handling**: Comprehensive error handling on both client and server
- 🎭 **Profile Pictures**: Dynamic avatar generation based on gender

## 🛠️ Tech Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **Apollo Server** - GraphQL server
- **MongoDB** - Database
- **Mongoose** - ODM for MongoDB
- **Passport.js** - Authentication middleware
- **bcryptjs** - Password hashing
- **express-session** - Session management

### Frontend
- **React 18** - UI library
- **Apollo Client** - GraphQL client and state management
- **React Router** - Client-side routing
- **Tailwind CSS** - Utility-first CSS framework
- **Chart.js & React-Chartjs-2** - Data visualization
- **Framer Motion** - Animation library
- **React Hot Toast** - Toast notifications
- **React Icons** - Icon library

## 🚀 Quick Start

### Prerequisites
- Node.js (v18 or higher)
- MongoDB (local or cloud instance)
- npm or yarn package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/graphql-income-tracker-mern-app.git
   cd graphql-income-tracker-mern-app
   ```

2. **Install dependencies**
   ```bash
   # Install backend dependencies
   npm install
   
   # Install frontend dependencies
   npm install --prefix frontend
   ```

3. **Environment Configuration**
   
   Create a `.env` file in the root directory:
   ```env
   MONGO_URI=mongodb://localhost:27017/income-tracker
   # Or use MongoDB Atlas: mongodb+srv://username:password@cluster.mongodb.net/income-tracker
   
   SESSION_SECRET=your-super-secret-session-key-here
   NODE_ENV=development
   ```

4. **Start the application**
   
   **Development Mode:**
   ```bash
   # Start backend server (runs on http://localhost:4000)
   npm run dev
   
   # In a new terminal, start frontend (runs on http://localhost:3000)
   cd frontend
   npm run dev
   ```
   
   **Production Mode:**
   ```bash
   # Build and start the application
   npm run build
   npm start
   ```

## 📁 Project Structure

```
graphql-income-tracker-mern-app/
├── backend/
│   ├── db/
│   │   └── connectDB.js          # Database connection
│   ├── models/
│   │   ├── user.model.js         # User schema
│   │   └── transaction.model.js  # Transaction schema
│   ├── resolvers/
│   │   ├── index.js              # Combined resolvers
│   │   ├── user.resolver.js      # User GraphQL resolvers
│   │   └── transaction.resolver.js # Transaction GraphQL resolvers
│   ├── typeDefs/
│   │   ├── index.js              # Combined type definitions
│   │   ├── user.typeDef.js       # User GraphQL schema
│   │   └── transaction.typeDef.js # Transaction GraphQL schema
│   ├── passport/
│   │   └── passport.config.js    # Passport authentication config
│   ├── dummyData/
│   │   └── data.js               # Sample data for testing
│   └── index.js                  # Server entry point
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── ui/               # UI components
│   │   │   ├── skeletons/        # Loading skeletons
│   │   │   └── *.jsx             # Feature components
│   │   ├── pages/
│   │   │   └── *.jsx             # Page components
│   │   ├── graphql/
│   │   │   ├── queries/          # GraphQL queries
│   │   │   └── mutations/        # GraphQL mutations
│   │   └── utils/                # Utility functions
│   └── public/                   # Static assets
└── package.json                  # Root package.json
```

## 🔧 Available Scripts

### Root Directory
- `npm run dev` - Start backend in development mode with nodemon
- `npm run build` - Build the entire application
- `npm start` - Start the application in production mode

### Frontend Directory
- `npm run dev` - Start frontend development server
- `npm run build` - Build frontend for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

## �️ Database Schema

### User Model
```javascript
{
  username: String (unique, required)
  name: String (required)
  password: String (required, hashed)
  profilePicture: String (auto-generated)
  gender: String (male/female)
  createdAt: Date
  updatedAt: Date
}
```

### Transaction Model
```javascript
{
  userId: ObjectId (ref: User, required)
  description: String (required)
  paymentType: String (cash/card, required)
  category: String (saving/expense/investment, required)
  amount: Number (required)
  location: String (optional)
  date: Date (required)
}
```

## 🔌 GraphQL API

### Queries
- `authUser` - Get authenticated user
- `user(userId: ID!)` - Get user by ID
- `transactions` - Get all user transactions
- `transaction(transactionId: ID!)` - Get transaction by ID
- `categoryStatistics` - Get spending statistics by category

### Mutations
- `signUp(input: SignUpInput!)` - Register new user
- `login(input: LoginInput!)` - Authenticate user
- `logout` - End user session
- `createTransaction(input: CreateTransactionInput!)` - Create new transaction
- `updateTransaction(input: UpdateTransactionInput!)` - Update existing transaction
- `deleteTransaction(transactionId: ID!)` - Delete transaction

## 🎨 UI Features

- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile
- **Dark/Light Theme**: Tailwind CSS with theme support
- **Interactive Charts**: Visual representation of spending patterns
- **Real-time Updates**: Apollo Client cache updates
- **Loading States**: Skeleton components for better UX
- **Toast Notifications**: User feedback for actions
- **Form Validation**: Client-side validation with error messages

## 🚀 Deployment

### Heroku Deployment
1. Create a Heroku app
2. Set environment variables in Heroku dashboard
3. Deploy using Git or GitHub integration

### Railway Deployment
1. Connect your GitHub repository
2. Set environment variables
3. Deploy automatically on push

### Environment Variables for Production
```env
MONGO_URI=your-mongodb-atlas-connection-string
SESSION_SECRET=your-production-session-secret
NODE_ENV=production
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request


## 🐛 Known Issues

- Session persistence across browser restarts (by design)
- Chart.js responsiveness on very small screens

---

**Happy Tracking! 💰**
