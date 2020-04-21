---
title: Gå till åtgärdscentret för att visa och godkänna dina automatiska undersöknings- och reparationsuppgifter
description: Använda Åtgärdscentret för att visa information om automatisk undersökning och godkänna väntande åtgärder
keywords: Åtgärdscenter, hotskydd, utredning, varning, väntande, automatiserad, upptäckt
search.appverid: met150
ms.prod: M365-security-compliance
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: c3406ebf5962d6f0ac08c1ee280bab725cf1c3bd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626964"
---
# <a name="the-action-center"></a>Åtgärdscentret

**Gäller:**
- Microsoft Hotskydd

Använd åtgärdscentret för att se resultatet av aktuella och tidigare undersökningar på organisationens enheter och postlådor. Beroende på vilken typ av hot och resulterande dom, [reparationsåtgärder](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) sker automatiskt eller efter godkännande av organisationens säkerhetsoperationer team. Alla åtgärder för reparation, oavsett om de väntar på godkännande eller redan har godkänts, konsolideras i åtgärdscentret. 

![Åtgärdscenter](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>En "enda glasruta" upplevelse

Åtgärdscentret ger en "enda glasruta" för aktiviteter, till exempel:
- Godkänna pågående saneringsåtgärder.
- Visa en granskningslogg över redan godkända reparationsåtgärder. Och
- Granska slutförda reparationsåtgärder.

Säkerhetsoperationsteamet kan arbeta mer effektivt och ändamålsenligt eftersom åtgärdscentret ger en omfattande vy över Microsoft Threat Protection på jobbet.

## <a name="go-to-the-action-center"></a>Gå till åtgärdscentret

1. Gå [https://security.microsoft.com](https://security.microsoft.com) till och logga in. 

2. Välj **Åtgärdscenter**i navigeringsfönstret . 

3. I åtgärdscentret visas två flikar: **Väntande** och **Historik**.

    - På fliken **Väntande** listas undersökningar som kräver granskning och godkännande av någon i säkerhetsoperationsteamet för att fortsätta. Se till att granska och vidta åtgärder för väntande objekt som du ser här.

    - På fliken **Historik** visas tidigare undersökningar och åtgärder för reparation som har vidtagits automatiskt. Du kan visa data för den senaste dagen, veckan, månaden eller sex månader.

4. Om du bara vill visa de kolumner som du vill visa väljer du **Anpassa kolumner**.<br/>![Åtgärdscenter i Microsofts hotskydd](../../media/mtp-action-center.png)

5. Välj ett objekt i listan om du vill visa mer information om en undersökning. Utredningens detaljvy öppnas.<br/>![Detaljer om undersökningen](../../media/mtp-air-investdetails.png)

    - Om undersökningen gäller e-postinnehåll (t.ex. är entiteten en postlåda) kan undersökningsinformation som finns öppen i Säkerhets- & Compliance Center ([https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation)). 

    - Om undersökningen omfattar en enhet, utredningsuppgifter öppna[https://security.microsoft.com](https://security.microsoft.com)i säkerhetscentret ( ). 

> [!TIP]
> Om du tror att något har missats eller felaktigt upptäckts av automatiska undersöknings- och svarsfunktioner i Microsoft Threat Protection, låt oss veta! Se [Så här rapporterar du falska positiva identifieringar/negativ i automatiska funktioner för undersökning och svar (AIR) i Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

## <a name="required-permissions-for-action-center-tasks"></a>Nödvändiga behörigheter för åtgärdscenteraktiviteter

Om du vill godkänna eller avvisa väntande åtgärder i åtgärdscentret måste du ha behörigheter tilldelade enligt följande tabell:

|Åtgärd för reparation |Obligatoriska roller och behörigheter |
|--|----|
|Microsoft Defender ATP-reparation (enheter) |Rollen Säkerhetsadministratör som tilldelats i[https://portal.azure.com](https://portal.azure.com)Azure Active Directory ( )[https://admin.microsoft.com](https://admin.microsoft.com)eller Microsoft 365 administrationscenter ( )<br/>--- eller ---<br/>Active remediation actions-rollen som tilldelats i Microsoft Defender ATP <br/> <br/> Mer information finns i följande resurser: <br/>- [Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Skapa och hantera roller för rollbaserad åtkomstkontroll (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Office 365 ATP-reparation (Office-innehåll och e-post)  |Rollen Säkerhetsadministratör som tilldelats i[https://portal.azure.com](https://portal.azure.com)Azure Active Directory ( )[https://admin.microsoft.com](https://admin.microsoft.com)eller Microsoft 365 administrationscenter ( )<br/>--- och --- <br/>Sök- och rensningsrollen som tilldelats[https://protection.office.com](https://protection.office.com)Security & Compliance Center ( ) <br/><br/>**VIKTIGT:** Om du bara har rollen Säkerhetsadministratör tilldelad i Security & Compliance Center kan du inte komma åt funktionerna i Åtgärdscenter eller Microsoft Threat Protection. Du måste ha rollen Säkerhetsadministratör tilldelad i Azure Active Directory eller Microsoft 365 admincenter. <br/><br/>Mer information finns i följande resurser: <br/>- [Administratörsrollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Behörigheter i Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Användare som har rollen Global administratör tilldelad i Azure Active Directory kan godkänna eller avvisa väntande åtgärder i åtgärdscentret. Som bästa praxis bör dock din organisation begränsa antalet personer som har rollen Global administratör tilldelad. Vi rekommenderar att du använder säkerhetsadministratören, aktiva reparationsåtgärder och sök- och rensningsroller som anges ovan för behörigheter till åtgärdscenter.

## <a name="next-steps"></a>Nästa steg 

- [Läs mer om incidenter i Microsoft Threat Protection](incidents-overview.md)

- [Visa resultaten av en automatiserad undersökning](mtp-autoir-results.md)

- [Läs mer om jakt i Microsofts hotskydd](advanced-hunting-overview.md)

