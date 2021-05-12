---
title: Komma igång med anpassade typer av känslig information
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Lär dig hur du skapar, ändrar, tar bort och testar anpassade typer av känslig information för DLP i det grafiska användargränssnittet i Säkerhets- och efterlevnadscenter.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36238d14d3d6a1f84b0fdcae62635922f62b58d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161948"
---
# <a name="get-started-with-custom-sensitive-information-types"></a>Komma igång med anpassade typer av känslig information

Om de förkonfigurerade typerna av känslig information inte uppfyller dina behov kan du skapa egna anpassade typer av känslig information som du definierar helt och hållet, eller så kan du kopiera någon som är förkonfigurerad och ändra den.

Anpassade typer av känslig information som du skapar med den här metoden läggs till i regelpaketet med namnet `Microsoft.SCCManaged.CustomRulePack`.

Det finns två sätt att skapa en ny typ av känslig information:

- [från början där du definierar alla element helt](#create-a-custom-sensitive-information-type)
- [kopiera och ändra en befintlig typ av känslig information](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a>Innan du börjar

- Du bör känna till olika typer av känslig information och vad de består av. Gå till [Mer information om typer av känslig information](sensitive-information-type-learn-about.md). Det är viktigt att förstå rollerna med:
    - [reguljära uttryck](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) – Microsoft 365-typer av känslig information använder motorn Boost.RegEx 5.1.3
    - nyckelordslistor – du kan skapa en egen när du definierar typen av känslig information eller välja från befintliga nyckelordslistor
    - [nyckelordsordlista](create-a-keyword-dictionary.md)
    - [funktioner](what-the-dlp-functions-look-for.md)
    - [konfidensnivåer](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- Du måste ha behörighet som global administratör eller efterlevnadsadministratör för att skapa, testa och distribuera en anpassad typ av känslig information via användargränssnittet. Gå till [Om administratörsroller](/office365/admin/add-users/about-admin-roles?view=o365-worldwide) i Office 365.

- Organisationen måste ha en prenumeration, till exempel Office 365 Enterprise, som omfattar dataförlustskydd (DLP). Gå till [Tjänstbeskrivning för meddelandeprincip och efterlevnad](/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc). 


> [!IMPORTANT]
> Microsofts kundtjänst och support kan inte hjälpa dig att skapa anpassade klassificeringar eller mönster för reguljära uttryck. Supporttekniker kan ge begränsat stöd för funktionen, till exempel genom att tillhandahålla exempel på mönster för reguljära uttryck i testningssyfte eller hjälpa till med felsökning av ett befintligt mönster för reguljära uttryck som inte utlöses som förväntat, men kan inte garantera att anpassad innehållsmatchning kommer att uppfylla dina krav eller åtaganden.

## <a name="create-a-custom-sensitive-information-type"></a>Skapa en anpassad typ av känslig information

Använd den här proceduren för att skapa en ny typ av känslig information som du definierar helt. 

1. I Efterlevnadscenter går du till **Dataklassificering** \> **Typer av känslig information** och väljer **Skapa informationstyp**.
2. Fyll i värden för **Namn** och **Beskrivning** och välj **Nästa**.
3. Välj **Skapa mönster**. Du kan skapa flera mönster, var och en med olika element och konfidensnivåer, när du definierar din nya typ av känslig information.
4. Välj standardkonfidensnivån för mönstret. Värdena är **Låg konfidens**, **Medelhög konfidens** och **Hög konfidens**.
5. Välja och definiera **primärelement**. Primärelementet kan vara ett **reguljärt uttryck** med en valfri verifierare, en **nyckelordslista**, en **nyckelordsordlista** eller någon av de förkonfigurerade **funktionerna**. Mer information om DLP-funktioner finns i [Vad DLP-funktionerna letar efter](what-the-dlp-functions-look-for.md).
6. Fyll i ett värde för **Teckennärhet**.
7. (Valfritt) Lägg till stödelement om du har några sådana. Stödelement kan vara ett reguljärt uttryck med en valfri verifierare, en nyckelordslista, en nyckelordsordlista eller någon av de fördefinierade funktionerna. 
8.  (Valfritt) Lägg till [**ytterligare kontroller**](#more-information-on-additional-checks) från listan över tillgängliga kontroller.
9. Välj **Skapa**.
10. Välj **Nästa**.
11. Välj den **rekommenderade konfidensnivån** för den här typen av känslig information.
12. Kontrollera inställningen och välj **Skicka**.

> [!IMPORTANT]
> Microsoft 365 använder Search Crawler för att identifiera och klassificera känslig information på SharePoint Online- och OneDrive för företag-webbplatser. För att identifiera den nya anpassade typen av känslig information i befintligt innehåll måste innehållet återcrawlas. Innehållet crawlas enligt ett schema men du kan manuellt återcrawla innehåll för en webbplatssamling, en lista eller ett bibliotek. Mer information finns i [Manuellt begära crawlning och omindexering av en webbplats, ett bibliotek eller en lista](/sharepoint/crawl-site-content).

13. På sidan **Dataklassificering** visas alla typer av känslig information. Välj **Uppdatera** och bläddra sedan efter eller använd sökverktyget för att hitta den typ av känslig information som du har skapat.

## <a name="test-a-sensitive-information-type"></a>Testa en typ av känslig information

Du kan testa olika typer av känslig information i listan. Vi föreslår att du testar alla typer av känslig information som du skapar innan du använder dem i en princip.

1. Förbered två filer, till exempel ett Word-dokument. Ett med innehåll som matchar de element du angav i din typ av känslig information och ett som inte matchar.
2. I Efterlevnadscenter går du till **Dataklassificering** \> **Typer av känslig information** och väljer typen av känslig information i listan för att öppna informationsfönstret. Välj sedan **Testa**.
3. Ladda upp en fil och välj **Testa**.
4. Granska resultatet på sidan **Matchar resultat** och välj **Slutför**.

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a>Ändra anpassade typer av känslig information i Efterlevnadscenter

1. I Efterlevnadscenter går du till **Dataklassificering** \> **Typer av känslig information** och väljer den typ av känslig information i listan som du vill ändra. Välj sedan **Redigera**.
2. Du kan lägga till andra mönster, med unika primära element och stödelement, konfidensnivåer, teckennärhet och [**ytterligare kontroller**](#more-information-on-additional-checks) eller redigera/ta bort befintliga.

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a>Ta bort anpassade typer av känslig information i Efterlevnadscenter 

> [!NOTE]
> Du kan bara ta bort anpassade typer av känslig information. Du kan inte ta bort inbyggda typer av känslig information.

> [!IMPORTANT]
> Innan du tar bort en anpassad typ av känslig information ska du kontrollera att inga DLP-principer eller e-postflödesregler i Exchange (kallas även transportregler) fortfarande refererar till den typ av känslig information som finns.

1. I Efterlevnadscenter går du till **Dataklassificering** \> **Typer av känslig information** och väljer den typ av känslig information i listan som du vill ta bort.
2. På den utfällbara menyn som öppnas väljer du **Ta bort**.

## <a name="copy-and-modify-a-sensitive-information-type"></a>Kopiera och ändra en typ av känslig information

Använd den här proceduren för att skapa en ny typ av känslig information som baseras på en befintlig typ av känslig information. 

1. I Efterlevnadscenter går du till **Dataklassificering** \> **Typer av känslig information** och väljer den typ av känslig information som du vill kopiera.
2. Välj **Kopiera** på den utfällbara menyn.
3. Välj **Uppdatera** i listan med typer av känslig information och bläddra eller sök efter kopian du just skapade. Sökning efter partiella strängar fungerar, så du kan söka efter bara `copy` så returnerar sökningen alla typer av känslig information med ordet `copy` i namnet. 
4. Fyll i värden för **Namn** och **Beskrivning** och välj **Nästa**.
5. Välj din kopia av typen av känslig information och välj **Redigera**. 
6. Ge den nya typen av känslig information ett nytt **namn** och en **beskrivning**.
7. Du kan välja att redigera eller ta bort befintliga mönster och lägga till nya. Välj standardkonfidensnivån för det nya mönstret. Värdena är **Låg konfidens**, **Medelhög konfidens** och **Hög konfidens**.
8. Välja och definiera **primärelement**. Primärelementet kan vara ett **reguljärt uttryck**, en **nyckelordslista**, en **nyckelordsordlista** eller någon av de förkonfigurerade **funktionerna**. Se [Vad DLP-funktionerna letar efter](what-the-dlp-functions-look-for.md).
9. Fyll i ett värde för **Teckennärhet**.
10. (Valfritt) Om du har **stödelement** eller några [**ytterligare kontroller**](#more-information-on-additional-checks) lägger du till dem. Om det behövs kan du gruppera dina **stödelement**.
11. Välj **Skapa**.
12. Välj **Nästa**.
13. Välj den **rekommenderade konfidensnivån** för den här typen av känslig information.
14. Kontrollera inställningen och välj **Skicka**.

Du kan också skapa anpassade typer av känslig information med hjälp av PowerShell- och Exact Data Match-funktioner. Mer information om dessa metoder finns i:
- [Skapa en anpassad typ av känslig information i Säkerhets- och efterlevnadscenter PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Skapa en anpassad typ av känslig information för DLP med Exact Data Match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="more-information-on-additional-checks"></a>Mer information om ytterligare kontroller

Här finns definitioner och några exempel för tillgängliga ytterligare kontroller.

**Exkludera specifika matchningar**: Med den här kontrollen kan du definiera nyckelord som ska uteslutas när matchningar identifieras för det mönster du redigerar. Du kan till exempel utesluta testkreditkortsnummer som "4111111111111111" så att de inte matchas som ett giltigt nummer.

**Börjar eller börjar inte med tecken**: Med den här kontrollen kan du definiera vilka tecken de matchande objekten måste eller inte får börja med. Om du till exempel vill att mönstret bara ska identifiera kreditkortsnummer som börjar med 41, 42 eller 43, markerar du **Börjar med** och lägger till 41, 42 och 43 i listan, avgränsade med kommatecken. 

**Slutar eller slutar inte med tecken**: Med den här kontrollen kan du definiera vilka tecken de matchande objekten måste eller inte får sluta med. Om ditt medarbetar-ID-nummer inte får sluta med 0 eller 1 väljer du **Slutar inte med** och lägger till 0 och 1 i listan, avgränsade med kommatecken.

**Exkludera dubblettecken**: Med den här kontrollen kan du ignorera matchningar där alla siffror är samma. Om till exempel alla siffror i det sexsiffriga medarbetar-ID-numret inte får vara samma kan du välja **Exkludera dubblettecken** för att utesluta 111111, 222222, 333333, 444444, 555555, 666666, 777777, 888888, 999999 och 000000 i listan med giltiga matchningar för medarbetar-ID.

**Inkludera eller exkludera prefix**: Med den här kontrollen kan du definiera de nyckelord som måste eller inte får hittas omedelbart före den matchande enheten. Beroende på ditt val matchas enheter, eller matchas inte, om de föregås av de prefix du tar med här. Om du till exempel **exkluderar** prefixet **GUID:** betraktas inte en enhet som föregås av **GUID:** som en matchning.

**Inkludera eller exkludera suffix**: Med den här kontrollen kan du definiera de nyckelord som måste eller inte får hittas omedelbart efter den matchande enheten. Beroende på ditt val matchas enheter, eller matchas inte, om de följs av de suffix du tar med här. Om du till exempel **exkluderar** suffixet **:GUID** matchas inte text som följs av **:GUID**.


> [!NOTE]
> Microsoft 365 Information Protection har i förhandsversionen stöd för teckenuppsättningsspråk med dubbla byte för:
> - Kinesiska (förenklad)
> - Kinesiska (traditionell)
> - Koreanska
> - Japanska
>
>Det här stödet är tillgängligt för typer av känslig information. Mer information finns i [Viktig information gällande stöd i Information Protection för teckenuppsättningar med dubbla byte (förhandsversion)](mip-dbcs-relnotes.md).