---
title: Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer
description: Hantera hur Microsoft Defender Antivirus får skydd och produktuppdateringar.
keywords: uppdateringar, säkerhetsbaslinjer, skydd, schemauppdateringar, tvinga uppdateringar, mobiluppdateringar, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b70cf96cde7d4dff8e2a4db6ce2469090dba7eb1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765617"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivirus

Det finns två typer av uppdateringar som är relaterade till att hålla Microsoft Defender Antivirus uppdaterat:

- Säkerhetsintelligensuppdateringar
- Produktuppdateringar

> [!IMPORTANT]
> Att hålla Microsoft Defender Antivirus uppdaterat är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack.  
> Uppdatera antivirusskyddet även om Microsoft Defender Antivirus körs i passiv [form.](./microsoft-defender-antivirus-compatibility.md)
> 
> Om du vill se de senaste motor-, plattforms- och signaturdatumen går du till Säkerhetsintelligensuppdateringar för [Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

## <a name="security-intelligence-updates"></a>Säkerhetsintelligensuppdateringar

Microsoft Defender Antivirus använder [moln levererat skydd](cloud-protection-microsoft-defender-antivirus.md) (kallas även Microsofts tjänst för avancerat skydd eller KARTOR) och laddar regelbundet ned säkerhetsintelligensuppdateringar för att skydda dig.

> [!NOTE]
> Uppdateringar släpps under kb-nummer nedan:  
> Microsoft Defender Antivirus: KB2267602  
> System Center Endpoint Protection: KB2461484

Moln levererat skydd är alltid på och kräver en aktiv anslutning till Internet för att fungera. Säkerhetsintelligensuppdateringar sker enligt ett schemalagt tidsfrekvens (kan konfigureras via princip). Mer information finns i [Använda Molnskydd i Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md) 

En lista över de senaste säkerhetsintelligensuppdateringarna finns i [Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

Motoruppdateringar ingår i säkerhetsintelligensuppdateringar och släpps varje månad.

## <a name="product-updates"></a>Produktuppdateringar

Microsoft Defender Antivirus kräver [månatliga uppdateringar (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (kallas plattformsuppdateringar) och kommer att få större funktionsuppdateringar tillsammans med Windows 10-versioner. 

Du kan hantera distributionen av uppdateringar på något av följande sätt: 

- [Windows Server Update Service (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- Den vanliga metoden du använder för att distribuera Microsoft och Windows-uppdateringar till slutpunkter i nätverket.

Mer information finns i [Hantera källorna för uppdateringar av Microsoft Defender Antivirus Protection](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).

> [!NOTE]
> Månatliga uppdateringar släpps i faser, vilket resulterar i att flera paket visas i [Window Server Update Services.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)

## <a name="monthly-platform-and-engine-versions"></a>Månadsplattform och motorversioner

Information om hur du uppdaterar eller installerar plattformsuppdateringen finns [i Uppdatering för Windows Defender-program mot skadlig programvara.](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)

Alla våra uppdateringar innehåller 
- prestandaförbättringar
- förbättringar av användbarheten. och 
- förbättringar av integreringen (Cloud, Microsoft 365 Defender).
<br/><br/>

<details>
<summary> Mars–2021 (plattform: 4.18.2103.7 | Motor: 1.1.18000.5)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.335.36.0**  
&ensp;Utgiven: **1 april 2021**  
&ensp;Plattform: **4.19.2103.7**  
&ensp;Motor: **1.1.18000.5**  
&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**
    
### <a name="whats-new"></a>Nyheter

- Förbättring av motor för funktionsövervakning 
- Expanderade nätverkets råstyrt-attackåtgärder 
- Det gick inte att ändra händelsegenerering av försök [när skydd mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md) är aktiverat

### <a name="known-issues"></a>Kända problem
Inga kända problem  
<br/>
</details><details>
<summary> Februari-2021 (Plattform: 4.18.2102.3 | Motor: 1.1.17900.7)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.333.7.0**  
&ensp;**Utgiven: 9 mars 2021**  
&ensp;Plattform: **4.19.2102.3**  
&ensp;Motor: **1.1.17900.7**  
&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**
    
### <a name="whats-new"></a>Nyheter

- Förbättrad återställning av tjänster genom skydd [mot manipulering](prevent-changes-to-security-settings-with-tamper-protection.md)
- Utöka skyddsområdet för manipulering

### <a name="known-issues"></a>Kända problem
Inga kända problem  
<br/>
</details><details>
<summary> Januari–2021 (plattform: 4.18.2101.9 och | Motor: 1.1.17800.5)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**  
&ensp;**Utgiven: 2 februari 2021**  
&ensp;Plattform: **4.18.2101.9**  
&ensp;Motor: **1.1.17800.5**  
&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**
    
### <a name="whats-new"></a>Nyheter

- Sårbarhetsidentifieringsförbättringar i Shellcode
- Bättre synlighet för försök att stjäl autentiseringsuppgifter
- Förbättringar av antivirusfunktionerna i Microsoft Defender Antivirus services
- Förbättrat stöd för ARM x64-egulering
- Åtgärd: EDR-blockeringsavisering finns kvar i hothistoriken efter att initial identifiering utförts i realtid

### <a name="known-issues"></a>Kända problem
Inga kända problem  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>Tidigare versionsuppdateringar: Endast teknisk uppgraderingssupport

När en ny paketversion har släppts begränsas stödet för de tidigare två versionerna till endast teknisk support. Versioner som är äldre än de som anges i det här avsnittet och tillhandahålls endast för teknisk uppgraderingssupport. 
<br/><br/>
<details>
<summary> November-2020 (plattform: 4.18.2011.6 | Motor: 1.1.17700.4)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.1854.0**  
&ensp;Utgiven: **3 december 2020**  
&ensp;Plattform: **4.18.2011.6**  
&ensp;Motor: **1.1.17700.4**  
&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**
    
### <a name="whats-new"></a>Nyheter

- Förbättrad [SmartScreen-status](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) för loggning

### <a name="known-issues"></a>Kända problem
Inga kända problem  
<br/>
</details><details>
<summary> Oktober-2020 (plattform: 4.18.2010.7 | Motor: 1.1.17600.5)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.327.7.0**  
&ensp;**Utgiven: 29 oktober 2020**  
&ensp;Plattform: **4.18.2010.7**  
&ensp;Motor: **1.1.17600.5**  
&ensp;Supportfas: **Säkerhets- och kritiska uppdateringar**
    
### <a name="whats-new"></a>Nyheter

- Nya beskrivningar av särskilda hotkategorier
- Förbättrade funktioner för emulerande
- Förbättrade funktioner för tillåtna/blockerade värdadresser
- Nytt alternativ i Defender CSP för att ignorera sammanslagning av undantag för lokala användare

### <a name="known-issues"></a>Kända problem

Inga kända problem  
<br/>
</details><details>
<summary> September-2020 (Plattform: 4.18.2009.7 | Motor: 1.1.17500.4)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.325.10.0**  
&ensp;**Utgiven: 01 oktober 2020**  
&ensp;Plattform: **4.18.2009.7**  
&ensp;Motor: **1.1.17500.4**  
&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**
    
### <a name="whats-new"></a>Nyheter

- Administratörsbehörighet krävs för att återställa filer i karantän
- XML-formaterade händelser stöds nu
- Stöd för CSP för att ignorera undantagskopplingar
- Nya hanteringsgränssnitt för:
   - UDP-kontroll
   - Nätverksskydd på Server 2019
   - Undantag för IP-adress i nätverksskydd
- Förbättrad insyn i TPM-mått
- Förbättrad vba-modulskanning för Office

### <a name="known-issues"></a>Kända problem

Inga kända problem  
<br/>
</details>
<details>
<summary> Augusti-2020 (plattform: 4.18.2008.9 | Motor: 1.1.17400.5)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.323.9.0**  
&ensp;Släppt: **27 augusti 2020**  
&ensp;Plattform: **4.18.2008.9**  
&ensp;Motor: **1.1.17400.5**  
&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**

### <a name="whats-new"></a>Nyheter

- Lägga till fler telemetrihändelser
- Förbättrad sökhändelsetelemetri
- Förbättrad övervakning av beteende för minnessökningar
- Förbättrad genomsökning av makroströmmar
- `AMRunningMode`Tillagd Get-MpComputerStatus PowerShell-cmdlet
- [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) ignoreras. Microsoft Defender Antivirus stängs automatiskt av när programmet upptäcker ett annat antivirusprogram.


### <a name="known-issues"></a>Kända problem
Inga kända problem  
<br/>
</details>

<details>
<summary> Juli–2020 (plattform: 4.18.2007.8 | Motor: 1.1.17300.4)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.321.30.0**  
&ensp;**Utgiven: 28 juli 2020**  
&ensp;Plattform: **4.18.2007.8**  
&ensp;Motor: **1.1.17300.4**  
&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**
    
### <a name="whats-new"></a>Nyheter

- Förbättrad telemetri för BITS
- Förbättrad validering av Authenticode-kodsigneringscertifikat

### <a name="known-issues"></a>Kända problem
Inga kända problem  
<br/>
</details>

<details>
<summary> Juni-2020 (plattform: 4.18.2006.10 | Motor: 1.1.17200.2)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.319.20.0**  
&ensp;**Utgiven: 22 juni 2020**  
&ensp;Plattform: **4.18.2006.10**  
&ensp;Motor: **1.1.17200.2**  
&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**
    
### <a name="whats-new"></a>Nyheter

- Möjlighet att ange [platsen för supportloggarna](./collect-diagnostic-data.md)
- Hoppa över en aggressiv uppslagssökning i passivt läge.
- Tillåt att Defender uppdaterar med anslutningar med datamätare
- Korrigerad prestandajustering när cachelagring är inaktiverat 
- Åtgärdad registerfråga 
- Fast genomsöknings slumpvisisering i ADMX

### <a name="known-issues"></a>Kända problem
Inga kända problem  
<br/>
</details>

<details>
<summary> Maj-2020 (plattform: 4.18.2005.4 | Motor: 1.1.17100.2)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.317.20.0**  
&ensp;**Utgiven: 26 maj 2020**  
&ensp;Plattform: **4.18.2005.4**  
&ensp;Motor: **1.1.17100.2**  
&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**
    
### <a name="whats-new"></a>Nyheter

- Förbättrad loggning för genomsökningshändelser
- Förbättrad kraschhantering i användarläge.
- Händelsespårning har lagts till för skydd mot manipulering
- Åtgärdat AMSI-exempel för inskickning
- Åtgärdat AMSI-molnblockering
- Installationslogg för säkerhetsuppdatering åtgärdad

### <a name="known-issues"></a>Kända problem
Inga kända problem  
<br/>
</details>

<details>
<summary> April 2020 (plattform: 4.18.2004.6 | Motor: 1.1.17000.2)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.315.12.0**  
&ensp;Utgiven: **30 april 2020**  
&ensp;Plattform: **4.18.2004.6**  
&ensp;Motor: **1.1.17000.2**  
&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**
    
### <a name="whats-new"></a>Nyheter
- WDfilterförbättringar
- Lägga till mer hanterbara händelsedata till händelser för minskning av attackytan
- Åtgärdad versionsinformation i diagnostikdata och WMI
- Åtgärdat felaktig plattformsversion i användargränssnittet efter plattformsuppdatering
- Dynamisk URL-information för skydd mot fillösa hot
- Sökfunktion för UEFI
- Utöka loggning för uppdateringar

### <a name="known-issues"></a>Kända problem
Inga kända problem  
<br/>
</details>

<details>
<summary> Mars-2020 (plattform: 4.18.2003.8 | Motor: 1.1.16900.2)</summary>

&ensp;Uppdateringsversion av säkerhetsinformation: **1.313.8.0**  
&ensp;Utgiven: **24 mars 2020**  
&ensp;Plattform: **4.18.2003.8**  
&ensp;Motor: **1.1.16900.4**  
&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**
    
### <a name="whats-new"></a>Nyheter

- Alternativet CPU-begränsning tillagt [i MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)
- Förbättra diagnostikfunktionerna
- minska timeout för säkerhetsintelligens (5 min)
- Utöka funktionen intern AMSI-motorlogg
- Förbättra meddelandet om processblockering
   
### <a name="known-issues"></a>Kända problem
[**Åtgärdat**] Microsoft Defender Antivirus hoppar över filer när du kör en genomsökning.

<br/>
</details>

<details>

<summary> Februari-2020 (plattform: - | Motor: 1.1.16800.2)</summary>
  

&ensp;Uppdateringsversion av säkerhetsinformation: **1.311.4.0**   
&ensp;**Utgiven: 25 februari 2020**  
&ensp;Plattform/klient: **-**  
&ensp;Motor: **1.1.16800.2**  
&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**
     
### <a name="whats-new"></a>Nyheter

  
### <a name="known-issues"></a>Kända problem
Inga kända problem
<br/>
</details>

<details>
<summary> Januari-2020 (plattform: 4.18.2001.10 | Motor: 1.1.16700.2)</summary>
  

Uppdateringsversion av säkerhetsinformation: **1.309.32.0**  
Utgiven: **30 januari 2020**  
Plattform/klient: **4.18.2001.10**  
Motor: **1.1.16700.2**  
&ensp;Supportfas: **Teknisk uppgraderingssupport (endast)**
     
### <a name="whats-new"></a>Nyheter

- Åtgärdat BSOD på WS2016 med Exchange
- Uppdateringar för supportplattformer när TMP omdirigeras till nätverkssökvägen
- Plattforms- och motorversioner läggs till [i WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- utöka uppdateringen av nödsignaturer [till passivt läge](./microsoft-defender-antivirus-compatibility.md)
- Åtgärda att 4.18.1911.3 hänger sig
   
### <a name="known-issues"></a>Kända problem

[**Åtgärdat**] enheter som använder [modernt vänteläge](/windows-hardware/design/device-experiences/modern-standby) kan uppleva att windows Defender-filterdrivrutinen hänger sig, vilket resulterar i en lucka i skyddet.  Påverkade datorer verkar för kunden inte ha uppdaterat till den senaste plattform för program mot skadlig programvara.  
<br/>
> [!IMPORTANT]
> Den här uppdateringen är:
> - krävs av RS1-enheter med lägre version av plattformen för att stödja SHA2.
> - har en omstartsflagga för system som har hängande problem.
> - återgiven i april 2020 och kommer inte att ersättas av nyare uppdateringar för att behålla framtida tillgänglighet.  
> - kategoriseras som en uppdatering på grund av omstartskravet; och
> - erbjuds endast med [Windows Update.](https://support.microsoft.com/help/4027667/windows-10-update)
<br/>
</details>

<details>
<summary> November-2019 (Plattform: 4.18.1911.3 | Motor: 1.1.16600.7)</summary>

Uppdateringsversion av säkerhetsinformation: **1.307.13.0**  
**Utgiven: 7 december 2019**  
Plattform: **4.18.1911.3**  
Motor: **1.1.17000.7**  
Supportfas: **Inget stöd**  
     
### <a name="whats-new"></a>Nyheter

- Åtgärdat MpCmdRun-spårningsnivå
- Åtgärdat WDFilter-versionsinformation
- Förbättra meddelanden (PUA)
- lägga till MRT-loggar i stödfiler
   
### <a name="known-issues"></a>Kända problem
När den här uppdateringen installeras behöver enheten hopppaketet 4.10.2001.10 för att kunna uppdatera till den senaste versionen av plattformen.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Support för Microsoft Defender Antivirus-plattformen
Plattforms- och motoruppdateringar tillhandahålls varje månad. Håll dig aktuell med de senaste plattformsuppdateringarna för att få fullständigt stöd. Vår supportstruktur är dynamisk och utvecklas till två faser beroende på tillgängligheten för den senaste versionen av plattformen:

- **Servicefas för säkerhets-** och kritiska uppdateringar – När du kör den senaste versionen av plattformen får du både säkerhets- och kritiska uppdateringar till plattformen för skydd mot skadlig programvara.
 
- **Fas för teknisk support (endast)** – När en ny plattformsversion har släppts kommer stödet för äldre versioner (N-2) att minska till teknisk support. Plattformsversioner äldre än N-2 stöds inte längre.*

\* Teknisk support kommer att fortsätta tillhandahållas för uppgraderingar från Windows 10-versionen (se Plattformsversion som ingår i [Windows 10-versioner)](#platform-version-included-with-windows-10-releases)till den senaste versionen av plattformen.

Under den tekniska supportfasen (endast) tillhandahålls kommersiellt rimliga supportärenden via Microsofts kundtjänst & Support och Microsofts hanterade supporterbjudanden (till exempel Premier-support). Om ett supportärende kräver eskalering till utveckling för vidare vägledning, kräver en uppdatering som inte är säkerhetsfri eller kräver en säkerhetsuppdatering, uppmanas kunderna att uppgradera till den senaste versionen av plattformen eller en mellanliggande uppdatering (*).

### <a name="platform-version-included-with-windows-10-releases"></a>Plattformsversion som ingår i Windows 10-versioner
Tabellen nedan innehåller microsoft Defender Antivirus-plattformen och motorversioner som levereras med de senaste Windows 10-versionerna:    

|Windows 10-version  |Plattformsversion  |Motorversion |Supportfas |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | Teknisk uppgraderingssupport (endast) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | Teknisk uppgraderingssupport (endast) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | Teknisk uppgraderingssupport (endast) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | Teknisk uppgraderingssupport (endast) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | Teknisk uppgraderingssupport (endast) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | Teknisk uppgraderingssupport (endast) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | Teknisk uppgraderingssupport (endast) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | Teknisk uppgraderingssupport (endast) |  

Information om versionen av Windows 10 finns i informationsbladet [om Windows livscykel.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>Uppdateringar för DISM (Deployment Image Servicing and Management)

Vi rekommenderar att du uppdaterar dina Windows 10-versioner (Enterprise-, Pro- och Home-utgåvor), Windows Server 2019 och Windows Server 2016 OS-installationsbilder med de senaste uppdateringarna för antivirus och program mot skadlig programvara. Genom att hålla os-installationsbilderna uppdaterade undviker du lucka i skyddet. 

Mer information finns i [Installationsbilder för Microsoft Defender-operativsystemet för Windows.](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)

<details>
<summary>1.1.2104.01</summary>

&ensp;Paketversion: **1.1.2104.01**    
&ensp;Plattformsversion: **4.18.2102.4**   
&ensp;Motorversion: **1.1.18000.5**  
&ensp;Signaturversion: **1.335.232.0**    
    
### <a name="fixes"></a>Korrigeringar
- Ingen

### <a name="additional-information"></a>Ytterligare information
- Ingen  
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;Paketversion: **1.1.2103.01**    
&ensp;Plattformsversion: **4.18.2101.9**   
&ensp;Motorversion: **1.1.17800.5**  
&ensp;Signaturversion: **1.331.2302.0**    
    
### <a name="fixes"></a>Korrigeringar
- Ingen

### <a name="additional-information"></a>Ytterligare information
- Ingen  
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;Paketversion: **1.1.2102.03**    
&ensp;Plattformsversion: **4.18.2011.6**   
&ensp;Motorversion: **1.1.17800.5**  
&ensp;Signaturversion: **1.331.174.0**    
    
### <a name="fixes"></a>Korrigeringar
- Ingen

### <a name="additional-information"></a>Ytterligare information
- Ingen  
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;Paketversion: **1.1.2101.02**    
&ensp;Plattformsversion: **4.18.2011.6**   
&ensp;Motorversion: **1.1.17700.4**  
&ensp;Signaturversion: **1.329.1796.0**    
    
### <a name="fixes"></a>Korrigeringar
- Ingen

### <a name="additional-information"></a>Ytterligare information
- Ingen  
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;Paketversion: **1.1.2012.01**    
&ensp;Plattformsversion: **4.18.2010.7**   
&ensp;Motorversion: **1.1.17600.5**  
&ensp;Signaturversion: **1.327.1991.0**    
    
### <a name="fixes"></a>Korrigeringar
- Ingen

### <a name="additional-information"></a>Ytterligare information
- Ingen  
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;Paketversion: **1.1.2011.02**    
&ensp;Plattformsversion: **4.18.2010.7**   
&ensp;Motorversion: **1.1.17600.5**  
&ensp;Signaturversion: **1.327.658.0**    
    
### <a name="fixes"></a>Korrigeringar
- Ingen

### <a name="additional-information"></a>Ytterligare information
- Uppdaterade Microsoft Defender Antivirus-signaturer  
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;Paketversion: **1.1.2011.01**    
&ensp;Plattformsversion: **4.18.2009.7**  
&ensp;Motorversion: **1.1.17600.5**  
&ensp;Signaturversion: **1.327.344.0**    
    
### <a name="fixes"></a>Korrigeringar
- Ingen

### <a name="additional-information"></a>Ytterligare information
- Ingen  
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;Paketversion: **1.1.2011.01**    
&ensp;Plattformsversion: **4.18.2008.9**   
&ensp;Motorversion: **1.1.17400.5**  
&ensp;Signaturversion: **1.327.2216.0**    
    
### <a name="fixes"></a>Korrigeringar
- Ingen

### <a name="additional-information"></a>Ytterligare information
- Lade till stöd för installationsbilder för Windows 10 RS1 eller senare.  
<br/>
</details>

## <a name="additional-resources"></a>Ytterligare resurser

| Artikel | Beskrivning  |
|:---|:---|
|[Installationsbilder för Microsoft Defender-uppdatering för Windows-operativsystemet](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Granska uppdateringspaket för program mot skadlig programvara för bilder av OS-installationen (WIM- och VHD-filer). Hämta installationsbilder för Microsoft Defender Antivirus för Windows 10 (Enterprise, Pro och Home), Windows Server 2019 och Windows Server 2016.  |
|[Hantera hur skyddsuppdateringar hämtas och tillämpas](manage-protection-updates-microsoft-defender-antivirus.md) | Skyddsuppdateringar kan skickas via många källor. |
|[Hantera när skyddsuppdateringar ska hämtas och tillämpas](manage-protection-update-schedule-microsoft-defender-antivirus.md) | Du kan schemalägga när skyddsuppdateringar ska hämtas. |
|[Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md) | Om en slutpunkt missar en uppdatering eller schemalagd genomsökning kan du tvinga fram en uppdatering eller genomsökning nästa gång en användare loggar in. |
|[Hantera händelsebaserade tvingade uppdateringar](manage-event-based-updates-microsoft-defender-antivirus.md) | Du kan ange att skyddsuppdateringar ska hämtas vid start eller efter vissa molnskyddshändelser. |
|[Hantera uppdateringar för mobila enheter och virtuella maskiner (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| Du kan ange inställningar, till exempel om uppdateringar ska göras på batterikraft, som är särskilt användbara för mobila enheter och virtuella datorer. |
