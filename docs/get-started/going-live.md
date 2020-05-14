---
id: going-live
title: Going Live
sidebar_label: Going Live
---

This article demonstrates how you can deploy your project to `dev`, `prod` and any other environment you may have. At the end of this process you will have a public URL to show your website to the world.

## 1. Create a `dev` environment config

Open the `api/.env.json` file. You should see a similar config file:

```json
{
  "default": {
    "GRAPHQL_INTROSPECTION": true,
    "GRAPHQL_PLAYGROUND": true,
    "S3_BUCKET": "webiny-files-72858e17",
    "JWT_SECRET": "GSyWyuHU2uHrO+wnSO8OjQ+wPbuQmBclVNFejoo9qmsQRNFAZHu+PFSyq48+"
  }
}
```

In the top-level of the project, look at the `.env.json` file. You should something similar:
```json
{
    "default": {
      "MONGODB_SERVER": "mongodb+srv://username:password@my-db-123.mongodb.net/test?retryWrites=true",
      "MONGODB_NAME": "webiny-72858e17"
    }
}
```

If you don't want to change anything for your `dev` environment, leave them as is.

However, if you want to use a different database, for example, you can create a new config block and override the `default` values:

```json
{
  "default": {
    "MONGODB_SERVER": "mongodb+srv://username:password@my-db-123.mongodb.net/test?retryWrites=true",
    "MONGODB_NAME": "webiny-72858e17"
  },
  "dev": {
    "MONGODB_NAME": "webiny-dev-72858e17",
    "JWT_SECRET": "A different JWT secret"
  }
}
```

## 2. Deploy API using `dev` environment

From the root of your project, run the following command:

```
webiny deploy api --env=dev
```


## 3. Deploy apps using `dev` environment

From the root of your project, run the following command:

```
webiny deploy apps --env=dev
```

## Other environments

If you also want to deploy a `prod` environment, repeat the procedure using the `prod` value.

This can be extended if you need more environments, you can easily add them in the same procedure shown above, but you will need to also add the appropriate build scripts to your apps, in the following files:

```
apps/admin/package.json
apps/site/package.json
```

An example script for `staging` environment could look like this:

```
"build:staging": "env-cmd -r .env.json -e default,staging webiny run build"
```
