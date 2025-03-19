# Account Management

## Overview

This feature allows users to **view their wallet details**, including **wallet address, UTXOs (Unspent Transaction Outputs), assets, and NFTs** directly within the extension

## **User Story**

> **As a user, I want to view my wallet address, UTXO, assets, and NFTs within the extension.**

## **User Flow**

{% stepper %}
{% step %}
User navigate to the **"Wallet"** page in the extension.
{% endstep %}

{% step %}
The extension makes an API call to retrieve wallet data.
{% endstep %}

{% step %}
The backend interacts with the blockchain provider to retrieve and process wallet data before responding to the extension
{% endstep %}

{% step %}
The **wallet address, UTXOs, assets, and NFTs** are displayed.
{% endstep %}
{% endstepper %}

## User Flow Diagrams

<figure><img src="../../.gitbook/assets/account-management (1).png" alt=""><figcaption></figcaption></figure>

## Troubleshooting & Common Issues

| **Issue**                       | **Possible Cause**        | **Solution**                  |
| ------------------------------- | ------------------------- | ----------------------------- |
| Unable to retrieve the template | API request failed        | Check console logs for errors |
| "Request Timed Out" error       | Network issue or API down | Retry after a few minutes     |

## API Reference

### Get UTXOs

Get UTXOs of address

<mark style="color:green;">`GET`</mark> /wallet/utxos

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Query Params**

| Name    | Type   | Description            |
| ------- | ------ | ---------------------- |
| address | string | Cardano wallet address |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "data": {
        "utxos": [
            {
                "address": "addr_test1qr7xvrx6zea988hz5juazw32qyfmh5jg6z9euursqs390pz62landnfc3ggslmdvaglwmuquuxt2pkkxctzp0adfrxasyzm9m9",
                "tx_hash": "2471655859eb683cf5d9bdf79bc320c8e262b8decb1ee163aed65c74b47aaa41",
                "tx_index": 1,
                "output_index": 1,
                "amount": [
                    {
                        "unit": "lovelace",
                        "quantity": "1137840"
                    },
                    {
                        "unit": "5498906fdd86ac9b36f18302273b1fbe89b24ddb228d6eeea01af11874657374",
                        "quantity": "1"
                    }
                ],
                "block": "4928ea0f74daa61e6b3e5c88c78454a38fdaed39d5d8b7ce67938e31f43da5fb"
            },
            {
                "address": "addr_test1qr7xvrx6zea988hz5juazw32qyfmh5jg6z9euursqs390pz62landnfc3ggslmdvaglwmuquuxt2pkkxctzp0adfrxasyzm9m9",
                "tx_hash": "e19d0a0c7b68b2b7d6af8fa0b5a9d19a49a9adadedf0d0f71801b69c5cc0c047",
                "tx_index": 0,
                "output_index": 0,
                "amount": [
                    {
                        "unit": "lovelace",
                        "quantity": "1150770"
                    },
                    {
                        "unit": "c79cd50a487a9ee340ac945492ba2387b43bb110a1149966c192f1474e667454657374",
                        "quantity": "1"
                    }
                ],
                "block": "23f7508abbcc14776f263cf20a0f9d2d485fe2e71899bbbf315b6ffbe54cf1f0"
            }
        ]
    },
    "msg": "OK",
    "code": 201
}
```
{% endtab %}

{% tab title="500" %}
```json
{
  "code": ,
  "msg": "",
  "data": {
  
  }
}
```
{% endtab %}
{% endtabs %}

### Get NFTs

Get NFTs of address

<mark style="color:green;">`GET`</mark> /wallet/nfts

Get&#x20;

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Query Params**

| Name    | Type   | Description            |
| ------- | ------ | ---------------------- |
| address | string | Cardano wallet address |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "data": {
        "nfts": [
            {
                "unit": "5498906fdd86ac9b36f18302273b1fbe89b24ddb228d6eeea01af11874657374",
                "quantity": "1",
                "assetDetails": {
                    "asset": "5498906fdd86ac9b36f18302273b1fbe89b24ddb228d6eeea01af11874657374",
                    "policy_id": "5498906fdd86ac9b36f18302273b1fbe89b24ddb228d6eeea01af118",
                    "asset_name": "74657374",
                    "fingerprint": "asset19dhuvw96yxnxgeatqx7ph7rqdwtekrccxr0cx9",
                    "quantity": "1",
                    "initial_mint_tx_hash": "baa549172566c96d198583d2d8450b06f1852bc039f570cc39a0cb4f85bbb296",
                    "mint_or_burn_count": 1,
                    "onchain_metadata": {
                        "name": "test",
                        "image": "test",
                        "mediaType": "image/png",
                        "description": "test"
                    },
                    "onchain_metadata_standard": "CIP25v1",
                    "onchain_metadata_extra": null,
                    "metadata": null
                }
            }
        ]
    },
    "msg": "OK",
    "code": 201
}
```
{% endtab %}

{% tab title="500" %}
```json
{
  "code": ,
  "msg": "",
  "data": {
  
  }
}
```
{% endtab %}
{% endtabs %}

## Demo

### Screenshot

<figure><img src="../../.gitbook/assets/account-management.png" alt=""><figcaption></figcaption></figure>

### Video

{% embed url="https://youtu.be/qrJtfNQOvrg" %}

🔹 _For any issues, please refer to the_ [_Troubleshooting Section_](account-management.md#troubleshooting-and-common-issues) _or open an Issue on GitHub._
