---
title: Komma igång med core eDiscovery-ärenden i Microsoft 365
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
description: Här beskrivs hur du kommer igång med Core eDiscovery i Microsoft 365. När du tilldelar eDiscovery-behörigheter och skapar ett ärende kan du lägga till medlemmar, skapa eDiscovery-innehåll som sätts i innehåll och sedan söka efter och exportera innehåll som är relevant för din undersökning.
ms.openlocfilehash: 9466b2e3268a447a4008363e88290d4d02558c76
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341478"
---
# <a name="get-started-with-core-ediscovery-in-microsoft-365"></a>Komma igång med Core eDiscovery i Microsoft 365

Core eDiscovery i Microsoft 365 innehåller ett grundläggande eDiscovery-verktyg som organisationer kan använda för att söka efter och exportera innehåll i Microsoft 365 och Office 365. Du kan också använda Grundläggande eDiscovery för att placera ett eDiscovery-värde på innehållsplatser, till exempel Exchange-postlådor, SharePoint-webbplatser, OneDrive-konton och Microsoft Teams. Inget krävs för att distribuera Bas-eDiscovery, men det finns vissa nödvändiga uppgifter som en IT-administratör och eDiscovery-hanterare måste slutföra innan organisationen kan börja använda Core eDiscovery för att söka, exportera och bevara innehåll.

I den här artikeln beskrivs de steg som krävs för att konfigurera Bas-eDiscovery. Detta omfattar att säkerställa korrekt licensiering som krävs för att få tillgång till Core eDiscovery och placera ett eDiscovery-värde på innehållsplatser, samt att tilldela behörigheter till din IT-grupp, din juridiska grupp och din undersökningsteam så att de kan komma åt och hantera ärenden. Den här artikeln innehåller också en översikt över hur fall kan söka efter och exportera innehåll.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Steg 1: Verifiera och tilldela rätt licenser

Licensiering för bas-eDiscovery kräver rätt organisationsprenumeration och licensiering per användare.

- **Organisationsprenumeration:** För att få tillgång till grundläggande eDiscovery i Microsoft 365 Efterlevnadscenter eller Office 365 Security & Compliance Center och använda funktionerna för att hålla och exportera måste organisationen ha en Microsoft 365 E3 eller Office 365 E3-prenumeration eller senare.

- **Licensiering per användare:** För att kunna skapa ett eDiscovery-tillstånd för postlådor och webbplatser måste en användare tilldelas någon av följande licenser, beroende på organisationens prenumeration:

  - En Microsoft 365 E3 licens Office 365 E3 eller senare

   ELLER

  - Office 365 E1 licens med Exchange Online abonnemang 2 eller Exchange Online - arkivering med tilläggslicens

  OCH

  - Office 365 E1 licens med en tilläggslicens SharePoint Online abonnemang 2 OneDrive för företag abonnemang 2
  
  Mer information om hur du tilldelar licenser finns [i Tilldela licenser till användare.](../admin/manage/assign-licenses-to-users.md)

För information om licensiering:

