---
title: Felsöka problem med livesvar i Microsoft Defender ATP
description: Felsöka problem som kan uppstå när du använder livesvar i Microsoft Defender ATP
keywords: felsöka livesvar, live, svar, låst, fil
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 27f2c7eb01a857ec38b11797c0703710c02ac1bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076801"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Felsöka problem med livesvar i Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

På den här sidan finns detaljerade anvisningar för felsökning av problem med livesvar.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>Det går inte att komma åt filen under svarssessioner i livesändning
Om du stöter på ett felmeddelande när du försöker vidta en åtgärd under en svarssession och du får ett felmeddelande som säger att filen inte kan kommas åt måste du följa stegen nedan för att åtgärda problemet.

1. Kopiera följande skriptkodavsnitt och spara det som en PS1-fil:

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. Lägg till skriptet i livesvarsbiblioteket.
3. Kör skriptet med en parameter: filsökvägen för den fil som ska kopieras.
4. Navigera till TEMP-mappen.
5. Kör den åtgärd du vill vidta för den kopierade filen.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>Långsamma svarssessioner eller fördröjningar vid initiala anslutningar
Live Response utnyttjar Defender för slutpunkts sensorregistrering med WNS-tjänsten i Windows. Om du har anslutningsproblem med live-svar bekräftar du följande information:
1. `notify.windows.com` inte är blockerad i din miljö. Mer information finns i Konfigurera [enhetsproxy och Internetanslutningsinställningar.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)
2. WpnService (Windows Push Notifications System Service) inaktiveras inte.

Läs artiklarna nedan för fullständig förståelse av WpnService-tjänstens beteende och krav:
- [Översikt över Windows Push Notification Services (WNS)](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Företagsbrandväggs- och proxykonfigurationer för stöd för WNS-trafik](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Offentliga IP-intervall för Microsoft Push Notifications Service (MPNS)](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

