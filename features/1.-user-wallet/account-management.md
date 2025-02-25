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

<figure><img src="../../.gitbook/assets/account-management.png" alt=""><figcaption></figcaption></figure>

## Troubleshooting & Common Issues

Coming soon

## API Reference

Coming soon

## Demo

Coming soon

🔹 _For any issues, please refer to the_ [_Troubleshooting Section_](account-management.md#troubleshooting-and-common-issues) _or open an Issue on GitHub._
