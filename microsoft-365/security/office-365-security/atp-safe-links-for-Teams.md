---
title: ATP Säkra länkar för teams, safelinks, säkra länkar, blockera skadliga länkar, office 365 atp, Teams säkra länkar, stoppa användare från att klicka på dåliga länkar, skadliga länkar
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
description: Team kommer nu att ha tillgång till säkra länkar vid tidpunkten för ditt klick. Oavsett om du använder chattar 1-mot-1-chattar, mellan grupper eller i kanaler och flikar, om du har en prenumeration på Office 365 ATP, har du möjlighet att aktivera och använda den här säkerhetsfunktionen.
ms.openlocfilehash: d7586dba86c7ec9f43457b5510a1255e06bb6bf9
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588282"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a>Säkra länkar i team

> [!IMPORTANT]
> Den här funktionen finns i **Offentlig förhandsversion** för kunder i MICROSOFT Teams Technology Adoption Program (TAP) från och med den 28 februari 2020. Den här anteckningen tas bort från artikeln när säkra länkar för teams är mer allmänt tillgängliga.

Microsoft Teams, ett molnbaserat microsoftprogram för att hantera ditt arbete, använder redan säkra bilagor (för Office 365), men det har nu tillgång till säkra länkar när du klickar. Oavsett om du använder chattar, gruppchattar, kanaler eller flikar, om du har en prenumeration på Office 365 ATP, har du möjlighet att aktivera och använda den här säkerhetsåtgärden. Mer information om licenskrav finns i [Microsoft 365 Licensväg för tjänster på klientnivå.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

Så här fungerar det:

1. När du startar Teams-programmet kontrollerar Microsoft 365 att användaren tillhör en organisation som har Office 365 ATP och att användaren ingår i en aktiv princip för säkra länkar med dess skydd aktiverat för Microsoft Teams.

2. Om ovanstående är sant valideras webbadresser vid klicktillfället i Chattar, Gruppchattar, Kanaler och i flikar för den användaren.

## <a name="what-will-users-experience"></a>Vad kommer användarna att uppleva?

Alla skyddade användare kommer att ha den här upplevelsen med farliga webbadresser:

- Om du klickar på länken från en Teams-konversation, gruppchatt eller från kanaler återges en sida i standardwebbläsaren. Om du klickar på länken från en fäst flik visas sidan i teams-gränssnittet på den fliken och alternativet att öppna i webbläsaren inaktiveras av säkerhetsskäl.

- Den här användaren kommer att blockeras från att gå vidare till webbadressens webbplats.

Om användaren som skickade länken inte skyddas av Office 365 ATP kan han eller hon klicka på webbadressen på sin dator och lösa problemplatsen. Detta gör det dubbelt viktigt för administratörer att vara medvetna om vilka deras skyddade användare är och bör vara.

![En sida med säkra länkar för team som rapporterar en skadlig länk och blockerar överföring till sidan.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

Om du klickar på knappen *Gå bakåt* på den här sidan i Teams stängs den (eller kan det leda till att en tom sida som användarna kan stänga ute). Men om du klickar på länken igen kommer det att resultera i en ny bedömning av webbplatsens rykte så att den här sidan visas igen.

> [!NOTE]
> Vissa Microsoft 365-administratörer aktiverar meddelandet **Fortsätt ändå** på blockeringssidan. Men om Safe Links mäter rykte en webbplats och finner det saknas, bör ingen ytterligare klickning genomföras. Det rekommenderas inte att användare kringgår säkerhetsåtgärder. Vänligen väg in detta i dina överväganden innan du aktiverar Fortsätt ändå.
