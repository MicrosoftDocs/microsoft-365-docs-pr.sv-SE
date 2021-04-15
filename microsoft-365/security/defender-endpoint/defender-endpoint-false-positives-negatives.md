---
title: Åtgärda falska positiva/negativa i Microsoft Defender för Endpoint
description: Lär dig hur du hanterar falska positiva eller falska negativa resultat i Microsoft Defender för Slutpunkt.
keywords: antivirus, undantag, undantag, defender atp, false positive, false negative, blockerad fil, blockerad url
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs, yonghree, jcedola
ms.custom: FPFN
ms.openlocfilehash: f2615cf5ec49c9df27472f04c367f30511e9c0cc
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759876"
---
# <a name="address-false-positivesnegatives-in-microsoft-defender-for-endpoint"></a>Åtgärda falska positiva/negativa i Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146806)

I slutpunktsskyddslösningar är en falsk positivhet en enhet, till exempel en fil eller en process, som identifierades och identifierades som skadlig, även om enheten faktiskt inte är ett hot. En falsk negativ är en enhet som inte identifierades som ett hot, även om den faktiskt är skadlig. Falska positiva/negativa kan uppstå med alla lösningar för skydd mot hot, inklusive [Microsoft Defender för slutpunkt.](microsoft-defender-endpoint.md)

![Definition av falska positiva och negativa tal i Defender för Slutpunkt](images/false-positives-overview.png)

Som tur är går det att vidta åtgärder för att åtgärda och minska den här typen av problem. Om du ser falska positiva/negativa resultat i Microsoft [Defender](../defender/microsoft-365-security-center-mde.md)Säkerhetscenter kan dina säkerhetsåtgärder vidta åtgärder för att åtgärda dem på följande sätt:

