---
title: Bevara mottagare av hemlig kopia och utökad distributionsgrupp för eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: In-Place, bevarande av juridiska skäl och Microsoft 365 bevarandeprinciper kan du bevara postlådeinnehållet så att det uppfyller efterlevnadskrav och eDiscovery-krav.
ms.openlocfilehash: f00ed951fb68778b9c62ae874c2cca964bd6cb5c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162254"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Bevara mottagare av hemlig kopia och utökad distributionsgrupp för eDiscovery
  
In-Place bevarande, bevarande av juridiska [](./retention.md) skäl och Microsoft 365-bevarandeprinciper (skapas i Säkerhets- och efterlevnadscenter för &) kan du bevara postlådeinnehållet så att det uppfyller efterlevnadskrav och eDiscovery-krav. Information om mottagare som är direkt adresserade i fälten Till och Kopia i ett meddelande tas med i alla meddelanden som standard. Men det kan hända att din organisation måste kunna söka efter och återskapa information om alla mottagare av ett meddelande. Detta omfattar följande:
  
- **Mottagare som hanteras med hjälp av fältet Hemlig kopia i ett meddelande:** Mottagare av hemlig kopia lagras i meddelandet i avsändarens postlåda, men inkluderas inte i meddelanderubrikerna som levereras till mottagarna. 
    
- **Utökade mottagare i distributionsgruppen:** Mottagare som får meddelandet eftersom de är medlemmar i en distributionsgrupp där meddelandet har adresseras, antingen i fälten Till, Kopia eller Hemlig kopia. 
    
Exchange Online och Exchange Server 2013 (kumulativ uppdatering 7 och senare versioner) behåller information om mottagare av hemlig kopia och utökade distributionsgruppsmottagare. Du kan söka efter den här informationen med hjälp av en eDiscoveryIn-Place-sökning i administrationscentret för Exchange (EAC) eller en innehållssökning i säkerhets- &-efterlevnadscentret. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Hur mottagare av hemlig kopia och mottagare i den utökade distributionsgruppen bevaras

Som vi nämnt tidigare lagras information om hemlig kopias mottagare med meddelandet i avsändarens postlåda. Den här informationen indexeras och är tillgänglig för eDiscovery-sökningar och eDiscovery-rymmer. 
  
Information om mottagare i en expanderad distributionsgrupp lagras med meddelandet när du placerar en postlåda på plats In-Place bevarande av juridiska skäl eller Bevarande av juridiska skäl. I Office 365 lagras den här informationen även när Microsoft 365 bevarandeprincip tillämpas på en postlåda. Medlemskap i distributionsgruppen bestäms när meddelandet skickas. Den utökade mottagare som lagras med meddelandet påverkas inte av ändringar av medlemskap i gruppen när meddelandet skickas. 
  
| Information om... | Lagras i... | Lagras som standard? | Är tillgänglig för... |
|:-----|:-----|:-----|:-----|
|Mottagare av till och kopia  <br/> |Meddelandeegenskaper i avsändarens och mottagarnas postlådor.  <br/> |Ja  <br/> |Avsändare, mottagare och efterlevnadsansvariga  <br/> |
|Mottagare av hemlig kopia  <br/> |Meddelandeegenskap i avsändarens postlåda.  <br/> |Ja  <br/> |Sändare och efterlevnadsansvariga  <br/> |
|Utökade mottagare i distributionsgruppen  <br/> |Meddelandeegenskaper i avsändarens postlåda.  <br/> |Nej. Expanderad mottagarinformation för distributionsgruppen lagras när en postlåda placeras på plats In-Place bevarande av juridiska skäl eller tilldelas till en Microsoft 365 bevarandeprincip.  <br/> |Efterlevnadsansvariga  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Söka efter meddelanden som skickats till Hemlig kopia och expanderat distributionsgruppsmottagare

När du söker efter meddelanden som skickats till en mottagare innehåller eDiscovery-sökresultat nu meddelanden som skickats till en distributionsgrupp där mottagaren är medlem. I följande tabell visas scenarier där meddelanden som skickas till Hemlig kopia och utökade mottagare i distributionsgruppen returneras i eDiscovery-sökningar.
  
Scenario 1: John är medlem i US-Sales distributionsgrupp. I den här tabellen visas eDiscovery-sökresultat när Bob skickar ett meddelande till Johan direkt eller indirekt via en distributionsgrupp.
  
| När du söker i Bobs postlåda efter skickade meddelanden ... | Meddelandet skickas med... | Innehåller resultatet meddelande? |
|:-----|:-----|:-----|
|Till:John  <br/> |John på TO  <br/> |Ja  <br/> |
|Till:John  <br/> |US-Sales på TO  <br/> |Ja  <br/> |
|Till:US-Sales  <br/> |US-Sales på TO  <br/> |Ja  <br/> |
|Kopia:John  <br/> |John på kopia  <br/> |Ja  <br/> |
|Kopia:John  <br/> |US-Sales på kopia  <br/> |Ja  <br/> |
|Kopia:US-Sales  <br/> |US-Sales på kopia  <br/> |Ja  <br/> |
   
