<?xml version="1.0" encoding="UTF-8"?>
<bot_config>
    <bot>
        <name>Binary Over/Under Bot</name>
        <description>Bot that trades binary options on Deriv with Over/Under strategy</description>
        
        <trade_conditions>
            <!-- Trade Condition 1: RSI indicator strategy -->
            <condition>
                <name>RSI Overbought Strategy</name>
                <indicator>RSI</indicator>
                <value>70</value>
                <trade_type>Under</trade_type>
                <logic>greater_than</logic>
                <timeframe>5</timeframe> <!-- timeframe in minutes -->
                <risk_level>medium</risk_level>
            </condition>

            <condition>
                <name>RSI Oversold Strategy</name>
                <indicator>RSI</indicator>
                <value>30</value>
                <trade_type>Over</trade_type>
                <logic>less_than</logic>
                <timeframe>5</timeframe>
                <risk_level>medium</risk_level>
            </condition>

            <!-- Trade Condition 2: Moving Average Cross -->
            <condition>
                <name>MA Cross Over Strategy</name>
                <indicator>MovingAverage</indicator>
                <value>20</value> <!-- Short period moving average -->
                <trade_type>Over</trade_type>
                <logic>crosses_above</logic>
                <timeframe>5</timeframe>
                <risk_level>high</risk_level>
            </condition>

            <condition>
                <name>MA Cross Under Strategy</name>
                <indicator>MovingAverage</indicator>
                <value>50</value> <!-- Long period moving average -->
                <trade_type>Under</trade_type>
                <logic>crosses_below</logic>
                <timeframe>5</timeframe>
                <risk_level>high</risk_level>
            </condition>

            <!-- Additional condition for minimizing losses -->
            <condition>
                <name>Loss Limit Strategy</name>
                <logic>total_loss_less_than</logic>
                <value>50</value> <!-- Total loss amount, for example -->
                <action>stop_trading</action>
                <timeframe>10</timeframe> <!-- check every 10 minutes -->
            </condition>
        </trade_conditions>

        <risk_management>
            <!-- Risk management settings -->
            <max_loss_per_trade>5</max_loss_per_trade> <!-- Risk per trade -->
            <max_consecutive_losses>3</max_consecutive_losses> <!-- Stop after 3 consecutive losses -->
            <max_daily_loss>50</max_daily_loss> <!-- Stop trading after reaching a daily loss limit -->
            <trade_size>10</trade_size> <!-- Amount to trade -->
        </risk_management>

        <execution>
            <platform>Deriv</platform> <!-- Trading platform -->
            <api_key>Your_API_Key_Here</api_key> <!-- API Key for automated trading -->
            <timeout>30</timeout> <!-- Timeout for trading actions -->
        </execution>

    </bot>


    </bot>
</bot_config>
