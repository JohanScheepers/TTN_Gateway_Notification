<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/JohanScheepers/TTN_Gateway_Notification">
    <img src="images/SIGNALOWL.jpg" alt="Logo" width="160" height="80">
  </a>

  <h3 align="center">TTN Gateway Radius and New Node</h3>

  <p align="center">
    Project is aimed to use the TTN API to plot gateways and location of potential new node on map
    <br />
    <a href="https://github.com/JohanScheepers/TTN_Gateway_Notification"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/JohanScheepers/TTN_Gateway_Notification/blob/main/images/gatewayRadius.gif">View Demo</a>
    ·
    <a href="https://github.com/JohanScheepers/TTN_Gateway_Notification/issues">Report Bug</a>
    ·
    <a href="https://github.com/JohanScheepers/TTN_Gateway_Notification/issues">Request Feature</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li>
	<a href="#usage">Usage</a>
	<ul>
        <li><a href="#gateway-within-radius">Gateway within Radius</a></li>
        <li><a href="#radius-around-gateway">Radius around Gateway</a></li>
        <li><a href="#plot-new-node">Plot New Node</a></li>
	   <li><a href="#airtime-calculator-for-loRaWAN">Airtime calculator for LoRaWAN</a></li>
	   <li><a href="#the-things-network-status-page">The Things Network Status Page</a></li>
        <li><a href="#demo">Demo</a></li>
        <li><a href="#flow">Flow</a></li>
      </ul>
    </li> 
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

In this project we are going to call on two TTN API. Namely the <a href="https://mapper.packetbroker.net/api/v2/gateways?distanceWithin[latitude]=52.3676&distanceWithin[longitude]=4.9041&distanceWithin[distance]=7500&netID=000013&tenantID=ttn">TTN Radius API</a> to get the gateways within a certain radius form a GPS coordinate and the <a href="https://mapper.packetbroker.net/api/v2/gateways/netID=000013,tenantID=ttn,id=bb1st-jansmuts-1">TTN Gateway API</a> to get gateway specific data. These two API will plot the gateway on the map, including their status information. Bear in mind these API are rate limited.



`TTN_Gateway_Node`


### Built With

* []()Node-Red
* []()node-red-dashboard
* []()node-red-contrib-web-worldmap
* []()TTN API




<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites

* Node-Red
  ```sh
  https://nodered.org/docs/getting-started/
  ```

* node-red-dashboard
  ```sh
  https://flows.nodered.org/node/node-red-dashboard
  ```

* node-red-contrib-web-worldmap
  ```sh
  https://flows.nodered.org/node/node-red-contrib-web-worldmap
  ```




### Installation

1. Install Node-Red following the relevant getting started guide for your operating system form the official website
   ```sh
   https://nodered.org/docs/getting-started/
   ```
2. Install npm  package node-red-dashboard
   ```sh
   npm install node-red-dashboard
   ```
3. Install npm  node-red-contrib-web-worldmap
   ```sh
   npm install node-red-contrib-web-worldmap
   ```
4. Install the Node-Red flow
   ```sh
   https://github.com/JohanScheepers/TTN_Gateway_-Notification-/blob/master/flow/TTN_Gateway_Radius.json
   ```





<!-- USAGE EXAMPLES -->
## Usage

There are three user interfacing areas, Gateway within Radius, Radius around Gateway and Plot New Node.

### Gateway within Radius

Here the user have three fields to complete, Latitude dec, Longitude dec and Distance KM, once these are completed the ‘Get’ is used. This calls on the TTN Radius API to get all the Gateways within the specified radius from the coordinates supplied. The Latitude dec, Longitude dec are in decimal format and Distance KM is in kilometres.

This in turn calls on the TTN Gateway API that returns data more specific to the gateway. This triggers a flow that map the gateways on a map.

There are several fields of data about the gateway, we are only going  to display the following fields in tables, 'name', 'eui', 'latitude', 'longitude', 'rxRate', 'txRate', 'updateAt' and 'onlin'e.

There are two tables, Gateway Status Offline and Gateway Status Online. These tables display all the offline and online gateways, each field is selectable. If the field is selected the map zooms to that specific gateway.

### Radius around Gateway

Here we can set four different radiuses plotted around the gateways, this in in kilometres. Complete the distance and the radius will be plotted on the map.

The clear these radiuses, either select CLEAR RADIUS or change the field value to 0.

### Plot New Node

Here we set the Latitude dec, Longitude dec and the Distance KM. The fields Latitude dec, Longitude dec are in in decimal format and Distance KM are in kilometres.

You simply complete the coordinates and the point will be plotted on the map. If you require a radius drawn around the point you complete the Distance KM.

This invokes a flow that generates the table "Distance Node to Gateway". In this table we are displaying attributes of the gateway, like 'name', 'eui', 'latitude', 'longitude", there are two other fields of interest here. 'distance KM' and 'azimuth' this is the distance from the node to the gateway and the azimuth from the node to the gateway.

The delete the point from the map you press the DELETE button.

### Airtime calculator for LoRaWAN

This is a call to the website of arjanvanb - 'https://avbentem.github.io/airtime-calculator/ttn/eu868/10' this is a calculator to assist you to see the relationship between your payload length and SF value have on the airtime of your uplink or downlink.

### The Things Network Status Page

This is a call the The Things Network Status Page, showing some of the gateway statistic and other useful information.

### Demo
 
<img src="images/gatewayRadius.gif" alt="Demo" width="900" height="450">


### Flow

<img src="images/flow.png" alt="Demo" width="900" height="450">




<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/JohanScheepers/TTN_Gateway_Notification/issues) for a list of proposed features (and known issues).



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact


Project Link: [https://github.com/JohanScheepers/TTN_Gateway_Notification](https://github.com/JohanScheepers/TTN_Gateway_Node)






<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[forks-shield]: https://img.shields.io/github/forks/JohanScheepers/repo.svg?style=for-the-badge
[forks-url]: https://github.com/JohanScheepers/repo/network/members
[stars-shield]: https://img.shields.io/github/stars/JohanScheepers/repo.svg?style=for-the-badge
[stars-url]:https://github.com/JohanScheepers/TTN_Gateway_Notification/stargazers
[issues-shield]: https://img.shields.io/github/issues/JohanScheepers/repo.svg?style=for-the-badge
[issues-url]: https://github.com/JohanScheepers/repo/issues
[license-shield]: https://img.shields.io/github/license/JohanScheepers/repo.svg?style=for-the-badge
[license-url]: https://github.com/JohanScheepers/repo/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/johan-scheepers-6a263514a/