Scenario 2: Bob skickar ett e-postmeddelande till John (To/Cc) och Jack (Bcc direkt eller indirekt via en distributionsgrupp). I tabellen nedan visas eDiscovery-sökresultat.
  
| När du söker ... | För meddelanden som skickats... | Innehåller resultatet meddelande? | Kommentar |
|:-----|:-----|:-----|:-----|
|Bobs postlåda  <br/> |Till/Kopia:John  <br/> |Ja  <br/> |Visar en indikation på att Jack var Hemlig kopia.  <br/> |
|Bobs postlåda  <br/> |Hemlig kopia:Jack  <br/> |Ja  <br/> |Visar en indikation på att Jack var Hemlig kopia.  <br/> |
|Bobs postlåda  <br/> |Hemlig kopia:Jack (via distributionsgrupp)  <br/> |Ja  <br/> |Listan över medlemmar i distributionsgruppen Hemlig kopia, expanderad när meddelandet skickades, visas i förhandsgranskning, export och loggar för eDiscovery-sökning.  <br/> |
|Johns postlåda  <br/> |Till/Kopia:John  <br/> |Ja  <br/> |Ingen indikation på mottagare av hemlig kopia.  <br/> |
|Johns postlåda  <br/> |Hemlig kopia:Jack (direkt eller via distributionsgrupp)  <br/> |Nej  <br/> |Informationen om Hemlig kopia lagras inte i meddelandet som levereras till mottagarna. Du måste söka i avsändarens postlåda.  <br/> |
|Jacks postlåda  <br/> |Till/Kopia:John (direkt eller via distributionsgrupp)  <br/> |Ja  <br/> |Information om Till/Kopia inkluderas i meddelanden som levereras till alla mottagare.  <br/> |
|Jacks postlåda  <br/> |Hemlig kopia:Jack (direkt eller via distributionsgrupp)  <br/> |Nej  <br/> |Informationen om Hemlig kopia lagras inte i meddelandet som levereras till mottagarna. Du måste söka i avsändarens postlåda.  <br/> |
   
## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

 **F. När och var lagras mottagarinformationen för Hemlig kopia?**
  
A. Mottagarens information om hemlig kopia sparas som standard i det ursprungliga meddelandet i avsändarens postlåda. Om mottagaren av den hemlig kopian är en distributionsgrupp utökas medlemskapet i distributionsgruppen endast om avsändarens postlåda är spärrad eller tilldelad Microsoft 365 bevarandeprincip.
  
 **F. När och var lagras listan med utökade mottagare i distributionsgruppen?**
  
A. Gruppmedlemskap utökas när meddelandet skickas. Listan över expanderade medlemmar i distributionsgruppen lagras i det ursprungliga meddelandet i avsändarens postlåda. Avsändarens postlåda måste finnas på plats In-Place, bevarande av juridiska skäl eller tilldelad till en Microsoft 365 bevarandeprincip.
  
 **F. Kan mottagarna av Till/Kopia se vilka mottagare som skickades hemlig kopia?**
  
A. Nej. Den här informationen ingår inte i meddelanderubriker och visas inte för mottagare av till/kopia. Avsändaren kan se fältet Hemlig kopia i det ursprungliga meddelandet som lagrats i postlådan. Efterlevnadsansvariga kan se den här informationen vid sökning i avsändarens postlåda.
  
 **F. Hur kan jag se till att mottagare i en utökad distributionsgrupp alltid bevaras?**
  
A. Om du vill se till att utökade medlemmar [](/Exchange/policy-and-compliance/holds/place-all-mailboxes-on-hold) i distributionsgruppen alltid bevaras med ett meddelande kan du skapa en bevarandeprincip för alla postlådor eller Microsoft 365 hela organisationen. 
  
 **F. Vilka typer av grupper stöds?**
  
A. Distributionsgrupper, e-postaktiverade säkerhetsgrupper och dynamiska distributionsgrupper stöds. 
  
 **F. Finns det någon gräns för antalet mottagare i distributionsgruppen som utökas och lagras i meddelandet?**
  
A. Upp till 10 000 medlemmar i en distributionsgrupp bevaras.
  
 **F. Stöds kapslade distributionsgrupper?**
  
A. Ja, 25 nivåer med kapslade distributionsgrupper utökas.
  
 **F. Var visas mottagarinformationen för Hemlig kopia och utökad distributionsgrupp?**
  
A. Mottagare i hemlig kopia och utökad distributionsgrupp visas för efterlevnadsansvariga när de utför en eDiscovery-sökning. Mottagare av hemlig kopia och utökad distributionsgrupp ingår i sökresultat som kopieras till en identifieringspostlåda eller exporteras till en PST-fil och i eDiscovery-loggen som ingår i sökresultatet. Mottagarinformation för hemlig kopia är också tillgänglig i förhandsgranskningen.
  
 **F. Vad händer om en medlem i en distributionsgrupp är dold från organisationens globala adresslista (GAL)?**
  
A. Det gör ingen effekt. Om mottagare är dolda från den utökade distributionsgruppen ingår de fortfarande i listan över mottagare i den utökade distributionsgruppen.