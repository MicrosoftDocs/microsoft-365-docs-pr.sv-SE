---
title: Adress komprometterade användarkonton med automatiserad undersökning och svar
keywords: AIR, autoIR, Microsoft Defender för Slutpunkt, automatiserad, undersökning, svar, åtgärd, hot, avancerat, hot, skydd, komprometterat
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
ms.date: 06/10/2021
description: Lär dig hur du kan snabba upp processen med att identifiera och åtgärda komprometterade användarkonton med funktioner för automatisk undersökning och svar i Microsoft Defender för Office 365 abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd1ad6f52114340153f3958441bfb9500db67215
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108591"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Adress komprometterade användarkonton med automatiserad undersökning och svar

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


[Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) innehåller kraftfulla [funktioner för automatisk undersökning och](office-365-air.md) svar (AIR). Med sådana funktioner kan ditt säkerhetsteam spara mycket tid och arbete på att hantera hot. Microsoft fortsätter att förbättra säkerhetsfunktionerna. Nyligen har AIR-funktionerna förbättrats med en säkerhetsspelbok för användare som komprometterats (för närvarande i förhandsversionen). Läs den här artikeln om du vill veta mer om den komprometterade säkerhetsspelboken för användare. Mer information finns i blogginlägget Snabba upp tid för att upptäcka och svara på användarnas intrång och begränsa intrångsomfånget med [Microsoft Defender Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) mer information.

![Automatisk undersökning för en komprometterad användare](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Den komprometterade säkerhetsspelboken för användare gör det möjligt för organisationens säkerhetsteam att:

- Snabbare identifiering av komprometterade användarkonton.
- Begränsa omfattningen av ett intrång när ett konto har komprometterats. och
- Reagera på komprometterade användare mer effektivt och effektivare.

## <a name="compromised-user-alerts"></a>Komprometterade användaraviseringar

När ett användarkonto har komprometterats uppstår ett fel som är atypiskt eller onormalt. Till exempel kan nätfiske och skräppost skickas internt från ett betrott användarkonto. Defender för Office 365 kan upptäcka sådana problem i e-postmönster och samarbetsaktivitet inom Office 365. I så fall inträffar aviseringar och åtgärder som innebär hot börjar.

Här är till exempel ett meddelande som utlöstes på grund av misstänkt e-postmeddelande:

![Avisering som utlösts på grund av att misstänkta e-postmeddelanden skickas](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Och här är ett exempel på en varning som utlöstes när en avsändargräns nåddes för en användare:

![Avisering som utlöstes genom att sändningsgränsen har nåtts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Undersöka och svara på en komprometterad användare

När ett användarkonto har komprometterats utlöses aviseringar. Och i vissa fall blockeras och hindras användarkontot från att skicka ytterligare e-postmeddelanden tills problemet har lösts av organisationens team för säkerhetsåtgärder. I andra fall påbörjas en automatiserad undersökning som kan leda till rekommenderade åtgärder som din säkerhetsgrupp ska vidta.

- [Visa och undersöka begränsade användare](#view-and-investigate-restricted-users)

- [Visa information om automatiserade undersökningar](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Du måste ha tillräcklig behörighet för att utföra följande uppgifter. Se [Behörigheter som krävs för att använda AIR-funktioner](office-365-air.md#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Visa och undersöka begränsade användare

Du har några alternativ för att navigera till en lista med begränsade användare. I portalen för e Microsoft 365 Defender kan du till exempel gå till Skicka **e-& och granska** \>  \> **begränsade användare.** I följande procedur beskrivs  navigering med instrumentpanelen Aviseringar, som är ett bra sätt att se olika typer av aviseringar som kan ha utlösts.

1. Öppna Microsoft 365 Defender <https://security.microsoft.com> () och gå till Incidenter **& aviseringar** \> . Du kan också använda om du vill gå **direkt** till sidan <https://security.microsoft.com/alerts> Aviseringar.

2. På sidan **Aviseringar** filtrerar du resultaten efter tidsperiod och principen med namnet Användare begränsad **från att skicka e-post.**

   ![Sidan Aviseringar i Microsoft 365 Defender filtrerats för begränsade användare](../../media/m365-sc-alerts-page-with-restricted-user.png)

3. Om du markerar posten genom att  klicka på namnet öppnas en användare som inte kan skicka e-post med ytterligare information som du kan granska. Bredvid knappen **Hantera** aviseringar kan du klicka på Ikonen Fler alternativ Fler alternativ och sedan välja Visa begränsad användarinformation för att gå till sidan Begränsade användare där du kan släppa en begränsad ![ ](../../media/m365-cc-sc-more-actions-icon.png)  [användare.](removing-user-from-restricted-users-portal-after-spam.md)  

   ![Användaren begränsad från att skicka e-postsida från Aviseringscenter](../../media/m365-sc-alerts-user-restricted-from-sending-email-page.png)

### <a name="view-details-about-automated-investigations"></a>Visa information om automatiserade undersökningar

När en automatiserad undersökning har påbörjats kan du se dess information och resultat i Säkerhets- & efterlevnadscenter. Gå till **Undersökning av** \> **hothantering** och välj sedan en undersökning för att visa dess detaljer.

Mer information finns i [Visa information om en undersökning](air-view-investigation-results.md).

## <a name="keep-the-following-points-in-mind"></a>Tänk på följande

- **Håll dig borta från dina aviseringar.** Som du vet kommer en kompromiss att bli oupptäckta ju längre bort, desto större möjlighet till negativt påverkan och kostnad för organisationen, kunder och partner. Tidiga identifieringar och snabba svar är avgörande för att minska hot, och särskilt när en användares konto har komprometterats.

- **Automationen hjälper till, men ersätter inte, ditt säkerhetsteam.** Automatiska undersöknings- och svarsfunktioner kan upptäcka en komprometterad användare tidigt, men din säkerhetsgrupp måste troligtvis engagera sig och undersöka och åtgärda det. Behöver du hjälp med det här? Se [Granska och godkänna åtgärder](air-review-approve-pending-completed-actions.md).

- **Förlita dig inte på en avisering om misstänkt inloggning, bara din .** När ett användarkonto har komprometterats kan det hända att det utlöser en avisering om misstänkt inloggning. Ibland är det en serie aktiviteter som inträffar när ett konto har komprometterats som utlöser en avisering. Vill du veta mer om aviseringar? Se [Aviseringsprinciper.](../../compliance/alert-policies.md)

## <a name="next-steps"></a>Nästa steg

- [Granska de behörigheter som krävs för att använda AIR-funktioner](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Hitta och undersöka skadlig e-post i Office 365](investigate-malicious-email-that-was-delivered.md)

- [Läs mer om AIR i Microsoft Defender för Endpoint](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Besök Microsoft 365 Översikt och se vad som kommer snart och lanseras](https://www.microsoft.com/microsoft-365/roadmap?filters=)