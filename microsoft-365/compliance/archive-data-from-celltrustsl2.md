---
title: Arkivera data från CellTrust SL2-plattformen till Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Lär dig att konfigurera och använda en CellTrust SL2-dataanslutning för att importera och arkivera mobilkommunikationsdata.
ms.openlocfilehash: 0929a92978f9b48d40153b3cc7328e5e05b54fd0
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097222"
---
# <a name="archive-data-from-celltrust-sl2-to-microsoft-365-preview"></a>Arkivera data från CellTrust SL2 till Microsoft 365 (förhandsversion)

CellTrust SL2 samlar in mobilkommunikationsdata och integrerar med den inledande arkiveringsteknikern för att uppfylla kraven för elektronisk upptäckt för bestämmelser som FINRA, HIPAA, FOIA och TCPA. SL2 Data Connector importerar mobila kommunikationsobjekt till Microsoft 365. I den här artikeln beskrivs processen för integrering av SL2 med Microsoft 365 med hjälp av CellTrust SL2 Data Connector för arkivering. Om du slutför den här processen förutsätts det att du prenumererar på CellTrust SL2-tjänsten och känner till SL2-arkitekturen. Mer information om SL2 finns i <www.celltrust.com>.

När data har importerats till användarnas postlådor i Microsoft 365 kan du använda efterlevnadsfunktioner i Microsoft 365, till exempel Bevarande av juridiska skäl, eDiscovery, Microsoft 365 bevarandeprinciper och kommunikationsefterlevnad. Med hjälp av CellTrust SL2 Data Connector för att importera och arkivera data i Microsoft 365 kan hjälpa din organisation att följa myndighets- och regelpolicyer.

## <a name="overview-of-archiving-with-the-celltrust-sl2-data-connector"></a>Översikt över arkivering med CellTrust SL2 Data Connector

På CellTrusts SL2-plattform samlas kommunikationsdata från flera källor in. SL2-datakällor är antingen Person till person (P2P) eller Program-till-person (A2P). Processen som beskrivs i den här artikeln gäller endast P2P-datakällor. För alla P2P-datakällor är minst en part i samarbetet en SL2-användare som prenumererar på SL2-tjänsten. Följande översikt förklarar processen med att använda CellTrust SL2 Data Connector i Microsoft 365.

![Arkiveringsarbetsflöde för CellTrust SL2-tjänsten](../media/CellTrustSL2ConnectorWorkflow.png)

1. SL2-användare skickar och tar emot data till och från SL2-tjänster i Microsoft Azure molnet.

2. Organisationen har en SL2-domän i CellTrusts SL2-molntjänstmiljö. Din domän kan ha en eller flera organisationsenheter (OUs). SL2-molntjänsten överför dina data till ett mycket säkert område på Microsoft Azure-plattformen, så att dina data aldrig lämnar Microsoft Azure miljön. Beroende på DITT SL2-abonnemang (Enterprise, SMB eller Government) är din domän antingen värd för Microsoft Azure Global eller Microsoft Azure Government.

3. När du har skapat CellTrust SL2 Data Connector, din domän och OUs (oavsett SL2-plan), kan du börja skicka data till Microsoft 365. Datafeeden struktureras för att stödja rapportering baserat på datakällor, OUs eller själva domänen. Din organisation behöver därför bara en koppling för att mata alla datakällor för att Microsoft 365.

4. Kopplingen skapar en mapp under varje mappad användare med en Office 365 licens med namnet **CellTrust SL2.** Den här mappningen ansluter en CellTrust SL2-användare till en Office 365 postlåda med hjälp av en e-postadress. Om ett användar-ID i CellTrust SL2 inte överensstämmer Office 365, arkiveras inte användarens data.

## <a name="before-you-set-up-a-connector"></a>Innan du skapa en koppling