- Ladda ned och se "Discover & Respond"-lösningen i jämförelse [av Microsoft 365 kompatibilitetslicensiering.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

- Se [tjänstbeskrivningen & Säkerhets- och efterlevnadscenter.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="step-2-assign-ediscovery-permissions"></a>Steg 2: Tilldela eDiscovery-behörigheter

För att få åtkomst till grundläggande eDiscovery eller läggas till som medlem i ett core eDiscovery-ärende måste användaren tilldelas rätt behörigheter. Mer specifikt måste en användare läggas till som medlem i rollgruppen för eDiscovery Manager Office 365 Säkerhets- & efterlevnadscenter. Medlemmar i den här rollgruppen kan skapa och hantera grundläggande eDiscovery-ärenden. De kan lägga till och ta bort medlemmar, lägga till och ta bort eDiscovery-innehåll för användare, skapa och redigera sökningar och exportera innehåll från en core eDiscovery-fråga.

Utför följande steg för att lägga till användare i rollgruppen för eDiscovery-hanteraren:

1. Gå till <https://compliance.microsoft.com/permissions> och logga in med autentiseringsuppgifterna för ett administratörskonto i din Microsoft 365 eller Office 365 organisation.

2. På sidan **Behörigheter** väljer du **rollgruppen för eDiscovery-hanteraren.**

3. På den utfällande sidan för eDiscovery Manager klickar **du på** Redigera bredvid **avsnittet eDiscovery Manager.**

4. Klicka på Välj Identifieringshanteraren i guiden För redigeringsroll på sidan Välj **eDiscovery** **Manager.**

5. Klicka **på** Lägg till och markera kryssrutan för alla användare som du vill lägga till i rollgruppen.

6. Klicka **på Lägg** till för att lägga till de valda användarna och klicka sedan på **Klar**.

7. Klicka **på** Spara för att lägga till användarna i rollgruppen och klicka sedan **på Stäng** för att slutföra steget.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Mer information om rollgruppen för eDiscovery-hanteraren

Det finns två undergrupper i rollgruppen för eDiscovery-hanteraren. Skillnaden mellan dessa undergrupper beror på omfattningen.

- **eDiscovery Manager:** Kan visa och hantera core eDiscovery-fall som de skapar eller är medlemmar i. Om en annan eDiscovery Manager skapar ett ärende men inte lägger till en andra eDiscovery Manager som medlem i det fallet kan inte den andra eDiscovery-hanteraren visa eller öppna ärendet på Core eDiscovery-sidan i efterlevnadscentret. I allmänhet kan de flesta i organisationen läggas till i undergruppen för eDiscovery Manager.

- **eDiscovery-administratör:** Kan utföra alla uppgifter som en eDiscovery-hanterare kan utföra. En eDiscovery-administratör kan dessutom:

  - Visa alla ärenden som listas på sidan Bas-eDiscovery.
  
  - Hantera alla ärende i organisationen när de har lagt till sig själva som medlem i ärendet.

  - Access och exportera ärendedata för alla fall i organisationen.

  På grund av den breda omfattningen av åtkomst bör en organisation bara ha ett fåtal administratörer som är medlemmar i undergruppen eDiscovery-administratörer.

Mer information om eDiscovery-behörigheter och en beskrivning av varje roll som tilldelas till rollgruppen för eDiscovery-hanteraren finns i Tilldela [eDiscovery-behörigheter.](assign-ediscovery-permissions.md)

## <a name="step-3-create-a-core-ediscovery-case"></a>Steg 3: Skapa ett grundläggande eDiscovery-ärende

Nästa steg är att skapa ett ärende och börja använda Core eDiscovery. Så här skapar du ett ärende och lägger till medlemmar. Den användare som skapar ärendet läggs automatiskt till som medlem.

1. Gå till [https://compliance.microsoft.com](https://compliance.microsoft.com) och logga in med autentiseringsuppgifterna för ett användarkonto som har tilldelats lämpliga eDiscovery-behörigheter. Medlemmar i rollgruppen Organisationshantering kan också skapa grundläggande eDiscovery-ärenden.

2. I navigeringsfönstret till vänster på fliken Microsoft 365 Efterlevnadscenter på Visa **alla** och sedan på **eDiscovery > Core**.

3. På sidan **Bas-eDiscovery** klickar du på **Skapa ett ärende.**

4. På den **utfällbara** sidan Nytt ärende ger du ärendet ett namn (obligatoriskt) och skriver en valfri beskrivning. Namnet på ärendet måste vara unikt inom organisationen.

5. Klicka **på Spara** för att skapa ärendet.

   Det nya ärendet skapas och visas på sidan Bas-eDiscovery. Du kan behöva klicka på **Uppdatera för** att visa det nya ärendet.

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>Steg 4 (valfritt): Lägga till medlemmar i ett grundläggande eDiscovery-ärende

Om du skapar ett ärende i steg 3 och är den enda personen som kommer att använda ärendet behöver du inte utföra det här steget. Du kan börja använda ärendet för att skapa eDiscovery-innehåll, söka efter innehåll och exportera sökresultat. Utför det här steget om du vill ge andra användare (eller rollgrupper) åtkomst till ärendet.

1. På sidan **Bas-e-dataidentifiering** i Microsoft 365 Efterlevnadscenter klickar du på namnet på det ärende som du vill lägga till medlemmar i.

2. På startsidan för ärendet väljer du fliken **Inställningar** och väljer sedan Access & **behörigheter.**

3. På den **utfäll & i Access** klickar du på Lägg **till** under Medlemmar **för** att lägga till medlemmar i ärendet.

    Du kan också välja att lägga till rollgrupper som medlemmar i ett ärende. Klicka **på Lägg till** under **Rollgrupper.** Du kan bara tilldela rollgrupper där du är medlem i ett ärende. Det beror på att rollgrupper styr vem som kan tilldela medlemmar till ett e-dataidentifieringsfall.

4. I listan över personer eller rollgrupper som kan läggas till som medlemmar i ärendet klickar du till vänster om namnet på de personer (eller rollgrupper) som du vill lägga till. Om du har en stor lista över personer eller rollgrupper som kan läggas till som medlemmar kan du använda sökrutan för att söka efter en specifik person eller rollgrupp i listan. 
  
5. När du har valt de personer eller rollgrupper  du vill lägga till som medlemmar i ärendet klickar du på Spara för att spara de nya medlemmarna eller rollgrupperna.

## <a name="explore-the-core-ediscovery-workflow"></a>Utforska eDiscovery-kärnarbetsflödet

Här är ett enkelt arbetsflöde för att skapa eDiscovery som kan hjälpa dig att komma igång med att använda grundläggande eDiscovery, söka efter innehåll som är relevant för din undersökning och sedan exportera dessa data för ytterligare granskning. I vart och ett av de här stegen kommer vi också att belysa vissa utökade grundläggande eDiscovery-funktioner som du kan utforska.

![Basarbetsflöde för eDiscovery](../media/CoreEdiscoveryWorkflow.png)

1. **[Skapa ett eDiscovery-hold](create-ediscovery-holds.md)**. Det första steget när ett ärende har skapats är att sätta ett värde på (kallas även *för ett e-dataidentifieringsland)* för innehållsplatserna för de personer som är intressanta för din undersökning. Innehållsplatserna omfattar Exchange postlådor, SharePoint webbplatser, OneDrive-konton och postlådor och webbplatser som är kopplade till Microsoft Teams och Office 365 Grupper. Även om det här steget är valfritt behålls innehåll som kan vara relevant för ärendet under undersökningen om du skapar ett bevarande av e-dataidentifiering. När du skapar ett bevarande för e-dataidentifiering kan du bevara allt innehåll på specifika innehållsplatser eller skapa ett frågebaserat bevarande för att bara bevara det innehåll som matchar en bevarandefråga. Förutom att bevara innehållet är ett annat bra skäl att skapa eDiscovery-innehåll snabbt söka efter platser för innehåll som är spärrade (i stället för att behöva välja varje plats att söka på) när du skapar och kör sökningar i nästa steg. När du har slutfört undersökningen kan du släppa alla väntande ändringar som du har skapat.

2. **[Söka efter innehåll](search-for-content-in-core-ediscovery.md)**. När du har skapat eDiscovery-innehåll kan du använda det inbyggda sökverktyget för att söka på platser för innehåll som är spärrade. Du kan också söka efter data som kan vara relevanta för ärendet på andra innehållsplatser. Du kan skapa och köra olika sökningar som är kopplade till ärendet. Du använder nyckelord, egenskaper [](keyword-queries-and-search-conditions.md) och villkor för att skapa sökfrågor som returnerar sökresultat med de data som troligen är relevanta för ärendet. Du kan också:

   - Visa sökstatistik som kan hjälpa dig att förfina sökningen för att begränsa resultatet.

   - Förhandsgranska sökresultaten för att snabbt kontrollera om relevanta data hittas.

   - Ändra en fråga och kör sökningen igen.

3. **[Exportera och ladda ned sökresultat](export-content-in-core-ediscovery.md)**. När du söker efter och hittar data som är relevanta för din undersökning kan du exportera dem från Office 365 för granskning av personer utanför undersökningsteamet. Att exportera data är en process i två steg. Det första steget är att exportera resultatet av en sökning från en Office 365. Du uppnår detta genom att kopiera resultatet av en sökning till en plats som tillhandahålls Azure Storage Microsoft. Nästa steg är att använda verktyget för eDiscovery-export för att ladda ned innehållet till en lokal dator. Förutom de exporterade datafilerna innehåller innehåller exportpaketet även en exportrapport, en sammanfattningsrapport och en felrapport.
