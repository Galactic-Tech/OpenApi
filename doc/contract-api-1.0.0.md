# Base Url
The base url

Name | base endpoint
------------ | ------------
行情 Websocket |wss://exwarehousetest.trubit.com/market
Rest-api | https://exwarehousetest.trubit.com/api/v1

# Contract Public Endpoint

## `Exchange time`

Exchange server time

### **Request Weight:**

Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ----

### **Request Url:**
```bash
GET /basic/time
```

### **Parameters：**

Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ----
------------ | ------------ | ------------ | ------------ | ----
### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`timezone`|string|`UTC`|Timestamp
`serverTime`|long|`1685004422191`|Return the current server timestamp (ms)
`formatServerTime`|string|`2023-05-25 16:47:02.191`|Return the current server format time
    
```json
{
  "code": 0,
  "message": "OK",
  "result": {
    "serverTime": 1685004422191,
    "formatServerTime": "2023-05-25 16:47:02.191"
  }
}
```

## `Exchange info`

Exchange trading rules and symbol information

### **Request Weight:**

0

### **Request Url:**
```bash
GET /basic/exchangeInfo
```

### **Parameters：**

Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ----
------------ | ------------ | ------------ | ------------ | ----

### **Response:**

In the `contracts` field:
All information about current contract positions by the exchange will be displayed.

Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`symbol`|string|`XRPUSDT`|Contract name
`desc`|string|`XRP Perpetual`|Contract desc
`enabled`|string|`true`|Contract status
`sim`|string|`false`|Simulation contract
`lotSize`|float|`1`| 最小数量间隔
`minQty`|float|`1`|Minimum quantity allowed
`qtyDecimal`|float|`0`|Precision of the contract quantity
`priceDecimal`|float|`5`|Precision of the contract price
`tick`|float|`0.00001`|最小价格间隔
`fxCurrency`|string|`USDT`|Quote asset. For the contract, it means by which currency the contract is quoted.

In the `riskLimitSettings` filed:

Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`riskValue`|double|`2000000`| The limitation of position amount based on the following requirement
`maintenanceMarginRate`|float|`0.1`|Maintenance margin rate
`maxLeverage`|float|`10`|Minimum maintenance margin rate required

```json
{
  "code": 0,
  "message": "OK",
  "result": [
    {
      "symbol": "TBTCTUSDT",
      "tick": 1.0,
      "lotSize": 1.0,
      "desc": "TBTC Perpetual Sim",
      "minQty": 1.0,
      "fxCurrency": "TUSDT",
      "qtyDecimal": 0,
      "priceDecimal": 0,
      "riskLimitSettings": [
        {
          "riskValue": 2.0E7,
          "maintenanceMarginRate": 0.049,
          "maxLeverage": 10.0
        },
        {
          "riskValue": 1.0E7,
          "maintenanceMarginRate": 0.024,
          "maxLeverage": 20.0
        },
        {
          "riskValue": 2000000.0,
          "maintenanceMarginRate": 0.0095,
          "maxLeverage": 50.0
        },
        {
          "riskValue": 1000000.0,
          "maintenanceMarginRate": 0.005,
          "maxLeverage": 100.0
        },
        {
          "riskValue": 100000.0,
          "maintenanceMarginRate": 0.004,
          "maxLeverage": 125.0
        }
      ],
      "enabled": true,
      "sim": true
    },
    {
      "symbol": "BTCUSDT",
      "tick": 0.1,
      "lotSize": 1.0,
      "desc": "BTC Perpetual",
      "minQty": 1.0,
      "fxCurrency": "USDT",
      "qtyDecimal": 0,
      "priceDecimal": 1,
      "riskLimitSettings": [
        {
          "riskValue": 2.0E7,
          "maintenanceMarginRate": 0.049,
          "maxLeverage": 10.0
        },
        {
          "riskValue": 1.0E7,
          "maintenanceMarginRate": 0.024,
          "maxLeverage": 20.0
        },
        {
          "riskValue": 2000000.0,
          "maintenanceMarginRate": 0.0095,
          "maxLeverage": 50.0
        },
        {
          "riskValue": 1000000.0,
          "maintenanceMarginRate": 0.005,
          "maxLeverage": 100.0
        },
        {
          "riskValue": 100000.0,
          "maintenanceMarginRate": 0.004,
          "maxLeverage": 125.0
        }
      ],
      "enabled": true,
      "sim": false
    },
    {
      "symbol": "ETHUSDT",
      "tick": 0.05,
      "lotSize": 1.0,
      "desc": "ETH Perpetual",
      "minQty": 1.0,
      "fxCurrency": "USDT",
      "qtyDecimal": 0,
      "priceDecimal": 2,
      "riskLimitSettings": [
        {
          "riskValue": 1.0E7,
          "maintenanceMarginRate": 0.044,
          "maxLeverage": 1.0
        },
        {
          "riskValue": 7500000.0,
          "maintenanceMarginRate": 0.035,
          "maxLeverage": 2.0
        },
        {
          "riskValue": 6000000.0,
          "maintenanceMarginRate": 0.03,
          "maxLeverage": 4.0
        },
        {
          "riskValue": 5000000.0,
          "maintenanceMarginRate": 0.027,
          "maxLeverage": 5.0
        },
        {
          "riskValue": 4000000.0,
          "maintenanceMarginRate": 0.022,
          "maxLeverage": 10.0
        },
        {
          "riskValue": 3000000.0,
          "maintenanceMarginRate": 0.019,
          "maxLeverage": 20.0
        },
        {
          "riskValue": 2500000.0,
          "maintenanceMarginRate": 0.0145,
          "maxLeverage": 25.0
        },
        {
          "riskValue": 1500000.0,
          "maintenanceMarginRate": 0.01,
          "maxLeverage": 50.0
        },
        {
          "riskValue": 1000000.0,
          "maintenanceMarginRate": 0.0085,
          "maxLeverage": 75.0
        },
        {
          "riskValue": 500000.0,
          "maintenanceMarginRate": 0.005,
          "maxLeverage": 100.0
        },
        {
          "riskValue": 50000.0,
          "maintenanceMarginRate": 0.004,
          "maxLeverage": 125.0
        }
      ],
      "enabled": true,
      "sim": false
    },
    {
      "symbol": "XRPUSDT",
      "tick": 1.0E-5,
      "lotSize": 1.0,
      "desc": "XRP Perpetual",
      "minQty": 1.0,
      "fxCurrency": "USDT",
      "qtyDecimal": 0,
      "priceDecimal": 5,
      "riskLimitSettings": [
        {
          "riskValue": 1500000.0,
          "maintenanceMarginRate": 0.04,
          "maxLeverage": 5.0
        },
        {
          "riskValue": 500000.0,
          "maintenanceMarginRate": 0.025,
          "maxLeverage": 10.0
        },
        {
          "riskValue": 300000.0,
          "maintenanceMarginRate": 0.015,
          "maxLeverage": 25.0
        },
        {
          "riskValue": 50000.0,
          "maintenanceMarginRate": 0.0095,
          "maxLeverage": 50.0
        }
      ],
      "enabled": true,
      "sim": false
    }
  ]
}
```

## `Index`

Index price of underlying asset 

### **Request Weight:**
0

### **Request Url:**
```bash
GET /contract/index
```
### **Parameters：**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ----
symbol|string|`NO`||The index symbol of underlying. If this parameter is not sent, all index symbols will be returned.

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`index`|float|`8342.73`|The index price of the underlying
`EDP`|float|`8432.32`|The index EDP (estimated delivery price) of underlying. The average price of the index in the last 10 minutes. This will be the price when the contract is going to be settled.

