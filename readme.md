# Strapi BlogPost Setup

## Overview
This project demonstrates setting up **Strapi CMS** locally and creating a **BlogPost** content type with custom fields.

## Prerequisites
- Node.js v18 or higher
- npm or yarn
- Git
- GitHub account

## Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/Mohdkaif-78/scrapi-project.git
cd scrapi-project
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Run Strapi Locally
```bash
npm run develop
```

The admin panel will automatically open at `http://localhost:1337/admin`

If it doesn't open, visit it manually in your browser.

### 4. Project Structure
```
my-strapi-project/
├── src/
│   ├── api/              # API endpoints and content types
│   ├── admin/            # Admin customizations
│   └── index.js          # Entry point
├── config/               # Configuration files
├── public/               # Static files
├── .env                  # Environment variables
└── package.json          # Dependencies
```

## BlogPost Content Type

### Fields Created
The **BlogPost** collection type includes the following fields:

| Field Name | Type | Required | Description |
|---|---|---|---|
| title | Text | ✓ | Blog post title |
| slug | Text | ✓ | URL-friendly identifier |
| excerpt | Text | | Short summary of the post |
| content | Rich Text | ✓ | Main blog content |
| author | Text | | Author name |
| category | Text | | Blog category/topic |
| tags | Text | | Comma-separated tags |
| publishedAt | Date | | Publication date |
| updatedAt | Date | | Last modification date |
| featuredImage | Media | | Cover image for the post |
| readTime | Number | | Estimated reading time (minutes) |

### Sample Data
Sample blog posts have been created to demonstrate the content type structure.

### Accessing the API
Once Strapi is running, access your blog posts via:

```
GET http://localhost:1337/api/blog-posts
```

Response example:
```json
{
  "data": [
    {
      "id": 1,
      "attributes": {
        "title": "Getting Started with Strapi",
        "slug": "getting-started-with-strapi",
        "excerpt": "Learn how to set up Strapi CMS",
        "content": "...",
        "author": "John Doe",
        "category": "Tutorial",
        "publishedAt": "2026-02-02T00:00:00.000Z"
      }
    }
  ],
  "meta": {
    "pagination": {
      "page": 1,
      "pageSize": 25,
      "total": 1
    }
  }
}
```

## Available Commands

### Development
```bash
npm run develop
# Starts Strapi in watch mode (auto-restart on file changes)
```

### Production Build
```bash
npm run build
# Builds the admin panel and prepares for deployment
```

### Start (without watch mode)
```bash
npm run start
# Runs Strapi without automatic reload
```

### Database Seeding
```bash
npm run seed:example
# Populates database with example data
```

## Features Completed

✅ Strapi installed and configured locally  
✅ BlogPost content type created with 11 custom fields  
✅ Sample blog post data added  
✅ Project pushed to GitHub  
✅ API endpoints functional  
✅ Documentation created  

## Database

By default, this project uses **SQLite** for local development, which creates a `data.db` file.

### Switch to PostgreSQL (Optional)
To use PostgreSQL instead:

1. Update `.env` file with your PostgreSQL credentials
2. Reinstall dependencies: `npm install`
3. Restart Strapi

## Next Steps

- **Create More Content Types**: Add Author, Category, or Comment types
- **Add Plugins**: Extend functionality with Strapi plugins
- **Create Frontend**: Connect a React/Vue/Next.js frontend
- **Deploy**: Deploy to Strapi Cloud, Heroku, or your own server
- **Customize Admin**: Customize the admin panel UI

## Deployment

To deploy this Strapi project:

```bash
npm run build
npm run deploy
```

Or use Strapi Cloud for managed hosting.

## Troubleshooting

### Port 1337 already in use
```bash
PORT=3000 npm run develop
```

### Clear database
```bash
rm data.db
npm run develop
```

### Reset admin user
```bash
npm run strapi admin:create-user
```

## Resources

- **Strapi Documentation**: https://docs.strapi.io
- **Strapi API Reference**: https://docs.strapi.io/api
- **Community Support**: https://strapi.io/community

## Video Documentation

A comprehensive Loom video walkthrough is available showing:
- Project setup and installation
- Admin panel navigation
- BlogPost content type creation
- Sample data addition
- API endpoint testing
- GitHub repository structure

[Loom Video Link - To be added after recording]

## Author
Mohd Kaif

## License
MIT

---

**Last Updated**: February 2, 2026
