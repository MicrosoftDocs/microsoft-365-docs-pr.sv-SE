---
title: Förbereda Office-distribution genom Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Lär dig hur du automatiskt installera 32-bitars Office apps på Windows 10 datorer och hålla dem uppdaterade.
ms.openlocfilehash: 20269c493b0e3b5a7deb56a24a5e1a9583ef9d0a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074659"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>Förbereda Office-distribution genom Microsoft 365 Business

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Förbereda för automatisk installation av Office-program på klientdatorer

Du kan använda Microsoft 365 Business för att automatiskt installera 32-bitars Office-program på datorer med Windows 10 och för att automatiskt uppdatera dem till de senaste versionerna.
  
Det här fungerar bäst om användarens dator kör Windows 10 Business och:
  
- Inte har befintliga Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access och OneDrive).
    
    eller
    
- har en befintlig Klicka-och-kör-version av Office installerad.
    
Du kan avgöra om du har Klicka-och-kör-versionen av Office genom att välja **Arkiv** \> **Konto** ( **Office-konto** i Outlook) i valfritt Office-program. Om du ser Office-uppdateringar enligt följande bild utfördes installationen med Klicka-och-kör. 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Vem kan dra fördel av den här funktionen**
  
Användaren vars dator:
  
- **har** en användarlicens för Windows 10 Business, en aktiv Microsoft 365 Business-licens och Windows 10 Creators Update samt är ansluten till Azure Active Directory. 
    
- **inte har** 64-bitars Office-program (exempel: Word, Excel och Powerpoint). Den här funktionen är inget bra alternativ om 64-bitarsversionen av Office-programmen är ett krav eftersom funktionen saknar stöd för att starta en 64-bitars Klicka-och-kör-version av Office 2016 från Microsoft 365 Business-administratörskonsolen. 
    
- **Har inga** fristående 2016-program installerade med Windows Installer (MSI) (till exempel Visio eller Project). Microsoft 365 Business uppgraderar Office till Klicka-och-kör-versionen av Office 2016 och det fungerar inte med Office 2016 MSI fristående program. 
    
Följande tabell visar, beroende på startstatus, de åtgärder som användaren eller administratören behöver vidta för en lyckad distribution av 32-bitars Klicka-och-kör-version av Office från Microsoft 365 Business-administratörskonsolen.
  
|**Status vid start av Office-installationen**|**Åtgärd att vidta före Microsoft 365 Business Office-installationen**|**Slutstatus**|
|:-----|:-----|:-----|
|Ingen Office-programsvit installerad  <br/> |Ingen  <br/> |32-bitarsversionen av Office 2016 installeras med Klicka-och-kör  <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office (2016 eller tidigare) och inga fristående program  <br/> |Ingen  <br/> |Uppgraderad till den senaste 32-bitars Klicka-och-kör-versionen av Office 2016, enligt behov **\*** <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office och 32-bitars eller 64-bitars Klicka-och-kör-versioner av fristående Office-program (till exempel Visio och Project)  <br/> |Ingen  <br/> |Fristående program påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016  <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office och eventuella 32-bitars eller 64-bitars (med undantag av 2016) fristående MSI Office-program  <br/> |Ingen  <br/> |Fristående program påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016  <br/> ||||
|Alla befintliga 64-bitars Klicka-och-kör-versioner av Office  <br/> |Avinstallera 64-bitars Office-program om det går bra att ersätta dem med 32-bitars Office-program  <br/> |Om 64-bitarsprogram tas bort installeras 32-bitars Klicka-och-kör-versionen av Office 2016  <br/> |
|En befintlig MSI-installation av Office 2016 med eller utan fristående program  <br/> |Avinstallera MSI-versionen av Office 2016.  <br/> |32-bitars Klicka-och-kör-version av Office 2016 installeras. Inga ändringar av fristående program  <br/> |
|En befintlig MSI-installation av Office 2013 (eller tidigare) och/eller fristående Office-program  <br/> |Ingen  <br/> |32-bitars Klicka-och-kör-versionen av Office 2016 kan installeras sida vid sida med befintlig MSI-installation av Office (och fristående program)  <br/> |
||||
   
 **(\*) Obs!** Uppgraderar inte till 32-bitars Klicka-och-kör-versionen av Office 2016 på grund av ett känt programfel. En programkorrigering är under utveckling. 
  