- Kontrollera att du har en domän i cellTrust SL2-molntjänstmiljön. Kontakta CellTrust om du vill ha mer information om hur du skaffar en produktions- eller utvärderingsversion av [EN SL2-domän.](https://www.celltrust.com/contact-us/#form)

- Skaffa autentiseringsuppgifterna för att få åtkomst till administratörskontot för SL2-domänen.

- Den användare som skapar datakopplingen CellTrust SL2 i steg 1 (och slutför den i steg 3) måste tilldelas rollen Importera och exportera postlåda i Exchange Online. Den här rollen krävs för att lägga till kopplingar **på sidan Datakopplingar** i Microsoft 365 Efterlevnadscenter. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Importera och exportera postlåda i rollgruppen Organisationshantering i Exchange Online. Du kan också skapa en rollgrupp, tilldela rollen Importera och exportera postlåda och sedan lägga till lämpliga användare som medlemmar. Mer information finns i avsnitten [Skapa rollgrupper](/Exchange/permissions-exo/role-groups#create-role-groups) och [Ändra rollgrupper](/Exchange/permissions-exo/role-groups#modify-role-groups) i artikeln "Hantera rollgrupper i Exchange Online".

## <a name="step-1-create-a-celltrust-sl2-connector"></a>Steg 1: Skapa en CellTrust SL2-koppling

Det första steget är att skapa en datakoppling i Microsoft 365 Efterlevnadscenter.

1. Gå till <https://compliance.microsoft.com> och klicka **på Datakopplingar** i det vänstra navigeringsfönstret.

2. Klicka på **Filter** på fliken **Översikt,** välj **Efter CellTrust** och använd sedan filtret.

   ![Konfigurera filter för att visa CellTrust-kopplingar](../media/DataConnectorsFilter.png)

3. Klicka **på CellTrust SL2 (förhandsversion**).

4. På sidan **CellTrust SL2 (förhandsversion**) produktbeskrivning klickar du på **Lägg till koppling**.

5. Klicka på **Acceptera på** sidan **Användningsvillkor.**

6. Ange ett unikt namn som identifierar kopplingen och klicka sedan på **Nästa.** Det namn du anger identifierar kopplingen på sidan **Datakopplingar** när du har skapat den.

7. På sidan **Logga in på ditt CellTrust-konto** klickar du på Logga in på **CellTrust.** Du omdirigeras till **CellTrust-portalen för Microsoft 365** i ett nytt webbläsarfönster.

## <a name="step-2-select-the-domains-or-ous-to-archive"></a>Steg 2: Välj de domäner eller OUs som ska arkiveras

Nästa steg är att logga in på ett administratörskonto för din CellTrust SL2-domän och välja de domäner och OUs som ska arkiveras i Microsoft 365.

1. På sidan CellTrust **Microsoft 365 Connector** väljer du din miljö i SL2-molntjänsten för att visa en inloggningssida.

   Vanligtvis bör du se ett alternativ som representerar din miljö. Men om du har domäner i fler än en miljö visas alternativ för varje miljö. När du har gör ett val omdirigeras du till inloggningssidan för SL2.

2. Logga in med autentiseringsuppgifterna för domänen eller OU-administratörskontot.

   Om du loggar in som SL2-domänadministratör ser du namnet på din domän och OUs i den domänen. Om du inte har OUs visas bara namnet på din domän. Om du loggar in som OU-administratör visas bara namnet på OU-enheten.

3. Aktivera de affärsenheter som du vill arkivera. Om du väljer domänen markeras inte de OUs automatiskt. Du måste aktivera varje OU separat för att arkivera den.

   ![Aktivera OUs att arkivera](../media/EnableCellTrustOUs.png)

4. När du är klar med dina val stänger du webbläsarfönstret och återgår till guidesidan i Microsoft 365 Efterlevnadscenter. Efter några sekunder går guiden automatiskt vidare till nästa steg i mappningen av användare.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Steg 3: Mappa användare och slutför kopplingskonfigurationen

Det sista steget är att mappa användare och slutföra kopplingskonfigurationen i Microsoft 365 Efterlevnadscenter.

1. På sidan **Användarmappning** markerar du Aktivera automatisk **användarmappning** om e-postadressen för användare är densamma i både SL2 och Microsoft 365. Annars bör du manuellt använda e-postadresser genom att ladda upp en CSV-fil som mappar användarnas SL2-adress till Microsoft 365 adress.

2. Klicka **på** Nästa, granska dina inställningar och klicka sedan **på Slutför** för att skapa kopplingen.

   Den nya kopplingen läggs till i listan på **sidan Datakopplingar.**

## <a name="get-help-from-celltrust"></a>Få hjälp från CellTrust

Mer information om hur du kontaktar CellTrust finns på sidan [CellTrust](https://www.celltrust.com/contact-us/#support) Kundsupport om du vill ha hjälp med att konfigurera en CellTrust SL2-datakoppling.

## <a name="more-information"></a>Mer information

- En domänadministratör kan konfigurera en koppling för domänen eller andra OUs i den domänen. Om du använder OU-administratörskontot kan du bara konfigurera en koppling för den specifika OU:n.

- För att genomföra stegen ovan måste du vara tilldelad en licens Microsoft 365 E5 och ha rätt Microsoft Office administratörsrättigheter.

- Testa den nya anslutningen genom att skicka ett sms med hjälp av SL2-mobilappen eller från SL2-portalen. Gå till Microsoft 365 postlådan och öppna **mappen CellTrust SL2** i inkorgen. Det kan ta några minuter innan sms:et visas i postlådan.

- Många lagar och bestämmelser kräver att elektronisk kommunikation bevaras på ett sådant sätt att den, när den begärs, kan produceras som bevis. E-dataidentifiering används för att producera elektronisk kommunikation. EIA-lösningar (Enterprise Information Archiving) är utformade för att utföra eDiscovery och tillhandahåller funktioner som bevarandeprinciphantering, dataklassificering och innehålls överseende. Microsoft 365 en långsiktig bevarandelösning för att följa bestämmelser och standarder som påverkar organisationen.

- Termen *arkivering som* används i det här dokumentet refererar till arkivering i samband med användning i en EIA-lösning (Enterprise Information Archiving). EIA-lösningar har eDiscovery-funktioner som skapar dokument för rättstvist, rättstvist, granskningar och undersökningar. Arkivering i samband med säkerhetskopiering och återställning som används för katastrofåterställning och affärskontinuering är inte den avsedda användningen av termen i det här dokumentet.
