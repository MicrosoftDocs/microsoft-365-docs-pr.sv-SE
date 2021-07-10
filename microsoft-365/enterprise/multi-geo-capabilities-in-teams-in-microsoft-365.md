---
title: Multi-Geo Capabilities i Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Läs mer om Teams fungerar med Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362672"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Multi-Geo capabilities in Microsoft Teams

Med multi geofunktioner i Teams kan Teams lagras i vila på en viss geoplats. Chattdata består av chattmeddelanden, inklusive privata meddelanden, kanalmeddelanden och bilder som används i chattar.

Teams använder den önskade dataplatsen (PDL) för användare och grupper för att avgöra var data ska lagras. Om PDL-data inte anges eller är ogiltiga lagras data på klientorganisationens centrala plats.

## <a name="user-chat"></a>Användarchatt

Användarchatt innehåller 1:1-meddelanden, 1:många och privata mötesmeddelanden.

När en ny användare skapas Teams användarens PDL och lagrar alla chattdata på den geoplatsen.

Om en administratör lägger till eller ändrar PDL för en användare läggs användarens chattdata till i en migreringskö för att flyttas till den angivna geoplatsen för befintliga användare.

Lagringsplatsen för en 1:1- eller en-till-många-chatt baseras på PDL för den person som skapade chatten. Om användarens PDL ändras migreras chatten till den nya geoplatsen. Lagringsplatsen för en möteschatt baseras på mötesorganisatörens PDL.

Du hittar den aktuella platsen för en användares Teams genom att [ansluta Teams PowerShell](/powershell/module/teams/connect-microsoftteams) och köra följande kommando:

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>Kanalmeddelanden

Varje Microsoft 365 har en PDL (Preferred Data Location) som betecknar den geoplats där relaterade data ska lagras. Teams använder PDL för gruppen som är kopplad till varje team för att avgöra var kanalmeddelandedata för teamet ska lagras. Det omfattar chatt som sker i ett kanalmöte.

När en användare skapar ett nytt team avgör den användarens PDL vilken PDL som ska Microsoft 365 gruppen. Grupp-PDL avgör var gruppens data lagras. Om användarens PDL ändras senare ändras inte gruppens PDL.

Om en administratör lägger till eller ändrar PDL för den Microsoft 365-grupp som har stöd för ett team, läggs teamets kanalmeddelandedata till i en migreringskö som ska flyttas till den angivna geoplatsen.

Om du ändrar PDF-Microsoft 365 för gruppen köar Teams data som ska migreras till den valda platsen. Men det migrerar inte automatiskt den SharePoint eller de filer som är associerade med gruppen. Du måste flytta webbplatsen separat genom att följa procedurerna i Flytta [en SharePoint till en annan geoplats.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations) Se till att göra båda stegen för att Teams data och SharePoint för en grupp på olika platser.

För att hitta den aktuella platsen för ett teams data [ansluter du till Teams PowerShell](/powershell/module/teams/connect-microsoftteams) och kör följande kommando:

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>Användarupplevelse

Teams Multi-Geo är sömlös för slutanvändaren. När du ändrar PDL för en användare eller grupp köas respektive data för migreringen och migreringen sker automatiskt utan att påverka användaren eller deras Teams-klient även om de är aktiva medan migreringen sker.

## <a name="see-also"></a>Mer information finns även i

[Microsoft 365 Konfiguration för flera geoklienter](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[Administrera en Multi-Geo-Miljö](administering-a-multi-geo-environment.md)

[Administrera Exchange Online postlådor i en miljö med flera geografiska miljöer](administering-exchange-online-multi-geo.md)
