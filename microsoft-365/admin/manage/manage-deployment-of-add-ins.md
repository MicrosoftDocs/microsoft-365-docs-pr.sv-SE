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
description: Lär dig att distribuera tillägg till användare och grupper i organisationen med hjälp av Centraliserad distribution i administrationscentret.
ms.openlocfilehash: 2d3b90a75f38a2c1146c0b0e5470c80b0af2c63f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572279"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Distribuera tillägg i administrationscentret

Office-tillägg hjälper dig att anpassa dina dokument och effektivisera hur du får tillgång till information på webben [(se Börja använda Office tillägg](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Som administratör kan du distribuera Office för användarna i organisationen med hjälp av funktionen Centraliserad distribution i Microsoft 365 administrationscenter. Centraliserad distribution är det rekommenderade och mest funktionsrika sättet för de flesta administratörer att distribuera tillägg till användare och grupper inom en organisation.

Mer information om hur du tar reda på om din organisation kan stödja centraliserad distribution finns i Ta reda [på om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).

Mer information om hur du hanterar tillägg efter distribution finns [i Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  För Word använder Excel och PowerPoint en [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) App Catalog för att distribuera tillägg till användare i en lokal miljö utan anslutning till Microsoft 365 och/eller stöd för SharePoint-tillägg som krävs. För Outlook du Exchange en kontrollpanel för att distribuera i en lokal miljö utan anslutning till Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Rekommenderad metod för Office tillägg

Om du vill distribuera tillägg med hjälp av en stegvis metod rekommenderar vi följande:
  
1. Rulla ut tillägget till en liten uppsättning affärsintressenter och medlemmar av IT-avdelningen. Om distributionen lyckas går du till steg 2.
    
2. Rulla ut tillägget till fler personer inom verksamheten. Utvärdera resultaten igen och fortsätt med fullständig distribution om det lyckas.
    
3. Utför en fullständig distribution till alla användare.
    
Beroende på målgruppens storlek kan du lägga till eller ta bort utrullningssteg.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuera Office ett tillägg med administrationscentret

Innan du börjar bör [du se Ta reda på om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).
  
1. Gå till sidan Inställningar  tillägg i \> **administrationscentret.** Om sidan Lägg till inte **visas går du** till sidan **Inställningar** \> **integrerade** \>  appar.

2. Välj **Distribuera tillägg** högst upp på sidan och välj sedan **Nästa**.

    > [!NOTE]
    > Administrationscentret uppdateras till distributionsupplevelsen med integrerade appar. Integrerade appar är bara synliga för globala administratörer, medan den gamla upplevelsen fortfarande finns för andra. Om du inte ser stegen ovan går du till avsnittet Centraliserad distribution genom att gå till **Inställningar**  >  **integrerade appar**. Välj Tillägg högst **upp på** sidan Integrerade **appar**.

3. Välj ett alternativ och följ instruktionerna.
  
4. Om du har valt alternativet att lägga till ett tillägg från Office Store gör du ditt tilläggsval. </br>

    Du kan visa tillgängliga tillägg efter kategorier: **Föreslås för dig**, **Betyg** eller **Namn**. Endast kostnadsfria tillägg är tillgängliga från Office Store. Betalda tillägg stöds inte för närvarande. När du har valt ett tillägg accepterar du villkoren för att fortsätta. <br/> 

    > [!NOTE]
    > Med Office Store distribueras uppdateringar och förbättringar automatiskt till användare.

5. På nästa sida väljer du **Alla**, **Specifika användare/grupper** eller **Bara jag** för att ange vem tillägget ska distribueras till. Använd sökrutan för att hitta specifika användare eller grupper. <br/>

    > [!NOTE]
    > Mer information om andra tillstånd som gäller för ett tillägg finns [i Tilläggs tillstånd](./manage-addins-in-the-admin-center.md).
  
6. Välj **Distribuera**.
  
7. En grön bock visas när tillägget distribueras. Följ anvisningarna på sidan för att testa tillägget.

    > [!NOTE]
    > Användare kan behöva starta om Office för att visa tilläggsikonen i menyfliksområdet i appen. Outlook kan ta upp till 24 timmar att visas i appflikyfliksområdet.

8. När du är klar väljer du **Nästa**. Om du har distribuerat till bara dig själv kan du välja **Ändra vem som har åtkomst till tillägget för** att distribuera till fler användare.

    Om du har distribuerat tillägget till andra medlemmar i organisationen följer du anvisningarna för att meddela distributionen av tillägget. <br/>
  
    Det är bra att informera användare och grupper om att det distribuerade tillägget är tillgängligt. Överväg att skicka ett e-postmeddelande som beskriver när och hur du använder tillägget. Inkludera eller länka till hjälpinnehåll eller vanliga frågor som kan hjälpa användare om de har problem med tillägget.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Överväganden när du tilldelar ett tillägg till användare och grupper

Globala administratörer och Exchange administratörer kan tilldela ett tillägg till alla eller till specifika användare och grupper. Varje alternativ har konsekvenser:
  
- **Alla** Det här alternativet tilldelar tillägget till varje användare i organisationen. Använd det här alternativet sparsamt och endast för tillägg som verkligen är universella för din organisation.

- **Användare** Om du tilldelar ett tillägg till en enskild användare och sedan distribuerar tillägget till en ny användare måste du först lägga till den nya användaren.

- **Grupper** Om du tilldelar ett tillägg till en grupp tilldelas användare som läggs till i gruppen automatiskt tillägget. När en användare tas bort från en grupp förlorar användaren åtkomsten till tillägget. I båda fallen krävs ingen ytterligare åtgärd från administratören.

- **Bara jag.** Om du tilldelar ett tillägg till bara dig själv tilldelas tillägget endast ditt konto, vilket är idealiskt för att testa tillägget.

Rätt alternativ för din organisation beror på din konfiguration. Vi rekommenderar dock att du gör tilldelningar med hjälp av grupper. Som administratör kan det vara enklare att hantera tillägg genom att använda grupper och styra medlemskapet i dessa grupper i stället för att tilldela enskilda användare varje gång. I vissa situationer kanske du vill begränsa åtkomsten till en liten uppsättning användare genom att göra tilldelningar till specifika användare genom att tilldela användare manuellt.
  
## <a name="more-about-office-add-ins-security"></a>Mer Office säkerhet för tillägg

Office-tillägg kombinerar en XML-manifestfil som innehåller vissa metadata om tillägget, men viktigast av allt pekar på ett webbprogram som innehåller all kod och logik. Tillägg kan variera i sina funktioner. Tillägg kan till exempel:
  
- Visa data.

- Läs en användares dokument för att tillhandahålla kontextuella tjänster.

- Läsa och skriv data till och från en användares dokument för att ge värdet till den användaren.

Mer information om typer och funktioner för Office-tillägg [finns i översikten över Office Tilläggsplattform](/office/dev/add-ins/overview/office-add-ins), särskilt avsnittet "Anatomi för ett Office-tillägg".
  
För att interagera med användarens dokument måste tillägget deklarera vilken behörighet det behöver i manifestet. En javascript-API-åtkomstbehörighetsmodell på fem nivåer utgör grunden för sekretess och säkerhet för användare av tillägg i åtgärdsfönstret. Majoriteten av tilläggen i Office Store är nivå ReadWriteDocument med nästan alla tillägg som stöder åtminstone ReadDocument-nivån. Mer information om behörighetsnivåer finns i Begära [behörigheter för API-användning i innehålls- och åtgärdsfönstertillägg](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
När du uppdaterar ett manifest är de typiska ändringarna i ett tilläggsikon och text. Ibland ändras tilläggskommandon. Behörigheterna för tillägget ändras dock inte. Webbprogrammet där all kod och logik för tillägget körs kan ändras när som helst, vilket är webbapplikationens natur.
  
Uppdateringar för tillägg sker på följande sätt:
  
- **Tillägg för affärsområde:** I det här fallet, när en administratör uttryckligen laddade upp ett manifest, kräver tillägget att administratören laddar upp en ny manifestfil för att stödja metadataändringar. Nästa gång den relevanta Office program startar uppdateras tillägget. Webbprogrammet kan ändras när som helst.

    > [!NOTE]
    > Administratören behöver inte ta bort ett LOB-tillägg för att göra en uppdatering.   I avsnittet Tillägg kan admin helt enkelt klicka på LOB-tillägget och välja **uppdateringsknappen i** det nedre högra hörnet. Uppdateringen fungerar bara om versionen av det nya tillägget är större än det befintliga tillägget.

- **Office Store-tillägg:** När en administratör valde ett tillägg från Office Store uppdateras tillägget senare i Centraliserad distribution om ett tillägg uppdateras i Office Store. Nästa gång den relevanta Office program startar uppdateras tillägget. Webbprogrammet kan ändras när som helst.
  
## <a name="related-content"></a>Relaterat innehåll

[Hantera tillägg i administrationscentret (artikel)](manage-addins-in-the-admin-center.md)

[Skapa det första word-åtgärdsfönstret (artikel)](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)

[Minderåriga och förvärv av tillägg från butiken (artikel)](minors-and-acquiring-addins-from-the-store.md)
  
[Använd PowerShell-cmdletar för centraliserad](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) distribution för att hantera tillägg (artikel)
  
[Felsökning: Användaren ser inte tillägg (artikel)](/office365/troubleshoot/access-management/user-not-seeing-add-ins)