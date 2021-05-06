---
title: Tjänstkryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Sammanfattning Förstå dataåter motståndskraft i Microsoft Office 365.
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "52161789"
---
# <a name="service-encryption"></a>Tjänstkryptering

Utöver kryptering på volymnivå använder du Exchange Online, Microsoft Teams, SharePoint Online och OneDrive för företag också Tjänstkryptering för att kryptera kunddata. Tjänstekryptering ger två alternativ för nyckelhantering:

## <a name="microsoft-managed-keys"></a>Microsoft-hanterade nycklar
Microsoft hanterar alla kryptografiska nycklar, inklusive rotnycklar för tjänstekryptering. Det här alternativet är för närvarande aktiverat som standard Exchange Online, SharePoint Online OneDrive för företag. Microsoft-hanterade nycklar tillhandahåller standardkryptering av tjänster om du inte bestämmer dig för att börja använda kundnyckeln. Om du vid ett senare tillfälle bestämmer dig för att sluta använda kundnyckeln utan att följa datarensningssökvägen förblir dina data krypterade med de Microsoft-hanterade nycklarna. Dina data krypteras alltid på den här standardnivån som minst. 

## <a name="customer-key"></a>Customer Key
Du tillhandahåller rotnycklar som används med tjänstkryptering och hanterar dessa nycklar med Azure-nyckelvalv. Microsoft hanterar alla andra nycklar. Det här alternativet kallas kundnyckel och är för närvarande tillgängligt för Exchange Online, SharePoint Online och OneDrive för företag. (Tidigare kallat Avancerad kryptering med BYOK. Läs [Förbättra transparensen och kontrollen för Office 365 kunder](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) för det ursprungliga tillkännagivandet.)

Tjänstkryptering ger flera fördelar:

- Ger ytterligare ett skyddslager ovanpå BitLocker.

- Det här gör att Windows från åtkomsten till programdata som lagras eller bearbetas av operativsystemet.

- Innehåller ett alternativ för kundnyckel som gör det möjligt för tjänster med flera innehavare att tillhandahålla nyckelhantering per klientorganisation.

- Förbättrar möjligheten Microsoft 365 att uppfylla kraven från kunder som har specifika efterlevnadskrav för kryptering.

Med kundnyckel kan du generera egna kryptografiska nycklar med hjälp av en lokal maskinvarutjänstmodul (HSM) eller Azure-nyckelvalv (AKV). Oavsett hur du skapar nyckeln använder du AKV för att styra och hantera de kryptografiska nycklar som används av Office 365. När dina nycklar lagras i AKV kan de användas som roten till en av nyckelringarna som krypterar postlådedata eller filer.

En annan fördel med kundnyckel är den kontroll du har över möjligheten för Microsoft att bearbeta dina data. Om du vill ta bort data från Office 365, till exempel om du vill avsluta tjänsten hos Microsoft eller ta bort en del av dina data som lagras i molnet, kan du göra det och använda kundnyckel som teknisk kontroll. Genom att ta bort data säkerställer du att ingen, inklusive Microsoft, kan komma åt eller bearbeta data. Kundnyckeln kompletterar och kompletterar Microsofts Lockbox som du använder för att styra Microsofts åtkomst till dina data.

Mer information om hur du ställr in kundnyckel för Microsoft 365 för Exchange Online, Microsoft Teams, SharePoint Online, inklusive gruppwebbplatser och OneDrive för företag, finns i följande artiklar:

- [Tjänstkryptering med kundnyckel](customer-key-overview.md)

- [Konfigurera kundnyckel](customer-key-set-up.md)

- [Hantera kundnyckel](customer-key-manage.md)

- [Rulla eller rotera en kundnyckel eller en tillgänglighetsnyckel](customer-key-availability-key-roll.md)

- [Förstå tillgänglighetsnyckeln](customer-key-availability-key-understand.md)
