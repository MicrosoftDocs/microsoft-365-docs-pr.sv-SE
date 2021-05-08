---
title: Microsoft Defender Antivirus på Windows Server
description: Läs om hur du aktiverar och konfigurerar Microsoft Defender Antivirus i Windows Server 2016 och Windows Server 2019.
keywords: windows defender, server, s defender, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269498"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender Antivirus på Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus är tillgängligt på följande versioner av Windows Server:
- Windows Server 2019
- Windows Server, version 1803 eller senare
- Windows Server 2016. 

I vissa fall kallas Microsoft Defender Antivirus för *Endpoint Protection*. Protectionmotorn är dock densamma. Även om funktionerna, konfigurationen och hanteringen i stort sett är desamma för Microsoft Defender Antivirus i [Windows 10](microsoft-defender-antivirus-in-windows-10.md)finns det några viktiga skillnader på Windows Server:

- I Windows Server [tillämpas automatiska undantag](configure-server-exclusions-microsoft-defender-antivirus.md) baserat på den definierade serverrollen.
 
- Om du kör en lösning som inte är en Microsoft-antivirus-/antimalwarelösning på Windows Server förs inte Microsoft Defender Antivirus automatiskt in i antingen passivt läge eller inaktiverat läge. Du kan dock ställa in Microsoft Defender Antivirus på passivt eller inaktiverat läge manuellt.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Konfigurera Microsoft Defender Antivirus på Windows Server

Det finns flera steg i processen för att konfigurera och köra Microsoft Defender Antivirus på en serverplattform:

