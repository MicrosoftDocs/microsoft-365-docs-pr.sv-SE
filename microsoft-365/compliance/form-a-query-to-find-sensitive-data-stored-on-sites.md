---
title: Skapa en fråga för att hitta känsliga data som lagras på webbplatser
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Använd dataförlustskydd (DLP) i SharePoint Online för att upptäcka dokument som innehåller känsliga data i hela klientorganisationen.
ms.openlocfilehash: 04bf2e97dd2b5530838aef9fcb4b4467270d2d9d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287485"
---
# <a name="form-a-query-to-find-sensitive-data-stored-on-sites"></a>Skapa en fråga för att hitta känsliga data som lagras på webbplatser

Användare lagrar ofta känsliga data, till exempel kreditkortsnummer, personnummer eller personliga uppgifter, på sina webbplatser och med tiden kan detta exponera en organisation för betydande risk för dataförlust. Dokument som lagras på OneDrive för företag webbplatser kan delas med personer utanför organisationen som inte ska ha tillgång till informationen. Med dataförlustskydd (DLP) i SharePoint Online kan du upptäcka dokument som innehåller känsliga data i hela klientorganisationen. När dokumenten har upptäckts kan du arbeta med dokumentägarna och skydda dem. I det här avsnittet får du hjälp att skapa en fråga för att söka efter känsliga data.