1.  [Granska och klassificera aviseringar](#part-1-review-and-classify-alerts) 
2.  [Granska åtgärder som har vidtagits](#part-2-review-remediation-actions)
3.  [Granska och definiera undantag](#part-3-review-or-define-exclusions)
4.  [Skicka en entitet för analys](#part-4-submit-a-file-for-analysis)
5.  [Granska och justera dina skyddsinställningar för hot](#part-5-review-and-adjust-your-threat-protection-settings)

Du kan få hjälp om du fortfarande har problem med falska positiva/negativa när du har utfört de uppgifter som beskrivs i den här artikeln. Se [Behöver du mer hjälp?](#still-need-help)

![Steg för att åtgärda falska positiva och negativa tal](images/false-positives-step-diagram.png)

> [!NOTE]
> Den här artikeln är avsedd som vägledning för säkerhetsoperatorer och säkerhetsadministratörer som använder [Microsoft Defender för Slutpunkt.](microsoft-defender-endpoint.md)

## <a name="part-1-review-and-classify-alerts"></a>Del 1: Granska och klassificera aviseringar

Om du ser ett [meddelande](alerts.md) som utlöstes eftersom något identifierades som skadligt eller misstänkt, och som inte borde ha varit det, kan du dölja varningen för den enheten. Du kan också dölja aviseringar som inte nödvändigtvis är falska positiva, men som inte är viktiga. Vi rekommenderar att du även klassificerar aviseringar. 

Att hantera dina varningar och klassificera sant/falskt-positiva hjälper till att utbilda din lösning för hotskydd och kan minska antalet falska positiva eller falska negativa resultat över tid. Om du vidtar de här stegen minskar också bruset i instrumentpanelen för säkerhetsåtgärder så att säkerhetsteamet kan fokusera på arbetsobjekt med högre prioritet.

### <a name="determine-whether-an-alert-is-accurate"></a>Avgöra om en avisering är korrekt

Innan du klassificerar eller ignorerar en avisering måste du avgöra om aviseringen är korrekt, en falsk positiv eller en varning.

1. Gå till Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) och logga in.

2. Välj Aviseringskö **i navigeringsfönstret.**

3. Välj en avisering om du vill ha mer information om aviseringen. (Se [Granska aviseringar i Microsoft Defender för Slutpunkt](review-alerts.md).)

4. Beroende på aviseringsstatusen följer du stegen som beskrivs i följande tabell: 

| Aviseringsstatus | Vad kan jag göra? |
|:---|:---|
| Aviseringen är korrekt | Tilldela aviseringen och undersök [den](investigate-alerts.md) sedan ytterligare. |
| Aviseringen är en falsk positiv | 1. [Klassificera aviseringen](#classify-an-alert) som en falsk positivhet. <br/>2. [Ignorera aviseringen](#suppress-an-alert). <br/> 3. [Skapa en indikator för](#indicators-for-microsoft-defender-for-endpoint) Microsoft Defender för Endpoint. <br/> 4. [Skicka en fil till Microsoft för analys](#part-4-submit-a-file-for-analysis). |
| Aviseringen är korrekt, men den är inte viktig | [Klassificera aviseringen](#classify-an-alert) som en sant positiv och utelämna [sedan aviseringen](#suppress-an-alert). |

### <a name="classify-an-alert"></a>Klassificera en avisering

Aviseringar kan klassificeras som falska positiva resultat eller sant positiva resultat i Microsoft Defender Säkerhetscenter. Genom att klassificera aviseringar kan du träna Microsoft Defender för Endpoint så att du med tiden ser fler sanna aviseringar och färre falska aviseringar.

1. Gå till Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) och logga in.

2. Välj **Aviseringskö** och välj sedan en avisering.

3. För den valda aviseringen väljer du **Åtgärder**  >  **Hantera avisering**. Ett utfällt fönster öppnas.

4. I avsnittet **Hantera avisering** väljer du antingen **True-avisering** **eller Falskt-avisering.** (Använd **falsk varning för** att klassificera en felaktighet.)

> [!TIP]
> Mer information om hur du ignorerar aviseringar finns i [Hantera Microsoft Defender för slutpunktsaviseringar.](/microsoft-365/security/defender-endpoint/manage-alerts) Och om organisationen använder en säkerhetsinformations- och händelsehanteringsserver (SIEM) ser du till att definiera en regel för regeln här också. 

### <a name="suppress-an-alert"></a>Ignorera en avisering

Om du har aviseringar som antingen är falska positiva eller som är sanna positiva, men för oimporterande händelser, kan du dölja dessa aviseringar i Microsoft Defender Säkerhetscenter. Att dölja aviseringar hjälper till att minska bruset i instrumentpanelen för säkerhetsåtgärder. 

1. Gå till Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) och logga in.

2. I navigeringsfönstret väljer du **Aviseringskö**.

3. Markera en avisering om att du inte vill öppna **fönstret** Information.

4. I fönstret **Information** väljer du ellipsen (**...**) och sedan **Skapa en regel för en uteslutning.**

5. Ange alla inställningar för regeln för regeln och välj sedan **Spara**.

> [!TIP]
> Behöver du hjälp med regelregler? Mer [information finns i Ignorera en avisering och skapa en ny regel för en ny regel.](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule)

## <a name="part-2-review-remediation-actions"></a>Del 2: Granska åtgärder

[Åtgärdsåtgärder, som](manage-auto-investigation.md#remediation-actions)att skicka en fil till karantän eller stoppa en process, vidtas på enheter (till exempel filer) som identifieras som hot. Flera typer av åtgärder sker automatiskt genom automatiserad undersökning och Microsoft Defender Antivirus:   
- Sätt en fil i karantän
- Ta bort en registernyckel
- "Kill a process"
- Stoppa en tjänst
- Inaktivera en drivrutin
- Ta bort en schemalagd aktivitet

Andra åtgärder, som att starta en antivirussökning eller samla in ett undersökningspaket, kan inträffa manuellt eller via [Live Response.](live-response.md) Åtgärder som vidtas i Live Response kan inte ångras.

När du har granskat dina aviseringar är nästa steg att [granska åtgärder](manage-auto-investigation.md). Om några åtgärder har vidtagits på grund av falska positiva resultat kan du ångra de flesta typerna av åtgärdsåtgärder. Specifikt kan du:

- [Återställa en fil i karantän från Åtgärdscenter](#restore-a-quarantined-file-from-the-action-center)
- [Ångra flera åtgärder samtidigt](#undo-multiple-actions-at-one-time)
- [Ta bort en fil från karantän på flera enheter.](#remove-a-file-from-quarantine-across-multiple-devices)  och 
- [Återställa fil från karantän](#restore-file-from-quarantine)

När du har granskat och ångrat åtgärder som har [utförts](#part-3-review-or-define-exclusions)på grund av falska positiva resultat kan du fortsätta att granska eller definiera undantag .

### <a name="review-completed-actions"></a>Granska slutförda åtgärder

1. Gå till Åtgärdscenter ( [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) ) och logga in. 

2. Välj fliken **Historik** för att visa en lista över åtgärder som har vidtagits.  

3. Välj ett objekt om du vill visa mer information om åtgärden som har vidtagits.

### <a name="restore-a-quarantined-file-from-the-action-center"></a>Återställa en fil i karantän från Åtgärdscenter

1. Gå till Åtgärdscenter ( [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) ) och logga in.

2. Välj **en åtgärd** som du vill ångra på fliken Historik.

3. Välj Ångra i den utfällade **rutan.** Om åtgärden inte kan ångras med den här metoden visas inte knappen **Ångra.** (Mer information finns i [Ångra slutförda åtgärder](manage-auto-investigation.md#undo-completed-actions).)

### <a name="undo-multiple-actions-at-one-time"></a>Ångra flera åtgärder samtidigt

1. Gå till Åtgärdscenter ( [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) ) och logga in.

2. Markera **de åtgärder** du vill ångra på fliken Historik.

3. I fönstret till höger på skärmen väljer du **Ångra**.

### <a name="remove-a-file-from-quarantine-across-multiple-devices"></a>Ta bort en fil från karantän på flera enheter 

> [!div class="mx-imgBorder"]
> ![Karantänfil](images/autoir-quarantine-file-1.png)

1. Gå till Åtgärdscenter ( [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) ) och logga in.

2. På fliken **Historik** väljer du en fil som har karantänfilen **Åtgärdstyp.**

3. I fönstret till höger på skärmen väljer du Använd för **fler X-instanser** av den här filen och sedan **Ångra**.

### <a name="restore-file-from-quarantine"></a>Återställa fil från karantän

Du kan återställa och ta bort en fil från karantän om du har fastställt att den är ren efter en undersökning. Kör följande kommando på varje enhet där filen satts i karantän.

1. Öppna en upphöjd kommandoradsfråga på enheten:

   1. Gå till **Start** och skriv _cmd_.

   1. Högerklicka på **Kommandotolken** och välj **Kör som administratör.**

2. Ange följande kommando och tryck på **Retur:**

    ```console
    "ProgramFiles%\Windows Defender\MpCmdRun.exe" –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
    ```

    > [!NOTE]
    > I vissa fall kan **ThreatName visas** som: `EUS:Win32/
CustomEnterpriseBlock!cl` . Defender för Endpoint återställer alla egna blockerade filer som har satts i karantän på den här enheten under de senaste 30 dagarna.

    > [!IMPORTANT]
    > En fil som har satts i karantän som ett potentiellt nätverkshot kanske inte kan återställas. Om en användare försöker återställa filen efter karantänen är filen kanske inte tillgänglig. Det kan bero på att systemet inte längre har nätverksautentiseringsuppgifter för att få åtkomst till filen. Vanligtvis beror det på en tillfällig inloggning till ett system eller en delad mapp och åtkomsttoken har upphört att gälla.

3. I fönstret till höger på skärmen väljer du Använd för **fler X-instanser** av den här filen och sedan **Ångra**. 


## <a name="part-3-review-or-define-exclusions"></a>Del 3: Granska eller definiera undantag

Ett undantag är en enhet, till exempel en fil eller url, som du anger som ett undantag för åtgärder. Den undantagna enheten kan fortfarande identifieras, men inga åtgärder vidtas på den enheten. Den identifierade filen eller processen stoppas inte, skickas till karantän, tas bort eller ändras på annat sätt av Microsoft Defender för Slutpunkt. 

Så här definierar du undantag i Microsoft Defender för Slutpunkt:
- [Definiera undantag för Microsoft Defender Antivirus](#exclusions-for-microsoft-defender-antivirus)
- [Skapa "tillåt"-indikatorer för Microsoft Defender för Endpoint](#indicators-for-microsoft-defender-for-endpoint)

> [!NOTE]
> Undantag från Microsoft Defender Antivirus gäller endast för antivirusskydd, inte för andra Microsoft Defender-funktioner för slutpunkter. Om du vill utesluta filer allmänt använder du undantag för Microsoft Defender Antivirus och [anpassade indikatorer](/microsoft-365/security/defender-endpoint/manage-indicators) för Microsoft Defender för Slutpunkt.

Procedurerna i det här avsnittet beskriver hur du definierar undantag och indikatorer.

### <a name="exclusions-for-microsoft-defender-antivirus"></a>Undantag för Microsoft Defender Antivirus

I allmänhet behöver du inte definiera undantag för Microsoft Defender Antivirus. Se till att du definierar undantag sparsamt och att du endast tar med filer, mappar, processer och process öppna filer som resulterar i falska positiva resultat. Kontrollera även regelbundet att du har definierat undantag. Vi rekommenderar att du [använder Microsoft Endpoint Manager](/mem/endpoint-manager-overview) för att definiera eller redigera dina undantag för antivirus. Du kan emellertid använda andra metoder, till exempel [Grupprincip](/azure/active-directory-domain-services/manage-group-policy) (se [Hantera Microsoft Defender för slutpunkt).](manage-atp-post-migration.md)

> [!TIP]
> Behöver du hjälp med undantag för antivirusprogram? Se [Konfigurera och validera undantag för Microsoft Defender Antivirus-genomsökningar.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)

#### <a name="use-microsoft-endpoint-manager-to-manage-antivirus-exclusions-for-existing-policies"></a>Använda Microsoft Endpoint Manager för att hantera undantag för antivirus (för befintliga principer)

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Välj **Endpoint Security**  >  **Antivirus** och välj sedan en befintlig princip. (Om du inte har en befintlig princip, eller om du vill skapa en ny princip, kan du gå vidare [till nästa procedur](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)).

3. Välj **Egenskaper** och bredvid **Konfigurationsinställningar** väljer du **Redigera**.

4. Visa **undantag för Microsoft Defender Antivirus** och ange sedan dina undantag.

5. Välj **Granska + spara** och välj sedan **Spara.**

#### <a name="use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions"></a>Använda Microsoft Endpoint Manager för att skapa en ny antivirusprincip med undantag

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Välj **Endpoint Security**  >  **Antivirus**+ Create  >  **Policy**. 

3. Välj en plattform (till exempel **Windows 10 och senare**, **macOS** eller **Windows 10 och Windows Server).**

4. Under **Profil** väljer du **Microsoft Defender Antivirus-undantag** och sedan **Skapa**.

5. Ange ett namn och en beskrivning för profilen och välj sedan **Nästa**.

6. På fliken **Konfigurationsinställningar** anger du dina undantag för antivirus och väljer sedan **Nästa.**

7. Om du **använder omfattningstaggar** i organisationen på fliken Omfattningstaggar anger du omfattningstaggar för principen du skapar. (Se [Omfattningstaggar](/mem/intune/fundamentals/scope-tags).)

8. På **fliken Tilldelningar** anger du de användare och grupper som principen ska tillämpas på och väljer sedan **Nästa.** (Om du behöver hjälp med tilldelningar kan du gå [till Tilldela användar- och enhetsprofiler i Microsoft Intune](/mem/intune/configuration/device-profile-assign).)

9. Granska **inställningarna på fliken** Granska + skapa och välj sedan **Skapa**.

### <a name="indicators-for-microsoft-defender-for-endpoint"></a>Indikatorer för Microsoft Defender för Slutpunkt

[Indikatorer](/microsoft-365/security/defender-endpoint/manage-indicators) (särskilt indikatorer för kompromettering och IOC) gör det möjligt för teamet med säkerhetsåtgärder att definiera identifiering, skydd och undantag från enheter. Du kan till exempel ange att vissa filer ska utelämnas från genomsökningar och åtgärdsåtgärder i Microsoft Defender för Slutpunkt. Indikatorer kan också användas för att generera aviseringar för vissa filer, IP-adresser eller URL-adresser.

Om du vill ange enheter som undantag för Microsoft Defender för Endpoint skapar du "tillåt"-indikatorer för de enheterna. Sådana "tillåt"-indikatorer i Microsoft [](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)Defender för Slutpunkt gäller för nästa generations [skydd,](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)identifiering och svar av slutpunkter och automatiserad undersökning [& åtgärd](/microsoft-365/security/defender-endpoint/automated-investigations).

"Tillåt"-indikatorer kan skapas för:

- [Filer](#indicators-for-files)
- [IP-adresser, URL:er och domäner](#indicators-for-ip-addresses-urls-or-domains)
- [Programcertifikat](#indicators-for-application-certificates)

![Diagram över indikatortyper](images/false-positives-indicators.png)

#### <a name="indicators-for-files"></a>Indikatorer för filer

Om du skapar en indikator för "tillåt" för en [fil,](/microsoft-365/security/defender-endpoint/indicator-file)till exempel en körbar fil, förhindrar det att filer som din organisation använder blockeras. Filer kan innehålla flyttbara körbara filer (PE), till exempel `.exe` `.dll` filer. 

Innan du skapar indikatorer för filer bör du kontrollera att följande krav uppfylls:
- Microsoft Defender Antivirus är konfigurerat med molnbaserat skydd aktiverat (se [Hantera molnbaserat skydd)](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)
- Antimalware client version is 4.18.1901.x or later 
- Enheter kör Windows 10, version 1703 eller senare. Windows Server 2016; eller Windows Server 2019 
- Funktionen [Blockera eller tillåt är aktiverad](/microsoft-365/security/defender-endpoint/advanced-features) 

#### <a name="indicators-for-ip-addresses-urls-or-domains"></a>Indikatorer för IP-adresser, URL-adresser och domäner

Om du skapar en "tillåt"-indikator för en [IP-adress, URL-adress](/microsoft-365/security/defender-endpoint/indicator-ip-domain)eller domän förhindrar det att webbplatser eller IP-adresser som din organisation använder blockeras.

Innan du skapar indikatorer för IP-adresser, URL:er eller domäner bör du kontrollera att följande krav uppfylls:
- Nätverksskydd i Defender för Slutpunkt är aktiverat i blockläge (se [Aktivera nätverksskydd](/microsoft-365/security/defender-endpoint/enable-network-protection))
- Antimalware client version is 4.18.1906.x or later 
- Enheter kör Windows 10, version 1709 eller senare 

Anpassade nätverksindikatorer är aktiverat i Microsoft Defender Säkerhetscenter (se [Avancerade funktioner)](/microsoft-365/security/defender-endpoint/advanced-features)   

#### <a name="indicators-for-application-certificates"></a>Indikatorer för programcertifikat 

När du [skapar en "tillåt"-indikator](/microsoft-365/security/defender-endpoint/indicator-certificates)för ett programcertifikat förhindrar det att program, till exempel internt utvecklade program, som din organisation använder blockeras. `.CER` eller `.PEM` så stöds filnamnstillägg.   

Innan du skapar indikatorer för programcertifikat ska du kontrollera att följande krav uppfylls:
- Microsoft Defender Antivirus är konfigurerat med molnbaserat skydd aktiverat (se [Hantera molnbaserat skydd)](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)
- Antimalware client version is 4.18.1901.x or later 
- Enheter kör Windows 10, version 1703 eller senare. Windows Server 2016; eller Windows Server 2019 
- Definitioner av skydd mot virus och hot är uppdaterade  

> [!TIP]
> När du skapar indikatorer kan du definiera dem en i gånger ett, eller importera flera objekt samtidigt. Tänk på att det finns en gräns på 15 000 indikatorer för en enskild klientorganisation. Och du kan behöva samla in viss information först, till exempel information om filhash. Kontrollera att du har granskat förutsättningarna innan du [skapar indikatorer .](manage-indicators.md) 

## <a name="part-4-submit-a-file-for-analysis"></a>Del 4: Skicka en fil för analys

Du kan skicka enheter, till exempel filer och identifieringar utan filer, till Microsoft för analys. Microsoft security analyze all submissions, and their results help inform Microsoft Defender for Endpoint threat protection capabilities. När du loggar in på webbplatsen för inskickat material kan du spåra dina inskickade material.

### <a name="submit-a-file-for-analysis"></a>Skicka en fil för analys

Om du har en fil som antingen identifierats felaktigt som skadlig eller har missats följer du dessa steg för att skicka filen för analys.

1. Läs riktlinjerna här: [Skicka filer för analys](/windows/security/threat-protection/intelligence/submission-guide).

2. Besök webbplatsen för inskicking av Microsoft Security Intelligence ( [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) ) och skicka in dina filer.

### <a name="submit-a-fileless-detection-for-analysis"></a>Skicka en fillös identifiering för analys

Om något identifierades som skadlig programvara baserat på beteende och du inte har en fil, kan du skicka filen `Mpsupport.cab` för analys. Du kan hämta *.cab-filen* med hjälp av verktyget Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) i Windows 10.

1.  Gå till ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` och kör sedan som `MpCmdRun.exe` administratör.

2.  Skriv `mpcmdrun.exe -GetFiles` och tryck sedan på **Retur.**
   En .cab-fil skapas som innehåller olika diagnostikloggar. Platsen för filen anges i utdata från kommandotolken. Platsen är som standard `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .

3.  Läs riktlinjerna här: [Skicka filer för analys](/windows/security/threat-protection/intelligence/submission-guide).

4.  Gå till webbplatsen för inskickade Microsoft Security Intelligence [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) () och skicka in .cab-filer.

### <a name="what-happens-after-a-file-is-submitted"></a>Vad händer när en fil har skickats?

Din inskickad information skannas omedelbart av våra system för att ge dig den senaste avgörande informationen redan innan en analytiker börjar hantera ditt ärende. Det är möjligt att en fil redan har skickats in och bearbetats av en analytiker. I sådana fall görs ett snabbt avgörande.

För inlämningar som inte redan har bearbetats prioriteras de för analys enligt följande:

- Vanliga filer som kan påverka ett stort antal datorer får högre prioritet.
- Autentiserade kunder, särskilt företagskunder med giltiga [SAID (Software Assurance-ID)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)får högre prioritet.
- Inskickade som har hög prioritet av SAID-innehavare ges omedelbar uppmärksamhet.

Du kan söka efter uppdateringar om din inskickning genom att logga in på webbplatsen [för inskickade Microsoft Security Intelligence.](https://www.microsoft.com/wdsi/filesubmission) 

> [!TIP]
> Mer information finns i [Skicka filer för analys.](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions)

## <a name="part-5-review-and-adjust-your-threat-protection-settings"></a>Del 5: Granska och justera dina inställningar för skydd mot hot

Microsoft Defender för Slutpunkt har ett brett utbud av alternativ, bland annat möjligheten att finjustera inställningar för olika funktioner. Om du får flera falska positiva resultat bör du granska organisationens inställningar för skydd mot hot. Du kan behöva göra några justeringar för att:

- [Moln levererat skydd](#cloud-delivered-protection)
- [Åtgärd för potentiellt oönskade program](#remediation-for-potentially-unwanted-applications)
- [Automatiserad undersökning och åtgärder](#automated-investigation-and-remediation)

### <a name="cloud-delivered-protection"></a>Moln levererat skydd

Kontrollera din moln levererat skyddsnivå för Microsoft Defender Antivirus. Som standard har moln levererat skydd inställningen **Ej konfigurerad,** vilket motsvarar en normal skyddsnivå för de flesta organisationer. Om ditt moln levererat skydd är inställt på **Hög,** Hög **+** eller Nolldögont kan du uppleva ett högre antal falska positiva resultat. 

> [!TIP]
> Mer information om hur du konfigurerar ditt moln levererat skydd finns [i Ange skyddsnivån för moln levererat.](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus)

Vi rekommenderar att du [använder Microsoft Endpoint Manager](/mem/endpoint-manager-overview) för att redigera eller ange skyddsinställningar som levereras i molnet. Du kan emellertid använda andra metoder, till exempel [Grupprincip](/azure/active-directory-domain-services/manage-group-policy) (se [Hantera Microsoft Defender för slutpunkt).](manage-atp-post-migration.md)

#### <a name="use-microsoft-endpoint-manager-to-review-and-edit-cloud-delivered-protection-settings-for-existing-policies"></a>Använd Microsoft Endpoint Manager för att granska och redigera skyddsinställningar som levereras till molnet (för befintliga principer)

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Välj **Endpoint Security**  >  **Antivirus** och välj sedan en befintlig princip. (Om du inte har en befintlig princip, eller om du vill skapa en ny princip, kan du gå vidare [till nästa procedur](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)).

3. Under **Hantera** väljer du **Egenskaper**. Välj sedan Redigera bredvid **Konfigurationsinställningar.** 

4. Expandera **Molnskydd** och granska din aktuella inställning på **raden Moln levererat skyddsnivå.** Vi rekommenderar att du ställer in moln levererat skydd till **Ej** konfigurerat, vilket ger starkt skydd samtidigt som det minskar risken för falska positiva resultat.

5. Välj **Granska + spara** och sedan **Spara.**

#### <a name="use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy"></a>Använd Microsoft Endpoint Manager för att ange skyddsinställningar som levereras i molnet (för en ny princip)

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Välj **Endpoint Security**  >  **Antivirus**+ Create  >  **policy**.

3. För **Plattform** väljer du ett alternativ och sedan För **Profile** väljer du **Antivirus** eller Microsoft Defender Antivirus (det **specifika** alternativet beror på vad du valde för **plattform**.) Välj sedan **Skapa**.

4. På **fliken Grunder** anger du ett namn och en beskrivning för principen. Välj sedan **Nästa**.

5. På fliken **Konfigurationsinställningar** **expanderar du Molnskydd** och anger följande inställningar:
   - Ställ **in Aktivera moln levererat skydd till** **Ja.**
   - Ställ **in skyddsnivån Moln levererat till** Ej **konfigurerad**. (Den här nivån ger en stark skyddsnivå som standard, samtidigt som du minskar risken för falska positiva resultat.)

6. Om du **använder omfattningstaggar** i organisationen på fliken Omfattningstaggar anger du omfattningstaggar för principen. (Se [Omfattningstaggar](/mem/intune/fundamentals/scope-tags).)

7. På **fliken Tilldelningar** anger du de användare och grupper som principen ska tillämpas på och väljer sedan **Nästa.** (Om du behöver hjälp med tilldelningar kan du gå [till Tilldela användar- och enhetsprofiler i Microsoft Intune](/mem/intune/configuration/device-profile-assign).)

8. Granska **inställningarna på fliken** Granska + skapa och välj sedan **Skapa**.  

### <a name="remediation-for-potentially-unwanted-applications"></a>Åtgärd för potentiellt oönskade program

Potentiellt oönskade program (PUA) är en kategori med programvara som kan göra att enheter körs långsamt, visar oväntade annonser eller installerar annan programvara som kan vara oväntad eller oönskad. Exempel på PUA-program är reklamprogramvara, sammanslagning av programvara och programvara som fungerar annorlunda med säkerhetsprodukter. Även om PUA inte betraktas som skadlig programvara, är vissa typer av programvara PUA baserat på deras beteende och rykte.

> [!TIP]
> Mer information om PUA finns i Identifiera [och blockera potentiellt oönskade program.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
 
Beroende på vilka appar din organisation använder kan det hända att du får falska positiva resultat som ett resultat av inställningarna för PUA-skydd. Om det behövs kan du köra PUA-skydd i granskningsläge ett tag eller använda PUA-skydd på en delmängd enheter i organisationen. PUA-skydd kan konfigureras för webbläsaren Microsoft Edge och för Microsoft Defender Antivirus.

Vi rekommenderar att du [använder Microsoft Endpoint Manager för](/mem/endpoint-manager-overview) att redigera eller ange PUA-skyddsinställningar. Du kan emellertid använda andra metoder, till exempel [Grupprincip](/azure/active-directory-domain-services/manage-group-policy) (se [Hantera Microsoft Defender för slutpunkt).](manage-atp-post-migration.md)

#### <a name="use-microsoft-endpoint-manager-to-edit-pua-protection-for-existing-configuration-profiles"></a>Använda Microsoft Endpoint Manager för att redigera PUA-skydd (för befintliga konfigurationsprofiler)

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Välj   >  **Konfigurationsprofiler för** enheter och välj sedan en befintlig princip. (Om du inte har en befintlig princip, eller om du vill skapa en ny princip, kan du gå [vidare till nästa procedur](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile).)

3. Under **Hantera** väljer du **Egenskaper** och bredvid Konfigurationsinställningar **väljer** du sedan **Redigera**.

4. På fliken **Konfigurationsinställningar** rullar du ned och expanderar **Microsoft Defender Antivirus.**

5. Ange **Granska för Identifiera potentiellt oönskade** **program.** (Du kan inaktivera det, men med granskningsläget kan du se identifieringar.)

6. Välj **Granska + spara** och välj sedan **Spara.**

#### <a name="use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile"></a>Använd Microsoft Endpoint Manager för att ange PUA-skydd (för en ny konfigurationsprofil)

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Välj   >  **Konfigurationsprofiler för enheter**+ Skapa  >  **profil**.

3. För plattformen **väljer** du **Windows 10 och senare** och för Profil **väljer** du **Enhetsbegränsningar**.

4. På fliken **Grunder anger** du ett namn och en beskrivning för principen. Välj sedan **Nästa**.

5. På fliken **Konfigurationsinställningar** rullar du ned och expanderar **Microsoft Defender Antivirus.**

6. Ange **Granska för Identifiera potentiellt oönskade** program och välj sedan **Nästa.**  (Du kan inaktivera PUA-skydd, men med granskningsläget kan du se identifieringar.)

7. På **fliken Tilldelningar** anger du de användare och grupper som principen ska tillämpas på och väljer sedan **Nästa.** (Om du behöver hjälp med tilldelningar kan du gå [till Tilldela användar- och enhetsprofiler i Microsoft Intune](/mem/intune/configuration/device-profile-assign).)

8. På fliken **Tillämplighetsregler** anger du de OS-utgåvor eller versioner som ska ingå eller exkluderas från principen. Du kan till exempel ange att principen ska tillämpas på alla enheter vissa versioner av Windows 10. Välj sedan **Nästa**.

9. Granska **inställningarna på fliken** Granska + skapa och välj sedan **Skapa**.

### <a name="automated-investigation-and-remediation"></a>Automatiserad undersökning och åtgärder

[Funktionerna automatisk undersökning och åtgärder](automated-investigations.md) (AIR) är utformade för att undersöka varningar och vidta omedelbar åtgärd för att lösa överträdelser. När aviseringar utlöses och en automatiserad undersökning körs genereras en bedömning för varje bevis som undersöks. Omdömen kan vara *skadliga,* *misstänkta* eller *inga hot hittades.* 

Åtgärder vidtas [på](/microsoft-365/security/defender-endpoint/automation-levels) artefakter som anses vara skadliga eller misstänkta, beroende på hur mycket automatisering som har ställts in för din organisation och *andra* *säkerhetsinställningar.* I vissa fall sker åtgärder automatiskt. i andra fall vidtas åtgärder manuellt eller bara efter godkännande från säkerhetsteamet. 

- [Läs mer om automatiseringsnivåer](/microsoft-365/security/defender-endpoint/automation-levels)– och sedan 
- [Konfigurera AIR-funktioner i Defender för Slutpunkt](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation).

> [!IMPORTANT]
> Vi rekommenderar att *du använder fullständig* automation för automatiserad undersökning och åtgärd. Stäng inte av de här funktionerna på grund av en felaktig positiv inställning. Använd i stället [indikatorerna "tillåt" för att](#indicators-for-microsoft-defender-for-endpoint)definiera undantag och ange att automatisk undersökning och åtgärd ska vidta lämpliga åtgärder automatiskt. Genom [att följa dessa](automation-levels.md#levels-of-automation) anvisningar kan du minska antalet varningar som säkerhetsgruppen måste hantera. 

## <a name="still-need-help"></a>Behöver du fortfarande hjälp?

Kontakta teknisk support om du har gått igenom alla steg i den här artikeln och fortfarande behöver hjälp.

1. Gå till Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) och logga in.

2. Välj frågetecken (**?**) i det övre högra hörnet och välj sedan **Microsoft support.**

3. Beskriv **problemet i** fönstret Supportassistenten och skicka sedan meddelandet. Därifrån kan du öppna en tjänstförfrågan.  

## <a name="see-also"></a>Se även

[Hantera Microsoft Defender för Slutpunkt](manage-atp-post-migration.md)

[Översikt över Microsoft Defender Säkerhetscenter](/microsoft-365/security/defender-endpoint/use) 
