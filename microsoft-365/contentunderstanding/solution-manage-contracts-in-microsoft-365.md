---
title: Hantera kontrakt med en Microsoft 365 lösning
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du hanterar kontrakt med en Microsoft 365 lösning av SharePoint Syntex, Microsoft Teams och Power Automate.
ms.openlocfilehash: 806ea9fd048dec198a19fa79f3b60f3f3cb81018
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281314"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>Hantera kontrakt med en Microsoft 365 lösning

I den här artikeln beskrivs hur du skapar en kontraktshanteringslösning för organisationen med hjälp SharePoint Syntex och komponenter i Microsoft 365. Det ger dig ett ramverk som hjälper dig att planera och skapa en lösning som passar dina unika affärsbehov. Även om den här lösningen inte passar dina affärsbehov som helhet kan delar av den användas i din planering för att skapa en anpassad lösning för kontraktshantering.

## <a name="identify-the-business-problem"></a>Identifiera affärsproblemet

Det första steget när du planerar ditt kontraktshanteringssystem är att förstå problemet du försöker lösa. För den här lösningen måste fyra viktiga problem åtgärdas:

- **Identifiera kontrakt**. Din organisation arbetar med många dokument, till exempel fakturor, kontrakt, arbetsutdrag och så vidare.  Vissa är digitala tillgångar som skickas via e-post och vissa är papperstillgångar som skickas via traditionell e-post. Du behöver ett sätt att identifiera alla kundkontrakt i alla andra dokument och sedan klassificera dem som sådana.

- **Spåra historik för kontraktsgodkännanden**. Din organisation behöver ett tillförlitligt sätt att ta reda på om kontrakt har godkänts eller avvisats och om betalningen har bearbetats. 

- **Webbplats för hantering av godkännanden av avtal.** Din organisation måste skapa en webbplats för samarbete där alla nödvändiga intressenter enkelt kan granska kontrakt. Intressenter bör vid behov kunna granska hela avtalet, men det är mest viktigt att se flera nyckelfält från varje kontrakt (till exempel kundnamn, inköpsordernummer och total kostnad). Intressenterna bör enkelt kunna godkänna eller avvisa inkommande kontrakt.

- **Route reviewed contracts**. Godkända och avvisade kontrakt måste dirigeras genom ett visst arbetsflöde. Godkända kontrakt måste dirigeras till en tredjepartsansökan för betalningsbearbetning. Avvisade kontrakt måste dirigeras för ytterligare granskning.

## <a name="overview-of-the-solution"></a>Översikt över lösningen

  ![Översikt över lösningen med hjälp SharePoint Syntex, SharePoint, Teams och Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

Den här lösningen för kontraktshantering innehåller fyra komponenter Microsoft 365:

- **Microsoft SharePoint Syntex**: Skapa modeller för att identifiera och klassificera kontraktsfilerna och extrahera lämplig data från dem.

- **Microsoft SharePoint listor:** Använd den formatering som är tillgänglig i moderna SharePoint för att presentera kontrakt i ett företagsvänligt format.

- **Microsoft Teams:** Använd funktionerna i en Teams kanal och tillhörande flikar så att dina intressenter kan granska och hantera kontrakt.

- **Power Automate:** Använd flöden för att styra kontrakt genom godkännandeprocessen och sedan till ett tredjepartsprogram för betalning.

### <a name="how-it-all-works"></a>Så här fungerar allt

  ![Diagram över lösningen som visar arbetsflödet för att ladda upp dokument, extrahera data, meddela intressenter och godkänna eller avvisa avtalet.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. Dokument laddas upp till ett SharePoint ett dokumentbibliotek. En SharePoint med en förstå-modell för Syntex-dokument har använts i dokumentbiblioteket. Varje fil kontrolleras för att se om någon matchar en typ av innehåll av typen "kontrakt" som filen letar efter. Om en matchning hittas klassificeras filen som ett "kontrakt" och innehållstypen för dokumentet uppdateras.

2. Modellen hämtar även specifika data från varje kontraktsfil som intressenter är intresserade av, till exempel *klient,* leverantörer och *avgiftsbelopp.*

    Följande sida är ett exempel på ett kontrakt som modellen har utbildning för att identifiera.

      ![Exempel på ett kontrakt.](../media/content-understanding/contract.png)

3. I Microsoft Teams är alla intressenter medlemmar i en säker Teams kanal där alla kontrakt i dokumentbiblioteket visas för godkännande eller avvisning. Med hjälp Teams funktioner meddelas alla intressenter när nya kontrakt behöver granskas.
 
4. Med hjälp Power Automate flyttas kontrakt genom godkännandeprocessen i Teams kanalen. När en medlem godkänner ett avtal ändras kontraktsstatusen för att godkännas, alla medlemmar meddelas via ett Teams-inlägg och ett radobjekt skapas för att visa att avtalet är klart för utbetalning. Den här processen kan utökas till att skriva direkt till en betalningsansökan från tredje part.

5.  När en medlem avvisar ett kontrakt ändras statusen till avvisad och alla medlemmar meddelas via ett Teams inlägg.

## <a name="create-the-solution"></a>Skapa lösningen

I nästa avsnitt får du detaljerad information om hur du konfigurerar din lösning för kontraktshantering. Den är uppdelad i tre steg:

- [Steg 1. Använda SharePoint Syntex för att identifiera kontraktsfiler och extrahera data](solution-manage-contracts-step1.md)
- [Steg 2. Använd Microsoft Teams för att skapa din kanal för kontraktshantering](solution-manage-contracts-step2.md)
- [Steg 3. Använd Power Automate för att skapa ett flöde för att bearbeta dina kontrakt](solution-manage-contracts-step3.md)