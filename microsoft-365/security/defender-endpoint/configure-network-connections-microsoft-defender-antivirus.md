---
title: Konfigurera och verifiera nätverksanslutningar för Microsoft Defender Antivirus
description: Konfigurera och testa anslutningen till Microsoft Defender Antivirus molnskyddstjänst.
keywords: antivirus, Microsoft Defender Antivirus, antimalware, säkerhet, försvarare, moln, aggressivitet, skyddsnivå
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
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572531"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Konfigurera och verifiera nätverksanslutningar för Microsoft Defender Antivirus

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

För att Microsoft Defender Antivirus att det molnbaserade skyddet fungerar korrekt måste du konfigurera nätverket så att anslutningar mellan slutpunkterna och vissa Microsoft-servrar tillåts. I den här artikeln visas de anslutningar som måste tillåtas, till exempel genom att använda brandväggsregler, och instruktioner för hur du validerar anslutningen. Genom att konfigurera ditt skydd på rätt sätt kan du se till att du får det bästa värdet från dina molnbaserade skyddstjänster.

Se blogginlägget Viktiga [ändringar i Slutpunkten för Microsoft Active Protection Services för](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) viss information om nätverksanslutning.

> [!TIP]
> Du kan också besöka Microsoft Defender for Endpoint-demowebbplatsen [demo.wd.microsoft.com för](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) att bekräfta att följande funktioner fungerar:
>
> - Molnbaserat skydd
> - Snabb inlärning (inklusive block vid första anblicken)
> - Potentiellt oönskad programblockering

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Tillåt anslutningar till Microsoft Defender Antivirus molntjänst

Den Microsoft Defender Antivirus molntjänsten ger snabbt och starkt skydd för dina slutpunkter. Att aktivera den molnbaserade skyddstjänsten är valfritt, men det rekommenderas starkt eftersom det ger viktigt skydd mot skadlig kod på dina slutpunkter och i hela nätverket.

> [!NOTE]
> Den Microsoft Defender Antivirus molntjänsten är en mekanism för att leverera uppdaterat skydd till ditt nätverk och punkter. Även om det kallas en molntjänst är det inte bara skydd för filer som lagras i molnet, utan använder distribuerade resurser och maskininlärning för att leverera skydd till dina punkter i en hastighet som är mycket snabbare än traditionella Security Intelligence-uppdateringar.

Se [Aktivera molnskydd för](enable-cloud-protection-microsoft-defender-antivirus.md) information om hur du aktiverar tjänsten med Intune, Microsoft Endpoint Configuration Manager, Grupprincip, PowerShell-cmdletar eller på enskilda klienter i Windows-säkerhet appen. 

När du har aktiverat tjänsten kan du behöva konfigurera nätverket eller brandväggen för att tillåta anslutningar mellan den och slutpunkterna.

Eftersom ditt skydd är en molntjänst måste datorer ha tillgång till Internet och nå Microsoft Defender för Office 365 maskininlärningstjänster. Uteslut inte WEBBADRESSen `*.blob.core.windows.net` från någon form av nätverksinspektion. 

Tabellen nedan visar tjänsterna och tillhörande webbadresser. Kontrollera att det inte finns några brandväggs- eller nätverksfiltreringsregler som nekar åtkomst till dessa webbadresser, eller att du kan behöva skapa en tillåt-regel specifikt för dem (exklusive WEBBADRESSen `*.blob.core.windows.net` ). Nedan nämns webbadresser använder port 443 för kommunikation.


