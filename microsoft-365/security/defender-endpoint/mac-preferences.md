---
title: Ange inställningar för Microsoft Defender för Slutpunkt för Mac
description: Konfigurera Microsoft Defender för Slutpunkt för Mac i företagsorganisationer.
keywords: microsoft, defender, atp, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: d2bea469031e2c5932e859fbad7d442ebe4d34ed
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860929"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a>Ange inställningar för Microsoft Defender för Slutpunkt i macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint för macOS](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
>Den här artikeln innehåller instruktioner för hur du anger inställningar för Microsoft Defender för Slutpunkt på macOS i företagsorganisationer. Information om hur du konfigurerar Microsoft Defender för slutpunkt i macOS med kommandoradsgränssnittet finns i [Resurser](mac-resources.md#configuring-from-the-command-line).

## <a name="summary"></a>Sammanfattning

I företagsorganisationer kan Microsoft Defender för slutpunkt i macOS hanteras via en konfigurationsprofil som distribueras med ett av flera hanteringsverktyg. De inställningar som hanteras av ditt säkerhetsteam har företräde framför inställningar som anges lokalt på enheten. Om du vill ändra inställningar som ställts in via konfigurationsprofilen krävs eskalerade behörigheter och är inte tillgängligt för användare utan administrativ behörighet.

I den här artikeln beskrivs konfigurationsprofilens struktur, en rekommenderad profil som du kan använda för att komma igång och instruktioner om hur du distribuerar profilen.

## <a name="configuration-profile-structure"></a>Konfigurationsprofilstruktur

Konfigurationsprofilen är en *PLIST-fil* som består av poster som identifieras med en nyckel (som betecknar namnet på inställningen), följt av ett värde, vilket beror på vilken typ av inställning det är. Värdena kan antingen vara enkla (till exempel ett numeriskt värde) eller komplexa, till exempel en kapslad lista med inställningar.

>[!CAUTION]
>Konfigurationsprofilens layout beror på vilken hanteringskonsol du använder. Följande avsnitt innehåller exempel på konfigurationsprofiler för JAMF och Intune.

Den översta nivån i konfigurationsprofilen innehåller produktomfattande inställningar och poster för underavsnitt av Microsoft Defender för slutpunkt, som förklaras mer ingående i nästa avsnitt.

### <a name="antivirus-engine-preferences"></a>Inställningar för antivirusmotor

Avsnittet *antivirusEngine* i konfigurationsprofilen används för att hantera inställningarna för antiviruskomponenten i Microsoft Defender för slutpunkt.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | antivirusEngine |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |

#### <a name="enable--disable-real-time-protection"></a>Aktivera/inaktivera realtidsskydd

Ange om du vill aktivera realtidsskydd som genomsöker filer när de används.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | enableRealTimeProtection |
| **Datatyp** | Boolesk |
| **Möjliga värden** | true (standard) <br/> false |

#### <a name="enable--disable-passive-mode"></a>Aktivera/inaktivera passivt läge

Ange om antivirusmotorn körs i passiv form. Passivt läge har följande konsekvenser: 
- Realtidsskydd är inaktiverat
- Skanning på begäran är aktiverat
- Automatisk åtgärd för hot är inaktiverat
- Säkerhetsintelligensuppdateringar är aktiverat
- Statusmenyikonen är dold

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | passivläge |
| **Datatyp** | Boolesk |
| **Möjliga värden** | false (standard) <br/> true |
| **Kommentarer** | Tillgängligt i Microsoft Defender för slutpunkt version 100.67.60 eller senare. |

#### <a name="exclusion-merge-policy"></a>Princip för undantagskoppling

Ange kopplingsprincipen för undantag. Det här kan vara en kombination av administratörsdefinierade och användardefinierade undantag ( `merge` ) eller endast administratörsdefinierade undantag ( `admin_only` ). Den här inställningen kan användas för att begränsa lokala användare från att definiera sina egna undantag.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | exclusionsMergePolicy |
| **Datatyp** | Sträng |
| **Möjliga värden** | koppla (standard) <br/> admin_only |
| **Kommentarer** | Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare. |

#### <a name="scan-exclusions"></a>Undantag för skanning

Ange enheter som inte ska genomsökas. Undantag kan anges med fullständiga sökvägar, filnamnstillägg eller filnamn.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | undantag |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |

##### <a name="type-of-exclusion"></a>Typ av undantag

Ange innehåll som ska undantas från att genomsökas efter typ.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | $type |
| **Datatyp** | Sträng |
| **Möjliga värden** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |

##### <a name="path-to-excluded-content"></a>Sökväg till utelämnat innehåll

Ange innehåll som inte ska genomsökas efter fullständig sökväg.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | sökväg |
| **Datatyp** | Sträng |
| **Möjliga värden** | giltiga sökvägar |
| **Kommentarer** | Gäller endast om *$type* *är undantagenPath* |

##### <a name="path-type-file--directory"></a>Sökvägstyp (fil/katalog)

Ange om *sökvägsegenskapen* refererar till en fil eller katalog. 

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | isDirectory |
| **Datatyp** | Boolesk |
| **Möjliga värden** | false (standard) <br/> true |
| **Kommentarer** | Gäller endast om *$type* *är undantagenPath* |

##### <a name="file-extension-excluded-from-the-scan"></a>Filnamnstillägget är undantaget från genomsökningen

Ange innehåll som ska undantas från att genomsökas efter filtillägg.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | tillägg |
| **Datatyp** | Sträng |
| **Möjliga värden** | giltiga filnamnstillägg |
| **Kommentarer** | Gäller endast om *$type* *är undantagenFileExtension* |

##### <a name="process-excluded-from-the-scan"></a>Process som uteslutits från genomsökningen

Ange en process där all filaktivitet är undantagen från genomsökning. Processen kan antingen anges med sitt namn (t.ex. `cat` ) eller med en fullständig sökväg (t.ex. `/bin/cat` ).

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | Namn |
| **Datatyp** | Sträng |
| **Möjliga värden** | valfri sträng |
| **Kommentarer** | Gäller endast om *$type* *är undantagenFilnamn* |

#### <a name="allowed-threats"></a>Tillåtna hot

Ange hot med namn som inte blockeras av Defender för Slutpunkt för Mac. Dessa hot kommer att tillåtas att köras.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | allowedThreats |
| **Datatyp** | Matris med strängar |

#### <a name="disallowed-threat-actions"></a>Otillåtna hotåtgärder

Begränsar de åtgärder som den lokala användaren på en enhet kan vidta när hot upptäcks. De åtgärder som ingår i den här listan visas inte i användargränssnittet.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | disallowedThreatActions |
| **Datatyp** | Matris med strängar |
| **Möjliga värden** | tillåt (begränsar användare från att tillåta hot) <br/> återställning (hindrar användare från att återställa hot från karantän) |
| **Kommentarer** | Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare. |

#### <a name="threat-type-settings"></a>Inställningar för hottyp

Ange hur vissa hottyper hanteras av Microsoft Defender för Slutpunkt i macOS.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | threatTypeSettings |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |

##### <a name="threat-type"></a>Hottyp

Ange hottyper.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | tangent |
| **Datatyp** | Sträng |
| **Möjliga värden** | potentially_unwanted_application <br/> archive_bomb |

##### <a name="action-to-take"></a>Åtgärd att vidta

Ange vilken åtgärd som ska vidtas när ett hot av den typ som anges i föregående avsnitt identifieras. Välj bland följande alternativ:

- **Granskning:** din enhet är inte skyddad mot den här typen av hot, men en post om hot loggas.
- **Blockering:** din enhet är skyddad mot den här typen av hot och du meddelas i användargränssnittet och säkerhetskonsolen.
- **Av:** din enhet är inte skyddad mot den här typen av hot och inget loggas.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | värde |
| **Datatyp** | Sträng |
| **Möjliga värden** | granskning (standard) <br/> blockera <br/> av |

#### <a name="threat-type-settings-merge-policy"></a>Princip för sammanfogning av hottyper

Ange kopplingsprincipen för inställningar av hottyper. Det kan vara en kombination av administratörsdefinierade och användardefinierade inställningar ( `merge` ) eller bara administratörsdefinierade inställningar ( `admin_only` ). Den här inställningen kan användas för att hindra lokala användare från att definiera sina egna inställningar för olika hottyper.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | threatTypeSettingsMergePolicy |
| **Datatyp** | Sträng |
| **Möjliga värden** | koppla (standard) <br/> admin_only |
| **Kommentarer** | Tillgängligt i Microsoft Defender för slutpunkt version 100.83.73 eller senare. |

#### <a name="antivirus-scan-history-retention-in-days"></a>Historik för antivirussökningshistorik kvar (i dagar)

Ange antalet dagar som resultaten ska behållas i genomsökningshistoriken på enheten. Gamla genomsökningsresultat tas bort från historiken. Gamla filer i karantän som också har tagits bort från disken.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | scanResultsRetentionDays |
| **Datatyp** | Sträng |
| **Möjliga värden** | 90 (standard). Tillåtna värden är 1 dag till 180 dagar. |
| **Kommentarer** | Tillgängligt i Microsoft Defender för slutpunkt version 101.07.23 eller senare. |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Maximalt antal objekt i historiken för antivirussökning

Ange det maximala antalet poster som ska behållas i genomsökningshistoriken. Posterna innehåller alla genomsökningar på begäran som utförts tidigare och alla antivirusprogramn.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | scanHistoryMaximumItems |
| **Datatyp** | Sträng |
| **Möjliga värden** | 10000 (standard). Tillåtna värden är från 5 000 objekt till 1 5 000 objekt. |
| **Kommentarer** | Tillgängligt i Microsoft Defender för slutpunkt version 101.07.23 eller senare. |

### <a name="cloud-delivered-protection-preferences"></a>Inställningar för moln levererat skydd

Konfigurera de molnbaserade skyddsfunktionerna i Microsoft Defender för Slutpunkt i macOS.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | cloudService |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |

#### <a name="enable--disable-cloud-delivered-protection"></a>Aktivera/inaktivera moln levererat skydd

Ange om du vill aktivera moln levererat skydd på enheten eller inte. Vi rekommenderar att du behåller den här funktionen aktiverad för att förbättra säkerheten för dina tjänster.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | aktiverat |
| **Datatyp** | Boolesk |
| **Möjliga värden** | true (standard) <br/> false |

#### <a name="diagnostic-collection-level"></a>Diagnostiksamlingsnivå

Diagnostikdata används för att hålla Microsoft Defender för Endpoint säkert och uppdaterat, identifiera, diagnostisera och åtgärda problem samt göra produktförbättringar. Den här inställningen bestämmer nivån för diagnostik som skickas av Microsoft Defender för Slutpunkt till Microsoft.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | diagnosticLevel |
| **Datatyp** | Sträng |
| **Möjliga värden** | valfritt (standard) <br/> obligatoriskt |

#### <a name="enable--disable-automatic-sample-submissions"></a>Aktivera/inaktivera automatiska exempelinskick

Avgör om misstänkta exempel (som troligen innehåller hot) skickas till Microsoft. Du uppmanas att ange om den inskickade filen troligen innehåller personlig information.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | automaticSampleSubmission |
| **Datatyp** | Boolesk |
| **Möjliga värden** | true (standard) <br/> false |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Aktivera/inaktivera automatiska säkerhetsintelligensuppdateringar

Avgör om säkerhetsintelligensuppdateringar installeras automatiskt:

|Avsnitt|Värde|
|:---|:---|
| **Nyckel** | automaticDefinitionUpdateEnabled |
| **Datatyp** | Boolesk |
| **Möjliga värden** | true (standard) <br/> false |

### <a name="user-interface-preferences"></a>Inställningar för användargränssnitt

Hantera inställningar för användargränssnittet i Microsoft Defender för Slutpunkt i macOS.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | userInterface |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |

#### <a name="show--hide-status-menu-icon"></a>Visa/dölj statusmenyikon

Ange om du vill visa eller dölja statusmenyikonen i det övre högra hörnet av skärmen.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | hideStatusMenuIcon |
| **Datatyp** | Boolesk |
| **Möjliga värden** | false (standard) <br/> true |

#### <a name="show--hide-option-to-send-feedback"></a>Visa/dölj alternativ för att skicka feedback

Ange om användare kan skicka feedback till Microsoft genom att gå till `Help`  >  `Send Feedback` .

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | userInitiatedFeedback |
| **Datatyp** | Sträng |
| **Möjliga värden** | aktiverad (standard) <br/> inaktiverad |
| **Kommentarer** | Tillgängligt i Microsoft Defender för slutpunkt version 101.19.61 eller senare. |

### <a name="endpoint-detection-and-response-preferences"></a>Inställningar för identifiering av slutpunkter och svar

Hantera inställningarna för slutpunktsidentifierings- och svarskomponenten (EDR) i Microsoft Defender för slutpunkten i macOS.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | edr |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |

#### <a name="device-tags"></a>Enhetstaggar

Ange ett taggnamn och dess värde. 

- GROUP-taggen taggar enheten med det angivna värdet. Taggen återspeglas i portalen under enhetssidan och kan användas för filtrering och gruppering av enheter.

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | taggar |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |

##### <a name="type-of-tag"></a>Typ av tagg

Anger typ av tagg

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | tangent |
| **Datatyp** | Sträng |
| **Möjliga värden** | `GROUP` |

##### <a name="value-of-tag"></a>Värdet på taggen

Anger värdet för taggen

|Avsnitt|Värde|
|:---|:---|
| **Domän** | `com.microsoft.wdav` |
| **Nyckel** | värde |
| **Datatyp** | Sträng |
| **Möjliga värden** | valfri sträng |

> [!IMPORTANT]  
> - Du kan bara ange ett värde per taggtyp.
> - Typ av taggar är unika och bör inte upprepas i samma konfigurationsprofil.

## <a name="recommended-configuration-profile"></a>Rekommenderad konfigurationsprofil

För att komma igång rekommenderar vi följande konfiguration för ditt företag för att dra nytta av alla skyddsfunktioner som Microsoft Defender för Endpoint tillhandahåller.

Följande konfigurationsprofil (eller, vid JAMF, en egenskapslista som kan laddas upp till profilen för anpassade inställningar) kommer att:
- Aktivera realtidsskydd (RTP)
- Ange hur följande hottyper ska hanteras:
  - **Potentiellt oönskade program (PUA)** blockeras
  - **Arkiveringsskyddet** (en fil med hög komprimeringshastighet) granskas i Microsoft Defender för Slutpunktsloggar
- Aktivera automatiska säkerhetsintelligensuppdateringar
- Aktivera moln levererat skydd
- Aktivera automatisk exempelinskickning

### <a name="property-list-for-jamf-configuration-profile"></a>Egenskapslista för JAMF-konfigurationsprofil

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Intune-profil

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>Exempel på fullständig konfigurationsprofil

Följande mallar innehåller poster för alla inställningar som beskrivs i det här dokumentet och kan användas för mer avancerade scenarier där du vill ha mer kontroll över Microsoft Defender för slutpunkt i macOS.

### <a name="property-list-for-jamf-configuration-profile"></a>Egenskapslista för JAMF-konfigurationsprofil

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Intune-profil

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a>Egenskapslistverifiering

Egenskapslistan måste vara en giltig *.plist-fil.* Det här kan kontrolleras genom att köra:

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

Om filen är rätt utformad returnerar kommandot ovan en utgångskod `OK` för `0` . Annars visas ett fel som beskriver problemet och kommandot returnerar en utgångskod för `1` .

## <a name="configuration-profile-deployment"></a>Konfigurationsprofildistribution

När du har skapat konfigurationsprofilen för ditt företag kan du distribuera den via hanteringskonsolen som företaget använder. I följande avsnitt finns instruktioner om hur du distribuerar den här profilen med HJÄLP av JAMF och Intune.

### <a name="jamf-deployment"></a>JAMF-distribution

Från JAMF-konsolen öppnar du Datorkonfigurationsprofiler , navigerar till den konfigurationsprofil du vill  >  använda och väljer sedan **Anpassade inställningar.** Skapa en post med `com.microsoft.wdav` som inställningsdomän och ladda upp den *.plist som produceras* tidigare.

>[!CAUTION]
>Du måste ange rätt inställningsdomän ( ). Annars kan inte inställningarna identifieras av `com.microsoft.wdav` Microsoft Defender för Slutpunkt.

### <a name="intune-deployment"></a>Intune-distribution

1. Öppna **Hantera**  >  **enhetskonfiguration**. Välj **Hantera**  >  **profiler**  >  **skapa profil**.

2. Välj ett namn för profilen. Ändra **Platform=macOS** till **Profiltyp=Anpassad**. Välj Konfigurera.

3. Spara den .plist som produceras tidigare som `com.microsoft.wdav.xml` .

4. Ange `com.microsoft.wdav` namnet på den anpassade **konfigurationsprofilen.**

5. Öppna konfigurationsprofilen och ladda upp `com.microsoft.wdav.xml` filen. (Den här filen skapades i steg 3.)

6. Välj **OK**.

7. Välj   >  **Hantera uppgifter.** På fliken **Inkludera** väljer du **Tilldela till alla användare & alla enheter.**

>[!CAUTION]
>Du måste ange rätt namn på den anpassade konfigurationsprofilen. Annars identifieras inte de här inställningarna av Microsoft Defender för Endpoint.

## <a name="resources"></a>Resurser

- [Referens för konfigurationsprofil (Utvecklardokumentation för Apple)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
