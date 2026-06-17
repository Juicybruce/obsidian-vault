#### Dev process new project:

- standardise our docker compose vs DDEV usage
	- We don't want both in the template
- Blank DB (preconfigured) - move to an s3 for maintenance
	- Can this be a YAML file that the script uses to change settings in a WP core install instead?
- Symlink created by composer for theme folder - bug
- Update example.env + wp-config.php to allow for s3 local
- update docker-compose to allow write acces to uploads and custom fields and blocks
- Scripts (new or existing) should be globally available, not committed to template
- Tim's virtual host + local DNS thing
- COMPOSE_PROJECT_NAME - set somewhere in scripts, also useful for our virtual port and local domain hostname stuff
- MCP adapter setup for development (add .mcp to project root)
- an easier time for things like importing/exporting db's? Wp cli access? Does this actually make DDEV a stronger candidate, because the commands for doing common tasks are too complex to remember for the docker compose version
- another thing is the fact you can use ddev commands at any point in child directories, you can't do that with docker compose. eg, `docker compose exec` lacks context when you are in the theme directory
- How are we fetching existing DB's for projects? developer.ionata API access?
- Add build to the pipeline!
- Another basetheme thing to discuss would be some default spacing css variables instead of using the gap-*

- these changes need to be pulled into existing projects
- partials into base theme
- ai agent guidance + docs into basetheme

- add Evo's 
	- menu nav walker
	- Post type registration

Steps for new project (automate):
1. name, project-code other info (admin name and password etc)
2. pulls theme (branch choice)
3. rewrite theme stuff (rm .git, updates style.css, composer, package.json)
4. rewrite template stuff (root composer.json) - can this be handled in another way? Yes turns out `composer config` is a command and I'm an idiot
5. cp the example.env
6. run composer update
7. Handle DDEV / Docker compose first up
8. handle initial DB population
	1. Handle setting changes (Site name etc)
9. Prompts user to fill out Bitwarden

Steps for existing project (automate):
1. fetch project repo (maybe a gum search of all `wp-project-*`?)
2. fetches databases
3. gives s3 uploads options (minio vs local vs connection to s3 bucket)
4. cp example.env
5. composer install
6. npm initial install