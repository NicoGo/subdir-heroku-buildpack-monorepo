Originally from

Helps to build monorepo app (Spring/React in my case) by defining two env variables:

`PROJECT_PATH_BACK` Path to the back-end (Spring Boot) code.
`PROJECT_PATH_FRONT` Path to the front-end (React) code.

# How to use:
1. `heroku buildpacks:clear` if necessary
2. `heroku buildpacks:set https://github.com/NicoGo/subdir-heroku-buildpack-monorepo`
3. `heroku buildpacks:add heroku/nodejs` or whatever buildpack you need for your application
4. `heroku config:set PROJECT_PATH_FRONT=front-end` pointing to what you want to be a project front-end.
5. `heroku config:set PROJECT_PATH_BACK=back-end` pointing to what you want to be a project back-end.
6. Deploy your project to Heroku.

# How it works
The buildpack takes subdirectory you configured, erases everything else, and copies that subdirectory to project root. Then normal Heroku slug compilation proceeds.
