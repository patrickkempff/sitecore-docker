# docker-sitecore container

An out-of-the-box Sitecore website using Docker. The easiest way it to use docker-compose (yaml file included) to create a container for each of it's dependencies (asp.net, mssql server and mongodb).

**_Please note; this is work in progress and is not intended to use in production!_**

## Installation

### With docker-compose

First clone the repo:

	git clone git@github.com:Redhotminute/docker-sitecore

* [Download the Sitecore distribution](https://dev.sitecore.net/Downloads/Sitecore_Experience_Platform/82/Sitecore_Experience_Platform_82_Update2.aspx) (developer account needed)
* Unzip and copy the Sitecore files into the sitecore folder.
* Copy your license.xml into sitecore/Data
* Copy web/ConnectionString.config into Sitecore/Website/App_Config
* Copy web/z.DockerConfig.config into Sitecore/Website/App_Config/Include

## Usage
Run docker-compose in your cli:

	docker-compose up
	

Docker-compose will start 3 (micro)services:

1. **web** --> asp.net IIS container
2. **mssql** --> MSSQL Server 2016 Express container
3. **mongodb** --> MongoDB container

