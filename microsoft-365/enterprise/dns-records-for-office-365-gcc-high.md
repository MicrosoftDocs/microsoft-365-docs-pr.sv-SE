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

*Den här artikeln gäller Office 365 GCC High och Microsoft 365 GCC High*

När du hanterar Office 365-GCC hög måste du lägga till dina SMTP-och SIP-domäner i din Online Services-klient organisation.  Du ska göra detta med den nya-MsolDomain cmdlet i Azure AD PowerShell eller använda [Azure stats Portal](https://portal.azure.us) för att börja lägga till domänen och bevisa ägarskap.

När du har lagt till dina domäner till klient organisationen och validerat kan du använda följande vägledning för att lägga till lämpliga DNS-poster för tjänsterna nedan.  Du kan behöva ändra tabellen nedan för att passa organisationens behov med avseende på den inkommande MX-posten (erna) och eventuella befintliga Exchange Autodiscover-poster.  Vi rekommenderar starkt att koordinera dessa DNS-poster med din meddelande grupp för att undvika avbrott eller problem med att skicka e-post.

## <a name="exchange-online"></a>Exchange Online

| Type (Typ) | Ordningen | Värdnamn | Pekar på adress eller värde | TTL |
| --- | --- | --- | --- | --- |
| MX | siffrorna | @ | *klient organisation*. mail.Protection.Office365.us (se nedan för mer information) | 1 timme |
| TXT | - | @ | v = spf1 inkluderar include SPF. Protection. Office365. USA-alla | 1 timme |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 timme |

### <a name="exchange-autodiscover-record"></a>Autodiscover-post för Exchange

Om du har en lokal Exchange-Server rekommenderar vi att du lämnar din befintliga post på plats medan du migrerar till Exchange Online och uppdaterar den posten när du har slutfört migreringen. 

### <a name="exchange-online-mx-record"></a>Exchange Online MX-post

MX-postens värde för godkända domäner följer ett standardformat enligt ovan: *klient organisation*. mail.Protection.Office365.us, vilket ersätter *klient organisationen* med den första delen av ditt standard klient namn.

Om klient namnet till exempel är contoso.onmicrosoft.us använder du **contoso.mail.Protection.Office365.us** som värde för MX-posten.

## <a name="skype-for-business-online"></a>Skype för företag – Online

### <a name="cname-records"></a>CNAME-poster

| Type (Typ) | Värdnamn | Pekar på adress eller värde | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1 timme |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 timme |

### <a name="srv-records"></a>SRV-poster

| Type (Typ) | Tjänst | Protokoll | Port | Väga | Ordningen | Namn | Mål | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_Transmission | 443 | 9.1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1 timme |
| SRV | \_sipfederationtls | \_TCP | 5061 | 9.1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 timme |

## <a name="additional-dns-records"></a>Ytterligare DNS-poster

> [!IMPORTANT]
> Om du har en befintlig *msoid* CNAME-post i DNS-zonen måste du **ta bort** posten från DNS för närvarande.  Msoid-posten är inkompatibel med Microsoft 365 Enterprise *-appar (tidigare Office 365 ProPlus)* och hindrar aktiveringen från att lyckas.
