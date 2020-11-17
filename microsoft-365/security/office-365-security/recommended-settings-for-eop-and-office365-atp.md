---
title: Microsoft-rekommendationer för säkerhets inställningar för EOP och Defender för Office 365, rekommendationer, principer för avsändare, domänbaserade meddelanden och prosvars linjer, DomainKeys identifierat e-post, steg, hur fungerar det, säkerhets bas linjer, bas linjer för EOP, original planerna för Defender för Office 365, konfigurera Defender för Office 365, konfigurera EOP, konfigurera Defender för Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Vad är metod tips för säkerhets inställningar för Exchange Online Protection (EOP) och Defender för Office 365? Vad är de senaste rekommendationerna för standard skydd? Vad ska användas om du vill veta mer? Vilka extrafunktioner får du om du även använder Defender för Office 365?
ms.openlocfilehash: bc91ba58c9dc14954f638853ad24fcf7a26684e3
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123483"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Rekommenderade inställningar för EOP och Microsoft Defender för Office 365-säkerhet

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP)** är den grundläggande säkerheten för Microsoft 365-prenumerationer och skyddar obehöriga e-postmeddelanden från att nå dina anställdas inkorgar. Men med nya, mer sofistikerade attacker är det ofta nödvändigt att förbättra skyddet varje dag. **Microsoft Defender för Office 365** Abonnemang 1 eller abonnemang 2 innehåller ytterligare funktioner som ger administratörer fler lager med säkerhet, kontroll och undersökning.

Även om vi stärker säkerhets administratören för att anpassa sina säkerhets inställningar finns det två säkerhets nivåer i EOP och Microsoft Defender för Office 365 som vi rekommenderar: **standard** och **strict**. Varje kunds miljö och behov är olika, men vi tror att de här filtrerings nivåerna hindrar oönskad e-post från att nå dina anställdas inkorg i de flesta fall.

Om du automatiskt vill använda standardinställningarna eller strikta inställningar för användare kan du läsa [förvalda säkerhets principer i EOP och Microsoft Defender för Office 365](preset-security-policies.md).

> [!NOTE]
> Skräp post regeln måste aktive ras på post lådor för att filtreringen ska fungera korrekt. Det är aktiverat som standard, men du bör kontrol lera om det inte verkar fungera. Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor i Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

I den här artikeln beskrivs standardinställningarna och rekommenderade standardinställningar och strikta inställningar för att skydda användarna.

> [!TIP]
> Office 365-modulen för Configuration Analyzer (ORCA) för PowerShell kan hjälpa dig (administratörer) att hitta de aktuella värdena för dessa inställningar. Med cmdleten **Get-ORCAReport** skapar du en utvärdering av skydd mot skräp post, nätfiske och andra hygien inställningar. Du kan ladda ned ORCA-modulen på <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Skydd mot skräp post, mot skadlig program vara och mot nätfiske-säkerhet i EOP

Skydd mot skräp post, mot skadlig program vara och anti-nätfiske är EOP funktioner som kan konfigureras av administratörer. Vi rekommenderar följande standard-eller strikta konfigurationer.

### <a name="eop-anti-spam-policy-settings"></a>EOP princip inställningar för skräp post

Information om hur du skapar och konfigurerar principer för skräp post hantering finns i [Konfigurera principer för skräp post i Office 365](configure-your-spam-filter-policies.md).

****

