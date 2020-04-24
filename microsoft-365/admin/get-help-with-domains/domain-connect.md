---
title: Använda Domain Connect
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Lär dig hur du arbetar med Domain Connect-aktiverade registratorer och lägger till din domän i Microsoft 365.
ms.openlocfilehash: 6a86783ca880f6cb4ea833e4c2b659de4da5e5c1
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2020
ms.locfileid: "43800017"
---
# <a name="using-domain-connect"></a>Använda Domain Connect

 **[Läs frågor och svar om domäner](../setup/domains-faq.md)** om du inte hittar det du letar efter.
  
[Med Domain](https://www.domainconnect.org/) Connect-aktiverade registratorer kan du lägga till din domän i Microsoft 365 i en trestegsprocess som tar minuter. 
  
I guiden bekräftar vi bara att du äger domänen och sedan automatiskt konfigurerar domänens poster, så att e-post kommer till Microsoft 365 och andra Microsoft 365-tjänster, som Teams, fungerar med din domän.
  
> [!NOTE]
> Se till att inaktivera popup-blockerare i webbläsaren innan du startar installationsguiden.
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Domain Connect-registratorer som integreras med Microsoft 365

- [1&amp;1 IONOS](https://www.1and1.com/)
- [123Reg (På andra)](https://www.123-reg.co.uk/)
- [Godaddy](https://www.godaddy.com/)
- [Wordpress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer eller WildWestDomains (GoDaddy-återförsäljare med SecureServer DNS hosting)
    - [MadDog domäner](https://www.maddogdomains.com/)
    - [BilligaNamn](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a>Vad händer med min e-post och webbplats?

När du är klar med installationen uppdateras MX-posten för din domän så att den pekar på Microsoft 365 och all e-post för din domän börjar komma till Microsoft 365. Kontrollera att du har lagt till användare och konfigurerat postlådor i Office 365 för alla som får e-post i din domän.
  
Om du har en webbplats som du använder med ditt företag kommer den att fortsätta fungera där den är. Installationsstegen För Domain Connect påverkar inte din webbplats.
