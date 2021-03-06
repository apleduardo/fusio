_Ever growing list of ideas and thoughts howto improve and extend Fusio. Topics_ 
_which are likely to be implemented are moved to a seperate github issue_

### 0.3

- [x] Update config help texts
- [x] Add CORS support to backend config
- [x] Installer handle upgrade from 0.2.x to 0.3.x
- [x] Complete Fusio consumer Account/ChangePassword API
- [x] Think about action to build better nested responses
  - [ ] Option to execute another action inside a template
  - [x] In general we need some kind of data templating engine where it is easy
        to write json data and call other actions etc.
- [x] Add database protractor tests
- [x] Add transactions to services
- [x] Disable edit button of scope backend, consumer and authorization since a 
      user would remove all assigned routes on save #13

### 0.4

- [ ] Add consumer and documentation protractor tests
- [ ] Improve cache action add option to specific get or uri parameters which
      come into the cache key
- [ ] Automatically add the consumer scope the to the scope list
- [ ] Database UI add auto increment option
- [ ] App button to regenerate app key and secret
- [ ] Consumer if access was already granted dont ask the user again instead 
      redirect the user directly or show the access token. We could add this 
      logic maybe to the meta lookup response
- [ ] Test GitHub/Google/Facebook login
- [ ] General test build an API and use different libraries to test OAuth2 
      interoperability
- [ ] Option to ratelimit specific apps
- [ ] Add forms endpoint
      The user can select a route, request method and an input field which
      contains the form format. Maybe based on https://github.com/joshfire/jsonform
  - [ ] Add a html endpoint which can render a form for an API endpoint for 
        humans to enter. This could be embeded per iframe in a website etc.
  - [ ] We need a new point forms. There a user can create a form for a schema.
        This form has an abstract json format which describes the look of the 
        form (look at schemaform.io or xforms). This abstract form can be 
        rendered in javascript, java, etc.
  - [ ] How do we handle form submits where a access token is required at the 
        backend (which is probably always required)?
  - [ ] We should build different libraries (javascript, java, etc.) to build 
        these forms
- [ ] Add action which can build a REST API for a table
- [ ] Import allow swagger format

### 0.x

- [ ] Add docker and vagrant box to easy test and deploy fusio
- [ ] Add function to measure execution time of an action add also additional
      chart to the statistics panel which shows slow actions. Maybe we should
      add a debug mode where those metrics are measured
- [ ] Add option to get and use a refresh token to extend the life time of an 
      access token
- [ ] When creating an connection verify that the connection works #2
- [x] Add option to store variables with an app which can be used for conditions 
      or in an action #6
- [ ] Add an API console where it is possible to test the API #7
  - [ ] Use http://schemaform.io/ to build a form based on a jsonschems to 
        submit data to the endpoint
        https://github.com/joshfire/jsonform
- [ ] Evaluate V8Js and check whether we could write an action where a user can 
      write an action in javascript
- [ ] Add different roles for the backend. I.e. an admin/manager and developer.
      A developer account can only edit specific entries
  - [ ] Probably we need a interface for developers. A editor view where the
        developer can design the APIs where he was assigned to
- [ ] Optimize the way how data is organized. I.e. we could have many actions or 
      schemas, we need a way to group or categorize entries so it is easier to
      organize
  - [x] Add filter action/schema by route and add link from routes to 
        action/schema with filtered route id
  - [ ] Probably use https://github.com/nickperkinslondon/angular-bootstrap-nav-tree
- [ ] Add proper CORS handling
- [ ] Add method to relogin if token expires. Probably we should save the expire
      time and make the relogin attempt based on this
- [ ] Write backend in TypeScript JS6 support transition to Angular2
- [ ] Add system log where every login and system change is shown
  - [ ] Add login bruteforce protection. Therefor we must log the ip of every 
        login attempt
  - [ ] We should add a limitation to the access token endpoint this would
        protect also the login
- [ ] Add action to simplify creating more complex logic (if else, switch).
  - [ ] In long term we could build a flowchart like yahoo pipes to build the 
        actions
  - [ ] Use http://js.cytoscape.org/ to build a graph from the actions/schema
  - [x] Write a processor action where a user can define multiple actions in
        a YAML format
