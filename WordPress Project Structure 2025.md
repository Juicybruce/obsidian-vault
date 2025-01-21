#work 

### WordPress side of things

WordPress specified in the `composer.json` as a dependency
- does now allow us to change the WP version per site

Theme is also listed as a dependency (with a path listed as a composer repo)
- Theme composer dictates some theme-specific plugins (like ACF or any additions)

`Composer installers` is the package that allows the specific syntax for installation paths for different types of plugins + theme

S3 uploads is utilised to replace the local uploads storage
- env vars for bucket name and region

Dockerfile is the one that is used in production, as is the Dockerfile.nginx and the nginx config. PHP.ini is also prod and can be changed

Docker composer files:
- base - this is **just** WordPress and Nginx, not even an image. Needs to be provided an image to run
- dev - this has a build step and other config to allow it to run locally

- You can specify the docker compose to use in the .env file (don't even need to source it!)

.dev container is an isolated dev environment for use when your local differs from the container
- extends the development one, but gives you a read/write FS (prod is read only)

If you want HTTPS:
- add a trusted local cert and extend the nginx config
- Or add another container to handle the https 

## 