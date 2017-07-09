---
layout: post
title:  "Curl"
date:   2017-03-11 07:12:00 +0100
categories: command
---

### Examples

```
gem install colorful_json

curl -i -H "Accept: application/json" -H "Content-Type: application/json" -X GET | cjson

curl -H "Accept: application/xml" -H "Content-Type: application/xml" -X GET http://hostname/resource | xmllint --format
```
