---
title: Schemalägga genomsökningar med Microsoft Defender för Slutpunkt i macOS
description: Lär dig hur du schemalägger en automatisk genomsökningstid för Microsoft Defender för Slutpunkt i macOS för att bättre skydda organisationens tillgångar.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, genomsökningar, antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a93ea3427c72eb5529715b92cb18d01462493cc6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842860"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Schemasökningar med Microsoft Defender för Slutpunkt i macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Du kan starta en sökning med hot när som helst med Microsoft Defender för Endpoint, men ditt företag kan ha nytta av schemalagda eller tidsade genomsökningar. Du kan till exempel schemalägga en genomsökning så att den körs i början av varje arbetsdag eller vecka. 

## <a name="schedule-a-scan-with-launchd"></a>Schemalägga en genomsökning *med startad*

Du kan skapa ett skanningsschema med det *startad* daemon på en macOS-enhet.

1. Följande kod visar det schema du behöver använda för att schemalägga en genomsökning. Öppna en textredigerare och använd det här exemplet som en guide för din egen schemalagda genomsökningsfil.

    Mer information om filformatet *.plist* som används här finns i [Listfiler för informationsegenskap](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) på den officiella Apple-utvecklarwebbplatsen.

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. Spara filen som *com.microsoft.wdav.schedquickscan.plist*.

    > [!TIP]
    > Om du vill köra en fullständig genomsökning i stället för en snabbsökning kan du ändra rad 12, och använda alternativet i stället för (dvs. ) och spara filen som `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* i stället för *com.microsoft.wdav.sched **quick** scan.plist*.

3. Öppna **terminalen**.
4. Ange följande kommandon för att läsa in filen:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. Den schemalagda genomsökningen kommer att köras vid det datum, den tid och den frekvens som du har definierat i p-listan. I exemplet körs skanningen vid 02:00 varje fredag. 

    Värdet `Weekday` för använder ett `StartCalendarInterval` heltal för att ange den femte dagen i veckan eller fredag.

 > [!IMPORTANT]
 > Agenter som körs med *lansering körs* inte vid den schemalagda tiden medan enheten är i viloläge. De körs i stället när enheten återgår till viloläge.
 >
 > Om enheten är avstängd körs skanningen vid nästa schemalagda genomsökningstid.

## <a name="schedule-a-scan-with-intune"></a>Schemalägga en genomsökning med Intune

Du kan också schemalägga skanningar med Microsoft Intune. Den [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) skript som finns i Skript för [Microsoft Defender](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) för Slutpunkt finns kvar när enheten återgår från viloläge. 

Mer detaljerade anvisningar om hur du använder det här skriptet i ditt företag finns i Använda skript på macOS-enheter i [Intune.](/mem/intune/apps/macos-shell-scripts)
