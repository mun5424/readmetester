# Fundspring

Monorepo for Fundspring for LF Foundation.

## Dependencies

- node version 8.11

If you are using node version later than 9, you will need to roll back to a version greater than 4 and less than 9.

Run the following commands on Homebrew. 

```
brew install node@8
brew unlink node 
brew link node@8 
```
- golang version 1.10

Make sure to have this repository under the correct $GOPATH else the go build commands will not work.

- gometalinter
```
brew tap alecthomas/homebrew-tap
brew install gometalinter
```
If the yarn install-all complains that gometalinter.v2 is not found, you simply need to link gometalinter.v2 from gometalinter using the following command.
```
ln -s /usr/local/bin/gometalinter /usr/local/bin/gometalinter.v2 
```
- dep
- yarn ^1.5
- webpack
- docker/docker-compose
- bash

## Basic Setup

- Make a clone of this project.
- Set up your personal AWS credentials under ~/.aws/credentials, with the profile name lff
  ```ini
  [lff]
  aws_access_key_id = XXXXXXXXXX
  aws_secret_access_key = XXXXXXXXXX
  ```
- Install everything recursively by calling `yarn install-all`

## CI Setup

This project uses drone.io for CI. The CI expects the following environment variables.

- SLACK_WEBHOOK - A hook for build succeess/failure notifications
- AWS_ACCESS_KEY_ID - The production AWS access key id.
- AWS_SECRET_ACCESS_KEY - The production AWS secret access key.
- DANGER_GITHUB_API_TOKEN - The danger github api token to use.

## CI Usage

The README in each subfolder has information about specific deployments. You can test the example CI process using the Drone.io [CLI tool](http://docs.drone.io/cli-installation/).
