---
title: Undersök aviseringar i Microsoft 365 Defender
description: Undersök aviseringar som visas på olika enheter, användare och postlådor.
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
ms.openlocfilehash: 567916e9e1a1d96d77bc6c187b384a1ec3be72a5
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022719"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Undersök aviseringar i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Aviseringar utgör grunden för alla händelser och anger förekomsten av skadliga eller misstänkta händelser i din miljö. Aviseringar är vanligtvis en del av en bredare attack och ger ledtrådar om en händelse.

I Microsoft 365 Defender sammanförs relaterade aviseringar för [formulärincidenter.](incidents-overview.md) Incidenter ger alltid ett bredare sammanhang för en attack, men det kan vara värdefullt att analysera aviseringar när en djupare analys krävs. 

I **kön Aviseringar** visas den aktuella uppsättningen aviseringar. Du kommer till aviseringskön **från Incidenter & aviseringar > aviseringar** i snabbstarten av Microsoft 365 Defender portalen [(security.microsoft.com).](https://security.microsoft.com)

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Exempel på aviseringskön":::

Aviseringar från olika Microsoft-säkerhetslösningar som Microsoft Defender för Endpoint, Microsoft Defender för Office 365 och Microsoft 365 Defender visas här.

Som standard visar aviseringskön i Microsoft 365 Defender-portalen de nya och pågående aviseringarna från de senaste 30 dagarna. Den senaste aviseringen visas högst upp i listan så att du kan se den först. 

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

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exempel på informationssidan för en avisering i Microsoft 365 Defender portalen":::

Du kan också välja **åtgärden Öppna huvudaviseringssidan** i **fönstret Hantera** avisering.

En aviseringssida består av följande avsnitt: 

- Aviseringsartikel, som är kedjan med händelser och aviseringar som är relaterade till den här aviseringen i kronologisk ordning
- Sammanfattningsinformation

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exempel på informationssidan för en avisering i Microsoft 365 Defender portalen":::

På en aviseringssida kan du välja punkterna (**...**) bredvid en enhet för att se tillgängliga åtgärder, till exempel öppna aviseringssidan eller länka aviseringen till en annan händelse.

### <a name="alert-sources"></a>Aviseringskällor
Microsoft 365 Defender kan komma från lösningar som Microsoft Defender för Endpoint, Microsoft Defender för Office 365 och Microsoft Cloud App Security. Du kanske lägger märke till aviseringar med in prepended characters i aviseringen. Följande tabell innehåller vägledning för att hjälpa dig att förstå mappningen av aviseringskällor baserat på det tecken som ska förberedas i aviseringen.

> [!NOTE]
> - De ursprungliga GUID:erna är endast specifika för enhetliga upplevelser, till exempel enhetlig aviseringskö, sida för enhetliga aviseringar, enhetlig undersökning och enhetlig incident.<br>
> - Det in prepended-tecknet ändrar inte GUID för aviseringen. Den enda ändringen i GUID är den in prepended component.<br>


Aviseringskälla | Insnabbtecken 
:---|:---
Microsoft Defender för Office 365 | `fa{GUID}` <br> Exempel: `fa123a456b-c789-1d2e-12f1g33h445h6i` 
Microsoft Defender för Endpoint | `da` eller `ed` för aviseringar om anpassad identifiering <br> 
Microsoft Defender for Identity | `aa{GUID}` <br> Exempel: `aa123a456b-c789-1d2e-12f1g33h445h6i` 
Microsoft Cloud App Security |`ca{GUID}` <br> Exempel: `ca123a456b-c789-1d2e-12f1g33h445h6i` 

### <a name="analyze-affected-assets"></a>Analysera påverkade tillgångar

Avsnittet **Åtgärder som** vidtas har en lista över påverkade tillgångar, till exempel postlådor, enheter och användare som påverkas av den här aviseringen. 

Du kan också välja **Visa i åtgärdscenter** för att visa **fliken** Historik **i Åtgärdscenter** Microsoft 365 Defender administrationsportalen. 

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
> Ett sätt att hantera aviseringar via taggar. Taggningsfunktioner för Microsoft Defender för Office 365 stegvis distribueras och är för närvarande i förhandsversion. <br>
> För närvarande används ändrade taggnamn bara på aviseringar som skapats *efter* uppdateringen. Aviseringar som har genererats innan ändringen återspeglar inte det uppdaterade taggnamnet. 

Från det här fönstret kan du även utföra följande ytterligare åtgärder: 

- Öppna huvudaviseringssidan
- Kontakta en Microsoft-expert på hot
- Visa inskickat material
- Länka till ett annat incident
- Se aviseringen på en tidslinje
- Skapa en regel för en regel

Här är ett exempel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Exempel på åtgärder på en avisering i Microsoft 365 Defender portalen":::

Listan med ytterligare åtgärder beror på typen av avisering.

## <a name="resolve-an-alert"></a>Lösa en avisering

När du är klar med att analysera en avisering  och den kan lösas går du  till fönstret Hantera avisering för aviseringen och markerar dess status som Löst och klassificerar den som en **falsk** avisering eller **Sant-avisering.** För verkliga varningar anger du aviseringens hottyp i **fältet Determination.**

Genom att klassificera aviseringar och ange deras avgörande hjälper du Microsoft 365 Defender att tillhandahålla mer sanna aviseringar och mindre falska aviseringar.

## <a name="next-steps"></a>Nästa steg

Fortsätt din undersökning om det behövs för händelser i [processen.](investigate-incidents.md)

## <a name="see-also"></a>Se även

- [Översikt över incidenter](incidents-overview.md)
- [Hantera incidenter](manage-incidents.md)
- [Undersöka incidenter](investigate-incidents.md)
