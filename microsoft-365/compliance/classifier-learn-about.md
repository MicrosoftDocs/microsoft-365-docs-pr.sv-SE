---
title: Mer information om utbildningsbara klassificerare
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: En Microsoft 365 utbildare är ett verktyg som du kan träna för att identifiera olika typer av innehåll genom att ge den positiva och negativa prover att titta på. När klassificeraren har utbildning kan du bekräfta att dess resultat är korrekta. Sedan använder du det för att söka igenom organisationens innehåll och klassificera det för att tillämpa bevarande- eller känslighetsetiketter eller inkludera det i DLP (data loss prevention) eller kvarhållningsprinciper.
ms.openlocfilehash: 1881e4de87fd41f21bb1f2236d46391b3a1ed785
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162980"
---
# <a name="learn-about-trainable-classifiers"></a>Mer information om utbildningsbara klassificerare

Att klassificera och märka innehåll så att det kan skyddas och hanteras korrekt är startpunkten för informationsskyddsgrenen. Microsoft 365 finns tre sätt att klassificera innehåll.

## <a name="manually"></a>Manuellt

Den här metoden kräver en mänsklig bedömning och åtgärd. En administratör kan antingen använda befintliga etiketter och typer av känslig information eller skapa egna och sedan publicera dem. Användare och administratörer tillämpar dem på innehåll när de stöter på det. Sedan kan du skydda innehållet och hantera dess disposition.

## <a name="automated-pattern-matching"></a>Automatiserad mönstermatchning

Den här kategori av klassificeringsmetoder omfattar att söka efter innehåll genom:

- Nyckelord eller metadatavärden (frågespråk för nyckelord).
- Använda tidigare identifierade mönster för känslig information som personnummer, kreditkortsnummer och bankkontonummer (definitioner av [typ av känslig information).](sensitive-information-type-entity-definitions.md)
- Känna igen ett objekt eftersom det är en variant på en mall [(fingerutskrift av dokument)](document-fingerprinting.md).
- Använda närvaro av exakta strängar [(exakta datamatchningar).](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

Känslighets- och bevarandeetiketter kan sedan tillämpas automatiskt för att göra innehållet tillgängligt för användning i Läs mer om skydd mot [dataförlust](dlp-learn-about-dlp.md)) och tillämpa automatiskt [bevarandeprinciper för bevarandeetiketter.](apply-retention-labels-automatically.md)

## <a name="classifiers"></a>Klassificerare

Den här klassificeringsmetoden är särskilt väl lämpad för innehåll som inte lätt kan identifieras med de manuella eller automatiserade mönstermatchningsmetoderna. Den här klassificeringsmetoden handlar mer om att utbilda en klassificerare att identifiera ett objekt baserat på vad objektet är, inte efter element som finns i objektet (mönstermatchning). En klassificerare lär sig att identifiera en typ av innehåll genom att titta på hundratals exempel på innehåll som du är intresserad av att klassificera. Du börjar med att mata in exempel som definitivt ligger i kategorin. När de har bearbetars testar du det genom att ge det en blandning av både matchande och icke-matchande exempel. Klassificeraren gör sedan prognoser om huruvida ett visst objekt faller inom den kategori som du skapar. Sedan bekräftar du resultaten, sorterar sant positiva tal, sant negativa, falskt negativa och falskt negativa för att öka noggrannheten i dess prognoser. 

När du publicerar klassificeraren sorteras objekten på platser som SharePoint Online, Exchange och OneDrive, och klassificerar innehållet. När du har publicerat klassificeraren kan du fortsätta att utbilda den med hjälp av en feedbackprocess som liknar den första utbildningsprocessen.

### <a name="where-you-can-use-trainable-classifiers"></a>Här kan du använda utbildande klassificerare
Både inbyggda klassificerare och utbildare finns tillgängliga som ett villkor för [Office automatisk](apply-sensitivity-label-automatically.md)etiketter med känslighetsetiketter [,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) tillämpa bevarandeprincip automatiskt baserat på ett villkor och i [kommunikationsefterlevnad.](communication-compliance.md) 

Känslighetsetiketter kan använda klassificerare som villkor, se [Använda en känslighetsetikett på innehållet automatiskt.](apply-sensitivity-label-automatically.md)

> [!IMPORTANT]
> Klassificerare fungerar bara med objekt som inte är krypterade och är på engelska.

## <a name="types-of-classifiers"></a>Typer av klassificerare

- **förskapade klassificerare** – Microsoft har skapat och i förväg utbildat ett antal klassificerare som du kan börja använda utan att ha utbildat dem. De här klassificerarna visas med statusen `Ready to use` för .
- **Anpassade klassificerare** – Om du har klassificeringsbehov som omfattar mer än vad de i förväg utbildade klassificerarna omfattar kan du skapa och utbilda egna klassificerare.

