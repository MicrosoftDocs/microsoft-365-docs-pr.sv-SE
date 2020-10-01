---
title: Microsoft-rekommendationer för EOP och Office 365 ATP-säkerhets inställningar, rekommendationer, avsändarens princip ramverk, domänbaserade meddelande rapportering och prosvars regler, DomainKeys identifierat e-post, steg, hur fungerar den, säkerhets bas linjer för EOP, bas linjer för ATP, installation ATP, setup EOP, Configure ATP, Configure EOP, säkerhets konfiguration
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
description: Vilka är de bästa metoderna för säkerhets inställningar för Exchange Online Protection (EOP) och Avancerat skydd (ATP)? Vad är de senaste rekommendationerna för standard skydd? Vad ska användas om du vill veta mer? Och vilka extrafunktioner får du om du även använder avancerat skydd (ATP)?
ms.openlocfilehash: 012bccb265f6b587176eec8f8bed94ce4bf4f211
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328036"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Rekommenderade inställningar för EOP och Office 365 säkerhet för ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP)** är den grundläggande säkerheten för Microsoft 365-prenumerationer och skyddar obehöriga e-postmeddelanden från att nå dina anställdas inkorgar. Men med nya, mer sofistikerade attacker är det ofta nödvändigt att förbättra skyddet varje dag. **Office 365 Avancerat skydd (ATP)** ATP-abonnemang 1 eller ATP-abonnemang 2 innehåller fler funktioner som ger administratörer större kontroll över säkerheten, kontrollen och undersökningen.

Även om vi stärker säkerhets administratören för att anpassa sina säkerhets inställningar finns det två säkerhets nivåer i EOP och Office 365 ATP som vi rekommenderar: **standard** och **strict**. Varje kunds miljö och behov är olika, men vi tror att dessa nivåer av inställningar för e-postfiltrering hindrar oönskad e-post från att nå dina anställdas inkorg i de flesta fall.

Om du automatiskt vill använda standardinställningarna eller strikta inställningar för användare kan du läsa [förvalda säkerhets principer i EOP och Office 365 ATP](preset-security-policies.md).

> [!IMPORTANT]
> Skräp post regeln måste aktive ras på en post låda för att filtreringen ska fungera korrekt. Det är aktiverat som standard, men du bör kontrol lera om det inte verkar fungera. Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor i Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

I det här avsnittet beskrivs dessa Microsoft-rekommenderade inställningar för att skydda användarna.

> [!TIP]
> Det finns en ny PowerShell-modul som du kan hämta som heter Office 365 Advanced Threat Protection (ORCA) som hjälper dig att avgöra vissa av de här inställningarna. När du kör som administratör i klient organisationen kan get-ORCAReport hjälpa till att generera en utvärdering av inställningar för skräp post, anti-Phish och andra meddelanden. Du kan ladda ned den här modulen på https://www.powershellgallery.com/packages/ORCA/ .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Skydd mot skräp post, mot skadlig program vara och mot nätfiske-säkerhet i EOP

Skydd mot skräp post, mot skadlig program vara och mot nätfiske är funktioner i EOP som kan konfigureras av administratörer. Vi rekommenderar följande konfigurationer.

### <a name="eop-anti-spam-policy-settings"></a>EOP princip inställningar för skräp post

