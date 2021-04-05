---
title: Ange inställningar för Microsoft Defender ATP för Linux
ms.reviewer: ''
description: Här beskrivs hur du konfigurerar Microsoft Defender ATP för Linux på företag.
keywords: microsoft, defender, atp, linux, installation, distribuera, avinstallation, enkel, ansible, linux, redhat, ubuntu, ubuntu, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5aedf841ddfc5a592fe4afd2f13d6470e24c438c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587521"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a>Ange inställningar för Microsoft Defender för Endpoint för Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
>Det här avsnittet innehåller instruktioner för hur du anger inställningar för Defender för Slutpunkt för Linux i företagsmiljöer. Om du är intresserad av att konfigurera produkten på en enhet från kommandoraden kan du gå till [Resurser](linux-resources.md#configure-from-the-command-line).

I företagsmiljöer kan Defender för Endpoint för Linux hanteras via en konfigurationsprofil. Den här profilen distribueras från valfri hanteringsverktyg. Inställningar som hanteras av företaget har företräde framför inställningar som anges lokalt på enheten. Med andra ord kan användarna i företaget inte ändra inställningar som anges i den här konfigurationsprofilen.

I den här artikeln beskrivs profilens struktur (inklusive en rekommenderad profil som du kan använda för att komma igång) och instruktioner om hur du distribuerar profilen.

## <a name="configuration-profile-structure"></a>Konfigurationsprofilstruktur

Konfigurationsprofilen är en .json-fil som består av poster som identifieras av en nyckel (som betecknar namnet på inställningen), följt av ett värde, vilket beror på vilken typ av inställning det är. Värdena kan vara enkla, till exempel numeriska värden eller komplexa, till exempel en kapslad lista med inställningar.

Vanligtvis använder du ett konfigurationsverktyg för att skicka en fil med ```mdatp_managed.json``` namnet på ```/etc/opt/microsoft/mdatp/managed/``` platsen.

Den översta nivån i konfigurationsprofilen omfattar produktomfattande inställningar och poster för underavsnitt av produkten, som förklaras mer detaljerat i nästa avsnitt.

### <a name="antivirus-engine-preferences"></a>Inställningar för antivirusmotor

Avsnittet *antivirusEngine* i konfigurationsprofilen används för att hantera inställningarna för antiviruskomponenten i produkten.

|||
|:---|:---|
| **Nyckel** | antivirusEngine |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |
|||

#### <a name="enable--disable-real-time-protection"></a>Aktivera/inaktivera realtidsskydd

Avgör om realtidsskydd (genomsökning av filer när de används) är aktiverat eller inte.

|||
|:---|:---|
| **Nyckel** | enableRealTimeProtection |
| **Datatyp** | Boolesk |
| **Möjliga värden** | true (standard) <br/> false |
|||

#### <a name="enable--disable-passive-mode"></a>Aktivera/inaktivera passivt läge

Avgör om antivirusmotorn körs i passiv form eller inte. I passivt läge:
- Realtidsskydd är inaktiverat.
- Skanning på begäran är aktiverat.
- Automatisk åtgärd för hot är inaktiverat.
- Säkerhetsintelligensuppdateringar aktiveras.
- Statusmenyikonen är dold.

|||
|:---|:---|
| **Nyckel** | passivläge |
| **Datatyp** | Boolesk |
| **Möjliga värden** | false (standard) <br/> true |
| **Kommentarer** | Tillgängligt i Defender för slutpunkt version 100.67.60 eller senare. |
|||

#### <a name="exclusion-merge-policy"></a>Princip för undantagskoppling

Anger kopplingsprincipen för undantag. Det kan vara en kombination av administratörsdefinierade och användardefinierade undantag ( `merge` ) eller endast administratörsdefinierade undantag ( `admin_only` ). Den här inställningen kan användas för att begränsa lokala användare från att definiera sina egna undantag.

|||
|:---|:---|
| **Nyckel** | exclusionsMergePolicy |
| **Datatyp** | Sträng |
| **Möjliga värden** | koppla (standard) <br/> admin_only |
| **Kommentarer** | Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare. |
|||

#### <a name="scan-exclusions"></a>Undantag för skanning

Enheter som har uteslutits från genomsökningen. Undantag kan anges med fullständiga sökvägar, filnamnstillägg eller filnamn.

|||
|:---|:---|
| **Nyckel** | undantag |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |
|||

**Typ av undantag**

Anger vilken typ av innehåll som undantas från genomsökningen.

|||
|:---|:---|
| **Nyckel** | $type |
| **Datatyp** | Sträng |
| **Möjliga värden** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |
|||

**Sökväg till utelämnat innehåll**

Används för att utesluta innehåll från genomsökningen genom den fullständiga sökvägen.

|||
|:---|:---|
| **Nyckel** | sökväg |
| **Datatyp** | Sträng |
| **Möjliga värden** | giltiga sökvägar |
| **Kommentarer** | Gäller endast om *$type* *är undantagenPath* |
|||

**Sökvägstyp (fil/katalog)**

Anger om *sökvägsegenskapen* refererar till en fil eller katalog. 

|||
|:---|:---|
| **Nyckel** | isDirectory |
| **Datatyp** | Boolesk |
| **Möjliga värden** | false (standard) <br/> true |
| **Kommentarer** | Gäller endast om *$type* *är undantagenPath* |
|||

**Filnamnstillägget är undantaget från genomsökningen**

Används för att utesluta innehåll från genomsökningen efter filnamnstillägget.

|||
|:---|:---|
| **Nyckel** | tillägg |
| **Datatyp** | Sträng |
| **Möjliga värden** | giltiga filnamnstillägg |
| **Kommentarer** | Gäller endast om *$type* *är undantagenFileExtension* |
|||

**Process som uteslutits från genomsökningen**

Anger en process där all filaktivitet är undantagen från genomsökning. Processen kan antingen anges med sitt namn (till exempel `cat` ) eller med en fullständig sökväg (t.ex. `/bin/cat` ).

|||
|:---|:---|
| **Nyckel** | Namn |
| **Datatyp** | Sträng |
| **Möjliga värden** | valfri sträng |
| **Kommentarer** | Gäller endast om *$type* *är undantagenFilnamn* |
|||

#### <a name="allowed-threats"></a>Tillåtna hot

Lista över hot (identifieras med namnet) som inte blockeras av produkten och i stället får köras.

|||
|:---|:---|
| **Nyckel** | allowedThreats |
| **Datatyp** | Matris med strängar |
|||

#### <a name="disallowed-threat-actions"></a>Otillåtna hotåtgärder

Begränsar de åtgärder som den lokala användaren på en enhet kan vidta när hot upptäcks. De åtgärder som ingår i den här listan visas inte i användargränssnittet.

|||
|:---|:---|
| **Nyckel** | disallowedThreatActions |
| **Datatyp** | Matris med strängar |
| **Möjliga värden** | tillåt (begränsar användare från att tillåta hot) <br/> återställning (hindrar användare från att återställa hot från karantän) |
| **Kommentarer** | Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare. |
|||

#### <a name="threat-type-settings"></a>Inställningar för hottyp

Inställningen *för threatTypeSettings* i antivirusmotorn används för att styra hur vissa hottyper hanteras av produkten.

|||
|:---|:---|
| **Nyckel** | threatTypeSettings |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |
|||

**Hottyp**

Typ av hot som beteendet är konfigurerat för.

|||
|:---|:---|
| **Nyckel** | tangent |
| **Datatyp** | Sträng |
| **Möjliga värden** | potentially_unwanted_application <br/> archive_bomb |
|||

**Åtgärd att vidta**

Åtgärd att vidta när de kommer över en typ av hot som anges i föregående avsnitt. Kan vara:

- **Granskning:** Enheten är inte skyddad mot den här typen av hot, men en post om hot loggas.
- **Blockering:** Enheten är skyddad mot den här typen av hot och du meddelas i säkerhetskonsolen.
- **Av:** Enheten är inte skyddad mot den här typen av hot och inget loggas.

|||
|:---|:---|
| **Nyckel** | värde |
| **Datatyp** | Sträng |
| **Möjliga värden** | granskning (standard) <br/> blockera <br/> av |
|||

#### <a name="threat-type-settings-merge-policy"></a>Princip för sammanfogning av hottyper

Anger kopplingsprincipen för inställningar av hottyper. Det kan vara en kombination av administratörsdefinierade och användardefinierade inställningar ( `merge` ) eller bara administratörsdefinierade inställningar ( `admin_only` ). Den här inställningen kan användas för att hindra lokala användare från att definiera sina egna inställningar för olika hottyper.

|||
|:---|:---|
| **Nyckel** | threatTypeSettingsMergePolicy |
| **Datatyp** | Sträng |
| **Möjliga värden** | koppla (standard) <br/> admin_only |
| **Kommentarer** | Tillgängligt i Defender för slutpunkt version 100.83.73 eller senare. |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a>Historik för antivirussökningshistorik kvar (i dagar)

Ange antalet dagar som resultaten ska behållas i genomsökningshistoriken på enheten. Gamla genomsökningsresultat tas bort från historiken. Gamla filer i karantän som också har tagits bort från disken.

|||
|:---|:---|
| **Nyckel** | scanResultsRetentionDays |
| **Datatyp** | Sträng |
| **Möjliga värden** | 90 (standard). Tillåtna värden är 1 dag till 180 dagar. |
| **Kommentarer** | Tillgängligt i Defender för slutpunkt version 101.04.76 eller senare. |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Maximalt antal objekt i historiken för antivirussökning

Ange det maximala antalet poster som ska behållas i genomsökningshistoriken. Posterna innehåller alla genomsökningar på begäran som utförts tidigare och alla antivirusprogramn.

|||
|:---|:---|
| **Nyckel** | scanHistoryMaximumItems |
| **Datatyp** | Sträng |
| **Möjliga värden** | 10000 (standard). Tillåtna värden är från 5 000 objekt till 1 5 000 objekt. |
| **Kommentarer** | Tillgängligt i Defender för slutpunkt version 101.04.76 eller senare. |
|||

### <a name="cloud-delivered-protection-preferences"></a>Inställningar för moln levererat skydd

*CloudService-posten* i konfigurationsprofilen används för att konfigurera produktens molndrivna skyddsfunktion.

|||
|:---|:---|
| **Nyckel** | cloudService |
| **Datatyp** | Ordlista (kapslad inställning) |
| **Kommentarer** | I följande avsnitt finns en beskrivning av innehållet i ordlistan. |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a>Aktivera/inaktivera moln levererat skydd

Avgör om moln levererat skydd är aktiverat på enheten eller inte. Vi rekommenderar att du behåller den här funktionen aktiverad för att förbättra säkerheten för dina tjänster.

|||
|:---|:---|
| **Nyckel** | aktiverat |
| **Datatyp** | Boolesk |
| **Möjliga värden** | true (standard) <br/> false |
|||

#### <a name="diagnostic-collection-level"></a>Diagnostiksamlingsnivå

Diagnostikdata används för att hålla Defender för Slutpunkt säker och uppdaterad, identifiera, diagnostisera och åtgärda problem samt göra produktförbättringar. Den här inställningen bestämmer nivån för diagnostik som skickas av produkten till Microsoft.

|||
|:---|:---|
| **Nyckel** | diagnosticLevel |
| **Datatyp** | Sträng |
| **Möjliga värden** | valfritt (standard) <br/> obligatoriskt |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a>Aktivera/inaktivera automatiska exempelinskick

Avgör om misstänkta exempel (som troligen innehåller hot) skickas till Microsoft. Det finns tre nivåer för kontroll av exempelinskick:

- **Ingen**: inga misstänkta exempel skickas till Microsoft.
- **Kassaskåp**: endast misstänkta exempel som inte innehåller personligt identifierbar information skickas automatiskt. Det här är standardvärdet för den här inställningen.
- **Alla**: alla misstänkta exempel skickas till Microsoft.

|||
|:---|:---|
| **Nyckel** | automaticSampleSubmissionConsent |
| **Datatyp** | Sträng |
| **Möjliga värden** | none (ingen) <br/> kassaskåp (standard) <br/> alla |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Aktivera/inaktivera automatiska säkerhetsintelligensuppdateringar

Avgör om säkerhetsintelligensuppdateringar installeras automatiskt:

|||
|:---|:---|
| **Nyckel** | automaticDefinitionUpdateEnabled |
| **Datatyp** | Boolesk |
| **Möjliga värden** | true (standard) <br/> false |
|||

## <a name="recommended-configuration-profile"></a>Rekommenderad konfigurationsprofil

För att komma igång rekommenderar vi följande konfigurationsprofil för ditt företag för att kunna dra nytta av alla skyddsfunktioner som Defender för Endpoint tillhandahåller.

Följande konfigurationsprofil:

- Aktivera realtidsskydd (RTP)
- Ange hur följande hottyper ska hanteras:
  - **Potentiellt oönskade program (PUA)** blockeras
  - **Arkivposterna** (fil med hög komprimeringshastighet) granskas i produktloggarna
- Aktivera automatiska säkerhetsintelligensuppdateringar
- Aktivera moln levererat skydd
- Aktivera automatisk exempelinskick på `safe` nivå

### <a name="sample-profile"></a>Exempelprofil

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>Exempel på fullständig konfigurationsprofil

Följande konfigurationsprofil innehåller poster för alla inställningar som beskrivs i det här dokumentet och kan användas för mer avancerade scenarier där du vill ha mer kontroll över produkten.

### <a name="full-profile"></a>Fullständig profil

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a>Validering av konfigurationsprofil

Konfigurationsprofilen måste vara en giltig JSON-formaterad fil. Det finns ett antal verktyg som kan användas för att verifiera detta. Om du till exempel har `python` installerat på enheten:

```bash
python -m json.tool mdatp_managed.json
```

Om JSON-koden är rätt utformad matar kommandot ovan ut den tillbaka till terminalen och returnerar en utgångskod för `0` . Annars visas ett fel som beskriver problemet och kommandot returnerar en utgångskod för `1` .

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>Verifiera att filen mdatp_managed.jsfungerar som förväntat
Kontrollera att din /etc/opt/microsoft/mdatp/managed/mdatp_managed.jsfungerar korrekt genom att se "[managed]" bredvid de här inställningarna:  
- cloud_enabled
- cloud_automatic_sample_submission_consent
- passice_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> För mdatp_managed.jsatt börja gälla krävs ingen omstart av wdavdaemon.

## <a name="configuration-profile-deployment"></a>Konfigurationsprofildistribution

När du har skapat konfigurationsprofilen för ditt företag kan du distribuera den via det hanteringsverktyg som företaget använder. Defender för Endpoint för Linux läser den hanterade konfigurationen från *filen /etc/opt/microsoft/mdatp/managed/mdatp_managed.js.*
