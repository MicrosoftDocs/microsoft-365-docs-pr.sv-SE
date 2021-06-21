---
title: Microsoft Defender för Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender för Office 365 innehåller säkra bifogade filer, säkra länkar, avancerade verktyg för skydd mot nätfiske, rapporteringsverktyg och funktioner för hotinformation.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 81a45f6839538118c5413c1f5fc09e0cd19903a0
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029879"
---
# <a name="microsoft-defender-for-office-365"></a>Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Läs [Avancerad Outlook.com-säkerhet för Microsoft 365-prenumeranter](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2) om du använder Outlook.com, Microsoft 365 Family eller Microsoft 365 Personal och vill ha information om säkra länkar och säkra bifogade filer i Outlook.

Microsoft Defender för Office 365 skyddar din organisation mot skadliga hot från e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. Defender för Office 365 inkluderar:

- **[Principer för hotskydd](#configure-microsoft-defender-for-office-365-policies)**: Definiera skyddsprinciper för hot för att ange rätt skyddsnivå för din organisation.

- **[Rapporter](#view-microsoft-defender-for-office-365-reports)**: Visa realtidsrapporter för att övervaka Defender för Office 365-prestanda i organisationen.

- **[Funktioner för undersökning av hot och svar](#use-threat-investigation-and-response-capabilities)**: Använd verktygen för nya funktioner för att undersöka, förstå, simulera och förhindra hot.

- **[Automatiserade funktioner för undersökning och svar](office-365-air.md)**: Spara tid och ansträngning för att undersöka och mildra hot.

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a>Interaktiv guide till Microsoft Defender för Office 365
I den här interaktiva guiden får du lära dig hur du skyddar din organisation med Microsoft Defender för Office 365. Du kommer att se hur Defender för Office 365 kan hjälpa dig att definiera skyddsprinciper, analysera hot till din organisation och reagera på attacker.

[Ta del av den interaktiva guiden](https://aka.ms/MSDO-IG)

## <a name="getting-started"></a>Komma igång

Om du inte har använt Microsoft Defender för Office 365 eller vill ha mer information om *att göra* kan du dra nytta av den ursprungliga Defender för Office 365-konfigurationen i segment, undersöka och Visa rapporter som använder den här artikeln som en referens. Här är logiska tidiga konfigurations segment:

- Konfigurera allt med "*anti*" i namnet.
  - anti-skadlig kod
  - anti-phishing
  - anti-spam
- Konfigurera allt med "*säkert*" i namnet.
  - Säkra länkar
  - Säkra bifogade filer
- Försvara arbets belastningarna (t. ex. SharePoint Online, OneDrive och Teams)
- Skydda med Zero-Hour auto purge

Om du vill lära dig genom att göra [klickar du på den här länken](protect-against-threats.md).

> [!NOTE]
> Microsoft Defender för Office 365 finns med två olika typer av abonnemang. Du kan se om du har **plan 1** om du har "real tids identifiering" och **plan 2** om du har hot Explorer. Planen du har påverkar de verktyg du kommer att se, så var säker på att du är medveten om din plan när du lär dig.

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2

I följande tabell sammanfattas vad som ingår i varje abonnemang.

****

|Microsoft Defender för Office 365 Abonnemang 1|Microsoft Defender för Office 365 abonnemang 2|
|---|---|
|Funktioner för konfiguration, skydd och identifiering: <ul><li>[Säkra bifogade filer](safe-attachments.md)</li><li>[Säkra länkar](safe-links.md)</li><li>[Säkra bilagor för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Skydd mot nätfiske i Defender för Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Identifiering i realtid](threat-explorer.md)</li></ul>|Microsoft Defender för Office 365 Abonnemang 1  <br>--- plus ---<br> Funktioner för automatisering, undersökning, reparationer och utbildning:<ul><li>[Hotspårare](threat-trackers.md)</li><li>[Hotutforskaren](threat-explorer.md)</li><li>[Automatiska undersökningar och svar](office-365-air.md)</li><li>[Attacksimulator](attack-simulator.md)</li><li>[Kampanjvyer](campaigns.md)</li></ul>|
|

- Microsoft Defender för Office 365 Abonnemang 2 ingår i Office 365 E5, Office 365 A5, Microsoft 365 E5 Security och Microsoft 365 E5.

- Microsoft Defender för Office 365 Abonnemang 1 ingår i Microsoft 365 Business Premium.

- Microsoft Defender för Office 365, Abonnemang 1 och Microsoft Defender för Office 365 Plan 2 är tillgängliga som ett tillägg för vissa abonnemang. Läs mer i [Funktionstillgänglighet för Microsoft Defender för Office 365-abonnemang](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Funktionen [Säkra dokument](safe-docs.md) är bara tillgänglig för användare med Microsoft 365 E5- eller Microsoft 365 E5 Säkerhet-licenser (inte inkluderad i Microsoft Defender för Office 365-abonnemang).

- Om du inte har Microsoft Defender för Office 365, kan du [kontakta försäljningsavdelningen för att starta en utvärderingsversion](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) och se hur Defender för Office 365 fungerar för din organisation.

## <a name="configure-microsoft-defender-for-office-365-policies"></a>Konfigurera principer för Microsoft Defender för Office 365

Med Microsoft Defender för Office 365 kan din organisations säkerhetsteam konfigurera skydd genom att definiera principer i Microsoft 365 Defender-portalen (gå till <https://security.microsoft.com> \> **E-post och samarbete** \> **Principer och regler**).

Lär dig mer genom att titta på [den här videon](https://www.youtube.com/watch?v=vivvTmWJ_3c).

> [!TIP]
> En kort lista över principer som ska definieras finns i [Skydda mot hot](protect-against-threats.md).

## <a name="defender-for-office-365-policies"></a>Principer för Defender för Office 365:

Principerna som definieras för din organisation avgör beteendet och skyddsnivån för fördefinierade hot. Principalternativ är mycket flexibla. Din organisations säkerhetsgrupp kan t. ex. ge skydd mot detaljerade hot på användar-, organisations-, mottagar- och domännivå. Det är viktigt att granska dina principer regelbundet eftersom nya hot och utmaningar dyker upp dagligen.

- **[Säkra bifogade filer](safe-attachments.md)**: Ger nolldagarsskydd för att skydda ditt meddelandesystem genom att kontrollera e-postbilagor för skadligt innehåll. Den dirigerar alla meddelanden och bifogade filer som inte har en signatur i en särskild miljö, och använder sedan maskininlärnings- och analystekniker för att upptäcka skadliga avsikter. Om det inte går att hitta någon misstänkt aktivitet överförs meddelandet till postlådan. Mer information finns i [konfigurera policyer för säkra bifogade filer](set-up-safe-attachments-policies.md).

- **[Säkra länkar](safe-links.md)**: Tillhandahåller klickverifiering av URL:er, till exempel i e-postmeddelanden och Office-filer. Skyddet är pågående och används i alla dina meddelanden och din Office-miljö. Länkar söks igenom för varje klick: säkra länkar är tillgängliga och skadliga länkar blockeras dynamiskt. Mer information finns i [Ställ in policyer för säkra länkar](set-up-safe-links-policies.md).

- **[Säkra bilagor för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md)**: skyddar din organisation när användare samarbetar och delar filer genom att identifiera och blockera skadliga filer på gruppwebbplatser och dokumentbibliotek. Mer information finns i [Aktivera Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

- **[Skydd mot nätfiske i Defender för Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: identifierar försök att imitera användare och interna eller anpassade domäner. Det tillämpar maskininlärningsmodeller och avancerade algoritmer för identifiering av personifiering för att avvärja nätfiskeattacker. Mer information finns i [Skydd mot nätfiske i Defender för Office 365](configure-mdo-anti-phishing-policies.md).

## <a name="view-microsoft-defender-for-office-365-reports"></a>Visa rapporter för Microsoft Defender för Office 365 Plan 2

I Microsoft Defender för Office 365 ingår [rapporter](view-reports-for-mdo.md)för övervakning av Defender för Office 365. Du kan komma åt rapporterna i Microsoft 365 Defender-portalen på **Rapporter** \> **E-post och samarbete** \> **E-post- och samarbetsrapporter** eller direkt på <https://security.microsoft.com/securityreports>.

Rapporterar uppdateringar i realtid, så att du får de senaste insikterna. I de här rapporterna får du också rekommendationer, och de uppmärksammar dig på kommande hot. I fördefinierade rapporter finns följande:

- [Hotutforskaren (eller realtidsidentifieringar)](threat-explorer.md)
- [Statusrapport för hotskydd](view-reports-for-mdo.md#threat-protection-status-report)
- ... och många fler.

## <a name="use-threat-investigation-and-response-capabilities"></a>Använda funktioner för undersökning av hot och svar

Microsoft Defender för Office 365-abonnemang 2 inkluderar förstklassiga [verktyg för undersökning av hot och svar](office-365-ti.md) som gör att din organisations säkerhetsgrupp kan förutse, förstå och förhindra skadliga attacker.

- **[Hotspårare](threat-trackers.md)** ger den senaste informationen om rådande cybersäkerhetsproblem. Du kan till exempel visa information om det senaste skadliga programmet och vidta motåtgärder innan det blir ett faktiskt hot för din organisation. Tillgängliga spårare inkluderar [viktiga spårare](threat-trackers.md#noteworthy-trackers), [trender](threat-trackers.md#trending-trackers), [populära spårare](threat-trackers.md#tracked-queries) och [sparade frågor](threat-trackers.md#saved-queries).

- **[Hotutforskaren (eller realtidsidentifieringar)](threat-explorer.md)** (kallas även för Utforskaren) är en realtidsrapport som gör att du kan identifiera och analysera de senaste hoten. Du kan konfigurera Utforskaren för att visa data för anpassade perioder.

- **[Med en attacksimulator](attack-simulator.md)** kan du köra realistiska angreppsscenarier i din organisation för att identifiera säkerhetsproblem. Simulering av aktuella typer av attacker är tillgängliga, inklusive harpunfiske för hämtning av autentiseringsuppgifter och bilageattacker samt råstyrkeattacker på lösenord.

## <a name="save-time-with-automated-investigation-and-response"></a>Spara tid med automatiserad undersökning och svar

(**NYTT!**) När du ska undersöka en potentiell cyberattack är tiden avgörande. Ju tidigare du kan identifiera och mildra hot, desto bättre blir din organisation. [Funktionerna för automatiserade undersökning och svar](office-365-air.md) (AIR) innehåller en uppsättning säkerhetsspelböcker som du kan starta automatiskt, t. ex. när en avisering initieras, eller manuellt, t. ex. från en vy i Utforskaren. Med AIR kan du spara arbetstid och arbetskraft i säkerhetsarbetet för att begränsa riskerna effektivt och effektivt. Mer information finns i [AIR in Office 365](office-365-air.md) (AIR i Office 365).

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>Behörigheter som krävs för att använda Microsoft Defender för Office 365-funktioner

För att få åtkomst till Microsoft Defender för Office 365-funktioner måste du vara tilldelad en lämplig roll. Följande tabell innehåller några exempel:

<br>

****

|Roll eller rollgrupp|Resurser för att få mer information|
|---|---|
|global administratör (organisationshantering)|Du kan tilldela den här rollen i Azure Active Directory eller i Microsoft 365 Defender-portalen. Mer information finns under [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md).|
|Säkerhetsadministratör|Du kan tilldela den här rollen i Azure Active Directory eller i Microsoft 365 Defender-portalen. Mer information finns under [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md).|
|Organisationshantering i Exchange Online|[Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo) <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|Sök och rensa|Den här rollen är endast tillgänglig på Microsoft 365 Defender-portalen eller Microsoft 365 Efterlevnadscenter. Mer information finns i [Behörigheter på Microsoft 365 Defender-portalen](permissions-microsoft-365-security-center.md) och [Behörigheter i Microsoft 365 Efterlevnadscenter](../../compliance/microsoft-365-compliance-center-permissions.md).|
|||

## <a name="get-microsoft-defender-for-office-365"></a>Hämta Microsoft Defender för Office 365

Microsoft Defender för Office 365 ingår i vissa prenumerationer, t.ex. Microsoft 365 E5, Office 365 E5, Office 365 A5 och Microsoft 365 Business Premium. Om din prenumeration inte innehåller Defender för Office 365 kan du köpa Defender för Office 365, abonnemang 1 eller Defender för Office 365 abonnemang 2, som ett tillägg för vissa prenumerationer. Mer information finns i följande resurser:

- [Tillgänglighet för Microsoft Defender för Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) för en lista över prenumerationer som innehåller Defender för Office 365-abonnemang.

- [Tillgängliga funktioner i abonnemang för Microsoft Defender för Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) för en lista över funktioner som ingår i abonnemang 1 och 2.

- [Hämta rätt Microsoft Defender för Office 365-](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) om du vill jämföra abonnemang och köpa Defender för Office 365.

- [Starta en kostnadsfri utvärderingsversion](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Säkra dokument i Microsoft Defender för Office 365

Nya funktioner läggs till i Microsoft Defender för Office 365 kontinuerligt. Mer information finns i följande resurser:

- I [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=Microsoft%2CDefender%2Cfor%2COffice%2C365) finns en lista över nya funktioner som utvecklas och lanseras.

- [Tjänstbeskrivning för Microsoft Defender för Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) beskriver funktioner och tillgänglighet i Defender för Office 365-abonnemang.

## <a name="see-also"></a>Se även

- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

- [Automatiserad undersökning och svar (AIR) i Microsoft 365 Defender](../defender/m365d-autoir.md)
