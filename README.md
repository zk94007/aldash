# AlDash
AlDash is for admin side dashboard system for user activities.

### Packages used
- go-chi/chi
- lib/pq
- jmoiron/sqlx
- markbates/pop/nulls
- gorilla/sessions
- gorilla/csrf
- gorilla/securecookies
- markbates/refresh
- microcosm-cc/bluemonday
- pkg/errors
- pressly/douceur
- pressly/goose
- satori/go.uuid
- spf13/cobra


### Installation and usage

1. Clone the repository
```
git clone https://github.com/toptal3/aldash	
cd aldash
```

2. Install the dependencies
```
glide install
npm install
```

3. Create the following environment variables.
```
PORT=1212
ENVIRONMENT=development (change to 'production' in the production environment)
HOST=localhost
DATABASE_URL=XXX (replace)
TEST_DATABASE_URL=XXX (replace)
MIGRATIONS_DIR=app/migrations
CSRF_KEY=XXX (replace with 32 character string (use the gen-key command))
HASH_KEY=XXX (replace with 64 character string (use the gen-key command))
BLOCK_KEY=XXX (replace with 32 character string (use the gen-key command))
SMTP_HOST=127.0.0.1
SMTP_PORT=1025
SMTP_USERNAME=__REPLACE__
SMTP_PASSWORD=__REPLACE__
MAILER_FROM=XXX (e.g: support@alloy.dev)
MAILER_HOST=http://localhost:1212
ASSET_URL=http://localhost:1212 (if you are using a CDN in production, this can be set to that URL)
```

3. Start the development server
```
go install
alloy dev
```

Now you can open your browser and navigate to http://localhost:1212 to see it in action. Any changes you make to the .go files will be automatically picked up and the app will be re-compiled.


### Project structure

```
    ├── README.md
    ├── app
    │   ├── handlers
    │   ├── mailer
    │   ├── migrations
    │   ├── models
    │   ├── router
    │   │   ├── middleware
    │   │   └── router.go
    │   ├── services
    │   │   ├── db.go
    │   │   └── session.go
    │   ├── templates
    │   │   ├── admin
    │   │   ├── layouts
    │   │   ├── mailer
    │   │   ├── pages
    │   └── views
    ├── assets
    │   ├── fonts
    │   ├── images
    │   ├── js
    │   └── scss
    │       ├── admin
    │       ├── frontend
    │       └── frontend.scss
    ├── cmd
    ├── testutils
    ├── glide.yaml
    ├── main.go
    ├── package.json
    ├── refresh.yml
    └── webpack.config.js
```