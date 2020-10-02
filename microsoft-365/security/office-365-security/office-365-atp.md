---
title: Office 365 Avancerat skydd
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 Avancerat skydd innehåller säkra bifogade filer, säkra länkar, avancerade verktyg för skydd mot nätfiske, rapporteringsverktyg och funktioner för hotinformation.
ms.openlocfilehash: e156967ff6e594503868f979e9c7f18b6bee02e2
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327219"
---
# <a name="office-365-advanced-threat-protection-atp"></a>Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Läs [Avancerad Outlook.com-säkerhet för Microsoft 365-prenumeranter](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2) om du använder Outlook.com, Microsoft 365 Family eller Microsoft 365 Personal och vill ha information om säkra länkar och säkra bifogade filer i Outlook.

Office 365 Advanced Threat Protection (ATP) skyddar din organisation mot skadliga hot från e-postmeddelanden, länkar (URL: er) och samarbetsverktyg. ATP innehåller:

- **[Principer för hotskydd](#configure-atp-policies)**: Definiera skyddsprinciper för hot för att ange rätt skyddsnivå för din organisation.

- **[Rapporter](#view-office-365-atp-reports)**: Visa realtidsrapporter för att övervaka ATP-prestanda i organisationen.

- **[Funktioner för undersökning av hot och svar](#use-threat-investigation-and-response-capabilities)**: Använd verktygen för nya funktioner för att undersöka, förstå, simulera och förhindra hot.

- **[Automatiserade funktioner för undersökning och svar](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)**: Spara tid och ansträngning för att undersöka och mildra hot.

## <a name="getting-started"></a>Komma igång

Om du inte har använt Office 365 Avancerat skydd eller vill ha mer information om *att göra*kan du dra nytta av den ursprungliga ATP-konfigurationen i segment, undersöka och Visa rapporter som använder den här artikeln som en referens. Här är logiska tidiga konfigurations segment:

- Konfigurera allt med "*anti*" i namnet.
    - anti-skadlig kod
    - anti-phishing
    - anti-spam
- Konfigurera allt med "*säkert*" i namnet.
    - säkra länkar
    - Säkra bifogade filer
- Försvara arbets belastningarna (t. ex. SharePoint Online, OneDrive och Teams) 
- Skydda med Zero-Hour auto purge

Om du vill lära dig genom att göra [klickar du på den här länken](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide&preserve-view=true). 

> [!NOTE]
> ATP kommer från två olika plan typer. Du kan se om du har **plan 1** om du har "real tids identifiering" och **plan 2**om du har hot Explorer. Planen du har påverkar de verktyg du kommer att se, så var säker på att du är medveten om din plan när du lär dig.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP-abonnemang 1 och 2

I följande tabell sammanfattas vad som ingår i varje abonnemang.

****

|Office 365 ATP-abonnemang 1|Office 365 ATP-abonnemang 2|
|---|---|
|<br/>Funktioner för konfiguration, skydd och identifiering: <ul><li>[Säkra bifogade filer](atp-safe-attachments.md)</li><li>[Säkra länkar](atp-safe-links.md)</li><li>[ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[ATP-skydd mot nätfiske](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[Identifiering i realtid](threat-explorer.md)</li></ul>|Funktioner i Office 365 ATP-abonnemang 1<br/>--- plus ---<br/>Funktioner för automatisering, undersökning, reparationer och utbildning:</li><li>[Hotspårare](threat-trackers.md)</li><li>[Hotutforskaren](threat-explorer.md)</li><li>[Automatiska undersökningar och svar](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[Attacksimulator](attack-simulator.md)</li></ul>|
|

- Office 365 ATP Plan 2 ingår i Office 365 E5, Office 365 A5, Microsoft 365 E5 Security och Microsoft 365 E5.

- Office 365 ATP-abonnemang 1 ingår i Microsoft 365 Business Premium.

- Office 365 ATP-abonnemang 1 och Office 365 ATP-abonnemang 2 är tillgängliga som ett tillägg för vissa prenumerationer. Mer information finns i [Feature availability across ATP plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) (Funktionstillgänglighet för ATP-abonnemang).

- Funktionen [säkra dokument](safe-docs.md) är bara tillgänglig för användare med Microsoft 365 E5- eller Microsoft 365 E5 Säkerhet-licenser (inte inkluderad i Office 365 ATP-abonnemang).

- Om du inte har Office 365 ATP, kan du [kontakta försäljningsavdelningen för att starta en utvärderingsversion](https://go.microsoft.com/fwlink/p/?LinkId=518644) och se hur ATP fungerar för din organisation.

## <a name="configure-atp-policies"></a>Konfigurera ATP-principer

Med Office 365 ATP kan din organisations säkerhetsteam konfigurera skydd genom att definiera principer i Säkerhets- och efterlevnadscenter (gå till [https://protection.office.com](https://protection.office.com) > **Hothantering** > **Princip**.)

> [!TIP]
> En kort lista över principer som ska definieras finns i [Skydda mot hot](protect-against-threats.md).

## <a name="advanced-threat-protection-policies"></a>Policyer för avancerad hotskydd

Principerna som definieras för din organisation avgör beteendet och skyddsnivån för fördefinierade hot. Principalternativ är mycket flexibla. Din organisations säkerhetsgrupp kan t. ex. ge skydd mot detaljerade hot på användar-, organisations-, mottagar- och domännivå. Det är viktigt att granska dina principer regelbundet eftersom nya hot och utmaningar dyker upp dagligen.

- **[Säkra bifogade filer](atp-safe-attachments.md)**: Ger nolldagarsskydd för att skydda ditt meddelandesystem genom att kontrollera e-postbilagor för skadligt innehåll. Den dirigerar alla meddelanden och bifogade filer som inte har en signatur i en särskild miljö, och använder sedan maskininlärnings- och analystekniker för att upptäcka skadliga avsikter. Om det inte går att hitta någon misstänkt aktivitet överförs meddelandet till postlådan. Mer information finns i [konfigurera policyer för säkra bifogade filer](set-up-atp-safe-attachments-policies.md).

- **[Säkra länkar](atp-safe-links.md)**: Tillhandahåller klickverifiering av URL:er, till exempel i e-postmeddelanden och Office-filer. Skyddet är pågående och används i alla dina meddelanden och din Office-miljö. Länkar söks igenom för varje klick: säkra länkar är tillgängliga och skadliga länkar blockeras dynamiskt. Mer information finns i [Ställ in policyer för säkra länkar](set-up-atp-safe-links-policies.md).

- **[ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md)**: skyddar din organisation när användare samarbetar och delar filer genom att identifiera och blockera skadliga filer på gruppwebbplatser och dokumentbibliotek. Mer information finns i [Aktivera Office 365 ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

- **[ATP-skydd mot nätfiske](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)**: identifierar försök att imitera användare och interna eller anspassade domäner. Det tillämpar maskininlärningsmodeller och avancerade algoritmer för identifiering av personifiering för att avvärja nätfiskeattacker. Mer information finns i [konfigurera principer för ATP-skydd mot nätfiske i Office 365](configure-atp-anti-phishing-policies.md).

## <a name="view-office-365-atp-reports"></a>Visa rapporter om Office 365 ATP

Office 365 ATP innehåller en avancerad [instrumentpanel för rapportering](view-reports-for-atp.md) för att övervaka ATP-prestanda. Du kan komma åt den via **Rapporter** > **Instrumentpanel** i Säkerhets- och efterlevnadscentret.

Rapporterar uppdateringar i realtid, så att du får de senaste insikterna. I de här rapporterna får du också rekommendationer, och de uppmärksammar dig på kommande hot. I fördefinierade rapporter finns följande:

- [Hotutforskaren (eller realtidsidentifieringar)](threat-explorer.md)

- [Statusrapport för hotskydd](view-reports-for-atp.md#threat-protection-status-report)

- [Filtypsrapporter för ATP](view-reports-for-atp.md#advanced-threat-protection-file-types-report)

- [Meddelandedispositionsrapport för ATP](view-reports-for-atp.md#advanced-threat-protection-message-disposition-report)

- ... och många fler.

## <a name="use-threat-investigation-and-response-capabilities"></a>Använda funktioner för undersökning av hot och svar

Office 365 ATP-abonnemang 2 inkluderar förstklassiga [verktyg för undersökning av hot och svar](office-365-ti.md) som gör att din organisations säkerhetsgrupp kan förutse, förstå och förhindra skadliga attacker.

- **[Hotspårare](threat-trackers.md)** ger den senaste informationen om rådande cybersäkerhetsproblem. Du kan till exempel visa information om det senaste skadliga programmet och vidta motåtgärder innan det blir ett faktiskt hot för din organisation. Tillgängliga spårare inkluderar [viktiga spårare](threat-trackers.md#noteworthy-trackers), [trender](threat-trackers.md#trending-trackers), [populära spårare](threat-trackers.md#tracked-queries) och [sparade frågor](threat-trackers.md#saved-queries).

- **[Hotutforskaren (eller realtidsidentifieringar)](threat-explorer.md)** (kallas även för Utforskaren) är en realtidsrapport som gör att du kan identifiera och analysera de senaste hoten. Du kan konfigurera Utforskaren för att visa data för anpassade perioder.

- **[Med en attacksimulator](attack-simulator.md)** kan du köra realistiska angreppsscenarier i din organisation för att identifiera säkerhetsproblem. Simulering av aktuella typer av attacker är tillgängliga, inklusive harpunfiske för hämtning av autentiseringsuppgifter och bilageattacker samt råstyrkeattacker på lösenord.

## <a name="save-time-with-automated-investigation-and-response"></a>Spara tid med automatiserad undersökning och svar

(**NYTT!**) När du ska undersöka en potentiell cyberattack är tiden avgörande. Ju tidigare du kan identifiera och mildra hot, desto bättre blir din organisation. [Funktionerna för automatiserade undersökning och svar](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) innehåller en uppsättning säkerhetsspelböcker som du kan starta automatiskt, t. ex. när en avisering initieras, eller manuellt, t. ex. från en vy i Utforskaren. Med AIR kan du spara arbetstid och arbetskraft i säkerhetsarbetet för att begränsa riskerna effektivt och effektivt. Mer information finns i [AIR in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR i Office 365).

## <a name="permissions-required-to-use-atp-features"></a>Behörigheter som krävs för att använda ATP-funktioner

För att få åtkomst till ATP-funktioner i Säkerhets- och efterlevnadscentret måste du vara tilldelad en lämplig roll. Följande tabell innehåller några exempel:

|Roll eller rollgrupp|Resurser för att få mer information|
|---|---|
|Global administratör (detta kan tilldelas i Azure Active Directory eller i Säkerhets- och efterlevnadscenter)|[Om administratörsroller i Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Säkerhetsadministratör (detta kan tilldelas i Azure Active Directory eller i Säkerhets- och efterlevnadscenter)|[Administratörens rollbehörigheter i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md)|
|Organisationshantering för Exchange Online (detta har tilldelats i Exchange Online)|[Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|Sök och rensa (det här är bara tilldelat i Säkerhets- och efterlevnadscenter)|[Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md)|

Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).

## <a name="get-office-365-atp"></a>Skaffa Office 365 ATP

Office 365 ATP ingår i vissa prenumerationer, t.ex. Microsoft 365 E5, Office 365 E5, Office 365 A5 och Microsoft 365 Business Premium. Om Office 365 ATP inte ingår i din prenumeration kan du köpa ATP-abonnemang 1 eller ATP-abonnemang 2 som ett tillägg till vissa prenumerationer. Mer information finns i följande resurser:

- [Office 365 Avancerat skydd](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) för en lista över prenumerationer som innehåller ATP-abonnemang.

- [Tillgängliga funktioner i abonnemang för Avancerat skydd (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) för en lista över funktioner som ingår i abonnemang 1 och 2.

- [Skaffa rätt Office 365 Avancerat skydd](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) för att jämföra abonnemang och köpa Office 365 ATP.

- [Starta en kostnadsfri utvärderingsversion](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Nya funktioner i Office 365 ATP

Nya funktioner läggs till i Office 365 ATP kontinuerligt. Mer information finns i följande resurser:

- I [Microsoft 365-översikten](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) finns en lista över nya funktioner som utvecklas och lanseras.

- [Beskrivning av tjänsten Office 365 Avancerat skydd](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) beskriver funktioner och tillgänglighet för ATP-abonnemang.

## <a name="see-also"></a>Snabbreferens

- [Microsoft Hotskydd](../mtp/microsoft-threat-protection.md)

- [Automatiserad undersökning och svar (AIR) i Microsoft Hotskydd](../mtp/mtp-autoir.md)