> [!NOTE]
> Elektronisk upptäckt, eDiscovery och DLP är premiumfunktioner som kräver en [SharePoint Online abonnemang 2.](https://go.microsoft.com/fwlink/?LinkId=510080)

## <a name="forming-a-basic-dlp-query"></a>Utforma en enkel DLP-fråga

Det finns tre delar som utgör en enkel DLP-fråga: SensitiveType, antal intervall och konfidensområde. Precis som i följande bild är **SensitiveType:" \<type\>** obligatoriskt, både och **|\<count range\>** är **|\<confidence range\>** valfria.

![Exempelfråga indelad i obligatorisk och valfri](../media/DLP-query-example-text.png)

### <a name="sensitive-type---required"></a>Känslig typ – obligatoriskt

Så vad är varje del? SharePoint DLP-frågor börjar vanligtvis med egenskapen och ett namn på informationstyp från lager `SensitiveType:"` [av känslig information](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)och slutar med ett `"` . Du kan också använda namnet på en [anpassad typ av känslig information](create-a-custom-sensitive-information-type.md) som du skapat för organisationen. Du kanske letar efter dokument som innehåller kreditkortsnummer. I ett sådant fall använder du följande format:  `SensitiveType:"Credit Card Number"` . Eftersom du inte tog med antal intervall eller konfidensintervall returnerar frågan alla dokument där ett kreditkortsnummer identifieras. Det här är den enklaste frågan du kan köra och den returnerar flest resultat. Kom ihåg att stavning och avstånd i den känsliga typen spelar roll.

### <a name="ranges---optional"></a>Intervall – valfritt

Båda de två följande delarna är områden, så nu ska vi snabbt undersöka hur ett område ser ut. I SharePoint DLP-frågor representeras ett grundläggande område av två tal avgränsade med två punkter, som ser ut så här: `[number]..[number]` . Om det används  `10..20` skulle intervallet till exempel hämta tal från 10 till 20. Det finns många olika intervallkombinationer och flera av dem behandlas i det här avsnittet.

Nu ska vi lägga till ett antal i frågan. Du kan använda antalsområde för att definiera antalet förekomster av känslig information som ett dokument måste innehålla innan det tas med i frågeresultatet. Om du till exempel vill att frågan endast ska returnera dokument som innehåller exakt fem kreditkortsnummer använder du följande:  `SensitiveType:"Credit Card Number|5"` . Med antalsområde kan du även identifiera dokument som utgör en hög grad av risk. Din organisation kan till exempel anse dokument med fem eller fler kreditkortsnummer som en hög risk. För att hitta dokument som passar detta villkor använder du den här frågan:  `SensitiveType:"Credit Card Number|5.."` . Du kan också hitta dokument med fem eller färre kreditkortsnummer med hjälp av den här frågan:  `SensitiveType:"Credit Card Number|..5"` .

#### <a name="confidence-range"></a>Konfidensområde

Slutligen är konfidensintervallet nivån av konfidens om den identifierade känsliga typen verkligen är en matchning. Värdena för konfidensområde fungerar på ungefär samma sätt som antal intervall. Du kan skapa en fråga utan att inkludera ett antal intervall. Om du till exempel vill söka efter dokument med valigt antal kreditkortsnummer – så länge konfidensintervallet är 85 procent eller högre – kan du använda den här frågan:  `SensitiveType:"Credit Card Number|*|85.."` .

> [!IMPORTANT]
> Asterisken ( `*` ) är ett jokertecken som innebär att alla värden fungerar. Du kan använda jokertecknet ( ) antingen i antalsområdet eller i konfidensområdet, `*` men inte i en känslig typ.

### <a name="additional-query-properties-and-search-operators-available-in-the-ediscovery-center"></a>Ytterligare frågeegenskaper och sökoperatorer tillgängliga i eDiscovery Center

Med DLP i SharePoint introduceras även egenskapen LastSensitiveContentScan, som kan hjälpa dig att söka efter filer som genomsöks inom en viss tidsperiod. Frågeexempel för  `LastSensitiveContentScan` egenskapen finns i [exempel på komplexa frågor i](#examples-of-complex-queries) nästa avsnitt.

Du kan inte bara använda DLP-specifika egenskaper för att skapa en fråga, utan även standardegenskaper SharePoint för eDiscovery-sökning, till exempel `Author` eller `FileExtension` . Du kan använda operatorer för att skapa komplexa frågor. Listan över tillgängliga egenskaper och operatorer finns i blogginlägget [Använda sökegenskaper och operatorer med eDiscovery.](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)

## <a name="examples-of-complex-queries"></a>Exempel på komplexa frågor

I följande exempel används olika typer, egenskaper och operatorer för att illustrera hur du kan förfina frågorna så att du hittar exakt det du letar efter.

<br>

****

|Fråga|Förklaring|
|---|---|
|`SensitiveType:"International Banking Account Number (IBAN)"`|Namnet kan verka konstigt eftersom det är så långt, men det är rätt namn för den typ av känslig information. Se till att använda exakta namn från [inventeringen av typer av känslig information.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) Du kan också använda namnet på en [anpassad typ av känslig information](create-a-custom-sensitive-information-type.md) som du skapat för organisationen.|
|`SensitiveType:"Credit Card Number|1..4294967295|1..100"`|Då returneras dokument med minst en matchning av den känsliga typen "Kreditkortsnummer". Värdena för varje intervall är respektive lägsta och högsta värden. Ett enklare sätt att skriva den här  `SensitiveType:"Credit Card Number"` frågan är , men var är det roliga med den?|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018"`|Då returneras dokument med 5–25 kreditkortsnummer som skannades från den 11 augusti 2018 till den 13 augusti 2018.|
|`SensitiveType:"Credit Card Number|5..25" AND LastSensitiveContentScan:"8/11/2018..8/13/2018" NOT FileExtension:XLSX`|Då returneras dokument med 5–25 kreditkortsnummer som skannades från den 11 augusti 2018 till den 13 augusti 2018. Filer med XLSX-filnamnstillägg tas inte med i frågeresultaten.  `FileExtension` är en av många egenskaper som du kan ta med i en fråga. Mer information finns i Använda [sökegenskaper och operatorer med eDiscovery.](/archive/blogs/quentin/using-search-properties-and-operators-with-ediscovery)|
|`SensitiveType:"Credit Card Number" OR SensitiveType:"U.S. Social Security Number (SSN)"`|Då returneras dokument som innehåller antingen ett kreditkortsnummer eller ett personnummer.|
|

## <a name="examples-of-queries-to-avoid"></a>Exempel på frågor som du kan undvika

Alla frågor skapas inte lika. Följande tabell innehåller exempel på frågor som inte fungerar med DLP i SharePoint beskriver varför.

<br>

****

|Fråga som inte stöds|Orsak|
|---|---|
|`SensitiveType:"Credit Card Number|.."`|Du måste lägga till minst en siffra.|
|`SensitiveType:"NotARule"`|"NotARule" är inte ett giltigt namn på känslig typ. Endast namn i [lagertyperna för känslig information](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help) fungerar i DLP-frågor.|
|`SensitiveType:"Credit Card Number|0"`|Noll är inte giltigt som antingen minimivärdet eller maxvärdet i ett område.|
|`SensitiveType:"Credit Card Number"`|Det kan vara svårt att se, men det finns extra tomt utrymme mellan "Kredit" och "Kort" som gör frågan ogiltig. Använd exakt namn på känsliga typer från [inventeringen av typer av känslig information.](/Exchange/what-the-sensitive-information-types-in-exchange-look-for-exchange-2013-help)|
|`SensitiveType:"Credit Card Number|1. .3"`|Tvåperiodsdelen ska inte avgränsas med blanksteg.|
|`SensitiveType:"Credit Card Number| |1..|80.."`|Det finns för många röravgränsare ( \| ). Följ det här formatet i stället: `SensitiveType: "Credit Card Number|1..|80.."`|
|`SensitiveType:"Credit Card Number|1..|80..101"`|Konfidensvärden representerar en procentsats, men får inte överstiga 100. Välj ett tal mellan 1 och 100 i stället.|
|

## <a name="for-more-information"></a>Mer information

- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)
- [Köra en innehållssökning](content-search.md)
- [Nyckelordsfrågor och sökvillkor för innehållssökning](keyword-queries-and-search-conditions.md)
