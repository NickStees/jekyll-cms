# About

This Jekyll Demo site is meant to showcase how a typical site can be created with Jekyll. It features a mix of developer friendly features such as galleries built from the file system, along with Client friendly features using Netlify CMS for basic editing that a client can login and update content.

**Live Demo** [https://jekyll-netlifycms.netlify.com/](https://jekyll-netlifycms.netlify.com/)

# Features at a Glance

- **Gulp.js** modern build allows for SASS/SCSS and JS/Babel processing.
- Fast **live reloading** local development with Browser Sync
- Homepage markup freedom that lets developers go wild!
- Use partials/includes for re-useable content such as headers, footer and calls to action (\_include/call-to-action.html) that is easy to maintain.
- Dynamic page content from .CSV files that are easy for clients to manage using Excel.
- Image gallery built from images in the file system. Developers simply add an image to a folder and the gallery is updated.
- **Netlify CMS integration** allows editing pages as well as creating News.
- Contact form uses Netlify Forms to receive submissions which can be piped to other services
- Uses Jekyll `\_data` to output content like variables across multiple pages, making content easy to maintain.

# Getting started

This project requires first that [Jekyll be installed](https://jekyllrb.com/docs/installation/) along with the [Node.js](https://nodejs.org/en/download/). If its your first time run `gem install jekyll bundler` to install both Jekyll and Bundler locally.

After cloning the project

- run `bundle install` to install gem dependencies
- run `npm install` to install npm modules
- run `gulp` to start live development
  <!-- Markdown snippet -->
  [![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/NickStees/jekyll-cms)

## SCSS and JS

The theme and JS files are located in the `/assets/_scss` and `/assets/js` folder. Gulp will process these files and build the sites CSS and JS files.

## Netlify CMS Integration

The Netlify CMS edits the YAML files in `_data/*` along with the `_posts` folder for the sites News. By allowing the Netlify CMS to edit mainly the `_data` files, you are free to use advanced markup on the rest of the site pages (more than markdown provides), and to pull in Netlify CMS content you simply tell Jekyll to output {{ site.data.home.title }} to access the Netlify CMS managed YAMl data.

Each _.html page will need a corresponding _.yml file that the Netlify CMS will edit.

You can have Netlify CMS save content as Markdown, and have Jekyll process it into html using the markdownify Liquid filter ex. {{ site.data.home.intro-body | markdownify }}

This site also uses some 'Global' yaml files that can be edited which are like site wide settings that multiple pages use such as a business address or phone number. So only one Global file needs updated, and the rest of the site is updated.

News can be created by the Netlify CMS similar to a blog example, which creates markdown files in the `\_posts` directory.

## Directories Explained

This is a quick overview of this projects directories, and how they are used.

- **\_data** Jekyll [Data Files](https://jekyllrb.com/docs/datafiles/) which is also what Netlify CMS will mainly edit to update site pages.
- **\_includes** Reuseable components/partials that are used across multiple pages
- **\_layouts** Default Jekyll layouts
- **\_posts** Defautl Jekyll [Posts/News](https://jekyllrb.com/docs/posts/) articles configued to be edited by Netlify CMS
- **admin** Netlify CMS configuration
- **api** An example of making a static JSON file an API endpoint
- **assets** SCSS/JS files mainly related to the Theme, processed by Gulp.js
- **docs** A folder used to build dynamic pages (Documents) based on the files in these folders, easy for a Developer to maintain.
- **img** Static images as well as the Gallery Page is dynamically created from the contents of the `img/gallery` folder
- **uploads** The location Netlify CMS editor uploads files.
- **\_\_\_.html** The site pages are mainly created from these .html files which pull data from the `_data` directory that can be maintained from the Netlify CMS