Information om hur du skapar och konfigurerar principer för skräp post hantering finns i [Konfigurera principer för skräp post i Office 365](configure-your-spam-filter-policies.md).

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|Åtgärd för **skräp post** <br/><br/> _SpamAction_|**Flytta meddelandet till mappen skräp post** <br/><br/> `MoveToJmf`|**Karantän meddelande** <br/><br/> `Quarantine`||
|Åtgärd för dubblettidentifiering för **snabb meddelanden** <br/><br/> _HighConfidenceSpamAction_|**Karantän meddelande** <br/><br/> `Quarantine`|**Karantän meddelande** <br/><br/> `Quarantine`||
|Åtgärd för identifiering av **nätfiske-e-post** <br/><br/> _PhishSpamAction_|**Karantän meddelande** <br/><br/> `Quarantine`|**Karantän meddelande** <br/><br/> `Quarantine`||
|Åtgärd för **e-post med hög exakthet** <br/><br/> _HighConfidencePhishAction_|**Karantän meddelande** <br/><br/> `Quarantine`|**Karantän meddelande** <br/><br/> `Quarantine`||
|**Mass utskick av e-post** <br/><br/> _BulkSpamAction_|**Flytta meddelandet till mappen skräp post** <br/><br/> `MoveToJmf`|**Karantän meddelande** <br/><br/> `Quarantine`||
|Mass utskick <br/><br/> _BulkThreshold_|18.6|9.4|Standardvärdet är för tillfället 7, men vi rekommenderar att du ändrar det till 6. Mer information finns i [Mass inklagomåls nivå (BCL) i Office 365](bulk-complaint-level-values.md).|
|Karantän period <br/><br/> _QuarantineRetentionPeriod_|30 dagar|30 dagar||
|**Säkerhets tips** <br/><br/> _InlineSafetyTipsEnabled_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|Tillåtna avsändare <br/><br/> _AllowedSenders_|Inga|Inga||
|Tillåtna avsändare-domäner <br/><br/> _AllowedSenderDomains_|Inga|Inga|Det är inte nödvändigt att lägga till domäner som du äger (kallas även _godkända domäner_) i listan med tillåtna avsändare. Faktum är att det är en hög risk eftersom den skapar möjligheter för dåliga aktörer att skicka e-post som annars skulle filtreras bort. Använd [förfalsknings intelligens](learn-about-spoof-intelligence.md) i säkerhets & Compliance Center på sidan **Inställningar för skräp post** för att granska alla avsändare som har falska e-postadresser i organisationens e-postdomäner eller som falska e-postadresser för avsändare i externa domäner.|
|Spärrade avsändare <br/><br/> _BlockedSenders_|Inga|Inga||
|Blockerade avsändare <br/><br/> _BlockedSenderDomains_|Inga|Inga||
|**Aktivera skräp post meddelanden för slutanvändare** <br/><br/> _EnableEndUserSpamNotifications_|Aktiverad <br/><br/> `$true`|Aktiverad <br/><br/> `$true`||
|**Skicka skräp post meddelanden till slutanvändaren var (dagar)** <br/><br/> _EndUserSpamNotificationFrequency_|3 dagar|3 dagar||
|**Spam** <br/><br/> _SpamZapEnabled_|Aktiverad <br/><br/> `$true`|Aktiverad <br/><br/> `$true`||
|**Phish ZAP** <br/><br/> _PhishZapEnabled_|Aktiverad <br/><br/> `$true`|Aktiverad <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|På|På|Den här inställningen är bara tillgänglig i PowerShell.|
|

Det finns flera andra avancerade inställningar för skräp post filter (ASF) i principer för skräp post filtrering som håller på att vara föråldrade. Mer information om tids linjerna för avskrivning av dessa funktioner kommer att förmedlas utanför det här avsnittet.

Vi rekommenderar att **du inaktiverar dessa ASF-inställningar för** både **standard** -och **strikta** nivåer. Mer information om ASF-inställningar finns i [Avancerade inställningar för skräp post filter (ASF) i Office 365](advanced-spam-filtering-asf-options.md).

****

|Säkerhetsfunktionens namn|Kommentar|
|---|---|
|**Bild länkar till fjärranslutna webbplatser** (_IncreaseScoreWithImageLinks_)||
|**Numerisk IP-adress i URL** (_IncreaseScoreWithNumericIps_)||
|**Gruppomdirigera till annan port** (_IncreaseScoreWithRedirectToOtherPort_)||
|**URL till. B2B argumentssida eller. info webbplatser** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Tomma meddelanden** (_MarkAsSpamEmptyMessages_)||
|**Java script eller VBScript i HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Ram-eller iframe-taggar i HTML** (_MarkAsSpamFramesInHtml_)||
|**Objekt-Taggar i HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Bädda in Taggar i HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Formulär koder i HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Webb program fel i HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Använda känslig ord lista** (_MarkAsSpamSensitiveWordList_)||
|**SPF-post: hårda fel** (_MarkAsSpamSpfRecordHardFail_)||
|**ID för villkorsstyrd avsändare: hårda fel** (_MarkAsSpamFromAddressAuthFail_)||
|_AutoMarkAsSpamNdrBackscatter_( **NDR** )||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP utgående princip inställningar för skräp post