### **Example:**
```js
{
  "index":{
    "BTCUSDT":"8243.21666667",
    "OKBUSDT":"1.482",
    "BNBUSDT":"31.2658",
    "HTUSDT":"3.1209",...
    },
  "edp":{
    "BTCUSDT":"8258.98505556",
    "OKBUSDT":"1.48578333",
    "BNBUSDT":"31.48741917",
    "HTUSDT":"3.14308",...
  }
}
```

## `fundingRate`

Get current funding rate (*historical under construction*)

### **Request Weight:**
0

### **Request Url:**
```bash
GET /openapi/contract/v1/fundingRate
```

### **Parameters：**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ----
`symbol`|string|`NO`||The contract symbol. If not sent, records for all symbols will be returned as the result.
`state`|string|`NO`|`current`|Get `current` or `past` funding rate.
`from`|long|`NO`||Timestamp to start
`to`|long|`NO`||Timestamp to end
`limit`|integer|`NO`|`20`| The number of entries returned

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`symbol`|string|`BTCUSD`|The contract symbol
`intervalStart`|long|`1554710400000`|Timestamp when the interval start
`intervalEnd`|long|`1554710400000`|Timestamp when the interval end
`rate`|float|`0.00321`|The funding rate of this interval
`index`|float|`10076.34`|Index price at the time of settlement

### **Example:**

```js
[
  {
    'symbol': 'BTC-PERP-REV',
    'intervalStart': '1570708800000',
    'intervalEnd': '1570737600000',
    'rate': '-0.000048567445464006'
  },...
]
```

## `depth`

Retrieve the contracts order book.


### **Request Weight:**

Adjusted based on the limit:

Limit|Weight
------------ | ------------
5, 10, 20, 50, 100|1
500|5
1000|10


### **Request Url:**
```
GET /openapi/quote/v1/contract/depth
```

### **Parameters:**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | -----
`symbol`|string|`YES`||The contract symbol to be retrieved
`limit`|integer|`NO`|`100` (max = 100)|The number of entries returned for bids and asks

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`time`|long|`1550829103981`|Current timestamp (ms)
`bids`|list|(see below)|List of all bids details, best bids first. 
`asks`|list|(see below)|List of all asks details, best asks first. 

The fields `bids` and `asks` are lists of orderbook price level entries, sorted from best to worst.

Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`''`|float|`123.10`|price level
`''`|float|`300`|The total quantity of orders for this price level

### **Example:**

```js
{
  "time": 1555049455783,
  "bids": [
   ["78.82", "0.526"],//[Price, Quantity]
   ["77.24", "1.22"],
   ["76.65", "1.043"],
   ["76.58", "1.34"],
   ["75.67", "1.52"],
   ["75.12", "0.635"],
   ["75.02", "0.72"],
   ["75.01", "0.672"],
   ["73.73", "1.282"],
   ["73.58", "1.116"],
   ["73.45", "0.471"],
   ["73.44", "0.483"],
   ["72.32", "0.383"],
   ["72.26", "1.283"],
   ["72.11", "0.703"],
   ["70.61", "0.454"]],
   "asks": [
     ["122.96", "0.381"],//[Price, Quantity]
     ["144.46", "1"],
     ["155.55", "0.065"],
     ["160.16", "0.052"],
     ["200", "0.775"],
     ["249", "0.17"],
     ["250", "1"],
     ["300", "1"],
     ["400", "1"],
     ["499", "1"]]
   }

```

## `trades`

Retrieve the latest trades that have occurred for a specific contract.

### **Request Weight:**

1

### **Request URL:**
```
GET /openapi/quote/v1/contract/trades
```
### **Parameters：**
Parameter|type|required|default|description
------------ | ------------ | ------------ | ------------ | ------
`symbol`|string|`YES`||The contract symbol
`limit`|integer|`NO` (clamped to max 1000)|`100`|The number of filled trades returned

### **Response:**

Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`price`|float|`0.055`|Trade price
`time`|long|`1537797044116`|Current timestamp (ms)
`qty`|float|`5`|The quantity traded
`isBuyerMaker`|string|`true`|Maker or taker of the trade. `true`= maker, `false` = taker


### **Example:**
```js
[
  {
    "price": "1.21",
    "time": 1555034474064,
    "qty": "0.725",
    "isBuyerMaker": False
  },...
]
```

## `klines`

Retrieves the kline information (open, high, low, trade volume, etc.) for a specific contract.

### **Request Weight:**

1

### **Request URL:**
```
GET /openapi/quote/v1/contract/klines
```

### **Parameters：**
| Name|Type|Required|Default|Description |
| ------------ | ------------ | ------------ | ------------ | ---- |
|`symbol`|string|`YES`||The contract symbol.|
|`interval`|string|`YES`||Interval of the kline. Identifiable values: `1m`,`5m`,`15m`,`30m`,`1h`,`1d`,`1w`,`1M`|
|`limit`|integer|`NO`|`1000`|The maxium number of entries returned is 1000.|
|`to`|integer|`NO`||timestamp of the last datapoint|

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`''`|long|`1538728740000`|Open timestamp
`''`|float|`36.00000`|Open
`''`|float|`36.00000`|High
`''`|float|`36.00000`|Low
`''`|float|`36.00000`|Close
`''`|float|`148976.11427815`|Trade amount
`''`|long|`1538728740000`|Close timestamp
`''`|float|`2434.19055334`|Quote asset amount
`''`|integer|`308`|The number of filled trades
`''`|float|`1756.87402397`|Taker buy base asset amount
`''`|float|`28.46694368`|Taker buy quote asset amount


### **Example:**
```js
[
  [
    1538728740000, //Open timestamp
    "36.000000000000000000", //open
    "36.000000000000000000", //high
    "36.000000000000000000", //low
    "36.000000000000000000", //close
    "148976.11427815",  // Trade amount
    1499644799999,      // Close timestamp
    "2434.19055334",    // Quote asset amount
    308,                // The number of filled trades
    "1756.87402397",    // Taker buy base asset amount
    "28.46694368"       // Taker buy quote asset amount
  ],...
]
```

# Private Endpoints

## `Order`

Places order for a contract. This API endpoint requires your request signed.

### **Request Weight:**

Speed limit: 20 times /1s Speed limit rule: apiKey

### **Request URL:**
```bash
POST /trade/api/trade/enterOrder
```

### **Parameters：**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ------------
`symbol`|string|`YES`|`--`|The contract symbol, eg: BTCUSDT
`side`|string|`YES`|`--`|Direction of the order. Direction type: `Buy`, `Sell`
`orderType`|string|`YES`|`--`|The order type, includes: `LIMIT`, `Market`
`currency `|string|`YES`|`--`|Currency of account, eg: BTC, ETH, USDT
`qty`|double|`YES`|`0`|The number of contracts to buy, USDT units to calculate the quantity
`openPosition `|boolean|`YES`|`true`|Open position or Close position order, eg: true or false
`price`|double|`NO`. **REQUIRED** for (`LIMIT`) orders|`--`|Order price
`triggerPrice`|double|`NO`|`--`|Trigger price for conditional order
`trailingStop`|double|`NO`|`--`|Trailing stop value for advanced order, conflict with stopLossPrice
`stopLossPrice`|double|`NO`|`--`|Stop loss price for advanced order, conflict with trailingStop
`stopWinPrice`|double|`NO`|`--`|Stop win price for advanced order
`tif`|string|`NO`|`GTC`|Type of advanced order, Available values : FILL_OR_KILL, GOOD_TILL_CANCEL, IMMEDIATE_OR_CANCEL, QUEUE_OR_CANCEL
`triggerType`|string|`NO`|`--`|Trigger type of price for conditional order, eg: LAST or INDEX, it will be LAST if not providedAvailable values : INDEX, LAST, MARK
`stopWinType`|string|`NO`|`--`|Stop win type of price for advanced order, eg: Limit or Market, it's required if stopWinPrice is set Available values : Limit, Market
`clientOrderId`|string|`NO`|`--`|An unique ID for the order (user defined)
`hidden`|boolean|`NO`|`false`|Hidden order or not, it's false by default
`showQty`|double|`NO`|`0`|show quantity for hidden order, set value for it only when hidden is true

