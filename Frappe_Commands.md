# Initialize a new bench
    bench init [bench-name]

# Create a new site
    bench new-site [site-name]

# Start the bench
    bench start

# Install an app on a site
    bench --site [site-name] install-app [app-name]

# Update bench
    bench update

# Migrate a site
    bench --site [site-name] migrate

# Backup a site
    bench --site [site-name] backup

# Restore a site from a backup
    bench --site [site-name] restore [path-to-backup-file]

# Get a list of sites
    bench list-sites

# Get a list of apps
    bench list-apps

# Restart bench
    bench restart
    # or use sudo supervisorctl restart all

# Backup bench
    bench backup-all-sites

    # Backup all sites managed by the bench
    # This command creates a backup of the database and files for all sites.
    # It is useful to ensure that you have a restore point before making any changes or updates.
    bench backup-all-sites

# Bench migrate
bench migrate
The `bench migrate` command is used in the Frappe framework to apply changes to the database schema and update the codebase for a specific site. This command is typically run after pulling new code changes or making modifications to the code that affect the database structure.

Here's a detailed explanation of its usage:

1. **Apply Database Migrations**: When you make changes to the database schema (e.g., adding new fields, modifying existing fields), these changes need to be applied to the actual database. The `bench migrate` command handles this by running the necessary migrations.

2. **Sync Changes**: It ensures that any changes in the DocTypes, custom scripts, and other configurations are synchronized with the database.

3. **Rebuild Search Index**: If there are changes that affect the search index, this command will rebuild the index to reflect the latest data.

4. **Update Translations**: It updates the translations for the site, ensuring that any new or modified translations are applied.

### Example Usage

To run the `bench migrate` command, navigate to your bench directory in the terminal and execute:

```sh
bench migrate
```

This will apply all pending migrations and synchronize the database schema with the latest code changes for the current site.

### Example in Documentation

You might include this in your documentation as follows:

```markdown
# Migrate bench
    bench migrate

    # Apply database migrations and synchronize changes for the current site
    # This command updates the database schema, syncs DocTypes, rebuilds the search index, and updates translations.
    bench migrate
```

# Bench App Development Commands

## Create a new app
    bench new-app [app-name]

    # This command creates a new Frappe app with the specified name.
    # It sets up the necessary directory structure and files for the app.
    bench new-app my_app

## Install an app
    bench --site [site-name] install-app [app-name]

    # This command installs the specified app on the given site.
    # It ensures that the app is available and functional on the site.
    bench --site my_site install-app my_app

## Uninstall an app
    bench --site [site-name] uninstall-app [app-name]

    # This command uninstalls the specified app from the given site.
    # It removes the app's database tables and files from the site.
    bench --site my_site uninstall-app my_app

## Remove an app
    bench remove-app [app-name]

    # This command removes the specified app from the bench.
    # It deletes the app's directory and files from the bench.
    bench remove-app my_app

## Build assets
    bench build

    # This command compiles and builds the assets (CSS, JS) for the apps.
    # It ensures that the latest changes to the assets are reflected.
    bench build

## Watch for changes
    bench watch

    # This command watches for changes in the assets and rebuilds them automatically.
    # It is useful during development to see changes in real-time.
    bench watch

## Clear cache
    bench clear-cache

    # This command clears the cache for the bench.
    # It is useful to ensure that the latest changes are applied.
    bench clear-cache

## Clear site cache
    bench --site [site-name] clear-cache

    # This command clears the cache for the specified site.
    # It ensures that the latest changes are applied to the site.
    bench --site my_site clear-cache

## Set Maintenance Mode
    bench --site [site-name] set-maintenance-mode [on/off]

    # This command enables or disables maintenance mode for the specified site.
    # When maintenance mode is on, the site will display a maintenance page to visitors.
    bench --site my_site set-maintenance-mode on

## Rebuild Website
    bench --site [site-name] build-website

    # This command rebuilds the website for the specified site.
    # It regenerates the static pages and assets for the site.
    bench --site my_site build-website

## Reinstall Site
    bench --site [site-name] reinstall

    # This command reinstalls the specified site.
    # It drops the existing database and creates a new one, effectively resetting the site.
    bench --site my_site reinstall

## Drop Site
    bench drop-site [site-name]

    # This command drops the specified site.
    # It deletes the site's database and files, removing it completely.
    bench drop-site my_site

## Set Site Config
    bench --site [site-name] set-config [key] [value]

    # This command sets a configuration value for the specified site.
    # It updates the site's configuration file with the given key-value pair.
    bench --site my_site set-config developer_mode 1

## Get Site Config
    bench --site [site-name] get-config [key]

    # This command retrieves a configuration value for the specified site.
    # It reads the site's configuration file and returns the value for the given key.
    bench --site my_site get-config developer_mode

    ## Doctype Commands

    ### Create a new Doctype
        bench --site [site-name] new-doctype [doctype-name]

        # This command creates a new Doctype with the specified name on the given site.
        # It sets up the necessary files and configurations for the Doctype.
        bench --site my_site new-doctype my_doctype

    ### Export Doctype
        bench --site [site-name] export-doctype [doctype-name]

        # This command exports the specified Doctype's definition to a JSON file.
        # It is useful for version control and sharing Doctype configurations.
        bench --site my_site export-doctype my_doctype

    ### Import Doctype
        bench --site [site-name] import-doctype [path-to-json-file]

        # This command imports a Doctype definition from a JSON file.
        # It updates the Doctype configuration on the site with the imported definition.
        bench --site my_site import-doctype /path/to/my_doctype.json

    ### Delete Doctype
        bench --site [site-name] delete-doctype [doctype-name]

        # This command deletes the specified Doctype from the given site.
        # It removes the Doctype's database table and files.
        bench --site my_site delete-doctype my_doctype