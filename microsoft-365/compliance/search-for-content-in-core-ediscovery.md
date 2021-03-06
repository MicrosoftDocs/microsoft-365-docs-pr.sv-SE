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
description: Sök efter innehåll som kan vara relevant för ett grundläggande eDiscovery-ärende.
ms.openlocfilehash: 8d2e2a20135312a8f111a071abbe77b03b8e8363
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311783"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Söka efter innehåll i ett grundläggande eDiscovery-ärende

När ett grundläggande e-dataidentifieringsfall skapas och intressanta personer för ärendet ställs in på en plats kan du skapa och köra en eller flera sökningar efter innehåll som är relevant för ärendet. Sökningar som är kopplade till ett grundläggande eDiscovery-ärende visas inte på sidan Innehållssökning i Microsoft 365 efterlevnadscenter.  De här sökningarna visas på **sidan** Sökningar i det grundläggande eDiscover-fall som sökningarna är associerade med. Det innebär också att sökningar kopplade till ett ärende endast kan nås av ärendemedlemmarna.

Så här skapar du en grundläggande eDiscovery-sökning:
  
1. Gå till och logga in med autentiseringsuppgifterna för användarkontot som har tilldelats lämpliga <https://compliance.microsoft.com> eDiscovery-behörigheter och är medlem i ärendet.

2. I det vänstra navigeringsfönstret i Microsoft 365 kompatibilitetscenter klickar du på Visa alla **och** sedan på **eDiscovery > Core**.

3. På sidan **Bas-e-dataidentifiering** markerar du det ärende som du vill skapa en associerad sökning i och klickar sedan på **Öppna ärende.**

4. På startsidan **för** ärendet klickar du på fliken **Sökningar** och sedan på **Ny sökning**.

   ![Klicka på Ny sökning för att skapa en grundläggande eDiscovery-sökning](../media/CoreeDiscoverySearch1.png)

   > [!NOTE]
   > Med **Sök efter ID-lista**-alternativet kan du söka efter specifika e-postmeddelanden och andra postlådeobjekt med hjälp av en lista med Exchange-ID:n. Om du vill skapa en sökning med en ID-lista skickar du en fil med kommaavgränsade värden (CSV) som identifierar de specifika postlådeobjekt som du vill söka efter. Anvisningar finns i [Förbereda en CSV-fil för en ID-listsökning](csv-file-for-an-id-list-content-search.md).

5. Skriv **ett namn för** sökningen i guiden Ny sökning och en valfri beskrivning som hjälper dig att identifiera sökningen. Namnet på sökningen måste vara unikt i din organisation.

6. På sidan **Platser** väljer du innehållsplatserna som du vill söka i. Du kan söka i postlådor, webbplatser och gemensamma mappar.

    ![Välj vilka innehållsplatser som ska vara undantagna](../media/ContentSearchLocations.png)
  
   1. **Exchange-postlådor**: Ställ in växlingsknappen på **På** och klicka sedan på **Välj användare, grupper eller teams** för att ange vilka postlådor som inte ska ingå. Använd sökrutan för att hitta användarpostlådor och distributionsgrupper (för att undanta gruppmedlemmars postlådor) som ska uteslutas. Du kan också söka i postlådan som är kopplad till ett Microsoft-team (för kanalmeddelanden), Office 365-grupp och Yammer-grupp. Mer information om programdata som har lagrats i postlådor finns i [Innehåll som lagras i postlådor för eDiscovery](what-is-stored-in-exo-mailbox.md).

   2. **SharePoint-webbplatser**: Ställ in växlingsknappen på **På** och klicka sedan på **Välj webbplatser** för att ange SharePoint-webbplatser och OneDrive-konton som ska uteslutas. Skriv in URL-adressen för varje webbplats som du vill utesluta. Du kan också lägga till URL-adressen till SharePoint-webbplatsen för ett Microsoft-team, Office 365-grupp eller Yammer-grupp.
  
   3. **Gemensamma Exchange-mappar**: Ställ in växlingsknappen på **På** för att utesluta alla gemensamma mappar i Exchange Online-organisationen. Du kan inte välja specifika gemensamma mappar att utesluta. Låt växlingsknappen stå på Av om du inte vill utesluta gemensamma mappar.
  
   4. Låt den här kryssrutan vara markerad för att söka efter Teams-innehåll för lokala användare. Om du till exempel söker i alla Exchange-postlådor i organisationen när den här kryssrutan är markerad tas molnbaserad lagring som används för att lagra Teams-chattdata för lokala användare med i sökningen. Mer information finns i [Söka efter Teams-chattdata för lokala användare](search-cloud-based-mailboxes-for-on-premises-users.md).