**NOTE** For **Market Orders**, you need to set `orderType` as **`MARKET`**.

You can get contract price and quantity precision configuration data in the `exchange` endpoint.

Note: if your balance does not meet the margin requirement (which is the minimum margin requirement + open position fee + close position fee), "*insufficient balance*" error message will be returned.


### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`created`|long|`1570759718825`|Timestamp when the order is created
`modified`|long|`1551062936784`|Timestamp when this order was updated last time
`id`|string|`O101-20230531-025722-174-1016`|The order ID
`clientOrderId`|string|`213443`|An unique order ID whic is defined by user 
`symbol`|string|`BTC-PERP-REV`|The contract symbol
`price`|float|`8200`|The order price
`qty`|float|`1.01`|Order quantity
`cumQty`|float|`1.01`|The number of orders that has been executed
`avgPx`|float|`4754.24`|Average price of filled orders
`side`|string|`--`|Direction of the order. Direction type: `Buy`, `Sell`
`type`|string|`--`|The order type, includes: `LIMIT`, `Market`
`tif`|string|`GTC`|Type of advanced order, Available values : FILL_OR_KILL, GOOD_TILL_CANCEL, IMMEDIATE_OR_CANCEL, QUEUE_OR_CANCEL
`fee`|double|`--`|Fees incurred for this order.

```json
{
  "code": 0,
  "message": "OK",
  "result": "{\"id\":\"O101-20230531-025722-174-1016\",\"symbol\":\"BTCUSDT\",\"created\":1685501842000,\"modified\":1685501842000,\"side\":\"Sell\",\"type\":\"Limit\",\"tif\":\"GOOD_TILL_CANCEL\",\"uid\":\"1323056886107491328\",\"currency\":\"BTC\",\"price\":28000.0,\"qty\":100.0,\"openPosition\":true,\"cumQty\":0.0,\"avgPx\":0.0,\"ordStatus\":\"PENDING_NEW\",\"iceberg\":false,\"showQty\":0.0,\"source\":\"Normal\",\"pnl\":0.0,\"fee\":0.0}"
}
```
## `Query Order`

Request order by id

### **Limit:**

Speed limit: 20 times /1s, Speed limit rule: apiKey

### **Request URL:**
```bash
GET /trade/api/trade/queryOrderById
```

### **Parameters：**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ------------
`orderId`|string|`O101-20230531-025722-174-1016`|`YES`|The order ID

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`id`|string|`O101-20230531-025722-174-1016`|The order ID
`uid`|string|`1323056886107491328`|The User ID
`symbol`|string|`BTCUSDT`|The contract symbol
`created`|long|`1570759718825`|Timestamp when the order is created
`modified`|long|`1551062936784`|Timestamp when this order was updated last time
`clientOrderId`|string|`213443`|An unique order ID whic is defined by user
`side`|string|`--`|Direction of the order. Direction type: `Buy`, `Sell`
`type`|string|`--`|The order type, includes: `LIMIT`, `Market`
`tif`|string|`GTC`|Type of advanced order, Available values : FILL_OR_KILL, GOOD_TILL_CANCEL, IMMEDIATE_OR_CANCEL, QUEUE_OR_CANCEL
`currency`|string|`USDT`|Currency of account, eg: BTC, ETH, USDT
`price`|double|`8200`|The order price
`qty`|double|`11.0`|Order quantity
`openPosition`|boolean|`true`|Open position or Close position order, eg: true or false
`ordStatus`|boolean|`true`|Open position or Close position order, eg: true or false
`cumQty`|double|`11.0`|The number of orders that has been executed
`avgPx`|double|`4754.24`|Average price of filled orders
`ordStatus`|string|`FILLED`|The order status, includes: `PENDING_NEW`, `NEW`, `PARTIALLY_FILLED`, `FILLED`, `PENDING_CANCEL`, `CANCELED`, `REJECTED`, `PENDING_REPLACE`, `REPLACED`, `WAITING`
`iceberg`|boolean|`false`|The order is iceberg
`showQty`|double|`1.0`|The order showQty
`pnl`|double|`1.1`|Pnl incurred for this order.
`fee`|double|`1.1`|Fees incurred for this order.
`triggerPrice`|double|`--`|Trigger price for conditional order
`triggerType`|string|`--`|Trigger type of price for conditional order, eg: LAST or INDEX, it will be LAST if not providedAvailable values : INDEX, LAST, MARK
`trailingStop`|double|`--`|Trailing stop value for advanced order, conflict with stopLossPrice
`stopLossPrice`|double|`--`|Stop loss price for advanced order, conflict with trailingStop
`stopWinPrice`|double|`--`|Stop win price for advanced order
`stopWinType`|string|`--`|Stop win type of price for advanced order, eg: Limit or Market, it's required if stopWinPrice is set Available values : Limit, Market
`trailingStop`|double|`--`|Trailing stop value for advanced order, conflict with stopLossPrice
```json
{
  "code": 0,
  "message": "OK",
  "result": {
    "id": "O101-20230531-040439-546-1837",
    "uid": "1323056886107491328",
    "symbol": "BTCUSDT",
    "created": 1685505879000,
    "modified": 1685505879000,
    "side": "Buy",
    "type": "Market",
    "tif": "GOOD_TILL_CANCEL",
    "currency": "BTC",
    "price": 0.0,
    "qty": 100.0,
    "openPosition": false,
    "cumQty": 100.0,
    "avgPx": 27620.2,
    "ordStatus": "FILLED",
    "iceberg": false,
    "showQty": 0.0,
    "source": "Normal",
    "pnl": 1.3365529862569942E-6,
    "fee": -1.448215436528338E-6,
    "triggerPrice": null,
    "triggerType": null,
    "stopLossPrice": null,
    "stopWinType": null,
    "stopWinPrice": null,
    "trailingStop": null
  }
}
```
## `Query Trades`

Request trades by order id

### **Limit:**

Speed limit: 10 times /1minutes, Speed limit rule: apiKey

### **Request URL:**
```bash
GET /trade/api/trade/queryTrades
```

### **Parameters：**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ------------
`orderId`|string|`O101-20230531-025722-174-1016`|`YES`|The order ID

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`id`|string|`T101-20230531-040439-548-1608`|The trade ID
`symbol`|string|`BTCUSDT`|The contract symbol
`currency`|string|`USDT`|Currency of account, eg: BTC, ETH, USDT
`orderId`|string|`O101-20230531-025722-174-1016`|The order ID
`side`|string|`--`|Direction of the order. Direction type: `Buy`, `Sell`
`openPosition`|boolean|`true`|Open position or Close position order, eg: true or false
`userId`|string|`1323056886107491328`|The user id
`accountId`|string|`1323056886107491328`|The account id
`price`|double|`8200`|The trade price
`qty`|double|`11.0`|Order quantity
`fee`|double|`1.1`|Fees incurred for this order.
`feeRate`|double|`0.0002`|Fee rate
`createdTimestamp`|long|`1570759718825`|Timestamp when the order is created
```json
{
  "code": 0,
  "message": "OK",
  "result": [
    {
      "id": "T101-20230531-040439-548-1608",
      "symbol": "BTCUSDT",
      "orderId": "O101-20230531-040439-546-1837",
      "side": "Buy",
      "openPosition": false,
      "userId": "1323056886107491328",
      "accountId": "1323056886107491328-CCF-BTC",
      "price": 27620.2,
      "qty": 100.0,
      "fee": -1.448215436528338E-6,
      "feeRate": -4.0E-4,
      "createdTimestamp": "1685505880000",
      "currency": "BTC"
    }
  ]
}
```
## `Query Orders`

