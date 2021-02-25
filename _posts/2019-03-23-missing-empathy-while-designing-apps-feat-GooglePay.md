---
title: Missing empathy while designing apps feat GooglePay
date: 2019-03-23 00:00:00 Z
categories:
- General
- Technology
layout: post
author: dinakaran
image: assets/images/og_image.jpg
---

Empathy in Design Thinking is one of the most important considerations while designing anything, especially building mobile apps.Empathy helps to understand the user's pain points and how they can be addressed in the best possible ways. It is putting ourselves in the shoes of the customers and help to provide User Experience that is refined, elegant and magical.

> In Design Thinking, empathy is, “deep understanding of the problems and realities of the people you are designing for”. It involves learning about the difficulties people face, as well as uncovering their latent needs and desires in order to explain their behaviours. To do so, we need to have an understanding of the people’s environment, as well as their roles in and interactions with their environment.


[UPI](https://www.npci.org.in/product-overview/upi-product-overview) is the new set of APIs that are provided by a consortium of banks in India and fintech companies can use the core banking services. [Google Pay](https://pay.google.com/intl/en_in/about/) by Google is one such application that has jumped into the bandwagon of providing core banking services by using the APIs.

For the most part, the app is a delight to use. It works flawlessly and I use it regularly for making fund transfers to friends and family. I also use it to make bill payment for a host of different services and experience has been smooth, except when it is not.

### A not-so-great User Experience 

I had a recent experience with Google Pay and its not-so happy-flow in action. Google Pay app can be used to pay for offline transactions in retail stores through a QR code. All that is required is to scan the QR code displayed in the POS and make the transaction from the mobile app. Whenever such payments are made, the common expectation is of these three situations :

- Payment Successful. 
- Payment failed but money credited back instantly. 
- Payment failed but money will be credited back in 2-3 days.


When the payment is successful, money is instantly credited into the seller's account, who can validate and give the goods purchased.

When payment fails, try another payment or use a different mode of payment to complete the transaction. 

But what happened with Google Pay is a 4th option :

- Payment processing - money debited from my account but not credited into the seller's account.

![IMG_20190323_100743.jpg]({{site.baseurl}}/assets/images/IMG_20190323_100743.jpg)


So I'm at the store with the status of '**Payment Processing**'. And the seller is unwilling to give the goods as money is not received in his account. I cannot make one more payment because I'm not sure if my first payment is a success or a failure.

### How Google Pay's customer support spectacularly fails

And this is where Google Pay's customer support is amazing. 

- There is no option to chat with customer support through the app as the option is disabled.
- There is no way to instantly communicate in anyway with the customer support other than waiting for call-back.

![Screenshot_2019-03-23-08-58-56-595_com.google.android.gms.png]({{site.baseurl}}/assets/images/Screenshot_2019-03-23-08-58-56-595_com.google.android.gms.png)


What the app informs you is that the transaction may take upto 7 days to be processed. How would such a design make sense while making a small purchase at a local store! In some cases where the app takes 3 days for a transaction to process , should this important message be displayed when the user is trying to make a transaction in the first place?

As a user, I believed it to be an instantaneous real-time transfer because UPI is based on [IMPS](https://en.wikipedia.org/wiki/Immediate_Payment_Service) where payments are real time and the transactions are either success or failure - nothing in-between. If I was made aware with a warning message that payments are not real-time in Google Pay, then as a user, I would have made an informed decision whether to make the payment or not. 

> The very reason that the message is displayed post the transaction makes me feel betrayed about the whole user experience as the app was more focussed on the happy-flow and encourage users to make payment and such messages that it may take 2-3 days to process would stop the user from making the transaction.

![IMG_20190323_095130.jpg]({{site.baseurl}}/assets/images/IMG_20190323_095130.jpg)


I left the shop informing the seller that I will come and collect the goods once the money is credited into his account. I kept waiting for 3 days but the status was still the same. 

So I used Google Pay's Twitter customer support and they told me to wait for 3 days again, which has actually passed, but the status of the transaction is still **'Payment Processing'**. The transaction had an option of raising a dispute for any transactions post 3 days. I raised a **Dispute Claim** and processing time to settle claim was 2 weeks. In the meantime , the payment transaction status changed to **Success**. I had no clue when the status was changed. Should there not be various stages for a transaction to clarify when the payment was processed and money credited into the seller's account ? There is no such information made available to the users.

![IMG_20190323_095047.jpg]({{site.baseurl}}/assets/images/IMG_20190323_095047.jpg)


### Multiple visits to the shop to complete my shopping

With the dispute claim in  process, I went to the shop again and the shopkeeper confirmed that the money is credited into his account and so I collected my purchase. But then, the disputed claim is also **under process** and am not sure if Google Pay will roll back the transaction,thereby leading to a situation where I received the goods, but transaction rolled back and I owe the seller again.

I requested for customer care call back and I got a call back during which the issue was explained in detail, the customer care acknowledged that many customers face this problem and issue was escalated within Google Pay, but not sure what action would be taken.
> This whole user experience is bad, really bad. What should have been a basic Success or Failure type of transactions ended up me visiting the shop twice, couple of follow up with Google Pay via the app and Twitter leading to terrible user experience.

Empathy is one of the most important aspect during Design Thinking and somehow Google Pay has missed implementing this while designing their app and user journeys. 

This also made me realize how banks handle this much better. Banks while making transactions prompt and inform users upfront about availability and processing of services, good customer support via phone or email that helps to handle these kinds of situation really well. Even other UPI apps like PayTM and PhonePe has better customer support when compared to Google Pay.I sincerely wish Google Pay listens.

Till next time, Cheers
