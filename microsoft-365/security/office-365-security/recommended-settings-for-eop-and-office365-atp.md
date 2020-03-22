---
title: Microsofts rekommendationer för säkerhetsinställningar för EOP och Office 365 ATP, rekommendationer, Sender Policy Framework, Domänbaserad meddelanderapportering och överensstämmelse, domännycklar identifierade e-postmeddelanden, steg, hur fungerar det, säkerhetsbaslinjer, baslinjer för EOP, baslinjer för ATP, setup ATP, setup EOP, konfigurera ATP, konfigurera EOP, säkerhetskonfiguration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 12/12/2019
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
ms.openlocfilehash: b68c10eccfdacd7782f402b5712a808ff278254d
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895233"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Rekommenderade inställningar för EOP- och Office 365 ATP-säkerhet

**Exchange Online Protection (EOP)** är kärnan i säkerheten för Office 365-prenumerationer och hjälper till att förhindra att skadliga e-postmeddelanden når dina anställdas inkorgar. Men med nya, mer sofistikerade attacker som växer fram varje dag, krävs ofta bättre skydd. **Office 365 Avancerat skydd mot hot (ATP)** ATP Plan 1 eller ATP Plan 2 innehåller ytterligare funktioner som ger administratörer fler lager av säkerhet, kontroll och undersökning.

Även om vi ger säkerhetsadministratörer möjlighet att anpassa sina säkerhetsinställningar finns det två säkerhetsnivåer i EOP och Office 365 ATP som vi rekommenderar: **Standard** och **Strikt**. Varje kunds miljö och behov är olika, men vi tror att dessa nivåer av e-postfiltrering konfigurationer kommer att bidra till att förhindra oönskad e-post från att nå dina anställdas inkorg i de flesta situationer.

> [!IMPORTANT]
> Skräppostregeln måste aktiveras på en postlåda för att filtrering ska fungera korrekt. Det är aktiverat som standard, men du bör kontrollera det om filtrrering inte verkar fungera. Mer information finns i [Konfigurera inställningar för skräppost på Exchange Online-postlådor i Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

I det här avsnittet beskrivs de här Microsoft-rekommenderade inställningarna för att skydda dina Office 365-användare.

> [!TIP]
> Det finns en ny PowerShell-modul som du kan hämta kallas Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) som hjälper till att avgöra några av dessa inställningar. När du kör som administratör i din klientorganisation kommer Get-ORCAReport att bidra till att generera en bedömning av inställningarna för anti-spam, anti-phish och andra inställningar för meddelandehygien. Du kan ladda https://www.powershellgallery.com/packages/ORCA/ner denna modul på .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Anti-spam, anti-malware och anti-phishing skydd i EOP

Anti-spam, anti-malware och anti-phishing är funktioner i EOP som kan konfigureras av administratörer. Vi rekommenderar följande konfigurationer.

### <a name="eop-anti-spam-policy-settings"></a>EOP:s policyinställningar för skräppost mot skräppost

Om du vill skapa och konfigurera principer mot skräppost finns i [Konfigurera principer mot skräppost i Office 365](configure-your-spam-filter-policies.md).

