---
title: ATP-säkra Länkar för team, safelinks, säkra länkar, blockera skadliga länkar, Office 365 ATP, teams Safe Links, hindra användare från att klicka på felaktiga länkar, illasinnade länkar
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Teams kommer nu att ha till gång till säkra länkar när du klickar på. Oavsett om du använder chattar 1-i-1-chatt, mellan grupper eller i kanaler och på flikar, om du har ett abonnemang på Office 365 ATP kan du aktivera och använda den här säkerhetsfunktionen.
ms.openlocfilehash: 362fb37b352a77aea07b899b707dbf4ac3d440d5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198757"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a>Säkra länkar i Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Den här funktionen är i **offentlig för hands version** för kunder i Microsoft Teams-programmet (tryck) enligt februari 2020. Den här anteckningen tas bort från artikeln när säkra Länkar för team är mer tillgängligt.

Microsoft Teams, ett Microsoft Cloud-baserat program för att hantera ditt arbete använder redan säkra bifogade filer (för Office 365), men nu kommer du åt säkra länkar när du klickar på den. Oavsett om du använder chattar, gruppchatt, kanaler eller flikar om du har ett abonnemang på Office 365 ATP kan du aktivera och använda den här säkerhets åtgärden. Mer information om licensierings kraven finns i [Microsoft 365 licens rådgivning för tjänster på klient organisations nivå](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

Så här fungerar det:

1. När du startar Teams-programmet kontrollerar Microsoft 365 att användaren tillhör en organisation som har Office 365 ATP och att användaren ingår i en Active Safe Links-princip med skydd aktiverat för Microsoft Teams.

2. Om ovanstående stämmer val IDE ras URL-adresser vid tiden för Klicka i chatt, gruppchattar, kanaler och på flikar för den användaren.

## <a name="what-will-users-experience"></a>Vad händer med användare?

Alla skyddade användare får denna upplevelse med farliga webb adresser:

- Om länken klickade på en grupp konversation, gruppchatt eller från kanaler visas en sida i standard webbläsaren. Om länken klickade på en Fäst flik visas sidan i användar gränssnittet på fliken och alternativet att öppna i webbläsaren kommer att avaktiveras av säkerhets skäl.

- Denna användare kommer att blockeras från att gå vidare till URL-adressen.

Om användaren som skickade länken inte är skyddad av Office 365 ATP är han eller hon fri att klicka på URL-adressen på sin dator och lösa problemet. Det gör det dubblerat viktigt för administratörer att vara medvetna om vilka deras skyddade användare och bör vara.

![En Safe Links för Teams-sidan rapporterar en skadlig länk och blockerar transitering till sidan.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Om du klickar på knappen *gå tillbaka* på den här sidan i Teams stängs det (eller så kan användarna få en tom sida). Om du klickar på länken igen kommer du att få en ny utvärdering av webbplatsens rykte så att sidan visas igen.

> [!NOTE]
> I vissa Microsoft 365-administratörer aktive ras meddelandet **Fortsätt ändå** på sidan blockera. Men om Safe Links mäter ryktet hos en webbplats och hittar den inte längre behöver du bara klicka-och-genom. Det rekommenderas inte att användare kringgår säkerhets åtgärder. Var god ange detta innan du aktiverar Fortsätt ändå.
