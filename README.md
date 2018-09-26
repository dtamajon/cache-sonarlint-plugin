# Caché Studio plugin for sonarlint-ci

A plugin to use sonarlint-cli in Caché Studio, to allow analyze your caché code locally.


## Requeriments
- You need the cachéQuality plugin, which can be downloaded from 
https://www.cachequality.com/downloads

- If you decide to download cachéQuality for Caché Studio, follow the steps 
described next to the downloaded file. If you download just the cachéQuality plugin,
follow this steps.

- Download sonarlint-cli from https://github.com/litesolutions/sonarlint-cli

- Copy the sonarlint folder to the <caché_studio_root>/bin folder.

- Copy the cachéQuality plugin to the <caché_studio_root>/plugins folder.


## Installation
- From Caché Studio, import the file %ZStudio.SourceControl.cls. After the import 
you must compile the file and close Caché Studio.

- Open Management Portal, and navigate to 
  Home > System Administration > Configuration > Additional Settings > Source Control.
  
- On the left panel, select the namespace in which you imported the 
%ZStudio.SourceControl.cls file in Caché Studio. On the right side, select the 
file %ZStudio.SourceControl.cls and save.

- To check the plugin is properly installed, open the namespace in which you installed 
the plugin on Caché Studio.

- Now, compile any file from your namespace. In the log panel you will see the results 
of the source analysis for that file.

## Connected mode
The plugin can be configured to use Connected mode. In this case, rules will be synchronized from your SonarQube server.
```
Set ^SonarLint("url")="http://sonarqube.your.org:9000"
Set ^SonarLint("projectKey")="ProjectName"
```
Then you have to specify either token
```
Set ^SonarLint("token")="yoursonarqubetoken"
```
 or login/password
```
Set ^SonarLint("login")="login"
Set ^SonarLint("password")="password"
```