7. På sidan **Definiera dina sökvillkor** skriver du en nyckelordsfråga och lägger till villkor i sökfrågan om det behövs.

   ![Konfigurera sökfrågan](../media/ContentSearchQuery.png)

   1. Ange nyckelord, meddelandeegenskaper, till exempel datum för skickade och mottagna meddelanden, eller dokumentegenskaper som filnamn eller det datum då ett dokument senast ändrades. Du kan använda mer komplexa frågor som innehåller booleska operatorer som **AND**, **OR**, **NOT**, och **NEAR**. Om du lämnar nyckelordsrutan tom inkluderas allt innehåll på den angivna innehållsplatsen i sökresultatet. Mer information finns i [Nyckelordsfrågor och sökvillkor för eDiscovery](keyword-queries-and-search-conditions.md).

   2. Alternativt kan du klicka på kryssrutan **Visa nyckelordlista** och skriva ett nyckelord på varje rad. Om du gör det kopplas nyckelorden på varje rad samman med en logisk operator (**c:s**) som fungerar ungefär som operatorn **OR** i sökfrågan som skapas.

      Varför ska jag använda nyckelordslistan? Du kan få statistik som visar hur många objekt som matchar varje nyckelord. Det kan hjälpa dig att snabbt ta reda på vilka nyckelord som är mest (och minst) effektiva. Du kan också använda en nyckelordsfras (omgiven av parenteser) på en rad. Mer information om nycklelordslistor och sökstatistik finns i [Visa nyckelordsstatistik för sökningar](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).

      > [!NOTE]
      > Eftersom stora nyckelordlistor kan orsaka problem kan du endast använda maximalt 20 rader i nyckelordslistan.

   3. Du kan lägga till sökvillkor om du vill begränsa sökningen och få en mer förfinad uppsättning resultat. Varje villkor lägger till en sats i sökfrågan som skapas och körs när du startar sökningen. Ett villkor kopplas till nyckelordsfrågan (anges i nyckelordsrutan) med en logisk operator (**c:c**) som fungerar ungefär som operatorn **AND**. Det innebär att objekten måste uppfylla både nyckelordsfrågan och ett eller flera villkor för att tas med i resultatet. Det är så du begränsar resultatet med hjälp av villkor. En lista och beskrivning av de villkor som du kan använda i en sökfråga finns i [Sökvillkor](keyword-queries-and-search-conditions.md#search-conditions).

8. Granska sökinställningarna (och redigera om det behövs) och skicka sedan sökningen för att starta den.

När sökningen är klar kan du förhandsgranska sökresultaten. Om det behövs klickar **du på** Uppdatera på **sidan Sökningar** för att visa sökningen som du skapade.

## <a name="more-information-about-searching-content-locations"></a>Mer information om hur du söker efter innehållsplatser

- När du klickar **på Välj användare, grupper** eller team för att ange postlådor att söka i är postlådeväljaren som visas tom. Det här är för att förbättra prestandan. Om du vill lägga till mottagare i listan klickar du på Välj **användare,** grupper eller team , skriver ett namn (minst tre tecken) i sökrutan, markerar kryssrutan bredvid namnet och klickar sedan på **Välj**.

- Du kan lägga till inaktiva postlådor, Microsoft Teams, Yammer-grupper, Office 365-grupper och distributionsgrupper i listan med postlådor att söka i. Dynamiska distributionsgrupper stöds inte. Om du lägger Microsoft Teams, Yammer Grupper eller Office 365 Grupper genomsöks grupp- eller grupppostlådan. Postlådorna för gruppmedlemmarna genomsöks inte.

- Om du vill lägga till webbplatser i sökningen aktiverar du växlingsknappen och klickar sedan på **Välj webbplatser**. Skriv URL:en för varje webbplats som du vill söka i. Du kan också lägga till URL-adressen för en SharePoint för ett Microsoft-team, en Yammer grupp eller en Office 365 grupp.
