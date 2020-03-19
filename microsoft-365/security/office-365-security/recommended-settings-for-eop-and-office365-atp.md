---
title: Microsofts rekommendationer för eop- och Office 365 ATP-säkerhetsinställningar, rekommendationer, ramverk för avsändares policyram, domänbaserad meddelanderapportering och konformelse, DomainKeys Identified Mail, steg, hur fungerar det, säkerhetsbaslinjer, baslinjer för EOP, baslinjer för ATP, setup ATP, setup EOP, konfigurera ATP, konfigurera EOP, säkerhetskonfiguration
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
description: Vilka är metodtips för EOP (Exchange Online Protection) och ATP-säkerhetsinställningar (Advanced Threat Protection) och Advanced Threat Protection (ATP) ? Vilka är de nuvarande rekommendationerna för standardskydd? Vad ska användas om du vill vara striktare? Och vilka extrafunktioner får du om du också använder Advanced Threat Protection (ATP)?
ms.openlocfilehash: b7c98fe4b362a5be72be9e103a2602cd4954e028
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42812267"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Rekommenderade inställningar för EOP- och Office 365 ATP-säkerhet

**Exchange Online Protection (EOP)** är kärnan i säkerheten för Office 365-prenumerationer och hjälper till att hindra skadliga e-postmeddelanden från att nå inkorgarna för den anställde. Men med nya, mer sofistikerade attacker som växer fram varje dag krävs ofta bättre skydd. **Office 365 Avancerat hotskydd (ATP)** ATP Plan 1 eller ATP Plan 2 innehåller ytterligare funktioner som ger administratörer fler lager av säkerhet, kontroll och undersökning.

Även om vi ger säkerhetsadministratörer möjlighet att anpassa sina säkerhetsinställningar finns det två säkerhetsnivåer i EOP och Office 365 ATP som vi rekommenderar: **Standard** och **Strikt**. Varje kunds miljö och behov är olika, men vi tror att dessa nivåer av konfigurationer för postfiltrering hjälper till att förhindra oönskad e-post från att nå dina anställdas inkorg i de flesta situationer.

> [!IMPORTANT]
> Skräpe-konfigurationen måste aktiveras i postlådan för att filtreringen ska fungera korrekt. Detta är aktiverat som standard, men bör kontrolleras om filtrering inte verkar fungera. Läs [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) för att ta reda på mer. 

I det här avsnittet beskrivs följande Microsoft-rekommenderade inställningar för att skydda dina Office 365-användare.

> [!TIP]
> Det finns en ny PowerShell-modul som du kan hämta kallas Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) som hjälper till att avgöra några av dessa inställningar. När get-ORCAReport körs som administratör i din klient dator hjälper det att generera en bedömning av inställningarna för anti-spam, anti-phish och andra inställningar för meddelandehygien. Du kan ladda https://www.powershellgallery.com/packages/ORCA/ner den här modulen på .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Anti-spam, anti-malware och anti-phishing skydd i EOP

Anti-spam, anti-malware och anti-phishing är funktioner i EOP som kan konfigureras av administratörer. Vi rekommenderar följande konfigurationer.

### <a name="eop-anti-spam-policy-settings"></a>EOP-policyinställningar för skräppost

|Namn på säkerhetsfunktioner|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Åtgärder för identifiering av skräppost|Flytta meddelande till mappen Skräppost|Meddelande om karantän||
|Åtgärder för identifiering av skräppost med högt förtroende|Meddelande om karantän|Meddelande om karantän||
|Åtgärd för identifiering av nätfiske|Meddelande om karantän|Meddelande om karantän||
|Åtgärd för phish-e-sökning i e-post|Meddelande om karantän|Meddelande om karantän||
|Åtgärder för identifiering av masse-e-post|Flytta meddelande till mappen Skräppost|Meddelande om karantän||
|Ange tröskelvärde för massutskick till|6|4|Standardvärdet är för närvarande 7, men vi rekommenderar att du ändrar det till 6. Mer information finns i [Värden på massklagomålsnivå](bulk-complaint-level-values.md).|
|Karantänlagringsperiod|30 dagar|30 dagar||
|Säkerhetstips|På|På||
|Tillåtna avsändare|Ingen|Ingen||
|Tillåtna avsändare-domäner|Ingen|Ingen|Det krävs inte att lägga till domäner som du äger (kallas även _godkända domäner)_ i listan över tillåtna avsändare. I själva verket anses det vara hög risk eftersom det skapar möjligheter för dåliga aktörer att skicka e-post som annars skulle filtreras bort. Använd [falska uppgifter](learn-about-spoof-intelligence.md) i Security & Compliance Center på sidan Inställningar för **skräppost** för att granska alla avsändare som förfalskar antingen domäner som ingår i organisationen eller förfalskaexterna externa domäner.|
|Blockerade avsändare|Ingen|Ingen||
|Blockerade avsändare-domäner|Ingen|Ingen||
|Frekvens för skräppostanmälan för slutanvändare|Aktiverat|Aktiverat|3 dagar|
|Automatisk rensning av noll timmar|På|På|För både Spam och Phish ZAP|
|MarkAsSpamBulkMail|På|På|Den här inställningen är endast tillgänglig i PowerShell|

