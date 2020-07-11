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
description: Lär dig att distribuera tillägg till användare och grupper i organisationen med hjälp av Centraliserad distribution i administrationscentret.
ms.openlocfilehash: 51db2bf7b618bddf2c6de417b7f5e53c91a64a1b
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102866"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Distribuera tillägg i administrationscentret

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Office-tillägg hjälper dig att anpassa dina dokument och effektivisera ditt sätt att komma åt information på webben (se [Börja använda office-tillägget](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Som administratör kan du distribuera Office-tillägg för användarna i organisationen med hjälp av funktionen Centraliserad distribution i administrationscentret för Microsoft 365. Centraliserad distribution är det rekommenderade och mest funktionsrika sättet för de flesta administratörer att distribuera tillägg till användare och grupper inom en organisation. 

Mer information om hur du tar reda på om din organisation kan stödja centraliserad distribution finns [i Avgöra om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).

Mer information om hur du hanterar tillägg efter distributionen finns [i Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  För Word, Excel och PowerPoint används en [SharePoint-appkatalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) för att distribuera tillägg till användare i en lokal miljö utan anslutning till Microsoft 365 och/eller stöd för SharePoint-tillägg som krävs. I Outlook används Exchange-kontrollpanelen för att distribuera i en lokal miljö utan anslutning till Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Rekommenderad metod för distribution av Office-tillägg

Om du vill distribuera tillägg med hjälp av en stegvis metod rekommenderar vi följande:
  
1. Rulla ut tillägget till en liten uppsättning affärsintressenter och medlemmar på IT-avdelningen. Om distributionen lyckas går du vidare till steg 2.
    
2. Rulla ut tillägget till fler individer inom verksamheten. Återigen utvärdera resultaten och, om det lyckas, fortsätta med fullständig distribution.
    
3. Utför en fullständig distribution för alla användare.
    
Beroende på målgruppens storlek kan du lägga till eller ta bort utrullningssteg.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuera ett Office-tillägg med administrationscentret

Innan du börjar läser du [Ta reda på om centraliserad distribution av tillägg fungerar för din organisation](centralized-deployment-of-add-ins.md).
  
1. Gå till sidan Inställningar **Settings** \> **i administrationscentret.**
    
2. Välj **Distribuera tillägg högst** upp på sidan och välj sedan **Nästa**.
    
3. Välj ett alternativ och följ instruktionerna.
  
4. Om du valde alternativet att lägga till ett tillägg från Office Store gör du ditt tilläggsval. </br>

    Du kan visa tillgängliga tillägg efter kategorier: **Förslag på för dig**, **Betyg**eller **Namn**. Endast kostnadsfria tillägg är tillgängliga i Office Store. Betalda tillägg stöds inte för närvarande. När du har valt ett tillägg godkänner du villkoren för att fortsätta. <br/> 

    > [!NOTE] 
    > Med alternativet Office Store uppdateras och förbättringar automatiskt för användarna.

5. På nästa sida väljer du **Alla**, **Specifika användare/grupper**eller **Bara jag** för att ange vem tillägget ska distribueras till. Använd sökrutan för att hitta specifika användare eller grupper. <br/>

    > [!NOTE] 
    > Mer information om andra tillstånd som gäller för ett tillägg finns [i Tilläggstillstånd](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).
  
6. Välj **Distribuera**.
  
7. En grön bock visas när tillägget distribueras. Följ instruktionerna på sidan för att testa tillägget.

    > [!NOTE]
    > Användare kan behöva starta om Office för att visa tilläggsikonen i menyfliksområdet för appen. Det kan ta upp till 24 timmar innan Outlook-tillägg visas i menyfliksområdet för appar.
    
8. När du är klar väljer du **Nästa**. Om du har distribuerat till bara dig själv kan du välja **Ändra vem som har åtkomst till tillägg** för att distribuera till fler användare.

    Om du har distribuerat tillägget till andra medlemmar i organisationen följer du instruktionerna för att meddela distributionen av tillägget. <br/>
  
    Det är bra att informera användare och grupper om att det distribuerade tillägget är tillgängligt. Överväg att skicka ett e-postmeddelande som beskriver när och hur du använder tillägget. Inkludera eller länka till Hjälpinnehåll eller vanliga frågor som kan hjälpa användarna om de har problem med tillägget.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Överväganden när du tilldelar ett tillägg till användare och grupper

Administratörer kan tilldela ett tillägg till alla eller till specifika användare och grupper. Varje alternativ har konsekvenser:
  
- **Alla** Det här alternativet tilldelar tillägget till alla användare i organisationen. Använd det här alternativet sparsamt och endast för tillägg som verkligen är universella för din organisation. 
    
- **Användare** Om du tilldelar ett tillägg till en enskild användare och sedan distribuerar tillägget till en ny användare måste du först lägga till den nya användaren.
    
- **Grupper** Om du tilldelar ett tillägg till en grupp tilldelas användare som läggs till i gruppen automatiskt tillägget. När en användare tas bort från en grupp förlorar användaren åtkomst till tillägget. I båda fallen krävs ingen ytterligare åtgärd från administratören. 

- **Bara jag** Om du tilldelar ett tillägg till bara dig själv tilldelas tillägget till endast ditt konto, vilket är idealiskt för att testa tillägget.
    
Det rätta alternativet för din organisation beror på din konfiguration. Vi rekommenderar dock att du gör tilldelningar med hjälp av grupper. Som administratör kan det vara enklare att hantera tillägg genom att använda grupper och styra medlemskapet i dessa grupper i stället för att tilldela enskilda användare varje gång. I vissa situationer kanske du vill begränsa åtkomsten till en liten uppsättning användare genom att göra tilldelningar till specifika användare genom att tilldela användare manuellt.
  
## <a name="more-about-office-add-ins-security"></a>Mer om office-tilläggssäkerhet

Office-tillägg kombinerar en XML-manifestfil som innehåller vissa metadata om tillägget, men viktigast av allt pekar på ett webbprogram som innehåller all kod och logik. Tillägg kan variera i sina funktioner. Tillägg kan till exempel:
  
- Visa data.
    
- Läs en användares dokument för att tillhandahålla kontextuella tjänster.
    
- Läs och skriv data till och från en användares dokument för att ge användaren värde.
    
Mer information om typerna och funktionerna i Office-tillägg finns i [plattformsöversikt för Office-tillägg,](https://go.microsoft.com/fwlink/p/?linkid=846362)särskilt avsnittet "Anatomi för ett Office-tillägg".
  
Om du vill interagera med användarens dokument måste tillägget deklarera vilken behörighet det behöver i manifestet. En javascript-api-åtkomstbehörighetsmodell på fem nivåer utgör grunden för sekretess och säkerhet för användare av tillägg i åtgärdsfönstret. Majoriteten av tilläggen i Office Store är lässkrivdokument på nivå med nästan alla tillägg som stöder åtminstone ReadDocument-nivån. Mer information om [behörighetsnivåerna finns i Begära behörigheter för API-användning i innehåll och tillägg till åtgärdsfönstret](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
När du uppdaterar ett manifest är de typiska ändringarna i ett tilläggs ikon och text. Ibland ändras tilläggskommandon. Men behörigheterna för tillägget ändras inte. Webbprogrammet där all kod och logik för tilläggskörningar kan ändras när som helst, vilket är webbprogrammens natur.
  
Uppdateringar för tillägg sker på följande sätt:
  
- **Tillägg för företagsrader:** I det här fallet, när en administratör uttryckligen laddade upp ett manifest, kräver tillägget att administratören överför en ny manifestfil för att stödja metadataändringar. Nästa gång de relevanta Office-programmen startar uppdateras tillägget. Webbprogrammet kan ändras när som helst. 

    > [!NOTE]
    > Administratören behöver inte ta bort ett LOB-tillägg för att göra en uppdatering.   I avsnittet Tillägg kan admin helt enkelt klicka på LOB-tillägget och välja **uppdateringsknappen** i det nedre högra hörnet. Uppdateringen fungerar bara om versionen av det nya tillägget är större än det befintliga tillägget.   
    
- **Office Store-tillägg:** När en administratör valde ett tillägg från Office Store, om ett tillägg uppdateras i Office Store, uppdateras tillägget senare i Centraliserad distribution. Nästa gång de relevanta Office-programmen startar uppdateras tillägget. Webbprogrammet kan ändras när som helst. 
  
## <a name="learn-more"></a>Mer information

Skapa och bygga [Office-tillägg](https://go.microsoft.com/fwlink/p/?linkid=846362)

[Hantera tillägg i administrationscentret](manage-addins-in-the-admin-center.md)

[Minderåriga och förvärva tillägg från butiken](minors-and-acquiring-addins-from-the-store.md)
  
[Använda centraliserade PowerShell-cmdlets för att hantera tillägg](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Felsöka: Användaren ser inte tillägg](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
