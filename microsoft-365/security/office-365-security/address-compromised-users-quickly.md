---
title: Adress som avslöjats användarkonton med automatisk undersökning och svar
keywords: AIR, autoIR, ATP, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd, komprometterat
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Lär dig hur du kan snabba upp processen med att identifiera och åtgärda komprometterade användarkonton med funktioner för automatisk undersökning och svar i Microsoft Defender för Office 365 abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1dda8c9b4aec30fd35efa153aaf032eee23b5e8a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288747"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Adress som avslöjats användarkonton med automatisk undersökning och svar

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


[Microsoft Defender för Office 365 abonnemang 2 innehåller](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) kraftfulla funktioner [för automatisk undersökning och svar](office-365-air.md) (AIR). Med sådana funktioner kan ditt säkerhetsteam spara mycket tid och arbete med att hantera hot. Microsoft fortsätter att förbättra säkerhetsfunktionerna. Nyligen förbättrades AIR-funktionerna till att omfatta en komprometterad säkerhetsspelbok för användare (för närvarande i förhandsversionen). Läs den här artikeln om du vill veta mer om den komprometterade säkerhetsspelboken för användare. Och i blogginlägget går det snabbare att identifiera och svara på användarnas intrång och begränsa intrångsomfånget med Microsoft Defender för [Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) för mer information.

![Automatiserad undersökning för en komprometterad användare](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Den komprometterade säkerhetsspelboken gör att organisationens säkerhetsteam kan:

- Gör identifieringen av komprometterade användarkonton snabbare.

- Begränsa omfattningen av ett intrång när ett konto har komprometterats. och

- Reagera på komprometterade användare mer effektivt och effektivare.

## <a name="compromised-user-alerts"></a>Komprometterade användaraviseringar

När ett användarkonto har komprometterats uppstår atypiska eller onormala beteenden. Till exempel kan nätfiske- och skräppostmeddelanden skickas internt från ett betrott användarkonto. Defender för Office 365 kan identifiera sådana projekt i e-postmönster och samarbetsaktivitet i Office 365. När detta inträffar utlöses varningar och åtgärder för hot börjar.

Här är till exempel en varning som utlöstes på grund av misstänkt e-postmeddelande:

![Avisering som utlösts på grund av misstänkt e-postutskick](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Och här är ett exempel på en avisering som utlöstes när en avsändargräns nåddes för en användare:

![Avisering som utlösts genom att sändningsgränsen har nåtts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Undersöka och svara en komprometterad användare

När ett användarkonto har komprometterats utlöses aviseringar. Och i vissa fall blockeras användarkontot och hindras från att skicka ytterligare e-postmeddelanden tills problemet har lösts av organisationens säkerhetsgrupp. I andra fall påbörjas en automatiserad undersökning som kan leda till rekommenderade åtgärder som din säkerhetsgrupp ska vidta.

- [Visa och undersöka begränsade användare](#view-and-investigate-restricted-users)

- [Visa information om automatiserade undersökningar](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Du måste ha tillräcklig behörighet för att utföra följande uppgifter. Se [behörigheter som krävs för att använda AIR-funktioner.](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>Visa och undersöka begränsade användare

Det finns några alternativ för att navigera till en lista med begränsade användare. I Säkerhets- och & till exempel gå till Granskning **av** begränsade användare för hantering \> **av** \> **hot.** Följande procedur beskriver navigering  med instrumentpanelen Aviseringar, som är ett bra sätt att se olika typer av aviseringar som kan ha utlösts.

1. Gå till <https://protection.office.com> och logga in.

2. Välj Instrumentpanelen för aviseringar **i** \> **navigeringsfönstret.**

3. Välj Begränsade **användare i** widgeten **Andra aviseringar.**

   ![Widget för andra aviseringar](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Listan över begränsade användare öppnas.

   ![Begränsade användare i Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Välj ett användarkonto i listan om du vill visa information och vidta åtgärder, till exempel släppa [en begränsad användare.](removing-user-from-restricted-users-portal-after-spam.md)

### <a name="view-details-about-automated-investigations"></a>Visa information om automatiserade undersökningar

När en automatiserad undersökning har startat kan du se dess information och resultat i Säkerhets- & Efterlevnadscenter. Gå till **Hothanteringsundersökningar** \> och välj sedan en undersökning för att visa dess detaljer.

Mer information finns i [Visa information om en undersökning.](air-view-investigation-results.md)

## <a name="keep-the-following-points-in-mind"></a>Tänk på följande punkter

- **Håll dig på dina aviseringar.** Som du vet, ju längre en kompromiss går oupptäckta, desto större möjlighet till omfattande påverkan och kostnad för organisationen, kunder och partners. Tidig identifiering och snabb respons är avgörande för att minimera hot, och särskilt när en användares konto har komprometterats.

- **Automation hjälper till, men ersätter inte ditt säkerhetsteam.** Automatiska undersöknings- och svarsfunktioner kan upptäcka en komprometterad användare tidigt, men din säkerhetsgrupp måste troligtvis engagera sig och undersöka och åtgärda det. Behöver du hjälp med det här? Se [Granska och godkänna åtgärder.](air-review-approve-pending-completed-actions.md)

- **Förlita dig inte på en misstänkt inloggningsavisering eftersom det är den enda indikatorn.** När ett användarkonto har komprometterats kan det hända att det utlöser en misstänkt inloggningsavisering. Ibland är det en serie aktiviteter som inträffar när ett konto har komprometterats som utlöser en avisering. Vill du veta mer om aviseringar? Se [aviseringsprinciper.](../../compliance/alert-policies.md)

## <a name="next-steps"></a>Nästa steg

- [Granska de behörigheter som krävs för att använda AIR-funktioner](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Hitta och undersöka skadlig e-post i Office 365](investigate-malicious-email-that-was-delivered.md)

- [Läs mer om AIR i Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Besök Microsoft 365 Roadmap och se vad som kommer snart och lanseras](https://www.microsoft.com/microsoft-365/roadmap?filters=)