| **Tjänst**| **Beskrivning** |**URL** |
| :--: | :-- | :-- |
| Microsoft Defender Antivirus molnbaserad skyddstjänst, även kallad Microsoft Active Protection Service (MAPS)|Används av Microsoft Defender Antivirus för att ge molnskydd|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Mu (Microsoft Update Service) <br/> Windows Wu (Update Service)|  Säkerhetsintelligens och produktuppdateringar   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Mer information finns [i Anslutningsslutpunkter för Windows Uppdatering](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Security Intelligence uppdaterar alternativ nedladdningsplats (ADL)|   Alternativ plats för Microsoft Defender Antivirus Security Intelligence-uppdateringar om den installerade säkerhetsintelligensen är in dated (7 eller fler dagar efter)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Lagring av skadlig kod|Upload plats för filer som skickas till Microsoft via formuläret Inlämning eller automatisk exempelinlämning    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Lista över återkallade certifikat (CRL)|Används av Windows när du skapar SSL-anslutningen till MAPS för uppdatering av listan över återkallade certifikat   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Symbol butik|Används av Microsoft Defender Antivirus för att återställa vissa kritiska filer under reparationsflöden  | `https://msdl.microsoft.com/download/symbols` |
| Universell telemetriklient| Används av Windows för att skicka klientdiagnostikdata; Microsoft Defender Antivirus använder telemetri för produktkvalitetsövervakning   | Uppdateringen använder SSL (TCP Port 443) för att hämta manifest och ladda upp diagnostikdata till Microsoft som använder följande DNS-slutpunkter:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Validera anslutningar mellan nätverket och molnet

När du har tillåtit webbadresserna ovan kan du testa om du är ansluten till molntjänsten Microsoft Defender Antivirus och rapporterar och tar emot information korrekt för att säkerställa att du är helt skyddad.

**Använd cmdline-verktyget för att validera molnskydd:**

Använd följande argument med kommandoradsverktyget Microsoft Defender Antivirus `mpcmdrun.exe` ( ) för att verifiera att nätverket kan kommunicera med Microsoft Defender Antivirus molntjänst:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Du måste öppna en version på administratörsnivå av kommandotolken. Högerklicka på objektet på Start-menyn, klicka på **Kör som administratör och** klicka på **Ja** vid behörighetsprompten. Det här kommandot fungerar bara Windows 10, version 1703 eller senare.

Mer information finns i [Hantera Microsoft Defender Antivirus med mpcmdrun.exe kommandoradsverktyget](command-line-arguments-microsoft-defender-antivirus.md).

**Försök att ladda ner en falsk skadlig fil från Microsoft:**

Du kan hämta en exempelfil Microsoft Defender Antivirus kommer att upptäcka och blockera om du är korrekt ansluten till molnet.

Ladda ner filen genom att besöka [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Den här filen är inte en faktisk bit av skadlig programvara. Det är en falsk fil som är utformad för att testa om du är korrekt ansluten till molnet.

Om du är korrekt ansluten visas en varning Microsoft Defender Antivirus meddelande.

Om du använder Microsoft Edge visas också ett meddelande:

![Microsoft Edge informera användaren om att skadlig programvara hittades](images/defender/wdav-bafs-edge.png)

Ett liknande meddelande visas om du använder Internet Explorer:

![Microsoft Defender Antivirus meddelande som informerar användaren om att skadlig kod hittades](images/defender/wdav-bafs-ie.png)

Du ser också en identifiering under **Karantänhot i** avsnittet Skanna **historik** i Windows-säkerhet appen:

1. Öppna appen Windows-säkerhet genom att klicka på sköldikonen i Aktivitetsfältet eller söka på Start-menyn för **Säkerhet**.

2. Välj **Virus & hotskydd** och välj sedan **Skyddshistorik**.

3. Under avsnittet **Karantänhot väljer du** Se fullständig **historik för att** se den upptäckta falska skadlig programvara.

   > [!NOTE]
   > Versioner av Windows 10 före version 1703 har ett annat användargränssnitt. Se [Microsoft Defender Antivirus i Windows-säkerhet appen](microsoft-defender-security-center-antivirus.md).

   Händelseloggen Windows visas också [Windows Defender 1116 för klienthändelse.](troubleshoot-microsoft-defender-antivirus.md)

## <a name="related-articles"></a>Relaterade artiklar

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Aktivera molnbaserat skydd](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Argument för kommandorad](command-line-arguments-microsoft-defender-antivirus.md)

- [Viktiga ändringar i slutpunkten för Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
