---
title: Microsoft-rekommendationer för EOP och Defender för Säkerhetsinställningar i Office 365
keywords: Säkerhetsrekommendationer för Office 365, Sender Policy Framework, domänbaserad meddelanderapportering och överensstämmelse, DomainKeys Identified Mail, steg, hur det fungerar, säkerhetsbaslinjer, baslinjer för EOP, baslinjer för Defender för Office 365, konfigurera Defender för Office 365, konfigurera EOP, konfigurera Defender för Office 365, konfigurera Defender för Office 365, konfigurera Defender för Office 365, konfigurera EOP, konfigurera Defender för Office 365, konfigurera EOP, säkerhetskonfiguration
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
description: Vilka metodtips gäller för Säkerhetsinställningar i Exchange Online Protection (EOP) och Defender för Office 365? Vilka är de aktuella rekommendationerna för standardskydd? Vad ska användas om du vill vara striktare? Och vad extra får du om du också använder Defender för Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7a609a069e0e35b673b0902f2600f9c5433a14bb
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166945"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Exchange Online Protection (EOP)** är kärnan i säkerheten för Microsoft 365-prenumerationer och ser till att skadliga e-postmeddelanden inte når de anställdas inkorgar. Men med nya, mer avancerade attacker som växer varje dag krävs ofta förbättrade skydd. **Microsoft Defender för Office 365** Abonnemang 1 eller abonnemang 2 innehåller ytterligare funktioner som ger administratörer fler lager för säkerhet, kontroll och undersökning.

Även om vi ger säkerhetsadministratörer möjlighet att anpassa sina säkerhetsinställningar finns det två säkerhetsnivåer i EOP och Microsoft Defender för Office 365 som vi rekommenderar: **Standard** och **Strikt.** Varje kund miljö och behov är olika, men vi tror att de här filtreringsnivåerna hjälper till att förhindra att oönskad e-post når de anställdas inkorg i de flesta situationer.

Information om hur du automatiskt använder standardinställningarna eller strikt för användarna finns i Förinställda säkerhetsprinciper i EOP och [Microsoft Defender för Office 365.](preset-security-policies.md)

> [!NOTE]
> Skräppostregeln måste vara aktiverad för postlådor för att filtreringen ska fungera korrekt. Det är aktiverat som standard, men du bör kontrollera det om filtrering inte verkar fungera. Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor i Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

I den här artikeln beskrivs standardinställningarna och de rekommenderade standard- och striktinställningarna för att skydda dina användare.

> [!TIP]
> Med orca-modulen (Advanced Threat Protection Recommended Configuration Analyzer) för Office 365 för PowerShell kan du (administratörer) hitta de aktuella värdena för de här inställningarna. Mer specifikt genererar **cmdleten Get-ORCAReport** en utvärdering av skydd mot skräppost, nätfiske och andra säkerhetsinställningar för meddelanden. Du kan ladda ned ORCA-modulen på <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Skydd mot skräppost, skadlig programvara och skydd mot nätfiske i EOP

Skydd mot skräppost, skadlig programvara och nätfiske är EOP-funktioner som kan konfigureras av administratörer. Vi rekommenderar följande standardkonfigurationer eller strikt konfigurationer.

### <a name="eop-anti-spam-policy-settings"></a>Principinställningar för EOP-skydd mot skräppost