|||||
|---|---|---|---|
|**Namn på säkerhetsfunktionen**|**Standard**|**Strikt**|**Kommentar**|
|**Åtgärder** för identifiering av skräppost <br/><br/> _SpamAction (Skräppost)_|**Flytta meddelande till mappen Skräppost** <br/><br/> `MoveToJmf`|**Karantänmeddelande** <br/><br/> `Quarantine`||
|**Åtgärder för** att upptäcka skräppost med högt förtroende <br/><br/> _HögtrohetSpamAction_|**Karantänmeddelande** <br/><br/> `Quarantine`|**Karantänmeddelande** <br/><br/> `Quarantine`||
|Identifiering av **nätfiske e-post** <br/><br/> _PhishSpamAction (PhishSpamAction)_|**Karantänmeddelande** <br/><br/> `Quarantine`|**Karantänmeddelande** <br/><br/> `Quarantine`||
|**Identifiering av nätfiskemeddelanden med högt förtroende** <br/><br/> _HögtroensAPhishAction_|**Karantänmeddelande** <br/><br/> `Quarantine`|**Karantänmeddelande** <br/><br/> `Quarantine`||
|**Massident e-identifiering** åtgärd <br/><br/> _BulkSpamAction_|**Flytta meddelande till mappen Skräppost** <br/><br/> `MoveToJmf`|**Karantänmeddelande** <br/><br/> `Quarantine`||
|Tröskelvärde för massutskick av e-post <br/><br/> _BulkDetrös innehav_|6|4|Standardvärdet är för närvarande 7, men vi rekommenderar att du ändrar det till 6. Mer information finns i [BCL (Bulk complaint level) i Office 365](bulk-complaint-level-values.md).|
|Kvarhållningsperiod för karantän <br/><br/> _KarantänReentionPeriod_|30 dagar|30 dagar||
|**Säkerhetstips** <br/><br/> _InlineSafetyTipsEnbard_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|Tillåtna avsändare <br/><br/> _Tillåtnasändare_|Ingen|Ingen||
|Tillåtna avsändningsdomäner <br/><br/> _AllowedSenderDomains_|Ingen|Ingen|Det krävs inte att du lägger till domäner som du äger (kallas även _godkända domäner)_ i listan över tillåtna avsändare. I själva verket anses det hög risk eftersom det skapar möjligheter för dåliga aktörer att skicka e-post som annars skulle filtreras bort. Använd [falska underrättelser](learn-about-spoof-intelligence.md) i Security & Compliance Center på sidan Inställningar för **skräppostskydd** för att granska alla avsändare som förfalskar antingen domäner som ingår i din organisation eller förfalskar externa domäner.|
|Blockerade avsändare <br/><br/> _Blockeradesändare_|Ingen|Ingen||
|Blockerade avsändaredomäner <br/><br/> _BlockeradeSenderDomäner_|Ingen|Ingen||
|**Aktivera skräppostmeddelanden för slutanvändare** <br/><br/> _AktiveraEndUserSpamNotifications_|Aktiverat <br/><br/> `$true`|Aktiverat <br/><br/> `$true`||
|**Skicka skräppostmeddelanden för slutanvändare varje (dagar)** <br/><br/> _EndUserSpamNotificationFrequency_|3 dagar|3 dagar||
|**Spam ZAP** <br/><br/> _SpamZapEnabled_|Aktiverat <br/><br/> `$true`|Aktiverat <br/><br/> `$true`||
|**Phish ZAP** <br/><br/> _PhishZapEnabled_|Aktiverat <br/><br/> `$true`|Aktiverat <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|På|På|Den här inställningen är endast tillgänglig i PowerShell.|
|

Det finns flera andra asf-inställningar (Advanced Spam Filter) i anti-spam-policyer som håller på att vara inaktuella. Mer information om tidslinjerna för avskrivning av dessa funktioner kommer att meddelas utanför det här avsnittet.

Vi rekommenderar att du inaktiverar dessa ASF-inställningar **Off** för både **standard-** och **strikta** nivåer. Mer information om ASF-inställningar finns [i ASF-inställningar (Advanced Spam Filter) i Office 365](advanced-spam-filtering-asf-options.md).

|||
|----|---|
|**Namn på säkerhetsfunktionen**|**Kommentarer**|
|**Bildlänkar till fjärrplatser** _(IncreaseScoreWithImageLinks)_||
|**Numerisk IP-adress i URL** _(IncreaseScoreWithNumericIps_)||
|**UL omdirigera till annan port** _(IncreaseScoreWithRedirectToOtherPort)_||
|**URL till .biz eller .info webbplatser** _(IncreaseScoreWithBizOrInfoUrls)_||
|**Tomma meddelanden** (_MarkAsSpamEmptyMessages_)||
|**JavaScript eller VBScript i HTML** _(MarkAsSpamJavaScriptInHtml_)||
|**Bildruta- eller IFrame-taggar i HTML** _(MarkAsSpamFramesInHtml_)||
|**Objekttaggar i HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Bädda in taggar i HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Formulärtaggar i HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Webbbuggar i HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Använd känslig ordlista** _(MarkAsSpamSensitiveWordList)_||
|**SPF-post: hårt fel** _(MarkAsSpamSpfRecordHardFail)_||
|**Filtrering av villkorlig avsändare: hårddiskmisslykning** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP-utgående skräppostprincipinställningar

Om du vill skapa och konfigurera principer för skräppost för utgående skräppost finns [i Konfigurera skräppostfiltrering i Office 365](configure-the-outbound-spam-policy.md).