Det finns flera andra parametrar i anti-spam-principen Advanced Spam filter (ASF) som håller på att inaktiveras. Mer information om tidslinjerna för avskrivningen av dessa funktioner kommer att meddelas utanför det här avsnittet.

Vi rekommenderar att du inaktiverar dessa **inställningar** för både standard- och strikta nivåer:

|Namn på säkerhetsfunktioner|Kommentarer|
|---------|---------|
|IncreaseScoreWithImageLinks||
|Öka ScoreMedNumericIps||
|IncreaseScoreWithRedirectToOtherPort||
|IncreaseScoreWithBizOrInfoUrls||
|MarkAsSpamTommaMeddelanden||
|MarkAsspamjavaScriptinhtml||
|MarkAsSpamFramesInHtml||
|MarkAsSpamobjecttagsinhtml||
|MarkAsspamembedtagsinhtml||
|Markasspamformtagsinhtml||
|MarkAsspamwebbugsinhtml||
|MarkAsSpamSensitiveWordList||
|MarkAsSpamFromAddressAuthFail||
|MarkAsSpamNdrBackscatter||
|MarkAsSpamSpfRecordHardFail||

#### <a name="eop-outbound-spam-filter-policy-settings"></a>Principinställningar för eop-utgående skräppostfilter

|Namn på säkerhetsfunktioner|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Begränsningar för utgående skräppostprincip mottagare - Extern timgräns|500|400||
|Begränsningar för skräppostprincipen Mottagare – Intern timgräns|1000|800||
|Resänd skräppostprincip Mottagargränser - Daglig gräns|1000|800||
|Åtgärd när en användare överskrider gränserna|Begränsa användaren från att skicka e-post|Begränsa användaren från att skicka e-post||

### <a name="eop-anti-malware-policy-settings"></a>Principinställningar för EOP mot skadlig kod

|Namn på säkerhetsfunktioner|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Identifiering av skadlig kod|Nej|Nej|Om skadlig kod upptäcks i en e-postbilaga sätts meddelandet i karantän och kan endast släppas av en administratör.|
|"Gemensamt filter för bifogade filer" för att blockera misstänkta filtyper|På|På||
|Automatisk rensning av skadlig kod|På|På||
|Meddela interna avsändare av meddelandet som inte levererats|Inaktiverad|Inaktiverad||
|Meddela externa avsändare av meddelandet som inte levererats|Inaktiverad|Inaktiverad||

### <a name="eop-anti-phishing-policy-settings"></a>Principinställningar för EOP mot nätfiske

|Namn på säkerhetsfunktioner|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Aktivera skydd mot förfalskning|På|På||
|Aktivera oautentiserad avsändare (taggning)|På|På||
|Om e-post skickas av någon som inte får förfalska din domän|Flytta meddelande till mottagarnas skräppostmappar|Karantän meddelandet||

## <a name="office-365-advanced-threat-protection-security"></a>Säkerhet för avancerat hotskydd för Office 365

