---
title: Undersök enheter på enheter med livesvar i Microsoft Defender för Slutpunkt
description: Få tillgång till en enhet som använder en säker anslutning med fjärrgränssnitt för att utföra en undersökning och vidta åtgärder för omedelbar respons på en enhet i realtid.
keywords: remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file,
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4898081103faa27c19d3a09ffba1b59670833dd8
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860803"
---
# <a name="investigate-entities-on-devices-using-live-response"></a>Undersök enheter på enheter med live-svar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Live Response ger säkerhetsoperationer direktåtkomst till en enhet (kallas även dator) med en fjärrgränssnittsanslutning. Det ger dig möjlighet att göra djupgående undersökningsarbete och vidta omedelbart åtgärder för att snabbt identifiera hot – i realtid. 

Live response är utformat för att förbättra undersökningar genom att göra det möjligt för säkerhetsgruppen att samla in tekniska data, köra skript, skicka misstänkta enheter för analys, åtgärda hot och proaktivt leta efter nya hot.<br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

Med live-svar kan analytiker göra följande:
- Kör grundläggande och avancerade kommandon för att göra saker på en enhet.
- Ladda ned filer som exempel på skadlig programvara och resultat av PowerShell-skript.
- Ladda ned filer i bakgrunden (nytt!).
- Ladda upp ett PowerShell-skript eller körbart till biblioteket och kör det på en enhet från klientorganisationsnivå.
- Vidta eller ångra åtgärder.

## <a name="before-you-begin"></a>Innan du börjar

Innan du kan starta en session på en enhet kontrollerar du att du uppfyller följande krav:

