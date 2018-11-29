---
title: MenuFinder API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - changelog
  - restaurants
  - categories
  - menus
  - dishes

search: true
---

# Introduction

Welcome to the MenuFinder API! You can use our API to get various informations about the menus proposed by our registered restaurant owners.
This API tries to follow the [json:api](https://jsonapi.org/) specifications as much as possible.

As you will probably notice, our API currently support only ``GET `` requests.

This API documentation page was created with [Slate](https://github.com/lord/slate).

## Inclusion of Related Resources
Since this API tries to follow json:api specifications, all its endpoints support [inclusion of related resources](https://jsonapi.org/format/#fetching-includes) where appropriate.

For readibility reasons, the ``included`` field is never shown in the response examples of endpoints which return a collection of object.<br>
In the other hand, the ``included`` field is shown where appropriate in the response examples of endpoints which return a single object.

## Related Resource Link
Some response documents contains [related resource links](https://jsonapi.org/format/#document-resource-object-related-resource-links)  but these endpoints have not been formally specified in this documentation.<br>
We should study if we should whether specify and implement these endpoints (such as ``api/beta/restaurants/1/menus``) or add a query parameter to the related type endpoint (such as ``api/beta/menus?restaurant=1``) or both.

## API Status
**This is the beta (unstable) version of our REST API**. There will probably be breaking changes until v1 is released, but they will be documented in the changelog below.