Ytterligare säkerhetsförmåner levereras med en ATP-prenumeration (Advanced Threat Protection) för Office 365. De senaste nyheterna och informationen finns [i Nyheter i Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP innehåller policyerna För säker bifogad fil och säkra länkar för att förhindra att e-post med potentiellt skadliga bilagor levereras och för att hindra användare från att klicka på potentiellt osäkra webbadresser.

> [!IMPORTANT]
> Avancerad anti-phishing är en av fördelarna med en Office 365 ATP-prenumeration. Även om den är aktiverad som standard ***måste*** du konfigurera minst en anti-phishing-princip innan den kan börja filtrera e-post. Om du glömmer att konfigurera policyer mot nätfiske kan användare utsättas för riskfyllda e-postmeddelanden. Var noga med att konfigurera dina anti-phishing-principer när du har lagt till en Office 365 ATP-prenumeration.

Om du har lagt till en Office 365 ATP-prenumeration i eop anger du följande konfigurationer.

### <a name="office-atp-anti-phishing-policy-settings"></a>Inställningar för office ATP-antinätfiske

EOP-kunder får grundläggande anti-phishing som tidigare beskrivits, men Office 365 ATP innehåller fler funktioner och kontroll för att förhindra, upptäcka och åtgärda mot attacker.

|Personifieringssäkerhetsfunktionsnamn|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|(Redigera personifieringsprincip) Lägga till användare att skydda|På|På|Beror på din organisation, men vi rekommenderar att du lägger till användare i viktiga roller. Internt kan dessa vara din VD, CFO och andra ledande befattningshavare. Externt kan dessa omfatta rådsmedlemmar eller din styrelse.|
|(Redigera personifieringsprincip) Inkludera automatiskt de domäner jag äger|På|På||
|(Redigera personifieringsprincip) Inkludera anpassade domäner|På|På|Beror på din organisation, men vi rekommenderar att du lägger till domäner som du interagerar med de flesta som du inte äger.|
|Om e-post skickas av en personifierad användare som du har angett|Karantän meddelandet|Karantän meddelandet||
|Om e-post skickas av en personifierad domän som du har angett|Karantän meddelandet|Karantän meddelandet||
|Visa tips för användare som utger sig för att vara|På|På||
|Visa tips för personifierade domäner|På|På||
|Visa tips för ovanliga tecken|På|På||
|Aktivera information om postlådan|På|På||
|Aktivera informationsbaserad personifieringsskydd för postlådan|På|På||
|Om e-post skickas av en personifierat användare som skyddas av postlådeinformation|Flytta meddelande till mottagarnas skräppostmappar|Karantän meddelandet||
|(Redigera personifieringsprincip) Lägga till betrodda avsändare och domäner|Ingen|Ingen|Beror på din organisation, men vi rekommenderar att du lägger till användare eller domäner som felaktigt markeras som phish på grund av personifiering bara och inte andra filter.|

|Namn på spoof-säkerhetsfunktionen|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Aktivera skydd mot förfalskning|På|På||
|Aktivera oautentiserad avsändare (taggning)|På|På||
|Om e-post skickas av någon som inte får förfalska din domän|Flytta meddelande till mottagarnas skräppostmappar|Karantän meddelandet||
|Aktivera misstänktsäkerhetstips|Falska|Sant|Den här inställningen är endast tillgänglig i PowerShell|
|TreatSoftPassAsAuthenticated|Sant|Falska|Den här inställningen är endast tillgänglig i PowerShell|


|Säkerhetsfunktionsnamn för avancerade inställningar|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Avancerade nätfisketströsklar|2 - Aggressiv|3 - Mer aggressiv||

### <a name="safe-links-settings"></a>Inställningar för säkra länkar

|Namn på säkerhetsfunktioner|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Använda ATP-säkra länkar i Office 365-appar, Office för iOS och Android|Aktiverat|Aktiverat|Detta omfattas av ATP Safe Links-policyerna som gäller för hela organisationen|
Spåra inte när användare klickar på säkra länkar|Inaktiverad|Inaktiverad|Detta är för både principer som gäller för hela organisationen och alla principer som gäller för specifika mottagare|
|Låt inte användare klicka igenom säkra länkar till original-URL|Aktiverat|Aktiverat|Detta är för både de principer som gäller för hela organisationen och alla principer som gäller för specifika mottagare|
|Åtgärd för okända potentiellt skadliga webbadresser i meddelanden|På|På||
|Använda url-sökning i realtid för misstänkta länkar och länkar som pekar på filer|Aktiverat|Aktiverat||
|Vänta tills URL-skanningen har slutförts innan meddelandet levereras|Aktiverat|Aktiverat||
|Använda säkra länkar i e-postmeddelanden som skickas inom organisationen|Aktiverat|Aktiverat||

### <a name="safe-attachments"></a>Säkra tillbehör

|Namn på säkerhetsfunktioner|Standard|Strikt|Kommentar|
|---------|---------|---------|---------|
|Aktivera ATP för SharePoint, OneDrive och Microsoft Teams|Aktiverat|Aktiverat||
|ATP Safe bilagor okänd malware svar|Blockera|Blockera||
|Omdirigera bifogad fil vid identifiering|Aktiverat|Aktiverat|Omdirigera till e-postadress för en säkerhetsadministratör som vet hur du avgör om den bifogade filen är skadlig kod eller inte|
|ATP Safe attachments svar om malware skanning för bilagor timeout eller fel inträffar|Aktiverat|Aktiverat||


## <a name="related-topics"></a>Relaterade ämnen

- Letar du efter bästa praxis med **Exchange Mail Flow / Exchange Transport Regler?** Mer information finns [i den här artikeln.](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop)

- Skicka misstänkta e-postmeddelanden, misstänkt skräppost, phish eller webbadresser till Microsoft för skanning. Använd **anvisningarna** för administratörer i den [här artikeln](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

- Använd de här länkarna för information om hur du **konfigurerar** [eop-tjänsten](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)och **konfigurerar** [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Glöm inte att se de användbara anvisningarna i "[Skydda mot hot i Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)".)

- **Säkerhetsbaslinjer för Windows** finns [här](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) för GPO/lokala alternativ och för Intune-baserad säkerhet, [här](https://docs.microsoft.com/intune/protect/security-baselines). Slutligen, en jämförelse mellan Microsoft Defender Advanced Threat Protection (ATP) och Windows Intune säkerhetsbaslinjer finns [här](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
