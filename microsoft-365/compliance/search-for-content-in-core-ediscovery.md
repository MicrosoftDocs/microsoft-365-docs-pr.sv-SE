---
title: Söka efter innehåll i en grundläggande e-dataidentifieringsfall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Du kan söka efter innehåll som kan vara relevant för ett grundläggande eDiscovery-ärende.
ms.openlocfilehash: d17a9d16643ec9077e02b5438597237b80f09af5
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/14/2020
ms.locfileid: "52161567"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Söka efter innehåll i ett grundläggande eDiscovery-ärende

När ett grundläggande e-dataidentifieringsfall skapas och intressanta personer för ärendet ställs in på en plats kan du skapa och köra en eller flera sökningar efter innehåll som är relevant för ärendet. Sökningar som är kopplade till ett grundläggande eDiscovery-ärende visas inte på sidan Innehållssökning i Microsoft 365 efterlevnadscenter.  De här sökningarna visas på **sidan** Sökningar i det grundläggande eDiscover-fall som sökningarna är associerade med. Det innebär också att sökningar kopplade till ett ärende endast kan nås av ärendemedlemmarna.

Så här skapar du en grundläggande eDiscovery-sökning:
  
1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och logga in med inloggningsuppgifterna för användarkontot som har tilldelats lämpliga eDiscovery-behörigheter.

2. I det vänstra navigeringsfönstret i Microsoft 365 kompatibilitetscenter klickar du på Visa alla **och** sedan på **eDiscovery > Core**.

3. På sidan **Bas-e-dataidentifiering** markerar du det ärende som du vill skapa en associerad sökning i och klickar sedan på **Öppna ärende.**

4. På **startsidan för** ärendet klickar du på **fliken** Sökningar.
  
5. Klicka på **Ny** sökning på **sidan Sök.**

