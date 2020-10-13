---
title: Metod tips för avancerade frågor
description: Lär dig hur du skapar snabba, effektiva och problem fria hotfrågor med avancerad jakt
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema, kusto, förhindra tids gräns, kommando rader, process-ID, optimera, metod tips, tolka, gå med och summera
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: f18a98b19b6a1920d1e4d2094ba0bab74f10035e
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430145"
---
# <a name="advanced-hunting-query-best-practices"></a>Metod tips för avancerad jakt frågor

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

Använd dessa rekommendationer för att få snabbare resultat och undvika tids gränser när komplexa frågor körs. För mer information om hur du förbättrar frågeresultatet kan du läsa [Kusto metod tips](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="understand-cpu-resource-limits"></a>Förstå gräns värden för processor resurser
Beroende på dess storlek har alla innehavare till gång till en mängd tilldelade CPU-resurser för att köra avancerade jakt frågor. Få reda på mer om olika tjänst gränser i [om begränsningar för avancerat jakt](advanced-hunting-limits.md).

Kunder som kör flera frågor regelbundet bör spåra förbrukningen och använda optimerings vägledningen i den här artikeln för att minimera störningar som orsakas av gräns värden.

## <a name="general-optimization-tips"></a>Allmänna optimerings tips

- **Ändra storlek på nya frågor**– om du misstänker att en fråga returnerar en stor resultat mängd ska du först bedöma den med hjälp av [operatorn Count](https://docs.microsoft.com/azure/data-explorer/kusto/query/countoperator). Använd [gräns](https://docs.microsoft.com/azure/data-explorer/kusto/query/limitoperator) eller synonym `take` för att undvika stora resultat mängder.
- **Använd filter tidigt**– Använd tids filter och andra filter för att minska data uppsättningen, särskilt innan du använder omvandlings-och analys funktioner, till exempel [substring ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/substringfunction), [Ersätt ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/replacefunction), [Rensa ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/trimfunction), [toupper ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/toupperfunction)eller [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). I exemplet nedan används parsnings funktionen [extractjson ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractjsonfunction) efter att filtrerings operatorerna har minskat antalet poster.

    ```kusto
    DeviceEvents
    | where Timestamp > ago(1d)
    | where ActionType == "UsbDriveMount" 
    | where DeviceName == "user-desktop.domain.com"
    | extend DriveLetter = extractjson("$.DriveLetter", AdditionalFields)
     ```

- **Har taktslag innehåller**– för att undvika att under strängar under vissa ord visas kan du använda `has` operatorn i stället för `contains` . [Läs mer om sträng operatorer](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators)
- **Leta i specifika kolumner**– titta i en viss kolumn i stället för att köra fullständig text ökning i alla kolumner. Använd inte `*` för att markera alla kolumner.
- **SKIFT läges känslig för snabb**sökningar är mer specifika och generellt sett mer. Namn på SKIFT läges känsliga [sträng operatorer](https://docs.microsoft.com/azure/data-explorer/kusto/query/datatypes-string-operators), till exempel `has_cs` och `contains_cs` , vanligt vis slutar med `_cs` . Du kan också använda en Skift läges känslig operator `==` i stället för `~=` .
- **Tolka, extrahera inte**– när det är möjligt kan du använda [operatorn parse](https://docs.microsoft.com/azure/data-explorer/kusto/query/parseoperator) eller en analys funktion som [parse_json ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsejsonfunction). Undvik `matches regex` operatorn sträng eller [extrahera ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/extractfunction), som båda använder reguljära uttryck. Reservera användning av reguljära uttryck för mer komplexa scenarier. [Läs mer om att analysera funktioner](#parse-strings)
- **Filtrera tabeller som inte är uttryck**– filtrera inte efter beräknade kolumner om du kan filtrera efter en tabell kolumn.
- **Inga termer med tre tecken**– Undvik jämförelse eller filtrering med hjälp av termer med tre tecken eller färre. Dessa villkor är inte indexerade och matchar dem kräver fler resurser.
- **Project selektiv**– gör dina resultat lättare att förstå genom att bara projicera de kolumner du behöver. Om du projicerar specifika kolumner innan du kör [Join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) eller liknande operationer förbättras prestanda.

## <a name="optimize-the-join-operator"></a>Optimera `join` operatorn
Med [operatorn](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator) sammanfoga kopplas rader från två tabeller med matchande värden i angivna kolumner. Använd de här tipsen för att optimera frågor som använder den här operatorn.

- **Mindre tabell till vänster**– `join` operatorn matchar poster i tabellen till vänster om ditt JOIN-uttryck på poster till höger. Genom att ha den mindre tabellen till vänster måste färre poster matchas, och därför blir frågan snabbare. 

    I tabellen nedan minskar vi den vänstra tabellen `DeviceLogonEvents` så att den bara täcker tre specifika enheter innan du ansluter den `IdentityLogonEvents` via konto-sid.
 
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

- **Använd den inre kopplings funktionen**– standard alternativet för att [förena](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-flavors) eller [innerunique-koppla](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#innerunique-join-flavor) ihop rader i den vänstra tabellen med hjälp av kopplings tangenten innan du returnerar en rad för varje träff till den högra tabellen. Om den vänstra tabellen innehåller flera rader med samma värde för `join` tangenten dubbleras dessa rader så att de lämnar en slumpmässig rad för varje unikt värde.

    Detta standard beteende kan leda till viktig information från den vänstra tabellen som kan ge användbar insyn. Frågan nedan visar till exempel endast ett e-postmeddelande med en viss bifogad fil, även om den bifogade filen skickades med flera e-postmeddelanden:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```

    För att adressera den här begränsningen använder vi den [inre kopplingen](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) genom `kind=inner` att ange att visa alla rader i den vänstra tabellen med matchande värden till höger:
    
    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```
- **Ansluta till poster från ett tidsfönster**– när du undersöker säkerhets händelser letar analytiker efter relaterade händelser som inträffar inom samma tids period. Använd samma tillvägagångs sätt när du använder olika `join` prestanda genom att minska antalet poster att kontrol lera.
    
    Frågan nedan söker efter inloggnings händelser inom 30 minuter efter att du har tagit emot en skadlig fil:

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
- **Tillämpa tids filter på båda sidor**– även om du inte undersöker ett specifikt tidsfönster kan du använda tids filter för både vänster och höger tabell för att minska antalet poster för att kontrol lera och förbättra `join` prestanda. Frågan nedan gäller `Timestamp > ago(1h)` båda tabellerna så att den bara ansluter till poster från den senaste timmen:

    ```kusto
    EmailAttachmentInfo
    | where Timestamp > ago(1h)
    | where Subject == "Document Attachment" and FileName == "Document.pdf"
    | join kind=inner (DeviceFileEvents | where Timestamp > ago(1h)) on SHA256 
    ```  

- **Använda tips för prestanda**– Använd tips med `join` operatorn för att instruera Server delen att distribuera belastningen när resurser körs. [Lär dig mer om att delta i tips](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator#join-hints)

    Med **[blanda tipset](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery)** kan du till exempel förbättra frågans prestanda när du ansluter tabeller med hjälp av en transparens med hög kardinalitet – en transparens med många unika värden – till exempel `AccountObjectId` i frågan nedan:

    ```kusto
    IdentityInfo
    | where JobTitle == "CONSULTANT"
    | join hint.shufflekey = AccountObjectId 
    (IdentityDirectoryEvents
        | where Application == "Active Directory"
        | where ActionType == "Private data retrieval")
    on AccountObjectId 
    ```
    
    Med **[sändnings tipset](https://docs.microsoft.com/azure/data-explorer/kusto/query/broadcastjoin)** ser du när den vänstra tabellen är liten (upp till 100 000 poster) och den högra tabellen är oerhört stor. Frågan nedan försöker till exempel ansluta till några e-postmeddelanden med specifika ämnen med _alla_ meddelanden som innehåller länkar i `EmailUrlInfo` tabellen:

    ```kusto
    EmailEvents 
    | where Subject in ("Warning: Update your credentials now", "Action required: Update your credentials now")
    | join hint.strategy = broadcast EmailUrlInfo on NetworkMessageId 
    ```

## <a name="optimize-the-summarize-operator"></a>Optimera `summarize` operatorn
Den [summerade operatorn](https://docs.microsoft.com/azure/data-explorer/kusto/query/summarizeoperator) aggregerar innehållet i en tabell. Använd de här tipsen för att optimera frågor som använder den här operatorn.

- **Sök efter distinkta värden**— i allmänhet `summarize` för att hitta distinkta värden som kan upprepas. Det kan vara onödigt att använda det för att aggregera kolumner som inte innehåller upprepade värden.

    Även om ett enskilt e-postmeddelande kan ingå i flera händelser används _inte_ exemplet nedan för `summarize` att ett nätverks meddelande-ID för ett enskilt e-postmeddelande alltid innehåller en unik avsändar adress.
 
    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by NetworkMessageId, SenderFromAddress   
    ```
    Det `summarize` går lätt att byta ut operatorn `project` , vilket ger eventuellt samma resultat när du förbrukar färre resurser:

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | project NetworkMessageId, SenderFromAddress   
    ```
    Följande exempel är en mer effektiv användning av `summarize` eftersom det kan finnas flera olika instanser av en avsändar adress som skickar e-post till samma mottagares adress. Sådana kombinationer är mindre distinkta och har troligen dubbletter.

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize by SenderFromAddress, RecipientEmailAddress   
    ```

- Om **du blandar frågan**– medan `summarize` är bäst i kolumner med repetitiva värden kan samma kolumner också ha en _hög kardinalitet_ eller ett stort antal unika värden. Precis som med `join` operatorn kan du även använda [blanda-tipset](https://docs.microsoft.com/azure/data-explorer/kusto/query/shufflequery) med `summarize` för att distribuera bearbetnings belastning och kan förbättra prestandan när du arbetar med kolumner med stor kardinalitet.

    Frågan nedan används `summarize` för att räkna distinkt mottagares e-postadress, som kan köras i hundratals tusen i stora organisationer. För att förbättra prestandan inkluderar den `hint.shufflekey` :

    ```kusto
    EmailEvents  
    | where Timestamp > ago(1h)
    | summarize hint.shufflekey = RecipientEmailAddress count() by Subject, RecipientEmailAddress
    ```

## <a name="query-scenarios"></a>Fråge scenarier

### <a name="identify-unique-processes-with-process-ids"></a>Identifiera unika processer med process-ID
Process-ID: n återvinns i Windows och återanvänds för nya processer. De kan inte fungera som unika identifierare för specifika processer.

Om du vill ha en unik identifierare för en process på en specifik dator använder du process-ID: t tillsammans med processen för skapande av process. När du ansluter till eller sammanfattar data i processer inkluderar du kolumner för datorns ID (antingen `DeviceId` eller `DeviceName` ), process-ID ( `ProcessId` eller `InitiatingProcessId` ) och processens skapelse tid ( `ProcessCreationTime` eller `InitiatingProcessCreationTime` )

I följande exempel fråga hittas processer med åtkomst till fler än 10 IP-adresser över Port 445 (SMB), eventuellt genomsökning efter fil resurser.

Exempel fråga:
```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId
InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

Frågan sammanfattar både efter båda `InitiatingProcessId` och `InitiatingProcessCreationTime` så att den ser ut på en enstaka gång, utan att flera processer med samma process-ID kan blandas.

### <a name="query-command-lines"></a>Kommando rader för fråga
Det finns många olika sätt att skapa en kommando rad för att utföra en uppgift. En angripare kan till exempel referera till en bildfil utan sökväg, utan fil namns tillägg, med hjälp av miljövariabler eller med citat tecken. Angriparen kan också ändra ordningen på parametrar eller lägga till flera citat tecken och blank steg.

Gör så här om du vill skapa fler fasta frågor kring kommando rader:

- Identifiera kända processer (till exempel *net.exe* eller *psexec.exe*) genom att matcha i fil namns fälten i stället för att filtrera på själva kommando raden.
- Kommando rads avsnitt för parsning med [funktionen parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) 
- Leta inte efter en exakt matchning på flera icke relaterade argument i en viss ordning när du frågar efter kommando rads argument. Använd i stället vanliga uttryck eller Använd flera separata innehåller operatorer.
- Använd Skift läges okänsliga träffar. Du kan till exempel använda `=~` , `in~` och `contains` i stället för `==` , `in` och `contains_cs` .
- För att minska kommando rads obfuscation metoder bör du överväga att ta bort citat tecken, ersätta kommatecken med blank steg och ersätta flera sammanhängande blank steg med ett enda blank steg. Det finns mer komplexa obfuscation-tekniker som kräver andra metoder, men dessa kan hjälpa dig att åtgärda dem.

Följande exempel visar olika sätt att skapa en fråga som söker efter filen *net.exe* att stoppa brand Väggs tjänsten "Mpssvc":

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

### <a name="ingest-data-from-external-sources"></a>Intag från externa källor
Om du vill införliva långa listor eller stora tabeller i din fråga kan du använda [externaldata-operatorn](https://docs.microsoft.com/azure/data-explorer/kusto/query/externaldata-operator) för att förtära data från en angiven URI. Du kan hämta data från filer i TXT, CSV, JSON eller [andra format](https://docs.microsoft.com/azure/data-explorer/ingestion-supported-formats). I exemplet nedan visas hur du kan använda den omfattande listan med SHA-256-hashar från MalwareBazaar (abuse.ch) för att kontrol lera bifogade filer i e-postmeddelanden:

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
Det finns olika funktioner som du kan använda för att effektivt hantera strängar som behöver parsas eller konverteras. 

| Sträng | & | Exempel på användning |
|--|--|--|
| Kommando rader | [parse_command_line ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-command-line) | Extrahera kommandot och alla argument. | 
| Banan | [parse_path ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parsepathfunction) | Extrahera avsnitt i en fil-eller mappsökväg. |
| Versions nummer | [parse_version ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-versionfunction) | Avkonstruerar ett versions nummer med upp till fyra avsnitt och upp till åtta tecken per avsnitt. Jämför versions åldern med analyserade data. |
| IPv4-adresser | [parse_ipv4 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv4function) | Konvertera en IPv4-adress till ett långt heltal. Använd [ipv4_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv4-comparefunction)om du vill jämföra IPv4-adresser utan att konvertera dem. |
| IPv6-adresser | [parse_ipv6 ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/parse-ipv6function)  | Konvertera en IPv4-eller IPv6-adress till det kanoniska IPv6-formatet. Använd [ipv6_compare ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/ipv6-comparefunction)om du vill jämföra IPv6-adresser. |

Om du vill veta mer om alla analys funktioner som stöds [läser du Kusto sträng funktioner](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalarfunctions#string-functions). 

## <a name="related-topics"></a>Relaterade ämnen
- [Dokumentation för Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
- [Tjänstbegränsningar](advanced-hunting-limits.md)
- [Hantera avancerade jakt fel](advanced-hunting-errors.md)
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
