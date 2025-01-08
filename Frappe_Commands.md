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

# Backup bench
    bench backup-all-sites