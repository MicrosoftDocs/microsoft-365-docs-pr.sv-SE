---
title: Avancerade metodtips för sökning i Microsoft 365 Defender
description: Lär dig hur du skapar snabba, effektiva och felfria hotförfrågningar med avancerad sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema, kusto, avoid timeout, command lines, process-id, optimize, best practice, parse, join, summarize
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: abc6b561c2fca8106397b1656432628c983e2ece
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952698"
---
# <a name="advanced-hunting-query-best-practices"></a>Avancerade metodtips för sökningsfrågor

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Använd de här rekommendationerna för att få resultat snabbare och undvika tidsgränser när du kör komplexa frågor. Mer vägledning om hur du förbättrar frågeprestanda finns [i Metodtips för Kusto-frågor.](/azure/kusto/query/best-practices)

## <a name="understand-cpu-resource-quotas"></a>Förstå kvoter för CPU-resurser
Beroende på klientorganisationens storlek har varje klientorganisation tillgång till en viss mängd CPU-resurser som tilldelats för avancerade sökfrågor. Detaljerad information om olika tjänstbegränsningar finns [i mer information om avancerade kvoter för sökning och användningsparametrar.](advanced-hunting-limits.md)

Kunder som kör flera frågor regelbundet bör spåra förbrukning och använda optimeringsvägledningen i den här artikeln för att minimera avbrottet som ett resultat av att kvoter eller användningsparametrar överskrids.

## <a name="general-optimization-tips"></a>Allmänna optimeringstips

