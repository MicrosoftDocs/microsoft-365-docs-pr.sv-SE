---
title: Hantera s.Advanced eDiscovery s Advanced eDiscovery sn
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lär dig hur du visar detaljer, redigerar och massredigerer listan med dokumentare i Advanced eDiscovery fall.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/30/2020
ms.locfileid: "52161706"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Hantera s.Advanced eDiscovery s Advanced eDiscovery sn

Sidan Dokument på fliken Källor **i ett** Advanced eDiscovery innehåller en lista över alla dokumentare som har lagts till i ärendet. När du har lagt till vårdnadshavare till ett ärende samlas information om varje enskild person automatiskt in Azure Active Directory och visas i Advanced eDiscovery.

![Hantera sn30-bibliotek](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>Visa information om innnarna

Om du vill visa information om en vårdnadshavare klickar du på den som har namn på listan på fliken **Informatiska.** En utfällningssida visas och innehåller följande information om den som är den som har befallt dig:

- Kontaktinformation

  - **Visningsnamn** – Det namn som visas i adressboken för den som är vårdnadshavare. Det här är vanligtvis en kombination av den som förnamn, initial för mellannamn och efternamn.
  
   - **Mail/SMTP** – Den primära SMTP-adressen för den som förser dokument med till exempel brianj@contoso.onmicrosoft.com. Den här användarens huvudnamn (UPN) visas också.

  - **Titel** – Den inseriska befattningen.

  - **Avdelning** – Namnet på avdelningen där den som förser den som arbetar.

  - **Chef** – den insertsiska chefen. Den utsedda chefen får eskaleringsmeddelanden till den här måsteen.
  
- Platsinformation

  - **Ort** – Den stad där den som är vårdnadshavare finns.

  - **Delstat** – delstat eller provins i den uppsnadiskt beserds adress.

  - **Land/region** – Landet/regionen där den som förser dig finns.

  - **Office** – Platsen för kontor i den som äger företaget.

- Ärendeinformation

  - **Status för håll** – anger om den som har blivit insnist har satts på is. 

  - **Kommunikationsstatus**: Anger om certifikats uppger att han eller hon har utfärdat en avis om väntande kort. Om certifikatägaren har utfärdat en avis är värdet för den här egenskapen **Publicerad.** Om den vårdnadshavare som inte har utfärdats ett meddelande är statusen **Ej publicerad.** 

  - **Status** – Den insereriska statusen i ärendet. En status för **Aktiv** anger att den som förser händelsen är en del av händelsen. Om en vårdnadshavare frisläpps från ett ärende ändras status till **Släppt**. 

- Datakällor och indexeringsinformation

    - **Datakällor** – Visar antalet och typen av datakällor (postlådor, webbplatser och Teams) som är kopplade till den vårdnadshavare och som är en del av ärendet.

    - **Uppdaterad tid för index** – Anger tid och datum för när det avancerade indexeringsjobbet senast utlöstes. Den här egenskapen anger också när den avancerade indexeringsprocessen pågår.


## <a name="edit-a-custodian"></a>Redigera en vårdnadshavare

I ditt fall kanske du upptäcker att det kan finnas ytterligare datakällor som är relevanta för en specifik & ditt ärende. I andra fall kanske du vill ta bort vissa datakällor som har granskats och anses som inte relevanta.

Så här uppdaterar du datakällorna som är associerade med en datakälla:

1. Gå till **eDiscovery > Advanced eDiscovery** och öppna ärendet.
  
2. Klicka på **fliken** Källor.
  
3. På sidan **Förser** med dokument väljer du en dokumenterare från listan och **klickar på Redigera** på den utfällade sidan.

    ![Redigera datakällor](../media/EditCustodianDataSource.PNG)
  
4. Klicka **på fliken Välj datakällor** om du vill ändra inställningarna för den uppsl själva postlådan Exchange den andra postlådan och OneDrive konto klickar du på Välj **datakällor.**
  
5. Klicka på **fliken Välj ytterligare datakällor** för att lägga till eller ta bort Teams, SharePoint postlådor Exchange postlådor associerade med den inserre. 

    Mer information om datakällor som är associerade med en vårdnadshavare finns i [Lägga till vårdnadshavare i ett ärende.](add-custodians-to-case.md) 
  
6. Klicka **på Håll i förvar** för att aktivera eller inaktivera förvaringen för den som äger platsen.

## <a name="re-index-custodian-data"></a>Omindexering av data

I de flesta eDiscovery-arbetsflöden för juridiska undersökningar genomsöks en delmängd av en dokumentares data efter att den vårdnadshavare som har lagts till i ett juridiskt ärende. På grund av mycket stora filstorlekar eller eventuella skadade data kan vissa objekt i datakällorna som är associerade med en vårdnadshavare delvis indexeras delvis. Med hjälp [av](indexing-custodian-data.md) den avancerade indexeringsfunktionerna i Advanced eDiscovery kan de flesta delvis indexerade objekt åtgärdas automatiskt genom att indexera om objekten på begäran.

Om en vårdnadshavare läggs till i ett ärende indexeras de data som är associerade med den vårdnadshavaren automatiskt om (genom den avancerade indexeringsprocessen). Det innebär att du kan låta data vara kvar i stället för att behöva ladda ned och åtgärda dem och sedan söka dem offline). Under livscykeln för ett juridiskt ärende kan det hända att nya datakällor kopplas till en dokumenterare. I det här fallet kan du indexera om den uppsövandes data genom att köra den avancerade indexeringsprocessen igen för att åtgärda alla delvis indexerade objekt och uppdatera indexet för de objekt som inte kan indexeras.