Request order by time

### **Limit:**

Speed limit: 10 times /1 minutes, Speed limit rule: apiKey, Response data limitation: 300

### **Request URL:**
```bash
GET /trade/api/trade/queryOrdersPro
```

### **Parameters：**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ------------
`prevTimeMillis`|long|`1685505879000`|`NO`|The order created, Query the data from the prevTimeMillis to the current time

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`id`|string|`O101-20230531-025722-174-1016`|The order ID
`uid`|string|`1323056886107491328`|The User ID
`symbol`|string|`BTCUSDT`|The contract symbol
`created`|long|`1570759718825`|Timestamp when the order is created
`modified`|long|`1551062936784`|Timestamp when this order was updated last time
`clientOrderId`|string|`213443`|An unique order ID whic is defined by user
`side`|string|`--`|Direction of the order. Direction type: `Buy`, `Sell`
`type`|string|`--`|The order type, includes: `LIMIT`, `Market`
`tif`|string|`GTC`|Type of advanced order, Available values : FILL_OR_KILL, GOOD_TILL_CANCEL, IMMEDIATE_OR_CANCEL, QUEUE_OR_CANCEL
`currency`|string|`USDT`|Currency of account, eg: BTC, ETH, USDT
`price`|double|`8200`|The order price
`qty`|double|`11.0`|Order quantity
`openPosition`|boolean|`true`|Open position or Close position order, eg: true or false
`ordStatus`|boolean|`true`|Open position or Close position order, eg: true or false
`cumQty`|double|`11.0`|The number of orders that has been executed
`avgPx`|double|`4754.24`|Average price of filled orders
`ordStatus`|string|`FILLED`|The order status, includes: `PENDING_NEW`, `NEW`, `PARTIALLY_FILLED`, `FILLED`, `PENDING_CANCEL`, `CANCELED`, `REJECTED`, `PENDING_REPLACE`, `REPLACED`, `WAITING`
`iceberg`|boolean|`false`|The order is iceberg
`showQty`|double|`1.0`|The order showQty
`pnl`|double|`1.1`|Pnl incurred for this order.
`fee`|double|`1.1`|Fees incurred for this order.
`triggerPrice`|double|`--`|Trigger price for conditional order
`triggerType`|string|`--`|Trigger type of price for conditional order, eg: LAST or INDEX, it will be LAST if not providedAvailable values : INDEX, LAST, MARK
`trailingStop`|double|`--`|Trailing stop value for advanced order, conflict with stopLossPrice
`stopLossPrice`|double|`--`|Stop loss price for advanced order, conflict with trailingStop
`stopWinPrice`|double|`--`|Stop win price for advanced order
`stopWinType`|string|`--`|Stop win type of price for advanced order, eg: Limit or Market, it's required if stopWinPrice is set Available values : Limit, Market
`trailingStop`|double|`--`|Trailing stop value for advanced order, conflict with stopLossPrice
```json
{
  "code": 0,
  "message": "OK",
  "result": [
    {
      "id": "O101-20230531-040439-546-1837",
      "uid": "1323056886107491328",
      "symbol": "BTCUSDT",
      "created": 1685505879000,
      "modified": 1685505879000,
      "side": "Buy",
      "type": "Market",
      "tif": "GOOD_TILL_CANCEL",
      "currency": "BTC",
      "price": 0.0,
      "qty": 100.0,
      "openPosition": false,
      "cumQty": 100.0,
      "avgPx": 27620.2,
      "ordStatus": "FILLED",
      "iceberg": false,
      "showQty": 0.0,
      "source": "Normal",
      "pnl": 1.3365529862569942E-6,
      "fee": -1.448215436528338E-6,
      "triggerPrice": null,
      "triggerType": null,
      "stopLossPrice": null,
      "stopWinType": null,
      "stopWinPrice": null,
      "trailingStop": null
    }
  ]
}
```
## `Query Active Orders`



### **Limit:**

Speed limit: 60 times /1 minutes, Speed limit rule: apiKey

### **Request URL:**
```bash
GET /trade/api/trade/queryActiveOrders
```

### **Parameters：**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ------------
`symbol`|long|`BTCUSDT`|`NO`|Retrieve active orders of symbol, eg: BTCUSDT; Will return all active orders of user if empty

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`id`|string|`O101-20230531-025722-174-1016`|The order ID
`uid`|string|`1323056886107491328`|The User ID
`symbol`|string|`BTCUSDT`|The contract symbol
`created`|long|`1570759718825`|Timestamp when the order is created
`modified`|long|`1551062936784`|Timestamp when this order was updated last time
`clientOrderId`|string|`213443`|An unique order ID whic is defined by user
`side`|string|`--`|Direction of the order. Direction type: `Buy`, `Sell`
`type`|string|`--`|The order type, includes: `LIMIT`, `Market`
`tif`|string|`GTC`|Type of advanced order, Available values : FILL_OR_KILL, GOOD_TILL_CANCEL, IMMEDIATE_OR_CANCEL, QUEUE_OR_CANCEL
`currency`|string|`USDT`|Currency of account, eg: BTC, ETH, USDT
`price`|double|`8200`|The order price
`qty`|double|`11.0`|Order quantity
`openPosition`|boolean|`true`|Open position or Close position order, eg: true or false
`ordStatus`|boolean|`true`|Open position or Close position order, eg: true or false
`cumQty`|double|`11.0`|The number of orders that has been executed
`avgPx`|double|`4754.24`|Average price of filled orders
`ordStatus`|string|`FILLED`|The order status, includes: `PENDING_NEW`, `NEW`, `PARTIALLY_FILLED`, `FILLED`, `PENDING_CANCEL`, `CANCELED`, `REJECTED`, `PENDING_REPLACE`, `REPLACED`, `WAITING`
`iceberg`|boolean|`false`|The order is iceberg
`showQty`|double|`1.0`|The order showQty
`pnl`|double|`1.1`|Pnl incurred for this order.
`fee`|double|`1.1`|Fees incurred for this order.
`triggerPrice`|double|`--`|Trigger price for conditional order
`triggerType`|string|`--`|Trigger type of price for conditional order, eg: LAST or INDEX, it will be LAST if not providedAvailable values : INDEX, LAST, MARK
`trailingStop`|double|`--`|Trailing stop value for advanced order, conflict with stopLossPrice
`stopLossPrice`|double|`--`|Stop loss price for advanced order, conflict with trailingStop
`stopWinPrice`|double|`--`|Stop win price for advanced order
`stopWinType`|string|`--`|Stop win type of price for advanced order, eg: Limit or Market, it's required if stopWinPrice is set Available values : Limit, Market
`trailingStop`|double|`--`|Trailing stop value for advanced order, conflict with stopLossPrice
```json
{
  "code": 0,
  "message": "OK",
  "result": [
    {
      "id": "O101-20230531-040439-546-1837",
      "uid": "1323056886107491328",
      "symbol": "BTCUSDT",
      "created": 1685505879000,
      "modified": 1685505879000,
      "side": "Buy",
      "type": "Market",
      "tif": "GOOD_TILL_CANCEL",
      "currency": "BTC",
      "price": 0.0,
      "qty": 100.0,
      "openPosition": false,
      "cumQty": 100.0,
      "avgPx": 27620.2,
      "ordStatus": "FILLED",
      "iceberg": false,
      "showQty": 0.0,
      "source": "Normal",
      "pnl": 1.3365529862569942E-6,
      "fee": -1.448215436528338E-6,
      "triggerPrice": null,
      "triggerType": null,
      "stopLossPrice": null,
      "stopWinType": null,
      "stopWinPrice": null,
      "trailingStop": null
    }
  ]
}
```

