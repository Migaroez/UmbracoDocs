---
description: How to deal with corrupt examine index
hidden: true
---

# Corrupt Indexes

## Overview
Due to any type of file system errors, the data integrity of the examine files might become compromised. When this leads to examine not being able to load the index, umbraco considers this index to be corrupt.

Since this might happen while parts of the system are already hooked into the examine lifecycle hooks, it is recommended to deal with this file corruption while the application is offline.

## Resolution in a self hosted environment
- Stop the app
- Delete the files from disk. The location of the files will differ depending on your setup, see [the load-balancing article](https://docs.umbraco.com/umbraco-cms/fundamentals/setup/server-setup/load-balancing/file-system-replication#examine-directory-factory-options) for more information
- Restart the app

## Resolution on umbraco cloud
- Open the project in the cloud portal
- Select the correct environment
- Open kudo in the debug console
- Choose CMD
- Navigate to `C:\home\site\wwwroot\umbraco\Data\Temp>`
- Click the delete button next to the index in question
- Restart the environment.