Information om hur du skapar och konfigurerar principer för skydd mot skräppost finns i [Konfigurera principer för skydd mot skräppost i Office 365.](configure-your-spam-filter-policies.md)

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Identifieringsåtgärd** för skräppost <p> _SpamAction_|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Sätt meddelande i karantän** <p> `Quarantine`||
|**Identifieringsåtgärd för skräppost med** hög konfidens <p> _HighConfidenceSpamAction_|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Sätt meddelande i karantän** <p> `Quarantine`|**Sätt meddelande i karantän** <p> `Quarantine`||
|**Identifieringsåtgärd för nätfiske** <p> _PhishSpamAction_|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Sätt meddelande i karantän** <p> `Quarantine`|**Sätt meddelande i karantän** <p> `Quarantine`||
|**Identifieringsåtgärd för nätfiske** med hög konfidens <p> _HighConfidencePhishAction_|**Sätt meddelande i karantän** <p> `Quarantine`|**Sätt meddelande i karantän** <p> `Quarantine`|**Sätt meddelande i karantän** <p> `Quarantine`||
|**Identifieringsåtgärd för massutskick** av e-post <p> _BulkSpamAction_|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Flytta meddelandet till mappen Skräppost** <p> `MoveToJmf`|**Sätt meddelande i karantän** <p> `Quarantine`||
|Tröskelvärde för massutskick av e-post <p> _BulkThreshold_|7|6|4|Mer information finns i [Nivå för gruppklagomål (BCL) i Office 365.](bulk-complaint-level-values.md)|
|Lagringstid i karantän <p> _QuarantineRetentionPeriod_|15 dagar|30 dagar|30 dagar||
|**Säkerhetstips** <p> _InlineSafetyTipsEnabled_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|Tillåtna avsändare <p> _AllowedSenders_|Inga|Inga|Inga||
|Tillåtna avsändardomäner <p> _AllowedSenderDomains_|Inga|Inga|Inga|Det kan vara dåligt att lägga till domäner i listan med tillåtna avsändare. Attacker skulle kunna skicka e-post som annars skulle filtreras bort. <p> Använd [förfalskningsinformation](learn-about-spoof-intelligence.md) i säkerhets- och efterlevnadscentret för & på inställningssidan Skydd mot skräppost för att granska alla avsändare som förfalskning av avsändar-e-postadresser på organisationens **e-postdomäner** eller förfalskning av avsändaradresser i externa domäner.|
|Spärrade avsändare <p> _BlockedSenders_|Inga|Inga|Inga||
|Spärrade avsändardomäner <p> _BlockedSenderDomains_|Inga|Inga|Inga||
|**Aktivera skräppost-aviseringar för slutanvändaren** <p> _EnableEndUserSpamNotifications_|Inaktiverad <p> `$false`|Aktiverad <p> `$true`|Aktiverad <p> `$true`||
|**Skicka skräppost-aviseringar till slutanvändare var (dagar)** <p> _EndUserSpamNotificationFrequency_|3 dagar|3 dagar|3 dagar||
|**Spam ZAP** <p> _SpamZapEnabled_|Aktiverad <p> `$true`|Aktiverad <p> `$true`|Aktiverad <p> `$true`||
|**Phish ZAP** <p> _PhishZapEnabled_|Aktiverad <p> `$true`|Aktiverad <p> `$true`|Aktiverad <p> `$true`||
|_MarkAsSpamBulkMail_|På|På|På|Den här inställningen är endast tillgänglig i PowerShell.|
|

Det finns flera andra avancerade inställningar för skräppostfilter (ASF) i policyn för skräppost som håller på att föraktas. Mer information om tidslinjerna för avskrivningen av dessa funktioner meddelas utanför den här artikeln.

Vi rekommenderar att du inaktiverar de här **ASF-inställningarna** för både **standard-** och **striktnivåer.** Mer information om ASF-inställningar finns i inställningarna för avancerat skräppostfilter [(ASF) i Office 365.](advanced-spam-filtering-asf-options.md)

****

