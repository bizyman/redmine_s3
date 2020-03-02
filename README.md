# S3 plugin for Redmine

## Description
This [Redmine](http://www.redmine.org) plugin makes file attachments be stored on [Amazon S3](http://aws.amazon.com/s3) rather than on the local filesystem. This is a fork for [original gem](http://github.com/tigrish/redmine_s3) and difference is that this one supports Redmine 4.0.x

## Installation
1. Make sure Redmine is installed and cd into it's root directory
2. `git clone -b 4.0-stable https://github.com/farend/redmine_s3.git plugins/redmine_s3`
3. `cp plugins/redmine_s3/config/s3.yml.example config/s3.yml`
4. Edit config/s3.yml with your favourite editor
5. `bundle install --without development test` for installing this plugin dependencies (if you already did it, doing a `bundle install` again would do no harm)
6. Restart web server/upload to production/whatever
7. *Optional*: Run `rake redmine_s3:files_to_s3` to upload files in your files folder to s3

## Options Overview
* The bucket specified in s3.yml will be created automatically when the plugin is loaded (this is generally when the server starts).

## Options Detail
* access_key_id: string key (required)
* secret_access_key: string key (required)
* bucket: string bucket name (required)
* folder: string folder name inside bucket (for example: 'attachments')
* endpoint: string endpoint instead of s3.amazonaws.com
* region: string aws region (activate when endpoint is not set)
* thumb_folder: string folder where attachment thumbnails are stored; defaults to 'tmp'

## License

This plugin is released under the [MIT License](http://www.opensource.org/licenses/MIT).
