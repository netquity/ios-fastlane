# Netquity Fastlane

Deployment tool for netquity's iOS applications

## Installation

Pull the repo and install the dependencies
```sh
bundle install
```

Make sure that you have the correct iOS distribution certificates installed on your system - you can do this by navigating to the Apple Developer portal and downloading YOUR certificate.
Afterwards double click on the downloaded certificate and add it to your login keychain.

## Config

Create a `config.yml` file in the root of this project. The config file should follow the format - Change this in accordance with whichever projects you plan on building:
```yaml
projects:
  project_name:
    git_url: "git@github.com:project/project.git"
    workspace_url: "project.xcworkspace"
    project_url: "project.xcodeproj"
    default_scheme: 'production'
    schemes:
      production: 'Project Scheme Name'
```

Create a `.env` file in the root of this project. This .env file contains the Fastlane user account, and AWS S3 configuration:
```
FASTLANE_USER=""
S3_ACCESS_KEY=""
S3_SECRET_ACCESS_KEY=""
S3_BUCKET=""
AWS_REGION=""
```

## Deploying

In the root directory run the command

```sh
bundle exec fastlane deploy project:{project_name} branch:{branch_name} environment:{scheme_key}
```
