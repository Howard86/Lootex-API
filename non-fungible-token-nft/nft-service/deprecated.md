---
description: This page collects deprecated APIs that Forge no longer supported
---

# Deprecated

{% api-method method="post" host="https://api.forge.lootex.dev" path="/v1/contracts/:contract\_address/txs" %}
{% api-method-summary %}
Synchronize NFT Properties
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to update NFT properties, synchronizing on-chain and off-chain data.**\(This will cost ETH!\)**
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

{% api-method-parameter name="Authorization" type="string" required=true %}
`ApiKey {{api_key}}` \(where`api_key` provided by Lootex support\)
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="action" type="string" required=true %}
`SYNCHRONIZE`
{% endapi-method-parameter %}

{% api-method-parameter name="payload" type="object" required=true %}
`{}`
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
NFT minting info is successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "data": [],
  "ok": true,
  "total_count": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Example Request \(cURL\)

```bash
curl --location --request POST "{{endpoint}}/v1/contracts/{{contract_address}}/txs" \
--header "Content-Type: application/json" \
--header "Authorization: ApiKey {{api_key}}" \
--data "{
    \"action\": \"SYNCHRONIZE\",
    \"payload\": {}
}"
```

