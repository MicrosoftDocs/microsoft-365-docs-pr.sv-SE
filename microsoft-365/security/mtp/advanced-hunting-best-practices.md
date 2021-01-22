---
title: Avancerade metodtips för sökfrågor i Microsoft 365 Defender
description: Lär dig att konstruera snabba, effektiva och felfria hot för sökning med avancerad sökning
keywords: avancerad sökning, hotsökning, cyberhot, schema, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schema, kusto, undvika timeout, kommandorader, process-id, optimera, bästa praxis, parse, gå med, sammanfatta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: cc6110cdd7dd71f80f6897cfbb0026ccce301cf7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928480"
---
# <a name="advanced-hunting-query-best-practices"></a>Avancerade metodtips för sökfrågor

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Använd de här rekommendationerna för att få resultat snabbare och undvika timeouts när du kör komplexa frågor. Mer vägledning om hur du förbättrar frågeprestanda finns i bästa praxis [för Kusto-frågor.](https://docs.microsoft.com/azure/kusto/query/best-practices)

## <a name="understand-cpu-resource-quotas"></a>Förstå CPU-resurskvoter
Beroende på storleken har varje innehavare tillgång till en viss mängd CPU-resurser som tilldelats för att köra avancerade sökfrågor. Detaljerad information om olika tjänstbegränsningar finns [i läsa om avancerade sökkvoter och användningsparametrar.](advanced-hunting-limits.md)

Kunder som kör flera frågor regelbundet bör spåra förbrukning och använda optimeringsvägledningen i den här artikeln för att minimera avbrottet som en följd av att kvoter eller användningsparametrar överskrids.

## <a name="general-optimization-tips"></a>Allmänna optimeringstips

- **Ändra storlek på nya frågor**– om du misstänker att en fråga kommer att returnera en stor resultatuppsättning bedömer du den först med hjälp av [antal-operatorn.](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator) Använd [begränsningen](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) eller dess synonym `take` för att undvika stora resultatuppsättningar.
- Använd filter tidigt – Använd tidsfilter och andra filter för att minska datauppsättningen, särskilt innan du använder omvandlings- och tolkningsfunktioner, till exempel [understräng()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [ersätt()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [rensa()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)eller [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). I exemplet nedan används parsingfunktionen [extractjson()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) när filtreringsoperatorer har minskat antalet poster.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Has beats contains**– To avoid searching substrings within words unnecessarily, use the `has` operator instead of `contains` . [Läs mer om strängoperatorer](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Titta i specifika kolumner –** titta i en specifik kolumn i stället för att köra fullständiga textsökningar i alla kolumner. Använd inte för `*` att kontrollera alla kolumner.
- **Case-sensitive for speed**– Case-sensitive searches are more specific and generally more performant. Namn på case-känsliga [strängoperatorer,](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)t.ex. `has_cs` `contains_cs` och, slutar vanligtvis `_cs` med. Du kan också använda operatorn case-sensitive equals `==` i stället för `=~` .
- **Tolka, extrahera inte**– När det är möjligt använder du [parsoperatorn](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) eller en tolkningsfunktion som [parse_json()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Undvik `matches regex` strängoperatorn eller [extrahera()-funktionen,](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction)som båda använder reguljära uttryck. Reservera användningen av reguljära uttryck för mer komplexa scenarier. [Läs mer om tolkningsfunktioner](#parse-strings)
- **Filtrera tabeller som inte** är uttryck. Filtrera inte efter en beräknad kolumn om du kan filtrera på en tabellkolumn.
- **Inga termer med tre tecken**– undvik att jämföra eller filtrera med termer med tre tecken eller färre. De här termerna indexeras inte och för att de ska matchas krävs fler resurser.
- **Projicera** selektivt – gör resultatet enklare att förstå genom att projicera endast de kolumner du behöver. Att projicera specifika kolumner innan [du kör koppling](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) eller liknande åtgärder ger också bättre prestanda.

## <a name="optimize-the-join-operator"></a>Optimera `join` operatorn
[Kopplingsoperatorn](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) slår ihop rader från två tabeller genom att matcha värden i angivna kolumner. Använd de här tipsen för att optimera frågor som använder den här operatorn.

- **Mindre tabell till vänster –** Operatorn matchar poster i tabellen till vänster om `join` kopplingsutdraget till poster till höger. Genom att ha den mindre tabellen till vänster behöver färre poster matchas, vilket gör frågan snabbare. 

    I tabellen nedan minskar vi den vänstra tabellen så att den bara omfattar tre specifika enheter innan du ansluter till den med hjälp av `DeviceLogonEvents` `IdentityLogonEvents` konto-SID.
 
    ```kusto
    DeviceLogonEvents 
    | where DeviceName in ("device-1.domain.com", "device-2.domain.com", "device-3.domain.com")
    | where ActionType == "LogonFailed"
    | join
        (IdentityLogonEvents
        | where ActionType == "LogonFailed"
        | where Protocol == "Kerberos")
    on AccountSid
    ```

- **Använd** en inre kopplingssmaksmak – Standardkopplingen eller [den inre](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) kopplingskopplingen deduplicerar rader i den vänstra tabellen genom kopplingsnyckeln innan du returnerar en rad för varje matchning till den högra tabellen. [](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) Om den vänstra tabellen har flera rader med samma värde för nyckeln, de raderna dedupliceras till att lämna en enda slumpmässig rad för `join` varje unikt värde.

    Med det här standardbeteendet kan viktig information från den vänstra tabellen visas som användbar information. Frågan nedan visar till exempel bara ett e-postmeddelande som innehåller en viss bifogad fil, även om samma bifogade fil skickades med flera e-postmeddelanden:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    För att åtgärda den här begränsningen tillämpar vi [den inre join-smakerna](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) genom att ange att alla rader i den vänstra tabellen `kind=inner` ska visas med matchande värden till höger:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Gå med i poster från ett** tidsfönster – När säkerhetshändelser undersöks letar analytiker efter relaterade händelser som inträffar under samma tidsperiod. Tillämpa samma metod när du också `join` använder prestandan genom att minska antalet poster som ska kontrolleras.
    
    Frågan nedan söker efter inloggningshändelser inom 30 minuter efter att en skadlig fil mottagits:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where MalwareFilterVerdict == "Malware" 
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Använd tidsfilter** på båda sidor – Även om du inte undersöker ett specifikt tidsperioder kan användning av tidsfilter på både den vänstra och den högra tabellen minska antalet poster för att kontrollera och förbättra `join` prestanda. Frågan nedan gäller för `Timestamp > ago(1h)` båda tabellerna så att den bara sammanför poster från den senaste timmen:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Använd tips för prestanda –** Använd tips med operatorn för att instruera backend att fördela belastningen när du kör `join` resursintensiva åtgärder. [Läs mer om tips om kopplingar](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Med slumpningen **[](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** kan du till exempel förbättra frågeprestandan när du sammanfogar tabeller med en tangent med hög kardinalitet – en nyckel med många unika värden – som i `AccountObjectId` frågan nedan:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    **[Sändningstipset](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** hjälper när den vänstra tabellen är liten (upp till 100 000 poster) och den högra tabellen är extremt stor. Frågan nedan försöker till exempel ansluta till några e-postmeddelanden som har specifika ämnen med _alla meddelanden_ som innehåller länkar i `EmailUrlInfo` tabellen:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Optimera `summarize` operatorn
[Summeringsoperatorn](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregerar innehållet i en tabell. Använd de här tipsen för att optimera frågor som använder den här operatorn.

- **Hitta distinkta värden**– använd i allmänhet för `summarize` att hitta distinkta värden som kan vara återkommande. Det kan vara onödigt att använda det för att sammanställa kolumner som inte har återkommande värden.

    Även om ett enskilt e-postmeddelande kan vara  en del av flera händelser är exemplet nedan inte ett effektivt sätt att använda, eftersom ett nätverksmeddelande-ID för ett enskilt e-postmeddelande alltid levereras med `summarize` en unik avsändaradress.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    Operatorn `summarize` kan enkelt ersättas `project` med, vilket potentiellt ger samma resultat samtidigt som du använder färre resurser:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Följande exempel är ett effektivare användnings sätt eftersom det kan finnas flera distinkta instanser av en avsändaradress som skickar `summarize` e-post till samma mottagaradress. Sådana kombinationer är mindre distinkta och kommer sannolikt att ha dubbletter.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Blanda frågan –** även om den bäst används i kolumner med repetitiva värden, kan samma kolumner också ha `summarize` hög _kardinalitet_ eller stora mängder unika värden. Precis som operatorn kan du även använda slumptipset för att fördela belastningen och potentiellt förbättra prestanda när du arbetar på `join` kolumner med hög [](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) `summarize` kardinalitet.

    Frågan nedan används för `summarize` att räkna distinkta mottagares e-postadresser, som kan köras i hundratusentals i stora organisationer. För att förbättra prestanda `hint.shufflekey` ingår:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Frågescenarier

### <a name="identify-unique-processes-with-process-ids"></a>Identifiera unika processer med process-ID
Process-ID :n (PIDs) återanvänds i Windows och återanvänds för nya processer. På egen hand kan de inte fungera som unika identifierare för specifika processer.

Om du vill unik identifierare för en process på en viss dator kan du använda process-ID:t tillsammans med tiden då processen skapades. När du sammanfogar eller sammanfattar data runt processer kan du ta med kolumner för maskinidentifieraren (eller), process-ID ( eller ) och tiden då processen skapades `DeviceId` `DeviceName` `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` (eller)

Följande exempelfråga hittar processer som har åtkomst till fler än 10 IP-adresser via port 445 (SMB), eventuellt genomsökning efter filresurser.

Exempelfråga:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

Frågan sammanfattas av både och så att den tittar på `InitiatingProcessId` `InitiatingProcessCreationTime` en enda process, utan att blanda flera processer med samma process-ID.

### <a name="query-command-lines"></a>Kommandorader för fråga
Det finns flera sätt att skapa en kommandorad för att utföra en aktivitet. En attack kan till exempel referera till en bildfil utan sökväg, utan filnamnstillägg, använda miljövariabler eller med citattecken. Attacken kan också ändra ordningen på parametrar eller lägga till flera citattecken och blanksteg.

Använd följande metoder för att skapa mer beständiga frågor kring kommandorader:

- Identifiera kända processer (till exempel *net.exe* eller *psexec.exe)* genom att matcha på filnamnsfälten i stället för att filtrera på själva kommandoraden.
- Tolka kommandoradsavsnitt med funktionen [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Vid sökning efter kommandoradsargument bör du inte söka efter en exakt matchning för flera orelaterade argument i en viss ordning. Använd i stället reguljära uttryck eller använd flera separata operatorer.
- Använd okänsliga matchningar. Du kan till exempel `=~` använda , och i stället för , och `in~` `contains` `==` `in` `contains_cs` .
- Överväg att ta bort citattecken, ersätta kommatecken med blanksteg och ersätta flera på varandra följande blanksteg med ett enda blanksteg för att minimera teknikerna för kommandoradskommunikation. Det finns mer komplexa förvirringstekniker som kräver andra metoder, men de här justeringarna kan vara till stor hjälp för vanliga.

Följande exempel visar olika sätt att skapa en fråga som söker efter filen *inet.exe* för att stoppa brandväggstjänsten "MpsSvc":

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on file name, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

### <a name="ingest-data-from-external-sources"></a>Mata in data från externa källor
Om du vill infoga långa listor eller stora tabeller i frågan använder du operatorn [externa data](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) för att mata in data från en viss URI. Du kan hämta data från filer i TXT, CSV, JSON eller [andra format.](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats) Exemplet nedan visar hur du kan använda den omfattande listan med SHA-256-hashtaggar för skadlig programvara som tillhandahålls av MalwareBazaar (abuse.ch) för att kontrollera bifogade filer i e-postmeddelanden:

```kusto
let abuse_sha256 = (externaldata(sha256_hash: string )
[@"https://bazaar.abuse.ch/export/txt/sha256/recent/"]
with (format="txt"))
| where sha256_hash !startswith "#"
| project sha256_hash;
abuse_sha256
| join (EmailAttachmentInfo 
| where Timestamp > ago(1d) 
) on $left.sha256_hash == $right.SHA256
| project Timestamp,SenderFromAddress,RecipientEmailAddress,FileName,FileType,
SHA256,MalwareFilterVerdict,MalwareDetectionMethod
```

### <a name="parse-strings"></a>Tolka strängar
Det finns olika funktioner som du kan använda för att effektivt hantera strängar som behöver parsing eller konvertering. 

| Sträng | Funktion | Användningsexempel |
|--|--|--|
| Kommandorader | [parse_command_line()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Extrahera kommandot och alla argument. | 
| Sökvägar | [parse_path()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Extrahera avsnitten i sökvägen till en fil eller mapp. |
| Versionsnummer | [parse_version()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Deconconstruct a version number with up to four sections and up to eight characters per section. Använd tolkade data för att jämföra versions ålder. |
| IPv4-adresser | [parse_ipv4()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Konvertera en IPv4-adress till ett långt heltal. Om du vill jämföra IPv4-adresser utan att konvertera dem använder [du ipv4_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| IPv6-adresser | [parse_ipv6()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Konvertera en IPv4- eller IPv6-adress till den kanoniska IPv6-notationen. Om du vill jämföra IPv6-adresser använder [du ipv6_compare()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Mer information om alla tolkningsfunktioner som stöds finns [i kustosträngfunktionerna.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions) 

## <a name="related-topics"></a>Relaterade ämnen
- [Språkdokumentation för kustofrågor](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Kvoter och användningsparametrar](advanced-hunting-limits.md)
- [Hantera avancerade sökfel](advanced-hunting-errors.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
