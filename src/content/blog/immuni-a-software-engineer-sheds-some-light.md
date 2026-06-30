---
title: "Immuni: A Software Engineer Sheds Some Light"
description: "An interview with Engineering Manager Christian Sisti discussing Italy's COVID-19 contact tracing app — its architecture, privacy trade-offs, and what made it hard to adopt."
pubDate: 2020-11-24
tags: ["engineering", "privacy", "mobile"]
heroImage: "covid-19_Adam_Niescioruk_Unsplash.png"
heroImageAlt: "Close-up of a COVID-19 test kit"
heroImageCredit: 'Photo by <a href="https://unsplash.com/@adamsky1973">Adam Nieścioruk</a> on <a href="https://unsplash.com/">Unsplash</a>'
---

*This is a self-made translation of an interview conducted by [Diletta Bufo](https://www.ecostampa.it/author/diletta-bufo/) in June 2020. [Here](https://www.ecostampa.it/blog/immuni-lingegnere-informatico-christian-sisti-fa-chiarezza/) you can find the original post. All mistakes are mine. Thanks to my friend Alessio Cortili for putting us in touch.*

---

> I believe that technology can help in putting knowledge into everyone's hands.

The Italian contact tracing application reached two million downloads, even if it can't be activated on every smartphone. On the Google Play Store, on top of that, a curious problem occurred: many users, searching for "Immuni", [downloaded by mistake](https://www.repubblica.it/tecnologia/2020/06/06/news/l-app-immuni-scaricata-1-5-milioni-di-volte-ma-sul-play-store-di-google-molti-la-scambiano-per-un-altra-299473250/) *Immune System*, a British app whose goal is to teach you about the immune system. Thinking it was the anti-COVID app, many people protested by leaving negative reviews since the Italian version wasn't available.

To understand how Immuni works, we interviewed Christian Sisti, 37, Engineering Manager living in Barcelona. Graduated at the University of Pisa, Sisti has been a fellow researcher at [CNR](https://www.area.pi.cnr.it/) in the Human-Computer Interaction (HCI) field.

![Christian Sisti in 2020](../../assets/blog/christian_sisti_2020.png)

---

**Have you downloaded Immuni?**

Yes, I downloaded the iOS version as soon as it became available. I had been following the news about it for some time and I was very curious to evaluate it firsthand. Unfortunately, at the moment, it only works on the Italian territory, but in the future there may be the possibility of integrating it with similar applications developed by other countries. I'm confident!

**Pros and cons of the application. Would you have designed it like this?**

Immuni looks good. The UI design is modern and intuitive. The app is based on the Exposure Notification API, a technology developed in combination by Apple and Google to cope with the Covid-19 emergency. This choice enables privacy — all data is encrypted and no personal information (identity, location, ...) is collected. It is also based on Bluetooth Low Energy, which allows minimizing energy consumption.

**A weak point?**

There are some criticalities. For example, a user may inadvertently turn off the phone's Bluetooth, making Immuni ineffective — a prompt notification could reduce this risk. If the application is uninstalled or the phone replaced, the unique code needed to receive alerts would be lost, making the data collected useless. Finally, it is not compatible with all smartphone models, due to the limitations imposed by the Exposure Notification API itself.

**As a computer engineer, how do you perceive the source code? Well structured or vulnerable?**

It is difficult to have an objective judgment without a careful analysis of each of its parts (iOS, Android, and Backend), which would take time. We are talking about a combination of different technologies that require different levels of specialization. From a quick check, I observed that the development team has chosen recent programming languages, such as Kotlin and Swift.

I noticed sufficient coverage of automatic tests, including the user interface. The code is well structured — you can see that it was written by professionals. The documentation is detailed, making it easier for other developers to approach the codebase. The presence of eventual vulnerabilities should, however, be assessed by penetration testing specialists.

Unfortunately, the fact that the app does not keep track of the user's identity makes it easier for an attacker to pollute the data. This is the cost of privacy. My advice is to keep Immuni always updated to the latest version, as it is in constant development to introduce improvements.

**Hundreds of thousands of people are downloading it, becoming an active part of a network of citizens that protects themselves and others. Do you think technology can make us more responsible?**

As of today millions of people already have Immuni. I believe that technology can help in putting knowledge into everyone's hands — at that point, there would be no more excuses for not doing our part. It is important to consider that the effectiveness of this application heavily depends on the number of people who use it. The higher the number of active users, the greater the potential impact in controlling the Coronavirus. People who get notified of having been in contact with someone affected by Covid-19 are recommended to self-quarantine. It would be nice if the government could guarantee the COVID-19 test for all of them — this would be a further incentive to use Immuni itself.

**What is the purpose of the collected data?**

The data are collected by the Italian government with two aims. The first is to provide the service — in other words, to inform users if they have come into contact with Covid-19 positive people. The second is to process it for research purposes. For example, the data could be used to estimate the number of positives per county. It is worth stating that, in any case, all the information collected will be deleted on 31 December 2020.

**You've been a "brain-drain". Do you plan to return to Italy one day?**

It was not easy to leave Italy, the family, and my friends, but I decided to take courage in both hands and play my cards. At the moment, I am very happy in Barcelona. The city is welcoming, the weather is excellent, and there is the sea! At the same time, the IT industry is expanding, making the city even more interesting from a professional point of view. If I plan to return to Italy? I have asked myself this many times. For now, the Italian panorama does not have much to offer me, especially in the places I love the most. One day... who knows!
