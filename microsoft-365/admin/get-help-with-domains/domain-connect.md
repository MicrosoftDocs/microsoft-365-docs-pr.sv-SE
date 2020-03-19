---
title: Använda domänanslutning
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Lär dig hur du arbetar med Domain Connect-aktiverade registratorer och lägger till din domän i Microsoft 365.
ms.openlocfilehash: 59e2f94fe83f87a5426064e49f0441356fbd732e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42811219"
---
# <a name="using-domain-connect"></a>Använda domänanslutning

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.
  
[Med Domänanslutningaktiverade](https://www.domainconnect.org/) registratorer kan du lägga till din domän i Microsoft 365 i en trestegsprocess som tar minuter. 
  
I guiden bekräftar vi bara att du äger domänen och sedan automatiskt konfigurerar domänens poster, så e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, till exempel Teams, fungerar med din domän.
  
> [!NOTE]
> Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domain Connect-registratorer som integreras med Microsoft 365

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg (på 80)](https://www.123-reg.co.uk/)
- [Godaddy](https://www.godaddy.com/)
- [Wordpress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple (på annat sätt)](https://mediatemple.net/)
- SecureServer eller WildWestDomains (GoDaddy-återförsäljare som använder SecureServer DNS-hosting)
    - [MadDog-domäner](https://www.maddogdomains.com/)
    - [BilligaNamn](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Vad händer med min e-postadress och hemsida?

När du har konfigurerat installationen uppdateras MX-posten för domänen för att peka på Microsoft 365 och all e-post för domänen börjar komma till Microsoft 365. Kontrollera att du har lagt till användare och konfigurerat postlådor i Office 365 för alla som får e-post i din domän.
  
Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är. Installationsstegen för Domain Connect påverkar inte din webbplats.
