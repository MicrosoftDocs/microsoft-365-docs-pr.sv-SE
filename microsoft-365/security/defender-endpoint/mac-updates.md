---
title: Distribuera uppdateringar för Microsoft Defender för slutpunkt på Mac
description: Kontrollera uppdateringar för Microsoft Defender för Slutpunkt på Mac i företagsmiljöer.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, uppdateringar, distribuera
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
ms.openlocfilehash: 6447aa4182846020312e9be870c5548d9415ac71
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842836"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>Distribuera uppdateringar för Microsoft Defender för slutpunkt i macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint för macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.

För att uppdatera Microsoft Defender för slutpunkt i macOS används ett program med namnet Microsoft AutoUpdate (MAU). Som standard söker MAU automatiskt efter uppdateringar varje dag, men du kan ändra det till varje vecka, varje månad eller manuellt.

![MAU skärmbild](images/MDATP-34-MAU.png)

Om du bestämmer dig för att distribuera uppdateringar med dina verktyg för programvarudistribution bör du konfigurera MAU att manuellt söka efter programuppdateringar. Du kan distribuera inställningar för att konfigurera hur och när MAU söker efter uppdateringar för Mac-datorer i organisationen.

## <a name="use-msupdate"></a>Använda msupdate

MAU innehåller ett kommandoradsverktyg, *msupdate,* som är utformat för IT-administratörer så att de får mer exakt kontroll över när uppdateringar tillämpas. Instruktioner för hur du använder verktyget finns i Uppdaterings- och [Office för Mac med hjälp av msupdate.](/deployoffice/mac/update-office-for-mac-using-msupdate)

I MAU är programidentifieraren för Microsoft Defender för Slutpunkt i macOS *WDAV00.* Ladda ned och installera de senaste uppdateringarna för Microsoft Defender för Slutpunkt i macOS genom att köra följande kommando från ett terminalfönster:

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Ange inställningar för Microsoft AutoUpdate

I det här avsnittet beskrivs de vanligaste inställningarna som kan användas för att konfigurera MAU. De här inställningarna kan distribueras som en konfigurationsprofil via hanteringskonsolen som ditt företag använder. Ett exempel på en konfigurationsprofil visas i följande avsnitt.

### <a name="set-the-channel-name"></a>Ange kanalnamn

Kanalen avgör typ och frekvens för uppdateringar som erbjuds via MAU. Enheter i `Beta` kan prova nya funktioner före enheter i och `Preview` `Current` . 

Kanalen `Current` innehåller den mest stabila versionen av produkten.

>[!IMPORTANT]
> Före Microsoft AutoUpdate version 4.29 hade kanaler olika namn: 
> 
> - `Beta` hette `InsiderFast` (Insider – snabbt)
> - `Preview` hette `External` (Insider – långsamt)
> - `Current` hette `Production`

>[!TIP]
>Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i ditt företag `Beta` för eller `Preview` .

|Avsnitt|Värde|
|:--|:--|
| **Domän** | `com.microsoft.autoupdate2` |
| **Nyckel** | ChannelName |
| **Datatyp** | Sträng |
| **Möjliga värden** | Beta <br/> Förhandsgranska <br/> Aktuell |
|||

>[!WARNING]
>Den här inställningen ändrar kanalen för alla program som uppdateras via Microsoft AutoUpdate. Om du vill ändra endast kanalen för Microsoft Defender för slutpunkt i macOS kör du följande kommando efter att `[channel-name]` du har ersatt med önskad kanal:
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>Ange uppdateringsintervall

Ändra hur ofta MAU söker efter uppdateringar.

|Avsnitt|Värde|
|:--|:--|
| **Domän** | `com.microsoft.autoupdate2` |
| **Nyckel** | UpdateCheckFrequency |
| **Datatyp** | Heltal |
| **Standardvärde** | 720 (minuter) |
| **Kommentar** | Det här värdet anges i minuter. |


### <a name="change-how-mau-interacts-with-updates"></a>Ändra hur MAU interagerar med uppdateringar

Ändra hur MAU söker efter uppdateringar.

|Avsnitt|Värde|
|:--|:--|
| **Domän** | `com.microsoft.autoupdate2` |
| **Nyckel** | HowToCheck |
| **Datatyp** | Sträng |
| **Möjliga värden** | Manuellt <br/> AutomaticCheck <br/> AutomaticDownload |
| **Kommentar** |  Observera att AutomaticDownload gör en nedladdning och installation utan att du behöver göra det. |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>Ändra om knappen Sök efter uppdateringar ska vara aktiverad

Ändra om lokala användare ska kunna klicka på alternativet "Sök efter uppdateringar" i användargränssnittet för Microsoft AutoUpdate.

|Avsnitt|Värde|
|:--|:--|
| **Domän** | `com.microsoft.autoupdate2` |
| **Nyckel** | EnableCheckForUpdatesButton |
| **Datatyp** | Boolesk |
| **Möjliga värden** | True (standard) <br/> False |


### <a name="disable-insider-checkbox"></a>Kryssrutan Inaktivera Insider

Inställd på sant för att göra "Gå med i Office Insider Program..." inte tillgänglig/nedtonad för användare.

|Avsnitt|Värde|
|:--|:--|
| **Domän** | `com.microsoft.autoupdate2` |
| **Nyckel** | DisableInsiderCheckbox |
| **Datatyp** | Boolesk |
| **Möjliga värden** | False (standard) <br/> True |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>Begränsa telemetrin som skickas från MAU

Ange falskt om du vill skicka minimalt med data om hjärtslag, ingen programanvändning och ingen miljöinformation.

|Avsnitt|Värde|
|:--|:--|
| **Domän** | `com.microsoft.autoupdate2` |
| **Nyckel** | SendAllTelemetryEnabled |
| **Datatyp** | Boolesk |
| **Möjliga värden** | True (standard) <br/> False |


## <a name="example-configuration-profile"></a>Exempel på konfigurationsprofil

Följande konfigurationsprofil används för att:
- Placera enheten i produktionskanalen
- Ladda ned och installera uppdateringar automatiskt
- Aktivera knappen Sök efter uppdateringar i användargränssnittet
- Tillåt användare på enheten att registrera sig i Insider-kanalerna


>[!WARNING]
>Nedanstående konfiguration är en exempelkonfiguration och bör inte användas i produktionen utan en korrekt granskning av inställningar och skräddarsy konfigurationer.

>[!TIP]
>Om du vill förhandsgranska nya funktioner och ge tidig feedback rekommenderar vi att du konfigurerar vissa enheter i ditt företag `Beta` för eller `Preview` .

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Production</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a>Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

Om du vill konfigurera MAU kan du distribuera den här konfigurationsprofilen från det hanteringsverktyg som företaget använder:
- Från JAMF laddar du upp den här konfigurationsprofilen och anger preference domain *till com.microsoft.autoupdate2*.
- Från Intune laddar du upp den här konfigurationsprofilen och anger namnet på den anpassade konfigurationsprofilen *på com.microsoft.autoupdate2.*

## <a name="resources"></a>Resurser

- [referens för msupdate](/deployoffice/mac/update-office-for-mac-using-msupdate)
