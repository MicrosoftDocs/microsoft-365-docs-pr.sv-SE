---
title: Information och resultat från en automatiserad undersökning
description: Du kan visa resultaten och nyckelresultaten under och efter en automatiserad undersökning
keywords: automatiserat, undersöka, resultat, analysera, information, åtgärd, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 02/08/2021
ms.openlocfilehash: 3d278c7fd06b2dd14bd9a8c0dcbe639d3c911828
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068910"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Information och resultat från en automatiserad undersökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

När en automatiserad undersökning körs [](m365d-autoir.md) är information om undersökningen tillgänglig både under och efter den automatiska undersökningsprocessen med Microsoft 365 Defender. Om du har nödvändiga [behörigheter kan](m365d-action-center.md#required-permissions-for-action-center-tasks)du visa de uppgifterna i en vy med undersökningsinformation. Vyn med undersökningsinformation ger dig uppdaterad status och möjlighet att godkänna eventuella väntande åtgärder. 

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

## <a name="new-unified-investigation-page"></a>(NY!) Sida för enhetlig undersökning

Undersökningssidan har nyligen uppdaterats för att inkludera information på dina enheter, e-post och samarbetsinnehåll. Den nya, enhetliga undersökningssidan definierar ett gemensamt språk och ger en enhetlig upplevelse för automatiska undersökningar i [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för Endpoint och Microsoft Defender för [Office 365.](../defender-365-security/defender-for-office-365.md) Välj länken i den gula banderollen som visas på sidan för enhetlig undersökning:
- Alla undersökningssidor i Säkerhets- och & Office 365 ( [https://protection.office.com](https://protection.office.com) )
- Undersökningssida i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )
- Alla funktioner för incidenter eller åtgärdscenter i det förbättrade säkerhetscentret i Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) )

## <a name="open-the-investigation-details-view"></a>Öppna detaljvyn för undersökningen

Du kan öppna vyn med undersökningsinformation med någon av följande metoder:
- [Markera ett objekt i Åtgärdscenter](#select-an-item-in-the-action-center)
- [Välj en undersökning från sidan Incidentinformation](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Markera ett objekt i Åtgärdscenter

I det [förbättrade åtgärdscentret](m365d-action-center.md) () samlas åtgärder på alla dina [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) enheter, e-& och samarbeta innehåll och [](m365d-remediation-actions.md) identiteter. Åtgärder i listan omfattar åtgärder som har vidtagits automatiskt eller manuellt. I Åtgärdscenter kan du visa åtgärder som väntar på godkännande och åtgärder som redan har godkänts eller slutförts. Du kan också gå till mer detaljerad information, till exempel en undersökningssida.

> [!TIP]
> Du måste ha [vissa behörigheter för](m365d-action-center.md#required-permissions-for-action-center-tasks) att godkänna, avvisa eller ångra åtgärder.

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 
2. Välj Åtgärdscenter i **navigeringsfönstret.** 
3. Välj ett **objekt på fliken** **Väntande** eller Historik. Den utfällna rutan öppnas.
4. Granska informationen i det utfällfönster som visas och gör sedan något av följande:
   - Välj **Sidan Öppna undersökning** om du vill visa mer information om undersökningen.
   - Välj **Godkänn** för att påbörja en väntande åtgärd.
   - Välj **Avvisa** för att förhindra att en väntande åtgärd vidtas.
   - Välj **Sök för** att gå till Avancerad [sökning](advanced-hunting-overview.md).

### <a name="open-an-investigation-from-an-incident-details-page"></a>Öppna en undersökning från informationssidan för en händelse

Använd sidan incidentinformation om du vill visa detaljerad information om en händelse, inklusive aviseringar som utlöstes information om berörda enheter, användarkonton eller postlådor.

![Incidentinformation](../../media/mtp-incidentdetails-tabs.png)

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 
2. I navigeringsfönstret väljer du **Incidenter &**  >  **Incidenter.** 
3. Markera ett objekt i listan och välj sedan **Öppna incidentsida**.
4. Välj **fliken Undersökningar** och välj sedan en undersökning i listan. Den utfällna rutan öppnas.
5. Välj **sidan Öppna undersökning.** 

## <a name="investigation-details"></a>Undersökningsinformation

Använd vyn med undersökningsinformation för att se tidigare, aktuella och väntande aktiviteter som hör till en undersökning. Vyn med undersökningsinformation liknar följande bild:

![Undersökningsinformation](../../media/mtp-air-investdetails.png)

I vyn Undersökningsinformation kan du se information om flikarna **Undersökningsdiagram**, Varningar, Enheter, Identiteter, Nyckelresultat, Enheter, Logg och Väntande åtgärder, som beskrivs i följande tabell.       

> [!NOTE]
> Vilka flikar som visas på sidan med undersökningsinformation beror på vad prenumerationen innehåller. Om din prenumeration till exempel inte omfattar Microsoft Defender för Office 365 abonnemang 2 visas inte fliken **Postlådor.**

| Tabb | Beskrivning |
|:--------|:--------|
| **Undersökningsdiagram**   | Ger en visuell representation av undersökningen. Visar enheter och visar hot som hittas, tillsammans med aviseringar och om några åtgärder väntar på godkännande.<br/>Du kan markera ett objekt i diagrammet om du vill visa mer information. Om du till exempel **väljer ikonen Bevis** kommer du till fliken **Bevis** där du kan se identifierade enheter och deras bedömningar. |
| **Varningar**    | Listar aviseringar kopplade till undersökningen. Varningar kan komma från skyddsfunktioner för hot på en användares enhet, i Office-appar, Cloud App Security och andra Microsoft 365 Defender-funktioner.|
| **Enheter** | Visar enheter som ingår i undersökningen tillsammans med deras åtgärdsnivå. (Åtgärdsnivåer motsvarar [automationsnivån för enhetsgrupper](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).) |
| **Postlådor** |Listar postlådor som påverkas av identifierade hot.  |
| **Användare**  | Här listas användarkonton som påverkas av identifierade hot. |
| **Bevis** | Listar bevis som upphöjts av varningar/undersökningar. Omfattar bedömningstillstånd *(skadlig,* misstänkt *eller Inga hot hittades)* och åtgärdsstatus. |
| **Enheter**  | Innehåller information om varje analyserad enhet, inklusive en bedömning för varje typ av enhet *(Skadlig,* Misstänkt eller *Inga hot hittades).*|
|**Logg**    | Visar en kronologisk, detaljerad vy av alla undersökningsåtgärder som har vidtagits efter att en avisering utlösts.|
| **Väntande åtgärder** | En lista med objekt som måste godkännas för att fortsätta. Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () för att godkänna väntande åtgärder. |

## <a name="next-steps"></a>Nästa steg

- [Godkänna eller avvisa åtgärder efter en automatiserad undersökning](m365d-autoir-actions.md)
- [Läs mer om åtgärder](m365d-remediation-actions.md)
