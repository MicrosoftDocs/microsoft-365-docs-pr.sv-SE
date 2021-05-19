---
title: Konfigurera och verifiera nätverksanslutningar för Microsoft Defender Antivirus
description: Konfigurera och testa anslutningen till Microsoft Defender Antivirus molnskyddstjänsten.
keywords: antivirus, Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, moln, aggressivhet, skyddsnivå
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 5e754c2f4b5406d4b91ef624415f3819d3171305
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536028"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Konfigurera och verifiera nätverksanslutningar för Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Om du Microsoft Defender Antivirus att moln levererat-skydd fungerar korrekt måste du konfigurera nätverket så att anslutningar tillåts mellan slutpunkterna och vissa Microsoft-servrar. Den här artikeln innehåller en lista över de anslutningar som måste tillåtas, till exempel genom att använda brandväggsregler, och innehåller instruktioner för att verifiera anslutningen. Om du konfigurerar skyddet på rätt sätt får du bästa möjliga värde från dina moln leveransskyddstjänster.

Mer information om [nätverksanslutningen finns i blogginlägget Viktiga](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) ändringar av Microsoft Active Protection Services-slutpunkten.

> [!TIP]
> Du kan också besöka demowebbplatsen Microsoft Defender för slutpunkt [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att följande funktioner fungerar:
>
> - Molnbaserat skydd
> - Fast learning (inklusive block vid första synen)
> - Potentiellt oönskad programblockering

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Tillåt anslutningar till Microsoft Defender Antivirus molntjänsten

Den Microsoft Defender Antivirus tjänst i molnet ger snabbt och starkt skydd för dina slutpunkter. Aktivering av den molnbaserade skyddstjänsten är valfri, men vi rekommenderar starkt att den ger ett viktigt skydd mot skadlig programvara på slutpunkter och i nätverket.

> [!NOTE]
> Den Microsoft Defender Antivirus molntjänsten är en mekanism för att tillhandahålla uppdaterat skydd till nätverket och slutpunkterna. Trots att det kallas för molntjänst är det inte bara skydd för filer som lagras i molnet utan använder distribuerade resurser och maskininlärning för att ge skydd till slutpunkterna i en takt som är mycket snabbare än traditionella säkerhetsintelligensuppdateringar.

Mer [information om](enable-cloud-protection-microsoft-defender-antivirus.md) hur du aktiverar tjänsten med Intune, Microsoft Endpoint Configuration Manager, Grupprincip, PowerShell-cmdlets eller på enskilda klienter i Windows-säkerhet-appen finns i Aktivera moln levererat skydd. 

När du har aktiverat tjänsten kan du behöva konfigurera nätverket eller brandväggen för att tillåta anslutningar mellan den och dina slutpunkter.

Eftersom ditt skydd är en molntjänst måste datorerna ha åtkomst till Internet och kunna nå Microsoft Defender för Office 365 maskininlärningstjänster. Exkludera inte URL:en `*.blob.core.windows.net` från någon typ av nätverksinspektion. 

I tabellen nedan visas tjänsterna och deras tillhörande URL:er. Kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till url-adresserna, eller så kan du behöva skapa en tillåta-regel specifikt för dem (undantaget `*.blob.core.windows.net` URL:en). Omnämnande URL:er använder port 443 för kommunikation.


| **Tjänst**| **Beskrivning** |**URL** |
| :--: | :-- | :-- |
| Microsoft Defender Antivirus moln levererad skyddstjänst, även kallad Microsoft Active Protection Service (MAPS)|Används av Microsoft Defender Antivirus för att ge moln levererat skydd|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) <br/> Windows Uppdateringstjänst (WU)|  Säkerhetsinformation och produktuppdateringar   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Mer information finns [i Anslutningsslutpunkter för Windows Uppdatering](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Alternativ nedladdningsplats för säkerhetsintelligensuppdateringar (ADL)|   Alternativ plats för Microsoft Defender Antivirus säkerhetsintelligensuppdateringar om den installerade säkerhetsintelligensen är in date (7 eller fler dagar efter)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Lagring av inskickade skadlig programvara|Upload plats för filer som skickats till Microsoft via formulär för inskickning eller automatiskt exempel    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Certifikatåterkallningslista (CRL)|Används av Windows när du skapar SSL-anslutningen till KARTOR för att uppdatera CRL   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Symbolarkiv|Används av Microsoft Defender Antivirus för att återställa vissa kritiska filer under åtgärdsflöden  | `https://msdl.microsoft.com/download/symbols` |
| Universell telemetriklient| Används av Windows för att skicka klientdiagnostikdata. Microsoft Defender Antivirus använder telemetri för övervakning av produktkvalitet   | Uppdateringen använder SSL (TCP Port 443) för att ladda ned manifest och ladda upp diagnostikdata till Microsoft som använder följande DNS-slutpunkter:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Verifiera anslutningar mellan ditt nätverk och molnet

När du har tillått webbadresserna ovan kan du testa om du är ansluten till Microsoft Defender Antivirus-molntjänsten och rapporterar och tar emot information på rätt sätt för att säkerställa att du är helt skyddad.

**Använd cmdline-verktyget för att verifiera moln levererat skydd:**

Använd följande argument med kommandoradsverktyget Microsoft Defender Antivirus ( ) för att verifiera att nätverket kan kommunicera Microsoft Defender Antivirus `mpcmdrun.exe` molntjänsten:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Du måste öppna en version på administratörsnivå av kommandotolken. Högerklicka på objektet på Start-menyn, klicka på **Kör som administratör och** klicka på **Ja** när behörigheter efterfrågas. Det här kommandot fungerar bara i Windows 10, version 1703 eller senare.

Mer information finns i [Hantera Microsoft Defender Antivirus med mpcmdrun.exe-kommandoradsverktyget](command-line-arguments-microsoft-defender-antivirus.md).

**Försök att ladda ned en falsk skadlig fil från Microsoft:**

Du kan ladda ned en exempelfil Microsoft Defender Antivirus kan identifiera och blockera om du är korrekt ansluten till molnet.

Ladda ned filen genom att gå till [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Den här filen är inte en faktisk del av skadlig programvara. Det är en falsk fil som är utformad för att testa om du är korrekt ansluten till molnet.

Om du är korrekt ansluten visas en varning om Microsoft Defender Antivirus meddelande.

Om du använder Microsoft Edge visas även ett meddelande:

![Microsoft Edge informerar användaren om att skadlig programvara hittades](images/defender/wdav-bafs-edge.png)

Ett liknande meddelande visas om du använder Internet Explorer:

![Microsoft Defender Antivirus som informerar användaren om att skadlig programvara hittades](images/defender/wdav-bafs-ie.png)

Du ser också en identifiering under Hot i karantän i avsnittet **Genomsökningshistorik** i Windows-säkerhet appen: 

1. Öppna Windows-säkerhet genom att klicka på sköldikonen i aktivitetsfältet eller söka efter Defender på **startmenyn.**

2. Välj panelen **& för skydd mot** hot (eller sköldikonen på den vänstra menyraden) och sedan etiketten **Sökhistorik:**

    ![Skärmbild av etiketten Skanna historik i Windows-säkerhet appen](images/defender/wdav-history-wdsc.png)

3. Under avsnittet **Hot i karantän väljer** du Se fullständig **historik för** att se den identifierade falska skadlig programvara.

   > [!NOTE]
   > Versioner av Windows 10 version 1703 har ett annat användargränssnitt. Se [Microsoft Defender Antivirus i Windows-säkerhet appen](microsoft-defender-security-center-antivirus.md).

   I Windows händelseloggen visas också [Windows Defender klienthändelse-ID 1116.](troubleshoot-microsoft-defender-antivirus.md)

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Aktivera molnbaserat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Kommandoradsargument](command-line-arguments-microsoft-defender-antivirus.md)

- [Viktiga ändringar av slutpunkten Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
