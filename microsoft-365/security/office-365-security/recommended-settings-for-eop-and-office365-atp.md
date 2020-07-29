---
title: Microsoft-rekommendationer för EOP- och Office 365 ATP-säkerhetsinställningar, rekommendationer, Sender Policy Framework, Domain-based Message Reporting and Conformance, DomainKeys Identified Mail, steg, hur fungerar det, säkerhetsbaslinjer, baslinjer för EOP, baslinjer för ATP, setup ATP, setup EOP, konfigurera ATP, konfigurera EOP, säkerhetskonfiguration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Vilka är bästa metoderna för säkerhetsinställningar för Exchange Online Protection (EOP) och Advanced Threat Protection (ATP). Vilka är de nuvarande rekommendationerna för standardskydd? Vad ska användas om du vill vara striktare? Och vilka extrafunktioner får du om du också använder Advanced Threat Protection (ATP)?
ms.openlocfilehash: f34c4e0aad2413fdeb082c37f980e6e4548db6b3
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430381"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Rekommenderade inställningar för EOP- och Office 365 ATP-säkerhet

**Exchange Online Protection (EOP)** är kärnan i säkerheten för Microsoft 365-prenumerationer och hjälper till att förhindra att skadliga e-postmeddelanden når dina anställdas inkorgar. Men med nya, mer sofistikerade attacker som växer fram varje dag, krävs ofta bättre skydd. **Office 365 Avancerat skydd mot hot (ATP)** ATP Plan 1 eller ATP Plan 2 innehåller ytterligare funktioner som ger administratörer fler lager av säkerhet, kontroll och undersökning.

Även om vi ger säkerhetsadministratörer möjlighet att anpassa sina säkerhetsinställningar finns det två säkerhetsnivåer i EOP och Office 365 ATP som vi rekommenderar: **Standard** och **Strikt**. Varje kunds miljö och behov är olika, men vi tror att dessa nivåer av e-postfiltrering konfigurationer kommer att bidra till att förhindra oönskad e-post från att nå dina anställdas inkorg i de flesta situationer.

Om du vill använda standardinställningarna eller Strikta inställningar automatiskt för användare finns [i Förinställda säkerhetsprinciper i EOP och Office 365 ATP](preset-security-policies.md).

> [!IMPORTANT]
> Skräppostregeln måste aktiveras på en postlåda för att filtrering ska fungera korrekt. Det är aktiverat som standard, men du bör kontrollera det om filtrrering inte verkar fungera. Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor i Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

I det här avsnittet beskrivs de här inställningarna som rekommenderas från Microsoft för att skydda användarna.

> [!TIP]
> Det finns en ny PowerShell-modul som du kan hämta kallas Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) som hjälper till att avgöra några av dessa inställningar. När du kör som administratör i din klientorganisation kommer Get-ORCAReport att bidra till att generera en bedömning av inställningarna för anti-spam, anti-phish och andra inställningar för meddelandehygien. Du kan ladda ner denna modul på https://www.powershellgallery.com/packages/ORCA/ .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Anti-spam, anti-malware och anti-phishing skydd i EOP

Anti-spam, anti-malware och anti-phishing är funktioner i EOP som kan konfigureras av administratörer. Vi rekommenderar följande konfigurationer.

### <a name="eop-anti-spam-policy-settings"></a>EOP-principinställningar mot skräppost

