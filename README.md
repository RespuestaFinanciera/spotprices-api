# Spotprices-api #
## How to Connect your Application with SpotPrices Web Service. ##

### 1) cURL Method: ###
**1.1) Get authentication token.**

Request.

	POST /spotprices-api/token.php?username=Trial04ea66c5&service_id=14e1b600b1fd HTTP/1.1
    Host: http://apps.prendario.com
	
	Request Params.
	username : SpotPrices App/Sevice Name e.g. Trial04ea66c5
	service_id : Service Unique Identifier. e.g. 14e1b600b1fd

Response.

	Content-Type : application/json
	Content:
	
	{
		status: "sucess",
		response: {
			fecha: "2013-04-01",
			vigencia: "2013-04-01 05:18:24",
			access_token: "EBA12_iAAbcB2A_adaBa"
		}
	}
	
**1.2) Send Autentication token and receive spotprocices data.**

Request.

	POST /spotprices-api/api_get.php?access_token=EBA12_iAAbcB2A_adaBa&service_id=14e1b600b1fd HTTP/1.1
    Host: http://apps.prendario.com
	
	Request Params.
	access_token : Authentication Token received before. (EBA12_iAAbcB2A_adaBa)
	service_id : Service Unique Identifier. e.g. 14e1b600b1fd

Response.

	Content-Type : application/json
	Content:
	
	{
		status: "success",
		response: [
			{
				symbol: "USD",
				date: "2013-03-30 11:32:40",
				value: "1.000000"
			},
			{
				symbol: "EUR",
				date: "2013-03-30 11:32:40",
				value: "1.282200"
			},
			{
				symbol: "MXN",
				date: "2013-03-30 11:32:40",
				value: "0.081215"
			},
			{
				symbol: "BRL",
				date: "2013-03-30 11:32:40",
				value: "0.494022"
			},
			{
				symbol: "AU",
				date: "2013-03-30 11:32:42",
				value: "51.364033"
			},
			{
				symbol: "AG",
				date: "2013-03-30 11:32:42",
				value: "0.909866"
			},
			{
				symbol: "CU",
				date: "2013-03-30 11:32:42",
				value: "0.109219"
			},
			{
				symbol: "PT",
				date: "2013-03-30 11:32:42",
				value: "50.380220"
			}
		]
	}


