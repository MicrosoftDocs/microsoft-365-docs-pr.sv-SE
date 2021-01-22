---
title: Enhetsövervakning & rapportering – Säkerhetscenter
description: Här beskrivs hur du kan hålla dina enheter säkra, uppdaterade och upptäcka potentiella hot i organisationen
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, enheter
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930504"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Enhetsövervakning och -rapportering i Microsoft 365 säkerhetscenter

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Håll dina enheter säkra, uppdaterade och hitta potentiella hot i Säkerhetscenter för Microsoft 365.

## <a name="view-device-alerts"></a>Visa enhetsaviseringar

Få uppdaterade aviseringar om intrångsaktivitet och andra hot på dina enheter från Microsoft Defender för Endpoint (tillgänglig med en E5-licens). Microsoft 365 Säkerhetscenter övervakar effektivt dessa varningar på en hög nivå med hjälp av önskat arbetsflöde.

### <a name="monitor-high-impact-alerts"></a>Övervaka varningar med hög effekt

Varje Microsoft Defender för slutpunktsavisering har en motsvarande allvarlighetsgrad (hög, medel, låg eller information). Den visar möjlig påverkan på nätverket om du blir utan uppvaknad.  

Använd **allvarlighetskortet för** enhetsaviseringar för att specifikt fokusera på varningar som är mer allvarliga och kan kräva omedelbar respons. Från det här kortet kan du se mer information på Microsoft Defender Säkerhetscenter-portalen.

