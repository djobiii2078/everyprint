---
title: EVERYTHING API

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python
  - javascript
  - ruby


includes:
  - verification
  - customers
  - commands
  - printers
  - available_file
  - broadcast
  - feedback
  - errors

search: true
---

# Introduction

Welcome to the EveryPrint API! This API communicates with our database to retrieve information about commands, printers and customers. Since we used `Chatfuel` to interact with our customers,
we had to design a plenty API endpoints which will communicate with `Chatfuel` in order to validate, save, collect and trim user's data.
