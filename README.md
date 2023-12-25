# Autotrade.cloud
This is manual for crypto trading bot https://autotrade.cloud

### Shortly about used technologies: 
Golang, Redis, Websocket, MySQL, Docker (+custom deploy system based on Docker API for Golang), Testify (for Unit testing)


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

* SYMBOL - cruptocurrency pair to trade with
* USDT limit - USDT amount for first buy transaction, bot will use unli this USDT amount to buy assen, quantity will be caclulated (usdt * price = asset quantity)
* Min profit percent - minimum profit percent to sell bought asset, for example position price is 100usdt, min profit 2.5% it means that bot will sell asset not less than 102.5usdt
* Extra charge trigger percent - if profit is negative and bit has budget for extra charge, bot will buy more asset to make average price less
* USDT budget for extra charge - budget for extra charge transaction (same like USDT limit but for extra charge), set to 0 extra charge percent or budget to disable extra buy transactions

New options available from 26 Dec 2023
<br/>
<img src="/images/image_3.png" width="600" title="New options for buy strategy setup">
<br/>

* Min price minutes period - amount of 1m (1 minute) klines to find minimum price value (bot will never buy anything above this value)
<img src="/images/image_4.png" width="600" title="Minimum price minutes period">

* Trading frame interval - interval for trading frame detection
* Trading frame period - period for trading frame detection

<img src="/images/image_5.png" width="600" title="Trading frame detection">

* Buy price history check interval - interval for buy price history validation 
* Buy price history check period - period for buy price history validation
<img src="/images/image_6.png" width="600" title="Buy price history check">

### How does work buy history check???
When bot calculates buy price it try to answer the question: "Can I sell with required minimum profit if buy this price?", if bot will not be able to sell required price, bot will move down buy price and try to answer this question again, until buy price will not be optimum 