||||
|---|---|---|---|
|**Namn på säkerhetsfunktionen**|**Standard**|**Strikt**|**Kommentar**|
|**Maximalt antal mottagare per användare: Gräns för extern timme** <br/><br/> _MottagareLimitExternalPerHour_|500|400||
|**Maximalt antal mottagare per användare: Gräns för intern timme** <br/><br/> _MottagareLimitInternalPerHour_|1000|800||
|**Maximalt antal mottagare per användare: Daglig gräns** <br/><br/> _MottagareLimitPerDay_|1000|800||
|**Åtgärd när en användare överskrider gränserna** <br/><br/> _ÅtgärdNärDessholdReached_|**Hindra användaren från att skicka e-post** <br/><br/> `BlockUser`|**Hindra användaren från att skicka e-post** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP-principinställningar för skadlig kod

Om du vill skapa och konfigurera principer mot skadlig kod finns [i Konfigurera principer mot skadlig kod i Office 365](configure-anti-malware-policies.md).

|||||
|---|---|---|---|
|**Namn på säkerhetsfunktionen**|**Standard**|**Strikt**|**Kommentar**|
|**Vill du meddela mottagarna om deras meddelanden sätts i karantän?** <br/><br/> _Åtgärder_|Nej <br/><br/> _Ta bortMessage_|Nej <br/><br/> _Ta bortMessage_|Om skadlig kod upptäcks i en bifogad fil i ett e-postmeddelande sätts meddelandet i karantän och kan endast släppas av en administratör.|
|**Filter för vanliga typer av bifogade filer** <br/><br/> _EnableFileFilter_|På <br/><br/> `$true`|På <br/><br/> `$true`|Den här inställningen sätter meddelanden i karantän som innehåller körbara bilagor baserat på filtyp, oavsett innehållet i bifogade filer.|
|**Automatisk rensning av skadlig kod noll timmar** <br/><br/> _ZapEnabled (påförande)_|På <br/><br/> `$true`|På <br/><br/> `$true`||
|**Meddela interna avsändare** av det olevererade meddelandet <br/><br/> _AktiveraInternalSenderAnmälningar_|Inaktiverad <br/><br/> `$false`|Inaktiverad <br/><br/> `$false`||
|**Meddela externa avsändare** av det olevererade meddelandet <br/><br/> _AktiveraExternalSenderAnmälningar_|Inaktiverad <br/><br/> `$false`|Inaktiverad <br/><br/> `$false`||
|

### <a name="eop-anti-phishing-policy-settings"></a>EOP:s principinställningar för phishing

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Aktivera skydd mot förfalskning|På|På||
|Aktivera oautentiserade avsändare (taggning)|På|På||
|Om e-post skickas av någon som inte får förfalska din domän|Flytta meddelande till mottagarnas skräppostmappar|Karantän meddelandet||

## <a name="office-365-advanced-threat-protection-security"></a>Säkerhet för avancerat skydd mot skydd i Office 365

