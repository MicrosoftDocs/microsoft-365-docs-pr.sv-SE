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
description: Lär dig hur du installerar 32-bitars Office-program automatiskt på Windows 10-datorer och håller dem uppdaterade.
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580063"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Förbereda Office-distribution genom Microsoft 365 för företag

Den här artikeln gäller Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Förbereda för automatisk installation av Office-program på klientdatorer

Du kan använda Microsoft 365 Business Premium för att automatiskt installera 32-bitars Office-program på Windows 10-datorer och hålla dem aktuella med uppdateringar.
  
Automatisk installation fungerar bäst om slutanvändarens dator finns på Windows 10 Business och:
  
- Inte har befintliga Office-skrivbordsprogram (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access och OneDrive).
    
    eller
    
- har en befintlig Klicka-och-kör-version av Office installerad.
    
Du kan avgöra om du har Klicka-och-kör-versionen av Office genom att välja **Arkiv** \> **Konto** ( **Office-konto** i Outlook) i valfritt Office-program. Om du ser **Office-uppdateringar** enligt följande bild har installationen utförts med Klicka-och-kör. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Vem drar nytta av den här funktionen?**
  
Användaren vars dator:
  
- **Har**  en användarlicens för Windows 10 Business, en aktiv Microsoft 365 för företag-licens, Windows 10 Creators Update och är ansluten till Azure Active Directory. 
    
- **Inte har** 64-bitars Office-program (exempel: Word, Excel och PowerPoint). Den här funktionen är inget bra alternativ om 64-bitarsversionen av Office-programmen är ett krav eftersom det inte finns något stöd för att starta en 64-bitars Klicka-och-kör-version av Office 2016 från administratörskonsolen för Microsoft 365 för företag. 
    
- **Har inga** fristående 2016-program installerade med Windows Installer (MSI) (till exempel Visio eller Project). Microsoft 365 för företag uppgraderar Office till Klicka-och-kör-versionen av Office 2016 och det fungerar inte med fristående Office 2016 MSI-program. 
    
I följande tabell visas vilka åtgärder som slutanvändare/administratörer kan behöva vidta, beroende på starttillståndet, för att få en lyckad 32-bitars Klicka-och-kör-version av Office-distribution från administratörskonsolen för Microsoft 365 för företag.
  
|**Status vid start av Office-installationen**|**Åtgärd att vidta innan Office-installationen av Microsoft 365 för företag**|**Slutstatus**|
|:-----|:-----|:-----|
|Ingen Office-programsvit installerad  <br/> |Ingen  <br/> |32-bitars office 2016 installeras med Klicka-och-kör  <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office (2016 eller tidigare) och inga fristående program  <br/> |Ingen  <br/> |Uppgraderad till den senaste 32-bitars Klicka-och-kör-versionen av Office 2016, enligt behov **\*** <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office och 32-bitars eller 64-bitars Klicka-och-kör-bitarsversionen av fristående Office-program (till exempel Visio och Project)  <br/> |Ingen  <br/> |Fristående program påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016  <br/> |
|Befintlig 32-bitars Klicka-och-kör-version av Office och eventuella 32-bitars eller 64-bitars (med undantag av 2016) fristående MSI Office-program  <br/> |Ingen  <br/> |Fristående program påverkas inte. Programsviten uppgraderas till 32-bitars Klicka-och-kör-versioner av Office 2016  <br/> ||||
|Alla befintliga 64-bitars Klicka-och-kör-versioner av Office  <br/> |Avinstallera 64-bitars Office-programmen om det går bra att ersätta dem med 32-bitars Office-program  <br/> |Om 64-bitarsprogram tas bort installeras 32-bitars Klicka-och-kör-versionen av Office 2016  <br/> |
|En befintlig MSI-installation av Office 2016 med eller utan fristående program  <br/> |Avinstallera MSI-versionen av Office 2016.  <br/> |32-bitars Klicka-och-kör-version av Office 2016 installeras. Inga ändringar av fristående program  <br/> |
|En befintlig MSI-installation av Office 2013 (eller tidigare) och/eller fristående Office-program  <br/> |Ingen  <br/> |32-bitars Klicka-och-kör-versionen av Office 2016 kan installeras sida vid sida med befintlig MSI-installation av Office (och fristående program)  <br/> |
||||
   
 **( \* ) Obs!** Uppgraderar inte till 32-bitars Klicka-och-kör-versionen av Office 2016 på grund av ett känt programfel. En korrigering pågår. 
  