- [ ] Unify backend filter usage
- [ ] When creating an action verify that the action works. How can we handle 
      template parameters for testing?
- [ ] Schema definitions limitations
  - [ ] There is no way to add query parameters
  - [ ] At the moment we only handle the schema for an 200 return. Probably add 
        possibility to add response schema for other status codes
- [ ] We need to create a marketplace where all adapters are listed and where
      developers can provide a adapter for their system
  - [ ] The best way todo this is to parse all packages with a specific tag 
        "fusio-adapter" from packagist add list them on fusio-project.org
        There is an API which we cna use to request specific tags
  - [ ] Extend the documentation howto write an adapter
- [ ] Build new adapters
  - [ ] Add action which builds a REST API from a table where a user only needs 
        to provide the table name. The action needs two routes /table and 
        /table/:id
  - [ ] Add SOAP action
  - [ ] Add couchdb action
  - [ ] Add an action merge which combines the result of two actions into one 
        result (This is probably already possible through the transform action)
  - [ ] Build adapters for popular systems i.e. wordpress/drupal etc.
  - [ ] Gateways to other systems which dont have an API
  - [ ] Gateways to complex systems i.e. sharepoint
- [ ] Consider disable request model for DELETE method since a DELETE should
      probably not include a request body?
- [x] Schema if a schema name changes or it gets deleted what happens with 
      schemas which refer to the changed schema? #3
  - [x] Since the cache includes the complete resolved schema the problem occurs
        of the user wants to save the schema which refers to an deleted schema

### 1.0

### Meta

- [ ] Add use case section to website
- [ ] Provide a video with a installation and demo about the system
- [x] Register domain maybe fusio-api.org or fusio-project.org
- [x] Add a online demo system
- [ ] ~~Add beta phase on the website. Where users can enter an email for an invite~~
- [ ] Extend manual
- [x] Setup discourse forum (we have a google group)
- [ ] For the stable release write about Fusio at 
  - [ ] http://nordicapis.com/create-with-us/
  - [ ] https://www.reddit.com/r/php / https://www.reddit.com/r/rest
  - [ ] http://www.sitepoint.com/

### Archive

- [ ] ~~Provide actions to create an API from a file i.e. JSON, XML maybe CSV?~~
- [x] Option to manually generate an access token
  - [ ] ~~Option to generate an access token for an application through the 
        backend. Maybe with an option to specify the expire time~~
  - [x] Probably add also an command to generate an access token
- [x] Simplifiy creating schemas
  - [ ] ~~Probably add third party java tool where it is possible to model  
        easily an schema~~ (This should be in any case an external project)
  - [x] Add possibility to upload json schema or add import json schema command
  - [x] If an json schema has no id probably use the psx_url from the config
        At the moment an error occurs if no id is available. Actually we need 
        the id only if we reference other schemas to resolve the $ref path
- [x] We need an adapter system. An adapter provides all configurations which 
      you need to create a REST API from a 3rd party system. The adapter uses 
      the core actions or provides actions by itself. It can use composer to get 
      dependencies. Fusio provides a custom adapter installer which handles all
      the logic
  - [x] Through this is would be possible to create a API for an existing
        system with i.e. "composer require fusio/drupal-adapter"
  - [x] The installer must ask the user for i.e. the API base path or the 
        connection which sould be used
- [ ] We probably need an marketplace for actions where we can provide 
      connectors for different software
  - [ ] New actions can be easily installed through composer. They must be only
        added to the configuration.php
  - [x] Through this we could create APIs for many server applications
  - [x] It should be possible for an action to define the routes which are 
        required for an action i.e. we could build a mail action and this action
        would needs one POST endpoint (i.e. /send) where we send a mail on post. 
        So it is not required that the endpoint is named /send but we must give
        the user the option to install the route. Probably an action should be
        wrapped as phar which we only have to copy to a sepcific folder
- [ ] ~~Add action "exec" which executes given PHP code~~
  - [x] It is easy possible to provide a custom action
- [ ] ~~Add general config. Probably to set the expire time of the oauth token.~~
  - [x] At the moment we have all config entries in the configuration.php which
        is sufficient
