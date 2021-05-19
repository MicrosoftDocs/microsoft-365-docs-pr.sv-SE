---
title: Microsoft Defender Antivirus på Windows Server
description: Lär dig hur du aktiverar och konfigurerar Microsoft Defender Antivirus på Windows Server 2016 och Windows Server 2019.
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
ms.date: 05/13/2021
ms.openlocfilehash: 1a1083d15698eb5bbdf2f6080b152b6f326c689a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539281"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender Antivirus på Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus tillgänglig på följande versioner av Windows Server:
- Windows Server 2019
- Windows Server, version 1803 eller senare
- Windows Server 2016. 

I vissa fall kallas Microsoft Defender Antivirus kallas för *Endpoint Protection*; Protectionmotorn är dock densamma. Även om funktionerna, konfigurationen och hanteringen till stor del är samma för Microsoft Defender Antivirus på [Windows 10](microsoft-defender-antivirus-in-windows-10.md)finns det några viktiga skillnader på Windows Server:

- På Windows Server [tillämpas automatiska undantag](configure-server-exclusions-microsoft-defender-antivirus.md) baserat på din definierade serverroll.
 
- På Windows Server och du kör en lösning som inte är ett Microsoft-antivirusprogram eller ett program mot skadlig programvara Microsoft Defender Antivirus inte antingen passivt läge eller inaktiverat läge automatiskt. Du kan dock manuellt Microsoft Defender Antivirus passivt eller inaktiverat läge.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Konfigurera Microsoft Defender Antivirus på Windows Server

Processen för att konfigurera och köra Microsoft Defender Antivirus på en serverplattform omfattar flera steg:

