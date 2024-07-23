# Instructions

## Part I: Create a Github App

1. Go to https://github.com/organizations/Submitty/settings/apps/new
2. Give the app a name and URL (submitty.org is fine, the URL isn't used for anything)
3. Unset "Webhook" > "Active"
4. Set "Permissions" > "Repository permissions" > "Pull Requests" to "Read-only"
5. Set "Permissions" > "Repository Permissions" > "Issues" to "Read-only"
6. Set "Permissions" > "Organization permissions" > "Projects" to "Read and write"
7. Finally, click Create GitHub App at the bottom of the page

## Part II: Install the Github App

1. Generate a private key. This will download a .pem file that we will use later
2. Copy/save the APP_ID (a six-digit number)
3. Go to "Install App" and Install on the Submitty organization
4. When it asks for repository access, choose All Repositories (this allows repositories created in the future to be handled by the app without having to change permissions for it; the Github Actions using this App will still be per-repo)

## Part III: Set up environment variables and secrets

1. https://github.com/organizations/Submitty/settings/variables/actions
2. Add a new organization variable called "APP_ID" and paste the six-digit APP_ID from earlier in
3. Go to "Secrets", and "Create Organization Secret"
4. Add a new organization secret called "APP_PEM" and paste the contents of the .pem file from earlier in, including the "BEGIN/END RSA PRIVATE KEY" header and footer

## That's it!
