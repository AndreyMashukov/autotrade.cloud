# Autotrade.cloud
This is manual for crypto trading bot https://autotrade.cloud

### Shortly about used technologies: 
Golang, Redis, Websocket, MySQL, Docker (+custom deploy system based on Docker API for Golang)


# How does it work? 

Bot has web interface on https://autotrade.cloud where user is able to create own bot instance, get IP of cloud instance and configure his custom trading strategy, then user can deploy instance and start trading

# Configuration 

When user creates first bot instance, personal account page will look like this
<br/>
<br/>
<img src="/images/image_1.png" width="400" title="personal account page">

By clicking "configuration" in right top corner of bot card, user will see bot configuration page, where user can setup trading strategy configuration and API/SECRET keys for Binance API
<br/>
<br/>
<img src="/images/image_2.png" width="600" title="crypto trading strategy configuration">

After any changes user have to press "Start/Restart" to apply changes and re-deploy bot container with new configuration
