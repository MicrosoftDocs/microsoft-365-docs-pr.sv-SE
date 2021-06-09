---
title: Samla in supportloggar i Microsoft Defender för slutpunkter med live-svar
description: Lär dig hur du samlar in loggar med livesvar för felsökning av problem med Microsoft Defender för slutpunkter
keywords: support, log, collect, troubleshoot, live response, liveanalyzer, analyzer, live, response
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
ms.openlocfilehash: 07593fac6ed9a3fbc00d904718380b386f31dba3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893419"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a>Samla in supportloggar i Microsoft Defender för slutpunkt med live-svar 


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


När du kontaktar supporten kan du bli ombedd att tillhandahålla utdatapaketet för verktyget Microsoft Defender för Endpoint Client Analyzer.

I det här avsnittet finns instruktioner om hur du kör verktyget via Live Response.

1. Ladda ned rätt skript
    * Endast Microsoft Defender för slutpunktsklientens sensorloggar: [LiveAnalyzer.ps1 skript](https://aka.ms/MDELiveAnalyzer).
      - Ungefärlig storlek för resultatpaket: ~100Kb 
    *  Microsoft Defender för slutpunktsklient sensor och antivirusloggar: [LiveAnalyzer+MDAV.ps1 skript](https://aka.ms/MDELiveAnalyzerAV).
       - Ungefärlig storlek för resultatpaket: ~10 MB 
 
2.  Starta en [Live Response-session](live-response.md#initiate-a-live-response-session-on-a-device) på den dator du behöver undersöka.

3.  Välj **Upload till biblioteket**.

    ![Bild på uppladdningsfil](images/upload-file.png)

4. Välj **Välj fil**.

    ![Bild på knappen Välj fil1](images/choose-file.png)

5. Markera den nedladdade filen med namnet MDELiveAnalyzer.ps1 klicka sedan på **Bekräfta**


   ![Bild på knappen Välj fil2](images/analyzer-file.png)


6. I LiveResponse-sessionen använder du kommandona nedan för att köra analyseraren och samla in resultatfilen:

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    [![Bild på kommandon ](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)


>[!NOTE]
> - Den senaste förhandsversionen av MDEClientAnalyzer kan laddas ned här: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) .
> 
> - LiveAnalyzer-skriptet laddar ned felsökningspaketet på måldatorn från: https://mdatpclientanalyzer.blob.core.windows.net .
> 
>   Om du inte kan låta datorn nå URL:en ovan laddar du upp MDEClientAnalyzerPreview.zip till biblioteket innan du kör LiveAnalyzer-skriptet:
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - Mer information om hur du samlar in data lokalt på en dator om datorn inte kommunicerar med Microsoft Defender för Endpoint-molntjänster, eller om den inte visas i Microsoft Defender för Slutpunktsportalen som förväntat, finns i Verifiera klientanslutningen till Microsoft Defender för [slutpunktstjänst-URL:er.](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)