- **Kontrollera att du kör en version av Windows som stöds.** <br/>
Enheter måste köra någon av följande versioner av Windows

  - **Windows 10**
    - [Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) eller senare  
    - [Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) med [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)
    - [Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) [med KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    - [Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) med [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) med [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)
  
  - **Windows Server 2019 – endast tillämpligt för offentlig förhandsversion**
    - Version 1903 eller (med [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) senare 
    - Version 1809 (med [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))

- **Aktivera livesvar från sidan avancerade inställningar**.<br>
Du måste aktivera svarsfunktion på sidan Avancerade [funktioner.](advanced-features.md)

    >[!NOTE]
    >Endast användare med administratörsroller för säkerhet och global administration kan redigera de här inställningarna.

- **Aktivera live-svar för servrar från sidan avancerade inställningar** (rekommenderas).<br>

    >[!NOTE]
    >Endast användare med administratörsroller för säkerhet och global administration kan redigera de här inställningarna.
    
- **Kontrollera att enheten har en nivå för automatiseringsreparation tilldelad**.<br>
Du måste minst aktivera den lägsta åtgärdsnivån för en viss enhetsgrupp. Annars kommer du inte att kunna upprätta en Live Response-session för en medlem i den gruppen.

    Du får följande felmeddelande:

    ![Bild på felmeddelande](images/live-response-error.png)

- **Aktivera körning av skript som inte tilldelats med Live Response** (valfritt). <br>

    >[!WARNING]
    >Om du tillåter användning av osignerade skript kan din exponering öka för hot.
 
  Vi rekommenderar inte att du kör osignerade skript eftersom det kan öka exponeringen mot hot. Om du måste använda dem måste du aktivera inställningen på sidan [Avancerade inställningar.](advanced-features.md)
    
- **Kontrollera att du har rätt behörigheter.**<br>
    Endast användare som har etablerats med rätt behörighet kan starta en session. Mer information om rolltilldelningar finns i [Skapa och hantera roller.](user-roles.md) 

    > [!IMPORTANT]
    > Alternativet för att ladda upp en fil till biblioteket är bara tillgängligt för dem med rätt behörighet för RBAC. Knappen är nedtonad för användare som endast har delegerade behörigheter.

    Beroende på vilken roll du har beviljats kan du köra grundläggande eller avancerade kommandon för livesvar. Användarbehörigheter styrs av den anpassade rollen RBAC. 

## <a name="live-response-dashboard-overview"></a>Översikt över instrumentpanelen för livesvar
När du startar en svarssession på en enhet öppnas en instrumentpanel. På instrumentpanelen finns information om sessionen, till exempel följande: 

- Vem skapade sessionen
- När sessionen startades
- Sessionens varaktighet

Instrumentpanelen ger dig också tillgång till:
- Koppla från session
- Ladda upp filer till biblioteket 
- Kommandokonsol
- Kommandologg


## <a name="initiate-a-live-response-session-on-a-device"></a>Starta en svarssession i live på en enhet 

1. Logga in på Microsoft Defender Säkerhetscenter.

2. Gå till sidan enhetslista och välj en enhet du vill undersöka. Sidan Enheter öppnas.

3. Starta livesvarssessionen genom att **välja Initiera svarssession i direktsändning.** En kommandokonsol visas. Vänta medan sessionen ansluts till enheten.

4. Använd de inbyggda kommandona för att göra det här. Mer information finns i [Live response-kommandon](#live-response-commands).

5. När du har slutfört din undersökning väljer **du Koppla från session** och sedan **Bekräfta**.

## <a name="live-response-commands"></a>Kommandon för livesvar

Beroende på vilken roll du har beviljats kan du köra grundläggande eller avancerade kommandon för livesvar. Användarbehörigheter styrs av anpassade rollerna i RBAC. Mer information om rolltilldelningar finns i [Skapa och hantera roller.](user-roles.md) 


>[!NOTE]
>Live response är ett molnbaserat interaktivt gränssnitt som exempelvis kan specifika kommandogränssnitt variera vad gäller svarstider beroende på nätverkskvalitet och systembelastning mellan slutanvändaren och målenheten.

### <a name="basic-commands"></a>Grundläggande kommandon

Följande kommandon är tillgängliga för användarroller som ges möjlighet att köra **grundläggande kommandon** för livesvar. Mer information om rolltilldelningar finns i [Skapa och hantera roller.](user-roles.md) 

| Kommando | Beskrivning |
|---|---|--- |
|`cd` | Ändrar den aktuella katalogen. | 
|`cls` | Tar bort konsolskärmen.  |
|`connect` | Startar en svarssession i direktsändning på enheten. |
|`connections` | Visar alla aktiva anslutningar. |
|`dir` | Visar en lista med filer och undermappar i en katalog. |
|`download <file_path> &` | En fil laddas ned i bakgrunden. |
|`drivers` |  Visar alla drivrutiner som är installerade på enheten. |
|`fg <command ID>` | Placera det angivna jobbet i förgrunden, vilket gör det till aktuellt jobb. <br> Obs! FG tar ett kommando-ID som är tillgängligt från jobb, inte från PID |
|`fileinfo` | Hämta information om en fil. |
|`findfile` | Söker efter ett namn på enheten. |
|`getfile <file_path>` | En fil laddas ned. |
|`help` | Innehåller hjälpinformation för livesvarskommandon. |
|`jobs` | Visar jobb som körs, deras ID och status. |
|`persistence` | Visar alla kända beständighetsmetoder på enheten. |
|`processes` | Visar alla processer som körs på enheten. |
|`registry` | Visar registervärden. |
|`scheduledtasks` | Visar alla schemalagda uppgifter på enheten. |
|`services` | Visar alla tjänster på enheten. |
|`trace` | Ställer in terminalens loggningsläge för felsökning. |

### <a name="advanced-commands"></a>Avancerade kommandon
Följande kommandon är tillgängliga för användarroller som ges möjlighet att köra **avancerade svarskommandon.** Mer information om rolltilldelningar finns i [Skapa och hantera roller.](user-roles.md) 

| Kommando | Beskrivning |
|---|---|
| `analyze` | Analyserar enheten med olika informationsmotorer för att nå ett omdöme. |
| `run` | Kör ett PowerShell-skript från biblioteket på enheten. |
| `library` | Visar filer som har laddats upp till livesvarsbiblioteket. |
| `putfile` | Lägger till en fil från biblioteket till enheten. Filer sparas i en arbetsmapp och tas bort när enheten startas om som standard. |
| `remediate` | Åtgärdar en enhet på enheten. Åtgärdsåtgärden varierar beroende på entitetstyp:<br>- Arkiv: ta bort<br>- Process: stopp, ta bort bildfil<br>- Tjänst: stoppa, ta bort bildfil<br>- Registerpost: ta bort<br>- Schemalagd aktivitet: ta bort<br>- Mappobjekt vid start: ta bort fil <br> Obs! Det här kommandot har ett kommando som krävs. Du kan använda kommandot `-auto` tillsammans med för att automatiskt köra kommandot som `remediate` krävs. 
|`undo` | Återställer en enhet som har åtgärdats. |


## <a name="use-live-response-commands"></a>Använda kommandon för livesvar

De kommandon som du kan använda i konsolen följer liknande principer som [Windows-kommandon.](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)

Med avancerade kommandon får du en robustare uppsättning åtgärder som gör att du kan vidta mer kraftfulla åtgärder, till exempel ladda ned och ladda upp en fil, köra skript på enheten och vidta åtgärder för en enhet.

### <a name="get-a-file-from-the-device"></a>Hämta en fil från enheten

För scenarier när du vill hämta en fil från en enhet som du undersöker kan du använda `getfile` kommandot. På så sätt kan du spara filen från enheten för ytterligare undersökning.

>[!NOTE]
>Följande filstorleksbegränsningar gäller:
>- `getfile` gräns: 3 GB
>- `fileinfo` gräns: 10 GB
>- `library` gräns: 250 MB

### <a name="download-a-file-in-the-background"></a>Ladda ned en fil i bakgrunden

Filerna kan nu laddas ned i bakgrunden så att teamet med säkerhetsåtgärder kan fortsätta att undersöka en påverkade enhet.

- Om du vill ladda ned en fil i bakgrunden skriver du . `download <file_path> &`
- Om du väntar på att en fil ska laddas ned kan du flytta den till bakgrunden genom att använda Ctrl + Z.
- Om du vill föra in en filnedladdning i förgrunden skriver du `fg <command_id>` .

Här är några exempel:


|Kommando  |Vad den gör  |
|---------|---------|
|`Download "C:\windows\some_file.exe" &`     |Börjar ladda ned en fil med *namnetsome_file.exe* fil i bakgrunden.         |
|`fg 1234`     |Returnerar en nedladdning med kommando-ID *1234 till* förgrunden.         |


### <a name="put-a-file-in-the-library"></a>Placera en fil i biblioteket

Live response har ett bibliotek där du kan placera filer i. Biblioteket lagrar filer (till exempel skript) som kan köras i en svarssession i direktsändning på klientorganisationsnivå.

Med Live Response kan PowerShell-skript köras, men du måste först placera filerna i biblioteket innan du kan köra dem. 

Du kan ha en samling PowerShell-skript som kan köras på enheter som du startar svarssessioner med i direktsändning. 

#### <a name="to-upload-a-file-in-the-library"></a>Ladda upp en fil i biblioteket

1. Klicka **på Ladda upp fil till bibliotek**. 

2. Klicka **på** Bläddra och markera filen.

3. Ge en kort beskrivning.

4. Ange om du vill skriva över en fil med samma namn.

5. Om du vill vara det ska du veta vilka parametrar som krävs för skriptet, markera kryssrutan skriptparametrar. I textfältet anger du ett exempel och en beskrivning.

6. Klicka **på Bekräfta.** 

7. (Valfritt) Kör kommandot för att verifiera att filen har laddats upp till `library` biblioteket.


### <a name="cancel-a-command"></a>Avbryta ett kommando
När som helst under en session kan du avbryta ett kommando genom att trycka på CTRL + C.  

>[!WARNING]
>Om du använder den här genvägen stoppas inte kommandot på agentsidan. Det avbryter bara kommandot i portalen. Så om du ändrar åtgärder som "åtgärd" kan det fortsätta medan kommandot avbryts. 

### <a name="automatically-run-prerequisite-commands"></a>Köra nödvändiga kommandon automatiskt

Vissa kommandon har nödvändiga kommandon för att köras. Om du inte kör det nödvändiga kommandot får du ett felmeddelande. Om du till exempel kör `download` kommandot utan `fileinfo` returneras ett fel.

Du kan använda flagga automatiskt för att automatiskt köra nödvändiga kommandon, till exempel:

```console
getfile c:\Users\user\Desktop\work.txt -auto
```

## <a name="run-a-powershell-script"></a>Köra ett PowerShell-skript 

Innan du kan köra ett PowerShell-skript måste du först ladda upp det till biblioteket. 

När skriptet har laddats upp till biblioteket använder du `run` kommandot för att köra skriptet.

Om du tänker använda ett osignerat skript i sessionen måste du aktivera inställningen på sidan [Avancerade inställningar för](advanced-features.md) funktioner.

>[!WARNING]
>Om du tillåter användning av osignerade skript kan din exponering öka för hot.

## <a name="apply-command-parameters"></a>Använda kommandoparametrar

- Läs konsolhjälpen om du vill lära dig mer om kommandoparametrar. Om du vill lära dig mer om ett enskilt kommando kör du:
 
    `help <command name>`

- Observera att parametrar hanteras utifrån en fast ordning när du tillämpar parametrar på kommandon:
 
    `<command name> param1 param2` 

- När du anger parametrar utanför den fasta ordningen ska du ange namnet på parametern med ett bindestreck innan du anger värdet:
 
    `<command name> -param2_name param2`

- När du använder kommandon som har nödvändiga kommandon kan du använda flaggor:

    `<command name> -type file -id <file path> - auto` eller `remediate file <file path> - auto` .

## <a name="supported-output-types"></a>Utdatatyper som stöds

Live Response har stöd för utdatatyper i tabell och JSON-format. För varje kommando finns det ett standardbeteende för utdata. Du kan ändra utdata i det valda utdataformatet med följande kommandon:

- `-output json`
- `-output table`

>[!NOTE]
>Färre fält visas i tabellformat på grund av det begränsade utrymmet. Om du vill se mer information i resultatet kan du använda JSON-utdatakommandot så att mer information visas.

## <a name="supported-output-pipes"></a>Utdatarör som stöds

Live Response har stöd för utdata piping till CLI och fil. CLI är standardbeteendet för utdata. Du kan pipa utdata till en fil med följande kommando: [kommando] > [filnamn].txt.  

Exempel:

```console
processes > output.txt
```

## <a name="view-the-command-log"></a>Visa kommandologgen

Välj fliken **Kommandologg** för att se de kommandon som används på enheten under en session. Varje kommando spåras med fullständig information som:
- ID
- Kommandorad
- Varaktighet
- Status och inmatnings- eller utdatas sidofält

## <a name="limitations"></a>Begränsningar

- Livesvarssessioner är begränsade till 25 livesvarssessioner åt gången.
- Värdet för inaktiv timeout för livesvarssession är 30 minuter. 
- En användare kan starta upp till 10 samtidiga sessioner.
- En enhet kan bara vara i en session i taget.
- Följande filstorleksbegränsningar gäller:
   - `getfile` gräns: 3 GB
   - `fileinfo` gräns: 10 GB
   - `library` gräns: 250 MB

## <a name="related-article"></a>Relaterad artikel
- [Kommandoexempel för livesvar](live-response-command-examples.md)
