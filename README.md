Omeka Amazon S3 Compatible Storage Adapter
===============================

This is an S3 compatible storage adapter for Omeka that provides an _alternative_ to
the `Omeka_Storage_Adapter_ZendS3` which ships with the application. It is a fork of https://github.com/EHRI/omeka-amazon-s3-storage-adapter that allows the addition of a custom endpoint for use with alternative storage engines that are S3-compatible like Minio.

The main differences from the standard Omeka S3 adapter are:

 - this adapter uses the official AWS S3 SDK library
 - it requires PHP 5.5 or above
 - requires you supply the custom endpoint and region in the configuration
 - it supports the V4 authorization mechanism that is required on AWS
   regions created after July 2014

## Usage

1. Install the plugin by extracting it to the `plugins` directory in your Omeka instance and enabling
   in admin/plugins
2. Add the following to your Omeka `application/configuration/config.ini` file:

```
storage.adapter = Omeka_Storage_Adapter_AmazonS3
storage.adapterOptions.accessKeyId = MY-ACCESS-KEY-ID
storage.adapterOptions.secretAccessKey = MY-SECRET-KEY
storage.adapterOptions.bucket = my-bucket-name
storage.adapterOptions.region = us-east-1
storage.adapterOptions.endpoint = https://yourcustomendpoint
```

**Note**: This plugin has not yet been tested much so use at your own risk!
