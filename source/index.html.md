---
title: Narnoo Live Booking And Reservations API Guide

language_tabs:
  - javascript
  - php
  - python
  - swift

toc_footers:
  - <a href='https://app.narnoo.com'>Sign up to Narnoo</a>

includes:
  - authentication
  - connect
  - product
  - booking
  - validation
  - reservation
  - definitions


search: true
---

# Introduction

<aside class="notice">
Latest documentation update: 25-07-2022.
</aside>

Welcome to the Narnoo live reservations API!

Narnoo now lets you check for product availability, pricing and create reservations for tourism products. Narnoo is not a booking platform, instead it acts as a gateway between major third party reservation systems. These systems include both operator direct reservation systems and tourism wholesalers.

Narnoo requires the distributor to have their own relationships with these booking platforms. You are required to have your own authentication to each system, this way Narnoo makes calls based on your relationships. Narnoo just acts as the gateway so you don't have to develop for each platform individually.

We have language bindings in JavaScript jQuery, PHP cURL, Python and Swift! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

If you have any issues or problems with our API or connecting with a reservations system then please contact us and we will do our best to help.

## Testing Environment

We have set up a testing environment which uses all the reservation systems' testing API calls. This means you can test the API without making real time bookings.

Please contact us at support@narnoo.com in relation to the testing endpoint. We have another form to test here.

> Testing endpoint: https://apis-test.narnoo.com/v1/

<aside class="notice">
Some reservations systems require you to have set up a testing API key. This will need to be entered into your Narnoo account until you are ready to go live.
</aside>

Once you're happy with testing you can change the endpoint URL and start making live calls.

<aside class="notice">
Some reservations systems require you to notify them when you are ready to start making real time calls. They have to update your authentication keys to work with their live API.
</aside>

## Current Reservation Systems

Reservation System | Testing API Keys | Live API Approval | Test Operator Products | Type
--------- | ------- |  ----------- |  ----------- |  -----------
Respax | No | Yes | No | Reservations
Rezdy | Yes | No | Rezdy Demo | Reservations
Website Travel | Yes | Yes | Website Travel Demo | Wholesaler
Fareharbor | Yes | Yes | Fareharbor Demo | Reservations
Procharter | Yes | Yes | Procharter Demo | Reservations
CheckFront | Yes | Supplier | Narnoo Demo | Reservations
Booking Boss | Yes | Yes | "Comming Soon" | Reservations
