---
title: DNS-poster för Office 365 GCC High
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
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Sammanfattning: DNS-poster för Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694522"
---
# <a name="dns-records-for-office-365-gcc-high"></a>DNS-poster för Office 365 GCC High

*Den här artikeln gäller för Office 365 GCC hög och Microsoft 365 GCC hög*

Som en del av onboarding till Office 365 GCC High måste du lägga till dina SMTP- och SIP-domäner till Online Services-klientorganisationen.  Du gör detta med hjälp av New-MsolDomain-cmdleten i Azure AD PowerShell eller använda [Azure Government-portalen](https://portal.azure.us) för att starta processen med att lägga till domänen och bevisa ägarskap.

När du har lagt till domänerna i klientorganisationen och validerat dem kan du använda följande anvisningar för att lägga till lämpliga DNS-poster för tjänsterna nedan.  Du kan behöva ändra tabellen nedan för att passa organisationens behov med avseende på den inkommande MX-posten eller -posterna och eventuella Exchange Autodiscover-poster du har.  Vi rekommenderar att du koordinerar de här DNS-posterna med meddelandeteamet för att undvika avbrott eller felaktig e-postleverans.

## <a name="exchange-online"></a>Exchange Online

| Typ | Prioritet | Värdnamn | Pekar på adress eller värde | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *klientorganisations*-mail.protection.office365.us (se nedan för ytterligare information) | 1 timme |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1 timme |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 timme |

### <a name="exchange-autodiscover-record"></a>Exchange Post för automatisk upptäckt

Om du har Exchange Server lokalt rekommenderar vi att du lämnar den befintliga posten på plats medan du migrerar till Exchange Online och uppdaterar posten när du har slutfört migreringen. 

### <a name="exchange-online-mx-record"></a>Exchange Online MX Record

MX-postvärdet för dina godkända domäner följer ett standardformat som anges *ovan:* klientorganisationens .mail.protection.office365.us, och ersätter klientorganisationen med den första delen av standardklientnamnet. 

Om ditt klientnamn till exempel är contoso.onmicrosoft.us, använder du **contoso.mail.protection.office365.us** som värde för MX-posten.

## <a name="skype-for-business-online"></a>Skype för företag – Online

### <a name="cname-records"></a>CNAME-poster

| Typ | Värdnamn | Pekar på adress eller värde | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1 timme |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 timme |

### <a name="srv-records"></a>SRV-poster

| Typ | Tjänst | Protokoll | Port | Vikt | Prioritet | Namn | Mål | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1 timme |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 timme |

## <a name="additional-dns-records"></a>Ytterligare DNS-poster

> [!IMPORTANT]
> Om du har en befintlig *msoid* CNAME-post i din DNS-zon måste **du ta** bort posten från DNS för stunden.  Msoid-posten är inte kompatibel med Microsoft 365 Enterprise *(tidigare Office 365 ProPlus)* och kommer att förhindra att aktiveringen lyckas.
