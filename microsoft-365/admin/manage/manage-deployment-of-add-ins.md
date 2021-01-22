---
title: Distribuera tillägg i administrationscentret
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.openlocfilehash: ef7237f20780cb67bc84561ad8617dd8da6f8b82
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926360"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Distribuera tillägg i administrationscentret

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Office-tillägg hjälper dig att anpassa dina dokument och förenkla åtkomsten till information på webben (se Komma igång med [ditt Office-tillägg).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) Som administratör kan du distribuera Office-tillägg för användarna i organisationen med hjälp av funktionen för centraliserad distribution i administrationscentret för Microsoft 365. Centraliserad distribution är den rekommenderade och mest funktionsrika sättet för de flesta administratörer att distribuera tillägg till användare och grupper inom en organisation. 

Mer information om hur du fastställer om organisationen har stöd för centraliserad distribution finns i Avgöra om centraliserad distribution av tillägg [fungerar för din organisation.](centralized-deployment-of-add-ins.md)

Mer information om hur du hanterar tillägg efter distributionen finns [i Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  För Word, Excel och PowerPoint används en [SharePoint-programkatalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) för att distribuera tillägg till användare i en lokal miljö utan anslutning till Microsoft 365 och/eller stöd för SharePoint-tillägg. För Outlook använder du Exchange-kontrollpanelen för att distribuera i en lokal miljö utan anslutning till Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Rekommenderad metod för distribution av Office-tillägg

Om du vill distribuera tillägg med en fasad metod rekommenderar vi följande:
  
1. Distribuera tillägget till ett mindre antal personer i företaget och till medlemmar i IT-avdelningen. Om distributionen lyckas går du vidare till steg 2.
    
2. Distribuera tillägget till fler personer inom företaget. Utvärdera resultatet på nytt och fortsätt med fullständig distribution om det lyckas.
    
3. Utför en fullständig utrullning för alla användare.
    
Beroende på målgruppens storlek kan du lägga till eller ta bort steg för utrullning.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuera ett Office-tillägg med hjälp av administrationscentret

Innan du börjar kan du [kontrollera om centraliserad distribution av tillägg fungerar för din organisation.](centralized-deployment-of-add-ins.md)
  
1. Gå till sidan  \> **Inställningar-tillägg i administrationscentret.** Om du inte ser **tilläggssidan går** du  till sidan Inställningar \> **för** integrerade \> **appar.**
    
2. Välj **Distribuera tillägg högst** upp på sidan och välj sedan **Nästa.**
 
    > [!NOTE]
    > Administrationscentret uppdateras för användning av integrerade appar. Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till  >  **Inställningar-integrerade appar.** Välj Tillägg högst **upp på** sidan Integrerade **appar.**
    
3. Välj ett alternativ och följ instruktionerna.
  
4. Om du valde alternativet att lägga till ett tillägg från Office Store gör du ditt tilläggsalternativ. </br>

    Du kan visa tillgängliga tillägg efter kategorier: Förslag **till dig,** **Klassificering** eller **Namn.** Endast kostnadsfria tillägg är tillgängliga från Office Store. Betalda tillägg stöds inte för närvarande. När du har valt ett tillägg accepterar du villkoren för att fortsätta. <br/> 

    > [!NOTE] 
    > Med alternativet Office Store distribueras uppdateringar och förbättringar automatiskt till användarna.

5. På nästa sida väljer du **Alla,** Specifika  **användare/grupper** eller Bara jag för att ange vem tillägget ska distribueras till. Använd sökrutan för att söka efter specifika användare eller grupper. <br/>

    > [!NOTE] 
    > Mer information om andra tillstånd som gäller för ett tillägg finns i [tilläggsstater.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)
  
6. Välj **Distribuera.**
  
7. Ett grönt skalstreck visas när tillägget har distribuerats. Följ anvisningarna på sidan för att testa tillägget.

    > [!NOTE]
    > Användare kan behöva köra om Office för att visa tilläggsikonen i menyfliksområdet för appen. Det kan ta upp till 24 timmar innan Outlook-tillägg visas i appfliksområde.
    
8. Välj Nästa när du är **klar.** Om du bara har distribuerat till dig själv kan du välja Ändra vem som har åtkomst till tillägget **för** distribution till fler användare.

    Om du har distribuerat tillägget till andra medlemmar i organisationen följer du anvisningarna för att meddela distributionen av tillägget. <br/>
  
    Vi är bra att informera användare och grupper om att det distribuerade tillägget är tillgängligt. Du kan skicka ett e-postmeddelande som beskriver när och hur du använder tillägget. Ta med eller länka till hjälpinnehåll eller vanliga frågor som kan hjälpa användare om de har problem med tillägget.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Att tänka på när du tilldelar ett tillägg till användare och grupper

Administratörer kan tilldela ett tillägg till alla eller till vissa användare och grupper. Varje alternativ har sina konsekvenser:
  
- **Alla** Med det här alternativet tilldelas tillägget till alla användare i organisationen. Använd det här alternativet sparsamt och bara för tillägg som verkligen är till för hela organisationen. 
    
- **Användare** Om du tilldelar ett tillägg till en enskild användare och sedan distribuerar tillägget till en ny användare måste du först lägga till den nya användaren.
    
- **Grupper** Om du tilldelar ett tillägg till en grupp tilldelas tillägget automatiskt till användare som läggs till i gruppen. När en användare tas bort från en grupp förlorar användaren åtkomsten till tillägget. I båda fallen krävs inga ytterligare åtgärder från administratören. 

- **Bara jag** Om du tilldelar ett tillägg till bara dig själv tilldelas tillägget bara till ditt konto, vilket är perfekt för att testa tillägget.
    
Rätt alternativ för din organisation beror på din konfiguration. Vi rekommenderar emellertid att tilldelningar görs med hjälp av grupper. Som administratör kan det vara enklare att hantera tillägg genom att använda grupper och kontrollera medlemskapet i de grupperna i stället för att tilldela enskilda användare varje gång. I vissa situationer kan du vilja begränsa åtkomsten till en liten uppsättning användare genom att tilldela tilldelningar till specifika användare genom att tilldela användare manuellt.
  
## <a name="more-about-office-add-ins-security"></a>Mer om säkerhet för Office-tillägg

Office-tillägg kombinerar en XML-manifestfil som innehåller vissa metadata om tillägget, men det viktigaste är att de pekar på ett webbprogram som innehåller all kod och logik. Tillägg kan ha olika funktioner. Tillägg kan till exempel:
  
- Visa data.
    
- Läsa en användares dokument för att tillhandahålla sammanhangsberoende tjänster.
    
- Läsa och skriva data till och från en användares dokument för att ge värde till användaren.
    
Mer information om typer och funktioner i Office-tillägg finns i plattformsöversikten för [Office-tillägg,](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)särskilt avsnittet "Beskrivning av ett Office-tillägg".
  
För att tillägget ska kunna interagera med användarens dokument måste det deklarera vilken behörighet som behövs i manifestet. En JavaScript API-åtkomstbehörighetsmodell med fem nivåer utgör grunden för sekretess och säkerhet för åtgärdsfönster tillägg. Majoriteten av tilläggen i Office Store är på nivån ReadWriteDocument med nästan alla tillägg som stöder minst ReadDocument-nivå. Mer information om behörighetsnivåer finns i [Begära behörigheter för API-användning i innehåll åtgärdsfönster tillägg.](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)
  
När du uppdaterar ett manifest är det vanligtvis ändringar av ikon och text för ett tillägg. Ibland kan tilläggskommandon ändras. Tilläggets behörigheter ändras däremot inte. Webbprogrammet där all kod och logik för tillägget körs kan ändras när som helst, vilket är natur hos webbprogram.
  
Uppdateringar för tillägg sker så här:
  
- **Verksamhets tillägg:** I det här fallet, där en administratör uttryckligen har laddat upp ett manifest, kräver tillägget att administratören laddar upp ett nytt manifest för att ge stöd för metadataändringar. Nästa gång Office-programmen startar uppdateras tillägget. Webbprogrammet kan ändras när som helst. 

    > [!NOTE]
    > Administratören behöver inte ta bort ett LOB-tillägg för att göra en uppdatering.   I avsnittet Tillägg kan administratören helt enkelt klicka på tillägget LOB och välja uppdateringsknappen **i** det nedre högra hörnet. Uppdateringen fungerar bara om versionen av det nya tillägget är senare än det befintliga tillägget.   
    
- **Office Store-tillägg:** När en administratör har valt ett tillägg från Office Store uppdateras tillägget senare i centraliserad distribution om ett tillägg uppdateras i Office Store. Nästa gång Office-programmen startar uppdateras tillägget. Webbprogrammet kan ändras när som helst. 
  
## <a name="learn-more"></a>Mer information

[Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md)

[Skapa ditt första Word åtgärdsfönster-tillägg.](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)

[Minderåriga och skaffa tillägg från Store](minors-and-acquiring-addins-from-the-store.md)
  
[Använda PowerShell-cmdlets för centraliserad distribution för att hantera tillägg](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Felsökning: Användaren ser inte tillägg](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
