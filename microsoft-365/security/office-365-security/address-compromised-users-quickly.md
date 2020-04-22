---
title: Adresskomprometerade användarkonton med automatisk undersökning och svar
keywords: AIR, autoIR, ATP, automatiserad, utredning, svar, sanering, hot, avancerad, hot, skydd, komprometterade
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Lär dig hur du snabbar upp processen med att identifiera och adressera komprometterade användarkonton med automatiska undersöknings- och svarsfunktioner i Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 60e9009ff77ebb58794ad7feaf522e1c6efc3039
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635778"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Adresskomprometerade användarkonton med automatisk undersökning och svar

[Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) innehåller kraftfulla [funktioner för automatisk undersökning och svar](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR). Sådana funktioner kan spara din säkerhetsoperation team mycket tid och ansträngning att hantera hot. Microsoft fortsätter att förbättra säkerhetsfunktionerna. Nyligen har AIR-funktionerna förbättrats så att de innehåller en komprometterade användarsäkerhetslekbok (för närvarande i förhandsversion). Läs den här artikeln om du vill veta mer om den komprometterade användarsäkerhetslekboken. Och se blogginlägget [Snabba upp tiden för att upptäcka och svara på användarnas kompromettering och begränsa överträdelseomfånget med Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) för ytterligare information.

![Automatiserad undersökning för en komprometterade användare](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Den komprometterade användarsäkerhetsuppspelningsboken gör det möjligt för organisationens säkerhetsteam att:

- Påskynda identifieringen av komprometterade användarkonton.

- Begränsa omfattningen av en överträdelse när ett konto har komprometterats. Och 

- Svara på komprometterade användare mer effektivt och ändamålsenligt.

## <a name="compromised-user-alerts"></a>Komprometterade användaraviseringar

När ett användarkonto komprometterats uppstår atypiska eller avvikande beteenden. Nätfiske- och skräppostmeddelanden kan till exempel skickas internt från ett betrott användarkonto. Office 365 Advanced Threat Protection kan identifiera sådana avvikelser i e-postmönster och samarbetsaktivitet i Office 365. När detta inträffar utlöses aviseringar och processen för att minska hotet börjar.

Här är till exempel en avisering som utlöstes på grund av misstänkt e-postsändning:

![Avisering utlöses på grund av misstänkt e-postsändning](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Och här är ett exempel på en avisering som utlöstes när en sändningsgräns uppnåddes för en användare:

![Avisering som utlöses genom att skicka gränsen har nåtts](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Undersöka och svara på en komprometterade användare

När ett användarkonto komprometteras utlöses aviseringar. Och i vissa fall blockeras det användarkontot och hindras från att skicka ytterligare e-postmeddelanden tills problemet har lösts av organisationens säkerhetsoperationsteam. I andra fall inleds en automatisk undersökning som kan resultera i rekommenderade åtgärder som säkerhetsteamet bör vidta.

- [Visa och undersöka begränsade användare](#view-and-investigate-restricted-users)

- [Visa information om automatiserade utredningar](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Du måste ha rätt behörighet för att kunna utföra följande uppgifter. Se [Nödvändiga behörigheter för att använda AIR-funktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Visa och undersöka begränsade användare

Du har några alternativ för att navigera till en lista över begränsade användare. I Security & Compliance Center kan du till exempel gå till Begränsad användning **av hothanteringsgranskning** > **Review** > **Restricted Users**. Följande procedur beskriver navigering med hjälp av instrumentpanelen **Aviseringar,** vilket är ett bra sätt att se olika typer av aviseringar som kan ha utlösts.

1. Gå [https://protection.office.com](https://protection.office.com) till och logga in.

2. Välj**Instrumentpanel**för aviseringar i **navigeringsfönstret** > .

3. I widgeten **Andra aviseringar** väljer du **Begränsade användare**.<br/>
   ![Widgeten Andra aviseringar](/microsoft-365/media/office365atp-otheralertswidget.jpg)<br/>
   Då öppnas listan över begränsade användare.<br/>![Begränsade användare i Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg) 

4. Välj ett användarkonto i listan om du vill visa information och vidta åtgärder, till exempel [släppa den begränsade användaren](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam). 

### <a name="view-details-about-automated-investigations"></a>Visa information om automatiserade utredningar

När en automatiserad undersökning har inletts kan du se dess information och resulterar i Security & Compliance Center. Gå till > **Hothanteringsutredningar**och välj sedan en undersökning för att visa dess detaljer. **Threat management**

Mer information finns i [Visa information om en undersökning](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results).

## <a name="keep-the-following-points-in-mind"></a>Tänk på följande punkter

- **Håll koll på dina aviseringar.** Som ni vet, ju längre en kompromiss går oupptäckt, desto större potential för omfattande påverkan och kostnader för din organisation, kunder och partners. Tidig identifiering och snabb respons är avgörande för att minska hot, och särskilt när en användares konto äventyras. 

- **Automation hjälper, men ersätter inte, säkerhetsoperationsteamet**. Automatiserade undersöknings- och svarsfunktioner kan identifiera en komprometterade användare tidigt, men säkerhetsoperationsteamet kommer sannolikt att behöva engagera sig och göra en del undersökningar och reparation. Behöver du hjälp med det här? Se [Granska och godkänna åtgärder](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).

- **Lita inte på en misstänkt inloggningsvarning som din enda indikator**. När ett användarkonto har komprometterats kan det hända att det utlöser en misstänkt inloggningsavisering. Ibland är det serien aktiviteter som inträffar efter att ett konto har komprometterats som utlöser en avisering. Vill du veta mer om varningar? Se [Varningsprinciper](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Nästa steg

- [Granska de behörigheter som krävs för att använda AIR-funktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [Hitta och undersöka skadlig e-post i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [Läs mer om AIR i Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Besök Översikten över Microsoft 365 för att se vad som kommer snart och rulla ut](https://www.microsoft.com/microsoft-365/roadmap?filters=)

