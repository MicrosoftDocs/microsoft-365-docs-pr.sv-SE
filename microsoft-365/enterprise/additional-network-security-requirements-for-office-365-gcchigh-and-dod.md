---
title: Ytterligare nätverkssäkerhetskrav för Office 365 GCC Hög och DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Sammanfattning: Office 365 GCC Hög och DoD har ytterligare nätverksäkerhetskrav'
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926565"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Ytterligare nätverkssäkerhetskrav för Office 365 GCC High and DOD

*Den här artikeln gäller för Office 365 GCC, Office 365 DOD, Microsoft 365 GCC Hög och Microsoft 365 DOD.*

Office 365 GCC Hög och DOD är säkra molnmiljöer för att uppfylla behoven hos myndigheter i USA och dess leverantörer och leverantörer.  De här molnmiljöerna har ytterligare nätverksbegränsningar för vilka externa slutpunkter tjänsterna har tillåtelse att komma åt.

GCC Kunder med hög behörighet och DOD som planerar att använda externa identiteter eller hybrid-samexistens kan kräva att Microsoft tillåter inkommande och/eller utgående åtkomst till dina befintliga lokala distributioner.  Några exempel på sådana aktiviteter är:

* Användning av externa identiteter (med Active Directory Federation Services eller liknande STS)
* Hybridexistens med lokal distribution Exchange Server eller Skype för företag hybriddistribution
* Migrering av befintligt användarinnehåll från ett lokalt system

Om du vill tillåta att tjänsten kommunicerar  med dina lokala slutpunkter måste du skicka ett e-postmeddelande Office 365 teknik för nätverksändringar.

> [!WARNING]
> Alla begäranden har ett **serviceavtal på tre** veckor och kan inte underlättas på grund av de säkerhets- och efterlevnadskontroller och distributionsförlopp som krävs.  Detta inkluderar första onboarding nätverksbegäranden samt eventuella ändringar när du har migrerat till tjänsten.  Kontrollera att nätverksteamen känner till tidslinjen och tar med den i planeringscyklerna.

Skicka ett [e-postmeddelande Office 365 för myndigheter Allow-List förfrågningar](mailto:o365gwlt@microsoft.com) med följande information:

* **Till:** [Office 365 för myndigheter Allow-List Förfrågningar](mailto:o365gwlt@microsoft.com)
* **Från:** En innehavaradministratör – skicka e-postmeddelandet **måste** matcha en global administratörskontakt i klientorganisationen
* **E-postämne:** Office 365 GCC hög nätverksbegäran – contoso.onmicrosoft.us (ersätt med ditt klientnamn)

Brödtexten i meddelandet ska innehålla följande data:

* Namnet på din Microsoft Online Services-klient (till exempel contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* En e-postdistributionslista som Microsoft kommunicerar med för den kommunikation som är relaterad till nätverksändringar och/eller uppföljning för ogiltiga undernät
* Ange om du planerar Microsoft Teams att använda hybridexistens med dina lokala distributioner
* Externt tillgängligt URL-adresssystem (till exempel sts.contoso.com) och IP-adressintervall i CIDR-notation (till exempel. 10.1.1.0/28)
* URL och IP-adressintervall för lokal PKI-certifikatåterkallningslista i CIDR-notation
* Externt tillgängligt URL- och IP-adressintervall för Exchange Server lokal distribution i CIDR-notation
* Externt tillgängligt URL- och IP-adressintervall för Skype för företag lokal distribution i CIDR-notation

Av säkerhetsskäl och efterlevnadsskäl bör du tänka på följande begränsningar för din begäran:

* Det finns en fyra undernätsbegränsning per klientorganisation
* Undernät måste vara i CIDR-notation (till exempel 10.1.1.0/28)
* Undernätsområden kan inte vara större än /24
* Vi **kan** inte ta emot förfrågningar om att tillåta åtkomst till kommersiella molntjänster (Office 365, Google G-Suite, Amazon Web Services osv.)

När din begäran har tagits emot och godkänts av Microsoft finns det ett treveckors SLA för implementering och kan inte genomföras.  Du får en första bekräftelse när vi har fått din begäran och en slutgiltig bekräftelse när den har slutförts.
