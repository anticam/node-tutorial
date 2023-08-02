<https://developers.sap.com/tutorials/btp-cf-buildpacks-node-create.html>

<https://github.com/cloudfoundry/multiapps-controller/wiki/Deployment-Descriptor>

<https://github.com/cloudfoundry/multiapps-controller/wiki/Supported-Parameters>

<https://github.com/SAP-docs/btp-cloud-platform/blob/main/docs/30-development/multitarget-applications-in-the-cloud-foundry-environment-d04fc0e.md>


<https://learning.sap.com/learning-journey/develop-advanced-extensions-with-sap-cloud-sdk/working-with-the-mta-yaml-file_a884b953-7212-439d-a5f0-5c3fd122f75f>


```
$ cf push -b https://github.com/cloudfoundry/nodejs-buildpack.git#v1.8.9
Pushing app myapp to org 530335dctrial / space dev as antal.perger@sap.com...
Applying manifest file C:\Users\antal\code\node-tutorial\manifest.yaml...

Updating with these attributes...
  ---
  applications:
+ - name: myapp
    path: C:\Users\antal\code\node-tutorial\myapp
    memory: 128M
+   random-route: true
+   buildpacks:
+   - https://github.com/cloudfoundry/nodejs-buildpack.git#v1.8.9
Manifest applied
Packaging files to upload...
Uploading files...
 699.61 KiB / 699.61 KiB [=========================================================] 100.00% 1s 

Waiting for API to complete processing files...

Staging app and tracing logs...
   -----> Download go 1.19
   -----> Running go build supply
   /tmp/buildpackdownloads/aab429aae59012ea0725c3d3f6c63937 ~
   ~
   -----> Nodejs Buildpack version 1.8.9
   -----> Bootstrapping python
   -----> Installing python 3.10.10
   Download [https://buildpacks.cloudfoundry.org/dependencies/python/python_3.10.10_linux_x64_cflinuxfs4_430b17fd.tgz]
   -----> Installing binaries
   engines.node (package.json): 14.x.x
   engines.npm (package.json): unspecified (use default)
   -----> Installing node 14.21.3
   Download [https://buildpacks.cloudfoundry.org/dependencies/node/node_14.21.3_linux_x64_cflinuxfs4_7efadd52.tgz]
   **WARNING** node 14.x.x will no longer be available in new buildpacks released after 2023-04-30.
   See: https://github.com/nodejs/Release
   Using default npm version: 6.14.18
   -----> Installing yarn 1.22.19
   Download [https://buildpacks.cloudfoundry.org/dependencies/yarn/yarn_1.22.19_linux_noarch_any-stack_32d0e82e.tgz]
   Installed yarn 1.22.19
   -----> Creating runtime environment
   NODE_ENV=production
   NODE_HOME=/tmp/contents226070833/deps/0/node
   NODE_MODULES_CACHE=true
   NODE_VERBOSE=false
   NPM_CONFIG_LOGLEVEL=error
   NPM_CONFIG_PRODUCTION=true
   -----> Building dependencies
   Prebuild detected (node_modules already exists)
   Rebuilding any native modules
   express@4.18.2 /tmp/app/node_modules/express
   accepts@1.3.8 /tmp/app/node_modules/accepts
   mime-types@2.1.35 /tmp/app/node_modules/mime-types
   mime-db@1.52.0 /tmp/app/node_modules/mime-db
   negotiator@0.6.3 /tmp/app/node_modules/negotiator
   array-flatten@1.1.1 /tmp/app/node_modules/array-flatten
   body-parser@1.20.1 /tmp/app/node_modules/body-parser
   bytes@3.1.2 /tmp/app/node_modules/bytes
   content-type@1.0.5 /tmp/app/node_modules/content-type
   debug@2.6.9 /tmp/app/node_modules/debug
   ms@2.0.0 /tmp/app/node_modules/ms
   depd@2.0.0 /tmp/app/node_modules/depd
   destroy@1.2.0 /tmp/app/node_modules/destroy
   http-errors@2.0.0 /tmp/app/node_modules/http-errors
   inherits@2.0.4 /tmp/app/node_modules/inherits
   setprototypeof@1.2.0 /tmp/app/node_modules/setprototypeof
   statuses@2.0.1 /tmp/app/node_modules/statuses
   toidentifier@1.0.1 /tmp/app/node_modules/toidentifier
   iconv-lite@0.4.24 /tmp/app/node_modules/iconv-lite
   safer-buffer@2.1.2 /tmp/app/node_modules/safer-buffer
   on-finished@2.4.1 /tmp/app/node_modules/on-finished
   ee-first@1.1.1 /tmp/app/node_modules/ee-first
   qs@6.11.0 /tmp/app/node_modules/qs
   side-channel@1.0.4 /tmp/app/node_modules/side-channel
   call-bind@1.0.2 /tmp/app/node_modules/call-bind
   function-bind@1.1.1 /tmp/app/node_modules/function-bind
   get-intrinsic@1.2.1 /tmp/app/node_modules/get-intrinsic
   has@1.0.3 /tmp/app/node_modules/has
   has-proto@1.0.1 /tmp/app/node_modules/has-proto
   has-symbols@1.0.3 /tmp/app/node_modules/has-symbols
   object-inspect@1.12.3 /tmp/app/node_modules/object-inspect
   raw-body@2.5.1 /tmp/app/node_modules/raw-body
   unpipe@1.0.0 /tmp/app/node_modules/unpipe
   type-is@1.6.18 /tmp/app/node_modules/type-is
   media-typer@0.3.0 /tmp/app/node_modules/media-typer
   content-disposition@0.5.4 /tmp/app/node_modules/content-disposition
   safe-buffer@5.2.1 /tmp/app/node_modules/safe-buffer
   cookie@0.5.0 /tmp/app/node_modules/cookie
   cookie-signature@1.0.6 /tmp/app/node_modules/cookie-signature
   encodeurl@1.0.2 /tmp/app/node_modules/encodeurl
   escape-html@1.0.3 /tmp/app/node_modules/escape-html
   etag@1.8.1 /tmp/app/node_modules/etag
   finalhandler@1.2.0 /tmp/app/node_modules/finalhandler
   parseurl@1.3.3 /tmp/app/node_modules/parseurl
   fresh@0.5.2 /tmp/app/node_modules/fresh
   merge-descriptors@1.0.1 /tmp/app/node_modules/merge-descriptors
   methods@1.1.2 /tmp/app/node_modules/methods
   path-to-regexp@0.1.7 /tmp/app/node_modules/path-to-regexp
   proxy-addr@2.0.7 /tmp/app/node_modules/proxy-addr
   forwarded@0.2.0 /tmp/app/node_modules/forwarded
   ipaddr.js@1.9.1 /tmp/app/node_modules/ipaddr.js
   range-parser@1.2.1 /tmp/app/node_modules/range-parser
   send@0.18.0 /tmp/app/node_modules/send
   mime@1.6.0 /tmp/app/node_modules/mime
   ms@2.1.3 /tmp/app/node_modules/send/node_modules/ms
   serve-static@1.15.0 /tmp/app/node_modules/serve-static
   utils-merge@1.0.1 /tmp/app/node_modules/utils-merge
   vary@1.1.2 /tmp/app/node_modules/vary
   Installing any new modules (package.json + package-lock.json)
   updated 58 packages in 2.141s
   8 packages are looking for funding
   run `npm fund` for details
   -----> Download go 1.19
   -----> Running go build finalize
   /tmp/buildpackdownloads/aab429aae59012ea0725c3d3f6c63937 ~
   ~
   Contrast Security no credentials found. Will not write environment files.
   inside Sealights hook
   service is not configured to run with Sealights

Waiting for app myapp to start...

Instances starting...
Instances starting...
Instances starting...
Instances starting...
Instances starting...
Instances starting...
Instances starting...

name:                myapp
requested state:     started
isolation segment:   trial
routes:              myapp-boring-toucan-pe.cfapps.us10-001.hana.ondemand.com
last uploaded:       Wed 02 Aug 22:01:09 CEST 2023
stack:               cflinuxfs4
buildpacks:
isolation segment:   trial
        name                                                          version   detect output   buildpack name
        https://github.com/cloudfoundry/nodejs-buildpack.git#v1.8.9   1.8.9     nodejs          
nodejs

type:            web
sidecars:
instances:       1/1
memory usage:    128M
start command:   npm start
     state     since                  cpu    memory          disk           logging             
 details
#0   running   2023-08-02T20:01:25Z   0.0%   18.8M of 128M   118.2M of 1G   10B/s of unlimited  

```

