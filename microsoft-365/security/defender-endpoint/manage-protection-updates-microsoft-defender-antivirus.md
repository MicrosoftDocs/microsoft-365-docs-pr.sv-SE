---
title: Hantera hur och var Microsoft Defender Antivirus tar emot uppdateringar
description: Hantera reservordningen för hur Microsoft Defender Antivirus får skyddsuppdateringar.
keywords: uppdateringar, säkerhetsbaslinjer, skydd, reservordning, ADL, MMPC, UNC, sökväg, dela, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 77f3c4f478e2124010445bacfe2c10c5810ed480
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690996"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>Hantera källor för uppdateringar av Microsoft Defender AntivirusSkydd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

Det är viktigt att hålla antivirusskyddet uppdaterat. Det finns två komponenter för hantering av skyddsuppdateringar för Microsoft Defender Antivirus: 
- *Var* uppdateringarna hämtas från och 
- *När* uppdateringar laddas ned och tillämpas. 

I den här artikeln beskrivs hur du anger varifrån uppdateringar ska laddas ned (detta kallas även reservordningen). I Avsnittet Hantera uppdateringar för Microsoft Defender Antivirus och använda baslinjer finns en översikt över hur uppdateringarna fungerar och hur du konfigurerar andra aspekter av uppdateringar (till exempel [schemaläggningsuppdateringar).](manage-updates-baselines-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> Uppdateringar för Microsoft Defender Antivirus Security Intelligence levereras via Windows Update och från och med måndagen den 21 oktober 2019 är alla säkerhetsintelligensuppdateringar SHA-2-signerade exklusivt. Enheterna måste uppdateras med stöd för SHA-2 för att du ska kunna uppdatera säkerhetsintelligens. Mer information finns i Krav [för stöd för SHA-2-kodsignering för Windows och WSUS 2019.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)  


<a id="fallback-order"></a>

## <a name="fallback-order"></a>Reservorder

Vanligtvis konfigurerar du slutpunkter att individuellt ladda ned uppdateringar från en primär källa följt av andra källor i prioritetsordning, baserat på din nätverkskonfiguration. Uppdateringar hämtas från källor i den ordning du anger. Om en källa inte är tillgänglig används nästa källa i listan omedelbart.

När uppdateringar publiceras används en logik för att minimera uppdateringens storlek. I de flesta fall är det bara skillnaderna mellan den senaste uppdateringen och den uppdatering som är installerad (det här kallas för delta) på enheten laddas ned och tillämpas. Storleken på deltat beror emellertid på två huvudfaktorer:
- Ålder för den senaste uppdateringen på enheten. och 
- Den källa som används för att ladda ned och installera uppdateringar. 

Ju äldre uppdateringar på en slutpunkt, desto större blir nedladdningen. Men du måste också överväga nedladdningsfrekvens. Ett uppdateringsschema som ofta används kan leda till större nätverksanvändning, medan ett schema som inte blir så ofta kan leda till större filstorlekar per nedladdning. 

Det finns fem platser där du kan ange var en slutpunkt ska hämta uppdateringar: 

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows Server Update-tjänsten](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [Nätverksresurs](#unc-share)
- [Säkerhetsintelligensuppdateringar](https://www.microsoft.com/en-us/wdsi/defenderupdates) för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig kod (din policy och ditt register kan ha den i listan Microsoft Malware Protection Center (MMPC) säkerhetsinformation, dess tidigare namn.)

För att säkerställa den bästa skyddsnivån ger Microsoft Update snabba versioner, vilket innebär mindre nedladdningar ofta. Tjänsten Windows Server Update, Microsoft Endpoint Configuration Manager och Microsofts säkerhetsinformationsuppdateringar tillhandahåller mindre vanliga uppdateringar. Delta kan alltså vara större, vilket resulterar i större nedladdningar. 

> [!IMPORTANT]
> Om du har angett uppdateringar för [Microsofts](https://www.microsoft.com/security/portal/definitions/adl.aspx) säkerhetsinformationssida som reservkälla efter Windows Server Update Service eller Microsoft Update hämtas uppdateringar endast från säkerhetsintelligensuppdateringar när den aktuella uppdateringen anses vara in datera. (Som standard är det sju dagar i följd då uppdateringar från Windows Server Update-tjänsten eller Microsoft Update-tjänsterna inte kan installeras.
> Du kan dock [ange antalet dagar innan skyddet rapporteras som inställt.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)<p>
> Från och med måndagen den 21 oktober 2019 kommer säkerhetsintelligensuppdateringar att vara SHA-2-signerade exklusivt. Enheter måste uppdateras med stöd för SHA-2 för att få de senaste säkerhetsintelligensuppdateringarna. Mer information finns i Krav [för stöd för SHA-2-kodsignering för Windows och WSUS 2019.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)

Varje källa har vanliga scenarier som beror på hur nätverket är konfigurerat, utöver hur ofta de publicerar uppdateringar, enligt beskrivningen i följande tabell:

|Plats | Exempelscenario |
|---|---|
|Windows Server Update-tjänsten | Du använder Windows Server Update Service för att hantera uppdateringar för nätverket.|
|Microsoft Update | Du vill att dina slutpunkter ska ansluta direkt till Microsoft Update. Detta kan vara användbart för slutpunkter som oregelbundet ansluter till företagsnätverket eller om du inte använder Windows Server Update-tjänsten för att hantera dina uppdateringar.|
|Filresurs | Du har icke-Internetanslutna enheter (till exempel virtuella maskiner). Du kan använda den Internetanslutna VM-värden för att hämta uppdateringar till en nätverksresurs från vilken de virtuella maskinerna kan hämta uppdateringarna. Se [VDI-distributionsguiden](deployment-vdi-microsoft-defender-antivirus.md) för hur filresurser kan användas i VDI-miljöer (Virtual Desktop Infrastructure).|
|Microsoft Endpoint Manager | Du använder Microsoft Endpoint Manager för att uppdatera slutpunkterna.|
|Säkerhetsintelligensuppdateringar för Microsoft Defender Antivirus och andra Microsoft-program mot skadlig programvara (tidigare kallad MMPC) |[Kontrollera att dina enheter har uppdaterats med stöd för SHA-2.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus) Microsoft Defender Antivirus Security intelligence-uppdateringar levereras via Windows Update och från och med måndagen den 21 oktober 2019 är säkerhetsintelligensuppdateringar SHA-2 signerad exklusivt. <br/>Ladda ned de senaste skyddsuppdateringarna på grund av en nyligen genomförd distribution eller för att tillhandahålla en stark, grundläggande bild för [VDI-distribution.](deployment-vdi-microsoft-defender-antivirus.md) Det här alternativet bör i allmänhet bara användas som en slutgiltig reservkälla, inte den primära källan. Den används endast om det inte går att hämta uppdateringar från Windows Server Update Service eller Microsoft Update [under ett angivet antal dagar.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)|

Du kan hantera i vilken ordning uppdateringskällor används med Grupprincip, Microsoft Endpoint Configuration Manager, PowerShell-cmdlets och WMI.

> [!IMPORTANT]
> Om du anger Windows Server Update-tjänsten som en nedladdningsplats måste du godkänna uppdateringarna, oavsett vilket hanteringsverktyg du använder för att ange platsen. Du kan konfigurera en regel för automatiskt godkännande med Windows Server Update-tjänsten, vilket kan vara användbart när uppdateringar kommer minst en gång om dagen. Mer information finns i Synkronisera [uppdateringar av slutpunktsskydd i fristående Windows Server Update Service.](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)

Procedurerna i den här artikeln beskriver först hur du  anger ordningen och sedan hur du ställer in alternativet Filresurs om du har aktiverat den.

## <a name="use-group-policy-to-manage-the-update-location"></a>Hantera uppdateringsplatsen med grupprinciper

1. På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

3. Klicka **på Principer** och sedan på Administrativa **mallar.**

4. Expandera trädet till **Windows-komponenter > Windows Defender > och** konfigurera följande inställningar:

   1.  Dubbelklicka på inställningen Definiera **ordningen på källor för nedladdning av säkerhetsintelligensuppdateringar** och ange alternativet **Aktiverad**.

   2.  Ange källordningen, avgränsad med ett enda rör, till exempel: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` , som på följande skärmbild.

   ![Skärmbild av grupprincipinställning med källordningen](images/defender/wdav-order-update-sources.png)

   3. Klicka på **OK**. Då anges ordningen för skydd av uppdateringskällor.

   4. Dubbelklicka på inställningen Definiera **filresurser för hämtning av säkerhetsintelligensuppdateringar** och ange alternativet **Aktiverad.**

   5. Ange filresurskällan. Om du har flera källor anger du varje källa i den ordning de ska användas, avgränsade med en enda rörledning. Använd [standard-UNC-notation](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) för att beteckna sökvägen, till exempel: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .  Om du inte anger några sökvägar hoppas den här källan över när den virtuella maskinerna laddar ned uppdateringar.

   6. Klicka på **OK**. Då anges ordningen på filresurser när källan refereras i grupprincipinställningen **Definiera ordningen** på källor....

> [!NOTE]
> För Windows 10, version 1703 upp till och med 1809 är principsökvägen **Windows Components > Microsoft Defender Antivirus > Signature Updates** For Windows 10, version 1903. Principsökvägen är Windows Components > Microsoft Defender Antivirus > Security Intelligence **Updates**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>Hantera uppdateringsplatsen med Konfigurationshanteraren

Mer [information om konfiguration av](/configmgr/protect/deploy-use/endpoint-definition-updates) Microsoft Endpoint Manager (current branch) finns i Konfigurera säkerhetsintelligensuppdateringar för Endpoint Protection.


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>Använda PowerShell-cmdlets för att hantera uppdateringsplatsen

Använd följande PowerShell-cmdlets för att ange uppdateringsordningen.

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
Mer information finns i följande artiklar:
- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [Använda PowerShell-cmdlets för att konfigurera och köra Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender-cmdlets](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>Använd WMI (Windows Management Instruction) för att hantera uppdateringsplatsen

Använd [ **metoden** Set för **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) för följande egenskaper:

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

Mer information finns i följande artiklar:
- [API:er för Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>Använda MDM (Mobile Device Management) för att hantera uppdateringsplatsen

Mer information om konfiguration av MDM finns i [Policy CSP – Defender/SignatureUpdateFallbackOrder.](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder)

## <a name="what-if-were-using-a-third-party-vendor"></a>Vad händer om vi använder en tredjepartsleverantör?

I den här artikeln beskrivs hur du konfigurerar och hanterar uppdateringar för Microsoft Defender Antivirus. Tredjepartsleverantörer kan emellertid användas för att utföra de här uppgifterna. 

Anta till exempel att Contoso har anställt Fabrikam för att hantera deras säkerhetslösning, där Microsoft Defender Antivirus ingår. Fabrikam använder [normalt Windows Management Instrumentation-,](./use-wmi-microsoft-defender-antivirus.md) [PowerShell-cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md)eller [Windows-kommandorad](./command-line-arguments-microsoft-defender-antivirus.md) för att distribuera korrigeringar och uppdateringar. 

> [!NOTE]
> Microsoft testar inte tredjepartslösningar för att hantera Microsoft Defender Antivirus.

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a>Skapa en UNC-delning för säkerhetsintelligensuppdateringar

Konfigurera en nätverksresurs (UNC/mappad enhet) för att hämta säkerhetsintelligensuppdateringar från MMPC-webbplatsen med hjälp av en schemalagd aktivitet.

1. Skapa en mapp där du vill spara skriptet i det system där du vill etablera resursen och ladda ned uppdateringarna.
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. Skapa den mapp som du ska spara signaturuppdateringarna i.
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. Ladda ned PowerShell-skriptet [från www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).

4. Klicka **på Manuell nedladdning.**

5. Klicka **på Ladda ned den obearbetade nupkg-filen**.

6. Extrahera filen.

7. Kopiera filen eller SignatureDownloadCustomTask.ps1 den mapp som du tidigare skapade, C:\Tool\PS-Scripts\ .

8. Använd kommandoraden för att konfigurera den schemalagda aktiviteten.
    > [!NOTE]
    > Det finns två typer av uppdateringar: fullständiga och delta.
   - För x64 delta:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - För x64 fullt:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - För x86 delta:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - För x86 fullt:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

    > [!NOTE]
    > När de schemalagda aktiviteterna har skapats hittar du dem i Schemaläggaren under Microsoft\Windows\Windows Defender
9. Kör varje aktivitet manuellt och kontrollera att du har data (mpam-d.exe, mpam-fe.exe och nis_full.exe) i följande mappar (du kanske har valt olika platser):

   - C:\Temp\TempSigs\x86
   - C:\Temp\TempSigs\x64

   Om den schemalagda aktiviteten misslyckas kör du följande kommandon:

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86″
    ```
    > [!NOTE]
    > Problem kan också bero på körningsprincipen.
    
10. Skapa en delning som pekar på C:\Temp\TempSigs (t.ex. \\ server\uppdateringar).
    > [!NOTE]
    > Som minst måste autentiserade användare ha läsbehörighet.
11. Ställ in delningsplatsen i principen på delningsplatsen.

    > [!NOTE]
    > Lägg inte till mappen x64 (eller x86) i sökvägen. Processen mpcmdrun.exe lägger till den automatiskt.

## <a name="related-articles"></a>Relaterade artiklar

- [Distribuera Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för slutpunkter som är in uppdaterade](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Hantera händelsebaserade tvingade uppdateringar](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Hantera uppdateringar för mobila enheter och virtuella maskiner](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)