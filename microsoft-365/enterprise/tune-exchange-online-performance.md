---
title: Justera Exchange Online-prestanda
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
description: Den här artikeln innehåller allmänna tips och länkar till andra resurser som beskriver hur du förbättrar prestanda för Exchange Online.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909448"
---
# <a name="tune-exchange-online-performance"></a>Justera Exchange Online-prestanda

Den här artikeln innehåller allmänna tips och länkar till andra resurser som beskriver hur du förbättrar prestanda för Exchange Online, särskilt före migreringen. Den här artikeln är en del [av Nätverksplanering och prestandajustering för Office 365](./network-planning-and-performance.md) projekt.
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Saker att tänka på för att förbättra Exchange Online prestanda

För att förbättra migreringens hastighet och minska organisationens bandbreddsbegränsningar för Exchange Online ska du tänka på följande:
  
- **Minska postlådestorleken.** Mindre postlådestorlek förbättrar migreringshastigheten. 
    
- **Använd postlådans flyttfunktioner med en Exchange hybriddistribution.** Med en Exchange hybriddistribution kan offline-e-post (i form av . OST-filer) behöver inte laddas ned på ny tid när du migrerar till Exchange Online. Det här minskar avsevärt bandbreddskraven för hämtning. 
    
- **Schemalägg postlådeflyttningar vid tider med låg Internettrafik och låg lokal Exchange användning.** När du schemalägger flyttningar skickas migreringsbegäranden till postlådereplikeringsproxyn och sker kanske inte omedelbart. 
    
- **Använd magera popup-Outlook för webben.** Med Mindre, minnesintensiva versioner av vissa e-postmeddelanden i Microsoft Edge eller Internet Explorer kan du återge vissa komponenter på servern. Mer information finns i Använda [mindre använda popup-fönster för att använda mindre minne när du läser e-postmeddelanden.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)


## <a name="general-advice"></a>Allmänna råd

- Kontrollera att DNS-uppslag för outlook.office.com anger MS-datacentret på en logisk postplats för din plats.

- Undersöka postlådans cachelagring och välj lämpliga alternativ (åter. cachelagringsperiod, cachelagring av delad postlåda och osv.

- Se till Outlook data inte passerar över VPN-anslutningar (till ett centralt kontor) innan det passerar via Internet.

- Se till att dina postlådedata följer begränsningarna för mapp- och artikelbelopp.
    
Mer information om hur Exchange migreringsprestanda finns i Office 365 [migreringsprestanda och metodtips.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)
