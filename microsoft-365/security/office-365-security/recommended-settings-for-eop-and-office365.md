---
title: Microsoft-rekommendationer för EOP och Defender Office 365 säkerhetsinställningar
keywords: Office 365 säkerhetsrekommendationer, Sender Policy Framework, domänbaserad meddelanderapportering och överensstämmelse, DomainKeys Identified Mail, steg, hur det fungerar, säkerhetsbaslinjer, baslinjer för EOP, baslinjer för Defender för Office 365 , konfigurera Defender för Office 365, konfigurera EOP, konfigurera Defender för Office 365, konfigurera EOP, säkerhetskonfiguration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Vad är metodtips för Exchange Online Protection (EOP) och Defender för Office 365 säkerhetsinställningar? Vilka är de aktuella rekommendationerna för standardskydd? Vad ska användas om du vill vara striktare? Och vad får du om du även använder Defender för Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f00e1e2356839e70acafb0f98a5424a1311082e7
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793226"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Rekommenderade inställningar för EOP och Microsoft Defender för Office 365 säkerhet

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** är kärnan i säkerheten för Microsoft 365-prenumerationer och ser till att skadliga e-postmeddelanden inte når de anställdas inkorgar. Men med nya, mer avancerade attacker som dyker upp varje dag krävs ofta förbättrade skydd. **Microsoft Defender för Office 365** Abonnemang 1 eller Abonnemang 2 innehåller ytterligare funktioner som ger administratörer fler lager av säkerhet, kontroll och undersökning.

Även om vi ger säkerhetsadministratörer möjlighet att anpassa sina säkerhetsinställningar finns det två säkerhetsnivåer i EOP och Microsoft Defender för Office 365 som vi rekommenderar: **Standard** och **Strikt.** Varje kund miljö och behov är olika, men vi tror att de här filtreringsnivåerna hjälper till att förhindra att oönskad e-post når de anställdas inkorg i de flesta fall.

Information om hur du automatiskt använder standardinställningarna eller striktinställningarna för användarna finns i Förinställda säkerhetsprinciper [i EOP och Microsoft Defender för Office 365.](preset-security-policies.md)

> [!NOTE]
> Skräppostregeln måste aktiveras på postlådor för att filtreringen ska fungera ordentligt. Det är aktiverat som standard, men du bör kontrollera om filtrering inte verkar fungera. Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).

I den här artikeln beskrivs standardinställningarna och även de rekommenderade inställningarna Standard och Strikt för att skydda dina användare. Tabellerna innehåller inställningarna i Säkerhetscenter Microsoft 365 PowerShell (Exchange Online PowerShell eller fristående Exchange Online Protection PowerShell för organisationer utan Exchange Online postlådor).

> [!TIP]
> Med Office 365 orCA-modulen (Advanced Threat Protection Recommended Configuration Analyzer) för PowerShell kan du (administratörer) hitta de aktuella värdena i de här inställningarna. Mer specifikt genererar **cmdlet:en Get-ORCAReport** en bedömning av skydd mot skräppost, nätfiske och andra inställningar för meddelanden. Du kan ladda ned ORCA-modulen hos <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Skydd mot skräppost, skadlig programvara och skydd mot nätfiske i EOP

Skydd mot skräppost, skadlig programvara och nätfiske är EOP-funktioner som kan konfigureras av administratörer. Vi rekommenderar följande standardkonfigurationer eller strikt konfigurationer.

### <a name="eop-anti-spam-policy-settings"></a>Principinställningar för skydd mot skräppost i EOP

