---
title: Skapa och kör en innehållssökning i Microsoft 365 Efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Använd eDiscovery-verktyget Innehållssökning i efterlevnadscentret för att söka efter innehåll i olika Microsoft 365-tjänster.
ms.openlocfilehash: a058c07d080962723e9f6bc7a150cbfb5074e7db
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311679"
---
# <a name="create-a-content-search"></a>Skapa en innehållssökning

Du kan använda eDiscovery-verktyget Innehållssökning Microsoft 365 Efterlevnadscenter för att söka efter lokalt innehåll, till exempel e-post, dokument och snabbmeddelandekonversationer i organisationen. Använd det här verktyget för att söka efter innehåll i följande Microsoft 365-datakällor:
  
- Exchange Online-postlådor

- SharePoint Online-webbplatser och OneDrive för företag-konton

- Microsoft Teams

- Microsoft 365-grupper

- Yammer-grupper

När du har kört en innehållssökning visas antalet innehållsplatser och ett uppskattat antal sökresultat den utfällbara söksidan. Du kan snabbt visa statistik, till exempel vilka innehållsplatser som har flest objekt som matchar sökfrågan. När du har kört en sökning kan du förhandsgranska resultaten eller exportera dem till en lokal dator.

## <a name="create-and-run-a-search"></a>Skapa och kör en sökning

För att komma åt sidan **Innehållssökning** i Microsoft 365 Efterlevnadscenter (för att köra sökningar och för att förhandsgranska och exportera resultat) måste en administratör, efterlevnadsansvarig eller eDiscovery-hanterare vara medlem i rollgruppen eDiscovery Manager i Säkerhets- och efterlevnadscentret. Mer information finns i [Tilldela eDiscovery-behörigheter](assign-ediscovery-permissions.md).
  
1. Gå till <https://compliance.microsoft.com> och logga in med autentiseringsuppgifterna för ett konto som har tilldelats rätt behörigheter.

2. I det vänstra navigeringsfönstret i Microsoft 365 Efterlevnadscenter klickar du på **Visa alla** och sedan på **Innehållssökning**.

3. Klicka på **Ny sökning** på sidan **Innehållssökning**.

   > [!NOTE]
   > Med **Sök efter ID-lista**-alternativet kan du söka efter specifika e-postmeddelanden och andra postlådeobjekt med hjälp av en lista med Exchange-ID:n. Om du vill skapa en sökning med en ID-lista skickar du en fil med kommaavgränsade värden (CSV) som identifierar de specifika postlådeobjekt som du vill söka efter. Anvisningar finns i [Förbereda en CSV-fil för en ID-listsökning](csv-file-for-an-id-list-content-search.md).

4. Ange ett namn för sökningen, en valfri beskrivning som hjälper dig att identifiera sökningen. Namnet på sökningen måste vara unikt i din organisation.

5. På sidan **Platser** väljer du innehållsplatserna som du vill söka i. Du kan söka i postlådor, webbplatser och gemensamma mappar.

    ![Välj vilka innehållsplatser som ska vara undantagna](../media/ContentSearchLocations.png)
  
   1. **Exchange-postlådor**: Ställ in växlingsknappen på **På** och klicka sedan på **Välj användare, grupper eller teams** för att ange vilka postlådor som inte ska ingå. Använd sökrutan för att hitta användarpostlådor och distributionsgrupper (för att undanta gruppmedlemmars postlådor) som ska uteslutas. Du kan också söka i postlådan som är kopplad till ett Microsoft-team (för kanalmeddelanden), Office 365-grupp och Yammer-grupp. Mer information om programdata som har lagrats i postlådor finns i [Innehåll som lagras i postlådor för eDiscovery](what-is-stored-in-exo-mailbox.md).

   2. **SharePoint-webbplatser**: Ställ in växlingsknappen på **På** och klicka sedan på **Välj webbplatser** för att ange SharePoint-webbplatser och OneDrive-konton som ska uteslutas. Skriv in URL-adressen för varje webbplats som du vill utesluta. Du kan också lägga till URL-adressen till SharePoint-webbplatsen för ett Microsoft-team, Office 365-grupp eller Yammer-grupp.
  
   3. **Gemensamma Exchange-mappar**: Ställ in växlingsknappen på **På** för att utesluta alla gemensamma mappar i Exchange Online-organisationen. Du kan inte välja specifika gemensamma mappar att utesluta. Låt växlingsknappen stå på Av om du inte vill utesluta gemensamma mappar.
  
   4. Låt den här kryssrutan vara markerad för att söka efter Teams-innehåll för lokala användare. Om du till exempel söker i alla Exchange-postlådor i organisationen när den här kryssrutan är markerad tas molnbaserad lagring som används för att lagra Teams-chattdata för lokala användare med i sökningen. Mer information finns i [Söka efter Teams-chattdata för lokala användare](search-cloud-based-mailboxes-for-on-premises-users.md).