- **Storlek på nya frågor –** Om du misstänker att en fråga kommer att returnera en stor resultatuppsättning bör du utvärdera den först med hjälp av [antal-operatorn](/azure/data-explorer/kusto/query/countoperator). Använd [begränsningen](/azure/data-explorer/kusto/query/limitoperator) eller dess synonym `take` för att undvika stora resultatuppsättningar.
- **Använda filter** tidigt – Använd tidsfilter och andra filter för att minska datauppsättningen, särskilt innan du använder omvandlings- och parsningsfunktioner, t.ex. [understräng()](/azure/data-explorer/kusto/query/substringfunction), [ersätt()](/azure/data-explorer/kusto/query/replacefunction), [rensa()](/azure/data-explorer/kusto/query/trimfunction), [toupper()](/azure/data-explorer/kusto/query/toupperfunction) [eller parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). I exemplet nedan används tolkningsfunktionen [extractjson()](/azure/data-explorer/kusto/query/extractjsonfunction) när filtreringsoperatorer har minskat antalet poster.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Har beats innehåller .** Du kan undvika att söka efter understrängar i ord i onödan genom att använda `has` operatorn i stället för `contains` . [Lär dig mer om strängoperatorer](/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Titta i specifika kolumner –** Leta i en specifik kolumn i stället för att köra en fullständig textsökning i alla kolumner. Använd inte för `*` att kontrollera alla kolumner.
- **Case-sensitive for speed**– Case-sensitive searches are more specific and generally more performant. Namnen på de [case-känsliga strängoperatorer](/azure/data-explorer/kusto/query/datatypes-string-operators)som exempelvis `has_cs` och , vanligtvis slutar med `contains_cs` `_cs` . Du kan också använda operatorn case-sensitive equals `==` i stället för `=~` .
- **Tolka, extrahera inte**– När det är möjligt använder du [parsoperatorn](/azure/data-explorer/kusto/query/parseoperator) eller en tolkningsfunktion som [parse_json()](/azure/data-explorer/kusto/query/parsejsonfunction). Undvik `matches regex` strängoperatorn eller [extrahera()-funktionen,](/azure/data-explorer/kusto/query/extractfunction)som båda använder reguljära uttryck. Reservera användningen av reguljära uttryck för mer komplexa scenarier. [Läs mer om tolkningsfunktioner](#parse-strings)
- **Filtrera tabeller och inte** uttryck – Filtrera inte efter en beräknad kolumn om du kan filtrera på en tabellkolumn.
- **Inga termer med tre tecken**– Undvik att jämföra eller filtrera med hjälp av termer med tre tecken eller färre. Termerna indexeras inte och för att de ska matchas krävs fler resurser.
- **Project selektivt**– Gör resultatet enklare att förstå genom att projicera endast de kolumner du behöver. Att projicera specifika kolumner innan [du kör koppling](/azure/data-explorer/kusto/query/joinoperator) eller liknande åtgärder ger också bättre prestanda.

## <a name="optimize-the-join-operator"></a>Optimera `join` operatorn
[Kopplingsoperatorn](/azure/data-explorer/kusto/query/joinoperator) slår samman rader från två tabeller genom att matcha värden i angivna kolumner. Använd de här tipsen om du vill optimera frågor som använder den här operatorn.

- **Mindre tabell till vänster –** Operatorn matchar poster i tabellen på vänster sida av kopplingssatsen till poster till `join` höger. Genom att ha den mindre tabellen till vänster behöver färre poster matchas, vilket gör frågan snabbare. 

    I tabellen nedan ser vi till att den vänstra tabellen endast omfattar tre specifika enheter innan du ansluter `DeviceLogonEvents` till den med via `IdentityLogonEvents` konto-SID.
 
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

- **Använd den inre join-smak**– Standard för join-smak eller [innerunique-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) deduplicerar rader i den vänstra tabellen med kopplingstangenten innan du returnerar en rad för varje matchning till höger tabell. [](/azure/data-explorer/kusto/query/joinoperator#join-flavors) Om den vänstra tabellen har flera rader med samma värde för nyckeln de här raderna dedupliceras till att lämna en enda `join` slumpmässig rad för varje unikt värde.

    Den här standardbeteendet kan lämna viktig information från den vänstra tabellen som kan ge användbar insyn. Frågan nedan visar till exempel bara ett e-postmeddelande som innehåller en viss bifogad fil, även om samma bifogade fil skickades med flera e-postmeddelanden:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    För att åtgärda den här begränsningen tillämpar vi [den inre join-smak](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) genom att ange att alla rader i den vänstra tabellen ska visas `kind=inner` med matchande värden till höger:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Koppla poster från ett tidsfönster**– När analytiker undersöker säkerhetshändelser letar analytiker efter relaterade händelser som inträffar under samma tidsperiod. Tillämpa samma metod när du också `join` använder fördelar prestanda genom att minska antalet poster att kontrollera.
    
    Med frågan nedan söker du efter inloggningshändelser inom 30 minuter efter att en skadlig fil mottagits:

    ```kusto
    EmailEvents
    | where Timestamp > ago(7d)
    | where ThreatTypes has "Malware"
    | project EmailReceivedTime = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0])
    | join (
    DeviceLogonEvents 
    | where Timestamp > ago(7d)
    | project LogonTime = Timestamp, AccountName, DeviceName
    ) on AccountName 
    | where (LogonTime - EmailReceivedTime) between (0min .. 30min)
    ```
- **Använda tidsfilter på** båda sidor – Även om du inte undersöker ett visst tidsfönster kan du minska antalet poster för att kontrollera och förbättra prestanda genom att använda tidsfilter på både den vänstra och den högra `join` tabellen. Frågan nedan gäller för `Timestamp > ago(1h)` båda tabellerna så att den bara sammanför poster från den senaste timmen:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Använd tips för prestanda –** Använd tips med operatorn för att instruera backend att fördela belastningen när du kör `join` resursintensiva åtgärder. [Läs mer om kopplingstips](/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Med slumpningen **[](/azure/data-explorer/kusto/query/shufflequery)** kan du till exempel förbättra frågeprestandan när du sammanfogar tabeller med en tangent med hög kardinalitet – en nyckel med många unika värden – som i `AccountObjectId` frågan nedan:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    **[Sändningstipset](/azure/data-explorer/kusto/query/broadcastjoin)** hjälper när den vänstra tabellen är liten (upp till 100 000 poster) och den högra tabellen är extremt stor. Frågan nedan försöker till exempel ansluta till några e-postmeddelanden som har specifika ämnen med _alla_ meddelanden som innehåller länkar i `EmailUrlInfo` tabellen:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Optimera `summarize` operatorn
[Summeringsoperatorn](/azure/data-explorer/kusto/query/summarizeoperator) aggregerar innehållet i en tabell. Använd de här tipsen om du vill optimera frågor som använder den här operatorn.

- **Hitta distinkta värden**– Använd i allmänhet för `summarize` att hitta distinkta värden som kan upprepas. Det kan vara onödigt att använda den för att sammanställa kolumner som inte har repetitiva värden.

    Även om ett enskilt e-postmeddelande kan vara  en del av flera händelser är exemplet nedan inte effektivt, eftersom ett nätverksmeddelande-ID för ett enskilt e-postmeddelande alltid levereras med en `summarize` unik avsändaradress.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    Operatorn `summarize` kan enkelt ersättas med , vilket `project` eventuellt ger samma resultat samtidigt som färre resurser används:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Följande exempel är ett mer effektivt sätt att använda eftersom det kan finnas flera distinkta instanser av en avsändaradress som skickar `summarize` e-post till samma mottagaradress. Sådana kombinationer är mindre distinkta och kan ha dubbletter.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- **Blanda frågan –** Även om den bäst används i kolumner med repetitiva värden, kan samma kolumner också ha hög `summarize` _kardinalitet_ eller ett stort antal unika värden. Precis som operatorn kan du även använda slumpa aningen med för att fördela belastningen och potentiellt förbättra prestandan när du `join` arbetar med kolumner med hög [](/azure/data-explorer/kusto/query/shufflequery) `summarize` kardinalitet.

    Frågan nedan använder för `summarize` att räkna distinkta mottagares e-postadress, som kan köras i hundratals tusentals i stora organisationer. För att förbättra prestanda omfattar `hint.shufflekey` det:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Frågescenarier

### <a name="identify-unique-processes-with-process-ids"></a>Identifiera unika processer med process-ID
Process-ID:n (PID) återanvänds i Windows återanvänds för nya processer. De kan på egen hand inte fungera som unika identifierare för specifika processer.

Om du vill få en unik identifierare för en process på en viss dator kan du använda process-ID:t tillsammans med den tid då processen skapades. När du sammanfogar eller sammanfattar data runt processer tar du med kolumner för maskinidentifieraren (antingen eller `DeviceId` `DeviceName` ), process-ID ( eller ) och tiden då processen skapades `ProcessId` ( eller `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` )

Följande exempelfråga hittar processer som har åtkomst till fler än 10 IP-adresser via port 445 (SMB), eventuellt genomsökning efter filresurser.

Exempelfråga:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

Frågan sammanfattas av båda och så att den tittar på en enda `InitiatingProcessId` `InitiatingProcessCreationTime` process, utan att blanda flera processer med samma process-ID.

### <a name="query-command-lines"></a>Frågekommandon
Det finns flera sätt att skapa en kommandorad för att utföra en aktivitet. En attackerare kan till exempel referera till en bildfil utan en sökväg, utan filnamnstillägg, med hjälp av miljövariabler eller med citattecken. Attacken kan också ändra ordningen på parametrar eller lägga till flera citattecken och blanksteg.

Använd följande metoder för att skapa mer beständiga frågor runt kommandorader:

- Identifiera de kända processerna (till *exempelnet.exe* eller *psexec.exe*) genom att matcha på filnamnsfälten, i stället för att filtrera på själva kommandoraden.
- Tolka kommandoradsavsnitt med funktionen [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) 
- Vid sökning efter kommandoradsargument bör du inte söka efter en exakt matchning för flera orelaterade argument i en viss ordning. I stället kan du använda reguljära uttryck eller använda flera separata operatorer.
- Använd fallkänsliga matchningar. Använd till exempel `=~` , och i stället för , och `in~` `contains` `==` `in` `contains_cs` .
- Överväg att ta bort citattecken, ersätta kommatecken med blanksteg och ersätta flera efterföljande blanksteg med ett enda blanksteg för att minimera teknik för att begränsa anropsteknik för kommandorader. Det finns mer komplexa lösningar på problem som kräver andra metoder, men de här justeringarna kan vara till stor hjälp för vanliga.

Följande exempel visar olika sätt att skapa en  fråga som söker efter filennet.exestoppa brandväggstjänsten "MpsSvc":

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
Om du vill infoga långa listor eller stora tabeller i frågan använder du [operatorn externaldata för](/azure/data-explorer/kusto/query/externaldata-operator) att mata in data från en viss URI. Du kan hämta data från filer i TXT, CSV, JSON eller [andra format.](/azure/data-explorer/ingestion-supported-formats) Exemplet nedan visar hur du kan använda den omfattande listan med SHA-256-hashprogram för skadlig programvara som tillhandahålls av MalwareBazaar (abuse.ch) för att kontrollera bifogade filer i e-postmeddelanden:

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
SHA256,ThreatTypes,DetectionMethods
```

### <a name="parse-strings"></a>Tolka strängar
Det finns olika funktioner som du kan använda för att effektivt hantera strängar som behöver parsning eller konvertering. 

| Sträng | Funktion | Användningsexempel |
|--|--|--|
| Kommandorader | [parse_command_line()](/azure/data-explorer/kusto/query/parse-command-line) | Extrahera kommandot och alla argument. | 
| Sökvägar | [parse_path()](/azure/data-explorer/kusto/query/parsepathfunction) | Extrahera avsnitten i en fil- eller mappsökväg. |
| Versionsnummer | [parse_version()](/azure/data-explorer/kusto/query/parse-versionfunction) | Avmarkera ett versionsnummer med upp till fyra avsnitt och upp till åtta tecken per avsnitt. Använd tolkade data för att jämföra versions ålder. |
| IPv4-adresser | [parse_ipv4()](/azure/data-explorer/kusto/query/parse-ipv4function) | Konvertera en IPv4-adress till ett långt heltal. Om du vill jämföra IPv4-adresser utan att konvertera dem använder [du ipv4_compare()](/azure/data-explorer/kusto/query/ipv4-comparefunction). |
| IPv6-adresser | [parse_ipv6()](/azure/data-explorer/kusto/query/parse-ipv6function)  | Konvertera en IPv4- eller IPv6-adress till den kanoniska IPv6-notationen. Jämför IPv6-adresser med hjälp [av ipv6_compare()](/azure/data-explorer/kusto/query/ipv6-comparefunction). |

Mer information om alla parsingsfunktioner som stöds finns [i Kusto-strängfunktioner.](/azure/data-explorer/kusto/query/scalarfunctions#string-functions) 

>[!NOTE]
>Vissa tabeller i den här artikeln kanske inte är tillgängliga i Microsoft Defender för Endpoint. [Aktivera Microsoft 365 Defender för](m365d-enable.md) att leta efter hot med hjälp av fler datakällor. Du kan flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Slutpunkt till Microsoft 365 Defender genom att följa stegen i Migrera avancerade sökfrågor från [Microsoft Defender för Slutpunkt.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Relaterade ämnen
- [Språkdokumentation för kustofrågor](/azure/data-explorer/kusto/query/)
- [Kvoter och användningsparametrar](advanced-hunting-limits.md)
- [Hantera avancerade sökfel](advanced-hunting-errors.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)