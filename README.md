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
    •
    <a href="https://github.com/JohanScheepers/TTN_Gateway_Notification/issues">Report Bug</a>
    •
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
    <li><a href="#usage">Usage</a> </li> 
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

In this project we are going to call on a TTN API. Namely the <a href="https://mapper.packetbroker.net/api/v2/gateways/netID=000013,tenantID=ttn,id=bb1st-jansmuts-1">TTN Gateway API</a> to get gateway specific data. This API will return the status of the gateway, namely if it is online or offline.


### Built With

* []()Node-Red
* []()node-red-contrib-telegrambot
* []()TTN API




<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps.

### Prerequisites

* Node-Red
  ```sh
  https://nodered.org/docs/getting-started/
  ```

* node-red-contrib-telegrambot
  ```sh
  https://flows.nodered.org/node/node-red-contrib-telegrambot
  ```
### Installation

1. Install Node-Red following the relevant getting started guide for your operating system form the official website
   ```sh
   https://nodered.org/docs/getting-started/
   ```
2. Install npm  package node-red-dashboard
   ```sh
   npm install node-red-contrib-telegrambot
   ```
4. Install the Node-Red flow
   ```sh
https://github.com/JohanScheepers/TTN_Gateway_Notification/blob/main/TTN_Gateway_Notification.json
   ```

5. There is a inject node at the beginning of the flow “Gateway ID”, copy and paste for each of your gateways.

6. In the string field add your gateway “Gateway ID” 
This is in the Node-red flow

<img src="images/injectNode.PNG" alt="Demo" width="450" height="200">

This is from The Things Network console

<img src="images/gatewayId.PNG" alt="Demo" width="450" height="450">

7. Create a Telegram bot https://core.telegram.org/bots#6-botfather
   ```sh
   https://core.telegram.org/bots#6-botfather
   ```

8. Create a new group on telegram and add the bot

9. Add Telegram Bot Raw to the group.

10. In the message that Telegram Bot Raw returns copy the “chat id”

 <img src="images/chatId.PNG" alt="Demo" width="450" height="450">

11. Insert the “chat ID” into the function node “Prep Telegram”

<img src="images/prepTelegram.PNG" alt="Demo" width="450" height="250">

12. In the Telegram Sender node add you bot name and select the pencil

<img src="images/telegramSender.PNG" alt="Demo" width="300" height="250">

13. Add you bot name and the token from Bot Father. Then select update and done

<img src="images/telegramToken.PNG" alt="Demo" width="300" height="250">

14. Deploy your flow.









<!-- USAGE EXAMPLES -->
## Usage

The flow will pole every 6 min the API and if the Gateway is off line, will send a message to telegram notifying you.


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
