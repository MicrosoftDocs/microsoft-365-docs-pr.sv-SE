---
title: 'Steg 5: optimera prestanda för klienten och Office 365-tjänsten'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Konfigurera TCP-inställningar och Office 365-tjänster för bättre prestanda.
ms.openlocfilehash: e3aefb417330ab791a3dd217e2e34591eba3e1d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805630"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a>Steg 5: optimera prestanda för klienten och Office 365-tjänsten

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![Fas 1 – nätverk](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Du kan öka prestandan genom att finjustera hur TCP (Transmission Control Protocol) fungerar mellan klientenheterna och Office 365-tjänsterna.

Du kan ändra följande TCP-inställningar på klientenheterna för att optimera TCP-prestanda:

- [Skala TCP](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/) så att klientenheten kan skicka fler data innan bekräftelse krävs
- [TCP inaktivitetstid](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/) så att klientenheten kan hantera öppna anslutningar effektivare
- [Maximal storlek på TCP-segmentet](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/) så att klientenheten kan skicka de största datablocken i ett paket
- [Selektiva TCP-bekräftelser](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/) så att klientenheten kan bekräfta mottagna data på ett effektivare sätt

Se följande resurser för att optimera prestandan för Office 365-tjänster:

- [Exchange Online](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [Skype för företag Online](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [SharePoint Online](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [Project Web App i Microsoft Project Online](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](networking-exit-criteria.md#crit-networking-step5) för detta steg.

## <a name="next-step"></a>Nästa steg

[Avslutsvillkor för nätverksinfrastruktur](networking-exit-criteria.md)