## `Amend Order`

Places Amend order for a contract. This API endpoint requires your request signed.

### **Request Weight:**

Speed limit: 10 times /1s Speed limit rule: apiKey

### **Request URL:**
```bash
POST /trade/api/trade/amendOrder
```

### **Parameters：**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ------------
`orderId`|string|`NO`|`--`|The order ID or An unique order ID defined by client
`qty`|double|`NO`|`0`|The number of contracts to buy, USDT units to calculate the quantity
`price`|double|`NO`. **REQUIRED** for (`LIMIT`) orders|`--`|Order price
`stopWinType`|string|`YES`|`--`|The order type, includes: `LIMIT`, `Market`
`triggerPrice`|double|`NO`|`--`|Trigger price for conditional order
`trailingStop`|double|`NO`|`--`|Trailing stop value for advanced order, conflict with stopLossPrice
`stopLossPrice`|double|`NO`|`--`|Stop loss price for advanced order, conflict with trailingStop
`stopWinPrice`|double|`NO`|`--`|Stop win price for advanced order
### **Response:**
```json
{
  "code": 0,
  "message": "OK",
  "result": null
}
```
## `cancel`

Cancels an order, `orderId` or `clientOrderId` is required. This API endpoint requires your request signed.

### **Request Weight:**

Speed limit: 40 times /1s Speed limit rule: apiKey

### **Request Url:**
```bash
POST /trade/api/trade/cancelOrder
```

### **Parameter:**

Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | -----
`orderId`|integer|`NO`|`--`|The order ID
`clientOrderId`|string|`NO`|`--`|Unique client customized ID for the order

 `orderId` and `clientOrderId`, at least one **MUST** be provided.

### **Response:**

Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`result`|integer|`O101-20230531-023520-732-0610`|The order ID or An unique order ID defined by client

```json
{
  "code": 0,
  "message": "OK",
  "result": "O101-20230531-023520-732-0610"
}
```
## `Close Position`

Close all position with market price

### **Request Weight:**

Speed limit: 8 times /1s Speed limit rule: apiKey

### **Request URL:**
```bash
POST /trade/api/trade/closePosition
```

### **Parameters：**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ------------
`symbol`|string|`YES`|`--`|The contract symbol, eg: BTCUSDT
`side`|string|`YES`|`--`|Position side, eg: `Long` or `Short`
`currency `|string|`YES`|`--`|Currency of account, eg: BTC, ETH, USDT

### **Response:**
```json
{
  "code": 0,
  "message": "OK",
  "result": null
}
```
## `Query Position`

Query all the position of the user

### **Limit:**

Speed limit: 60 times /1 minutes, Speed limit rule: apiKey

### **Request URL:**
```bash
GET /trade/api/trade/queryPosition
```

### **Parameters：**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | ------------
------------ | ------------ | ------------ | ------------ | ------------

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`uid`|string|`1323056886107491328`|The User ID
`currency`|string|`USDT`|Currency of account, eg: BTC, ETH, USDT
`symbol`|string|`BTCUSDT`|The contract symbol
`side`|string|`--`|Direction of the position. Direction type: `Long`, `Short`
`qty`|double|`11.0`|Position quantity
`price`|double|`4754.24`|Price of position
`closableQty`|double|`11.0`|Closable quantity
`pnlRate`|double|`-0.001`|Pnl rate
`value`|double|`11.0`|Position value by currency
`positionLeverage`|double|`11.0`|Position leverage
`liquidationPrice`|double|`11.0`|Liquidation price
`pnl`|double|`1.1`|Realized pnl
`urPnL`|double|`1.1`|Unrealized pnl
`deposit`|double|`1.1`|deposit
`lastPrice`|double|`1.1`|Last price
`created`|long|`1570759718825`|Timestamp when the position is created
`trailingStopPrice`|double|`--`|Trailing stop price
`stopLossPrice`|double|`--`|Stop loss price for advanced order, conflict with trailingStop
`stopWinPrice`|double|`--`|Stop win price for advanced order
`stopWinType`|string|`--`|Stop win type of price for advanced order, eg: Limit or Market, it's required if stopWinPrice is set Available values : Limit, Market
`trailingStop`|double|`--`|Trailing stop value for advanced order, conflict with stopLossPrice
```json
{
  "code": 0,
  "message": "OK",
  "result": [
    {
      "uid": "1323056886107491328",
      "currency": "ETH",
      "symbol": "BTCUSDT",
      "side": "Long",
      "qty": 0.0,
      "individualPosition": true,
      "price": 0.0,
      "closableQty": 0.0,
      "pnlRate": 0.0,
      "value": 0.0,
      "positionLeverage": 20.0,
      "trailingStopPrice": 0.0,
      "stopLossPrice": null,
      "stopWinType": null,
      "stopWinPrice": null,
      "trailingStop": null,
      "pnl": 0.0,
      "urPnL": 0.0,
      "liquidationPrice": 0.0,
      "deposit": 0.0,
      "created": "2023-02-15T11:40:13.000+00:00",
      "lastPrice": 27128.5
    },
    {
      "uid": "1323056886107491328",
      "currency": "ETH",
      "symbol": "BTCUSDT",
      "side": "Short",
      "qty": 0.0,
      "individualPosition": true,
      "price": 0.0,
      "closableQty": 0.0,
      "pnlRate": 0.0,
      "value": 0.0,
      "positionLeverage": 20.0,
      "trailingStopPrice": 0.0,
      "stopLossPrice": null,
      "stopWinType": null,
      "stopWinPrice": null,
      "trailingStop": null,
      "pnl": 0.0,
      "urPnL": 0.0,
      "liquidationPrice": 0.0,
      "deposit": 0.0,
      "created": "2023-02-15T11:40:13.000+00:00",
      "lastPrice": 27128.5
    },
    {
      "uid": "1323056886107491328",
      "currency": "USDT",
      "symbol": "BTCUSDT",
      "side": "Long",
      "qty": 0.0,
      "individualPosition": false,
      "price": 0.0,
      "closableQty": 0.0,
      "pnlRate": 0.0,
      "value": 0.0,
      "positionLeverage": 20.0,
      "trailingStopPrice": 0.0,
      "stopLossPrice": null,
      "stopWinType": null,
      "stopWinPrice": null,
      "trailingStop": null,
      "pnl": 0.0,
      "urPnL": 0.0,
      "liquidationPrice": 0.0,
      "deposit": 0.0,
      "created": "2023-05-19T09:08:55.000+00:00",
      "lastPrice": 27128.5
    },
    {
      "uid": "1323056886107491328",
      "currency": "USDT",
      "symbol": "BTCUSDT",
      "side": "Short",
      "qty": 100.0,
      "individualPosition": false,
      "price": 27117.1,
      "closableQty": 100.0,
      "pnlRate": -0.013644526885249529,
      "value": 100.0,
      "positionLeverage": 20.0,
      "trailingStopPrice": 0.0,
      "stopLossPrice": null,
      "stopWinType": null,
      "stopWinPrice": null,
      "trailingStop": null,
      "pnl": -0.04,
      "urPnL": -0.09742929738062658,
      "liquidationPrice": 162026.91766730743,
      "deposit": 5.0,
      "created": "2023-05-31T08:03:45.000+00:00",
      "lastPrice": 27128.5
    },
    {
      "uid": "1323056886107491328",
      "currency": "TUSDT",
      "symbol": "TBTCTUSDT",
      "side": "Long",
      "qty": 0.0,
      "individualPosition": true,
      "price": 0.0,
      "closableQty": 0.0,
      "pnlRate": 0.0,
      "value": 0.0,
      "positionLeverage": 20.0,
      "trailingStopPrice": 0.0,
      "stopLossPrice": null,
      "stopWinType": null,
      "stopWinPrice": null,
      "trailingStop": null,
      "pnl": 0.0,
      "urPnL": 0.0,
      "liquidationPrice": 0.0,
      "deposit": 0.0,
      "created": "2023-02-17T09:06:52.000+00:00",
      "lastPrice": 27135.0
    },
    {
      "uid": "1323056886107491328",
      "currency": "TUSDT",
      "symbol": "TBTCTUSDT",
      "side": "Short",
      "qty": 0.0,
      "individualPosition": true,
      "price": 0.0,
      "closableQty": 0.0,
      "pnlRate": 0.0,
      "value": 0.0,
      "positionLeverage": 20.0,
      "trailingStopPrice": 0.0,
      "stopLossPrice": null,
      "stopWinType": null,
      "stopWinPrice": null,
      "trailingStop": null,
      "pnl": 0.0,
      "urPnL": 0.0,
      "liquidationPrice": 0.0,
      "deposit": 0.0,
      "created": "2023-02-15T11:05:54.000+00:00",
      "lastPrice": 27135.0
    },
    {
      "uid": "1323056886107491328",
      "currency": "BTC",
      "symbol": "BTCUSDT",
      "side": "Long",
      "qty": 0.0,
      "individualPosition": false,
      "price": 0.0,
      "closableQty": 0.0,
      "pnlRate": 0.0,
      "value": 0.0,
      "positionLeverage": 16.0,
      "trailingStopPrice": 0.0,
      "stopLossPrice": null,
      "stopWinType": null,
      "stopWinPrice": null,
      "trailingStop": null,
      "pnl": 0.0,
      "urPnL": 0.0,
      "liquidationPrice": 0.0,
      "deposit": 0.0,
      "created": "2023-02-15T11:08:13.000+00:00",
      "lastPrice": 27128.5
    },
    {
      "uid": "1323056886107491328",
      "currency": "BTC",
      "symbol": "BTCUSDT",
      "side": "Short",
      "qty": 0.0,
      "individualPosition": false,
      "price": 0.0,
      "closableQty": 0.0,
      "pnlRate": 0.0,
      "value": 0.0,
      "positionLeverage": 16.0,
      "trailingStopPrice": 0.0,
      "stopLossPrice": null,
      "stopWinType": null,
      "stopWinPrice": null,
      "trailingStop": null,
      "pnl": 0.0,
      "urPnL": 0.0,
      "liquidationPrice": 0.0,
      "deposit": 0.0,
      "created": "2023-05-31T04:04:07.000+00:00",
      "lastPrice": 27128.5
    }
  ]
}
```
## `Switch PosSide`

