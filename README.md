# kxn-kodkvall-directus  
The purpose of this project is to get access to a simple web page REST-api, which can run locally on your computer.  

The base setup includes the following content types: home page, about page, pages and posts (with categories). The project comes with template data in database.

## Start project
npm install  
npx directus start  

## Authenticate
URL: http://127.0.0.1:8055/  
Username: admin@admin.com  
Password: admin  

When you are logged in, you can add, update or delete any content.  

You also have full access to change the behavior of this Directus project. But if you do that, other information in this README may become obsolete.  

## REST-API endpoint examples

### Start page

#### http://127.0.0.1:8055/items/startpage
Fetch startpage data.  
  
Contains title, hero (id) and content (HTML).

#### http://127.0.0.1:8055/items/startpage?fields=&ast;.&ast;
Fetch startpage data, including hero image metadata. This is required when you want to display hero image in frontend. See Assets endpoint example below to learn how to display images in your frontend application.  
  
Contains title, hero (metadata) and content.

### About page 
#### http://127.0.0.1:8055/items/about  
Fetch about page data.  

Contains content (HTML).  

### Pages
#### http://127.0.0.1:8055/items/pages
Fetch all pages data.  

Each page contains id, date created, date updated, title, content (HTML), slug, hero (id).

#### http://127.0.0.1:8055/items/pages?fields=&ast;.&ast;  
Fetch all pages data including hero image metadata.  

Each page contains id, date created, date updated, title, content (HTML), slug, hero (metadata).  

### Page
#### http://127.0.0.1:8055/items/pages/{{id}}
Fetch page data by id.  
  
Contains id, date created, date updated, title, content (HTML), slug, hero (id).  

#### http://127.0.0.1:8055/items/pages/{{id}}?fields=&ast;.&ast;  
Fetch page data by id, including hero metadata.  
  
Contains id, date created, date updated, title, content (HTML), slug, hero (metadata).  

#### http://127.0.0.1:8055/items/pages?filter[slug][_eq]={{slug}}
Fetch page data by slug.  
  
Contains id, date created, date updated, title, content (HTML), slug, hero (id).  

#### http://127.0.0.1:8055/items/pages?fields=&ast;.&ast;&filter[slug][_eq]={{slug}}
Fetch page data by slug, including hero metadata.  
  
Contains id, date created, date updated, title, content (HTML), slug, hero (metadata).  

### Posts
#### http://127.0.0.1:8055/items/posts
Fetch all posts data.  

Each post contains id, date created, date updated, title, content (HTML), categories (id).  

#### http://127.0.0.1:8055/items/posts?fields=&ast;.&ast;.&ast;  
Fetch all posts data including categories metadata.  

Each post contains iid, date created, date updated, title, content (HTML), categories (metadata).  

#### http://127.0.0.1:8055/items/posts?filter[categories][categories_id][id][_in]={{id:s}}
Fetch all posts data. Filter by category id. (id:s is a comma seperated list like 1,2,5)  

Each post contains id, date created, date updated, title, content (HTML), categories (id).  

### Post
#### http://127.0.0.1:8055/items/posts/{{id}}
Fetch post data by id.  
  
contains id, date created, date updated, title, content (HTML), categories (id).   

#### http://127.0.0.1:8055/items/posts/{{id}}?fields=&ast;.&ast;.&ast;  
Fetch post data by id, including categories metadata.  
  
contains id, date created, date updated, title, content (HTML), categories (metadata).  

### Categories

#### http://127.0.0.1:8055/items/categories
Fetch all categories data.  

Each category contains id and category title.

### Assets
#### http://127.0.0.1:8055/assets/{{id}}/{{filename_download}}
Fetch asset/image. Can be used as HTML img src in frontend. Use starpage and page hero metadata to find id and file_download.  
  
Example: http://127.0.0.1:8055/assets/626f2df6-d33f-414f-9c66-2074c3877e2e/ERP-budgeting.jpg  

### Directus docs
Read more about whats possible with Directus REST-api in official docs.  

Global parameters: https://docs.directus.io/reference/query.html

