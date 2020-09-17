# Deployment-of-Mongodb-and-Mongo-Express-UI-on-Kubernetes-
Deploying  Mongodb and accessing it from Mongo-Express UI on Kubernetes.

## Mongo Express
Web-based MongoDB admin interface written with Node.js, Express and Bootstrap3


## Features
--------

* Connect to multiple databases
* View/add/delete databases
* View/add/rename/delete collections
* View/add/update/delete documents
* Preview audio/video/image assets inline in collection view
* Nested and/or large objects are collapsible for easy overview
* Async on-demand loading of big document properties (>100KB default) to keep collection view fast
* GridFS support - add/get/delete incredibly large files
* Use BSON data types in documents
* Mobile / Responsive - Bootstrap 3 works passably on small screens when you're in a bind
* Connect and authenticate to individual databases
* Authenticate as admin to view all databases
* Database blacklist/whitelist
* Custom CA and CA validation disabling
* Supports replica sets

## External Service URL 
----------
<img src="https://github.com/rohnux/Deployment-of-Mongodb-and-Mongo-Express-UI-on-Kubernetes/blob/master/Screenshots/external-service-url.png" title="External Service URL from Minikube">

## Screenshots
-----------
Home Page | Database View | Collection View | Editing A Document
--- | --- | --- | ---
<img src="https://github.com/rohnux/Deployment-of-Mongodb-and-Mongo-Express-UI-on-Kubernetes/blob/master/Screenshots/mongo-express-home-page.png" title="Home Page showing databases"> | <img src="https://github.com/rohnux/Deployment-of-Mongodb-and-Mongo-Express-UI-on-Kubernetes/blob/master/Screenshots/mongodb-collections.png" title="Viewing collections in a database" /> | <img src="https://github.com/rohnux/Deployment-of-Mongodb-and-Mongo-Express-UI-on-Kubernetes/blob/master/Screenshots/mongodb-collection-view.png" title="Viewing documents in a collection" /> | <img src="https://github.com/rohnux/Deployment-of-Mongodb-and-Mongo-Express-UI-on-Kubernetes/blob/master/Screenshots/Editing%20the%20documents.png" title="Editing a document" />

## Environment Variables
-----------
You can use the following [environment variables](https://docs.docker.com/reference/run/#env-environment-variables) to modify the container's configuration:

    Name                              | Default         | Description
    ----------------------------------|-----------------|------------
    `ME_CONFIG_MONGODB_SERVER`        |`mongo` or `localhost`| MongoDB host name or IP address. The default is `localhost` in the config file and `mongo` in the docker image. If it is a replica set, use a comma delimited list of the host names.
    `ME_CONFIG_MONGODB_PORT`          | `27017`         | MongoDB port.
    `ME_CONFIG_MONGODB_URL`           | `mongodb://admin:pass@localhost:27017/db?ssl=false`
    `ME_CONFIG_MONGODB_ENABLE_ADMIN`  | `false`         | Enable administrator access. Send strings: `"true"` or `"false"`.
    `ME_CONFIG_MONGODB_ADMINUSERNAME` | ` `             | Administrator username.
    `ME_CONFIG_MONGODB_ADMINPASSWORD` | ` `             | Administrator password.
    `ME_CONFIG_MONGODB_AUTH_DATABASE` | `db`            | Database name (only needed if `ENABLE_ADMIN` is `"false"`).
    `ME_CONFIG_MONGODB_AUTH_USERNAME` | `admin`         | Database username (only needed if `ENABLE_ADMIN` is `"false"`).
    `ME_CONFIG_MONGODB_AUTH_PASSWORD` | `pass`          | Database password (only needed if `ENABLE_ADMIN` is `"false"`).
    `ME_CONFIG_SITE_BASEURL`          | `/`             | Set the express baseUrl to ease mounting at a subdirectory. Remember to include a leading and trailing slash.
    `ME_CONFIG_SITE_COOKIESECRET`     | `cookiesecret`  | String used by [cookie-parser middleware](https://www.npmjs.com/package/cookie-parser) to sign cookies.
    `ME_CONFIG_SITE_SESSIONSECRET`    | `sessionsecret` | String used to sign the session ID cookie by [express-session middleware](https://www.npmjs.com/package/express-session).
    `ME_CONFIG_BASICAUTH_USERNAME`    | ``              | mongo-express web login name. Sending an empty string will disable basic authentication.
    `ME_CONFIG_BASICAUTH_PASSWORD`    | ``              | mongo-express web login password.
    `ME_CONFIG_REQUEST_SIZE`          | `100kb`         | Used to configure maximum mongo update payload size. CRUD operations above this size will fail due to restrictions in [body-parser](https://www.npmjs.com/package/body-parser).
    `ME_CONFIG_OPTIONS_EDITORTHEME`   | `rubyblue`      | Web editor color theme, [more here](http://codemirror.net/demo/theme.html).
    `ME_CONFIG_OPTIONS_READONLY`      | `false`         | if readOnly is true, components of writing are not visible.
    `ME_CONFIG_SITE_SSL_ENABLED`      | `false`         | Enable SSL.
    `ME_CONFIG_MONGODB_SSLVALIDATE`   | `true`          | Validate mongod server certificate against CA
    `ME_CONFIG_SITE_SSL_CRT_PATH`     | ` `             | SSL certificate file.
    `ME_CONFIG_SITE_SSL_KEY_PATH`     | ` `             | SSL key file.
    `ME_CONFIG_SITE_GRIDFS_ENABLED`   | `false`         | Enable gridFS to manage uploaded files.
    `VCAP_APP_HOST`                   | `localhost`     | address that mongo-express will listen on for incoming connections.
    `VCAP_APP_PORT`                   | `8081`          | port that mongo-express will run on.
    `ME_CONFIG_MONGODB_CA_FILE`       | ``              | CA certificate File
    `ME_CONFIG_BASICAUTH_USERNAME_FILE`     | ``        | File version of ME_CONFIG_BASICAUTH_USERNAME
    `ME_CONFIG_BASICAUTH_PASSWORD_FILE`     | ``        | File version of ME_CONFIG_BASICAUTH_PASSWORD
    `ME_CONFIG_MONGODB_ADMINUSERNAME_FILE`  | ``        | File version of ME_CONFIG_MONGODB_ADMINUSERNAME
    `ME_CONFIG_MONGODB_ADMINPASSWORD_FILE`  | ``        | File version of ME_CONFIG_MONGODB_ADMINPASSWORD
    `ME_CONFIG_MONGODB_AUTH_USERNAME_FILE`  | ``        | File version of ME_CONFIG_MONGODB_AUTH_USERNAME
    `ME_CONFIG_MONGODB_AUTH_PASSWORD_FILE`  | ``        | File version of ME_CONFIG_MONGODB_AUTH_PASSWORD
