vossibility
---------------------

Vossibility provides better visibility for your open source project. The project was initially
started for [Docker](https://docker.io) but is not tied to it in any way.

This repository provides a usable stack to get started using `docker-compose`.

## Components

 Repository | Description
 -----------|--------------------------------------------------------------------------------------
 [`vossibility-collector`](https://github.com/icecrime/vossibility-collector) | Collect GitHub data and stores to Elastic Search
 [`vossibility-bulletin`](https://github.com/icecrime/vossibility-bulletin)   | Generate reports from vossibility data *(work in progress)*

## Sample dashboard

![Sample dashboard](https://github.com/icecrime/vossibility-collector/raw/master/resources/dashboard.png)

## Getting started

First, you want to retrieve the submodules:
``` sh
$> git submodule update --init # clone vossibility-collector into collector
```
You want to copy the example config.toml file to the right location:
``` sh
$> cp collector/examples/config.toml.examples collector/src/cmd/vossibility-collector/
```
Then you want to start the containers:
``` sh
$> docker-compose build
$> docker-compose up 
```
You now have a docker instance running. Kibana should give you data when
something happens on your repository provided that your nsq channel and topic
exist.