Information om hur du skapar och konfigurerar principer för utgående skräp post finns i [Konfigurera utgående skräp post filtrering i Office 365](configure-the-outbound-spam-policy.md).

Mer information om standard begränsningar för sändning av tjänsten finns i begränsningar för [sändning](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|**Maximalt antal mottagare per användare: extern Tim gräns** <br/><br/> _RecipientLimitExternalPerHour_|500|400||
|**Maximalt antal mottagare per användare: intern Tim gräns** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**Maximalt antal mottagare per användare: daglig gräns** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**Åtgärd när en användare överskrider gränserna** <br/><br/> _ActionWhenThresholdReached_|**Hindra användare från att skicka e-post** <br/><br/> `BlockUser`|**Hindra användare från att skicka e-post** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP policy inställningar för mot skadlig program vara

Information om hur du skapar och konfigurerar principer mot skadlig program vara finns i [Konfigurera principer mot skadlig program vara i Office 365](configure-anti-malware-policies.md).

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|**Vill du meddela mottagare om deras meddelanden är i karantän?** <br/><br/> _Fattning_|Nej <br/><br/> _DeleteMessage_|Nej <br/><br/> _DeleteMessage_|Om skadlig kod hittas i en e-postbilaga är meddelandet satt i karantän och kan bara släppas av en administratör.|
|**Filtret vanliga bilagor** <br/><br/> _EnableFileFilter_|På <br/><br/> `$true`|På <br/><br/> `$true`|Den här inställningen skapar karantän meddelanden som innehåller körbara bilagor baserat på filtyp, oavsett innehållet i bifogade filer.|
|**Automatisk borttagning av skadlig program vara** <br/><br/> _ZapEnabled_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Meddela interna avsändare** om det ej skickade meddelandet <br/><br/> _EnableInternalSenderNotifications_|Inaktiverad <br/><br/> `$false`|Inaktiverad <br/><br/> `$false`||
|**Meddela externa avsändare** för det ej skickade meddelandet <br/><br/> _EnableExternalSenderNotifications_|Inaktiverad <br/><br/> `$false`|Inaktiverad <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP standard princip inställningar för anti-nätfiske

Mer information om de här inställningarna finns i [Inställningar för förfalskningar](set-up-anti-phishing-policies.md#spoof-settings). Information om hur du konfigurerar dessa inställningar finns i [Konfigurera Antinätfiske-principer i EOP](configure-anti-phishing-policies-eop.md).

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|**Aktivera skydd mot förfalskning** <br/><br/> _EnableAntispoofEnforcement_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Aktivera oautentiserad avsändare** <br/><br/> _EnableUnauthenticatedSender_|På <br/><br/> `$true`|På <br/><br/> `$true`|Lägger till ett frågetecken (?) till avsändarens foto i Outlook för oidentifierade avsändare. Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md).|
|**Om e-post skickas av någon som inte har behörighet att använda din domän** <br/><br/> _AuthenticationFailAction_|**Flytta meddelandet till mottagarnas skräp post mappar** <br/><br/> `MoveToJmf`|**Sätt i karantän meddelandet** <br/><br/> `Quarantine`|Detta gäller spärrade avsändare i [Spoof-intelligens](learn-about-spoof-intelligence.md).|
|

## <a name="office-365-advanced-threat-protection-security"></a>Office 365 säkerhet för avancerat skydd

Ytterligare säkerhets förmåner kommer med en prenumeration på Office 365 Avancerat skydd (ATP). De senaste nyheterna och informationen finns i [Nyheter i Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP inkluderar principer för säkerhet för bifogade filer och säkra Länkar för att förhindra att e-post med potentiellt skadliga bilagor levereras och att användarna inte kan klicka på potentiellt osäkra URL: er.

> [!IMPORTANT]
> Avancerat skydd mot nätfiske är en av fördelarna med ett Office 365-abonnemang. Standard policyn [för ATP-nätfiske skyddar alla](set-up-anti-phishing-policies.md#spoof-settings) mottagare. De tillgängliga inställningarna för [skydd mot obehörig](#impersonation-settings-in-atp-anti-phishing-policies) användning för vissa avsändare eller sändande domäner är inte konfigurerade eller aktiverade i standard principen. För att aktivera skydd mot obehörig person måste du konfigurera minst ett ATP-Antivirus policy.

Om du har lagt till ett Office 365 ATP-abonnemang i din EOP ställer du in följande konfigurationer.

### <a name="atp-anti-phishing-policy-settings"></a>Inställningar för policy för Stöldskydd mot nätfiske

EOP-kunder får grundläggande anti-nätfiske enligt beskrivningen ovan, men Office 365 ATP innehåller fler funktioner och kontroll för att förhindra, upptäcka och åtgärda attacker. Information om hur du skapar och konfigurerar de här principerna finns i [Konfigurera principer för ATP-Antivirus i Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Inställningar för personifiering i principer för Stöldskydd med ATP

Mer information om dessa inställningar finns i [Inställningar för personifiering i principer för Stöldskydd mot ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies). Information om hur du konfigurerar dessa inställningar finns i [Konfigurera principer för ATP-Antivirus](configure-atp-anti-phishing-policies.md).

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|Skyddade användare: **lägga till användare att skydda** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|På <br/><br/> `$true` <br/><br/> \<list of users\>|På <br/><br/> `$true` <br/><br/> \<list of users\>|Beror på din organisation, men vi rekommenderar att du lägger till användare i viktiga roller. Det här kan vara VD, ekonomi och andra chefs ledare. Externt kan dessa innehålla råds medlemmar eller anslags tavla.|
|Skyddade domäner: **Inkludera domänerna som jag äger automatiskt** <br/><br/> _EnableOrganizationDomainsProtection_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|Skyddade domäner: **Inkludera anpassade domäner** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|På <br/><br/> `$true` <br/><br/> \<list of domains\>|På <br/><br/> `$true` <br/><br/> \<list of domains\>|Beror på din organisation, men vi rekommenderar att du lägger till domäner som du ofta interagerar med.|
|Skyddade användare: **om e-post skickas av en personifierad användare** <br/><br/> _TargetedUserProtectionAction_|**Sätt i karantän meddelandet** <br/><br/> `Quarantine`|**Sätt i karantän meddelandet** <br/><br/> `Quarantine`||
|Skyddade domäner: **om e-post skickas av en domänkontrollant** <br/><br/> _TargetedDomainProtectionAction_|**Sätt i karantän meddelandet** <br/><br/> `Quarantine`|**Sätt i karantän meddelandet** <br/><br/> `Quarantine`||
|**Visa tips för personifierade användare** <br/><br/> _EnableSimilarUsersSafetyTips_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Visa tips för personifierade domäner** <br/><br/> _EnableSimilarDomainsSafetyTips_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Visa tips för ovanliga tecken** <br/><br/> _EnableUnusualCharactersSafetyTips_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Aktivera post lådans intelligens?** <br/><br/> _EnableMailboxIntelligence_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Aktivera post Låde skydd baserat personifieringstoken?** <br/><br/> _EnableMailboxIntelligenceProtection_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Om e-post skickas av en personifierad användare som skyddas av Mailbox Intelligence** <br/><br/> _MailboxIntelligenceProtectionAction_|**Flytta meddelandet till mottagarnas skräp post mappar** <br/><br/> `MoveToJmf`|**Sätt i karantän meddelandet** <br/><br/> `Quarantine`||
|**Betrodda avsändare** <br/><br/> _ExcludedSenders_|Inga|Inga|Beror på din organisation, men vi rekommenderar att du lägger till användare som inte är markerade som Phish på grund av personifiering och inte andra filter.|
|**Betrodda domäner** <br/><br/> _ExcludedDomains_|Inga|Inga|Beror på din organisation, men vi rekommenderar att du lägger till domäner som inte är markerade som Phish på grund av personifiering och inte andra filter.|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Inställningar för förfalskning i principer för Stöldskydd med ATP

Observera att dessa inställningar är tillgängliga i [princip inställningar för skräp post i EOP](#eop-anti-spam-policy-settings).

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|**Aktivera skydd mot förfalskning** <br/><br/> _EnableAntispoofEnforcement_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Aktivera oautentiserad avsändare** <br/><br/> _EnableUnauthenticatedSender_|På <br/><br/> `$true`|På <br/><br/> `$true`|Lägger till ett frågetecken (?) till avsändarens foto i Outlook för oidentifierade avsändare. Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md).|
|**Om e-post skickas av någon som inte har behörighet att använda din domän** <br/><br/> _AuthenticationFailAction_|**Flytta meddelandet till mottagarnas skräp post mappar** <br/><br/> `MoveToJmf`|**Sätt i karantän meddelandet** <br/><br/> `Quarantine`|Detta gäller spärrade avsändare i [Spoof-intelligens](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Avancerade inställningar i Antivirus policys för ATP

Mer information om den här inställningen finns i [avancerade nät fiske trösklar i principer för ATP-nätfiske](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies). Information om hur du konfigurerar den här inställningen finns i [Konfigurera AntiPhishing-principer för ATP](configure-atp-anti-phishing-policies.md).

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|**Avancerade nät fiske trösklar** <br/><br/> _PhishThresholdLevel_|**2 – aggressivt** <br/><br/> `2`|**3 – mer aggressivt** <br/><br/> `3`||

### <a name="safe-links-settings"></a>Inställningar för säkra länkar

Säkra länkar i Office 365 ATP inkluderar globala inställningar som gäller för alla användare som är inkluderade i principer för aktiva säkra länkar och inställningar som är specifika för varje princip för säker länk. Mer information finns i [säkra länkar i Office 365 ATP](atp-safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Globala inställningar för säkra länkar

Om du vill konfigurera de här inställningarna läser du [Konfigurera globala inställningar för säkra länkar i Office 365 ATP](configure-global-settings-for-safe-links.md).

I PowerShell använder du cmdleten [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) för dessa inställningar.

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|**Använda säkra länkar i: Office 365-program** <br/><br/> _EnableSafeLinksForO365Clients_|På <br/><br/> `$true`|På <br/><br/> `$true`|Använda säkraste säkerhets länkar i Office 365 Desktop-och Mobile-appar (iOS och Android). Mer information finns i [Inställningar för säkra Länkar för Office 365-appar](atp-safe-links.md#safe-links-settings-for-office-365-apps).|
|**Spåra inte när användare klickar på säkra länkar** <br/><br/> _TrackClicks_|Av <br/><br/> `$true`|Av <br/><br/> `$true`|Den här inställningen rör spårning av användare i Office 365-appar som stöds.|
|**Tillåt inte att användare klickar genom säkra länkar till ursprunglig URL** <br/><br/> _AllowClickThrough_|På <br/><br/> `$false`|På <br/><br/> `$false`|Den här inställningen är relaterad till att klicka igenom i Office 365-appar som stöds.|
|Använda säkra länkar i: Office Web Access-assistenter <br/><br/> _EnableSafeLinksForWebAccessCompanion_|På <br/><br/> `$true`|På <br/><br/> `$true`|Använda säkra länkar i Office Web Apps. Observera att den här inställningen inte kan konfigureras.|
|

#### <a name="safe-links-policy-settings"></a>Princip inställningar för säkra länkar

Information om hur du konfigurerar dessa inställningar finns i [Konfigurera principer för säkra länkar i Office 365 ATP](set-up-atp-safe-links-policies.md).

I PowerShell använder du cmdleten [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) och [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) för dessa inställningar.

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|**Välj åtgärd för okända URL-adresser i meddelanden** <br/><br/> _IsEnabled_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Välj åtgärd för okända eller potentiellt skadliga URL-adresser i Microsoft Teams** <br/><br/> _EnableSafeLinksForTeams_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Använda URL-genomsökning i real tid för misstänkta länkar och länkar som pekar på filer** <br/><br/> _ScanUrls_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Vänta på att URL-genomsökningen ska slutföras innan du levererar meddelandet** <br/><br/> _DeliverMessageAfterScan_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Använda säkra länkar till e-postmeddelanden som skickas inom organisationen** <br/><br/> _EnableForInternalSenders_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Spåra inte när användare klickar på säkra länkar** <br/><br/> _DoNotTrackUserClicks_|Av <br/><br/> `$false`|Av <br/><br/> `$false`|
|**Tillåt inte att användare klickar genom säkra länkar till ursprunglig URL** <br/><br/> _DoNotAllowClickThrough_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|

### <a name="safe-attachments-settings"></a>Inställningar för säkra bifogade filer

Säkra bifogade filer i Office 365 ATP inkluderar globala inställningar som gäller för alla användare som ingår i Active Safeing Attachment-principer och inställningar som är specifika för varje princip för säker länk. Mer information finns i avsnitten [om säkra bifogade filer i Office 365 ATP](atp-safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Globala inställningar för säkra bifogade filer

Information om hur du konfigurerar de här inställningarna finns i [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) och [Safe Documents in Microsoft 365 E5](safe-docs.md).

I PowerShell använder du cmdleten [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) för dessa inställningar.

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|**Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** <br/><br/> _EnableATPForSPOTeamsODB_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Aktivera säkra dokument för Office-klienter**<bt/><br/> _EnableSafeDocs_|På <br/><br/> `$true`|På <br/><br/> `$true`||Den här inställningen är bara tillgänglig med Microsoft 365 E5-eller Microsoft 365 E5-säkerhets licenser. Mer information finns i [fel säkert dokument i Office 365 Avancerat skydd](safe-docs.md).|
|**Tillåt att personer klickar via skyddad vy även om säkra dokument har identifierat filen som skadlig**<bt/><br/> _AllowSafeDocsOpen_|Av <br/><br/> `$false`|Av <br/><br/> `$false`|Den här inställningen är relaterad till säkra dokument.|
|

#### <a name="safe-attachments-policy-settings"></a>Princip inställningar för säkra bifogade filer

Information om hur du konfigurerar dessa inställningar finns i [Konfigurera principer för säkra bifogade filer i Office 365 ATP](set-up-atp-safe-attachments-policies.md).

I PowerShell använder du cmdleten [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) och [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) för dessa inställningar.

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|**Osäkra bifogade filer, svar på skadlig program vara** <br/><br/> _Fattning_|Blockera <br/><br/> `Block`|Blockera <br/><br/> `Block`||
|**Omdirigera bilaga vid identifiering** : **Aktivera omdirigering** <br/><br/> _Omdirigeringstid_ <br/><br/> _RedirectAddress_|På och ange en e-postadress. <br/><br/> `$true` <br/><br/> en e-postadress|På och ange en e-postadress. <br/><br/> `$true` <br/><br/> en e-postadress|Omdirigera meddelanden till en säkerhets administratör för granskning.|
|**Använd ovanstående markering om genomsökning av skadlig kod för bifogade filer eller fel uppstår.** <br/><br/> _ActionOnError_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|

## <a name="related-topics"></a>Relaterade ämnen

- Letar du efter rekommendationer med regler för **Exchange-flöde/Exchange-överföring**? Mer information finns i [den här artikeln](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) .

- Administratörer och användare kan skicka falska positiva (bra e-postmeddelanden) och falska negativ (dålig e-post) till Microsoft för analys. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- Använd de här länkarna om du vill veta mer om hur du **ställer in** din [EOP-tjänst](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)och **konfigurerar** [Office 365 Avancerat skydd för hot](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Glöm inte att se de praktiska anvisningarna i "[skydda mot hot i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)".)

- **Säkerhets bas linjer för Windows** finns [här](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) för grup princip objekt och lokala inställningar och för Intune-baserad [säkerhet.](https://docs.microsoft.com/intune/protect/security-baselines) En jämförelse mellan säkerhets bas linjer för Microsoft Defender Avancerat skydd (ATP) och Windows Intune finns [här](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
