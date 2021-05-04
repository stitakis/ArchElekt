# 11. Improve Website availability and customer satisfaction by splitting the website in Customer Website and Employee Website

Date: 2021-04-30

## Status

Approved

## Context

Usage spikes of the system might lead to not beeing able to enter tickets, system freezes and the perception of ticket lost.

## Decision

Split website in Customer Website and Employee Website in order to decouple impact of employee activities from customer activities. We believe this will contribute to improved availability of the system and perception of Customer about the system.

## Consequences

More complexity due to more containers to be deployed and monitored. On the other hand, the system availability and reliability will improve. Also, impact of development changes will be reduced. Changes in one website will not impact the other one.