Om du vill skapa och konfigurera principer mot skräppost finns i [Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|**Åtgärder** för identifiering av skräppost <br/><br/> _SpamAction (Skräppost)_|**Flytta meddelande till mappen Skräppost** <br/><br/> `MoveToJmf`|**Karantänmeddelande** <br/><br/> `Quarantine`||
|**Åtgärder för** att upptäcka skräppost med högt förtroende <br/><br/> _HögtrohetSpamAction_|**Karantänmeddelande** <br/><br/> `Quarantine`|**Karantänmeddelande** <br/><br/> `Quarantine`||
|Identifiering av **nätfiskemeddelanden** <br/><br/> _PhishSpamAction (PhishSpamAction)_|**Karantänmeddelande** <br/><br/> `Quarantine`|**Karantänmeddelande** <br/><br/> `Quarantine`||
|**Identifiering av nätfiskemeddelanden med högt förtroende** <br/><br/> _HögkonfidenceFishAction_|**Karantänmeddelande** <br/><br/> `Quarantine`|**Karantänmeddelande** <br/><br/> `Quarantine`||
|**Massident e-identifiering** åtgärd <br/><br/> _BulkSpamAction_|**Flytta meddelande till mappen Skräppost** <br/><br/> `MoveToJmf`|**Karantänmeddelande** <br/><br/> `Quarantine`||
|Tröskelvärde för massutskick av e-post <br/><br/> _BulkThreshold_|6|4|Standardvärdet är för närvarande 7, men vi rekommenderar att du ändrar det till 6. Mer information finns i [BCL (Bulk complaint level) i Office 365](bulk-complaint-level-values.md).|
|Kvarhållningsperiod för karantän <br/><br/> _KarantänReentionPeriod_|30 dagar|30 dagar||
|**Säkerhetstips** <br/><br/> _InlineSafetyTipsEnbard_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|Tillåtna avsändare <br/><br/> _Tillåtnasändare_|Inga|Inga||
|Tillåtna avsändningsdomäner <br/><br/> _AllowedSenderDomains_|Inga|Inga|Det krävs inte att du lägger till domäner som du äger (kallas även _godkända domäner)_ i listan över tillåtna avsändare. I själva verket är det anses hög risk eftersom det skapar möjligheter för dåliga aktörer att skicka e-post som annars skulle filtreras bort. Använd [falska underrättelser](learn-about-spoof-intelligence.md) i security & Compliance Center på sidan Inställningar mot **skräppost** för att granska alla avsändare som förfalskar avsändande e-postadresser i organisationens e-postdomäner eller förfalskar e-postadresser för avsändaren i externa domäner.|
|Blockerade avsändare <br/><br/> _Blockeradesändare_|Inga|Inga||
|Blockerade avsändaredomäner <br/><br/> _BlockeradeSenderDomäner_|Inga|Inga||
|**Aktivera skräppostmeddelanden för slutanvändare** <br/><br/> _AktiveraEndUserSpamNotifications_|Aktiverad <br/><br/> `$true`|Aktiverad <br/><br/> `$true`||
|**Skicka skräppostmeddelanden för slutanvändare var (dagar)** <br/><br/> _EndUserSpamNotificationFransk_|3 dagar|3 dagar||
|**Spam ZAP** <br/><br/> _SpamZapEnabled_|Aktiverad <br/><br/> `$true`|Aktiverad <br/><br/> `$true`||
|**Phish ZAP** <br/><br/> _PhishZapEnabled_|Aktiverad <br/><br/> `$true`|Aktiverad <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|På|På|Den här inställningen är endast tillgänglig i PowerShell.|
|

Det finns flera andra asf-inställningar (Advanced Spam Filter) i anti-spam-policyer som håller på att vara inaktuella. Mer information om tidslinjerna för avskrivning av dessa funktioner kommer att meddelas utanför det här avsnittet.

Vi rekommenderar att du inaktiverar dessa **ASF-inställningar** för både **standard-** och **strikta** nivåer. Mer information om ASF-inställningar finns [i ASF-inställningar (Advanced Spam Filter) i Office 365](advanced-spam-filtering-asf-options.md).

|Namn på säkerhetsfunktionen|Kommentar|
|---|---|
|**Bildlänkar till fjärrplatser** _(IncreaseScoreWithImageLinks)_||
|**Numerisk IP-adress i URL** _(IncreaseScoreWithNumericIps_)||
|**UL omdirigera till annan port** _(IncreaseScoreWithRedirectToOtherPort_)||
|**URL till .biz eller .info webbplatser** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Tomma meddelanden** (_MarkAsSpamEmptyMessages_)||
|**JavaScript eller VBScript i HTML** _(MarkAsSpamJavaScriptInHtml_)||
|**Bildruta- eller IFrame-taggar i HTML** _(MarkAsSpamFramesInHtml_)||
|**Objekttaggar i HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Bädda in taggar i HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Formulärtaggar i HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Webbfel i HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Använd känslig ordlista** (_MarkAsSpamSensitiveWordList_)||
|**SPF-post: hårt misslyckas** _(MarkAsSpamSpfRecordHardFail_)||
|**Filtrering av villkorlig avsändare: hårddisk misslyckas** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP-utgående skräppostprincipinställningar

Om du vill skapa och konfigurera principer för skräppost för utgående skräppost finns [i Konfigurera skräppostfiltrering i Office 365](configure-the-outbound-spam-policy.md).

Mer information om standardgränserna för sändning i tjänsten finns i [Skicka gränser](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|**Maximalt antal mottagare per användare: Gräns för extern timme** <br/><br/> _MottagareLimitExternalPerHour_|500|400||
|**Maximalt antal mottagare per användare: Gräns för intern timme** <br/><br/> _MottagareLimitInternalPerHour_|1000|800||
|**Maximalt antal mottagare per användare: Daglig gräns** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**Åtgärd när en användare överskrider gränserna** <br/><br/> _ÅtgärdNärDessholdReached_|**Hindra användaren från att skicka e-post** <br/><br/> `BlockUser`|**Hindra användaren från att skicka e-post** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP-principinställningar för skadlig kod

Om du vill skapa och konfigurera principer mot skadlig kod finns [i Konfigurera principer mot skadlig kod i Office 365](configure-anti-malware-policies.md).

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|**Vill du meddela mottagarna om deras meddelanden sätts i karantän?** <br/><br/> _Åtgärder_|Nej <br/><br/> _Ta bortMessage_|Nej <br/><br/> _Ta bortMessage_|Om skadlig kod upptäcks i en bifogad fil i ett e-postmeddelande sätts meddelandet i karantän och kan endast släppas av en administratör.|
|**Filter för vanliga typer av bifogade filer** <br/><br/> _EnableFileFilter_|På <br/><br/> `$true`|På <br/><br/> `$true`|Den här inställningen sätter meddelanden i karantän som innehåller körbara bilagor baserat på filtyp, oavsett innehållet i bifogade filer.|
|**Automatisk rensning av skadlig kod noll timmar** <br/><br/> _ZapEnabled (påförande)_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Meddela interna avsändare** av det olevererade meddelandet <br/><br/> _AktiveraInternalSenderAnmälningar_|Inaktiverad <br/><br/> `$false`|Inaktiverad <br/><br/> `$false`||
|**Meddela externa avsändare** av det olevererade meddelandet <br/><br/> _AktiveraExternalSenderAnmälningar_|Inaktiverad <br/><br/> `$false`|Inaktiverad <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP:s standardinställningar för principen mot nätfiske

Mer information om dessa inställningar finns i [Spoof-inställningar](set-up-anti-phishing-policies.md#spoof-settings). Hur du konfigurerar dessa inställningar finns i [Konfigurera principer för nätfiske i EOP](configure-anti-phishing-policies-eop.md).

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|**Aktivera förfalskningsskydd** <br/><br/> _AktiveraAntispoofEnforcement_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Aktivera oautentiserade avsändare** <br/><br/> _AktiveraUnauthenticatedSender_|På <br/><br/> `$true`|På <br/><br/> `$true`|Lägger till ett frågetecken (?) i avsändarens foto i Outlook för oidentifierade förfalskade avsändare. Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md).|
|**Om e-post skickas av någon som inte får förfalska din domän** <br/><br/> _AutentiseringFailAction_|**Flytta meddelande till mottagarnas skräppostmappar** <br/><br/> `MoveToJmf`|**Karantän meddelandet** <br/><br/> `Quarantine`|Detta gäller blockerade avsändare i [falska underrättelser](learn-about-spoof-intelligence.md).|
|

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 Avancerad säkerhet för skydd mot hot

Ytterligare säkerhetsfördelar med en Office 365 Advanced Threat Protection-prenumeration (ATP). De senaste nyheterna och informationen finns i Nyheter och NYHETER [i Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP innehåller principerna För säker bifogad fil och säkra länkar för att förhindra att e-post med potentiellt skadliga bilagor levereras och för att hindra användare från att klicka på potentiellt osäkra webbadresser.

> [!IMPORTANT]
> Avancerad anti-phishing är en av fördelarna med en Office 365 ATP-prenumeration. Även om den är aktiverad som standard ***måste*** du konfigurera minst en anti-phishing-princip innan den kan börja filtrera e-post. Att glömma att konfigurera principer mot nätfiske kan utsätta användare för riskfyllda e-postmeddelanden. Var noga med att konfigurera dina anti-phishing-principer när du har lagt till en Office 365 ATP-prenumeration.

Om du har lagt till en Office 365 ATP-prenumeration i EOP anger du följande konfigurationer.

### <a name="office-atp-anti-phishing-policy-settings"></a>Inställningar för office ATP-principen mot nätfiske

EOP-kunder får grundläggande nätfiske som tidigare beskrivits, men Office 365 ATP innehåller fler funktioner och kontroller för att förebygga, upptäcka och åtgärda mot attacker. Om du vill skapa och konfigurera dessa principer finns i [Konfigurera ATP-principer för nätfiske i Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Inställningar för personifiering i ATP:s principer för phishing-phishing

Mer information om dessa inställningar finns [i Inställningar för personifiering i ATP:s principer för phishing.](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies) Hur du konfigurerar de här inställningarna finns i [Konfigurera ATP-principer för nätfiske](configure-atp-anti-phishing-policies.md).

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|Skyddade användare: **Lägg till användare för att skydda** <br/><br/> _AktiveraMålsbegäraSkydd_ <br/><br/> _TargetedAnvändareTillSkydd_|På <br/><br/> `$true` <br/><br/> \<list of users\>|På <br/><br/> `$true` <br/><br/> \<list of users\>|Beror på din organisation, men vi rekommenderar att du lägger till användare i viktiga roller. Internt kan dessa vara din VD, CFO och andra ledande befattningshavare. Externt kan dessa omfatta rådsmedlemmar eller din styrelse.|
|Skyddade domäner: **Inkludera automatiskt de domäner jag äger** <br/><br/> _AktiveraOrganisationDomainsSkydd_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|Skyddade domäner: **Inkludera anpassade domäner** <br/><br/> _AktiveraMålsbeställddomBeskydd_ <br/><br/> _TargetedDomainsToProtect_|På <br/><br/> `$true` <br/><br/> \<list of domains\>|På <br/><br/> `$true` <br/><br/> \<list of domains\>|Beror på din organisation, men vi rekommenderar att du lägger till domäner som du ofta interagerar med som du inte äger.|
|Skyddade användare: **Om e-post skickas av en personifierad användare** <br/><br/> _TargetedUserProtectionAction_|**Karantän meddelandet** <br/><br/> `Quarantine`|**Karantän meddelandet** <br/><br/> `Quarantine`||
|Skyddade domäner: **Om e-post skickas av en domän som personifieras** <br/><br/> _TargetedDomainProtectionAction_|**Karantän meddelandet** <br/><br/> `Quarantine`|**Karantän meddelandet** <br/><br/> `Quarantine`||
|**Visa tips för personifierade användare** <br/><br/> _EnableSimilarUsersSafetyTips_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Visa tips för personifierade domäner** <br/><br/> _AktiveraSimilarDomäntips_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Visa tips för ovanliga tecken** <br/><br/> _AktiveraOsexuelladiagramtips_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Aktivera postlådeinformation?** <br/><br/> _AktiveraPostboxIntelligens_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Vill du aktivera intelligensbaserat personifieringsskydd för postlåda?** <br/><br/> _AktiveraPostboxIntelligenceProtection_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Om e-post skickas av en personifierad användare som skyddas av postlådeinformation** <br/><br/> _MailboxIntelligenceProtectionAction_|**Flytta meddelande till mottagarnas skräppostmappar** <br/><br/> `MoveToJmf`|**Karantän meddelandet** <br/><br/> `Quarantine`||
|**Betrodda avsändare** <br/><br/> _UteslutnaS-avsändare_|Inga|Inga|Beror på din organisation, men vi rekommenderar att du lägger till användare som felaktigt markeras som phish på grund av personifiering och inte andra filter.|
|**Betrodda domäner** <br/><br/> _UteslutnaDomäner_|Inga|Inga|Beror på din organisation, men vi rekommenderar att du lägger till domäner som felaktigt markeras som phish på grund av personifiering och inte andra filter.|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Falska inställningar i ATP:s principer för phishing-phishing

Observera att det är samma inställningar som är tillgängliga i [principinställningarna mot skräppost i EOP](#eop-anti-spam-policy-settings).

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|**Aktivera förfalskningsskydd** <br/><br/> _AktiveraAntispoofEnforcement_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Aktivera oautentiserade avsändare** <br/><br/> _AktiveraUnauthenticatedSender_|På <br/><br/> `$true`|På <br/><br/> `$true`|Lägger till ett frågetecken (?) i avsändarens foto i Outlook för oidentifierade förfalskade avsändare. Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md).|
|**Om e-post skickas av någon som inte får förfalska din domän** <br/><br/> _AutentiseringFailAction_|**Flytta meddelande till mottagarnas skräppostmappar** <br/><br/> `MoveToJmf`|**Karantän meddelandet** <br/><br/> `Quarantine`|Detta gäller blockerade avsändare i [falska underrättelser](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Avancerade inställningar i ATP:s principer för phishing-phishing

Mer information om den här inställningen finns [i Avancerade tröskelvärden för nätfiske i ATP:s principer för nätfiske](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies). Den här inställningen finns i [Konfigurera ATP-principer för nätfiske](configure-atp-anti-phishing-policies.md).

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|**Avancerade tröskelvärden för nätfiske** <br/><br/> _PhishThresholdLevel_|**2 - Aggressiv** <br/><br/> `2`|**3 - Mer aggressiv** <br/><br/> `3`||

### <a name="atp-safe-links-policy-settings"></a>ATP-principinställningar för säkra länkar

Information om hur du konfigurerar de här inställningarna finns i [Konfigurera principer för betrodda länkar för Office 365 ATP](set-up-atp-safe-links-policies.md).

#### <a name="safe-links-policy-settings-in-the-default-policy-for-all-users"></a>Principinställningar för säkra länkar i standardprincipen för alla användare

**I**PowerShell använder du [cmdleten Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) för dessa inställningar.

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|**Använda säkra länkar i: Office 365-program** <br/><br/> _EnableSafeLinksForO365Clients_|På <br/><br/> `$true`|På <br/><br/> `$true`|Använd ATP Safe Links i Office 365-klienter (stationära och mobila datorer) (iOS och Android).|
|**Använda säkra länkar i: Office Web Access Companions** <br/><br/> _AktiveraSafeLinksForWebAccessCompanion_|På <br/><br/> `$true`|På <br/><br/> `$true`|Använd BETRODDa ATP-länkar i Office Web Apps.|
|**Spåra inte när användare klickar på säkra länkar** <br/><br/> _TrackClicks (Spår)_|Av <br/><br/> `$true`|Av <br/><br/> `$true`||
|**Låt inte användare klicka igenom säkra länkar till den ursprungliga webbadressen** <br/><br/> _TillåtClick-genomgången_|På <br/><br/> `$false`|På <br/><br/> `$false`||
|

#### <a name="safe-links-policy-settings-in-custom-policies-for-specific-users"></a>Principinställningar för säkra länkar i anpassade principer för specifika användare

**I**PowerShell använder du cmdletsen [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) och [Set-SafeLinksPolicy]( https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy ] för dessa inställningar.

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|**Välj åtgärden för okända potentiellt skadliga url:er i meddelanden** <br/><br/> _ÄrEnabled_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Välj åtgärden för okända eller potentiellt skadliga webbadresser i Microsoft Teams** <br/><br/> _EnableSafeLinksForTeams_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Använda URL-skanning i realtid efter misstänkta länkar och länkar som pekar på filer** <br/><br/> _ScanUrls_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Vänta tills URL-skanningen har slutförts innan meddelandet levereras** <br/><br/> _LevereraMessageAfterScan_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Använda säkra länkar till e-postmeddelanden som skickas inom organisationen** <br/><br/> _AktiveraFörinternalSenders_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Spåra inte när användare klickar på säkra länkar** <br/><br/> _DoNotTrackUserClicks_|Av <br/><br/> `$false`|Av <br/><br/> `$false`|
|**Låt inte användare klicka igenom säkra länkar till den ursprungliga webbadressen** <br/><br/> _DoNotAllowClickGenomgenom_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|

### <a name="atp-safe-attachments-policy-settings"></a>ATP Principinställningar för säkra bifogade filer

Information om hur du konfigurerar de här inställningarna finns i Konfigurera principer för [betrodda anslutningspunkter för Office 365 ATP](set-up-atp-safe-attachments-policies.md).

#### <a name="safe-attachments-policy-settings-in-the-default-policy-for-all-users"></a>Principinställningar för säkra bifogade filer i standardprincipen för alla användare

**I**PowerShell använder du [cmdleten Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) för dessa inställningar.

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|**Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** <br/><br/> _AktiveraATPForSPOTeamsODB_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Aktivera säkra dokument för Office-klienter**<bt/><br/> _EnableSafeDocs_|På <br/><br/> `$true`|På <br/><br/> `$true`||Den här inställningen är endast tillgänglig med Microsoft 365 E5- eller Microsoft 365 E5-säkerhetslicenser. Mer information finns [i Säkra dokument i Office 365 Advanced Threat Protection](safe-docs.md).|
|**Tillåt personer att klicka sig igenom skyddad vy även om säkra dokument har identifierat filen som skadlig**<bt/><br/> _AllowSafeDocsÖppna_|Av <br/><br/> `$false`|Av <br/><br/> `$false`||
|

#### <a name="safe-attachments-policy-settings-in-custom-policies-for-specific-users"></a>Principinställningar för säkra bifogade filer i anpassade principer för specifika användare

**I**PowerShell använder du cmdletsen [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) och [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) för dessa inställningar.

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---|---|---|---|
|**Säkra bilagor okänd malware svar** <br/><br/> _Åtgärder_|Blockera <br/><br/> `Block`|Blockera <br/><br/> `Block`||
|**Omdirigera bifogad fil vid identifiering** : **Aktivera omdirigering** <br/><br/> _Omdirigera_ <br/><br/> _Omdirigeraadress_|På och ange en e-postadress. <br/><br/> `$true` <br/><br/> en e-postadress|På och ange en e-postadress. <br/><br/> `$true` <br/><br/> en e-postadress|Omdirigera meddelanden till en säkerhetsadministratör för granskning.|
|**Använd ovanstående val om malware scanning för bilagor time out eller fel inträffar.** <br/><br/> _ActionOnError (_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|

## <a name="related-topics"></a>Relaterade ämnen

- Letar du efter metodtips med **Exchange Mail Flow / Exchange Transport Regler?** Se [den här artikeln](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) för mer information.

- Administratörer och användare kan skicka falska positiva identifieringar (bra e-post markerad som dålig) och falska negativ (dålig e-post tillåten) till Microsoft för analys. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- Använd de här länkarna för information om hur **du konfigurerar** [eOP-tjänsten](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)och **konfigurerar** [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Glöm inte att se de användbara anvisningarna i '[Skydda mot hot i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)'.)

- **Säkerhetsbaslinjer för Windows** finns [här](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) för GPO/lokala alternativ och för Intune-baserad säkerhet [här](https://docs.microsoft.com/intune/protect/security-baselines). Slutligen kan en jämförelse mellan Microsoft Defender Advanced Threat Protection (ATP) och Windows Intune säkerhetsbaslinjer hittas [här](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
