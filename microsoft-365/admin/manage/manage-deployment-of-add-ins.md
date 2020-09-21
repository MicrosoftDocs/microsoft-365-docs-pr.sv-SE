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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Lär dig att distribuera tillägg till användare och grupper i organisationen med hjälp av centraliserad distribution i administrations centret.
ms.openlocfilehash: 5806b2a33446a8e273c2aaf78e082c6fd753bbe4
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171286"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Distribuera tillägg i administrationscentret

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Med hjälp av Office-tillägg kan du anpassa dina dokument och förenkla hur du kommer åt informationen på webben (se [börja använda Office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Som administratör kan du distribuera Office-tillägg för användarna i organisationen med hjälp av funktionen centraliserad distribution i administrations centret för Microsoft 365. Centraliserad distribution är det rekommenderade och mest omfattande sättet för de flesta administratörer att distribuera tillägg till användare och grupper inom en organisation. 

Mer information om hur du tar reda på om din organisation har stöd för centraliserad distribution finns i [avgöra om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).

Mer information om hur du hanterar tillägg efter distribution finns i [Hantera tillägg i administrations centret](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  I Excel och PowerPoint används en SharePoint- [programkatalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) för att distribuera tillägg till användare i en lokal miljö utan anslutning till Microsoft 365 och/eller stöd för SharePoint-tillägg som krävs. För Outlook använder du Exchange-Kontrollpanelen för att distribuera i en lokal miljö utan anslutning till Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Rekommenderad metod för att distribuera Office-tillägg

För att kunna distribuera tillägg med hjälp av en stegvis lösning rekommenderar vi följande:
  
1. Distribuera tillägget till en mindre uppsättning intressenter och medlemmar i IT-avdelningen. Om distributionen lyckades går du vidare till steg 2.
    
2. Distribuera tillägget till fler personer inom företaget. Utvärdera resultatet och fortsätt med fullständig distribution om det lyckades.
    
3. Utför fullständig installation för alla användare.
    
Beroende på mål gruppens storlek kan du lägga till eller ta bort distributions steg.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuera ett Office-tillägg med administrations Center

Innan du börjar läser du [kontrol lera om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).
  
1. Gå till sidan tillägg i administrations centret **Settings** \> **Add-ins** .
    
2. Välj **distribuera tillägg** högst upp på sidan och välj sedan **Nästa**.
 
    > [!NOTE]
    > Administrations centret uppdateras till distributions miljön med integrerade appar. Om du inte ser ovanstående steg går du till avsnittet centraliserad distribution genom att gå till **Inställningar**för  >  **integrerade appar**. **Välj tillägg**högst upp på sidan för **integrerade appar** .
    
3. Välj ett alternativ och följ instruktionerna.
  
4. Om du valde alternativet att lägga till ett tillägg från Office Store gör du tillägget. </br>

    Du kan visa tillgängliga tillägg efter kategorier: **föreslaget för dig**, **betyg**eller **namn**. Det finns bara kostnads fria tillägg från Office Store. Betalda tillägg stöds för närvarande inte. När du har valt ett tillägg accepterar du villkoren och villkoren för att fortsätta. <br/> 

    > [!NOTE] 
    > Med Office Store-alternativet uppdateras uppdateringar och förbättringar automatiskt till användarna.

5. På nästa sida väljer du **alla**, **specifika användare/grupper**eller **bara jag** för att ange vem tillägget distribueras till. Använd sökrutan för att hitta specifika användare eller grupper. <br/>

    > [!NOTE] 
    > Om du vill veta mer om andra tillstånd som gäller för ett tillägg läser du [i tillägget](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).
  
6. Välj **distribuera**.
  
7. En grön markering visas när tillägget distribueras. Följ instruktionerna på sidan för att testa tillägget.

    > [!NOTE]
    > Användare kan behöva starta om Office för att Visa tilläggs ikonen i menyfliksområdet app. Outlook-tillägg kan ta upp till 24 timmar att visas på menyfliksområdet i appen.
    
8. När du är klar väljer du **Nästa**. Om du har distribuerat dig själv kan du välja **ändra vem som har åtkomst till tillägget** för att distribueras till fler användare.

    Om du har distribuerat tillägget till andra medlemmar i organisationen följer du anvisningarna för att meddela distributionen av tillägget. <br/>
  
    Det är en bra idé att informera användare och grupper om att det distribuerade tillägget är tillgängligt. Överväg att skicka ett e-postmeddelande som beskriver när och hur du ska använda tillägget. Infoga eller länka till hjälp innehåll och vanliga frågor om problem med tillägget.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Att tänka på när du tilldelar ett tillägg till användare och grupper

Administratörer kan tilldela ett tillägg till alla eller till specifika användare och grupper. Varje alternativ har betydelse:
  
- **Alla** Det här alternativet tilldelar tillägget till alla användare i organisationen. Använd det här alternativet sparsamt och bara för tillägg som är universella för din organisation. 
    
- **Användare** Om du tilldelar ett tillägg till en enskild användare, och sedan distribuerar tillägget till en ny användare, måste du först lägga till den nya användaren.
    
- **Grupper** Om du tilldelar ett tillägg till en grupp, tilldelas användare som läggs till i gruppen automatiskt tillägget. När en användare tas bort från en grupp förlorar användaren åtkomst till tillägget. I båda fallen krävs ingen ytterligare åtgärd från administratören. 

- **Bara jag** Om du tilldelar ett tillägg till dig själv tilldelas tillägget bara till ditt konto, som är idealiskt för testning av tillägget.
    
Det bästa alternativet för din organisation beror på din konfiguration. Vi rekommenderar att du gör uppgifter med hjälp av grupper. Som administratör kan det vara enklare att hantera tillägg genom att använda grupper och kontrol lera medlemskap för dessa grupper i stället för att tilldela enskilda användare varje gång. I vissa situationer kanske du vill begränsa åtkomsten till en liten uppsättning användare genom att göra uppgifter till specifika användare genom att tilldela användare manuellt.
  
## <a name="more-about-office-add-ins-security"></a>Mer om säkerhet för Office-tillägg

Office-tillägg kombinerar en XML-manifest fil som innehåller vissa metadata om tillägget, men det viktigaste är att peka på ett webb program som innehåller all kod och logik. Tillägg kan variera efter deras kapacitet. Tillägg kan till exempel:
  
- Visa data.
    
- Läs en användares dokument för att tillhandahålla kontextuella tjänster.
    
- Läsa och skriva data till och från en användares dokument för att ange värde för den användaren.
    
Mer information om olika typer av Office-tillägg finns i avsnittet om hur du lägger till en översikt över Office- [tilläggsprogram](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)
  
Om du vill interagera med användarens dokument måste tillägget deklarera vilken behörighet som krävs i manifestet. En JavaScript-behörighets modell med fem nivåer är grunden för sekretess och säkerhet för användare av åtgärds fönstrets tillägg. De flesta tilläggen i Office Store är nivå ReadWriteDocument med nästan alla tillägg som stöder minst ReadDocument nivå. Mer information om behörighets nivåer finns i [begära behörigheter för API-användning i tillägg för innehåll och åtgärds fönster](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
När du uppdaterar ett manifest är de typiska ändringarna för ett tilläggs ikon och text. Ibland kommer kommandon för tillägg att ändras. Men behörigheterna för tillägget ändras inte. Webb programmet där all kod och logik för tillägget körs kan ändras när som helst, vilket är webb programs beskaffenhet.
  
Uppdateringar för tillägg sker på följande sätt:
  
- **Tillägg för affärs område:** I det här fallet när en administratör explicit har laddat upp ett manifest kräver tillägget att administratören laddar upp en ny manifest fil för att stödja metadata ändringar. Nästa gång Office-programmen startas uppdateras tillägget. Webb programmet kan ändras när som helst. 

    > [!NOTE]
    > Administratören behöver inte ta bort ett LOB-tillägg för att göra en uppdatering.   I avsnittet tillägg kan administratören helt enkelt klicka på LOB-tillägget och välja **knappen Uppdatera** i det nedre högra hörnet. Update fungerar bara om den version av det nya tillägget är större än det befintliga tillägget.   
    
- **Office Store-tillägg:** När en administratör valde ett tillägg från Office Store, om en tilläggs uppdatering i Office Store, uppdateras tillägget senare i centraliserad distribution. Nästa gång Office-programmen startas uppdateras tillägget. Webb programmet kan ändras när som helst. 
  
## <a name="learn-more"></a>Mer information

[Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md)

[Skapar Office-tillägg](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).

[Minderåriga och förvärvade tillägg från Store](minors-and-acquiring-addins-from-the-store.md)
  
[Använda PowerShell-cmdlets för centraliserad distribution för att hantera tillägg](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Fel sökning: användaren ser inte tillägg](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