|Säkerhetsfunktionens namn|Standard|Standard|Tillåts|Kommentar|
|---|:---:|:---:|:---:|---|
|Åtgärd för **skräp post** <p> _SpamAction_|**Flytta meddelandet till mappen skräp post** <p> `MoveToJmf`|**Flytta meddelandet till mappen skräp post** <p> `MoveToJmf`|**Karantän meddelande** <p> `Quarantine`||
|Åtgärd för dubblettidentifiering för **snabb meddelanden** <p> _HighConfidenceSpamAction_|**Flytta meddelandet till mappen skräp post** <p> `MoveToJmf`|**Karantän meddelande** <p> `Quarantine`|**Karantän meddelande** <p> `Quarantine`||
|Åtgärd för identifiering av **nätfiske-e-post** <p> _PhishSpamAction_|**Flytta meddelandet till mappen skräp post** <p> `MoveToJmf`|**Karantän meddelande** <p> `Quarantine`|**Karantän meddelande** <p> `Quarantine`||
|Åtgärd för **e-post med hög exakthet** <p> _HighConfidencePhishAction_|**Karantän meddelande** <p> `Quarantine`|**Karantän meddelande** <p> `Quarantine`|**Karantän meddelande** <p> `Quarantine`||
|**Mass utskick av e-post** <p> _BulkSpamAction_|**Flytta meddelandet till mappen skräp post** <p> `MoveToJmf`|**Flytta meddelandet till mappen skräp post** <p> `MoveToJmf`|**Karantän meddelande** <p> `Quarantine`||
|Mass utskick <p> _BulkThreshold_|borttagning|18.6|9.4|Mer information finns i [Mass inklagomåls nivå (BCL) i Office 365](bulk-complaint-level-values.md).|
|Karantän period <p> _QuarantineRetentionPeriod_|15 dagar|30 dagar|30 dagar||
|**Säkerhets tips** <p> _InlineSafetyTipsEnabled_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|Tillåtna avsändare <p> _AllowedSenders_|Inga|Inga|Inga||
|Tillåtna avsändare-domäner <p> _AllowedSenderDomains_|Inga|Inga|Inga|Det är mycket dåligt att lägga till domäner i listan Tillåtna avsändare. Angripare kan skicka e-post som annars skulle filtreras bort. <p> Använd [förfalsknings intelligens](learn-about-spoof-intelligence.md) i säkerhets & Compliance Center på sidan **Inställningar för skräp post** för att granska alla avsändare som har falska e-postadresser i organisationens e-postdomäner eller som falska e-postadresser för avsändare i externa domäner.|
|Spärrade avsändare <p> _BlockedSenders_|Inga|Inga|Inga||
|Blockerade avsändare <p> _BlockedSenderDomains_|Inga|Inga|Inga||
|**Aktivera skräp post meddelanden för slutanvändare** <p> _EnableEndUserSpamNotifications_|Inaktiverad <p> `$false`|Aktiverad <p> `$true`|Aktiverad <p> `$true`||
|**Skicka skräp post meddelanden till slutanvändaren var (dagar)** <p> _EndUserSpamNotificationFrequency_|3 dagar|3 dagar|3 dagar||
|**Spam** <p> _SpamZapEnabled_|Aktiverad <p> `$true`|Aktiverad <p> `$true`|Aktiverad <p> `$true`||
|**Phish ZAP** <p> _PhishZapEnabled_|Aktiverad <p> `$true`|Aktiverad <p> `$true`|Aktiverad <p> `$true`||
|_MarkAsSpamBulkMail_|På|På|På|Den här inställningen är bara tillgänglig i PowerShell.|
|

Det finns flera andra avancerade inställningar för skräp post filter (ASF) i principer för skräp post filtrering som håller på att vara föråldrade. Mer information om tids linjerna för avskrivning av dessa funktioner kommer att förmedlas utanför den här artikeln.

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

