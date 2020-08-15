---
title: Ytterligare nätverks säkerhets krav för Office 365 GCC High and DoD
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
description: 'Sammanfattning: Office 365 GCC High and DoD har ytterligare nätverks säkerhets krav'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694609"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Ytterligare nätverks säkerhets krav för Office 365 GCC High and DOD

*Den här artikeln gäller Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High och Microsoft 365 DOD.*

Office 365 GCC High and DOD är säkra moln miljöer för att uppfylla behoven hos Förenta staternas regering och dess leverantörer och entreprenörer.  Dessa moln miljöer har ytterligare nätverks begränsningar för vilka externa slut punkter som tjänsterna tillåts komma åt.

GCC hög och DOD kund planering för att använda federerade identiteter eller hybrid samexistens kan kräva att Microsoft tillåter inkommande och/eller utgående åtkomst till dina befintliga lokala distributioner.  Här är några exempel på dessa aktiviteter:

* Användning av federerade identiteter (med Active Directory Federation Services eller ett likartat stöd för STS)
* Hybrid samexistens med en lokal Exchange-Server eller Skype för företag-distribution
* Migrering av befintliga användar innehåll från ett lokalt system

För att tjänsten ska kunna kommunicera med dina lokala slut punkter **måste** du skicka ett e-postmeddelande till Office 365 Engineering för nätverks ändringar.

> [!WARNING]
> Alla begär Anden har en **tre veckors** SLA och kan inte påskyndas på grund av de kontroll-och distributions ledningar som krävs.  Detta inkluderar inledande nätverks förfrågningar samt eventuella ändringar efter att du har migrerat till tjänsten.  Se till att nätverks teamen är medvetna om tids linjen och inkludera den i deras planerings cyklar.

Skicka ett e-postmeddelande till [Office 365 statligt Lägg](mailto:o365gwlt@microsoft.com) med följande information:

* **Till**: [Office 365 statligt Lägg](mailto:o365gwlt@microsoft.com)
* **Från**: en klient organisations administratör – e-postmeddelandet **måste** matcha en global administratörs kontakt i klient organisationen
* **E-postadress ämne**: Office 365 gcc High Network Request-contoso.onmicrosoft.us (Byt ut mot klient organisationens namn)

Bröd texten i meddelandet bör innehålla följande data:

* Ditt klient namn för Microsoft Online Services (till exempel contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* En distributions lista för e-post som Microsoft kommunicerar med för pågående kommunikation relaterade till nätverks ändringar och/eller uppföljning för ogiltiga undernät
* Ange om du planerar att använda Microsoft Teams hybrid Co-existens med lokala distributioner
* Externt identitets system (till exempel sts.contoso.com) och IP-adressintervall i CIDR-notation (t. 10.1.1.0/28)
* Lista med URL-adresser och IP-adressintervall för den lokala PKI-certifikat i CIDR-notation
* Externt tillgängliga URL-adresser och IP-adressintervall för en Exchange Server-lokal distribution i CIDR-notering
* Externt tillgängliga URL-adresser och IP-adressintervall för en lokal distribution av Skype för företag i CIDR-notering

Av säkerhets-och kontroll skäl bör du tänka på följande:

* Det finns fyra begränsningar för undernät per klient organisation
* Undernät måste vara i CIDR-notation (till exempel 10.1.1.0/28)
* Under nätets intervall får inte vara större än/24
* Vi **kan inte** hantera begär Anden om att tillåta åtkomst till kommersiella moln tjänster (kommersiella Office 365, Google G-Suite, Amazon Web Services, etc.)

När din begäran har tagits emot och godkänts av Microsoft är det ett tre veckors SLA för implementering och kan inte påskyndas.  Du får en första bekräftelse när vi har tagit emot din begäran och en slutgiltig bekräftelse när den har genomförts.
