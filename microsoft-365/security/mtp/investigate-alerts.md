---
title: Undersöka aviseringar i Microsoft 365 Defender
description: Undersök aviseringar som visas på olika enheter, användare och postlådor.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
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
ms.openlocfilehash: c4a67a6b0df9308e9e61733a951a5016fa69c082
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50928712"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Undersöka aviseringar i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Aviseringar utgör grunden för alla händelser och anger förekomsten av skadliga eller misstänkta händelser i din miljö. Aviseringar är vanligtvis en del av en bredare attack och ger ledtrådar om ett incidenter.

I Microsoft 365 Defender sammanställs relaterade aviseringar till formulärincidenter. Incidenter ger alltid en bredare kontext för en attack, men det kan vara värdefullt att undersöka aviseringar när en djupare analys krävs. 



## <a name="using-alert-pages-in-investigations"></a>Med aviseringssidor i undersökningar

Om du markerar en avisering på fliken Aviseringar på sidan Incidenter kommer du till de enskilda aviseringssidorna. En aviseringssida består av tre avsnitt: påverkade tillgångar, aviseringsavsnitt och informationsfönstret.

![Bild på exempelaviseringssida](../../media/new-alert-page2.png)

På en aviseringssida kan du välja ikonen med tre punkter (**...**) bredvid en enhet så att du kan se tillgängliga åtgärder som att öppna en specifik tillgångssida eller utföra specifika åtgärdssteg.

### <a name="analyze-affected-assets"></a>Analysera påverkade tillgångar
I avsnittet berörda tillgångar visas postlådor, enheter och användare som påverkas av den här aviseringen. Om du markerar något av resurskorten fylls informationsfönstret i med information, inklusive andra aviseringar som rör tillgångarna, om det finns några.


### <a name="trace-an-alerts-role-in-the-alert-story"></a>Spåra en aviserings roll i aviseringsartikeln
I aviseringsartikeln visas alla tillgångar eller enheter som är relaterade till aviseringen i en processträdvy. Aviseringen i rubriken är den som är i fokus när du först kommer till den valda aviseringens sida. Tillgångar i aviseringsartikeln är expanderbara och klickbara. De ger ytterligare information och snabb respons genom att göra det möjligt för dig att vidta åtgärder direkt i kontexten för aviseringssidan. 

> [!NOTE]
> Avsnittet med aviseringsavsnittet kan innehålla fler än en avisering, och ytterligare aviseringar om samma körningsträd visas före eller efter den avisering du har markerat.

### <a name="view-more-alert-information-in-the-details-pane"></a>Visa mer aviseringsinformation i informationsfönstret

I informationsfönstret visas först information om den markerade aviseringen med information och relaterade åtgärder. Om du väljer någon av de berörda tillgångarna eller enheterna i aviseringsinformationen ändras informationsfönstret för att ge sammanhangsberoende information och åtgärder för det valda objektet.

När du har valt en intresseenhet ändras informationsfönstret för att visa information om den valda entitetstypen, historisk information när den är tillgänglig och alternativ för att vidta åtgärder på den här enheten direkt från aviseringssidan.

### <a name="manage-alerts"></a>Hantera aviseringar

När du har undersökt aviseringarna kan du gå tillbaka till den avisering du började med, markera aviseringens status som Löst och klassificera den som en falsk avisering eller Sant-avisering. Klassificera aviseringar hjälper till att finjustera produkten och ge mer sanna aviseringar och mindre falska aviseringar.

> [!NOTE]
> Ett sätt att hantera aviseringar via taggar. Taggningsfunktioner för Microsoft Defender för Office 365 distribueras stegvis och är för närvarande i förhandsversion. <br>
> För närvarande används ändrade taggnamn bara på aviseringar som skapats *efter* uppdateringen. Aviseringar som skapades innan ändringen återspeglar inte det uppdaterade taggnamnet. 


## <a name="manage-the-unified-alert-queue"></a>Hantera den enhetliga aviseringskön

Om du väljer Aviseringar & incidenter i navigeringsfönstret för Microsoft 365 säkerhetscenter kommer du till den enhetliga aviseringskön. Aviseringar från olika Microsoft-säkerhetslösningar som Microsoft Defender för Endpoint, Microsoft Defender för Office 365 och Microsoft 365 Defender visas i det här avsnittet. 

![Bild av exempelaviseringssida](../../media/unified-alert-queue.png)

I kön Aviseringar visas en lista med aviseringar som har flaggats i nätverket. Som standard visar kön aviseringar som har setts de senaste 30 dagarna. De senaste aviseringarna visas högst upp i listan, vilket hjälper dig att se de senaste aviseringarna först.

> [!NOTE]
> Vid start har den enhetliga aviseringskön bara sju dagars tillgängligt aviseringar för Microsoft Defender för Office 365. Kön fortsätter att byggas med tiden. Om du behöver prioritera aviseringar innan den enhetliga aviseringskön startas använder du kön aviseringar i [Säkerhets- och efterlevnadscenter.](https://protection.office.com/viewalerts)


I det övre navigeringsfältet kan du:

- Använda filter
- Anpassa kolumner för att lägga till eller ta bort kolumner
- Exportera data

Du kan också filtrera aviseringar enligt olika villkor:

- Allvarlighetsgrad
- Status
- Kategori
- Identifieringskälla
- Princip
- Påverkade tillgångar
- Första aktiviteten
- Senaste aktivitet


Information om hur du startar en undersökning av en händelse finns [i Undersöka incidenter i Microsoft 365 Defender](investigate-incidents.md)
## <a name="see-also"></a>Se även

- [Översikt över incidenter](incidents-overview.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
