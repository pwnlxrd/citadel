![Profile views](https://gpvc.arturio.dev/pwnlxrd)  ![Version](https://img.shields.io/badge/version-1.0-brightgreen)  ![Lines of code](https://img.shields.io/tokei/lines/github/pwnlxrd/citadel)  [![Build Status](https://drone.pwndev.com/api/badges/pwnlxrd/Citadel/status.svg)](https://drone.pwndev.com/pwnlxrd/Citadel)

Citadel - local infrastructure in one docker-compose
===
* step-ca  
   local CA
* traefik  
   load-balance
* prometheus  
  Monitoring system & time series database
* blackbox  
   prober exporter
* alertmanager  
   handles alerts sent by client applications such as the prometheus server
* nodeexporter  
   Exporter for machine metrics
* cadvisor  
   provides container users an understanding of the resource usage and performance characteristics of their running containers
* grafana  
   open source analytics & monitoring solution for every database
* pushgateway  
   exists to allow ephemeral and batch jobs to expose their metrics to prometheus
* gitea-db  
   postgresql database for gitea
* gitea  
   self-hosted git service
* heimdall  
   organise all those links to your most used web sites and web applications in a simple way
* filtron  
   Reverse HTTP proxy to filter requests by different rules
* searx  
   Privacy-respecting metasearch engine
* morty  
   rewrites web pages to exclude malicious HTML tags and attributes
* dev-server-main  
   vs code container from isolated development
* drone-server
   drone ci/cd server
* drone-runner
   drone ci/cd runner