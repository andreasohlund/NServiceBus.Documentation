---
layout:
title: "NServiceBus and BizTalk"
tags: 
origin: http://www.particular.net/Articles/nservicebus-and-biztalk
---
BizTalk is a good centralized message broker with many adapters for third party applications, but service buses are inherently distributed, not centralized. Logical centralization leads to spaghetti code.

Mixing logical orchestration and routing with business logic, data access, and web services calls is not a good idea and leads to slow, unmaintainable code.

NServiceBus guides you away from these dangerous anti-patterns while still providing messaging patterns and integration.

Best of both worlds
-------------------

In many cases you need to integrate your code with existing systems and legacy applications possibly running on different technologies and proprietary protocols. This is a classical Enterprise Application Integration (EAI) situation and is not what service buses are meant to address.

In these cases, between your high-level business services you can use NServicebus, and within the relevant services, behind the service boundary, you can use BizTalk to perform the integration with your existing systems and legacy applications. Here's how it looks:

![How NServiceBus and BizTalk fit together in an architecture](https://particular.blob.core.windows.net/media/Default/images/NServiceBus_biztalk.png "How NServiceBus and BizTalk fit together in an architecture")

As you can see, the use of BizTalk behind a service boundary is something of an implementation/integration detail. By keeping the scope of the problem domain small, using BizTalk for a small orchestration to synchronize customer information between Oracle PeopleSoft and SalesForce won't run into either performance or maintainability problems.

Next steps
----------

Sometimes you need a hammer, sometimes you need a screwdriver, and sometimes you need both. While a Swiss army knife may appear to do both, it is a poor choice for any but the most trivial undertakings.

To learn more about dividing up your architecture into high-level business services, see the [presentation Udi gave on SOA](architectural-principles).

[This download from Microsoft](http://www.microsoft.com/downloads/details.aspx?displaylang=en&FamilyID=b57b7625-7316-4f56-b88e-1fb685efae5b) describes the details of getting NServiceBus and BizTalk to work together, including a whitepaper, code samples, and videos to get you up and running in no time.

If you haven't downloaded NServiceBus yet, [give it a try.](/downloads)

