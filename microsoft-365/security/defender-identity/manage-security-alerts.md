---
title: Microsoft Defender för identitetssäkerhetsvarningar i Microsoft 365 Defender
description: Lär dig hur du hanterar och granskar säkerhetsvarningar som utfärdats av Microsoft Defender för identitet i Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: c81f14b92b285359bda7e291bd8d3a8b636ae54d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228969"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Defender för identitetssäkerhetsvarningar i Microsoft 365 Defender

**Gäller för:**

- Microsoft 365 Defender
- Defender för identitet

I den här artikeln förklaras grunderna i hur du arbetar med Microsoft Defender för identitetssäkerhetsvarningar [Microsoft 365 säkerhetscenter.](/microsoft-365/security/defender/overview-security-center) [](/defender-for-identity)

Defender för identitetsaviseringar integreras inbyggt i [Microsoft 365 säkerhetscenter](https://security.microsoft.com) med ett dedikerat sidformat för identitetsavisering. Det här markerar det första steget i resan att [introducera hela Microsoft Defender för identitetsupplevelse i Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).

Den nya sidan med identitetsavisering ger Microsoft Defender för identitetskunder bättre signalberikande över domäner och nya automatiska identitetssvarsfunktioner. Det säkerställer att du håller dig säker och hjälper till att förbättra effektiviteten i dina säkerhetsåtgärder.

En av fördelarna med att undersöka aviseringar [via Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) är att Microsoft Defender för identitetsaviseringar är ytterligare korrelerad med information som hämtas från var och en av de andra produkterna i programsviten. Dessa förbättrade aviseringar är konsekventa med de Microsoft 365 Defender aviseringsformat som kommer från [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security) och Microsoft Defender för [slutpunkt.](/microsoft-365/security/defender-endpoint) På den nya sidan slipper du navigera till en annan produktportal och undersöker aviseringar som är associerade med identitet.

Aviseringar som kommer från Defender för identitet kan nu utlösa funktionerna för automatiserad undersökning och svar [(AIR)](/microsoft-365/security/defender/m365d-autoir) i Microsoft 365 Defender, inklusive automatisk åtgärd av aviseringar och minskning av verktyg och processer som kan bidra till den misstänkta aktiviteten.

> [!IMPORTANT]
> Som en del av de Microsoft 365 Defender har vissa alternativ och information ändrats från sin plats i Defender för identitetsportalen. Läs informationen nedan för att ta reda på var du hittar både de välbekanta och nya funktionerna.

## <a name="review-security-alerts"></a>Granska säkerhetsvarningar

Aviseringar kan nås från flera platser,  bland annat sidan Aviseringar, sidan  **Incidenter,** sidorna för enskilda enheter och från **sidan Avancerad** sökning. I det här exemplet granskar vi **sidan Aviseringar.**

I [säkerhetscentret Microsoft 365 du](https://security.microsoft.com/)till **Incidenter, & aviseringar** och sedan till **Aviseringar.**

![Gå till Incidenter och aviseringar och sedan Aviseringar](../../media/defender-identity/incidents-alerts.png)

Om du vill visa aviseringar från Defender för identitet väljer du **Filter** längst upp till höger och **sedan** Microsoft **Defender** för identitet under Tjänstkällor och väljer **Använd:**

![Filter för Defender för identitetshändelser](../../media/defender-identity/filter-defender-for-identity.png)

Aviseringarna visas med information i följande **kolumner:** Aviseringsnamn , **Taggar** **,** Allvarlighetsgrad **,** Undersökningstillstånd **,** **Status**, Kategori , **Identifieringskälla** **,** Påverkade tillgångar **,** Första **aktivitet och Senaste aktivitet**.

![Defender för identitetshändelser](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a>Hantera varningar

Om du klickar **på aviseringsnamnet** för en avisering går du till sidan med information om aviseringen. I den vänstra rutan visas en sammanfattning av Vad **har hänt:**

![Vad hände i aviseringen](../../media/defender-identity/what-happened.png)

Ovanför rutan **Vad hände** finns knapparna för **kontona ,** **Målvärd** och **Källvärd** för aviseringen. För andra aviseringar kan du se knappar för information om ytterligare värdar, konton, IP-adresser, domäner och säkerhetsgrupper. Välj någon av dem för att få mer information om enheterna som ingår.

I det högra fönstret visas **aviseringsinformationen.** Här kan du se mer information och utföra flera uppgifter:

- **Klassificera den här aviseringen** – Här kan du ange den här aviseringen som **en Sant-avisering** eller **Falskt-avisering**

    ![Klassificera avisering](../../media/defender-identity/classify-alert.png)

- **Aviseringstillstånd** **– I Ange** klassificering kan du klassificera aviseringen som **Sant** eller **Falskt.** I **Tilldelad till** kan du tilldela aviseringen till dig själv eller ta bort den.

    ![Aviseringstillstånd](../../media/defender-identity/alert-state.png)

- Aviseringsinformation **–** **Under** Aviseringsinformation hittar du mer information om den specifika aviseringen, följer en länk till dokumentation om typen av avisering, ser vilken händelse aviseringen är kopplad till, granskar alla automatiska undersökningar kopplade till den här aviseringstypen och ser vilka enheter och användare som påverkas.

    ![Aviseringsinformation](../../media/defender-identity/alert-details.png)

- **Kommentarer & –** här kan du lägga till dina kommentarer i aviseringen och se historiken för alla åtgärder som är associerade med aviseringen.

    ![Kommentarer och historik](../../media/defender-identity/comments-history.png)

- **Hantera avisering** – Om du **väljer Hantera** avisering går du till ett fönster där du kan redigera:
  - **Status** – Du kan välja **Ny**, **Löst** eller **Pågår.**
  - **Klassificering** – du kan välja **True alert eller** False **alert.**
  - **Kommentar** – Du kan lägga till en kommentar om aviseringen.

    Om du väljer de tre punkterna bredvid Hantera avisering  kan du kontakta en hotexpert **,** exportera aviseringen till en Excel-fil eller Länka till **en annan händelse**.

    ![Hantera avisering](../../media/defender-identity/manage-alert.png)

    > [!NOTE]
    > I Excel finns nu två länkar: Visa **i Microsoft Defender** för identitet **och visa i Microsoft 365 Defender.** Varje länk tar dig till relevant portal och ger information om aviseringen där.

## <a name="see-also"></a>Se även

- [Undersök aviseringar i Microsoft 365 Defender](../defender/investigate-alerts.md)
