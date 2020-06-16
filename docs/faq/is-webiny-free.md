---
id: is-webiny-free
title: Is Webiny free?
sidebar_label: Is Webiny free?
---

Yes, it is! 

Depending on what you use Webiny for, your hosting prices will vary though. If you host a site that rarely changes, you will be hitting the CDN all the time, which results in negligible expenses.

[Our API](/docs/deep-dive/architecture/api) heavily employs AWS Lambda Functions. It might be worth taking a look at [AWS Lambda Pricing](https://aws.amazon.com/lambda/pricing/): most of the regions cost less than 0.3$ per 1 million requests.

But there are plenty of free services out there:
- [MongoDB](https://www.mongodb.com/cloud/atlas) Atlas allows you to host a free MongoDB instance.
- [AWS](https://aws.amazon.com/) allows you to initially deploy services for free.

For development purposes, and even small production apps, free tier will most likely be enough to cover the usage of resources employed by Webiny.