Switch position side

### **Limit:**

Speed limit: 8 times /1s, Speed limit rule: apiKey

### **Request Url:**
```bash
POST /trade/api/trade/switchPosSide
```

### **Parameter:**

Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | -----
`twoSidePosition`|boolean|`YES`|`--`|Switch to two side position mode if true, otherwise, switch to one side position mode
`currency`|string|`YES`|`--`|Currency of account, eg: BTC, ETH, USDT
### **Response:**

Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
------------ | ------------ | ------------ | ------------

```json
{
  "code": 0,
  "message": "OK",
  "result": null
}
```
## `Change Position Mode`

Change position mode between Individual and Cross

### **Limit:**

Speed limit: 8 times /1s, Speed limit rule: apiKey

### **Request Url:**
```bash
POST /trade/api/trade/changePosMode
```

### **Parameter:**

Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | -----
`individual`|boolean|`YES`|`--`|Position mode, true -> Individual; false -> Cross
`currency`|string|`YES`|`--`|Currency of account, eg: BTC, ETH, USDT
### **Response:**

Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
------------ | ------------ | ------------ | ------------

```json
{
  "code": 0,
  "message": "OK",
  "result": null
}
```
## `Change PosLeverage`

Change position leverage

### **Limit:**

Speed limit: 8 times /1s, Speed limit rule: apiKey

### **Request Url:**
```bash
POST /trade/api/trade/changePosLeverage
```

### **Parameter:**

Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | -----
`leverage`|double|`YES`|`--`|Position leverage
`symbol`|string|`YES`|`--`|The contract symbol, eg: BTCUSDT
`currency`|string|`YES`|`--`|Currency of account, eg: BTC, ETH, USDT
### **Response:**

Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
------------ | ------------ | ------------ | ------------

```json
{
  "code": 0,
  "message": "OK",
  "result": null
}
```
## `Change Risk`

Change risk setting of position

### **Limit:**

Speed limit: 10 times /1s, Speed limit rule: apiKey

### **Request Url:**
```bash
POST /trade/api/trade/riskSetting
```

### **Parameter:**

Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | -----
`symbol`|string|`YES`|`--`|The contract symbol, eg: BTCUSDT
`currency`|string|`YES`|`--`|Currency of account, eg: BTC, ETH, USDT
`side`|string|`YES`|`--`|Position side, eg: Long or Short
`addDeposit`|double|`NO`|`--`|Increase or decrease extra deposit for individual position
`stopLossPrice`|double|`NO`|`--`|Stop loss price for advanced order, conflict with trailingStop
`stopWinPrice`|double|`NO`|`--`|Stop win price for advanced order
`stopWinType`|string|`NO`|`--`|Stop win type of price for advanced order, eg: Limit or Market, it's required if stopWinPrice is set Available values : Limit, Market
`trailingStop`|double|`NO`|`--`|Trailing stop value for advanced order, conflict with stopLossPrice

### **Response:**

Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
------------ | ------------ | ------------ | ------------

```json
{
  "code": 0,
  "message": "OK",
  "result": null
}
```
## `Query Accounts`

This endpoint is used to retrieve contract account balance. This endpoint requires
your request signed.

### **Limit:**

Speed limit: 60 times /1minutes, Speed limit rule: apiKey

### **Request Url:**
```bash
GET  /trade/api/trade/queryAccounts
```

### **Parameters:**
None

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`uid`|string|`1323056886107491328`|User id
`currency`|string|`USDT`|currency
`cash`|double|`0.01215991`|cash
`withdrawableCash`|double|`0`| Withdrawable cash
`frozenCash`|double|`0`| Frozen cash
`urPnl`|double|`0`| Unrealized pnl
`cashAvailable`|double|`0`| Available cash

### **Example:**

```json
{
    "code": 0,
        "message": "OK",
        "result": [
        {
            "uid": "1323056886107491328",
            "currency": "ETH",
            "cash": 0.0,
            "withdrawableCash": 0.0,
            "frozenCash": 0.0,
            "urPnl": 0.0,
            "cashAvailable": 0.0
        },
        {
            "uid": "1323056886107491328",
            "currency": "USDT",
            "cash": 499.90922659263174,
            "withdrawableCash": 499.90922659263174,
            "frozenCash": 0.0,
            "urPnl": 0.0,
            "cashAvailable": 499.90922659263174
        },
        {
            "uid": "1323056886107491328",
            "currency": "TUSDT",
            "cash": 1000.0,
            "withdrawableCash": 1000.0,
            "frozenCash": 0.0,
            "urPnl": 0.0,
            "cashAvailable": 1000.0
        },
        {
            "uid": "1323056886107491328",
            "currency": "BTC",
            "cash": 9.999288458956643,
            "withdrawableCash": 0.0,
            "frozenCash": 9.999288458956643,
            "urPnl": 2.573443933625344E-5,
            "cashAvailable": 9.999190074639152
        }
    ]
}
```
## `Query Accounts`

This endpoint is used to retrieve contract account balance. This endpoint requires
your request signed.

### **Limit:**