|Namn på säkerhetsfunktion|Kommentar|
|---|---|
|**Bildlänkar till fjärrwebbplatser** _(IncreaseScoreWithImageLinks_)||
|**Numerisk IP-adress i URL** _(IncreaseScoreWithNumericIps_)||
|**UL redirect to other port** _(IncreaseScoreWithRedirectToOtherPort_)||
|**URL till .biz- eller .info-webbplatser** _(IncreaseScoreWithBizOrInfoUrls_)||
|**Empty messages** _(MarkAsSpamEmptyMessages)_||
|**JavaScript eller VBScript i HTML** _(MarkAsSpamJavaScriptInHtml_)||
|**Ram- eller IFrame-taggar i HTML** _(MarkAsSpamFramesInHtml_)||
|**Objekttaggar i HTML** _(MarkAsSpamObjectTagsInHtml_)||
|**Bädda in taggar i HTML** _(MarkAsSpamEmbedTagsInHtml)_||
|**Formulärtaggar i HTML** _(MarkAsSpamFormTagsInHtml)_||
|**Webbbuggar i HTML** _(MarkAsSpamWebBugsInHtml)_||
|**Använda listan över känsliga ord** _(MarkAsSpamSensitiveWordList)_||
|**SPF-post: hård fail** _(MarkAsSpamSpfRecordHardFail_)||
|**Filtrering av villkorsstyrd avsändare-ID: hårt fel** _(MarkAsSpamFromAddressAuthFail)_||
|**NDR backscatter** _(MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Principinställningar för eOP-utgående skräppost

Information om hur du skapar och konfigurerar principer för utgående skräppost finns i [Konfigurera utgående skräppostfiltrering i Office 365.](configure-the-outbound-spam-policy.md)

Mer information om standardbegränsningar för sändning i tjänsten finns i [Sändningsgränser.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Maximalt antal mottagare per användare: Gräns för extern timme** <p> _RecipientLimitExternalPerHour_|0|500|400|Standardvärdet 0 innebär att tjänstens standardinställningar används.|
|**Maximalt antal mottagare per användare: Gräns för intern timme** <p> _RecipientLimitInternalPerHour_|0|1000|800|Standardvärdet 0 innebär att tjänstens standardinställningar används.|
|**Maximalt antal mottagare per användare: Daglig gräns** <p> _RecipientLimitPerDay_|0|1000|800|Standardvärdet 0 innebär att tjänstens standardinställningar används.|
|**Åtgärd när en användare överskrider gränserna** <p> _ActionWhenThresholdReached_|**Begränsa användarens sändning av e-post till följande dag** <p> `BlockUserForToday`|**Hindra användaren från att skicka e-post** <p> `BlockUser`|**Hindra användaren från att skicka e-post** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Principinställningar för EOP-skydd mot skadlig programvara

Information om hur du skapar och konfigurerar principer för skadlig programvara finns [i Konfigurera principer för skadlig programvara i Office 365.](configure-anti-malware-policies.md)

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Vill du meddela mottagarna om meddelandena har satts i karantän?** <p> _Åtgärd_|Nej <p> _DeleteMessage_|Nej <p> _DeleteMessage_|Nej <p> _DeleteMessage_|Om skadlig programvara identifieras i en e-postbilaga sätts meddelandet i karantän och kan bara släppas av en administratör.|
|**Vanliga typer av bifogade filer** <p> _EnableFileFilter_|Av <p> `$false`|På <p> `$true`|På <p> `$true`|Med den här inställningen sätts meddelanden som innehåller körbara bifogade filer i karantän baserat på filtyp, oavsett innehållet i den bifogade filen.|
|**Malware Zero-hour Auto Purge** <p> _ZapEnabled_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Meddela interna avsändare om** meddelandet som inte kan inte längre <p> _EnableInternalSenderNotifications_|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`||
|**Meddela externa avsändare om** meddelandet som inte längre kan förts fram <p> _EnableExternalSenderNotifications_|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Standardinställningar för EOP-policy mot nätfiske

Mer information om de här inställningarna finns i [Inställningarna för förfalskning.](set-up-anti-phishing-policies.md#spoof-settings) Information om hur du konfigurerar de här [inställningarna finns i Konfigurera principer för nätfiske i EOP.](configure-anti-phishing-policies-eop.md)

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Aktivera skydd mot förfalskning** <p> _EnableSpoofIntelligence_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Aktivera oauthenticerad avsändare** <p> _EnableUnauthenticatedSender_|På <p> `$true`|På <p> `$true`|På <p> `$true`|Lägger till ett frågetecken (?) på avsändarens foto i Outlook för oidentifierade förfalskningsavsändare. Mer information finns i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md)|
|**Om e-post skickas av någon som inte har tillåtelse att kapa din domän** <p> _AuthenticationFailAction_|**Flytta meddelandet till mottagarnas skräppostmappar** <p> `MoveToJmf`|**Flytta meddelandet till mottagarnas skräppostmappar** <p> `MoveToJmf`|**Sätt meddelandet i karantän** <p> `Quarantine`|Den här inställningen gäller för spärrade avsändare [i förfalskningsinformation.](learn-about-spoof-intelligence.md)|
|

## <a name="microsoft-defender-for-office-365-security"></a>Säkerhet i Microsoft Defender för Office 365

Ytterligare säkerhetsfördelar följer med en Microsoft Defender för Office 365-prenumeration. De senaste nyheterna och informationen finns i [Nyheter i Defender för Office 365.](whats-new-in-office-365-atp.md)

> [!IMPORTANT]
>
> - Standardprincipen för skydd mot nätfiske i Microsoft Defender för Office 365 ger skydd mot [förfalskning](set-up-anti-phishing-policies.md#spoof-settings) och postlådeinformation för alla mottagare. Men andra tillgängliga funktioner [för personifieringsskydd](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) och [avancerade inställningar är](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) inte konfigurerade eller aktiverade i standardprincipen. Om du vill aktivera alla skyddsfunktioner ändrar du standardprincipen för skydd mot nätfiske eller skapar ytterligare principer mot nätfiske.
>
> - Det finns inga standardprinciper för säkra länkar eller principer för säkra bifogade filer som automatiskt skyddar alla mottagare i organisationen. För att få skydd måste du skapa minst en princip för säkra länkar och en princip för säkra bifogade filer.
>
> - [Skydd mot säkra bifogade filer i SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md) och skydd mot säkra dokument är inte beroende av principer för säkra länkar. [](safe-docs.md)

Om prenumerationen omfattar Microsoft Defender för Office 365 eller om du har köpt Defender för Office 365 som ett tillägg anger du följande standardkonfigurationer eller strikt konfigurationer.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Inställningar för skydd mot nätfiskeprincip i Microsoft Defender för Office 365

EOP-kunder får grundläggande skydd mot nätfiske enligt beskrivningen ovan, men Microsoft Defender för Office 365 innehåller fler funktioner och kontroller som hjälper till att förhindra, identifiera och åtgärda mot attacker. Information om hur du skapar och konfigurerar dessa [principer finns i Konfigurera principer för nätfiske i Defender för Office 365.](configure-atp-anti-phishing-policies.md)

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Inställningar för personifiering i principer för skydd mot nätfiske i Microsoft Defender för Office 365

Mer information om de här inställningarna finns i inställningarna för personifiering i principer för skydd mot nätfiske [i Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Information om hur du konfigurerar de [här inställningarna finns i Konfigurera principer för nätfiske i Defender för Office 365.](configure-atp-anti-phishing-policies.md)

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|Skyddade användare: **Lägga till användare som ska skyddas** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Av <p> `$false` <p> none (ingen)|På <p> `$true` <p> \<list of users\>|På <p> `$true` <p> \<list of users\>|Beroende på din organisation rekommenderar vi att du lägger till användare (meddelandeavsändare) i nyckelroller. Internt kan skyddade avsändare vara din VD, ekonomichef och andra högre chefer. Externa, skyddade avsändare kan vara direktörer eller direktörer.|
|Skyddade domäner: **Inkludera automatiskt de domäner jag äger** <p> _EnableOrganizationDomainsProtection_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|Skyddade domäner: **Inkludera egna domäner** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Av <p> `$false` <p> none (ingen)|På <p> `$true` <p> \<list of domains\>|På <p> `$true` <p> \<list of domains\>|Beroende på din organisation rekommenderar vi att du lägger till domäner (avsändardomäner) som du inte äger, men som du ofta interagerar med.|
|Skyddade användare: **Om e-post skickas av en imiterad användare** <p> _TargetedUserProtectionAction_|**Använd ingen åtgärd** <p> `NoAction`|**Sätt meddelandet i karantän** <p> `Quarantine`|**Sätt meddelandet i karantän** <p> `Quarantine`||
|Skyddade domäner: **Om e-post skickas av en imiterad domän** <p> _TargetedDomainProtectionAction_|**Använd ingen åtgärd** <p> `NoAction`|**Sätt meddelandet i karantän** <p> `Quarantine`|**Sätt meddelandet i karantän** <p> `Quarantine`||
|**Visa tips för imiterade användare** <p> _EnableSimilarUsersSafetyTips_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Visa tips för imiterade domäner** <p> _EnableSimilarDomainsSafetyTips_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Visa tips för ovanliga tecken** <p> _EnableUnusualCharactersSafetyTips_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Aktivera inkorgsinformation?** <p> _EnableMailboxIntelligence_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Aktivera postlådebaserat personifieringsskydd?** <p> _EnableMailboxIntelligenceProtection_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Om e-post skickas av en imiterad användare som skyddas av postlådeinformation** <p> _MailboxIntelligenceProtectionAction_|**Använd ingen åtgärd** <p> `NoAction`|**Flytta meddelandet till mottagarnas skräppostmappar** <p> `MoveToJmf`|**Sätt meddelandet i karantän** <p> `Quarantine`||
|**Betrodda avsändare** <p> _ExcludedSenders_|Inga|Inga|Inga|Beroende på din organisation rekommenderar vi att du lägger till användare som felaktigt markeras som nätfiske på grund av endast personifiering och inte andra filter.|
|**Betrodda domäner** <p> _ExcludedDomains_|Inga|Inga|Inga|Beroende på din organisation rekommenderar vi att du lägger till domäner som felaktigt markeras som nätfiske på grund av endast personifiering och inte andra filter.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Inställningar för förfalskning i principer för skydd mot nätfiske i Microsoft Defender för Office 365

Observera att det är samma inställningar som finns i inställningarna [för skydd mot skräppostprincip i EOP.](#eop-anti-spam-policy-settings)

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|---|---|---|---|
|**Aktivera skydd mot förfalskning** <p> _EnableSpoofIntelligence_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Aktivera oauthenticerad avsändare** <p> _EnableUnauthenticatedSender_|På <p> `$true`|På <p> `$true`|På <p> `$true`|Lägger till ett frågetecken (?) på avsändarens foto i Outlook för oidentifierade förfalskningsavsändare. Mer information finns i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md)|
|**Om e-post skickas av någon som inte har tillåtelse att kapa din domän** <p> _AuthenticationFailAction_|**Flytta meddelandet till mottagarnas skräppostmappar** <p> `MoveToJmf`|**Flytta meddelandet till mottagarnas skräppostmappar** <p> `MoveToJmf`|**Sätt meddelandet i karantän** <p> `Quarantine`|Den här inställningen gäller för spärrade avsändare [i förfalskningsinformation.](learn-about-spoof-intelligence.md)|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Avancerade inställningar i principer för skydd mot nätfiske i Microsoft Defender för Office 365

Mer information om den här inställningen finns i Avancerade tröskelvärden för nätfiske i principer mot nätfiske i [Microsoft Defender för Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Information om hur du konfigurerar den [här inställningen finns i Konfigurera principer för nätfiske i Defender för Office 365.](configure-atp-anti-phishing-policies.md)

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Avancerade tröskelvärden för nätfiske** <p> _PhishThresholdLevel_|**1 – Standard** <p> `1`|**2 – Aggressiv** <p> `2`|**3 – Mer aggressiva** <p> `3`||
|

### <a name="safe-links-settings"></a>Inställningar för säkra länkar

Säkra länkar i Defender för Office 365 innehåller globala inställningar som gäller för alla användare som ingår i aktiva principer för säkra länkar och inställningar som är specifika för varje princip för säkra länkar. Mer information finns i [Säkra länkar i Defender för Office 365.](atp-safe-links.md)

#### <a name="global-settings-for-safe-links"></a>Globala inställningar för Säkra länkar

Information om hur du konfigurerar de här inställningarna finns i Konfigurera globala inställningar för [Säkra länkar i Defender för Office 365.](configure-global-settings-for-safe-links.md)

I PowerShell använder du cmdleten [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) för de här inställningarna.

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Använda säkra länkar i: Office 365-program** <p> _EnableSafeLinksForO365Clients_|På <p> `$true`|På <p> `$true`|På <p> `$true`|Använd Säkra länkar i Office 365-skrivbords- och mobilprogram (iOS och Android). Mer information finns i inställningarna [för Säkra länkar för Office 365-appar.](atp-safe-links.md#safe-links-settings-for-office-365-apps)|
|**Spåra inte när användare klickar på Säkra länkar** <p> _TrackClicks_|På <p> `$false`|Av <p> `$true`|Av <p> `$true`|Om du inaktiverar den här inställningen (ställa in _TrackClicks_ `$true` till) spåras användarklick i Office 365-program som stöds.|
|**Låt inte användare klicka genom Säkra länkar till den ursprungliga URL:en** <p> _AllowClickThrough_|På <p> `$false`|På <p> `$false`|På <p> `$false`|Om du använder den här inställningen (inställningen _AllowClickThrough_ till) förhindrar du att du klickar dig fram till den ursprungliga `$false` URL:en i Office 365-program som stöds.|
|

#### <a name="safe-links-policy-settings"></a>Principinställningar för säkra länkar

Information om hur du konfigurerar de här inställningarna finns i Konfigurera principer för säkra [länkar i Microsoft Defender för Office 365.](set-up-atp-safe-links-policies.md)

I PowerShell använder du [cmdlets New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) [och Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) för de här inställningarna.

> [!NOTE]
> Som vi beskrivit tidigare finns det ingen standardprincip för säkra länkar. Värdena i kolumnen Standard är standardvärdena i de nya principer för säkra länkar som du skapar.

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Välj åtgärden för okända potentiellt skadliga URL:er i meddelanden** <p> _IsEnabled_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Välj åtgärden för okända eller potentiellt skadliga URL-adresser i Microsoft Teams** <p> _EnableSafeLinksForTeams_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Använda URL-genomsökning i realtid för misstänkta länkar och länkar som pekar på filer** <p> _ScanUrls_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Vänta tills URL-skanningen har slutförts innan meddelandet levereras** <p> _DeliverMessageAfter Ent_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Använda säkra länkar i e-postmeddelanden som skickas inom organisationen** <p> _EnableForInternalSenders_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Spåra inte användarklick** <p> _DoNotTrackUserClicks_|Av <p> `$false`|Av <p> `$false`|Av <p> `$false`|Om du inaktiverar den här _inställningen (inställningen DoNotTrackUserClicks_ `$false` till) spåras användarnas klick.|
|**Tillåt inte att användare klickar till den ursprungliga URL:en** <p> _DoNotAllowClickThrough_|Av <p> `$false`|På <p> `$true`|På <p> `$true`|Om du använder den här inställningen _(inställningen DoNotAllowClickThrough_ till) går `$true` du inte vidare till den ursprungliga URL:en.|
|

### <a name="safe-attachments-settings"></a>Inställningar för säkra bifogade filer

Säkra bifogade filer i Microsoft Defender för Office 365 innehåller globala inställningar som inte har något samband med principer för säkra bifogade filer och inställningar som är specifika för varje princip för säkra länkar. Mer information finns i Säkra [bifogade filer i Defender för Office 365.](atp-safe-attachments.md)

#### <a name="global-settings-for-safe-attachments"></a>Globala inställningar för säkra bifogade filer

Information om hur du konfigurerar de här inställningarna finns i Aktivera Säkra bifogade filer för [SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) och Säkra dokument i [Microsoft 365 E5.](safe-docs.md)

I PowerShell använder du cmdleten [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) för de här inställningarna.

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Aktivera Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams.** <p> _EnableATPForSPOTeamsODB_|På <p> `$true`|På <p> `$true`||
|**Aktivera Säkra dokument för Office-klienter** <p> _EnableSafeDocs_|På <p> `$true`|På <p> `$true`|Den här inställningen är endast tillgänglig med Säkerhetslicenser för Microsoft 365 E5 eller Microsoft 365 E5. Mer information finns i [Säkra dokument i Microsoft Defender för Office 365.](safe-docs.md)|
|**Tillåt att andra klickar i Skyddad vy även om filen identifierats som skadlig i Säkra dokument** <p> _AllowSafeDocsOpen_|Av <p> `$false`|Av <p> `$false`|Den här inställningen är relaterad till Säkra dokument.|
|

#### <a name="safe-attachments-policy-settings"></a>Principinställningar för säkra bifogade filer

Information om hur du konfigurerar de här inställningarna finns i Konfigurera principer [för säkra bifogade filer i Defender för Office 365.](set-up-atp-safe-attachments-policies.md)

I PowerShell använder du [cmdlets New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) [och Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) för de här inställningarna.

> [!NOTE]
> Som vi beskrivit tidigare finns det ingen standardprincip för säkra bifogade filer. Värdena i kolumnen Standard är standardvärdena i nya principer för säkra bifogade filer som du skapar.

****

|Namn på säkerhetsfunktion|Standard|Standard|Strikt|Kommentar|
|---|:---:|:---:|:---:|---|
|**Okänd kod för säkra bifogade filer** <p> _Åtgärd_|Blockera <p> `Block`|Blockera <p> `Block`|Blockera <p> `Block`||
|**Omdirigering av bifogade filer vid identifiering:** **Aktivera omdirigering** <p> _Omdirigera_ <p> _RedirectAddress_|Av och ingen e-postadress har angetts. <p> `$true` <p> none (ingen)|På och ange en e-postadress. <p> `$true` <p> en e-postadress|På och ange en e-postadress. <p> `$true` <p> en e-postadress|Omdirigera meddelanden till en säkerhetsadministratör för granskning.|
|**Använd ovanstående val om skadlig programvara söker efter bifogade filer på en gång eller om det uppstår fel.** <p> _ActionOnError_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|

## <a name="related-articles"></a>Relaterade artiklar

- Letar du efter rekommendationer för **e-postflödesregler i Exchange (kallas även transportregler)?** Se [rekommendationer för konfigurering av e-postflödesregler i Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)

- Administratörer och användare kan skicka falska positiva meddelanden (bra e-postmeddelanden som markerats som dåliga) och falska negativa meddelanden (felaktig e-post tillåts) till Microsoft för analys. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- Använd de här länkarna för information om hur **du konfigurerar** [EOP-tjänsten](set-up-your-eop-service.md) **och konfigurerar** [Microsoft Defender för Office 365.](office-365-atp.md) Glöm inte de användbara anvisningarna i Skydda[mot hot i Office 365.](protect-against-threats.md)

- Här hittar du säkerhetsbaslinjer för **Windows:** Var hittar jag säkerhetsbaslinjerna? för GPO/lokala alternativ och Använd säkerhetsbaslinjer för att konfigurera [Windows 10-enheter i Intune för Intune-baserad](https://docs.microsoft.com/intune/protect/security-baselines) säkerhet. [](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) Slutligen finns det en jämförelse mellan Microsoft Defender för Slutpunkt och Microsoft Intune-säkerhetsbaslinjer i Jämför Microsoft Defender för slutpunkten och [Windows Intune-säkerhetsbaslinjerna.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
