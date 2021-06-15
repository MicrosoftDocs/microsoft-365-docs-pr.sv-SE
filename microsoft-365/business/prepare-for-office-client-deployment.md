---
title: Förbereda Office-distribution genom Microsoft 365 för företag
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Lär dig hur du automatiskt installerar 32-bitars Office-program på Windows 10 och håller dem uppdaterade.
ms.openlocfilehash: 843be426d817da1173769b3b66dc4c054179f0fd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924236"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Förbereda Office-distribution genom Microsoft 365 för företag

Den här artikeln gäller för Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Förbereda för automatisk installation av Office-program på klientdatorer

Du kan använda Microsoft 365 Business Premium för att automatiskt installera 32-bitars Office-programmen på Windows 10-datorer och hålla dem aktuella med uppdateringar.
  
Automatisk installation fungerar bäst om slutanvändarens dator finns på Windows 10 Business och:
  
- Inte har befintliga Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access och OneDrive).
    
    eller
    
- har en befintlig Klicka-och-kör-version av Office installerad.
    
Du kan avgöra om du har Klicka-och-kör-versionen av Office genom att välja **Arkiv** \> **Konto** ( **Office-konto** i Outlook) i valfritt Office-program. Om du **ser Office uppdateringar** enligt följande bild har installationen utförts med Klicka-och-kör. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Vem fördelarna med att ha den här funktionen**
  
Användaren vars dator:
  
- **Har** en Windows 10 Business, en aktiv användarlicens för Microsoft 365 för företag, Windows 10 Creators Update och är ansluten till Azure Active Directory. 
    
- **Inte har** 64-bitars Office (till exempel Word, Excel, PowerPoint). Om 64-bitars Office-appar krävs är den här funktionen inte något bra alternativ eftersom det inte finns stöd för att starta en 64-bitars Klicka-och-kör-version av Office från administratörskonsolen för Microsoft 365 för företag. 
    
- **Har inga** fristående 2016-program installerade med Windows Installer (MSI) (till exempel Visio eller Project). Microsoft 365 för företag uppgraderas Office till Klicka-och-kör-versionen av Office 2016 och som inte fungerar med fristående MSI Office 2016 MSI-appar. 
    
I följande tabell visas vilka åtgärder som slutanvändare/administratörer kan behöva vidta, beroende på starttillståndet, för att få en lyckad 32-bitars Klicka-och-kör-version av Office-distribution från administratörskonsolen för Microsoft 365 för företag.<br/>


|Status vid start av Office-installationen|Åtgärd att vidta innan Microsoft 365 för företag Office installationen|Slutstatus|
|:-----|:-----|:-----|
|Ingen Office-programsvit installerad  <br/> |Ingen  <br/> |Office 32-bitars 2016 installeras med Klicka-och-kör  <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office (2016 eller tidigare) och inga fristående program  <br/> |Ingen  <br/> |Uppgraderad till den senaste 32-bitars Klicka-och-kör-versionen av Office 2016, enligt behov **\*** <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office och 32-bitars eller 64-bitars Klicka-och-kör-bitars fristående Office-program (till exempel Visio och Project)  <br/> |Ingen  <br/> |Fristående program påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016  <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office och eventuella 32-bitars eller 64-bitars (med undantag av 2016) fristående MSI Office-program  <br/> |Ingen  <br/> |Fristående program påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016  <br/> |
|Alla befintliga 64-bitars Klicka-och-kör-versioner av Office  <br/> |Avinstallera 64-bitars-Office-apparna om det går bra att ersätta dem med 32-bitars Office program  <br/> |Om 64-bitarsprogram tas bort installeras 32-bitars Klicka-och-kör-versionen av Office 2016  <br/> |
|En befintlig MSI-installation av Office 2016 med eller utan fristående program  <br/> |Avinstallera MSI-versionen av Office 2016.  <br/> |32-bitars Klicka-och-kör-version av Office 2016 installeras. Inga ändringar av fristående program  <br/> |
|En befintlig MSI-installation av Office 2013 (eller tidigare) och/eller fristående Office-program  <br/> |Ingen  <br/> |32-bitars Klicka-och-kör-versionen av Office 2016 kan installeras sida vid sida med befintlig MSI-installation av Office (och fristående program)  <br/> |
||||
   
 **( \* ) Obs!** Uppgraderar inte till 32-bitars Klicka-och-kör-versionen av Office 2016 på grund av ett känt fel. En korrigering pågår. 
  