Så här utlöser du omindexeringsprocessen för att hantera delvis indexerade objekt:

1. Gå till **eDiscovery > Advanced eDiscovery** och öppna ärendet.

2. Klicka på **fliken** Källor.

3. På sidan **Förserna** väljer du en användare vars data måste indexeras om.

4. På den utfällade sidan klickar du **på Uppdatera index.**

   En dialogruta visas om att indexjobbet har skapats.

Omindexering av registrerade data är en långvariga process. Motsvarande jobb som skapas heter Omindexering av **data.** Du kan spåra förloppet på **fliken** Jobb eller på fliken Förnamn genom att övervaka statusen i kolumnen **Status för indexerat** jobb. 

Mer information finns i:

- [Arbeta med bearbetning av fel](processing-data-for-case.md)

- [Hantera jobb](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Släppa en vårdnadshavare från ett ärende

En vårdnadshavare frisläpps i situationer där ett ärende är avslutat, den som har en ansvarsskyldighet för att bevara innehållet för ett ärende eller när den som ska behåller sitt ärende inte längre anses vara relevant för ärendet. 

Om du släpper en vårdnadshavare efter att ett meddelande om förvaring publicerades, skickas ett meddelande om detta till den som har skickat in ett meddelande om detta. Dessutom tas eventuella spärrade fall i datakällor som var kopplade till den som var associerad med den som äger den bort. Om den vårdnadshavaren spärrades i tyst läge *,* där de inte har utfärdats någon form av aviseringar om juridiskt tillstånd, skickas inget meddelande om detta, men eventuella meddelanden som gjorts i datakällor som är associerade med den platsen tas bort.

Så här släpper du en vårdnadshavare: 

1. Gå till **eDiscovery > Advanced eDiscovery** och öppna ärendet.

2. Klicka på **fliken** Källor.

3. På sidan **Förserna** och väljer sedan den insläppta person som ska friges från ärendet.

4. På den utfällningssida som visas klickar du **på Släppenerer.**

   En varningssida visas med en förklaring om att om ett förvaringstecken placeras i en datakälla som är kopplad till den vårdnadshavaren tas det bort, att förvaringen kommer att tas bort och att alla andra förvaringstecken som är kopplade till ett annat Advanced eDiscovery gäller fortfarande. Det omfattar andra typer av bevarande- och kvarhållningsfunktioner (till exempel Microsoft 365 bevarandeprincip).

5. Klicka **på Ja** för att bekräfta att du vill släppa upp den som insläppt. 

    Statusen för den här användaren **på**  fliken Förfallna sidor är Inställd på Släppt och **Status** för Håll på den utfällade sidan ändras till **Falskt.** 

> [!NOTE]
> En vårdnadshavare kan vara inblandade i flera rättsfall samtidigt. Om en vårdnadshavare frisläpps från ett ärende påverkas inte kvarhållen eller meddelanden från andra ärenden.

## <a name="bulk-edit-custodians"></a>Massredigering av dokument dokument

Du kan använda massredigeraren för att redigera flera objekt samtidigt. Det gör du genom att markera två  eller flera objekt på fliken Oformatörare för att visa massredigeraren och sedan klicka på en av uppgifterna.

![Utfällningssida för att redigera inställningar för flera dokumentare](../media/AeDBulkEditCustodians.png)