Speed limit: 60 times /1minutes, Speed limit rule: apiKey

### **Request Url:**
```bash
GET  /trade/api/trade/queryAccounts
```

### **Parameters:**
None

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`uid`|string|`1323056886107491328`|User id
`currency`|string|`USDT`|currency
`twoWayPosition`|boolean|`true`|Two way position
`individualPosition`|boolean|`false`| Individual position

### **Example:**

```json
{
  "code": 0,
  "message": "OK",
  "result": [
    {
      "uid": "1323056886107491328",
      "currency": "ETH",
      "twoWayPosition": false,
      "individualPosition": true
    },
    {
      "uid": "1323056886107491328",
      "currency": "USDT",
      "twoWayPosition": true,
      "individualPosition": false
    },
    {
      "uid": "1323056886107491328",
      "currency": "TUSDT",
      "twoWayPosition": false,
      "individualPosition": true
    },
    {
      "uid": "1323056886107491328",
      "currency": "BTC",
      "twoWayPosition": true,
      "individualPosition": false
    }
  ]
}
```

### `openOrders`

Retrieves open orders. This API endpoint requires your request signed.

### **Request Weight:**

1

### **Request Url:**
```bash
GET /openapi/contract/v1/openOrders
```

### **Parameters:**
Parameter|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | --------
`symbol`|string|`NO`||Symbol of open orders. If not sent, all kinds of contract open orders will be returned.
`orderId`|integer|`NO`|| Order ID
`orderType`|string|`YES`||The order type: `LIMIT` and `STOP`.
`limit`|integer|`NO`|`20`|The number of entries returned.

If `orderId` is set, it will get orders whose `orderId` < that `orderId`. Otherwise the lastest open orders are returned.

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`time`|long|`1551062936784`|Timestamp when the order is created.
`updateTime`|long|`1551062936784`|Timestamp when this order was updated last time
`orderId`|integer|`891`|The order ID
`clientOrderId`|string|`213443`|An unique order ID defined by client
`symbol`|string|`BTC-PERP-REV`|The contract symbol
`price`|float|`4765.29`|The order price
`leverage`|float|`4`|Leverage of the order.
`origQty`|float|`1.01`|The quantity of the order
`executedQty`|float|`1.01`|The quantity of orders that has been executed
`avgPrice`|float|`4754.24`|Average price of filled orders.
`marginLocked`|float|`200`|Amount of margin locked for this order. This includes the `actual margin` needed plus fees to open and close the position.
`orderType`|string|`LIMIT`|The order type: `LIMIT` and `STOP`
`priceType`|string|`INPUT`|The price type: `INPUT`, `OPPONENT`, `QUEUE`, `OVER`, and `MARKET`
`side`|string|`BUY_OPEN`|Direction of the order: `BUY_OPEN`, `BUY_CLOSE`, `SELL_OPEN` and `SELL_CLOSE`
`status`|string|`NEW`|The status of the order: `NEW`, `PARTIALLY_FILLED`, `FILLED`, `CANCELED`, and `REJECTED`
`timeInForce`|string|`GTC`|Time in force. Possible values include `GTC`,`FOK`,`IOC`, and `LIMIT_MAKER`
`fees`|||Fees incurred for this order.

### **Example:**

```js
[
  {
    'time': '1570760254539',
    'updateTime': '0',
    'orderId': '469965509788581888',
    'clientOrderId': '1570760253946',
    'symbol': 'BTC-PERP-REV',
    'price': '8502.34',
    'leverage': '20',
    'origQty': '222',
    'executedQty': '0',
    'avgPrice': '0',
    'marginLocked': '0.00130552',
    'orderType': 'LIMIT',
    'side': 'BUY_OPEN',
    'fees': [],
    'timeInForce': 'GTC',
    'status': 'NEW',
    'priceType': 'INPUT'
  },...
]
```

## `historyOrders`

Retrieves history of orders that have been partially or fully filled or canceled. This API endpoint requires your request signed.

### **Request Weight:**

1

### **Request Url:**
```bash
GET /openapi/contract/v1/historyOrders
```

### **Parameters:**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | --------
`symbol`|string|`NO`||Symbol for history orders. If not sent, all contract history orders will be returned.
`orderId`|integer|`NO`|| Order ID
`orderType`|string|`YES`||The order type: `LIMIT`, `STOP`
`limit`|integer|`NO`|`20`|The number of entries returned.

If `orderId` is set, it will get orders whose `orderId` < that `orderId`. Otherwise the lastest open orders are returned.

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`time`|long|`1551062936784`|Timestamp when the order is created.
`updateTime`|long|`1551062936784`|Timestamp when this order was updated last time
`orderId`|integer|`891`|The order ID
`clientOrderId`|string|`213443`| An unique ID of the order
`symbol`|string|`BTC-PERP-REV`|The contract symbol
`price`|float|`4765.29`|The order price
`leverage`|float|`4`|Leverage of the order
`origQty`|float|`1.01`|The quantity of the order
`executedQty`|float|`1.01`|The quantity of orders that has been executed
`avgPrice`|float|`4754.24`|Average price of filled orders.
`marginLocked`|float|`200`|Amount of margin locked for this order. This includes the `actual margin` needed plus fees to open and close the position.
`orderType`|string|`LIMIT`|The order type: `LIMIT` and `STOP`
`priceType`|string|`INPUT`|The price type: `INPUT`, `OPPONENT`, `QUEUE`, `OVER`, and `MARKET`.
`side`|string|`BUY_OPEN`|Direction of the order: `BUY_OPEN`, `BUY_CLOSE`, `SELL_OPEN` and `SELL_CLOSE`
`status`|string|`NEW`|The status of the order: `NEW`, `PARTIALLY_FILLED`, `FILLED`, `CANCELED`, and `REJECTED`.
`timeInForce`|string|`GTC`|Time in force. Possible values include `GTC`,`FOK`,`IOC`, and `LIMIT_MAKER`
`fees`|||Fees incurred for this order.

### **Example:**

```js
[
  {
    'time': '1570759718825',
    'updateTime': '0',
    'orderId': '469961015902208000',
    'clientOrderId': '6423344174',
    'symbol': 'BTC-PERP-REV',
    'price': '8200',
    'leverage': '12.08',
    'origQty': '5',
    'executedQty': '0',
    'avgPrice': '0',
    'marginLocked': '0',
    'orderType': 'LIMIT',
    'side': 'BUY_OPEN',
    'fees': [],
    'timeInForce': 'GTC',
    'status': 'CANCELED',
    'priceType': 'INPUT'
  },...
]
```

## `getOrder`
Get details on a specific order

### **Request Weight:**

1

### **Request Url:**
```bash
GET /openapi/contract/v1/getOrder
```

### **Parameters:**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | -------
`symbol`|string|`NO`||Symbol for history orders. If not sent, all contract history orders will be returned.
`orderId`|integer|`NO`|| Order ID
`orderType`|string|`YES`||The order type: `LIMIT`, `STOP`