Information om hur du skapar och konfigurerar principer för skydd mot skräppost [finns i Konfigurera principer för skydd mot skräppost i EOP.](configure-your-spam-filter-policies.md)

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Identifieringsåtgärd** för skräppost <p> _SpamAction_|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Sätt meddelande i karantän** <p> `Quarantine`||
|**Identifiering av skräppost med hög** säkerhet <p> _HighConfidenceSpamAction_|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Sätt meddelande i karantän** <p> `Quarantine`|**Sätt meddelande i karantän** <p> `Quarantine`||
|**Identifiering av** nätfiske <p> _PhishSpamAction_|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Sätt meddelande i karantän** <p> `Quarantine`|**Sätt meddelande i karantän** <p> `Quarantine`||
|**Identifiering av nätfiske med** hög säkerhet <p> _HighConfidencePhishAction_|**Sätt meddelande i karantän** <p> `Quarantine`|**Sätt meddelande i karantän** <p> `Quarantine`|**Sätt meddelande i karantän** <p> `Quarantine`||
| Massidentifieringsåtgärd <p> _BulkSpamAction_|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Sätt meddelande i karantän** <p> `Quarantine`||
|**Tröskelvärde för massutskick av e-post** <p> _BulkThreshold_|7|6|4|Mer information finns i [Nivå för massklagomål (BCL) i EOP.](bulk-complaint-level-values.md)|
|_MarkAsSpamBulkMail_|På|På|På|Den här inställningen är endast tillgänglig i PowerShell.|
|**Behålla skräppost i karantän så här många dagar** <p> _QuarantineRetentionPeriod_|15 dagar|30 dagar|30 dagar||
|**Aktivera säkerhetstips för skräppost** <p> _InlineSafetyTipsEnabled_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|Tillåtna avsändare <p> _AllowedSenders_|Inga|Inga|Inga||
|Tillåtna avsändardomäner <p> _AllowedSenderDomains_|Inga|Inga|Inga|Det kan vara en mycket dålig idé att lägga till domäner i listan med tillåtna avsändare. Attacker skulle kunna skicka e-post som annars skulle kunna filtreras bort. <p> Använd [förfalskningsinformation](learn-about-spoof-intelligence.md) och klientorganisationens lista över [tillåtna/blockerade](tenant-allow-block-list.md) avsändare för att granska alla avsändare som kapar avsändar-e-postadresser i organisationens e-postdomäner eller förfalskning av avsändar-e-postadresser i externa domäner.|
|Spärrade avsändare <p> _BlockedSenders_|Inga|Inga|Inga||
|Spärrade avsändardomäner <p> _BlockedSenderDomains_|Inga|Inga|Inga||
|**Aktivera skräppost-aviseringar för slutanvändaren** <p> _EnableEndUserSpamNotifications_|Inaktiverad <p> `$false`|Aktiverad <p> `$true`|Aktiverad <p> `$true`||
|**Skicka skräppost-aviseringar till slutanvändare var (dagar)** <p> _EndUserSpamNotificationFrequency_|3 dagar|3 dagar|3 dagar||
|Aktivera zap (Zero-hour auto purge) för nätfiskemeddelanden <p> _PhishZapEnabled_|Aktiverad <p> `$true`|Aktiverad <p> `$true`|Aktiverad <p> `$true`||
|Aktivera ZAP för skräppostmeddelande <p> _SpamZapEnabled_|Aktiverad <p> `$true`|Aktiverad <p> `$true`|Aktiverad <p> `$true`||
|

Det finns många avancerade inställningar för skräppostfilter (ASF) i principer mot skräppost som håller på att föraktas. Mer information om tidslinjerna för avskrivningen av dessa funktioner anges utanför den här artikeln.

Vi rekommenderar att du lämnar följande ASF-inställningar **Av** för både **standard-** och **striktnivåer.** Mer information om ASF-inställningar finns i [Avancerade inställningar för skräppostfilter (ASF) i EOP.](advanced-spam-filtering-asf-options.md)

<br>

****

|Namn på säkerhetsfunktion|Kommentar|
|---|---|
|**Bildlänkar till fjärrwebbplatser** _(IncreaseScoreWithImageLinks_)||
|**Numerisk IP-adress i URL** (_IncreaseScoreWithNumericIps_)||
|**URL-omdirigering till annan port** (_IncreaseScoreWithRedirectToOtherPort_)||
|**Länkar till .biz- eller .info-webbplatser** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Tomma meddelanden** _(MarkAsSpamEmptyMessages_)||
|**Bädda in taggar i HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**JavaScript eller VBScript i HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Formulärtaggar i HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Ram- eller iframe-taggar i HTML** (_MarkAsSpamFramesInHtml_)||
|**Webbbuggar i HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Objekttaggar i HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Känsliga ord** (_MarkAsSpamSensitiveWordList_)||
|**SPF-post: hard fail** (_MarkAsSpamSpfRecordHardFail_)||
|**Sender ID filtering hard fail** _(MarkAsSpamFromAddressAuthFail_)||
|**Bakåtcatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Principinställningar för utgående skräppost i EOP

