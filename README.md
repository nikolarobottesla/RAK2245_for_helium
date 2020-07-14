# Helium LoRa Basics™ Station Gateway using balena.io, Raspberry Pi and RAK2245

This project deploys a Helium LoRa gateway with Basics Station Packet Forward protocol and balena.io. It runs on a Raspberry Pi or balenaFin with a RAK2245 Pi Hat.


## Introduction

Deploy a [Helium](https://www.helium.com/) LoRa gateway running the basics station Semtech Packet Forward protocol. We are using balena.io and RAK to reduce fricition for the LoRa gateway fleet owners.

The Basics Station protocol enables the LoRa gateways with a reliable and secure communication between the gateways and the cloud and it is becoming the standard Packet Forward protocol used by most of the LoRaWAN operators.


## Getting started

### Hardware

* Raspberry Pi 4 or [balenaFin](https://www.balena.io/fin/)
* [RAK 2245 pi hat](https://store.rakwireless.com/products/rak2245-pi-hat)
* SD card in case of the RPi 4

### Software

* A Helium account ([sign up here](https://console.thethingsnetwork.org)
* A balenaCloud account ([sign up here](https://dashboard.balena-cloud.com/)
* [balenaEtcher](https://balena.io/etcher)

Once all of this is ready, you are able to deploy this repository following instructions below.

## Deploy the code

### Via [Balena Deploy](https://www.balena.io/docs/learn/deploy/deploy-with-balena-button/)

Running this project is as simple as deploying it to a balenaCloud application. You can do it in just one click by using the button below:

[![](https://www.balena.io/deploy.png)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/balena-io-playground/RAK2245_for_helium)

Follow instructions, click Add a Device and flash an SD card with that OS image dowloaded from balenaCloud. Enjoy the magic 🌟Over-The-Air🌟!

## Configure the Helium Gateway

### Balena Helium LoRa Basics Station Service Variables

On this Helium gateway version, the gateway is not running the Helium miner. However it's using a RAK Helium miner version meanwhile the miner version is more stable.

Once successfully deployed, configure your board variables on balenaCloud.

1. Go to balenaCloud dashboard and get into your LoRa gateway device site.
2. Click "Device Variables" button on the left menu and add these variables.

Most of the variables have been generated automatically when the Application has been created with the Deploy with Balena button. Find here the variables description in case you need to change them.

Variable Name | Value | Description | Default
------------ | ------------- | ------------- | -------------
**`GW_GPS`** | `STRING` | Enables GPS | true or false
**`GW_RESET_PIN`** | `STRING` | Pin number that resets | 11 
**`SPI_SPEED`** | `STRING` | The Raspberry Pi and RAK2245 uses SPI to communicate and needs to use a specific speed | 20000000
**`TC_URI`** | `STRING` | basics station TC URI to get connected | ```ws://x2he.net:6090```


At this moment your Helium gateway should be up and running. Check on the Logs console if it shows the connected status.


## Attribution

- This is an adaptation of the [Semtech Basics Station repository](https://github.com/lorabasics/basicstation). Documentation [here](https://doc.sm.tc/station).
- This is in part working thanks of the work of Jose Marcelino from RAK Wireless and Marc Pous from balena.io.
- This is in part based on excellent work done by the Balena.io Hardware Hackers team.