- [x] Encrypt credentials in connection config field
- [x] Improve cache action, consider path parameters etc.
- [ ] ~~Add support for jsonapi format http://jsonapi.org/~~
      (We dont want to force a data format for the user. If a user wants to 
      generate such a response format it should be no problem to generate)
- [x] Add schema importer i.e. swagger, raml, etc. in order to easily generate
      the API endpoints. Probably start with swagger since its the most popular 
      (We have added a RAML importer)
  - [ ] ~~We could use http://ngmodules.org/modules/ng-file-upload for upload~~
- [x] Add mongodb action
- [x] At the moment the Oauth endpoint supports only "Resource Owner Password 
      Credentials" we need also support for "Authorization Code" so that the API
      can be used for web apps. Therefor we must provide a way for an consumer 
      to login and grant an app authorization / manage authorized apps etc. 
      Probably this can also be done through an API so that an API provider can 
      provide its own UI for the user #5
- [x] JSONSchema export API which replaces the schema:// references with an API
      endpoint url (we have now a json schema export command)
- [x] Add RAML import. We need probably a general import field where someone can
      upload a api sepc file (RAML) which gets then imported
- [x] Return only actions and schema which are active or locked. Disabled edit 
      and delete button for locked actions/schema
- [x] Add transform action to transform an incoming request into another form 
      i.e. with jsonpatch https://tools.ietf.org/html/rfc6902 #9
- [x] "Proxy" action which provides a way to call a different API and use the 
      response
  - [x] Probably we need different PROXY actions i.e. JSON, SOAP, XML etc.
  - [x] It must be possible to configure custom headers or at leat
        authentication
- [x] We need a overall function which normalizes the result of an action to a 
      consistent format
- [x] Add route select filter for action and schemas
- [x] Access token use better randoum source for generation
- [x] Add validation panel where a user can register a validator for a specific
      field inside a schema. The validator uses also the expression language. A
      adapter can also register new validators. 
- [x] It should be not possible to delete a route which has a API version in 
      production/deprecated status only in development and closed
- [x] If an routes was deleted the status flag is set to 0 .. it is then not
      possible to create an route with the same name
- [x] It should be not possible to delete an route which is in production status
- [x] If we change the API status from development to production we should copy
      all request/response/action data so that further edits dont change the API
      behaviour
- [x] On route save store all used actions and schemas in a seperate relation 
      table
- [x] If a route is moved from development to production mode lock all used 
      schemas and actions
- [x] Handle status for actions and schemas. Possible status: action, locked, 
      deleted. If a action or schema gets delete set only the status flag
- [x] Update /documentation html files (probably use AngularJS with material 
      design)
- [x] Add change password dialog for user account
- [x] Log errors from actions
- [x] Add statistic point where a user can get more detailed informations about 
      the apps/requests etc. A more detailed version of the dashboard where it 
      is possible to select a timeframe
- [x] Add better handling for passthru schema in documentation i.e. an box that 
      no schema was specified
- [x] Return all Apps per user on user details request
- [x] Add more hints to form inputs and link to more details help
- [x] Add install sample data command. The install command installs all needed 
      db entries so we dont need directly the sample data
- [x] Check delete dialogs
- [x] Documentation viewer add error handling if API returns 500
- [x] Add request rate limitations
      Is available through condition action an rateLimit methods
- [x] Scope tokens fix expires on text
- [x] Remove /doc routes from the scope
- [x] Dont allow /doc, /backend and /authentication as route path
- [x] Add useradd command
- [x] Add install script
- [x] Add action and backend api tests
- [x] Add authentication
- [x] Update create Route view
- [x] Schema add ace json editor where a user can insert the json schema. 
      References to other schemas are with "$ref": "#/definition/[schema_name]"
  - [x] Based on the schema we create an definition file which gets referenced 
        on the sql table
- [x] Possibility to set status level for the API. When the API is in production
      status it is not possible to change the models. Maybe we should copy the 
      used schema some where so that it dont changed.
  - [x] An API has the following status lifecycle: 
        development -> production -> deprecated
- [x] Add option to version an API. If you want change an production API you 
      have to add a new version
