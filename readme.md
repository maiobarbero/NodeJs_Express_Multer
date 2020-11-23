# INTRO

This is Node.js just a minimal app. Take it as an example, the aim is to be able to report polluted areas in the vicinity through coordinates and images
You can write you coordinates or use the btn to get them.

**Edit .env.example with your credential**

## Structure

- _db.config.js_ exports configuring parameters for MySQL connection & Sequelize. Edit .env.example with your credential
- _models/index.js_: uses configuration above to initialize Sequelize, models/image.model.js for Sequelize model Image.
- _views/index.html_ : contains HTML form for user to upload images.
- _routes/web.js_ : defines routes for endpoints that is called from views, use controllers to handle requests.
- _controllers_:

  - home.js returns views/index.html
  - upload.js handles upload & store images with middleware function
  - getAll.js endpoint to get all the reports (id,name,latitude,longitude)

- _middleware/upload.js_: initializes Multer Storage engine.
- _server.js_: initializes routes, runs Express app.

## DB (MySQL) Structure

===Database DB_NAME

== Structure of table images

|------  
|Col|Type|Null|Default  
|------  
|//**id**//|int(11)|No|  
|latitude|float|No|  
|longitude|float|No|  
|type|varchar(255)|Sì|NULL  
|name|varchar(255)|Sì|NULL  
|createdAt|datetime|No|  
|updatedAt|datetime|No|