### <a name="pre-trained-classifiers"></a>Förbaserade klassificerare

Microsoft 365 levereras med fem försorterade klassificerare:

> [!CAUTION]
> Vi använder inte längre  den förinlärde klassificeraren för anstötligt språk eftersom det har ökat ett stort antal falska positiva resultat. Använd den inte och om du använder den just nu bör du flytta bort dina affärsprocesser från den. Vi rekommenderar att du i stället **använder** de förinpassade klassarna **Threat** , **Svoritet** och trakasserier.

- **Meritförteckningar:** identifierar objekt som är textbaserade konton för en sökandes personliga, utbildningsrelaterade, kvalifikationer, yrkeserfarenhet och annan personlig information
- **Källkod:** identifierar objekt som innehåller en uppsättning instruktioner och uttryck som skrivs på de 25 översta använda datorprogrammeringsspråken på GitHub
    - ActionScript
    - C
    - C #
    - C++
    - Clojure
    - CoffeeScript
    - Gå till
    - Haskell
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - Objective-C
    - Perl
    - PHP
    - Python
    - R
    - Ruby
    - Scala
    - Shell
    - Swift
    - Tex
    - Vim Script

> [!NOTE]
> Källkod används för att identifiera när större delen av texten är källkod. Den identifierar inte källkodstext som är översedd med oformaterad text.

- **Trakasserier:** Upptäcker en specifik kategori med stötande språktextobjekt som är relaterade till stötande uppförande som är riktad mot en eller flera personer baserat på följande egenskaper: etnicitet, religion, nationella ursprung, kön, sexuell orientering, ålder, funktionshinder
- **Svordomar:** identifierar en specifik kategori med stötande språktextobjekt som innehåller uttryck som är försämnande för de flesta
- **Hot:** upptäcker en specifik kategori av anstötliga språktextobjekt som är relaterade till hot om våld eller att utföra fysisk skada eller skada en person eller egendom

De visas i **Microsoft 365 dataklassificeringsvyn** För utbildare  >    >   med statusen `Ready to use` .

![klassifierare som är förinsorterade](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Observera att det stötande språket, trakasserier, svordomar och hotklassare endast fungerar med sökbar text inte är uttömmande eller fullständig.  Ytterligare, språk och kulturstandarder ändras kontinuerligt, och mot bakgrund av dessa omotiv, förbehåller sig Microsoft rätten att uppdatera dessa klassificerare enligt eget gottfinnande. Klassificerarna kan hjälpa organisationen att övervaka anstötligt och annat språk som används, men klassificerarna tar inte itu med konsekvenserna av ett sådant språk och är inte avsedda att ge din organisation enbart möjlighet att övervaka eller svara på användning av ett sådant språk. Din organisation, och inte Microsoft eller dess dotterbolag, förblir ansvarig för alla beslut som rör övervakning, tillämpning, blockering, borttagning och lagring av innehåll som identifierats av en i förväg utbildad klassificerare.

### <a name="custom-classifiers"></a>Anpassade klassificerare

Om de i förväg utbildade klassificerarna inte uppfyller dina behov kan du skapa och utbilda dina egna klassificerare. Det finns avsevärt mer arbete att skapa egna, men de kommer att bli mycket bättre skräddarsydda efter organisationens behov. 

Du kan till exempel skapa utbildare för:
 
- Juridiska dokument – t.ex. juristklientbehörighet, avslutande uppsättningar, arbetsutdrag
- Strategiska affärsdokument – t.e. pressmeddelanden, sammanslagningar och förvärv, avtal, affärsplaner, immateriell egendom, patent, designdokument
- Prisinformation – som fakturor, prisuppgifter, arbetsorder, dokument med hög prissättning 
- Ekonomisk information – till exempel investeringar i organisationen, kvartalsvisa eller årliga resultat    

#### <a name="process-flow-for-creating-custom-classifiers"></a>Processflöde för att skapa anpassade klassificerare

Genom att skapa och publicera en klassificerare för användning i efterlevnadslösningar, till exempel kvarhållningsprinciper och kommunikations överanvändning, följer du det här flödet. Mer information om hur du skapar en egen utbildare finns i [Skapa en anpassad klassificerare](classifier-get-started-with.md).

![Anpassad klassificerare för processflöde](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Omklassning av klassificerare

Du kan förbättra noggrannheten för alla anpassade klassificerare och vissa i förväg utbildade klassificerare genom att ge dem feedback om hur korrekt klassificeringen de utför. Det kallas för att begränsa och följa det här arbetsflödet.

![arbetsflöde för omsämring av klassificerare](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Se även

- [Kvarhållningsetiketter](retention.md)
- [Mer information om dataförlustskydd](dlp-learn-about-dlp.md)
- [Känslighetsetiketter](sensitivity-labels.md)
- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)
- [Dokumentutskrift med finger](document-fingerprinting.md)
- [Exakt datamatchning](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