1. [Aktivera gränssnittet.](#enable-the-user-interface-on-windows-server)
2. [Installera Microsoft Defender Antivirus.](#install-microsoft-defender-antivirus-on-windows-server)
3. [Kontrollera att Microsoft Defender Antivirus körs](#verify-microsoft-defender-antivirus-is-running).
4. [Uppdatera säkerhetsinformation för program mot skadlig programvara](#update-antimalware-security-intelligence).
5. (Vid behov) [Skicka exempel](#submit-samples).
6. (Vid behov) [Konfigurera automatiska undantag](#configure-automatic-exclusions).
7. (Endast om det behövs) [Ställ in Microsoft Defender Antivirus på passivt läge](#need-to-set-microsoft-defender-antivirus-to-passive-mode).

## <a name="enable-the-user-interface-on-windows-server"></a>Aktivera användargränssnittet på Windows Server

Som standard installeras och fungerar Microsoft Defender Antivirus på Windows Server. Ibland installeras användargränssnittet som standard, men det behövs inte. Du kan använda PowerShell, grupprinciper eller andra metoder för att hantera Microsoft Defender Antivirus. 

Om GUI:t inte är installerat på servern och du  vill installera det, antingen guiden Lägg till roller och funktioner eller PowerShell-cmdlets.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Aktivera GUI:t med guiden Lägg till roller och funktioner

1. Se [Installera roller, rolltjänster och funktioner med hjälp](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)av guiden Lägg till roller och funktioner och använd guiden Lägg till roller och **funktioner.**

2. När du kommer till **steget Funktioner** i guiden väljer du alternativet GUI för Windows Defender under Windows **Defender-funktioner.** 

   I Windows Server 2016 ser guiden **Lägg till roller och funktioner** ut så här:

   ![Guiden Lägg till roller och funktioner med guid för Windows Defender-alternativet](images/server-add-gui.png)

   I Windows Server 2019 påminner **guiden Lägg till roller och funktioner** om liknande.

### <a name="turn-on-the-gui-using-powershell"></a>Aktivera GUI:t med PowerShell

Följande PowerShell-cmdlet aktiverar gränssnittet: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Installera Microsoft Defender Antivirus på Windows Server

Om du behöver installera eller installera om Microsoft Defender Antivirus på Windows Server kan du göra det med hjälp av guiden Lägg till **roller** och funktioner eller PowerShell.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>Använd guiden Lägg till roller och funktioner för att installera Microsoft Defender Antivirus

1. Läs den [här artikeln](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)och använd guiden Lägg till roller **och funktioner.**

2. När du kommer till **steget Funktioner** i guiden väljer du alternativet Microsoft Defender Antivirus. Välj även **alternativet GUI för Windows Defender.**

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>Använda PowerShell för att installera Microsoft Defender Antivirus

Om du vill använda PowerShell för att installera Microsoft Defender Antivirus kör du följande cmdlet:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Händelsemeddelanden för den antimalware-motor som ingår i Microsoft Defender Antivirus finns i [Microsoft Defender AV-händelser.](troubleshoot-microsoft-defender-antivirus.md)


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Kontrollera att Microsoft Defender Antivirus körs

När Du har installerat Microsoft Defender Antivirus är nästa steg att verifiera att det körs. Kör följande PowerShell-cmdlet på Windows Server-slutpunkten:

```PowerShell
Get-Service -Name windefend
```

Kontrollera att brandväggsskyddet är aktiverat genom att köra följande PowerShell-cmdlet:

```PowerShell 
Get-Service -Name mpssvc
```

Som ett alternativ till PowerShell kan du använda Kommandotolken för att verifiera att Microsoft Defender Antivirus körs. Det gör du genom att köra följande kommando från en kommandotolk: 

```console
sc query Windefend
```

Kommandot `sc query` returnerar information om Microsoft Defender Antivirus-tjänsten. När Microsoft Defender Antivirus körs visas `STATE` `RUNNING` värdet.

## <a name="update-antimalware-security-intelligence"></a>Uppdatera säkerhetsinformation för program mot skadlig programvara 

För att få uppdaterad säkerhetsinformation för program mot skadlig programvara måste du ha Windows Update-tjänsten igång. Om du använder en uppdateringshanteringstjänst, t.ex. Windows Server Update Services (WSUS), ser du till att uppdateringar för Microsoft Defender Antivirus Security Intelligence är godkända för de datorer du hanterar.

Som standard laddar inte Windows Update ned och installerar uppdateringar automatiskt på Windows Server 2019 eller Windows Server 2016. Du kan ändra den här konfigurationen på något av följande sätt:


|Metod  |Beskrivning  |
|---------|---------|
|**Windows Update** på Kontrollpanelen     |- **Om du installerar uppdateringar** installeras alla uppdateringar automatiskt, inklusive Windows Defender Säkerhetsintelligensuppdateringar. <br/>- **Ladda ned uppdateringar men låt mig välja** om jag vill installera dem så att Windows Defender kan ladda ned och installera säkerhetsintelligensuppdateringar automatiskt, men andra uppdateringar installeras inte automatiskt.       |
|**Grupprincip**     | Du kan konfigurera och hantera Windows Update med hjälp av inställningarna i Grupprincip på följande sätt: **Administrativa mallar\Windows-komponenter\Windows Update\Konfigurera automatiska uppdateringar**         |
|Registernyckeln **AUOptions**     |Med följande två värden kan Windows Update ladda ned och installera säkerhetsintelligensuppdateringar automatiskt: <br/>- **4**  -  **Installera uppdateringar automatiskt.** Det här värdet leder till att alla uppdateringar installeras automatiskt, inklusive Windows Defender Säkerhetsintelligensuppdateringar. <br/>- **3**  -  **Ladda ned uppdateringar men låt mig välja om jag vill installera dem**.  Med det här värdet kan Windows Defender ladda ned och installera Säkerhetsintelligensuppdateringar automatiskt, men andra uppdateringar installeras inte automatiskt.         |

För att säkerställa att skyddet mot skadlig programvara bibehålls rekommenderar vi att du aktiverar följande tjänster:

- Windows felrapporteringstjänst

- Windows Update-tjänst

I följande tabell visas tjänsterna för Microsoft Defender Antivirus och de beroende tjänsterna.

|Tjänstnamn|Filplats|Beskrivning|
|--------|---------|--------|
|Windows Defender-tjänsten (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Det här är den huvudsakliga Microsoft Defender Antivirus-tjänsten som måste köras hela tiden.|
|Windows-felrapporteringstjänst (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Den här tjänsten skickar felrapporter tillbaka till Microsoft.|
|Windows Defender-brandväggen (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|Vi rekommenderar att du lämnar windows Defender-brandväggstjänsten aktiverad.|
|Windows Update (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windows Update krävs för att få säkerhetsintelligensuppdateringar och uppdateringar av program mot skadlig programvara|

## <a name="submit-samples"></a>Skicka exempel

Exempel på inskickning gör att Microsoft kan samla in exempel på potentiellt skadlig programvara. För att ge fortsatt och uppdaterat skydd använder Microsoft forskare dessa exempel för att analysera misstänkta aktiviteter och skapa uppdaterade säkerhetsinformation mot skadlig kod. Vi samlar in körbara programfiler, till exempel .exe filer och .dll filer. Vi samlar inte in filer som innehåller personuppgifter som Microsoft Word-dokument och PDF-filer.

### <a name="submit-a-file"></a>Skicka en fil

1. Läs [inskickingsguiden.](/windows/security/threat-protection/intelligence/submission-guide)

2. Besök [exempelportalen för inskicking](https://www.microsoft.com/wdsi/filesubmission)och skicka filen.


### <a name="enable-automatic-sample-submission"></a>Aktivera automatisk exempelinskickning

Om du vill aktivera automatisk exempelinskickning startar du en Windows PowerShell-konsol som administratör och anger värdedata för **SubmitSamplesConsent** enligt någon av följande inställningar:

|Inställning  |Beskrivning  |
|---------|---------|
|**0**  -  **Fråga alltid**     |I antivirustjänsten Microsoft Defender uppmanas du att bekräfta inskickningen av alla nödvändiga filer. Det här är standardinställningen för Microsoft Defender Antivirus, men rekommenderas inte för installationer på Windows Server 2016 eller 2019 utan guid.         |
|**1**   -  **Skicka säkra exempel automatiskt**     |Antivirustjänsten Microsoft Defender skickar alla filer som markerats som "säkra" och frågar efter resten av filerna.         |
|**2**  -  **Skicka aldrig**      |Microsoft Defender Antivirus-tjänsten uppmanas inte och skickar inga filer.         |
|**3**  -  **Skicka alla exempel automatiskt**     |Antivirustjänsten Microsoft Defender skickar alla filer utan en uppmaning om att bekräfta.         |

## <a name="configure-automatic-exclusions"></a>Konfigurera automatiska undantag

För att säkerställa säkerhet och prestanda läggs vissa undantag till automatiskt utifrån de roller och funktioner som du installerar när du använder Microsoft Defender Antivirus på Windows Server 2016 eller 2019.

Se [Konfigurera undantag i Microsoft Defender Antivirus på Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md) 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>Behöver du ställa in Microsoft Defender Antivirus på passiv form?

Om du använder ett annat antivirusprogram än Microsoft som din primära antiviruslösning på Windows Server måste du ställa in Microsoft Defender Antivirus på passivt läge eller inaktiverat läge.

- På Windows Server, version 1803 eller senare, eller Windows Server 2019, kan du ställa in Microsoft Defender Antivirus på passivt läge.  

- I Windows Server 2016 stöds inte Microsoft Defender Antivirus tillsammans med en produkt som inte är en antivirus-/antimalware-produkt från Microsoft. I sådana fall måste du ställa in att Microsoft Defender Antivirus ska inaktiveras.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a>Ställ in Microsoft Defender Antivirus på passivt läge med PowerShell

Om du använder Windows Server, version 1803 eller Windows Server 2019 kan du ställa in Microsoft Defender Antivirus på passivt läge med hjälp av följande PowerShell-cmdlet:

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a>Ställ in Microsoft Defender Antivirus på passivt läge med grupprincip

PROCEDUR KRÄVS

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Ställ in Microsoft Defender Antivirus på passivt läge med hjälp av en registernyckel

Om du använder Windows Server, version 1803 eller Windows Server 2019 kan du ställa in Microsoft Defender Antivirus på passiv form genom att ange följande registernyckel:
- Sökväg: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Namn: `ForceDefenderPassiveMode`
- Typ: `REG_DWORD`
- Värde: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Inaktivera Microsoft Defender Antivirus med hjälp av guiden Ta bort roller och funktioner

1. Se [Installera eller avinstallera roller, rolltjänster eller funktioner och](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)använd guiden Ta bort roller och **funktioner.** 

2. När du kommer till **steget Funktioner** i guiden avmarkerar du alternativet **Windows Defender-funktioner.** 

    Om du tar **bort Windows Defender** för sig själv under avsnittet Om Windows **Defender-funktioner** uppmanas du att ta bort gränssnittsalternativet GUI för **Windows Defender.** 
    
    Microsoft Defender Antivirus körs fortfarande normalt utan användargränssnittet, men användargränssnittet kan inte aktiveras om du inaktiverar **Windows Defender-huvudfunktionen.**

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Inaktivera användargränssnittet i Microsoft Defender Antivirus med PowerShell

Om du vill inaktivera Microsoft Defender Antivirus GUI använder du följande PowerShell-cmdlet:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>Använder du Windows Server 2016?

Om du använder Windows Server 2016 och en antimalware/antivirusprodukt från tredje part som inte erbjuds eller utvecklas av Microsoft, måste du inaktivera/avinstallera Microsoft Defender Antivirus. 

> [!NOTE]
> Du kan inte avinstallera Windows-säkerhetsappen, men du kan inaktivera gränssnittet med hjälp av de här instruktionerna.

Följande PowerShell-cmdlet avinstallerar Microsoft Defender Antivirus på Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

Om du vill inaktivera Microsoft Defender Antivirus i Windows Server 2016 använder du följande PowerShell-cmdlet:

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>Se även

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Kompatibilitet med Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md)
