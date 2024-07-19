# Full-stack MERN Real Estate App: Build a Modern Marketplace

![MERN Stack](https://img.shields.io/badge/MERN_Stack-blue.svg)
![JWT Authentication](https://img.shields.io/badge/JWT_Authentication-red.svg)
![Firebase](https://img.shields.io/badge/Firebase-yellow.svg)
![React Redux](https://img.shields.io/badge/React_Redux-green.svg)
![MIT License](https://img.shields.io/badge/License-MIT-brightgreen.svg)

## Objective
The goal of this course is to guide you through building a cutting-edge real estate marketplace using the MERN stack. You'll learn to implement advanced features such as JWT, Firebase, and Google OAuth for authentication, along with sophisticated CRUD operations and deployment strategies.

## Developer Information
Name: Yuvraj Singh Chowdhary  
LinkedIn: [Connect with me](https://www.linkedin.com/in/yuvraj-singh-chowdhary/)  
GitHub Repo: [Full-stack MERN Real Estate App](https://github.com/sahandghavidel/mern-real-estate-app)  
Reddit: [Connect on Reddit](https://www.reddit.com/user/SuccessfulStrain9533/)

## Overview
This project is a comprehensive course designed to teach you how to build a full-featured real estate marketplace using the MERN stack. You'll learn to create advanced authentication mechanisms, implement real-world CRUD operations, and deploy the app using the 'render' platform.

## Key Features
- **Advanced Authentication**: Implement JWT, Firebase, and Google OAuth for secure and seamless user access.
- **Real-world CRUD Operations**: Create, read, update, and delete property listings using MongoDB.
- **User-friendly Features**: Enhance the user experience with image uploads, property listing management, and more.
- **Advanced Search Functionality**: Implement cutting-edge search features to help users find what they're looking for.
- **Deployment Made Easy**: Learn to deploy your MERN real estate app for free using the 'render' platform.

## Installation
To install the necessary libraries and start the project, follow these steps:

### Clone the Repository
```sh
git clone https://github.com/sahandghavidel/mern-real-estate-app.git
cd mern-real-estate-app
```

### Install Dependencies
#### Backend
```sh
cd backend
npm install
```

#### Frontend
```sh
cd frontend
npm install
```

### Environment Variables
Create a `.env` file in the `backend` directory and add the following:
```sh
MONGO_URI=<Your MongoDB URI>
JWT_SECRET=<Your JWT Secret>
FIREBASE_API_KEY=<Your Firebase API Key>
GOOGLE_CLIENT_ID=<Your Google OAuth Client ID>
```

## Running the Application
### Backend
```sh
cd backend
npm run dev
```

### Frontend
```sh
cd frontend
npm start
```

## Prerequisites
A basic understanding of JavaScript and React is recommended. This course is ideal for aspiring full-stack developers, React enthusiasts, or anyone eager to expand their web development toolkit.

## What You'll Learn
- Implementing advanced authentication using JWT, Firebase, and Google OAuth.
- Building robust CRUD operations for property listings.
- Enhancing user experience with features like image uploads and property management.
- Developing advanced search functionality.
- Deploying the application using the 'render' platform.

## Example Code Snippets
### Backend: JWT Authentication Middleware
```javascript
const jwt = require('jsonwebtoken');

const auth = (req, res, next) => {
  const token = req.header('x-auth-token');
  if (!token) return res.status(401).json({ msg: 'No token, authorization denied' });

  try {
    const decoded = jwt.verify(token, process.env.JWT_SECRET);
    req.user = decoded;
    next();
  } catch (e) {
    res.status(400).json({ msg: 'Token is not valid' });
  }
};

module.exports = auth;
```

### Frontend: Redux Action for Property Listing
```javascript
import axios from 'axios';
import { GET_PROPERTIES, PROPERTY_ERROR } from './types';

export const getProperties = () => async dispatch => {
  try {
    const res = await axios.get('/api/properties');
    dispatch({
      type: GET_PROPERTIES,
      payload: res.data,
    });
  } catch (err) {
    dispatch({
      type: PROPERTY_ERROR,
      payload: { msg: err.response.statusText, status: err.response.status },
    });
  }
};
```

## Conclusion
Join us on this immersive journey to master the MERN stack, advanced authentication, Firebase integration, Google OAuth, and much more. By the end of this course, you'll have a fully functional real estate application to showcase and a wealth of skills to boost your web development career.

🎓 Let's embark on this exciting learning adventure together! Don't forget to like, subscribe, and hit the notification bell to stay updated with our latest tutorials and courses. 🚀

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
