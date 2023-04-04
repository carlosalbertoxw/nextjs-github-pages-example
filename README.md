# Next.js GitHub Pages Example

## Overview
This is a simple example demonstrating how to deploy a static website using Next.js on GitHub Pages.

## Purpose
The purpose of this project is to provide a clear example of how to publish a Next.js website on GitHub Pages.

## Technologies Used
- Next.js

## Running the Project
- Clone and generate the static website: If you are cloning the main branch of this repository, run the following commands to generate the static website in the 'out' folder:
```
npm install
npm run export
```
## Creating a New Project from Scratch
- Create a new Next.js project: Choose a name for your project (e.g., nextjs-github-pages-example) and create the project using the following command:
```
npx create-next-app nextjs-github-pages-example
```
- Open the project folder: Use a text editor or the console to navigate to the application folder.
- Configure static export: Edit the next.config.js file to configure static export. You can refer to this example:
```
/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
  swcMinify: true,
  // Use the prefix for GitHub Pages
  basePath: '/nextjs-github-pages-example',
  assetPrefix: './',
  // Enable static export
  trailingSlash: true,
  images: {
    unoptimized: true
  },
}

module.exports = nextConfig
```
- Add export script: In the package.json file, add the following export script:
```
"scripts": {
  ...
  "export": "next build && next export"
}
```
- Test static export: Run the following command:
```
npm run export
```
- Create a GitHub repository: Create a new GitHub repository named nextjs-github-pages-example (or any other name you prefer).
- Connect the repository: Run the following command to connect your local project to the GitHub repository:
```
git remote add origin https://github.com/yourusername/nextjs-github-pages-example.git
```
- Commit and push changes: Commit the modified files and push them to the main branch on GitHub:
```
git add .
git commit -m 'Initial commit'
git push origin main
```
- Clone the repository to another location and navigate to it.
- Create and switch to 'gh-pages' branch: Create a new branch called gh-pages and switch to it:
```
git checkout --orphan gh-pages
```
- Prepare for deployment: Delete the entire contents of the gh-pages branch and move the generated files from the 'out' folder to the root of the branch.
```
git rm -rf .
```
- Disable Jekyll: Create a .nojekyll file in the root of the gh-pages branch. This file tells GitHub Pages not to use Jekyll, preventing files in the _next folder from being deleted.
```
touch .nojekyll
```
- Commit and push changes: Commit the modified files and push them to the gh-pages branch on GitHub:
```
git add .
git commit -m 'Deploy to GitHub Pages'
git push origin gh-pages
```
- Access the website: Wait a few minutes, then go to the settings page of your GitHub repository. In the 'Pages' section, you should see the URL to access your website.
