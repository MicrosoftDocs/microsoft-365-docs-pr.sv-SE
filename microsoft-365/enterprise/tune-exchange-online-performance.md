---
title: Justera prestanda för Exchange Online
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Den här artikeln innehåller allmänna tips och länkar till andra resurser som beskriver hur du kan förbättra prestanda för Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694759"
---
# <a name="tune-exchange-online-performance"></a>Justera prestanda för Exchange Online

Den här artikeln innehåller allmänna tips och länkar till andra resurser som beskriver hur du kan förbättra prestanda för Exchange Online, särskilt framför en migrering. Den här artikeln är en del av [nätverks planering och prestanda justering för Office 365](https://aka.ms/tune) Project.
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Saker att tänka på för att förbättra Exchange Online-prestanda

För att förbättra migreringens hastighet och minska din organisations bandbredds begränsningar för Exchange Online bör du tänka på följande:
  
- **Minska storleken på post lådan.** Mindre storlek på post lådan förbättrar migrations hastigheten. 
    
- **Använd flytt brev låde funktionen med en Exchange hybrid distribution.** Med en Exchange hybrid distribution, offline mail (i form av. OST-filer) behöver inte laddas ned igen när du migrerar till Exchange Online. Detta minskar avsevärt bandbredds kraven. 
    
- **Schemalägga att post lådorna ska inträffa under perioder med låg Internet trafik och lokal Exchange-användning.** När du schemalägger flyttningar skickas migreringsåtgärder till post lådans replikeringstopologi och kanske inte sker omedelbart. 
    
- **Använd Lean-popouts för Outlook på webben.** Lean popouts ger mindre, mindre minnes krävande versioner av vissa e-postmeddelanden i Microsoft Edge eller Internet Explorer genom att återge vissa komponenter på servern. Mer information finns i [använda Lean popouts för att minska mängden minne som används för att läsa e-postmeddelanden](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).


## <a name="general-advice"></a>Allmänna råd

- Kontrol lera att DNS-sökning för outlook.office.com anger MS-datacenter på en logisk start plats för platsen.

- Sök efter e-postcache och Välj lämpliga alternativ (Re. cachelagring period, cachelagring av delade post lådor, et osv).

- Håll dina Outlook-data från att skicka via VPN-anslutningar (till ett centralt kontor) innan det går via Internet.

- Kontrol lera att dina post lådors data stämmer överens med mapparna begränsningar och objekt.
    
Mer information om prestanda för Exchange-migrering finns i [Office 365-migreringens prestanda och metod tips](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).
  

