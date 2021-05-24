---
title: Distribuera tillägg i administrationscentret
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Lär dig att distribuera tillägg till användare och grupper i organisationen med hjälp av centraliserad distribution i administrationscentret.
ms.openlocfilehash: 8cc4f29cd2593d9651edaf87791f46dabdcc30b2
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636028"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Distribuera tillägg i administrationscentret

Office tillägg hjälper dig att anpassa dina dokument och förenkla åtkomsten till information på webben (se Börja använda [Office-tillägg).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) Som administratör kan du distribuera Office tillägg för användarna i organisationen med hjälp av funktionen för centraliserad distribution Microsoft 365 administrationscentret. Centraliserad distribution är den rekommenderade och mest funktionsrika lösningen för de flesta administratörer för att distribuera tillägg till användare och grupper inom en organisation.

Mer information om hur du fastställer om organisationen kan stödja centraliserad distribution finns i Avgöra om centraliserad distribution av tillägg [fungerar för din organisation.](centralized-deployment-of-add-ins.md)

Mer information om hur du hanterar tillägg efter distributionen finns [i Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  För Word använder Excel och PowerPoint en [SharePoint-programkatalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) för att distribuera tillägg till användare i en lokal miljö utan anslutning till Microsoft 365 och/eller stöd för SharePoint-tillägg som krävs. Du Outlook till Exchange på Kontrollpanelen för att distribuera i en lokal miljö utan anslutning till Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Rekommenderad metod för Office tillägg

Om du vill distribuera tillägg genom att använda en fasad metod rekommenderar vi följande:
  
1. Distribuera tillägget till ett mindre antal personer i företaget och till medlemmar i IT-avdelningen. Om distributionen lyckas går du vidare till steg 2.
    
2. Distribuera tillägget till fler personer inom företaget. Utvärdera resultatet på nytt och fortsätt med fullständig distribution om det lyckas.
    
3. Distribuera den till alla användare.
    
Beroende målgruppens storlek kan du lägga till eller ta bort utrullningssteg.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuera Office tillägg med hjälp av administrationscentret

Innan du börjar kan du [gå till Avgöra om centraliserad distribution](centralized-deployment-of-add-ins.md)av tillägg fungerar för din organisation.
  
1. I administrationscentret går du **Inställningar** \> **tilläggssidan.** Om du inte ser **tilläggssidan går** du till sidan **Inställningar** tillägg för \>  \> **integrerade** appar.

2. Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa.**

    > [!NOTE]
    > Administrationscentret uppdateras för användning av integrerade appar. Integrerade appar visas bara för globala administratörer, medan den gamla upplevelsen för andra finns kvar. Om du inte ser stegen ovan kan du gå till avsnittet Centraliserad distribution genom att gå till avsnittet **Inställningar**  >  **integrerade appar.** Högst upp på **sidan Integrerade** appar väljer du **Tillägg.**

3. Välj ett alternativ och följ instruktionerna.
  
4. Om du valde alternativet att lägga till ett tillägg från Office Store väljer du tillägget. </br>

    Du kan visa tillgängliga tillägg efter kategorier: Förslag **till dig,** **Klassificering** eller **Namn**. Endast kostnadsfria tillägg är tillgängliga från Office Store. Betalda tillägg stöds inte för närvarande. När du har valt ett tillägg godkänner du villkoren för att fortsätta. <br/> 

    > [!NOTE]
    > Med Office Store distribueras uppdateringar och förbättringar automatiskt till användarna.

5. På nästa sida väljer du **Alla,** Specifika  **användare/grupper** eller Bara jag för att ange vem tillägget har distribuerats till. Använd sökrutan för att söka efter specifika användare eller grupper. <br/>

    > [!NOTE]
    > Mer information om andra tillstånd som gäller för ett tillägg finns [i Tilläggsstater](./manage-addins-in-the-admin-center.md).
  
6. Välj **Distribuera**.
  
7. En grön bock visas när tillägget har distribuerats. Följ anvisningarna på sidan för att testa tillägget.

    > [!NOTE]
    > Användarna kan behöva Office för att visa tilläggsikonen i menyfliksområdet. Outlook tillägg kan ta upp till 24 timmar innan de visas i appfliksområde.

8. Välj Nästa när du är **klar.** Om du bara har distribuerat till dig själv kan du välja Ändra vem som har åtkomst till tillägget **för** att distribuera till fler användare.

    Om du har distribuerat tillägget till andra medlemmar i organisationen följer du anvisningarna för att meddela distributionen av tillägget. <br/>
  
    Vi är bra att informera användare och grupper om att det distribuerade tillägget är tillgängligt. Du kan skicka ett e-postmeddelande som beskriver när och hur du använder tillägget. Inkludera eller länka till hjälpinnehåll eller vanliga frågor som kan hjälpa användare om de har problem med tillägget.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Att tänka på när du tilldelar ett tillägg till användare och grupper

Globala administratörer och Exchange kan tilldela ett tillägg till alla eller till vissa användare och grupper. Varje alternativ har sina konsekvenser:
  
- **Alla** Med det här alternativet tilldelas tillägget till alla användare i organisationen. Använd det här alternativet sparsamt och bara för tillägg som verkligen är till för hela organisationen.

- **Användare** Om du tilldelar ett tillägg till en enskild användare och sedan distribuerar tillägget till en ny användare måste du först lägga till den nya användaren.

- **Grupper** Om du tilldelar ett tillägg till en grupp tilldelas tillägget automatiskt till användare som läggs till i gruppen. När en användare tas bort från en grupp förlorar användaren åtkomsten till tillägget. I båda fallen krävs inga ytterligare åtgärder från administratören.

- **Bara jag** Om du bara tilldelar ett tillägg till dig själv, tilldelas tillägget bara till ditt konto, vilket är perfekt för att testa tillägget.

Rätt alternativ för din organisation beror på din konfiguration. Vi rekommenderar emellertid att tilldelningar genom att använda grupper. Som administratör kan det vara enklare att hantera tillägg genom att använda grupper och kontrollera medlemskapet i de grupperna i stället för att tilldela enskilda användare varje gång. I vissa situationer kanske du vill begränsa åtkomsten till en liten uppsättning användare genom att tilldela vissa användare genom att tilldela användare manuellt.
  
## <a name="more-about-office-add-ins-security"></a>Mer Office om tilläggssäkerhet

Office kombinerar en XML-manifestfil som innehåller vissa metadata om tillägget, men det viktigaste är att de pekar på ett webbprogram som innehåller all kod och logik. Tillägg kan ha olika funktioner. Tillägg kan till exempel:
  
- Visa data.

- Läsa en användares dokument för att tillhandahålla sammanhangsberoende tjänster.

- Läsa och skriva data till och från en användares dokument för att ge värde till användaren.

Mer information om typer och funktioner i Office-tillägg finns i [plattformsöversikten för Office-tillägg](/office/dev/add-ins/overview/office-add-ins), särskilt avsnittet "Beskrivning av ett Office-tillägg".
  
För att tillägget ska kunna interagera med användarens dokument måste det deklarera vilken behörighet som behövs i manifestet. En JavaScript API-behörighetsmodell för åtkomst i fem nivåer utgör grunden för sekretess och säkerhet för användare av tillägg för åtgärdsfönster. Majoriteten av tilläggen i Office Store är på nivån ReadWriteDocument med nästan alla tillägg som stöder minst ReadDocument-nivå. Mer information om behörighetsnivåer finns i [Begära behörigheter för API-användning i innehåll och tillägg för åtgärdsfönster.](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)
  
När du uppdaterar ett manifest är det vanligtvis ändringar av ikon och text för ett tillägg. Ibland kan tilläggskommandon ändras. Tilläggets behörigheter ändras dock inte. Webbprogrammet där all kod och logik för tillägget körs kan ändras när som helst, vilket är hur webbprogram fungerar.
  
Uppdateringar för tillägg sker enligt följande:
  
- **Verksamhets tillägg:** I detta fall, där en administratör uttryckligen har laddat upp ett manifest, kräver tillägget att administratören laddar upp ett nytt manifest för att ge stöd för metadataändringar. Nästa gång det Office relevanta program startar uppdateras tillägget. Webbprogrammet kan ändras när som helst.

    > [!NOTE]
    > Administratören behöver inte ta bort ett LOB-tillägg för att göra en uppdatering.   I avsnittet Tillägg kan administratörer helt enkelt klicka på LOB-tillägget och välja knappen Uppdatera **i** det nedre högra hörnet. Uppdateringen fungerar bara om versionen av det nya tillägget är större än den för befintliga tillägget.

- **Office Store-tillägg:** När en administratör har valt ett tillägg från Office Store och tillägget uppdateras i Office Store uppdateras tillägget senare i den centraliserade distributionen. Nästa gång det Office relevanta program startar uppdateras tillägget. Webbprogrammet kan ändras när som helst.
  
## <a name="related-content"></a>Relaterat innehåll

[Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md) (artikel)\
[Skapa ditt första tillägg i åtgärdsfönstret i Word](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (artikel\
[Minderåriga och att skaffa](minors-and-acquiring-addins-from-the-store.md) tillägg från store (artikeln)\ Använd [PowerShell-cmdlets](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) för centraliserad distribution för att hantera tillägg (artikel)\  
[Felsökning: Användaren ser inte tillägg](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artikel)