Mer information om standard begränsningar för sändning av tjänsten finns i avsnittet om att [Skicka begränsningar](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

****

|Säkerhetsfunktionens namn|Standard|Standard|Tillåts|Kommentar|
|---|:---:|:---:|:---:|---|
|**Maximalt antal mottagare per användare: extern Tim gräns** <p> _RecipientLimitExternalPerHour_|siffrorna|500|400|Standardvärdet 0 betyder att använda tjänstens standardvärden.|
|**Maximalt antal mottagare per användare: intern Tim gräns** <p> _RecipientLimitInternalPerHour_|siffrorna|1000|800|Standardvärdet 0 betyder att använda tjänstens standardvärden.|
|**Maximalt antal mottagare per användare: daglig gräns** <p> _RecipientLimitPerDay_|siffrorna|1000|800|Standardvärdet 0 betyder att använda tjänstens standardvärden.|
|**Åtgärd när en användare överskrider gränserna** <p> _ActionWhenThresholdReached_|**Hindra användare från att skicka e-post till följande dag** <p> `BlockUserForToday`|**Hindra användare från att skicka e-post** <p> `BlockUser`|**Hindra användare från att skicka e-post** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP policy inställningar för mot skadlig program vara

Information om hur du skapar och konfigurerar principer mot skadlig program vara finns i [Konfigurera principer mot skadlig program vara i Office 365](configure-anti-malware-policies.md).

****

|Säkerhetsfunktionens namn|Standard|Standard|Tillåts|Kommentar|
|---|:---:|:---:|:---:|---|
|**Vill du meddela mottagare om deras meddelanden är i karantän?** <p> _Fattning_|Nej <p> _DeleteMessage_|Nej <p> _DeleteMessage_|Nej <p> _DeleteMessage_|Om skadlig kod hittas i en e-postbilaga är meddelandet satt i karantän och kan bara släppas av en administratör.|
|**Filtret vanliga bilagor** <p> _EnableFileFilter_|Av <p> `$false`|På <p> `$true`|På <p> `$true`|Den här inställningen skapar karantän meddelanden som innehåller körbara bilagor baserat på filtyp, oavsett innehållet i bifogade filer.|
|**Automatisk borttagning av skadlig program vara** <p> _ZapEnabled_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Meddela interna avsändare** om det ej skickade meddelandet <p> _EnableInternalSenderNotifications_|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`||
|**Meddela externa avsändare** för det ej skickade meddelandet <p> _EnableExternalSenderNotifications_|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`|Inaktiverad <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP standard princip inställningar för anti-nätfiske

Mer information om de här inställningarna finns i [Inställningar för förfalskningar](set-up-anti-phishing-policies.md#spoof-settings). Information om hur du konfigurerar dessa inställningar finns i [Konfigurera Antinätfiske-principer i EOP](configure-anti-phishing-policies-eop.md).

****

|Säkerhetsfunktionens namn|Standard|Standard|Tillåts|Kommentar|
|---|:---:|:---:|:---:|---|
|**Aktivera skydd mot förfalskning** <p> _EnableAntispoofEnforcement_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Aktivera oautentiserad avsändare** <p> _EnableUnauthenticatedSender_|På <p> `$true`|På <p> `$true`|På <p> `$true`|Lägger till ett frågetecken (?) till avsändarens foto i Outlook för oidentifierade avsändare. Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md).|
|**Om e-post skickas av någon som inte har behörighet att använda din domän** <p> _AuthenticationFailAction_|**Flytta meddelandet till mottagarnas skräp post mappar** <p> `MoveToJmf`|**Flytta meddelandet till mottagarnas skräp post mappar** <p> `MoveToJmf`|**Sätt i karantän meddelandet** <p> `Quarantine`|Den här inställningen gäller för spärrade avsändare i [Spoof-intelligens](learn-about-spoof-intelligence.md).|
|

## <a name="microsoft-defender-for-office-365-security"></a>Säkerhet för Microsoft Defender för Office 365

Ytterligare säkerhets fördelarna ingår i en Microsoft Defender för Office 365-prenumeration. För senaste nyheterna och information kan du se vad som [är nytt i Defender för Office 365](whats-new-in-office-365-atp.md).

> [!IMPORTANT]
>
> - Standard policyn för anti-phishing i Microsoft Defender för Office 365 tillhandahåller [förfalsknings skydd](set-up-anti-phishing-policies.md#spoof-settings) och post lådans intelligens för alla mottagare. Men de andra tillgängliga funktionerna för [skydd mot personifiering](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) och [Avancerade inställningar](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) är inte konfigurerade eller aktiverade i standard principen. Om du vill aktivera alla skydds funktioner ändrar du standard policyn för anti-phishing eller skapar ytterligare skydd mot nätfiske.
>
> - Det finns inga standard principer för säkra anslutningar eller principer för säkra bifogade filer som automatiskt skyddar alla mottagare i organisationen. För att skydda måste du skapa minst en princip för säker länk och principer för säkra bifogade filer.
>
> - [ATP för SharePoint-, OneDrive-och Microsoft Teams Protection-](atp-for-spo-odb-and-teams.md) och [Safe-dokument](safe-docs.md) -skydd har inga beroenden på principer för säkra länkar.

Om ditt abonnemang innehåller Microsoft Defender för Office 365 eller om du har köpt Defender för Office 365 som ett tillägg, anger du följande standard-eller strikta konfigurationer.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Inställningar för skydd mot nätfiske i Microsoft Defender för Office 365

EOP-kunder får grundläggande anti-nätfiske enligt beskrivningen ovan, men Microsoft Defender för Office 365 inkluderar fler funktioner och kontroll för att förhindra, upptäcka och åtgärda attacker. Information om hur du skapar och konfigurerar de här principerna finns i [Konfigurera Antinätfiske-principer i Defender för Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Inställningar för personifiering i principer för nätfiske i Microsoft Defender för Office 365

Mer information om de här inställningarna finns i inställningar för [personifiering i principer för nätfiske i Microsoft Defender för Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Information om hur du konfigurerar dessa inställningar finns i [Konfigurera policy mot nätfiske i Defender för Office 365](configure-atp-anti-phishing-policies.md).

****

|Säkerhetsfunktionens namn|Standard|Standard|Tillåts|Kommentar|
|---|:---:|:---:|:---:|---|
|Skyddade användare: **lägga till användare att skydda** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Av <p> `$false` <p> none (ingen)|På <p> `$true` <p> \<list of users\>|På <p> `$true` <p> \<list of users\>|Beroende på din organisation rekommenderar vi att du lägger till användare (avsändare) i viktiga roller. Skyddade avsändare kan vara VD, ekonomi och andra chefs ledare. Skyddade avsändare kan till exempel omfatta medlemmar eller anslags tavla.|
|Skyddade domäner: **Inkludera domänerna som jag äger automatiskt** <p> _EnableOrganizationDomainsProtection_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|Skyddade domäner: **Inkludera anpassade domäner** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Av <p> `$false` <p> none (ingen)|På <p> `$true` <p> \<list of domains\>|På <p> `$true` <p> \<list of domains\>|Beroende på din organisation rekommenderar vi att du lägger till domäner (avsändare) som du inte äger, men du interagerar ofta.|
|Skyddade användare: **om e-post skickas av en personifierad användare** <p> _TargetedUserProtectionAction_|**Tillämpa inte någon åtgärd** <p> `NoAction`|**Sätt i karantän meddelandet** <p> `Quarantine`|**Sätt i karantän meddelandet** <p> `Quarantine`||
|Skyddade domäner: **om e-post skickas av en domänkontrollant** <p> _TargetedDomainProtectionAction_|**Tillämpa inte någon åtgärd** <p> `NoAction`|**Sätt i karantän meddelandet** <p> `Quarantine`|**Sätt i karantän meddelandet** <p> `Quarantine`||
|**Visa tips för personifierade användare** <p> _EnableSimilarUsersSafetyTips_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Visa tips för personifierade domäner** <p> _EnableSimilarDomainsSafetyTips_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Visa tips för ovanliga tecken** <p> _EnableUnusualCharactersSafetyTips_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Aktivera post lådans intelligens?** <p> _EnableMailboxIntelligence_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|**Aktivera post Låde skydd baserat personifieringstoken?** <p> _EnableMailboxIntelligenceProtection_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Om e-post skickas av en personifierad användare som skyddas av Mailbox Intelligence** <p> _MailboxIntelligenceProtectionAction_|**Tillämpa inte någon åtgärd** <p> `NoAction`|**Flytta meddelandet till mottagarnas skräp post mappar** <p> `MoveToJmf`|**Sätt i karantän meddelandet** <p> `Quarantine`||
|**Betrodda avsändare** <p> _ExcludedSenders_|Inga|Inga|Inga|Beroende på din organisation rekommenderar vi att du lägger till användare som inte är markerade som nätfiske på grund av personifiering och inte andra filter.|
|**Betrodda domäner** <p> _ExcludedDomains_|Inga|Inga|Inga|Beroende på din organisation rekommenderar vi att du lägger till domäner som felaktigt markeras som nätfiske på grund av personifiering och inte andra filter.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Inställningar för förfalskning i principer för nätfiske i Microsoft Defender för Office 365

Observera att dessa inställningar är tillgängliga i [princip inställningar för skräp post i EOP](#eop-anti-spam-policy-settings).

****

|Säkerhetsfunktionens namn|Standard|Tillåts|Kommentar|
|---|---|---|---|
|**Aktivera skydd mot förfalskning** <p> _EnableAntispoofEnforcement_|På <p> `$true`|På <p> `$true`||
|**Aktivera oautentiserad avsändare** <p> _EnableUnauthenticatedSender_|På <p> `$true`|På <p> `$true`|Lägger till ett frågetecken (?) till avsändarens foto i Outlook för oidentifierade avsändare. Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md).|
|**Om e-post skickas av någon som inte har behörighet att använda din domän** <p> _AuthenticationFailAction_|**Flytta meddelandet till mottagarnas skräp post mappar** <p> `MoveToJmf`|**Sätt i karantän meddelandet** <p> `Quarantine`|Den här inställningen gäller för spärrade avsändare i [Spoof-intelligens](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Avancerade inställningar i policy mot nätfiske i Microsoft Defender för Office 365

Mer information om den här inställningen finns i [avancerade nät fiske trösklar i principer för nätfiske i Microsoft Defender för Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Om du vill konfigurera den här inställningen läser du [Konfigurera policyer för nätfiske i Defender för Office 365](configure-atp-anti-phishing-policies.md).

****

|Säkerhetsfunktionens namn|Standard|Standard|Tillåts|Kommentar|
|---|:---:|:---:|:---:|---|
|**Avancerade nät fiske trösklar** <p> _PhishThresholdLevel_|**1-standard** <p> `1`|**2 – aggressivt** <p> `2`|**3 – mer aggressivt** <p> `3`||
|

### <a name="safe-links-settings"></a>Inställningar för säkra länkar

Säkra länkar i Defender för Office 365 inkluderar globala inställningar som gäller för alla användare som ingår i principer för aktiva säkra länkar och inställningar som är specifika för varje princip för säkert länkar. Mer information finns i [fel säkert länkar i Defender för Office 365](atp-safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Globala inställningar för säkra länkar

Information om hur du konfigurerar dessa inställningar finns i [Konfigurera globala inställningar för säkra länkar i Defender för Office 365](configure-global-settings-for-safe-links.md).

I PowerShell använder du cmdleten [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) för dessa inställningar.

****

|Säkerhetsfunktionens namn|Standard|Standard|Tillåts|Kommentar|
|---|:---:|:---:|:---:|---|
|**Använda säkra länkar i: Office 365-program** <p> _EnableSafeLinksForO365Clients_|På <p> `$true`|På <p> `$true`|På <p> `$true`|Använda säkra länkar i Office 365 Desktop-och Mobile-appar (iOS och Android). Mer information finns i [Inställningar för säkra Länkar för Office 365-appar](atp-safe-links.md#safe-links-settings-for-office-365-apps).|
|**Spåra inte när användare klickar på säkra länkar** <p> _TrackClicks_|På <p> `$false`|Av <p> `$true`|Av <p> `$true`|Om du inaktiverar den här inställningen (ange _TrackClicks_ till `$true` ) spåras användares klickningar i Office 365-appar som stöds.|
|**Tillåt inte att användare klickar genom säkra länkar till ursprunglig URL** <p> _AllowClickThrough_|På <p> `$false`|På <p> `$false`|På <p> `$false`|Om du aktiverar den här inställningen (inställningen _AllowClickThrough_ to `$false` ) förhindras att klicka dig fram till den ursprungliga URL-adressen i Office 365-appar som stöds.|
|

#### <a name="safe-links-policy-settings"></a>Princip inställningar för säkra länkar

Information om hur du konfigurerar dessa inställningar finns i [Konfigurera principer för säkra länkar i Microsoft Defender för Office 365](set-up-atp-safe-links-policies.md).

I PowerShell använder du cmdleten [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) och [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) för dessa inställningar.

> [!NOTE]
> Enligt beskrivningen ovan finns ingen standard princip för säkra länkar. Värdena i standard kolumnen är standardvärden i principer för nya säkra länkar som du skapar.

****

|Säkerhetsfunktionens namn|Standard|Standard|Tillåts|Kommentar|
|---|:---:|:---:|:---:|---|
|**Välj åtgärd för okända URL-adresser i meddelanden** <p> _IsEnabled_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Välj åtgärd för okända eller potentiellt skadliga URL-adresser i Microsoft Teams** <p> _EnableSafeLinksForTeams_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Använda URL-genomsökning i real tid för misstänkta länkar och länkar som pekar på filer** <p> _ScanUrls_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Vänta på att URL-genomsökningen ska slutföras innan du levererar meddelandet** <p> _DeliverMessageAfterScan_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Använda säkra länkar till e-postmeddelanden som skickas inom organisationen** <p> _EnableForInternalSenders_|Av <p> `$false`|På <p> `$true`|På <p> `$true`||
|**Spåra inte användar klickningar** <p> _DoNotTrackUserClicks_|Av <p> `$false`|Av <p> `$false`|Av <p> `$false`|Om du inaktiverar den här inställningen (ange _DoNotTrackUserClicks_ till `$false` ) spåras användare.|
|**Tillåt inte att användare klickar genom till ursprunglig URL** <p> _DoNotAllowClickThrough_|Av <p> `$false`|På <p> `$true`|På <p> `$true`|Om du aktiverar den här inställningen (inställningen _DoNotAllowClickThrough_ to `$true` ) förhindras genom att klicka dig fram till original-URL: en.|
|

### <a name="safe-attachments-settings"></a>Inställningar för säkra bifogade filer

Säkra bifogade filer i Microsoft Defender för Office 365 inkluderar globala inställningar som inte har någon relation till principer för säkert bifogade filer och inställningar som är specifika för varje princip för säker länk. Mer information finns i avsnitten [om säkra bifogade filer i Defender för Office 365](atp-safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Globala inställningar för säkra bifogade filer

Information om hur du konfigurerar de här inställningarna finns i [Aktivera ATP för SharePoint, OneDrive och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) och [Safe Documents in Microsoft 365 E5](safe-docs.md).

I PowerShell använder du cmdleten [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) för dessa inställningar.

****

|Säkerhetsfunktionens namn|Standard|Standard|Tillåts|Kommentar|
|---|:---:|:---:|:---:|---|
|**Aktivera ATP för SharePoint, OneDrive och Microsoft Teams** <p> _EnableATPForSPOTeamsODB_|På <p> `$true`|På <p> `$true`||
|**Aktivera säkra dokument för Office-klienter**<bt/><br/> _EnableSafeDocs_|På <p> `$true`|På <p> `$true`|Den här inställningen är bara tillgänglig med Microsoft 365 E5-eller Microsoft 365 E5-säkerhets licenser. Mer information finns i [säkra dokument i Microsoft Defender för Office 365](safe-docs.md).|
|**Tillåt att personer klickar via skyddad vy även om säkra dokument har identifierat filen som skadlig**<bt/><br/> _AllowSafeDocsOpen_|Av <p> `$false`|Av <p> `$false`|Den här inställningen är relaterad till säkra dokument.|
|

#### <a name="safe-attachments-policy-settings"></a>Princip inställningar för säkra bifogade filer

Information om hur du konfigurerar dessa inställningar finns i [Konfigurera principer för säkra bifogade filer i Defender för Office 365](set-up-atp-safe-attachments-policies.md).

I PowerShell använder du cmdleten [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) och [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) för dessa inställningar.

> [!NOTE]
> Enligt beskrivningen ovan finns ingen standard princip för säkra bifogade filer. Värdena i standard kolumnen är standardvärden i nya principer för säkra bifogade filer som du skapar.

****

|Säkerhetsfunktionens namn|Standard|Standard|Tillåts|Kommentar|
|---|:---:|:---:|:---:|---|
|**Osäkra bifogade filer, svar på skadlig program vara** <p> _Fattning_|Blockera <p> `Block`|Blockera <p> `Block`|Blockera <p> `Block`||
|**Omdirigera bilaga vid identifiering** : **Aktivera omdirigering** <p> _Omdirigeringstid_ <p> _RedirectAddress_|Av och ingen e-postadress angavs. <p> `$true` <p> none (ingen)|På och ange en e-postadress. <p> `$true` <p> en e-postadress|På och ange en e-postadress. <p> `$true` <p> en e-postadress|Omdirigera meddelanden till en säkerhets administratör för granskning.|
|**Använd ovanstående markering om genomsökning av skadlig kod för bifogade filer eller fel uppstår.** <p> _ActionOnError_|På <p> `$true`|På <p> `$true`|På <p> `$true`||
|

## <a name="related-articles"></a>Relaterade artiklar

- Letar du efter rekommendationer för regler för **Exchange-flöden (kallas även transport regler**)? Se [metod tips för hur du konfigurerar regler för e-postflöden i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Administratörer och användare kan skicka falska positiva (bra e-postmeddelanden) och falska negativ (dålig e-post) till Microsoft för analys. Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).

- Använd de här länkarna om du vill veta mer om hur du **ställer in** din [EOP-tjänst](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)och **konfigurerar** [Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). Glöm inte de användbara anvisningarna för att[skydda mot hot i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

- **Säkerhets bas linjer för Windows** hittar du här: [var kan jag hämta säkerhets bas linjerna?](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) för GPO/lokala alternativ och [använda säkerhets bas linjer för att konfigurera Windows 10-enheter i Intune](https://docs.microsoft.com/intune/protect/security-baselines) för Intune-baserad säkerhet. En jämförelse mellan Microsoft Defender för slut punkter och säkerhets bas linjer för Microsoft Intune är att vara tillgänglig i [Jämför Microsoft Defender för slut punkten och säkerhets bas linjerna i Windows Intune](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