6. På sidan **Definiera dina sökvillkor** skriver du en nyckelordsfråga och lägger till villkor i sökfrågan om det behövs.

   ![Konfigurera sökfrågan](../media/ContentSearchQuery.png)

   1. Ange nyckelord, meddelandeegenskaper, till exempel datum för skickade och mottagna meddelanden, eller dokumentegenskaper som filnamn eller det datum då ett dokument senast ändrades. Du kan använda mer komplexa frågor som innehåller booleska operatorer som **AND**, **OR**, **NOT**, och **NEAR**. Om du lämnar nyckelordsrutan tom inkluderas allt innehåll på den angivna innehållsplatsen i sökresultatet. Mer information finns i [Nyckelordsfrågor och sökvillkor för eDiscovery](keyword-queries-and-search-conditions.md).

   2. Alternativt kan du klicka på kryssrutan **Visa nyckelordlista** och skriva ett nyckelord på varje rad. Om du gör det kopplas nyckelorden på varje rad samman med en logisk operator (**c:s**) som fungerar ungefär som operatorn **OR** i sökfrågan som skapas.

      Varför ska jag använda nyckelordslistan? Du kan få statistik som visar hur många objekt som matchar varje nyckelord. Det kan hjälpa dig att snabbt ta reda på vilka nyckelord som är mest (och minst) effektiva. Du kan också använda en nyckelordsfras (omgiven av parenteser) på en rad. Mer information om nycklelordslistor och sökstatistik finns i [Visa nyckelordsstatistik för sökningar](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).

      > [!NOTE]
      > Eftersom stora nyckelordlistor kan orsaka problem kan du endast använda maximalt 20 rader i nyckelordslistan.

   3. Du kan lägga till sökvillkor om du vill begränsa sökningen och få en mer förfinad uppsättning resultat. Varje villkor lägger till en sats i sökfrågan som skapas och körs när du startar sökningen. Ett villkor kopplas till nyckelordsfrågan (anges i nyckelordsrutan) med en logisk operator (**c:c**) som fungerar ungefär som operatorn **AND**. Det innebär att objekten måste uppfylla både nyckelordsfrågan och ett eller flera villkor för att tas med i resultatet. Det är så du begränsar resultatet med hjälp av villkor. En lista och beskrivning av de villkor som du kan använda i en sökfråga finns i [Sökvillkor](keyword-queries-and-search-conditions.md#search-conditions).

7. Granska sökinställningarna (och redigera om det behövs) och skicka sedan sökningen för att starta den.
  
Du kommer åt den här innehållssökningen igen, eller andra innehållssökningar som visas på sidan **Innehållssökning**, genom att markera sökningen och klicka på **Öppna**.
  
## <a name="next-steps"></a>Nästa steg

Här är en lista över efterföljande steg som du kan utföra när du har skapat och kört en innehållssökning.

- [Förhandsgranska sökresultaten](preview-ediscovery-search-results.md)

- [Visa statistik för sökresultaten](view-keyword-statistics-for-content-search.md)

- [Exportera sökresultaten](export-search-results.md)

- [Exportera en sökrapport](export-a-content-search-report.md)
