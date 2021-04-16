---
title: Använda Domain Connect
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Lär dig hur du arbetar med domänaktiverade domänregistratorer och lägger till din domän i Microsoft 365.
ms.openlocfilehash: 5dec69f70273e6a9430ce5926ed07888e197adcd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860661"
---
# <a name="using-domain-connect"></a>Använda Domain Connect

 **[Läs frågor och svar om domäner](../setup/domains-faq.yml)** om du inte hittar det du letar efter.
  
[Med domän ](https://www.domainconnect.org/) connect-aktiverade registratorer kan du lägga till din domän i Microsoft 365 i en trestegsprocess som bara tar några minuter. 
  
I guiden bekräftar vi bara att du äger domänen och sedan konfigureras domänens poster automatiskt, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, som Teams, fungerar med din domän.
  
> [!NOTE]
> Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domän connect-domänregistratorer som integrerar med Microsoft 365

- [1 &amp; 1 I ENTISKT](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Hannsk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer eller WildWestDomains (GoDaddy-återförsäljare som använder SecureServer DNS-värd)
    - [MadDog Web Hosting](https://maddogwebhosting.com/domains/)
    - [BilligaNamn](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Vad händer med min e-post och webbplats?

När du är klar med konfigurationen uppdateras MX-posten för din domän så att den pekar på Microsoft 365 och all e-post för domänen börjar komma till Microsoft 365. Kontrollera att du har lagt till användare och konfigurerat postlådor i Microsoft 365 för alla som får e-post i din domän!
  
Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är. Konfigurationsstegen för Domain Connect påverkar inte din webbplats.