cf deploy ...
```
#2.0#2023 08 02 19:54:10.868#Z#DEBUG#com.sap.cloud.lm.sl.xs2.471f4801-316e-11ee-9d50-eeee0a82121c.m1.stageAppTask#
######org.cloudfoundry.multiapps.controller.persistence.services.ProcessLogger########flowable-async-job-executor-thread-14112###
[PollStageAppStatusExecution] [m1] 5d6b88ce-e300-4803-b606-20d6d176156f [2023-08-02T19:48:22.508254] Failed to clone git repository at https://github.com/cloudfoundry/nodejs-buildpack.git (STDERR, STG)#

#2.0#2023 08 02 19:54:10.868#Z#DEBUG#com.sap.cloud.lm.sl.xs2.471f4801-316e-11ee-9d50-eeee0a82121c.m1.stageAppTask#
######org.cloudfoundry.multiapps.controller.persistence.services.ProcessLogger########flowable-async-job-executor-thread-14112###
[PollStageAppStatusExecution] [m1] 5d6b88ce-e300-4803-b606-20d6d176156f [2023-08-02T19:48:22.513266] Exit status 1 (STDOUT, STG)#
```
enable ssh
```
cf enable-ssh myapp
cf restart myapp
cf ssh-enabled myapp
cf ssh myapp

```

<https://docs.cloudfoundry.org/devguide/deploy-apps/ssh-apps.html>

<https://www.ibm.com/docs/en/cloud-private/3.2.x?topic=tap-cloud-foundry-cf-push-command-fails-download-external-buildpacks>

```
ssh to app
cd /tmp
git clone https://github.com/cloudfoundry/nodejs-buildpack.git 
works 

https://github.com/cloudfoundry/nodejs-buildpack.git 

vcap@3f442ced-8e5c-44ca-4e85-70dd:/tmp$ git clone https://github.com/cloudfoundry/nodejs-buildpack.git 
Cloning into 'nodejs-buildpack'...
remote: Enumerating objects: 32155, done.
remote: Counting objects: 100% (1443/1443), done.
remote: Compressing objects: 100% (770/770), done.
remote: Total 32155 (delta 766), reused 1229 (delta 605), pack-reused 30712
Receiving objects: 100% (32155/32155), 88.84 MiB | 1.96 MiB/s, done.
Resolving deltas:  19% (3180/16732)

```
