# SK-PLAYGROUND -- testbed for plugins

... why ...

## Setup
1. clone repo
2. install signalk-server (published), unit-under-test plugin (from local folder)
3. `npm install`
4. `./node_modules/.bin/signalk-server-setup`

```
Please run as root if you want this server configuration to run at every startup, type: "sudo signalk-server-setup"

? Are you sure you want to continue Yes
? Enter the location to store server configuration: ./server-config
? Do you want to update the existing configuration or start from scratch Start from scratch
? Enter your vessel name: SK-Playground-Vessel
? Enter your mmsi if you have one:
? Do you want to enable SSL? Yes
  ✔ Creating your server base deltas at server-config/baseDeltas.json
  ✔ Creating your server settings at server-config/settings.json
  ✔ Creating package.json
  ✔ Creating your server startup script at server-config/signalk-server
bobhy@Jessie-PC-wsl:~/src/sk/sk-playground$ ll server-config/
total 36
drwxr-xr-x 3 bobhy bobhy 4096 Dec 13 11:09 ./
drwxr-xr-x 5 bobhy bobhy 4096 Dec 13 11:16 ../
-rw-r--r-- 1 bobhy bobhy   19 Dec 13 10:44 .npmrc
-rw-r--r-- 1 bobhy bobhy  324 Dec 13 11:22 baseDeltas.json
-rw-r--r-- 1 bobhy bobhy  186 Dec 13 11:22 package.json
drwxr-xr-x 2 bobhy bobhy 4096 Dec 13 10:44 plugin-config-data/
-rw------- 1 bobhy bobhy  873 Dec 13 11:09 security.json
-rw-r--r-- 1 bobhy bobhy  116 Dec 13 11:22 settings.json
-rwxr-xr-x 1 bobhy bobhy   84 Dec 13 11:22 signalk-server*
bobhy@Jessie-PC-wsl:~/src/sk/sk-playground$
```

5. `./node_modules/.bin/signalk-generate-token -u root -e 1y -s server-config/security.json`