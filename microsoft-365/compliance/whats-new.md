---
title: Nyheter i Microsoft 365 Efterlevnad
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Oavsett om det handlar om att lägga till nya lösningar till efterlevnadscentret, uppdatera befintliga funktioner baserat på din feedback eller distribuera ny och uppdaterad dokumentation hjälper Microsoft 365 dig att hålla dig uppdaterad om den föränderliga miljön för efterlevnad. Ta reda på vad vi har gjort den här månaden.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1884989abba56a7da68a2a1372132015a81f5e03
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985018"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Nyheter i Microsoft 365 Efterlevnad

Oavsett om det handlar om att lägga till nya lösningar i [Microsoft 365 Efterlevnadscenter,](microsoft-365-compliance-center.md)uppdatera befintliga funktioner baserat på din feedback eller att distribuera ny och uppdaterad dokumentation hjälper Microsoft 365 dig att hålla dig uppdaterad om den föränderliga efterlevnadsmiljö. Ta en titt nedan för att se vad som är nytt i Microsoft 365 efterlevnad i dag.

> [!NOTE]
> Vissa efterlevnadsfunktioner distribueras i olika hastigheter för våra kunder. Om du inte ser en funktion ännu kan du prova att lägga till dig själv i [den riktade versionen](/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> Vill du veta vad som händer i andra administrationscenter? Läs följande artiklar:<br>[Vad är nytt i Administrationscenter för Microsoft 365](/office365/admin/whats-new-in-preview)<br>[Vad är nytt i SharePoint administrationscenter](/sharepoint/what-s-new-in-admin-center)<br>[Nyheter i Microsoft 365 Defender](../security/defender/whats-new.md)<br><br>
Besök även [Microsoft 365 Översikt](https://www.microsoft.com/microsoft-365/roadmap) och lär dig Microsoft 365 funktioner som släppts, håller på att lanseras, är under utveckling, har avbrutits eller släppts tidigare.

## <a name="may-2021"></a>Maj 2021

### <a name="data-loss-prevention"></a>Dataförlustskydd

- Nya riktlinjer för [planering av din strategi för skydd mot dataförlust.](dlp-overview-plan-for-dlp.md)

### <a name="retention-and-records-management"></a>Hantering av lagring och arkivhandlingar

- Om du släpper en bevarandeprincip från en SharePoint-webbplats eller ett OneDrive-konto behöver du inte längre vänta under respitperioden på 30 dagar innan du kan ta bort webbplatsen eller kontot. Många kunder efterfrågar den här ändringen.
- Dispositionsgranskning i flera steg i förhandsversionen: En administratör [](disposition.md) kan nu lägga till upp till fem på varandra följande steg av dispositionsgranskning för en bevarandeetikett, och granskare kan lägga till andra användare i dispositionsgranskningssteget. Du kan även anpassa e-postmeddelanden och påminnelser.

### <a name="sensitive-information-types"></a>Typer av känslig information

- Ny information som läggs till för att hjälpa [dig att ändra en nyckelordsordlista](sit-modify-keyword-dictionary.md).

### <a name="sensitivity-labels"></a>Känslighetsetiketter

- I förhandsgranskningen är en ny **inställning för autentiseringskontext** nu tillgänglig när du [konfigurerar en känslighetsetikett för grupper och webbplatser.]( sensitivity-labels-teams-groups-sites.md) Det här alternativet fungerar tillsammans med villkorsstyrda åtkomstprinciper i Azure AD för att tillämpa striktare villkor när användare använder SharePoint webbplatser som har etiketten tillämpad. Läs beroenden och [begränsningar innan du konfigurerar](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) den här inställningen.
- [Principer för automatisk](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) märkning som är konfigurerade just för Exchange stöder nu  känslighetsetiketter som använder kryptering med Låt användare tilldela behörigheter för alternativen Vidarebefordra inte Encrypt-Only lösenord.
- [Obligatoriska etiketter är](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) nu allmänt tillgängliga för alla Office, på alla plattformar.

## <a name="april-2021"></a>April 2021

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- [Begränsningar i Advanced eDiscovery](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set). Organisationer kan nu exportera upp till 5 miljoner objekt eller 500 MB, beroende på vilket som är mindre, i en enda export av objekt från en granskningsuppsättning.

### <a name="data-classification"></a>Dataklassificering

- [Märka aktiviteter som är tillgängliga i Aktivitetsutforskaren](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>Datakopplingar

- [Konfigurera en koppling för att arkivera Cisco Jabber på Oracle-data](/microsoft-365/compliance/archive-ciscojabberonoracle-data)
- [Konfigurera en koppling för att arkivera Cisco Jabber på PostgreSQL-data](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>Dataförlustskydd

- Nytt ämne för [referens för policyn för skydd mot dataförlust](/microsoft-365/compliance/dlp-policy-tips-reference).
- Nytt ämne för [Läs mer om skydd mot dataförlust](/microsoft-365/compliance/dlp-learn-about-dlp).
- Nytt ämne för [Komma igång med instrumentpanelen för skydd mot dataförlust](/microsoft-365/compliance/dlp-alerts-dashboard-get-started).

### <a name="retention-policies-and-retention-label-policies"></a>Bevarandeprinciper och bevarandeprinciper för etiketter

- Platsen Microsoft 365 Grupper har nu stöd för att tillämpa bevarandeinställningarna på bara Microsoft 365-postlådor eller bara de anslutna SharePoint-webbplatserna med hjälp av [PowerShell-cmdleten Set-RetentionCompliancePolicy med](/powershell/module/exchange/set-retentioncompliancepolicy) parametern *Applications.*

### <a name="sensitivity-labels"></a>Känslighetsetiketter

Outlook och uppdateringar:
- [Olika inställningar för standardetiketten och obligatoriska](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) etiketter stöds nu för inbyggd etikett. Tidigare fanns stöd för de här inställningarna endast av AIP Unified Labeling-klienten.
- [Nu stöds Endast](encryption-sensitivity-labels.md#let-users-assign-permissions) kryptering av macOS, iOS och Android.
- [Obligatoriska etiketter lanseras](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) för återstående plattformar.
- [Dynamiska markeringar med alla variabler](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) stöds i alla Outlook klienter.

## <a name="march-2021"></a>Mars 2021

Här är några av de ändringar Microsoft 365 av efterlevnadslösningar och innehåll för mars månad.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- **Advanced eDiscovery nu** med stöd för verktyget [och arbetsflödet för nya samlingar.](/microsoft-365/compliance/collections-overview) Andra nya ämnen är [att skapa ett utkast ,](/microsoft-365/compliance/create-draft-collection)spara ett utkast [till](/microsoft-365/compliance/commit-draft-collection)en granskningsuppsättning och samla in statistik [och rapporter.](/microsoft-365/compliance/collection-statistics-reports)
- **Exportera dokument** i en granskning inställd på ett [Azure-lagring](/microsoft-365/compliance/download-export-jobs) dokumentkonto.
- **Prediktiv kodningsmodul för Advanced eDiscovery**. Titta först på de nya [funktionerna för förutsägelsekodning](/microsoft-365/compliance/predictive-coding-overview) som ersätter den indragna relevansmodulen.

### <a name="data-classification"></a>Dataklassificering

- **Dataklassificeringsutforskaren**. [Komma igång med](/microsoft-365/compliance/data-classification-activity-explorer) dataklassificeringsutforskaren.

### <a name="data-connectors"></a>Datakopplingar

- **Privata nycklar**. Stöd för privata nycklar har lagts till i [Bloomberg Message-data,](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys) [ICE-chattdata](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) och [snabbkopplingar för Bloomberg-data.](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys)

### <a name="data-loss-prevention"></a>Skydd mot dataförlust

- **Microsoft Teams support**. Stöd för dataförlustskydd utökad [till Microsoft Teams.](/microsoft-365/compliance/dlp-teams-default-policy)
- **Microsoft Compliance-tillägg.** Komma igång med tillägget [Microsoft Compliance](/microsoft-365/compliance/dlp-chrome-get-started).

### <a name="encryption"></a>Kryptering

- **Kundnyckel för Microsoft 365**. [Översikt över kundnyckeln för](/microsoft-365/compliance/customer-key-tenant-level) Microsoft 365 på innehavarnivå (offentlig förhandsversion).
- **Dubbelnyckelkryptering**. Läs mer om [hur du aktiverar stöd för etiketterade och skyddade dokument](/microsoft-365/compliance/double-key-encryption) i SharePoint och OneDrive för företag.

### <a name="insider-risk-management"></a>Hantering av insiderrisk

Följande uppdateringar av insider-riskhanteringsfunktionerna släpptes för offentlig förhandsversion i mars:

- Ny analysfunktion för att identifiera risker innan du skapar insider-riskprinciper
- Nytt stöd och hantering av riskaktivitetssekvenser
- Stöd för ny kumulativ exfiltrationsidentifiering
- Ny hälsorapportering och rekommendation i programmet
- Ny granskningsloggfunktion och rapportering
- Förbättringar av guiden för att skapa princip
- Uppdateringar i Innehållsutforskaren
- Ny användarhanteringsprocess/-support (lägg till/ta bort användare från principer)
- Nytt stöd för AAD-integrering (avgående stöd för användarprincip)
- Uppdaterat domänstöd i principer (REGEX)
- Förbättringar och förbättringar av principmallen

Följande avsnitt har uppdaterats eller lagts till som stöd för dessa nya funktioner:

- [Lär dig mer om hantering av insiderrisker](/microsoft-365/compliance/insider-risk-management)
- [Planera för hantering av insiderrisker](/microsoft-365/compliance/insider-risk-management-plan)
- [Komma igång med inställningar för Insider-riskhantering](/microsoft-365/compliance/insider-risk-management-settings)
- [Komma igång med hantering av Insider-riskhantering](/microsoft-365/compliance/insider-risk-management-configure)
- [Skapa och hantera principer för hantering av insiderrisker](/microsoft-365/compliance/insider-risk-management-policies)
- [Undersöka aviseringar för insiderrisker](/microsoft-365/compliance/insider-risk-management-alerts)
- [Vidta åtgärder för insiderriskärenden](/microsoft-365/compliance/insider-risk-management-cases)
- [Granska aktiviteter med granskningsloggen för Insider-risker](/microsoft-365/compliance/insider-risk-management-audit-log)
- [Granska data med innehållsutforskaren för insiderrisker](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [Hantera arbetsflödet med instrumentpanelen Användare](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>Hantering av arkivhandlingar

- **Förbättringar av arkivplanen.** En uppdatering av [filplanen tar](file-plan-manager.md) bort eller förbättrar de tidigare längdbegränsningarna för import.
- **Ta bort bevarandeetiketter för arkivhandlingar**. En förhandsversion har stöd för möjligheten att ta [bort bevarandeetiketter](create-apply-retention-labels.md#deleting-retention-labels) som markerar objekt som arkivhandlingar.

### <a name="sensitive-information-types"></a>Typer av känslig information

Innehållet har lagts till eller uppdaterats i följande avsnitt:

- [Komma igång med anpassad typ av känslig information](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [Mer information om typer av känslig information](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Skapa anpassade typer av känslig information med Exact Data Match-baserad klassificering](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Skapa meddelanden för exakt datamatchning](/microsoft-365/compliance/sit-edm-notifications-activities)
- [Definitioner för typ av känslig information](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [Skapa en anpassad typ av känslig information med PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Skapa en nyckelordsordlista](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>Känslighetsetiketter

- **DoD-stöd**. Stöd för amerikanska myndigheter med DoD-miljöer.
- **Endast kryptera för Outlook.** Krypteringsalternativ för Outlook inkluderar nu Encrypt-Only när du markerar [Låt användare tilldela behörigheter.](encryption-sensitivity-labels.md#let-users-assign-permissions)
- **Tillämpa inbyggda etiketter i Office-appar.** Uppdaterad [vägledning](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) för hur du framtvingar inbyggda etiketter i Office-program när du har installerat Unified Labeling-klienten för Azure Information Protection.

## <a name="february-2021"></a>Februari 2021

Här är några av ändringarna av Microsoft 365-efterlevnadslösningar och -innehåll för februari månad.

### <a name="auditing"></a>Granskning

- **Hantera bevarandeprinciper för granskningsloggar.** Läs mer om den nya [instrumentpanelen för granskningsbevarandeprinciper.](/microsoft-365/compliance/audit-log-retention-policies#manage-audit-log-retention-policies-1)
- **Söka i granskningsloggen**. [Använd PowerShell-skript för att söka i granskningsloggen](/microsoft-365/compliance/audit-log-search-script).

### <a name="data-classification-content-explorer"></a>Dataklassificering – Innehållsutforskaren

Innehållet har lagts till eller uppdaterats i följande avsnitt:

- [Kom igång med innehållsutforskaren](/microsoft-365/compliance/data-classification-content-explorer)
- [Viktig information för dataklassificering](/microsoft-365/compliance/data-classification-pub-preview-relnotes)

### <a name="data-loss-prevention"></a>Skydd mot dataförlust

Innehållet har lagts till eller uppdaterats i följande avsnitt:

- [Läs mer om Slutpunkt DLP](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Skicka e-postaviseringar och visa principtips för DLP-principer](/microsoft-365/compliance/use-notifications-and-policy-tips)
- [Lär dig mer om dataförlustskydd i lokal skanner i Microsoft 365](/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [Komma igång med dataförlustskydd i lokal skanner](/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [Skapa en DLP-princip för att skydda dokument med FCI eller andra egenskaper](/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [Använda dataförlustskydd för slutpunkter](/microsoft-365/compliance/endpoint-dlp-using)
- [Komma igång med dataförlustskydd för slutpunkt](/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>eDiscovery

Innehållet har lagts till eller uppdaterats i följande avsnitt:

- [Dekryptering i Microsoft 365 eDiscovery-verktyg](/microsoft-365/compliance/ediscovery-decryption)
- [Nyckelordsfrågor och sökvillkor](/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [Ta ur relevansmodulen i Avancerad eDiscovery](/microsoft-365/compliance/relevance-module-retirement)
- [Använda ett skript för att lägga till användare i ett ärende för bas-eDiscovery](/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>Kryptering

Innehållet har lagts till eller uppdaterats i följande avsnitt:

#### <a name="azure-rights-management-service-rms"></a>Azure Rights Management Service (RMS)

- [Kundhanterade krypterings funktioner](/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Exchange Online-e-postkryptering med AD RMS](/microsoft-365/compliance/information-rights-management-in-exchange-online). Supporten för den här tjänsten har tagits bort. Du kan inte längre använda AD RMS i en Exchange-hybridmiljö. Migrera i stället till Azure RMS.

#### <a name="customer-key"></a>Customer Key

- [Kundnyckel för Microsoft 365 på klientorganisationsnivå](/microsoft-365/compliance/customer-key-tenant-level)
- [Översikt över säkerhet och efterlevnad](/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>IRM (Information Rights Management)

- [Tillämpa IRM (Information Rights Management) på en lista eller ett bibliotek.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) De här nationella molnen stöder inte den här inställningen:
    - Microsoft Cloud för amerikanska myndigheter
    - Microsoft Cloud Germany
    - Azure och Microsoft 365 som drivs av 21Vianet i Kina)
- [Konfigurera IRM för användning av en lokal AD RMS-server](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server). Stödet för den här tjänsten i en Exchange-hybridmiljö har tagits bort.

### <a name="sensitive-information-types"></a>Typer av känslig information

Innehållet har lagts till eller uppdaterats i följande avsnitt:

- [Mer information om typer av känslig information](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Skapa en anpassad typ av känslig information med PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Skapa en anpassad typ av känslig information med exakt datamatchning baserad klassificering](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Entitetsdefinitioner för typer av känslig information](/microsoft-365/compliance/sensitive-information-type-entity-definitions)


### <a name="sensitivity-labels"></a>Känslighetsetiketter

Innehållet har lagts till eller uppdaterats i följande avsnitt:

- **Extern delning i SharePoint.** När [det gäller behållaretiketter](sensitivity-labels-teams-groups-sites.md) släpps nu alternativet för extern delning från SharePoint-webbplatser som allmänt tillgängligt. Dessutom har administrationscentret för Microsoft 365 och Planner nu stöd för att använda känslighetsetiketterna. 
- **Samtidig redigering och spara automatiskt**. Stöd för [samtidig redigering och spara automatiskt](sensitivity-labels-coauthoring.md) för krypterade filer släpps som förhandsversion för testning i icke-produktionsklienter.

## <a name="january-2021"></a>Januari 2021

### <a name="support-for-card-content-in-teams"></a>Stöd för kortinnehåll i Teams

Följande Microsoft 365-efterlevnadslösningar har nu stöd för identifiering av [kortinnehåll som](/microsoftteams/platform/task-modules-and-cards/what-are-cards) genereras via appar i Teams-meddelanden:

- **Core och Advanced eDiscovery**. Kortinnehåll kan nu [sätts i is](create-ediscovery-holds.md#preserve-card-content) eller ingå [i sökningar](/microsoftteams/ediscovery-investigation#search-for-card-content) (gäller även innehållssökning).
- **Granska**. Kortaktivitet registreras [nu i granskningsloggen](/microsoftteams/audit-log-events#teams-activities).
- **Bevarandeprinciper.** Bevarandeprinciper kan nu användas för [att behålla och ta bort kortinnehåll.](retention-policies-teams.md#whats-included-for-retention-and-deletion)

### <a name="information-governance-and-records-management"></a>Informationsstyrning och hantering av arkivhandlingar

[Ny bedömning för](retention-regulatory-requirements.md#new-zealand-public-records-act) att hantera användning av informationsstyrning och hantering av arkivhandlingar för att uppfylla efterlevnadsskyldigheter för New Zealand Public Records Act.

### <a name="sensitivity-labels"></a>Känslighetsetiketter

- Känslighetsetiketter stöds nu för amerikanska myndigheters klientorganisation (GCC och GCC-H).
- Nytt [automatiskt etikettstöd](sensitivity-labels-office-apps.md) för macOS.

## <a name="december-2020"></a>December 2020

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Spotlight: Nytt innehåll för Insider Risk-lösningar

Microsoft 365-teamet arbetar hårt med att skapa innehållslösningsdokument för att främja hur efterlevnadsfunktioner kan användas tillsammans för att uppfylla dina efterlevnadsmål.

Först och främst är innehåll som binder samman våra Insider-risklösningar: kommunikationsefterlevnad, insider-riskhantering, informationsbarriärer och behörighetshantering. Här är en översikt över vad du hittar:

- [Ny landningssida för insiderrisklösningar](insider-risk-solution-overview.md). Innehåller information om risker som lösningarna kan hjälpa till att minimera, licenskrav, distributionssekvens, arkitekturbilder, utbildningsresurser med mera.
- Nya översiktsartiklar för varje insider-risklösning. Vägledning och länkar till artiklar som hjälper dig att lära dig mer om, planera, distribuera och hantera varje lösning:
  - [Kommunikationsefterlevnad](communication-compliance-solution-overview.md)
  - [Hantering av insiderrisk](insider-risk-management-solution-overview.md)
  - [Informationsbarriärer](information-barriers-solution-overview.md)
  - [Privilegierad åtkomsthantering](privileged-access-management-solution-overview.md)
  
Fler innehållslösningsdokument kommer snart!

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

Förbättrat arbetsflöde och förbättrade funktioner för [att lägga till dokument](add-custodians-to-case.md) och [icke-dokumentade datakällor](non-custodial-data-sources.md) till ett Advanced eDiscovery fall.

### <a name="data-connectors"></a>Datakopplingar

[Fyra nya Veritas-kopplingar som släppts](archiving-third-party-data.md#third-party-data-connectors): Redtail Speak, Salesforce Chatter, ServiceNow och Yieldbroker.

### <a name="encryption"></a>Kryptering

Vi [presenterar kundnyckel för Microsoft 365 på innehavarnivå.](customer-key-tenant-level.md) Med nycklar som du anger kan du skapa en datakrypteringsprincip (DEP) och tilldela den till klientorganisationen. Data krypteras i klientorganisationen för dessa arbetsbelastningar:

- Teams dina chattmeddelanden (1:1-chattar, gruppchattar, möteschattar och kanalkonversationer)
- Teams mediemeddelanden (bilder, kodstycken, videor, wiki-bilder)
- Teams samtals- och mötesinspelningar som lagras Teams lagringsutrymme
- Teams chattaviseringar
- Teams chattförslag från Cortana
- Teams statusmeddelanden
- Information om användare och Exchange Online

### <a name="records-management"></a>Hantering av arkivhandlingar

Rollgruppen [för hantering av arkivhandlingar beviljar](get-started-with-records-management.md#permissions-required-for-records-management) nu behörigheter för alla funktioner för hantering av arkivhandlingar, inklusive dispositionsgranskning.

### <a name="sensitivity-labels"></a>Känslighetsetiketter

- [Automatiskt märka data i Azure Purview (förhandsversion).](/azure/purview/create-sensitivity-label) Nu kan du skapa och automatiskt tillämpa känslighetsetiketter på tillgångar i Azure Purview, till exempel filer i Azure Blob-lagring och databaskolumner i SQL Server.
- [Kräv att användare använder en etikett för objekt](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents). Det här nya alternativet kallas även för obligatorisk märkning och kräver att användarna väljer och använder en känslighetsetikett under de specifika scenarierna.
