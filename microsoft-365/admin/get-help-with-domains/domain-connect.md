---
title: Använda domän anslutning
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
description: Lär dig hur du arbetar med domän Connect-reservdomänkontrollanter och lägger till din domän i Microsoft 365.
ms.openlocfilehash: e907317ec5b606c2fe73232a73c9abdfce26feea
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645353"
---
# <a name="using-domain-connect"></a>Använda domän anslutning

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.
  
Med [domän Connect-reservdomänkontrollanter](https://www.domainconnect.org/) kan du lägga till din domän i Microsoft 365 i en tre stegs process som tar minuter. 
  
I guiden bekräftar vi bara att du äger domänen och registrerar sedan automatiskt domänens poster, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, till exempel Teams, fungerar med din domän.
  
> [!NOTE]
> Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domän anslutnings registratorer som integreras med Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer eller WildWestDomains (GoDaddy åter försäljare med SecureServer DNS-värd)
    - [MadDog-domäner](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Vad händer med min e-post och webbplats?

När du har slutfört installationen uppdateras MX-posten för domänen så att den pekar på Microsoft 365 och alla e-postmeddelanden för domänen kommer att komma till Microsoft 365. Kontrol lera att du har lagt till användare och konfigurerat post lådor i Microsoft 365 för alla som får e-post på din domän!
  
Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är. Anvisningarna för att konfigurera domänen påverkar inte din webbplats.