Information om hur du skapar och konfigurerar principer för utgående skräppost finns [i Konfigurera utgående skräppostfiltrering i EOP.](configure-the-outbound-spam-policy.md)

Mer information om standardbegränsningar för sändning i tjänsten finns i [Sändningsgränser.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Ange en gräns för externa meddelanden** <p> _RecipientLimitExternalPerHour_|0|500|400|Standardvärdet 0 innebär att tjänstens standardinställningar används.|
|**Ange en gräns för interna meddelanden** <p> _RecipientLimitInternalPerHour_|0|1000|800|Standardvärdet 0 innebär att tjänstens standardinställningar används.|
|**Ange en daglig meddelandegräns** <p> _RecipientLimitPerDay_|0|1000|800|Standardvärdet 0 innebär att tjänstens standardinställningar används.|
|**Begränsning som gjorts för användare som når meddelandegränsen** <p> _ActionWhenThresholdReached_|**Begränsa användarens sändning av e-post till följande dag** <p> `BlockUserForToday`|**Hindra användaren från att skicka e-post** <p> `BlockUser`|**Hindra användaren från att skicka e-post** <p> `BlockUser`||
|**Automatiska vidare vidarebefordransregler** <p> _AutoForwardingMode_|**Automatiskt – systemkontrollerat** <p> `Automatic`|**Automatiskt – systemkontrollerat** <p> `Automatic`|**Automatiskt – systemkontrollerat** <p> `Automatic`|
|

### <a name="eop-anti-malware-policy-settings"></a>Principinställningar för skydd mot skadlig programvara i EOP

Information om hur du skapar och konfigurerar principer för skadlig programvara finns [i Konfigurera principer för skydd mot skadlig programvara i EOP.](configure-anti-malware-policies.md)

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Meddela mottagare när meddelanden sätts i karantän som skadlig programvara** <p> _Åtgärd_|Nej <p> _DeleteMessage_|Nej <p> _DeleteMessage_|Nej <p> _DeleteMessage_|Om skadlig programvara identifieras i en e-postbilaga sätts meddelandet i karantän och kan bara släppas av en administratör.|
|**Aktivera filtret för vanliga bifogade filer** <p> _EnableFileFilter_|Av <p> `$false`|På <p> `$true`|På <p> `$true`|Med den här inställningen sätts meddelanden som innehåller körbara bifogade filer i karantän beroende på filtyp, oavsett vilken bifogad fil det är.|
|**Aktivera automatisk rensning utan timme för skadlig programvara** <p> _ZapEnabled_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Meddela interna avsändare när meddelanden sätts i karantän som skadlig programvara** <p> _EnableInternalSenderNotifications_|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`||
|**Meddela externa avsändare när meddelanden sätts i karantän som skadlig programvara** <p> _EnableExternalSenderNotifications_|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`||
|

### <a name="eop-anti-phishing-policy-settings"></a>Inställningar för skydd mot nätfiske i EOP

Mer information om de här inställningarna finns [i Förfalskningsinställningar.](set-up-anti-phishing-policies.md#spoof-settings) Information om hur du konfigurerar de här [inställningarna finns i Konfigurera principer för skydd mot nätfiske i EOP.](configure-anti-phishing-policies-eop.md)

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Aktivera förfalskningsinformation** <p> _EnableSpoofIntelligence_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Om e-post identifieras som förfalskning** <p> _AuthenticationFailAction_|**Flytta meddelandet till mottagarnas skräppostmappar** <p> `MoveToJmf`|**Flytta meddelandet till mottagarnas skräppostmappar** <p> `MoveToJmf`|**Sätt meddelandet i karantän** <p> `Quarantine`|Den här inställningen gäller för förfalskningsavsändare som [](learn-about-spoof-intelligence.md) automatiskt har blockerats enligt förfalskningsinformation eller som manuellt blockerats i listan över [tillåtna/blockerade klientorganisationen.](tenant-allow-block-list.md)|
|**Visa (?) för oauthenticerade avsändare för förfalskning** <p> _EnableUnauthenticatedSender_|På <p> `$true`|På <p> `$true`|På <p> `$true`|Lägger till ett frågetecken (?) på avsändarens foto i Outlook för oidentifierade falska avsändare. Mer information finns i [Principer för skydd mot nätfiske](set-up-anti-phishing-policies.md).|
|**Visa via-taggen** <p> _EnableViaTag_|På <p> `$true`|På <p> `$true`|På <p> `$true`|Lägger till en via-tagg (chris@contoso.com via fabrikam.com) till från-adressen om den skiljer sig från domänen i DKIM-signaturen eller **MAIL FROM-adressen.** <p> Om du inte kan använda den här  inställningen styrs frågetecknet och via-taggen båda av Show **(?) för oauthenticerade** avsändare för förfalskning i organisationen.|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender för Office 365 säkerhet

Ytterligare säkerhetsförmåner följer med en Microsoft Defender för Office 365 prenumeration. De senaste nyheterna och informationen finns i [Nyheter i Defender för Office 365](whats-new-in-defender-for-office-365.md).

> [!IMPORTANT]
>
> - Standardprincipen för skydd mot nätfiske i Microsoft Defender för Office 365 tillhandahåller [förfalskningsskydd och](set-up-anti-phishing-policies.md#spoof-settings) postlådeinformation för alla mottagare. De andra funktionerna för [personifieringsskydd och](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) avancerade [inställningar är](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) dock inte konfigurerade eller aktiverade i standardprincipen. Om du vill aktivera alla skyddsfunktioner ändrar du standardprincipen för skydd mot nätfiske eller skapar ytterligare principer mot nätfiske.
>
> - Det finns inga standardprinciper Valv länkar eller principer Valv för bifogade filer som automatiskt skyddar alla mottagare i organisationen. För att få skydd måste du skapa minst en länkprincip och Valv en Valv för bifogade filer.
>
> - Valv bifogade filer [för SharePoint, OneDrive och Microsoft Teams-](mdo-for-spo-odb-and-teams.md) och [Valv-dokumentskydd](safe-docs.md) är inte beroende av Valv principer för länkar.

Om din prenumeration omfattar Microsoft Defender för Office 365 eller om du har köpt Defender för Office 365 som ett tillägg anger du följande standardkonfigurationer eller strikt konfigurationer.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Inställningar för mot nätfiskeprincip i Microsoft Defender för Office 365

EOP-kunder får grundläggande skydd mot nätfiske enligt beskrivningen tidigare, men Microsoft Defender för Office 365 har fler funktioner och kontroll för att förhindra, upptäcka och åtgärda angrepp. Information om hur du skapar och konfigurerar dessa [principer finns i Konfigurera principer för skydd mot nätfiske i Defender Office 365.](configure-atp-anti-phishing-policies.md)

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Inställningar för personifiering i principer för skydd mot nätfiske i Microsoft Defender för Office 365

Mer information om de här inställningarna finns [i Inställningar för personifiering i skydd mot nätfiske i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Information om hur du konfigurerar de här inställningarna finns i Konfigurera principer för [skydd mot nätfiske i Defender Office 365](configure-atp-anti-phishing-policies.md).

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|Skyddade användare (avsändare): **Ge användarna möjlighet att skydda** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Av <p> `$false` <p> none (ingen)|På <p> `$true` <p> \<list of users\>|På <p> `$true` <p> \<list of users\>|Beroende på din organisation rekommenderar vi att du lägger till användare (meddelandeavsändare) i viktiga roller. Internt kan skyddade avsändare vara din VD, CFO och andra högre chefer. Externa användare kan vara skyddade avsändare av direktörer eller direktörer.|
|Skyddade användare: **Om ett meddelande identifieras som en imiterad användare** <p> _TargetedUserProtectionAction_|**Använd inte någon åtgärd** <p> `NoAction`|**Sätt meddelandet i karantän** <p> `Quarantine`|**Sätt meddelandet i karantän** <p> `Quarantine`||
|Skyddade domäner: **Inkludera domäner som jag äger** <p> _EnableOrganizationDomainsProtection_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|Skyddade domäner: **Inkludera egna domäner** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Av <p> `$false` <p> none (ingen)|På <p> `$true` <p> \<list of domains\>|På <p> `$true` <p> \<list of domains\>|Beroende på din organisation rekommenderar vi att du lägger till domäner (avsändardomäner) som du inte äger men som du ofta interagerar med.|
|Skyddade domäner: **Om meddelandet identifieras som en imiterad domän** <p> _TargetedDomainProtectionAction_|**Använd inte någon åtgärd** <p> `NoAction`|**Sätt meddelandet i karantän** <p> `Quarantine`|**Sätt meddelandet i karantän** <p> `Quarantine`||
|**Lägga till betrodda avsändare och domäner** <p> _Undantagna Kalendrar_ <p> _ExcludedDomains_|Inga|Inga|Inga|Beroende på din organisation rekommenderar vi att du lägger till avsändare eller domäner som felaktigt identifieras som personifieringsförsök.|
|**Aktivera postlådeintelligens** <p> _EnableMailboxIntelligence_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Aktivera intelligens för personifieringsskydd** <p> _EnableMailboxIntelligenceProtection_|Av <p> `$false`|På <p> `$true`|På <p> `$true`|Med den här inställningen kan du använda den angivna åtgärden för identifiering av personifieringar efter postlådeintelligens.|
|**Om postlådeinformation identifierar och utger sig för att vara användare** <p> _MailboxIntelligenceProtectionAction_|**Använd inte någon åtgärd** <p> `NoAction`|**Flytta meddelandet till mottagarnas skräppostmappar** <p> `MoveToJmf`|**Sätt meddelandet i karantän** <p> `Quarantine`||
|**Visa säkerhetstips** <p> _EnableSimilarUsersSafetyTips_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Visa säkerhetstips** <p> _EnableSimilarDomainsSafetyTips_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Visa ovanliga tecken för användarpersonifiering säkerhetstips** <p> _EnableUnusualCharactersSafetyTips_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Inställningar för förfalskning i principer för nätfiske i Microsoft Defender för Office 365

Observera att det är samma inställningar som är tillgängliga i inställningarna [för skydd mot skräppost-policy i EOP.](#eop-anti-spam-policy-settings)

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Aktivera förfalskningsinformation** <p> _EnableSpoofIntelligence_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Om e-post identifieras som förfalskning** <p> _AuthenticationFailAction_|**Flytta meddelandet till mottagarnas skräppostmappar** <p> `MoveToJmf`|**Flytta meddelandet till mottagarnas skräppostmappar** <p> `MoveToJmf`|**Sätt meddelandet i karantän** <p> `Quarantine`|Den här inställningen gäller för förfalskningsavsändare som [](learn-about-spoof-intelligence.md) automatiskt har blockerats enligt förfalskningsinformation eller som manuellt blockerats i listan över [tillåtna/blockerade klientorganisationen.](tenant-allow-block-list.md)|
|**Visa (?) för oauthenticerade avsändare för förfalskning** <p> _EnableUnauthenticatedSender_|På <p> `$true`|På <p> `$true`|På <p> `$true`|Lägger till ett frågetecken (?) på avsändarens foto i Outlook för oidentifierade falska avsändare. Mer information finns i [Principer för skydd mot nätfiske](set-up-anti-phishing-policies.md).|
|**Visa via-taggen** <p> _EnableViaTag_|På <p> `$true`|På <p> `$true`|På <p> `$true`|Lägger till en via-tagg (chris@contoso.com via fabrikam.com) till från-adressen om den skiljer sig från domänen i DKIM-signaturen eller **MAIL FROM-adressen.** <p> Om du inte kan använda den här  inställningen styrs frågetecknet och via-taggen båda av Show **(?) för oauthenticerade** avsändare för förfalskning i organisationen.|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Avancerade inställningar i principer för skydd mot nätfiske i Microsoft Defender för Office 365

Mer information om den här inställningen finns i [Avancerade tröskelvärden för nätfiske i principer mot nätfiske i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Information om hur du konfigurerar den [här inställningen finns i Konfigurera principer för skydd mot nätfiske i Defender Office 365](configure-atp-anti-phishing-policies.md).

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Tröskelvärde för nätfiske** <p> _PhishThresholdLevel_|**1 – Standard** <p> `1`|**2 – Aggressivt** <p> `2`|**3 – Mer aggressiva** <p> `3`||
|

### <a name="safe-links-settings"></a>Valv Inställningar för länkar

Valv Länkar i Defender för Office 365 innehåller globala inställningar som gäller för alla användare som ingår i aktiva Valv-länkar samt inställningar som är specifika för varje Valv-länkprincip. Mer information finns i [Valv i Defender för Office 365](safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Globala inställningar för Valv Länkar

Information om hur du konfigurerar de [här inställningarna finns i Konfigurera globala Valv i Defender för Office 365](configure-global-settings-for-safe-links.md).

I PowerShell använder du cmdleten [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) för de här inställningarna.

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Använda Valv länkar i: Office 365 appar** <p> _EnableSafeLinksForO365Clients_|På <p> `$true`|På <p> `$true`|På <p> `$true`|Använd Valv länkar i Office 365 och mobila appar (iOS och Android). Mer information finns i inställningar [Valv länkar för appar Office 365 .](safe-links.md#safe-links-settings-for-office-365-apps)|
|**Spåra inte när användare klickar på skyddade länkar i Office 365 program** <p> _TrackClicks_|På <p> `$false`|Av <p> `$true`|Av <p> `$true`|Om du inaktiverar den här inställningen _(ange TrackClicks_ `$true` till ) spåras användarens klick i Office 365 program.|
|**Låt inte användare klicka till den ursprungliga URL:en i Office 365 appar** <p> _AllowClickThrough_|På <p> `$false`|På <p> `$false`|På <p> `$false`|Om du slår på den här inställningen _(inställningen AllowClickThrough_ till ) går du inte vidare till `$false` den ursprungliga URL:en i Office 365 program.|
|

#### <a name="safe-links-policy-settings"></a>Valv Principinställningar för länkar

Information om hur du konfigurerar de här Valv finns i Konfigurera principer för [Valv länkar i Microsoft Defender för Office 365.](set-up-safe-links-policies.md)

I PowerShell använder du [New-SafeLinksPolicy-](/powershell/module/exchange/new-safelinkspolicy) [och Set-SafeLinksPolicy-cmdlets](/powershell/module/exchange/set-safelinkspolicy) för dessa inställningar.

> [!NOTE]
> Som vi beskrivit tidigare finns det ingen standardprincip Valv länkar. Värdena i kolumnen Standard är standardvärdena i de nya Valv som du skapar.

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden** <p> _IsEnabled_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Välj åtgärden för okända eller potentiellt skadliga URL-adresser i Microsoft Teams** <p> _EnableSafeLinksForTeams_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Använd URL-skanning i realtid för misstänkta länkar och länkar som pekar på filer** <p> _ScanUrls_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Vänta tills URL-skanningen är klar innan du levererar meddelandet** <p> _DeliverMessageAfterScan_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Använda Valv länkar till e-postmeddelanden som skickas inom organisationen** <p> _EnableForInternalSenders_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Spåra inte användarklick** <p> _DoNotTrackUserClicks_|Av <p> `$false`|Av <p> `$false`|Av <p> `$false`|Om du inaktiverar den här inställningen _(inställningen DoNotTrackUserClicks_ `$false` till) spåras användarnas klick.|
|**Tillåt inte användare att klicka till den ursprungliga URL:en** <p> _DoNotAllowClickThrough_|Av <p> `$false`|På <p> `$true`|På <p> `$true`|Om du slår på den här inställningen _(inställningen DoNotAllowClickThrough_ till `$true` ) går du inte vidare till den ursprungliga WEBBADRESSen.|
|

### <a name="safe-attachments-settings"></a>Valv Inställningar för bifogade filer

Valv Bifogade filer i Microsoft Defender för Office 365 innehåller globala inställningar som inte har någon relation Valv principer för bifogade filer och inställningar som är specifika för Valv-länkprincipen. Mer information finns i Valv [i Defender för Office 365](safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Globala inställningar för bifogade filer Valv filer

Information om hur du konfigurerar de här inställningarna finns i Aktivera Valv bifogade filer [för SharePoint, OneDrive](turn-on-mdo-for-spo-odb-and-teams.md) och Microsoft Teams och [Valv Dokument i Microsoft 365 E5](safe-docs.md).

I PowerShell använder du cmdleten [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) för de här inställningarna.

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Aktivera Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams.** <p> _EnableATPForSPOTeamsODB_|På <p> `$true`|På <p> `$true`||
|**Aktivera dokument Valv för Office klienter** <p> _EnableSafeDocs_|På <p> `$true`|På <p> `$true`|Den här inställningen är endast tillgänglig med Microsoft 365 E5 eller Microsoft 365 E5 Security licenser. Mer information finns i Valv [i Microsoft Defender för Office 365](safe-docs.md).|
|**Tillåt att andra klickar i Skyddad vy även om Valv dokument identifierat filen som skadlig** <p> _AllowSafeDocsOpen_|Av <p> `$false`|Av <p> `$false`|Den här inställningen är relaterad till Valv Dokument.|
|

#### <a name="safe-attachments-policy-settings"></a>Valv Principinställningar för bifogade filer

Information om hur du konfigurerar de [här inställningarna Valv i Defender för Office 365](set-up-safe-attachments-policies.md).

I PowerShell använder du [New-SafeAttachmentPolicy-](/powershell/module/exchange/new-safeattachmentpolicy) [och Set-SafeAttachmentPolicy-cmdlets](/powershell/module/exchange/set-safelinkspolicy) för de här inställningarna.

> [!NOTE]
> Som vi beskrivit tidigare finns det ingen standardprincip Valv för bifogade filer. Värdena i kolumnen Standard är standardvärdena i nya Valv principer för bifogade filer som du skapar.

<br>

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Valv Okänd information om bifogade filer** <p> _Åtgärd_|Blockera <p> `Block`|Blockera <p> `Block`|Blockera <p> `Block`||
|**Omdirigera bifogade filer vid identifiering** : Aktivera **omdirigering** <p> _Omdirigera_ <p> _RedirectAddress_|Av och ingen e-postadress har angetts. <p> `$true` <p> none (ingen)|På och ange en e-postadress. <p> `$true` <p> en e-postadress|På och ange en e-postadress. <p> `$true` <p> en e-postadress|Omdirigera meddelanden till en säkerhetsadministratör för granskning.|
|**Använd markeringen ovan om sökning efter bifogade filer med skadlig programvara inträffar, eller om det uppstår ett fel.** <p> _ActionOnError_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|

## <a name="related-articles"></a>Relaterade artiklar

- Letar du efter rekommendationer för **Exchange e-postflödesregler (kallas även transportregler)?** Läs [Rekommendationer för konfiguration av e-postflödesregler i Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Administratörer och användare kan skicka falska positiva meddelanden (bra e-postmeddelande markerat som dåligt) och falskt negativa (felaktig e-post tillåts) till Microsoft för analys. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- Använd de här länkarna för information om hur **du konfigurerar** [din EOP-tjänst](/exchange/standalone-eop/set-up-your-eop-service) **och konfigurera** Microsoft Defender [för Office 365](defender-for-office-365.md). Glöm inte de användbara anvisningarna i "[Skydda mot hot i Office 365](protect-against-threats.md)".

- Här hittar du säkerhetsbaslinjer **för Windows:** Var hittar jag säkerhetsbaslinjerna? för alternativ för GPO/lokalt och Använd säkerhetsbaslinjer för att konfigurera Windows 10-enheter i [](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) [Intune](/intune/protect/security-baselines) för Intune-baserad säkerhet. Slutligen finns det en jämförelse mellan Microsoft Defender för Endpoint och Microsoft Intune-säkerhetsbaslinjer i Jämför Microsoft Defender för Slutpunkt och [Intune-säkerhetsbaslinjer i Windows.](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
