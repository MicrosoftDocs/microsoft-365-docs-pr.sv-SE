---
title: Förbereda för Office-klientdistribution av Microsoft 365 för företag
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Lär dig hur du installerar 32-bitars Office-appar automatiskt på Windows 10-datorer och håller dem uppdaterade.
ms.openlocfilehash: 2de492914edbde2afe593aac290c4a634b801443
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470956"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Förbereda för Office-klientdistribution av Microsoft 365 för företag

Den här artikeln gäller Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Förbereda för automatisk installation av Office-program på klientdatorer

Du kan använda Microsoft 365 Business Premium för att automatiskt installera 32-bitars Office-appar på Windows 10-datorer och hålla dem aktuella med uppdateringar.
  
Automatisk installation fungerar bäst om slutanvändarens dator finns på Windows 10 Business och:
  
- Inte har befintliga Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access och OneDrive).
    
    eller
    
- har en befintlig Klicka-och-kör-version av Office installerad.
    
Du kan avgöra om du har Klicka-och-kör-versionen av Office genom att välja **Arkiv** \> **Konto** ( **Office-konto** i Outlook) i valfritt Office-program. Om **Office-uppdateringar** visas i följande bild gjordes installationen med Klicka-och-kör.If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Vem drar nytta av att ha den här funktionen**
  
Användaren vars dator:
  
- **Har** en Windows 10 Business-användarlicens, en aktiv Microsoft 365 för företag-licens, Windows 10 Creators Update och ansluts till Azure Active Directory. 
    
- **Har inte** 64-bitars Office-program (t.ex. Om 64-bitars Office-appar krävs passar den här funktionen inte bra eftersom det inte finns något stöd för att utlösa en 64-bitars 2016 Click-to-Run-version av Office från administratörskonsolen Microsoft 365 för företag. 
    
- **Har inga** fristående 2016-program installerade med Windows Installer (MSI) (till exempel Visio eller Project). Microsoft 365 för företag uppgraderar Office till Click-to-Run-versionen av Office 2016 och det fungerar inte med fristående OFFICE 2016-appar. 
    
I följande tabell visas vilken åtgärd slutanvändarna/administratörerna kan behöva vidta, beroende på deras starttillstånd, för att ha en lyckad 32-bitars Click-to-Run-version av Office-distribution från microsoft 365 för företag-administratörskonsolen.
  
|**Status vid start av Office-installationen**|**Åtgärder som ska vidtas innan Microsoft 365 för företag Office installeras**|**Slutstatus**|
|:-----|:-----|:-----|
|Ingen Office-programsvit installerad  <br/> |Inga  <br/> |Office 2016 32-bitars installeras med Klicka-och-kör  <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office (2016 eller tidigare) och inga fristående program  <br/> |Inga  <br/> |Uppgraderad till den senaste 32-bitars Klicka-och-kör-versionen av Office 2016, enligt behov **\*** <br/> |
|Befintlig Klicka-och-kör 32-bitarsversion av Office och Klicka-och-kör 32-bitars eller 64-bitars fristående Office-appar (till exempel Visio, Project)  <br/> |Inga  <br/> |Fristående appar påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016  <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office och eventuella 32-bitars eller 64-bitars (med undantag av 2016) fristående MSI Office-program  <br/> |Inga  <br/> |Fristående appar påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016  <br/> ||||
|Alla befintliga 64-bitars Klicka-och-kör-versioner av Office  <br/> |Avinstallera 64-bitars Office-programmen om det är OK att ersätta dem med 32-bitars Office-program  <br/> |Om 64-bitarsprogram tas bort installeras 32-bitars Klicka-och-kör-versionen av Office 2016  <br/> |
|En befintlig MSI-installation av Office 2016 med eller utan fristående program  <br/> |Avinstallera MSI-versionen av Office 2016.  <br/> |32-bitars Klicka-och-kör-version av Office 2016 installeras. Inga ändringar av fristående program  <br/> |
|En befintlig MSI-installation av Office 2013 (eller tidigare) och/eller fristående Office-program  <br/> |Ingen  <br/> |32-bitars Klicka-och-kör-versionen av Office 2016 kan installeras sida vid sida med befintlig MSI-installation av Office (och fristående program)  <br/> |
||||
   
 **( \* ) Obs:** Uppgraderar inte till Click-to-Run 32-bitars version av Office 2016 på grund av ett känt fel. En lösning pågår. 
  
