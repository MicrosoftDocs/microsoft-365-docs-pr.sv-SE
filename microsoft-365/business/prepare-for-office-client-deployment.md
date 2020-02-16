---
title: Förbereda Office-distribution genom Microsoft 365 Business
f1.keywords:
- CSH
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Läs om hur du installerar 32-bitars Office-programmen på Windows 10-datorer automatiskt och håller dem uppdaterade.
ms.openlocfilehash: 0f8cd7df49ad627b190fad6737ec95a6d64d99d0
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065124"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>Förbereda Office-distribution genom Microsoft 365 Business

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Förbereda för automatisk installation av Office-program på klientdatorer

Du kan använda Microsoft 365 Business för att automatiskt installera 32-bitars Office-apparna på Windows 10-datorer och hålla dem aktuella med uppdateringar.
  
Automatisk installation fungerar bäst om slutanvändarens dator finns på Windows 10 Business och:
  
- Inte har befintliga Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access och OneDrive).
    
    eller
    
- har en befintlig Klicka-och-kör-version av Office installerad.
    
Du kan avgöra om du har Klicka-och-kör-versionen av Office genom att välja **Arkiv** \> **Konto** ( **Office-konto** i Outlook) i valfritt Office-program. Om du ser **Office-uppdateringar** som visas i följande bild gjordes installationen med Klicka-och-kör. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Vem tjänar på att ha den här funktionen**
  
Användaren vars dator:
  
- **har** en användarlicens för Windows 10 Business, en aktiv Microsoft 365 Business-licens och Windows 10 Creators Update samt är ansluten till Azure Active Directory. 
    
- **Har inte** 64-bitars Office-appar (exempel: Word, Excel, PowerPoint). Om 64-bitars Office-appar krävs är den här funktionen inte en bra passform eftersom det inte finns något stöd för att utlösa en 64-bitars 2016 Click-to-Run-version av Office från administrationskonsolen för Microsoft 365 Business. 
    
- **Har inga** fristående 2016-program installerade med Windows Installer (MSI) (till exempel Visio eller Project). Microsoft 365 Business uppgraderar Office till Click-to-Run-versionen av Office 2016 och som inte fungerar med fristående Office 2016-appar. 
    
I följande tabell visas vilken åtgärd slutanvändarna/administratörerna kan behöva vidta, beroende på deras starttillstånd, för att få en lyckad 32-bitars Klick-till-kör-version av Office-distributionfrån administrationskonsolen för Microsoft 365 Business.
  
|**Status vid start av Office-installationen**|**Åtgärd att vidta före Microsoft 365 Business Office-installationen**|**Slutstatus**|
|:-----|:-----|:-----|
|Ingen Office-programsvit installerad  <br/> |Ingen  <br/> |Office 2016 32-bitars installeras med Click-to-Run  <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office (2016 eller tidigare) och inga fristående program  <br/> |Ingen  <br/> |Uppgraderad till den senaste 32-bitars Klicka-och-kör-versionen av Office 2016, enligt behov **\*** <br/> |
|Befintlig 32-bitarsversion av Office och Klicka på-kör 32-bitars eller 64-bitars fristående Office-appar (till exempel Visio, Project)  <br/> |Ingen  <br/> |Fristående appar påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016  <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office och eventuella 32-bitars eller 64-bitars (med undantag av 2016) fristående MSI Office-program  <br/> |Ingen  <br/> |Fristående appar påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016  <br/> ||||
|Alla befintliga 64-bitars Klicka-och-kör-versioner av Office  <br/> |Avinstallera 64-bitars Office-apparna om det är OK att ersätta dem med 32-bitars Office-appar  <br/> |Om 64-bitarsprogram tas bort installeras 32-bitars Klicka-och-kör-versionen av Office 2016  <br/> |
|En befintlig MSI-installation av Office 2016 med eller utan fristående program  <br/> |Avinstallera MSI-versionen av Office 2016.  <br/> |32-bitars Klicka-och-kör-version av Office 2016 installeras. Inga ändringar av fristående program  <br/> |
|En befintlig MSI-installation av Office 2013 (eller tidigare) och/eller fristående Office-program  <br/> |Ingen  <br/> |32-bitars Klicka-och-kör-versionen av Office 2016 kan installeras sida vid sida med befintlig MSI-installation av Office (och fristående program)  <br/> |
||||
   
 **(\*) Anmärkning:** Uppgraderar inte till Click-to-Run 32-bitarsversion av Office 2016 på grund av ett känt fel. En fix pågår. 
  
