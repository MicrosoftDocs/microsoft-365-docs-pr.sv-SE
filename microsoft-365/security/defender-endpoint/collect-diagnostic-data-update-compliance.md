---
title: Samla in diagnostikdata för uppdateringsefterlevnad och Windows Defender Microsoft Defender Antivirus
description: Använd ett verktyg för att samla in data för felsökning av problem med uppdateringsefterlevnad när du använder tillägget Microsoft Defender Antivirus Assessment i
keywords: felsökning, fel, korrigering, uppdateringsefterlevnad, oms, bildskärm, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 9fbe2b624bec6bbe17bcf6bc8d3f842ba1e43ad7
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903738"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>Samla in diagnostikdata för uppdateringsefterlevnad för Microsoft Defender Antivirus bedömning


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

I den här artikeln beskrivs hur du samlar in diagnostikdata som kan användas av Microsofts support- och teknikteam för att felsöka problem som kan uppstå när du använder Microsoft Defender Antivirus Assessment-avsnittet i tillägget Uppdateringsefterlevnad.

Innan du försöker med den här processen bör du läsa [Felsöka Microsoft Defender Antivirus,](troubleshoot-reporting.md)uppfylla alla krav och vidta andra föreslagna felsökningssteg.

På minst två enheter som inte rapporterar eller visas i Uppdateringsefterlevnad hämtar du .cab-diagnostikfilen genom att göra följande:

1. Öppna en version på administratörsnivå av kommandotolken på följande sätt:
        
    a. Öppna **Start-menyn.**

    b. Skriv **cmd**. Högerklicka på **Kommandotolken och** välj sedan **Kör som administratör.**

    c. Ange administratörsautentiseringsuppgifter eller godkänn uppmaningen.
        
2. Navigera till Windows Defender katalogen. Som standard är det här `C:\Program Files\Windows Defender` .

3. Skriv in följande kommando och tryck sedan på **Retur**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. En .cab genereras som innehåller olika diagnostikloggar. Platsen för filen anges i utdata i kommandotolken. Platsen är som standard `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

5. Kopiera dessa .cab till en plats som Kan nås av Microsoft Support. Ett exempel kan vara en lösenordsskyddad OneDrive som du kan dela med oss.

6. Skicka ett e-postmeddelande <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">med hjälp av e-postmallen</a>för uppdateringsefterlevnad och fyll i mallen med följande information:
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>Se även

- [Felsöka Windows Defender Microsoft Defender Antivirus rapportering](troubleshoot-reporting.md)