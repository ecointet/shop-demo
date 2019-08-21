# Fintech Demo
A Cool Website (desktop & mobile) to demonstrate the SignalFx real-time monitoring.
Buy many watches and check your Business & Infrastructure in the same dashboard.

![Main Screen](https://github.com/ecointet/watch-store/blob/master/src/img/screen1.png?raw=true)

![Dashboard Screen](https://github.com/ecointet/watch-store/blob/master/src/img/screen2.png?raw=true)

## Features

- Watches bought from the last 5 minutes
- Watches sold by seconds
- Number of visitors / customers
- CPU / RAM of the Webserver (Nginx)
- Number of requests / seconds
- Simulate buyers / visitors (> 100)
- QR code auto-generated for sharing

## Alerting

- Configure your own SignalFx Detector : Ex: send a slack message if more than 13 watches are sold per seconds.

## Configuration

### STEP 1
`git clone https://github.com/ecointet/watch-store`
*Requirements : git, docker, docker-compose*

### STEP 2

Edit the file `docker-compose.yml` to set your own variables.
           
            - TOKEN=<SIGNALFX-API-TOKEN>
            - HOST=my-webserver
            - REALM=us0
            - BUYMETRIC=ecointet-buy

[Download this dashboard](https://raw.githubusercontent.com/ecointet/watch-store/master/template-dashboard.json) and edit it (search & replace):

- Replace **ecointet-buy** with your own metric (cf **BUYMETRIC** from STEP 2).
- Replace **my-webserver** with your own host (cf **HOST** from STEP 2).

Then import the file/dashboard to your [SignalFx app](app.signalfx.com)


### STEP 3

In the main folder (watch-store), Execute the commande `docker-compose up`

And go to [localhost:8181](http://localhost:8181/?company=Etiennem)

You can change the variable **company name** by your customer name.

### BONUS

- Debug info in the menu "DEBUG"
- Simulate customers & buyers with the button "Simulate Buyers"
- Share the app with the button "Share with people"