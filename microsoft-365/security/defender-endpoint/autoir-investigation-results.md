---
title: Information och resultat från en automatiserad undersökning
description: Du kan visa resultaten och nyckelresultaten under och efter en automatiserad undersökning
keywords: automatiserat, undersöka, resultat, analysera, information, åtgärd, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
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
ms.date: 02/02/2021
ms.openlocfilehash: b66640736e9dc3835919e39d482b2d38b0c9dcc7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183687"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Information och resultat från en automatiserad undersökning

**Gäller för:**
- Microsoft Defender för Endpoint

När en automatiserad undersökning [](automated-investigations.md) körs med Microsoft Defender för Endpoint är information om undersökningen tillgänglig både under och efter den automatiska undersökningen. Om du har nödvändiga behörigheter kan du visa de uppgifterna i en vy med undersökningsinformation. Vyn med undersökningsinformation ger dig uppdaterad status och möjlighet att godkänna eventuella väntande åtgärder. 

## <a name="new-unified-investigation-page"></a>(NY!) Sida för enhetlig undersökning

Undersökningssidan har nyligen uppdaterats för att inkludera information på dina enheter, e-post och samarbetsinnehåll. Den nya, enhetliga undersökningssidan definierar ett gemensamt språk och ger en enhetlig upplevelse för automatiska undersökningar i [Microsoft Defender](microsoft-defender-endpoint.md) för Endpoint och Microsoft Defender för [Office 365.](/microsoft-365/security/defender-365-security/office-365-atp) 

> [!TIP]
> Mer information om vad som ändras finns i [(NYTT!) Sida för enhetlig undersökning](/microsoft-365/security/mtp/mtp-autoir-results).

## <a name="open-the-investigation-details-view"></a>Öppna detaljvyn för undersökningen

Du kan öppna vyn med undersökningsinformation med någon av följande metoder:
- [Markera ett objekt i Åtgärdscenter](#select-an-item-in-the-action-center)
- [Välj en undersökning från sidan Incidentinformation](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Markera ett objekt i Åtgärdscenter

I det [förbättrade åtgärdscentret](auto-investigation-action-center.md) [sammanförs åtgärder](manage-auto-investigation.md#remediation-actions) på dina enheter, e-& och samarbetsinnehåll och identiteter. Åtgärder i listan omfattar åtgärder som har vidtagits automatiskt eller manuellt. I Åtgärdscenter kan du visa åtgärder som väntar på godkännande och åtgärder som redan har godkänts eller slutförts. Du kan också gå till mer detaljerad information, till exempel en undersökningssida.

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

1. Gå till [https://security.microsoft.com](https://security.microsoft.com) och logga in. 
2. I navigeringsfönstret väljer du **Incidenter &**  >  **Incidenter.** 
3. Markera ett objekt i listan och välj sedan **Öppna incidentsida**.
4. Välj **fliken Undersökningar** och välj sedan en undersökning i listan. Den utfällna rutan öppnas.
5. Välj **sidan Öppna undersökning.** 

## <a name="investigation-details"></a>Undersökningsinformation

Använd vyn med undersökningsinformation för att se tidigare, aktuella och väntande aktiviteter som hör till en undersökning. Vyn med undersökningsinformation liknar följande bild:

I vyn Undersökningsinformation kan du se information om flikarna **Undersökningsdiagram**, Varningar, Enheter, Identiteter, Nyckelresultat, Enheter, Logg och Väntande åtgärder, som beskrivs i följande tabell.       

> [!NOTE]
> Vilka flikar som visas på sidan med undersökningsinformation beror på vad prenumerationen innehåller. Om din prenumeration till exempel inte omfattar Microsoft Defender för Office 365 abonnemang 2 visas inte fliken **Postlådor.**

| Tabb | Beskrivning |
|:--------|:--------|
| **Undersökningsdiagram**   | Ger en visuell representation av undersökningen. Visar enheter och visar hot som hittas, tillsammans med aviseringar och om några åtgärder väntar på godkännande.<br/>Du kan markera ett objekt i diagrammet om du vill visa mer information. Om du till exempel **väljer ikonen Bevis** kommer du till fliken **Bevis** där du kan se identifierade enheter och deras bedömningar. |
| **Varningar**    | Listar aviseringar kopplade till undersökningen. Varningar kan komma från skyddsfunktioner för hot på en användares enhet, i Office-appar, Cloud App Security och andra Microsoft 365 Defender-funktioner.|
| **Enheter** | Visar enheter som ingår i undersökningen tillsammans med deras åtgärdsnivå. (Åtgärdsnivåer motsvarar [automationsnivån för enhetsgrupper](automation-levels.md).) |
| **Postlådor** |Listar postlådor som påverkas av identifierade hot.  |
| **Användare**  | Här listas användarkonton som påverkas av identifierade hot. |
| **Bevis** | Listar bevis som upphöjts av varningar/undersökningar. Omfattar bedömningstillstånd *(skadlig,* misstänkt *eller Inga hot hittades)* och åtgärdsstatus. |
| **Enheter**  | Innehåller information om varje analyserad enhet, inklusive en bedömning för varje typ av enhet *(Skadlig,* Misstänkt eller *Inga hot hittades).*|
|**Logg**    | Visar en kronologisk, detaljerad vy av alla undersökningsåtgärder som har vidtagits efter att en avisering utlösts.|
| **Väntande åtgärder** | En lista med objekt som måste godkännas för att fortsätta. Gå till Åtgärdscenter [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () för att godkänna väntande åtgärder. |

## <a name="see-also"></a>Se även

- [Granska åtgärdsåtgärder efter en automatiserad undersökning](manage-auto-investigation.md)
- [Visa och ordna kön Microsoft Defender för slutpunktsincidenter](view-incidents-queue.md)