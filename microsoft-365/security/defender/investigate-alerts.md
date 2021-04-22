---
title: Analysera aviseringar i Microsoft 365 Defender
description: Analysera aviseringar som visas på olika enheter, användare och postlådor.
keywords: incidenter, aviseringar, undersöker, analyserar, svar, korrelation, attack, datorer, enheter, användare, identiteter, identitet, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 18b4df6a2dbb22235d6781f1430f7a75e319fbcf
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939548"
---
# <a name="analyze-alerts-in-microsoft-365-defender"></a>Analysera aviseringar i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Aviseringar utgör grunden för alla händelser och anger förekomsten av skadliga eller misstänkta händelser i din miljö. Aviseringar är vanligtvis en del av en bredare attack och ger ledtrådar om en händelse.

I Microsoft 365 Defender sammanställs relaterade aviseringar till [formulärincidenter](incidents-overview.md). Incidenter ger alltid ett bredare sammanhang för en attack, men det kan vara värdefullt att analysera aviseringar när en djupare analys krävs. 

I **kön Aviseringar** visas den aktuella uppsättningen aviseringar. Du kommer till aviseringskön från **incidenter &** aviseringar > aviseringar i snabbstarten av säkerhetscentret för Microsoft 365 [(security.microsoft.com).](https://security.microsoft.com)

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Exempel på aviseringskön":::

Aviseringar från olika Microsoft-säkerhetslösningar som Microsoft Defender för Endpoint, Microsoft Defender för Office 365 och Microsoft 365 Defender visas här.

Som standard visar aviseringskön i Säkerhetscenter för Microsoft 365 de nya och pågående aviseringarna från de senaste 30 dagarna. Den senaste aviseringen visas högst upp i listan så att du kan se den först. 

Från standardaviseringskön kan  du välja  Filter för att visa ett filterfönster där du kan ange en delmängd av aviseringarna. Här är ett exempel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Exempel på filterfönstret för aviseringskön":::

Du kan filtrera aviseringar enligt följande kriterier:

- Allvarlighetsgrad
- Status
- Kategori
- Identifieringskälla
- Taggar
- Princip
- Påverkade tillgångar

## <a name="analyze-an-alert"></a>Analysera en avisering

Markera namnet på aviseringen om du vill se huvudaviseringssidan. Här är ett exempel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exempel på informationssidan för en avisering i Säkerhetscenter för Microsoft 365":::

Du kan också välja **åtgärden Öppna huvudaviseringssidan** i **fönstret Hantera** avisering.

En aviseringssida består av följande avsnitt: 

- Aviseringsartikel
- Åtgärder som vidtas (inklusive påverkade tillgångar)
- Relaterade händelser
- Sammanfattningsinformation

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exempel på informationssidan för en avisering i Säkerhetscenter för Microsoft 365":::

På en aviseringssida kan du välja ellipsen (**...**) bredvid en enhet för att se tillgängliga åtgärder, till exempel öppna sidan för specifika tillgångar eller vidta specifika åtgärdssteg.

### <a name="analyze-affected-assets"></a>Analysera påverkade tillgångar

Avsnittet **Åtgärder som** vidtas har en lista över påverkade tillgångar, till exempel postlådor, enheter och användare som påverkas av den här aviseringen. 

Du kan också välja Visa i  **åtgärdscenter** för att visa fliken Historik i Åtgärdscenter  i Säkerhetscenter för Microsoft 365. 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>Spåra en aviserings roll i aviseringsartikeln

I aviseringsartikeln visas alla tillgångar eller enheter som är relaterade till aviseringen i en processträdvy. Aviseringen i rubriken är den som är i fokus när du först kommer till den valda aviseringens sida. Tillgångar i aviseringsartikeln är expanderbara och klickbara. De ger ytterligare information och underlättar ditt svar genom att göra det möjligt för dig att vidta åtgärder direkt i samband med aviseringssidan. 

> [!NOTE]
> Avsnittet med aviseringsavsnittet kan innehålla fler än en avisering, och ytterligare aviseringar om samma körningsträd visas före eller efter den avisering du har markerat.

### <a name="view-more-alert-information-on-the-details-page"></a>Visa mer aviseringsinformation på informationssidan

På informationssidan visas information om den valda aviseringen, med information och relaterade åtgärder. Om du väljer någon av de berörda tillgångarna eller enheterna i aviseringsinformationen ändras informationssidan för att ge sammanhangsberoende information och åtgärder för det valda objektet.

När du har valt en intresseenhet ändras informationssidan för att visa information om den valda entitetstypen, historisk information när den är tillgänglig och alternativ för att vidta åtgärder på den här enheten direkt från aviseringssidan.

## <a name="manage-alerts"></a>Hantera varningar

Om du vill hantera en avisering markerar du aviseringen i kön med aviseringar på raden så att fönstret **Hantera avisering** visas. Här är ett exempel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Exempel på sammanfattningsfönstret för en avisering":::

I **aviseringsfönstret** Hantera kan du ange:

- Aviseringsstatus (Ny, Löst, Pågår).
- Aviseringens klassificering (Inte inställd, Sant meddelande, Falsk avisering).
- För klassificering som en verklig avisering anger du typen av hot för aviseringen i **fältet Determination** .
- En kommentar om aviseringen.

> [!NOTE]
> Ett sätt att hantera aviseringar via taggar. Taggningsfunktioner för Microsoft Defender för Office 365 distribueras stegvis och är för närvarande i förhandsversion. <br>
> För närvarande används ändrade taggnamn bara på aviseringar som skapats *efter* uppdateringen. Aviseringar som har genererats innan ändringen återspeglar inte det uppdaterade taggnamnet. 

Från det här fönstret kan du även utföra följande ytterligare åtgärder: 

- Öppna huvudaviseringssidan
- Kontakta en Microsoft-expert på hot
- Visa inskickat material
- Länka till ett annat incident
- Se aviseringen på en tidslinje
- Skapa en regel för en regel

Här är ett exempel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Exempel på åtgärder för en avisering i Säkerhetscenter för Microsoft 365":::

Listan med ytterligare åtgärder beror på typen av avisering.

## <a name="resolve-an-alert"></a>Lösa en avisering

När du är klar med att analysera en avisering  och den kan lösas går du  till fönstret Hantera avisering för aviseringen och markerar dess status som Löst och klassificerar den som en **falsk** avisering eller **Sant-avisering.** För verkliga varningar anger du aviseringens hottyp i **fältet Determination.**

Genom att klassificera aviseringar och ange deras avgörande hjälper du Microsoft 365 Defender att tillhandahålla mer sanna aviseringar och mindre falska aviseringar.

## <a name="see-also"></a>Se även

- [Översikt över incidenter](incidents-overview.md)
- [Hantera incidenter](manage-incidents.md)
- [Analysera incidenter](investigate-incidents.md)
