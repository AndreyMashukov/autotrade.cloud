# Autotrade.cloud

This is a manual for the crypto trading bot [Autotrade.cloud](https://autotrade.cloud).

### Brief Overview of Technologies Used: 
- **Golang**: For robust backend development.
- **Redis**: Efficient in-memory data store used for caching.
- **Websocket**: For real-time data communication.
- **MySQL**: Reliable database management system.
- **Docker**: Ensures easy deployment and scalability (+custom deploy system based on Docker API for Golang).
- **Testify**: Utilized for unit testing.

## How Does It Work?

Autotrade.cloud features a web interface where users can create their own bot instance, obtain the IP of the cloud instance, and configure their custom trading strategy. After configuration, users can deploy the instance and start trading.

## Configuration

Upon creating the first bot instance, the personal account page will appear as shown below:

![Personal Account Page](/images/image_1.png "Personal Account Page")

By clicking "configuration" in the top right corner of the bot card, users will be directed to the bot configuration page. Here, users can set up their trading strategy configuration and enter their Binance API/SECRET keys.

![Crypto Trading Strategy Configuration](/images/image_2.png "Crypto Trading Strategy Configuration")

After making any changes, users must press "Start/Restart" to apply the changes and re-deploy the bot container with the new configuration.

### Key Configuration Parameters:
- **SYMBOL**: Cryptocurrency pair to trade.
- **USDT Limit**: The USDT amount for the first buy transaction. The bot uses this amount to buy assets, with the quantity calculated as (usdt * price = asset quantity).
- **Min Profit Percent**: The minimum profit percentage for selling the bought asset. For example, if the position price is 100 USDT and the minimum profit is 2.5%, the bot will sell the asset for no less than 102.5 USDT.
- **Extra Charge Trigger Percent**: If the profit is negative and the bot has a budget for extra charge, it will buy more assets to reduce the average price.
- **USDT Budget for Extra Charge**: The budget for extra charge transactions (similar to USDT Limit but specifically for extra charges). Set to 0 to disable extra buy transactions.

### New Options Available from 26 Dec 2023:
![New Options for Buy Strategy Setup](/images/image_3.png "New Options for Buy Strategy Setup")

- **Min Price Minutes Period**: The amount of 1-minute Klines to determine the minimum price value (the bot will never buy above this value).
  ![Minimum Price Minutes Period](/images/image_4.png "Minimum Price Minutes Period")

- **Trading Frame Interval and Period**: Settings for detecting the trading frame.
  ![Trading Frame Detection](/images/image_5.png "Trading Frame Detection")

- **Buy Price History Check Interval and Period**: Intervals for validating the buy price history.
  ![Buy Price History Check](/images/image_6.png "Buy Price History Check")

### How Does the Buy History Check Work?
When calculating the buy price, the bot assesses whether it can sell the asset with the required minimum profit at this price. If the bot cannot sell at the required price, it will lower the buy price and reassess until it finds the optimum buy price.


# Frequently Asked Questions (FAQ)

1. **What is Autotrade.cloud?**
   Autotrade.cloud is an automated cryptocurrency trading bot that allows users to configure and deploy their own trading strategies on cloud instances.

2. **How do I start using Autotrade.cloud?**
   To start using the bot, visit https://autotrade.cloud, create your bot instance, configure your trading strategy, and deploy the instance to start trading.

3. **What technologies are used in Autotrade.cloud?**
   The bot is built using Golang, Redis, Websocket, MySQL, Docker, and Testify for unit testing.

4. **Do I need coding skills to use Autotrade.cloud?**
   No, you don't need coding skills. The bot offers a user-friendly web interface for configuring and managing your trading strategies.

5. **What exchanges does Autotrade.cloud support?**
   Currently, Autotrade.cloud supports Binance. You will need to provide your API and SECRET keys from Binance to trade.

6. **Is my investment safe with Autotrade.cloud?**
   While Autotrade.cloud provides tools for automated trading, all trading involves risk. It's important to understand the risks before trading.

7. **How can I optimize my trading strategy?**
   Autotrade.cloud offers various parameters like 'Min Price Minutes Period', 'Trading Frame Interval', and 'Buy Price History Check' to optimize your strategy.

8. **What is the 'Min Price Minutes Period'?**
   This feature allows the bot to determine the minimum price for a trade based on a specified number of 1-minute Klines.

9. **How does the 'Buy Price History Check' work?**
    This feature helps the bot decide if a potential buy price will allow for selling the asset at a required minimum profit. If not, the bot adjusts the buy price accordingly.

10. **Can I use Autotrade.cloud on multiple devices?**
    Yes, you can access your Autotrade.cloud account on multiple devices through the web interface.

11. **Are there any subscription fees or hidden costs?**
    Autotrade.cloud charges a subscription fee for using the bot. There are no hidden costs. All pricing details are transparently provided on the website.

12. **How often can I change my trading strategy?**
    You can modify your trading strategy as often as you like. Remember to restart your bot for the changes to take effect.

13. **What kind of customer support does Autotrade.cloud offer?**
    Autotrade.cloud provides customer support through email and a dedicated Telegram group.

14. **Can I track my trading performance?**
    Yes, Autotrade.cloud provides detailed reports and analytics to track your trading performance.

15. **Is there a limit to the number of trades I can make?**
    There is no limit to the number of trades. Your trading frequency will depend on your configured strategy and market conditions.

16. **How do I withdraw my profits?**
    Profits are managed through your linked exchange account. You can withdraw your profits according to the exchange's withdrawal process.

17. **Can I use Autotrade.cloud in my country?**
    Autotrade.cloud is available in most countries. However, it's important to check if your country allows cryptocurrency trading.

18. **What happens if I lose my internet connection?**
    Your trading bot runs on cloud instances, so it will continue trading even if you lose your internet connection.

19. **Can I cancel my subscription at any time?**
    Yes, you can cancel your subscription at any time through your account settings.

20. **Where can I find more information about setting up my bot?**
    Detailed setup instructions are available in the [Documentation](https://github.com/AndreyMashukov/autotrade.cloud/blob/main/README.md) section on GitHub.

For more detailed information, please visit our [Documentation](https://github.com/AndreyMashukov/autotrade.cloud/blob/main/README.md).

## Join Our Community
Stay updated and connect with fellow traders by joining our Telegram group: [Autotrade.cloud Telegram Group](https://t.me/autotrade_cloud). Here, you can find the latest news, updates, and exclusive offers!