Ytterligare säkerhetsfördelar med en Office 365 Advanced Threat Protection(ATP)-prenumeration. De senaste nyheterna och informationen finns i Nyheter och NYHETER [i Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP innehåller principerna för säker bifogad fil och säkra länkar för att förhindra att e-post med potentiellt skadliga bilagor levereras och för att hindra användare från att klicka på potentiellt osäkra webbadresser.

> [!IMPORTANT]
> Avancerad anti-phishing är en av fördelarna med en Office 365 ATP-prenumeration. Även om den är aktiverad som standard ***måste*** du konfigurera minst en anti-phishing-princip innan den kan börja filtrera e-post. Att glömma att konfigurera principer mot nätfiske kan utsätta användare för riskfyllda e-postmeddelanden. Var noga med att konfigurera dina principer mot nätfiske när du har lagt till en Office 365 ATP-prenumeration.

Om du har lagt till en Office 365 ATP-prenumeration i EOP anger du följande konfigurationer.

### <a name="office-atp-anti-phishing-policy-settings"></a>Inställningar för office ATP-principen mot nätfiske

EOP-kunder får grundläggande nätfiske som tidigare beskrivits, men Office 365 ATP innehåller fler funktioner och kontroll för att förebygga, upptäcka och åtgärda mot attacker.

|Namn på personifieringssäkerhet|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|(Redigera personifieringsprincip) Lägga till användare som ska skyddas|På|På|Beror på din organisation, men vi rekommenderar att du lägger till användare i viktiga roller. Internt kan dessa vara din VD, CFO och andra ledande befattningshavare. Externt kan dessa omfatta rådsmedlemmar eller din styrelse.|
|(Redigera personifieringsprincip) Inkludera automatiskt de domäner jag äger|På|På||
|(Redigera personifieringsprincip) Inkludera anpassade domäner|På|På|Beror på din organisation, men vi rekommenderar att du lägger till domäner som du interagerar med de flesta som du inte äger.|
|Om e-post skickas av en personifierad användare som du har angett|Karantän meddelandet|Karantän meddelandet||
|Om e-post skickas av en personifierad domän som du har angett|Karantän meddelandet|Karantän meddelandet||
|Visa tips för användare som är utgav sig för att vara personifierade|På|På||
|Visa tips för personifierade domäner|På|På||
|Visa tips för ovanliga tecken|På|På||
|Aktivera postlådeinformation|På|På||
|Aktivera intelligensbaserat personifieringsskydd för postlåda|På|På||
|Om e-post skickas av en personifierad användare som skyddas av postlådeinformation|Flytta meddelande till mottagarnas skräppostmappar|Karantän meddelandet||
|(Redigera personifieringsprincip) Lägga till betrodda avsändare och domäner|Ingen|Ingen|Beror på din organisation, men vi rekommenderar att du lägger till användare eller domäner som felaktigt markeras som phish på grund av personifiering och inte andra filter.|

|Namn på falska säkerhetsfunktioner|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Aktivera skydd mot förfalskning|På|På||
|Aktivera oautentiserade avsändare (taggning)|På|På||
|Om e-post skickas av någon som inte får förfalska din domän|Flytta meddelande till mottagarnas skräppostmappar|Karantän meddelandet||
|EnableSuspiciousSafetyTip|Falska|Sant|Den här inställningen är endast tillgänglig i PowerShell|
|TreatSoftPassAsAuthenticated TreatSoftPassAsAuthenticated TreatSoftPassAsAuthenticated TreatSoft|Sant|Falska|Den här inställningen är endast tillgänglig i PowerShell|


|Säkerhetsfunktionsnamn för avancerade inställningar|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Avancerade tröskelvärden för nätfiske|2 - Aggressiv|3 - Mer aggressiv||

### <a name="safe-links-settings"></a>Inställningar för säkra länkar

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Använda ATP-säkra länkar i Office 365 Apps, Office för iOS och Android|Aktiverat|Aktiverat|Detta omfattas av ATP Safe Links-policyerna som gäller för hela organisationen|
Spåra inte när användare klickar på säkra länkar|Inaktiverad|Inaktiverad|Detta gäller både principer som gäller för hela organisationen och alla principer som gäller för specifika mottagare|
|Låt inte användare klicka igenom säkra länkar till den ursprungliga webbadressen|Aktiverat|Aktiverat|Detta gäller både de principer som gäller för hela organisationen och alla principer som gäller för specifika mottagare|
|Åtgärd för okända potentiellt skadliga webbadresser i meddelanden|På|På||
|Använda URL-skanning i realtid efter misstänkta länkar och länkar som pekar på filer|Aktiverat|Aktiverat||
|Vänta tills URL-skanningen har slutförts innan meddelandet levereras|Aktiverat|Aktiverat||
|Använda säkra länkar till e-postmeddelanden som skickas inom organisationen|Aktiverat|Aktiverat||

### <a name="safe-attachments"></a>Säkra bilagor

|Namn på säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Aktivera ATP för SharePoint, OneDrive och Microsoft Teams|Aktiverat|Aktiverat||
|ATP Säkra bilagor okänd malware svar|Blockera|Blockera||
|Omdirigera bifogad fil vid identifiering|Aktiverat|Aktiverat|Omdirigera till e-postadress för en säkerhetsadministratör som vet hur man tar reda på om den bifogade filen är skadlig eller inte|
|ATP Säkra bilagor svar om malware skanning efter bilagor time out eller fel inträffar|Aktiverat|Aktiverat||


## <a name="related-topics"></a>Relaterade ämnen

- Letar du efter metodtips med **Exchange Mail Flow / Exchange Transport Regler?** Se [den här artikeln](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) för mer information.

- Skicka misstänkta e-postmeddelanden, misstänkt skräppost, phish eller webbadresser till Microsoft för sökning. Använd anvisningarna **för administratörsbidrag** i [den här artikeln](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

- Använd de här länkarna för information om hur **du konfigurerar** [eOP-tjänsten](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)och **konfigurerar** [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Glöm inte att se de användbara anvisningarna i '[Skydda mot hot i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)'.)

- **Säkerhetsbaslinjer för Windows** finns [här](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) för GPO/lokala alternativ och för Intune-baserad säkerhet [här](https://docs.microsoft.com/intune/protect/security-baselines). Slutligen kan en jämförelse mellan Microsoft Defender Advanced Threat Protection (ATP) och Windows Intune säkerhetsbaslinjer hittas [här](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
