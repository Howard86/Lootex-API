---
description: This page describes how you can manage your organization NFTs with Lootex API.
---

# NFT service

{% hint style="warning" %}
**Batch Mint NFTs** and **Synchronize NFT Properties** will cost ETH, please carefully monitor your organization Ethereum balance before proceeding!  
  
Contact Lootex support for more details.
{% endhint %}

{% api-method method="post" host="https://api.forge.lootex.dev" path="/v1/contracts/:contract\_address/assets/batch" %}
{% api-method-summary %}
Batch Mint NFTs
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to mint and send NFT to provided Ehtereum Address  
\(This will cost ETH!\)
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="contract\_address" type="string" required=true %}
Ethereum **address** of NFT smart contract
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=false %}
`application/json`
{% endapi-method-parameter %}

{% api-method-parameter name="ApiKey" type="string" required=true %}
`ApiKey {{api_key}}`  
\(where`api_key` provided by Lootex support\)
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="assets" type="array" required=true %}
`asset_object`
{% endapi-method-parameter %}

{% api-method-parameter name="asset\_object" type="object" required=true %}
must have following keys `to_address, name, description, image_url, background_color`
{% endapi-method-parameter %}

{% api-method-parameter name="to\_address" type="string" required=false %}
Receiver Ethereum address of minting NFT
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
Name of NFT \(single line\)
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
Description of NFT, supporting line  breaks
{% endapi-method-parameter %}

{% api-method-parameter name="image\_url" type="string" required=false %}
Valid image url of NFT
{% endapi-method-parameter %}

{% api-method-parameter name="background " type="string" required=true %}
6-digit color code \(e.g. FFFFFF\)
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Minting NFT request is successfully retrieved and ready to go on blockchain
{% endapi-method-response-example-description %}

