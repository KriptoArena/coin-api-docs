# KriptoArena.com coin instant API document.
The documentation for KriptoArena.com coin instant API document.

## Usage
Append your exchange's URL to the beginning of the methods to use the API. For example, to get ticker info from KriptoArena.com, use [https://api.kriptoarena.com/api] (https://api.kriptoarena.com/api)

## Questions & Problems
Please use the [issues](https://github.com/KriptoArena/coin-api-docs/issues) on this github project to ask questions and report bugs.

## Request Limits

* .../api/coin/ requests are limited to 3 requests per 1 seconds.
* .../api/ requests are limited to 3 requests per 1 seconds.

## Coin / Currency and Coin Ticker

<code>GET</code> .../coin/BTC_TRY
* BTC_TRY

**Result:**
``` json

{
	"coinCode": "BTC",
	"coinName": "Bitcoin",
	"currencyCode": "TRY",
	"currencyName": "Türk Lira",
	"price": 39802.35,
	"open": 42000.00,
	"high": 45000.00,
	"low": 2000.00,
	"change": 1.06,
	"volume": 55.72,
	"timestamp": 1508242980,
	"bid": 21153.00000000,
	"ask": 21234.00000000
}

```

<code>GET</code> .../coin/BTC_CHFT
* BTC_CHFT

**Result:**
``` json

{
	"coinCode": "BTC",
	"coinName": "Bitcoin",
	"currencyCode": "CHFT",
	"currencyName": "Crypto Holding",
	"price": 39802.35,
	"open": 42000.00,
	"high": 45000.00,
	"low": 2000.00,
	"change": 1.06,
	"volume": 55.72,
	"timestamp": 1508242980,
	"bid": 3980.12691000,
	"ask": 4064.83461000
}

```
<code>GET</code> .../coin/LTC_BTC
* LTC_BTC

**Result:**
``` json

{
	"coinCode": "LTC",
	"coinName": "Litecoin",
	"currencyCode": "BTC",
	"currencyName": "Bitcoin",
	"price": 0.01255198,
	"open": 0.01235271,
	"high": 0.01268362,
	"low": 0.01223700,
	"change": 1.61,
	"volume": 96.50000000,
	"timestamp": 1508242980,
	"bid": 0.01223737,
	"ask": 0.01266584
}

```

* coinCode: Api coin code.
* coinName: Api coin long name.
* currencyCode: Api currency code or coin code.
* currencyName: Api currency long name or coin long name.
* price: Last price.
* open: Price of the opening in the last 24 hours.
* high: Highest price in the last 24 hours.
* low: Lowest price in the last 24 hours.
* change: Change price in the last 24 hours.
* volume: Total volume in the last 24 hours.
* timestamp: Unix UTC timestamp date and time.
* bid: Highest current order.
* ask: Lowest current order.

## Coin / Currency and Coin All Ticker

<code>GET</code> .../ReturnTicker
* ReturnTicker

**Result:**
``` json

[
	{
		"coinCode": "BTC",
		"coinName": "Bitcoin",
		"currencyCode": "TRY",
		"currencyName": "Türk Lira",
		"price": 39802.35,
		"open": 42000.00,
		"high": 45000.00,
		"low": 2000.00,
		"change": 1.06,
		"volume": 55.72,
		"timestamp": 1508242980,
		"bid": 21153.00000000,
		"ask": 21234.00000000
	},
	{
		"coinCode": "BTC",
		"coinName": "Bitcoin",
		"currencyCode": "CHFT",
		"currencyName": "Crypto Holding",
		"price": 39802.35,
		"open": 42000.00,
		"high": 45000.00,
		"low": 2000.00,
		"change": 1.06,
		"volume": 55.72,
		"timestamp": 1508242980,
		"bid": 3980.12691000,
		"ask": 4064.83461000
	},
	{
		"coinCode": "LTC",
		"coinName": "Litecoin",
		"currencyCode": "BTC",
		"currencyName": "Bitcoin",
		"price": 0.01255198,
		"open": 0.01235271,
		"high": 0.01268362,
		"low": 0.01223700,
		"change": 1.61,
		"volume": 96.50000000,
		"timestamp": 1508242980,
		"bid": 0.01223737,
		"ask": 0.01266584
	}
	... and more...
]

```

* coinCode: Api coin code.
* coinName: Api coin long name.
* currencyCode: Api currency code or coin code.
* currencyName: Api currency long name or coin long name.
* price: Last price.
* open: Price of the opening in the last 24 hours.
* high: Highest price in the last 24 hours.
* low: Lowest price in the last 24 hours.
* change: Change price in the last 24 hours.
* volume: Total volume in the last 24 hours.
* timestamp: Unix UTC timestamp date and time.
* bid: Highest current order.
* ask: Lowest current order.

## Coin / Currency and Order Books

<code>GET</code> .../orderbook/BTC_TRY
* BTC_TRY

**Result:**
``` json

{
	"TimeStamp": 1560603859406,
	"Asks": [
	    {
	      "Quantity": 0.04,
	      "Price": 51072.13
	    },
	    {
	      "Quantity": 0.07,
	      "Price": 51088.72
	    },
	    {
	      "Quantity": 0.02,
	      "Price": 51091.54
	    },
	    ... and more...
     	],
	"Bids": [
	    {
	      "Quantity": 0.40757466,
	      "Price": 20100
	    },
	    {
	      "Quantity": 0.66698238,
	      "Price": 35100
	    },
	    {
	      "Quantity": 0.09,
	      "Price": 50734.75
	    },
	    ... and more...
        ]
}

```

* TimeStamp: Query time.
* Asks: Open sales orders.
	* Quantity: Quantity.
	* Price: Price.
* Bids: Open buy orders.
	* Quantity: Quantity.
	* Price: Price.
	
## Coin Wallet Status

<code>GET</code> .../walletstatus

**Result:**
``` json

[
  {
    "Deposit": true,
    "Withdraw": false,
    "MinWithdraw": 0.002,
    "Coin": "BTC"
  },
  {
    "Deposit": true,
    "Withdraw": true,
    "MinWithdraw": 0.004,
    "Coin": "LTC"
  },
  {
    "Deposit": true,
    "Withdraw": true,
    "MinWithdraw": 0.005,
    "Coin": "ETH"
  },
  {
    "Deposit": true,
    "Withdraw": true,
    "MinWithdraw": 5,
    "Coin": "XRP"
  },
  ... and more...
]

```

* Deposit: Coin deposit feature status.
* Withdraw: Coin withdraw feature status.
* MinWithdraw: Minimum withdraw value.
* Coin: Related coin.

## Coin / Currency and Completed Orders

<code>GET</code> .../trades/BTC_TRY
* BTC_TRY

**Result:**
``` json

[
  {
    "Id": 4684380,
    "Price": 64978,
    "Qty": 0.00314929,
    "Time": 1561472782
  },
  {
    "Id": 4681114,
    "Price": 64477,
    "Qty": 0.0045,
    "Time": 1561458950
  },
  {
    "Id": 4681042,
    "Price": 64477,
    "Qty": 0.0045,
    "Time": 1561458886
  },
  ... and more...
]

```

* Id: Transaction id.
* Price: Transaction price.
* Qty: Transaction value.
* Time: Unix timestamp date and time.

## Available Coin / Currency

Bitcoin
*	BTC_TRY
*	BTC_CHFT

Litecoin
*	LTC_TRY
*	LTC_CHFT
*	LTC_BTC

Ethereum
*	ETH_TRY
*	ETH_CHFT
*	ETH_BTC

Ripple
*	XRP_TRY
*	XRP_CHFT
*	XRP_BTC

Bitcoin Cash
*	BCH_TRY
*	BCH_CHFT
*	BCH_BTC

Bitcoin Gold
*	BTG_TRY
*	BTG_CHFT
*	BTG_BTC

Digital Cash
*	DASH_TRY
*	DASH_CHFT
*	DASH_BTC

Z Cash
*	ZEC_TRY
*	ZEC_CHFT
*	ZEC_BTC

Stellar
*	XLM_TRY
*	XLM_CHFT
*	XLM_BTC

Doge Coin
*	DOGE_TRY
*	DOGE_CHFT
*	DOGE_BTC

DigiByte
*	DGB_TRY
*	DGB_CHFT
*	DGB_BTC

Bitcoin Hyper
*	BHY_TRY
*	BHY_CHFT
*	BHY_BTC

0x ZeroX
*	ZRX_CHFT

Holo
*	HOT_CHFT

Pundi X
*	NPXS_CHFT
