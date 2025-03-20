# Deployment Guide for Wallet Tracker

## Prerequisites

1. A MongoDB Atlas account for the database
2. A cloud platform account (e.g., Heroku, Vercel, or DigitalOcean)
3. Node.js and npm installed locally

## Backend Deployment

1. Create a MongoDB Atlas cluster and get your connection string
2. Set up environment variables in your cloud platform:
   - `MONGODB_URI`: Your MongoDB Atlas connection string
   - `JWT_SECRET`: A secure random string for JWT authentication
   - `FRONTEND_URL`: Your frontend application URL
   - `NODE_ENV`: Set to 'production'

3. Deploy the backend:
   - If using Heroku:
     ```bash
     heroku create your-app-name
     git push heroku main
     ```
   - If using DigitalOcean App Platform:
     - Connect your repository
     - Select the Node.js environment
     - Configure environment variables
     - Deploy

## Frontend Deployment

1. Update the API base URL in `src/config.js` with your deployed backend URL
2. Build the frontend:
   ```bash
   npm run build
   ```
3. Deploy the frontend:
   - If using Vercel:
     - Connect your repository
     - Configure the build settings
     - Deploy
   - If using Netlify:
     - Upload the `dist` folder
     - Configure environment variables

## Post-Deployment

1. Test the application thoroughly
2. Monitor the logs for any errors
3. Set up SSL certificates if not provided by the platform
4. Configure automatic deployments

## Security Considerations

1. Use strong JWT secrets
2. Enable CORS only for your frontend domain
3. Use secure MongoDB connection strings
4. Keep environment variables private
5. Regular security updates

## Troubleshooting

1. Check CORS settings if API calls fail
2. Verify environment variables
3. Check MongoDB connection
4. Review application logs

For additional support, refer to the documentation of your chosen cloud platform.