![Allvarlighetskort för enhetsaviseringar](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Förstå källor till aviseringar

Microsoft Defender för Endpoint använder data från ett brett utbud av säkerhetsmätare och informationskällor för att generera varningar. Den kan till exempel använda identifieringsinformation från Microsoft Defender Antivirus och tredjepartsprogram mot skadlig programvara. Den kan också använda din egen anpassade hotinformation som tillhandahålls via webbtjänst-API:t.

Kortet **för identifiering av enhetsaviseringar** visar fördelningen av aviseringar efter källa. Spåra aktivitet relaterad till vissa källor, särskilt anpassade källor. Du kan också använda kortet för att fokusera på varningar som kommer från sensorer som inte är konfigurerade för att automatiskt blockera skadlig aktivitet eller komponenter.

![Kortet För identifiering av enhetsaviseringar](../../media/device-alert-detection-sources.png)

Från det här kortet kan du se mer information på Microsoft Defender Säkerhetscenter-portalen.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Förstå vilka typer av hot som utlöser aviseringar

Microsoft Defender för Slutpunkt sorterar varje avisering i en kategori som representerar ett visst steg i attackkedja eller typ av hotkomponent. En identifierade hotaktivitet kan till exempel kategoriseras som "rörelse av rörelse" för att ange att det fanns ett försök att nå andra enheter på nätverket. Aktiviteten har troligen inträffat efter att attacker har fått ett första fot fäste. När en hotkomponent upptäcks kan den klassificeras allmänt som skadlig programvara eller särskilt som en specifik hottyp. Detta gäller utpressningstrojaner, autentiseringsuppgifter som stjäls eller andra typer av skadlig eller oönskad programvara.

Kortet **med kategorier för enhetshot** visar fördelningen av aviseringar i dessa kategorier. Använd den här informationen för att identifiera hotaktivitet, till exempel försök till autentiseringsstöld, som vanligtvis har högre effekt än social engineering-försök. Du kan också övervaka potentiella hot som utpressningstrojaner.

![Kort med kategorier för enhetshot](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Övervaka aktiva aviseringar

Statuskortet **för enhetsaviseringar** anger antalet aviseringar som inte har lösts och kan behöva åtgärdas. Från det här kortet kan du se mer information på Microsoft Defender Säkerhetscenter-portalen.

![Statuskort för enhetsavisering](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Övervaka klassificering av lösta aviseringar

När du löser en Microsoft Defender för Slutpunkt-avisering kan din säkerhetspersonal ange om en avisering har verifierats som:

* En verklig varning som identifierar faktiska intrångsaktiviteter eller hotkomponenter
* En falsk varning som felaktigt har upptäckt normal aktivitet

**Klassificeringskortet för** enhetsaviseringar visar om dina lösta varningar har klassificerats som sanna eller falska varningar. Från det här kortet kan du visa mer information på Microsoft Defender Säkerhetscenter-portalen.

Obs! I vissa fall är klassificeringsinformation inte tillgänglig för vissa aviseringar.

![Klassificeringskort för enhetsavisering](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Övervaka att lösta aviseringar fastställs

Förutom att klassificera om en avisering är sann eller falsk vid en lösning kan din säkerhetspersonal ge ett avgörande. Ett avgörande anger vilken typ av normal eller skadlig aktivitet som hittades vid valideringen av aviseringen.

På **determinationskortet för enhetsavisering** visas vilken determination som tillhandahålls för varje avisering.

* **APT:** avancerat beständigt hot, som anger att den identifierade aktiviteten eller hotkomponenten är en del av en avancerad intrångskomponent som utformats för att få ett fothåll i det påverkade nätverket  
* **Skadlig** programvara: skadlig fil eller kod
* **Säkerhetspersonal**: normal aktivitet utförd av säkerhetspersonal
* **Säkerhetstestning:** aktivitet eller komponenter som är utformade för att simulera faktiska hot och som förväntas utlösa säkerhetsmätare och generera varningar
* **Oönskad programvara:** appar och annan programvara som inte anses vara skadlig men som på annat sätt strider mot policyn eller acceptabla användningsstandarder
* **Övriga:** andra avgöranden som inte omfattas av de angivna typerna

Från det här kortet kan du visa mer information i Microsoft Defender Säkerhetscenter.

![Determinationskort för enhetsavisering](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Förstå vilka enheter som är i riskzonen

**Enhetsskydd** visar risknivån för enheter. Risknivån baseras på faktorer som typ och allvarlighetsgrad för aviseringar på enheten.

![Kortet för enhetsskydd](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Övervaka och rapportera status för Intune-hanterade enheter

Följande rapporter innehåller data från enheter som är registrerade i Intune. Data från ej registrerade enheter ingår inte. Endast globala administratörer kan visa dessa kort.

Intune-registrerade enhetsdata omfattar:

* Enhetsefterlevnad
* Enheter med aktiv skadlig programvara
* Typer av skadlig programvara på enheter
* Skadlig programvara på enheter
* Enheter med identifiering av skadlig programvara
* Användare med identifiering av skadlig programvara

### <a name="monitor-device-compliance"></a>Övervaka enhetsefterlevnad

**Enhetsefterlevnad** visar hur många enheter som är registrerade i Intune och som uppfyller konfigurationsprinciper.

![Enhetsefterlevnadskort](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Upptäck enheter med identifiering av skadlig kod

**Identifiering av skadlig kod** på enheten anger antalet registrerade Intune-enheter med skadlig programvara som inte har lösts helt. En brist på lösning kan vara på grund av väntande åtgärder, en omstart, en fullständig genomsökning, manuella användaråtgärder eller om åtgärden inte slutförts.

![Kortet för identifiering av skadlig kod på enheten](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Förstå vilka typer av skadlig programvara som upptäckts

**Typer av skadlig programvara på** enheter visar olika typer av skadlig programvara som har upptäckts på enheter som är registrerade i Intune. Du kan undersöka varje typ av information i Microsoft 365 säkerhetscenter.

![Typer av skadlig programvara på kortet enheter](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Förstå den specifika skadlig programvara som upptäckts på dina enheter

**Skadlig programvara på enheter** ger en lista över den specifika skadlig programvara som upptäckts på dina enheter.

![Skadlig programvara på enheters kort](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Förstå vilka enheter som har mest skadlig programvara

**Enheter med identifiering av skadlig kod** visar vilka enheter som har flest identifieringar av skadlig programvara. i Säkerhetscenter för Microsoft 365 kan du undersöka om skadlig programvara är aktiv, vem som använder enheten och dess hanteringsstatus i Intune.

![Enheter med kortet för identifiering av skadlig programvara](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Förstå vilka användare som har de enheter som har mest skadlig programvara

**Användare med identifiering av skadlig programvara** visar användare med enheter som har de flesta identifieringar av skadlig programvara. I Säkerhetscenter för Microsoft 365 kan du se hur många enheter som har tilldelats till varje användare och mer information om varje enhet och typen av skadlig programvara.

![Användare med kortet för identifiering av skadlig programvara](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a>Övervaka och hantera distribution och identifiering av minskningsregel för attackytor

[ASR-regler (Attack Surface Reduction)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) hjälper till att förhindra åtgärder och appar som vanligtvis används av sårbarhetssökning efter skadlig programvara för att smitta enheter. Dessa regler styr när och hur körbara filer kan köras. Du kan till exempel förhindra att JavaScript eller VBScript startar en nedladdad körbar fil, blockera Win32 API-anrop från Office-makron eller blockera processer som körs från USB-enheter.

![Attackytans visitkort](../../media/attack-surface-reduction-rules.png)

Kortet **för minskning av attackytan** ger en översikt över distributionen av regler på dina enheter.

I det översta fältet på kortet visas det totala antalet enheter som finns i följande distributionsläge:

* **Blockläge:** enheter med minst en regel konfigurerad för att blockera upptäckt aktivitet
* **Granskningsläge:** enheter utan regler som anger att blockera upptäckt aktivitet, men har minst en regeluppsättning för att granska upptäckt aktivitet  
* **Av:** enheter med alla ASR-regler inaktiverade

På den nedre delen av det här kortet visas inställningar enligt regel på alla dina enheter. Varje stapel anger antalet enheter som är inställda på att blockeras, granskningsidentifiering eller har regeln helt inaktiverad.

### <a name="view-asr-detections"></a>Visa ASR-identifieringar

Om du vill visa detaljerad information om ASR-regelidentifiering i nätverket väljer du Visa **identifieringar** på kortet för minskning av **attackytan.** Fliken **Identifieringar** på sidan med detaljerad rapport öppnas.

![Fliken Identifieringar](../../media/detections-tab.png)

I diagrammet högst upp på sidan visas identifieringar över tidsstackningsidentifiering som har blockerats eller granskats. Tabellen längst ned visar de senaste identifieringarna. Använd följande information i tabellen för att förstå hur identifieringarna ser ut:

* **Upptäckt fil:** filen, vanligtvis ett skript eller ett dokument, vars innehåll utlöste den misstänkta attackaktiviteten
* **Regel:** namn som beskriver attackaktiviteterna som regeln har utformats för att fånga in. Läs om befintliga ASR-regler
* **Källapp:** programmet som läst in eller kört innehåll som utlöste den misstänkta attackaktiviteten. Det kan vara ett legitimt program, till exempel en webbläsare, ett Office-program eller ett systemverktyg som PowerShell
* **Publisher:** leverantören som släppte källappen

### <a name="review-device-asr-rule-settings"></a>Granska inställningar för ASR-regler för enheter

Gå till **fliken Konfiguration på rapportsidan** för minskning av attackytan och granska regelinställningarna för enskilda enheter.  Välj en enhet för att få detaljerad information om huruvida varje regel är i blockläge, granskningsläge eller helt inaktiverat.

![Fliken Konfiguration](../../media/configuration-tab.png)

Microsoft Intune tillhandahåller hanteringsfunktioner för dina ASR-regler. Om du vill uppdatera inställningarna väljer du **Kom** igång **under** Konfigurera enheter på fliken för att öppna enhetshantering på Intune.

### <a name="exclude-files-from-asr-rules"></a>Undanta filer från ASR-regler

Microsoft 365 Säkerhetscenter samlar in [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) namnen på filerna som du kanske vill utesluta från identifieringar genom regler för att minska attackytan. Genom att utesluta filer kan du minska antalet falska positiva identifieringar och använda minskningsregler för attackytan i blockläge med större säkerhet.

Undantagen hanteras i Microsoft Intune, men Microsoft 365 Säkerhetscenter innehåller ett analysverktyg som hjälper dig att förstå filerna. Om du vill börja samla in filer för undantag går du **till fliken** Lägg till undantag på **rapportsidan för minskning av attackytan.**

>[!NOTE]  
>Verktyget analyserar identifieringar av alla minskningsregler för attackytan, men [endast vissa regler stöder undantag.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)

![Fliken Lägg till undantag](../../media/add-exclusions-tab.png)

Tabellen innehåller alla filnamn som upptäckts av dina minskningsregler för attackytan. Du kan välja filer för att granska effekterna av att utesluta dem:

* Hur många färre identifieringar
* Hur många färre enheter rapporterar identifieringarna

Om du vill visa en lista över de markerade filerna med fullständiga sökvägar för undantag väljer du **Hämta undantagssökvägar.**

Loggar för ASR-regeln Blockera autentiseringsuppgifter som stjäls från Windows lokala säkerhetsutfärdares **undersystem (lsass.exe) fångar** källappens **lsass.exe.** Det är en vanlig systemfil, men fångas som den identifierade filen. Därför innehåller den genererade listan med undantagssökvägar den här filen. Om du vill utesluta filen som utlöste den här **regeln ilsass.exe** ska du använda sökvägen till källappen i stället för den identifierade filen.

Du hittar källappen genom [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) att köra följande avancerade fråga för den här specifika regeln (identifierad med regel-ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Söka efter undantag i filer

Innan du utesluter en fil från ASR rekommenderar vi att du kontrollerar filen för att avgöra om den verkligen inte är skadlig.

Om du vill granska en fil använder [du filinformationssidan](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) i Microsoft Defender Säkerhetscenter. Sidan innehåller information om intrånget och förhållandet för virustotal antivirusidentifiering. Du kan också använda sidan för att skicka filen för djupanalys.

Om du vill hitta en identifierad fil i Microsoft Defender Säkerhetscenter söker du efter alla ASR-identifieringar med hjälp av följande avancerade sökfråga:

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Använd **SHA1** **ellerItierprocessSHA1** i resultaten för att söka efter filen med hjälp av det universella sökfältet i Microsoft Defender Säkerhetscenter.