6. På sidan **Ny sökning** kan du lägga till nyckelord och villkor för att skapa sökfrågan. 

    ![Ny sökning](../media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
   a. Du kan ange nyckelord, meddelandeegenskaper, till exempel datum för skickade och mottagna meddelanden eller dokumentegenskaper, t.ex. filnamn eller det datum då ett dokument senast ändrades. Du kan använda mer komplexa frågor som använder en boolesk operator, som **AND**, **OR,** **NOT** eller **NEAR.** Du kan också söka efter känslig information (till exempel personnummer) i dokument eller söka efter dokument som har delats externt. Om du lämnar nyckelordsrutan tom inkluderas allt innehåll på de angivna innehållsplatserna i sökresultatet.

   b. Du kan klicka på **kryssrutan Visa nyckelordslista** och skriva ett nyckelord på varje rad. Om du gör det kopplas nyckelorden på varje rad av **operatorn** ELLER i sökfrågan som skapas. Du kan ange högst 20 nyckelord i listan.

    ![Nyckelordslista](../media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    Varför ska jag använda nyckelordslistan? Du kan få statistik som visar hur många objekt som matchar varje nyckelord. Det kan hjälpa dig att snabbt identifiera vilka nyckelord som är mest (och minst) effektiva. Du kan också använda en nyckelordsfras (omgivet av parenteser) i en rad. Mer information om sökstatistik finns i Visa [nyckelordsstatistik för innehållssökningsresultat](view-keyword-statistics-for-content-search.md).

    Mer information om hur du använder listan nyckelord finns i [Skapa en sökfråga.](content-search.md#building-a-search-query)

   c. Du kan klicka **på Villkor** och lägga till villkor i en sökfråga för att begränsa en sökning och returnera en mer förfinad uppsättning resultat. Varje villkor lägger till en sats i KQL-sökfrågan som skapas och körs när du startar sökningen. Ett villkor är logiskt kopplat till nyckelordsfrågan (anges i nyckelordsrutan) av **operatorn OCH.** Det innebär att objekt måste uppfylla både nyckelordsfrågan och varje villkor som ska tas med i resultatet. Så här kan du begränsa resultatet.

    Mer information om hur du skapar en sökfråga och använder villkor finns [i Nyckelordsfrågor för innehållssökning.](keyword-queries-and-search-conditions.md)

7. Under **Platser: platser som är platser i** lager väljer du de innehållsplatser som du vill söka efter. Du kan söka i postlådor, webbplatser och gemensamma mappar i samma sökning.

    ![Platser, platser som är väntande](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - **Alla platser**. Välj det här alternativet om du vill söka på alla innehållsplatser i organisationen. När du väljer det här alternativet kan du välja att söka i alla Exchange-postlådor (som innehåller postlådor för alla Microsoft Teams-, Yammer-grupper och Office 365-grupper), alla SharePoint- och OneDrive för företag-webbplatser (som innehåller webbplatser för alla Microsoft Teams-, Yammer-grupper och Office 365-grupper) och alla gemensamma mappar.
    
    - **Alla platser som är väntande**. Välj det här alternativet om du vill söka igenom alla innehållsplatser som har satts på plats för e-dataidentifiering i det här fallet. Om ärendet innehåller flera spärrade objekt genomsöks innehållsplatserna från alla platser. Om en innehållsplats dessutom har placerats på ett frågebaserat håll kommer endast objekt som är på plats att genomsökas när du kör den innehållssökning som du skapar i det här steget. Om en användare till exempel placerades i ett frågebaserat ärende som bevarar objekt som skickades eller skapades före ett visst datum skulle bara de objekten genomsökas. Detta sker genom att koppla frågan om ärendesök och innehållssökningsfrågan via en **OCH-operator.** Mer information finns i [Söka efter platser vid eDiscovery-hold.](create-ediscovery-holds.md#search-locations-on-ediscovery-hold)
    
    - **Specifika platser**. Välj det här alternativet för att välja de postlådor och webbplatser som du vill söka i. När du väljer det här alternativet **och klickar på** Ändra visas en lista över platser. Du kan välja att söka efter användare, grupper, team eller webbplatser. Du kan också söka i organisationens gemensamma mappar.
    
      ![Välja specifika platser](../media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
     Om du väljer det här alternativet och söker efter en plats med innehåll som är på plats, tillämpas inte frågor från ett frågebaserat ärendeknöjt på sökfrågan. Med andra ord genomsöks allt innehåll, inte bara det innehåll som bevaras av ett frågebaserat ärendefrågek.

8. När du har valt innehållsplatser att söka på klickar du på **Klar** och sedan på **Spara**.

9. På sidan **Ny sökning** klickar du på Spara **& kör** och anger sedan ett namn för sökningen. Sökningar som är kopplade till ett grundläggande eDiscovery-ärende måste ha namn som är unika i Office 365 organisation.

10. Klicka **på** Spara för att spara sökinställningarna och starta sökningen.

  När sökningen är klar kan du förhandsgranska sökresultaten. Om det behövs klickar **du** på Uppdatera **på sidan** Sökningar för att visa sökningen som du skapade i listan.

11. Klicka på sökningen för att visa den utfällande sidan, som innehåller statistik om sökningen och för att utföra andra uppgifter som att visa sökstatistik och exportera sökresultaten.

## <a name="more-information-about-searching-content-locations"></a>Mer information om hur du söker efter innehållsplatser

- När du klickar **på Välj användare, grupper** eller team för att ange postlådor att söka i är postlådeväljaren som visas tom. Det här är för att förbättra prestandan. Om du vill lägga till mottagare i listan klickar du på Välj **användare,** grupper eller team , skriver ett namn (minst 3 tecken) i sökrutan, markerar kryssrutan bredvid namnet och klickar sedan på **Välj**.

- Du kan lägga till inaktiva postlådor, Microsoft Teams, Yammer-grupper, Office 365-grupper och distributionsgrupper i listan med postlådor att söka i. Dynamiska distributionsgrupper stöds inte. Om du lägger Microsoft Teams, Yammer Grupper eller Office 365 Grupper genomsöks grupp- eller grupppostlådan. Postlådorna för gruppmedlemmarna genomsöks inte.

- Om du vill lägga till **webbplatser klickar du** på Välj **webbplatser** , klickar på Välj webbplatser igen och skriver sedan webbadressen för varje webbplats som du vill söka efter. Du kan också lägga till URL-adressen för en SharePoint för ett Microsoft-team, en Yammer grupp eller en Office 365 grupp.
