# CausalFunnel - Shopify Survey App

A dynamic Shopify application that injects survey forms into cart pages and provides comprehensive analytics through an admin dashboard.

## Live Demo & Deployment

🚀 **Deployed Application:** [https://shopify-assess.vercel.app/](https://shopify-assess.vercel.app/)

📹 **Demo Video:** [Watch the full demonstration](https://www.loom.com/share/2f5230b7da814301882801db5b8f60e0?sid=7f3b28bb-8de5-4905-922e-21f9c3d0624a)

The demo video showcases:
- Complete app installation process
- Survey form functionality on cart page
- Admin dashboard features
- Data analysis capabilities

## Project Overview

This application enables Shopify merchants to:
- Collect customer feedback through dynamic survey forms on the cart page
- Store and analyze survey responses
- View detailed analytics through an interactive dashboard
- Make data-driven decisions based on customer feedback

## Tech Stack

### Frontend
- Next.js 15.2.0
- React 19.0.0
- Shopify Polaris Design System
- Chart.js/Recharts for data visualization
- TailwindCSS for styling

### Backend
- Next.js API Routes
- Prisma ORM
- PostgreSQL for data storage
- Shopify App Bridge for integration

## Prerequisites

Before you begin, ensure you have:
- Node.js (v18 or higher)
- npm or yarn package manager
- A Shopify Partners account
- A development store in Shopify
- PostgreSQL database (we're using Supabase Postgres)

## Development Environment Setup

1. Clone the repository:
```bash
git clone <repository-url>
cd shopify-assess
```

2. Install dependencies:
```bash
npm install
# or
yarn install
```

3. Set up environment variables:
Create a `.env.local` file in the root directory with the following variables:
```env
# Shopify App Credentials
SHOPIFY_API_KEY="your_api_key"
SHOPIFY_API_SECRET="your_api_secret"
SHOPIFY_SCOPES="read_customers,write_customers,read_orders,read_products,read_content,write_content,write_script_tags"
SHOPIFY_APP_URL="your_app_url"
SHOPIFY_AUTH_CALLBACK_URL="your_app_url/api/auth/callback"

# Database
DATABASE_URL="your_prisma_database_url"
DIRECT_URL="your_postgres_direct_url"

# App Settings
NODE_ENV=development
HOST="your_app_url"
```

4. Set up the database:
```bash
npx prisma generate
npx prisma db push
```

5. Start the development server:
```bash
npm run dev
# or
yarn dev
```

## Installing the App on a Test Store

1. Log in to your Shopify Partners account

2. Create a new app in the Partners Dashboard:
   - Go to Apps > Create App
   - Set the App URL to `https://your-dev-url.com`
   - Set the Allowed redirection URL(s) to:
     - `https://your-dev-url.com/api/auth/callback`
     - `https://your-dev-url.com/api/auth/tokens`

3. In your development store:
   - Go to Apps > Add app
   - Search for your app name
   - Click "Install app"
   - Follow the OAuth process

## Local Testing

1. Start the development server:
```bash
npm run dev
```

2. Use ngrok or a similar tool to create a tunnel to your local server:
```bash
ngrok http 3000
```

3. Update your app URLs in the Shopify Partners Dashboard with the ngrok URL

4. Test the following features:
   - Survey form injection on the cart page
   - Survey submission and data storage
   - Admin dashboard functionality
   - Data visualization and analytics

## Project Structure

```
shopify-assess/
├── app/                    # Next.js app directory
│   ├── components/         # React components
│   ├── api/               # API routes
│   └── pages/             # App pages
├── prisma/                # Database schema and migrations
├── public/                # Static assets
└── styles/                # Global styles
```

## Features

1. Dynamic Survey Form
   - Automatically injects into cart pages
   - Responsive design
   - Multiple question types support
   - Real-time validation

2. Admin Dashboard
   - Summary statistics
   - Interactive charts and graphs
   - Response filtering and search
   - Export capabilities

3. Data Analysis
   - Response trends
   - Customer segmentation
   - Product correlations
   - Custom report generation

## Troubleshooting

Common issues and solutions:

1. **App installation fails**
   - Verify your API credentials
   - Check redirect URLs
   - Ensure proper app scopes

2. **Survey form not appearing**
   - Clear browser cache
   - Check script injection
   - Verify store permissions

3. **Database connection issues**
   - Verify Prisma connection string
   - Check PostgreSQL database access
   - Ensure proper network connectivity to Supabase
   - Verify DATABASE_URL and DIRECT_URL are properly set

## Support

For support, please:
1. Check the existing issues in the repository
2. Create a new issue with detailed information about your problem
3. Include relevant error messages and screenshots

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