1. [Aktivera gränssnittet.](#enable-the-user-interface-on-windows-server)
2. [Installera Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).
3. [Kontrollera Microsoft Defender Antivirus är igång.](#verify-microsoft-defender-antivirus-is-running)
4. [Uppdatera säkerhetsinformation för program mot skadlig programvara](#update-antimalware-security-intelligence).
5. (Vid behov) [Skicka exempel](#submit-samples).
6. (Vid behov) [Konfigurera automatiska undantag](#configure-automatic-exclusions).
7. (Endast om det behövs) [Ställ Microsoft Defender Antivirus till passivt läge](#need-to-set-microsoft-defender-antivirus-to-passive-mode).

## <a name="enable-the-user-interface-on-windows-server"></a>Aktivera användargränssnittet på Windows Server

Som standard är Microsoft Defender Antivirus installerad och fungerar på Windows Server. Ibland installeras användargränssnittet som standard, men det behövs inte. Du kan använda PowerShell, grupprinciper eller andra metoder för att hantera Microsoft Defender Antivirus. 

Om GUI:t inte är installerat på servern och du  vill installera det, antingen guiden Lägg till roller och funktioner eller PowerShell-cmdlets.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Aktivera GUI:t med guiden Lägg till roller och funktioner

1. Se [Installera roller, rolltjänster och funktioner med hjälp](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)av guiden Lägg till roller och funktioner och använd guiden Lägg till roller och **funktioner.**

2. När du kommer till **steget Funktioner** i guiden går du **Windows Defender** under Funktioner och väljer alternativet GUI **för Windows Defender** gränssnitt.

   I Windows Server 2016 ser guiden **Lägg till roller och funktioner** ut så här:

   ![Guiden Lägg till roller och funktioner med guid för Windows Defender alternativ](images/server-add-gui.png)

   I Windows Server 2019 påminner **guiden Lägg till roller och funktioner** om liknande.

### <a name="turn-on-the-gui-using-powershell"></a>Aktivera GUI:t med PowerShell

Följande PowerShell-cmdlet aktiverar gränssnittet: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Installera Microsoft Defender Antivirus på Windows Server

Om du behöver installera eller installera Microsoft Defender Antivirus på Windows Server kan du göra det med hjälp av guiden Lägg till roller **och** funktioner eller PowerShell.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>Använd guiden Lägg till roller och funktioner för att installera Microsoft Defender Antivirus

1. Läs den [här artikeln](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)och använd guiden Lägg till roller **och funktioner.**

2. När du kommer till **steget Funktioner** i guiden väljer du Microsoft Defender Antivirus funktioner. Välj även **guid för Windows Defender guidning.**

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>Använd PowerShell för att installera Microsoft Defender Antivirus

Om du vill använda PowerShell för Microsoft Defender Antivirus kör du följande cmdlet:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

Händelsemeddelanden för den programskyddsmotor som ingår i Microsoft Defender Antivirus finns i [Microsoft Defender AV-händelser.](troubleshoot-microsoft-defender-antivirus.md)


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Kontrollera Microsoft Defender Antivirus körs

När Microsoft Defender Antivirus har installerats är nästa steg att verifiera att den körs. Kör följande PowerShell-cmdlet på din Windows Server-slutpunkt:

```PowerShell
Get-Service -Name windefend
```

Kontrollera att brandväggsskyddet är aktiverat genom att köra följande PowerShell-cmdlet:

```PowerShell 
Get-Service -Name mpssvc
```

Som ett alternativ till PowerShell kan du använda Kommandotolken för att verifiera Microsoft Defender Antivirus körs. Det gör du genom att köra följande kommando från en kommandotolk: 

```console
sc query Windefend
```

Kommandot `sc query` returnerar information om Microsoft Defender Antivirus tjänst. När Microsoft Defender Antivirus körs visas `STATE` värdet `RUNNING` .

## <a name="update-antimalware-security-intelligence"></a>Uppdatera säkerhetsinformation för program mot skadlig programvara 

Om du vill ha uppdaterad säkerhetsinformation för program mot skadlig programvara måste Windows uppdatera tjänsten vara igång. Om du använder en uppdateringshanteringstjänst, till exempel Windows Server Update Services (WSUS), ser du till att uppdateringar för Microsoft Defender Antivirus Säkerhetsinformation har godkänts för de datorer du hanterar.

Som standard laddar Windows inte ned och installerar uppdateringar automatiskt på Windows Server 2019 eller Windows Server 2016. Du kan ändra den här konfigurationen på något av följande sätt:


|Metod  |Beskrivning  |
|---------|---------|
|**Windows på** Kontrollpanelen     | **Om du installerar uppdateringar** installeras alla uppdateringar automatiskt, även Windows Defender säkerhetsintelligensuppdateringar. <p>**Ladda ned uppdateringar men låt mig välja** om de ska installeras så att Windows Defender kan ladda ned och installera säkerhetsintelligensuppdateringar automatiskt, men andra uppdateringar installeras inte automatiskt.       |
|**Grupprincip**     | Du kan konfigurera och hantera Windows-uppdatering med hjälp av inställningarna i Grupprincip på följande sökväg: **Administrativa mallar\Windows Components\Windows Update\Configure Automatic Updates**         |
|Registernyckeln **AUOptions**     | Med följande två värden kan Windows att automatiskt ladda ned och installera säkerhetsintelligensuppdateringar: <p>**4**  -  **Installera uppdateringar automatiskt.** Det här värdet leder till att alla uppdateringar installeras automatiskt, Windows Defender säkerhetsintelligensuppdateringar. <p>**3**  -  **Ladda ned uppdateringar men låt mig välja om jag vill installera dem**.  Med det här Windows Defender du ladda ned och installera Säkerhetsintelligensuppdateringar automatiskt, men andra uppdateringar installeras inte automatiskt.         |

För att säkerställa att skyddet mot skadlig programvara bibehålls rekommenderar vi att du aktiverar följande tjänster:

- Windows Felrapportering tjänst

- Windows Uppdatera tjänst

I följande tabell visas tjänsterna för Microsoft Defender Antivirus och de beroende tjänsterna.

|Tjänstnamn|Filplats|Beskrivning|
|--------|---------|--------|
|Windows Defender Tjänst (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Det här är Microsoft Defender Antivirus tjänst som alltid måste köras.|
|Windows Felrapportering Tjänst (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Den här tjänsten skickar felrapporter tillbaka till Microsoft.|
|Windows Defender-brandväggen (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|Vi rekommenderar att Windows Defender-brandväggen tjänsten är aktiverad.|
|Windows Uppdatering (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windows Uppdatering krävs för att få säkerhetsintelligensuppdateringar och uppdateringar av program mot skadlig programvara|

## <a name="submit-samples"></a>Skicka exempel

Exempel på inskickning gör att Microsoft kan samla in exempel på potentiellt skadlig programvara. För att ge fortsatt och uppdaterat skydd använder Microsoft forskare dessa exempel för att analysera misstänkta aktiviteter och skapa uppdaterade säkerhetsinformation mot skadlig kod. Vi samlar in körbara programfiler, till exempel .exe filer och .dll filer. Vi samlar inte in filer som innehåller personuppgifter, t.ex. Microsoft Word dokument och PDF-filer.

### <a name="submit-a-file"></a>Skicka en fil

1. Läs [inskickingsguiden.](/windows/security/threat-protection/intelligence/submission-guide)

2. Besök [exempelportalen för inskicking](https://www.microsoft.com/wdsi/filesubmission)och skicka filen.


### <a name="enable-automatic-sample-submission"></a>Aktivera automatisk exempelinskickning

Om du vill aktivera automatisk exempelinskickning startar du en Windows PowerShell konsol som administratör och anger värdedata för **SubmitSamplesConsent** enligt någon av följande inställningar:

|Inställning  |Beskrivning  |
|---------|---------|
|**0**  -  **Fråga alltid**     |I Microsoft Defender Antivirus uppmanas du att bekräfta överföringen av alla nödvändiga filer. Det här är standardinställningen för Microsoft Defender Antivirus men rekommenderas inte för installationer på Windows Server 2016 eller 2019 utan guid.         |
|**1**   -  **Skicka säkra exempel automatiskt**     |I Microsoft Defender Antivirus skickar alla filer som markerats som "säkra" och uppmanar dig att ange resten av filerna.         |
|**2**  -  **Skicka aldrig**      |Tjänsten Microsoft Defender Antivirus fråga och skickar inga filer.         |
|**3**  -  **Skicka alla exempel automatiskt**     |Den Microsoft Defender Antivirus skickar alla filer utan att du uppmanas att bekräfta.         |

## <a name="configure-automatic-exclusions"></a>Konfigurera automatiska undantag

För att säkerställa säkerhet och prestanda läggs vissa undantag till automatiskt baserat på de roller och funktioner som du installerar när du använder Microsoft Defender Antivirus på Windows Server 2016 eller 2019.

Se [Konfigurera undantag i Microsoft Defender Antivirus på Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md) 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>Behöver du ställa Microsoft Defender Antivirus till passivt läge?

Om du använder ett annat antivirusprogram än Microsoft som din primära antiviruslösning på Windows Server, måste du ställa Microsoft Defender Antivirus till passivt läge eller inaktiverat läge.

- I Windows Server, version 1803 eller senare, eller Windows Server 2019, kan du Microsoft Defender Antivirus passivt läge.  

- På Windows Server 2016 stöds Microsoft Defender Antivirus inte tillsammans med en produkt som inte är ett Microsoft-antivirusprogram eller en antimalware-produkt. I sådana fall måste du Microsoft Defender Antivirus in i inaktivt läge.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Ställ Microsoft Defender Antivirus till passivt läge med hjälp av en registernyckel

Om du använder Windows Server, version 1803 eller Windows Server 2019 kan du ställa in Microsoft Defender Antivirus till passivt läge genom att ange följande registernyckel:
- Sökväg: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Namn: `ForceDefenderPassiveMode`
- Typ: `REG_DWORD`
- Värde: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Inaktivera Microsoft Defender Antivirus med hjälp av guiden Ta bort roller och funktioner

1. Se [Installera eller avinstallera roller, rolltjänster eller funktioner och](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)använd guiden Ta bort roller och **funktioner.** 

2. När du kommer till **steget Funktioner** i guiden avmarkerar du Windows Defender **Funktioner.** 

    Om du **rensar Windows Defender** för sig själv **under avsnittet Windows Defender-funktioner** uppmanas du att ta bort gränssnittsalternativet GUI **för Windows Defender.** 
    
    Microsoft Defender Antivirus körs fortfarande normalt utan användargränssnittet, men användargränssnittet kan inte aktiveras om du inaktiverar **Windows Defender** huvudfunktionen.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Stänga av Microsoft Defender Antivirus användargränssnittet med PowerShell

Om du vill inaktivera Microsoft Defender Antivirus GUI använder du följande PowerShell-cmdlet:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>Använder du Windows Server 2016?

Om du använder Windows Server 2016 och en antimalware/antivirusprodukt från tredje part som inte erbjuds eller utvecklas av Microsoft, måste du inaktivera/avinstallera Microsoft Defender Antivirus. 

> [!NOTE]
> Du kan inte avinstallera Windows-säkerhet-appen, men du kan inaktivera gränssnittet med hjälp av de här instruktionerna.

Följande PowerShell-cmdlet avinstallerar Microsoft Defender Antivirus på Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

Om du Microsoft Defender Antivirus att Windows Server 2016 med hjälp av följande PowerShell-cmdlet:

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>Se även

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus kompatibilitet](microsoft-defender-antivirus-compatibility.md)