```
{
    "assets": [
        {
            "name": "Privileged Explorer",
            "description": "非常早期的數位收藏品探險家，您有澄澈的眼和勇敢的心，往往能夠在大眾尚未看透趨勢時，就不畏質疑採取行動。這是一個全世界只有 100 個的限量徽章，此徽章代表您已經準備好開啟一段壯遊，探索一個鏈接真實的虛擬世界，挖掘尚未被發現的奇珍異寶。\n\n（#17 out of 100）",
            "external_url": "https://dex.lootex.dev",
            "image_url": "https://storage.googleapis.com/lootex-static/MeetTaipei/privileged-explorer.png",
            "background_color": "eeeeee",
            "contract_address": "0xdbba35892f7bf059c65279c0eebd05d9bb00af1f",
            "owner_address": "0x9478e2c334b4d3d0c8aca26ce22809816d227236",
            "token_id": 17,
            "attributes": [
                {
                    "trait_type": "ID Number",
                    "display_type": "number",
                    "is_onchain": false,
                    "value": 17
                },
                {
                    "trait_type": "Rarity",
                    "display_type": "string",
                    "is_onchain": false,
                    "value": "epic"
                },
                {
                    "trait_type": "Issue Date",
                    "display_type": "string",
                    "is_onchain": false,
                    "value": "Nov. 14, 2019"
                }
            ],
            "tx": {
                "id": 3071,
                "hash": "0x5b8285d5ec4b0bddbfc06d6809373eb89c6e1301f2ceb2d3c729d92a225188cd",
                "data": "0xd3fc98640000000000000000000000009478e2c334b4d3d0c8aca26ce22809816d22723600000000000000000000000000000000000000000000000000000000000000110000000000000000000000000000000000000000000000000000000000000060000000000000000000000000000000000000000000000000000000000000005468747470733a2f2f6170692e666f7267652e6c6f6f7465782e6465762f76312f6173736574732f3078646242413335383932463742463035396336353237394330454562643035443962623030616631662f3137000000000000000000000000",
                "status": "QUEUEING"
            }
        },
        {
            "name": "Privileged Explorer",
            "description": "非常早期的數位收藏品探險家，您有澄澈的眼和勇敢的心，往往能夠在大眾尚未看透趨勢時，就不畏質疑採取行動。這是一個全世界只有 100 個的限量徽章，此徽章代表您已經準備好開啟一段壯遊，探索一個鏈接真實的虛擬世界，挖掘尚未被發現的奇珍異寶。\n\n（#13 out of 100）",
            "external_url": "https://dex.lootex.dev",
            "image_url": "https://storage.googleapis.com/lootex-static/MeetTaipei/privileged-explorer.png",
            "background_color": "eeeeee",
            "contract_address": "0xdbba35892f7bf059c65279c0eebd05d9bb00af1f",
            "owner_address": "0x312ee068322071030a4ce5fb197d3179d0e24889",
            "token_id": 13,
            "attributes": [
                {
                    "trait_type": "ID Number",
                    "display_type": "number",
                    "is_onchain": false,
                    "value": 13
                },
                {
                    "trait_type": "Rarity",
                    "display_type": "string",
                    "is_onchain": false,
                    "value": "epic"
                },
                {
                    "trait_type": "Issue Date",
                    "display_type": "string",
                    "is_onchain": false,
                    "value": "Nov. 14, 2019"
                }
            ],
            "tx": {
                "id": 3067,
                "hash": "0x88bc1cf916b897bae78149b91dd89ef2f40c4baa1953612159b0175388c32112",
                "data": "0xd3fc9864000000000000000000000000312ee068322071030a4ce5fb197d3179d0e24889000000000000000000000000000000000000000000000000000000000000000d0000000000000000000000000000000000000000000000000000000000000060000000000000000000000000000000000000000000000000000000000000005468747470733a2f2f6170692e666f7267652e6c6f6f7465782e6465762f76312f6173736574732f3078646242413335383932463742463035396336353237394330454562643035443962623030616631662f3133000000000000000000000000",
                "status": "QUEUEING"
            }
        }
    ],
    "ok": true,
    "total_count": 17
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
`attribute_map` varies from different NFT smart contract, please contact Lootex support for your specific format
{% endhint %}

### Example Request \(cURL\)

```text
curl --location --request POST "{{endpoint}}/v1/contracts/{{contract_address}}/assets/batch" \
--header "Content-Type: application/json" \
--header "Authorization: ApiKey {{api_key}}" \
--data "{
    \"assets\": [
    	{
	        \"to_address\": \"0x312ee068322071030A4Ce5fB197d3179d0e24889\",
	        \"name\": \"Privileged Explorer\",
	        \"description\": \"非常早期的數位收藏品探險家，您有澄澈的眼和勇敢的心，往往能夠在大眾尚未看透趨勢時，就不畏質疑採取行動。這是一個全世界只有 100 個的限量徽章，此徽章代表您已經準備好開啟一段壯遊，探索一個鏈接真實的虛擬世界，挖掘尚未被發現的奇珍異寶。\\n\\n（#13 out of 100）",
	        \"image_url\": \"https://storage.googleapis.com/lootex-static/MeetTaipei/privileged-explorer.png\",
	        \"background_color\": \"eeeeee\",
	        \"attributes_map\": {
	            \"ID Number\": \"13\",
	            \"Rarity\": \"epic\",
	            \"Issue Date\": \"Nov. 14, 2019\"
	        }
    	},
    	{
	        \"to_address\": \"0x9478E2C334B4D3d0C8ACa26CE22809816d227236\",
	        \"name\": \"Privileged Explorer\",
	        \"description\": \"非常早期的數位收藏品探險家，您有澄澈的眼和勇敢的心，往往能夠在大眾尚未看透趨勢時，就不畏質疑採取行動。這是一個全世界只有 100 個的限量徽章，此徽章代表您已經準備好開啟一段壯遊，探索一個鏈接真實的虛擬世界，挖掘尚未被發現的奇珍異寶。\\n\\n（#17 out of 100）",
	        \"image_url\": \"https://storage.googleapis.com/lootex-static/MeetTaipei/privileged-explorer.png\",
	        \"background_color\": \"eeeeee\",
	        \"attributes_map\": {
	            \"ID Number\": \"17\",
	            \"Rarity\": \"epic\",
	            \"Issue Date\": \"Nov. 14, 2019\"
	        }
    	}
	]
}"
```