**Either `orderId` or `clientOrderId` must be sent**

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`time`|long|`1551062936784`|Timestamp when the order is created
`updateTime`|long|`1551062936784`|Timestamp when this order was updated last time
`orderId`|integer|`891`|The order ID
`clientOrderId`|string|`213443`|An unique order ID defined by client 
`symbol`|string|`BTC-PERP-REV`|The contract symbol
`price`|float|`4765.29`|The order price
`leverage`|float|`4`|Leverage of the order
`origQty`|float|`1.01`|The quantity of the order
`executedQty`|float|`1.01`|The quantity of orders that has been executed
`avgPrice`|float|`4754.24`|Average price of filled orders
`marginLocked`|float|`200`|Amount of margin locked for this order. This includes the `actual margin` needed plus fees to open and close the position.
`orderType`|string|`LIMIT`|The order type: `LIMIT` and `STOP`
`priceType`|string|`INPUT`|The price type: `INPUT`, `OPPONENT`, `QUEUE`, `OVER`, and `MARKET`.
`side`|string|`BUY_OPEN`|Direction of the order: `BUY_OPEN`, `BUY_CLOSE`, `SELL_OPEN` and `SELL_CLOSE`
`status`|string|`NEW`|The status of the order: `NEW`, `PARTIALLY_FILLED`, `FILLED`, `CANCELED`, and `REJECTED`.
`timeInForce`|string|`GTC`|Time in force. Possible values include `GTC`,`FOK`,`IOC`, and `LIMIT_MAKER`
`fees`|||Fees incurred for this order.


### **Example:**

```js
{
  'time': '1570760254539',
  'updateTime': '0',
  'orderId': '469965509788581888',
  'clientOrderId': '1570760253946',
  'symbol': 'BTC-PERP-REV',
  'price': '8502.34',
  'leverage': '20',
  'origQty': '222',
  'executedQty': '0',
  'avgPrice': '0',
  'marginLocked': '0.00130552',
  'orderType': 'LIMIT',
  'side': 'BUY_OPEN',
  'fees': [],
  'timeInForce': 'GTC',
  'status': 'NEW',
  'priceType': 'INPUT'
}
```

## `myTrades`
Retrieve the trade history of the account. This API endpoint requires your request to be signed.

### **Request Weight:**

1

### **Request Url:**
```bash
GET /openapi/contract/v1/myTrades
```

### **Parameters:**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | -------
`symbol`|string|`NO`|| The contract symbol. If not sent, trade history for all contacts will be returned.
`limit`|integer|`NO`|`20`|The number of trades returned (maxium 1000)
`fromId`|integer|`NO`||TradeId retrieved from.
`toId`|integer|`NO`||TradeId retrieved to.

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`time`|long|`1551062936784`|Timestamp when the order is created.
`tradeId`|long|`49366`|The trade ID
`orderId`|integer|`891`|The order ID
`matchOrderId`|long|`630491432`| The match order ID
`symbolId`|string|`BTC-PERP-REV`|The contract symbol
`price`|float|`4765.29`|The trade price
`quantity`|float|`1.01`|The quantity of the trade.
`feeTokenId`|string|`USDT`|Transaction fee token name
`fee`|||Transaction fee
`side`|string|`BUY`|Direction of the order: `BUY_OPEN`, `SELL_OPEN`, `BUY_CLOSE`, and `SELL_CLOSE`.
`orderType`|string|`LIMIT`|The order type: LIMIT, MARKET
`pnl`|float|`100.1`|Profit and loss


### **Example:**

```js
[
  {
    'time': '1570760582848',
    'tradeId': '469968263995080704',
    'orderId': '469968263793737728',
    "matchOrderId": 436002617267469062,
    'accountId': '456552319339779840',
    'symbolId': 'BTC-PERP-REV',
    'price': '8531.17',
    'quantity': '100',
    'feeTokenId': 'TBTC',
    'fee': '0.00000586',
    'type': 'LIMIT',
    'side': 'BUY_OPEN',
    'pnl': '100.1'
  },...
]
```

## `positions`

Retrieves current positions. This API endpoint requires your request signed.

### **Request Weight:**

1

### **Request Url:**
```bash
GET /openapi/contract/v1/positions
```

### **Parameters:**
Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | --------
`symbol`|string|`NO`||The contract symbol. If not sent, positions for all contracts will be returned.
`side`|string|`NO`||`LONG` or `SHORT`. Direction of the position. If not sent, positions for both sides will be returned.

### **Response:**
Name|Type|Example|Description
------------ | ------------ | ------------ | ------------
`symbol`|string|`BTC-PERP-REV`|The contract name
`side`|string|`LONG`|Position side
`avgPrice`|float|`100`|Average price for opening position
`position`|float|`20`|The quantity of contracts opened
`available`|float|`15`|The quantity of contracts available to be close
`leverage`|float|`5`|Leverage of the position
`lastPrice`|float|`100`|The latest trade price
`positionValue`|float|`2000`|Current position value
`flp`|float|`80`|Forced liquidation price
`margin`|float|`20`|Margin for this position
`marginRate`|float|`0.2`|Margin rate for current position.
`unrealizedPnL`|float|`0.0`|Unrealized profit and loss for current position held.
`profitRate`|float|`0.0000333`|Rate of return for the position.
`realizedPnL`|float|`6.8`|Cumulative realized profit and loss for this `position`.


### **Example:**
```js
[
  {
    'symbol': 'BTC-PERP-REV',
    'side': 'LONG',
    'avgPrice': '8183.11',
    'position': '1100',
    'available': '1100',
    'leverage': '6',
    'lastPrice': '8572.53',
    'positionValue': '0.12833346',
    'flp': '7523.65',
    'margin': '0.01251335',
    'marginRate': '0.14',
    'unrealizedPnL': '0.00608975',
    'profitRate': '0.0000333',
    'realizedPnL': '-0.00006721'
  },...
]
```

## `transfer` **(PENDING)**

This endpoint is used to transfer funds across different accounts. This endpoint requires your request signed.

### **Request Weight:**
1

### **Request Url:**
```bash
POST  /openapi/v1/transfer
```

### **Parameters:**

Name|Type|Required|Default|Description
------------ | ------------ | ------------ | ------------ | -------
`from`|string|`YES`||Transfer from which account.
`to`|string|`YES`||Transfer to which account.
`currency`|string|`YES`||The intended currency symbol to transfer. (`USDT`, `BTC`)
`amount`|float|`YES`||The amount of currency transfered.

Currently supports transferring assets across `wallet` and `contract` accounts.

### **Response:**

A confirmation message will be returned.

### **Example:**

```js
{
  'message': 'success',
  'timestamp': 1541161088303
}
```

## Key parameter explanation:

### `side`

The side of the trade.

`BUY_OPEN`: open a long position.

`SELL_CLOSE`: close a long position.

`SELL_OPEN`: open a short position.

`BUY_CLOSE`: close a short position.

### `priceType`

Price types.

`INPUT`: The system will use the price you entered exactly to fill the orders.

`OPPONENT`: Orders will be filled using the opposite side's best quote.

For example, if you are opening 10 contracts long, the best buy price is 10 and the best sell price is 11. You will send an order buying 10 contracts at 11. If the order, is not fully filled, the rest will be left on the orderbook.

`QUEUE`: Order will be send using the same side's best quote.

For example, if you are opening 10 contracts long, the best buy price is 10 and the best sell price is 11. You will be send an order buying 10 contracts at 10.

`OVER`: The price will be the best opposite's quote + overPrice(not a fixed value).

For example, if you are opening 10 contracts long, the best buy price is 10 and the best sell price is 11, you set the overPrice at 3. You will be send an order buying 10 contracts at (11+3)=14.

`MARKET`: The price will be newest price * (1 ± 5%).

For example, if you are opening 10 contracts long, the latest price is 10. Then you will be sending out an order buying 10 contracts at (10 * 1.05)=10.5.

### `timeInForce`

Time in force.

`GTC`: Good till canceled. Meaning the order will stand unless otherwise cancelled.

`IOC`: Immediate or cancel. Meaning the order will be cancelled if not executed immediately. Recommended if you want to fill the entire order immediately.

`FOK`: Fill or kill. Meaning the order will be canceled if not immediately filled. 

`LIMIT_MAKER`: Order will be cancelled if executed immediately.

### `orderType`

Order type.

`LIMIT`: Orders will be executed by a given specified price or better.


`STOP`: Order will be triggered once it reaches the `triggerPrice`.
