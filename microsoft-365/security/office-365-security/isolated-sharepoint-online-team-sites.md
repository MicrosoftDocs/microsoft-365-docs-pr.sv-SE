---
title: Isolerade SharePoint Online-gruppwebbplatser
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 'Sammanfattning: Lär dig mer om hur du använder isolerade SharePoint Online-gruppwebbplatser.'
ms.openlocfilehash: 5750db2206211b6bb231ea01a12d7426a1d731a9
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807942"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Isolerade SharePoint Online-gruppwebbplatser

 **Sammanfattning:** Lär dig mer om hur du använder isolerade SharePoint Online-gruppwebbplatser.
  
SharePoint Online-gruppwebbplatser är ett enkelt sätt att snabbt skapa ett utrymme för samarbete med anteckningar, dokument, artiklar, kalender och andra resurser i Microsoft Office 365. SharePoint Online-gruppwebbplatser baseras på en Office 365-grupp och har en förenklad administrationsmodell som tillåter öppet samarbete med en privat uppsättning gruppmedlemmar eller med hela organisationen. Med en standardinställd SharePoint Online-gruppwebbplats kan medlemmar i Office 365-gruppen bjuda in andra användare och styra behörighetsinställningar.
  
Men i vissa fall kan du vilja skapa en SharePoint Online-gruppwebbplats för samarbete med strängare kontroll av behörigheterna för den webbplatsen genom gruppmedlemskap och SharePoint Online-behörighetsnivåer, som bara hanteras av SharePoint-administratörer. Vi kallar det här för en isolerad webbplats, som isoleras till den uppsättning användare som samarbetar, visar dess innehåll eller administrerar webbplatsen. Du kan behöva en isolerad webbplats av följande anledningar:
  
- Ett hemligt projekt i organisationen.
    
- Placeringen av mycket känslig eller värdefull immateriell egendom för organisationen.
    
- Resurserna för en rättsåtgärd som vidtas av organisationen eller som den utsätts för.
    
- För att dela en Office 365-prenumeration mellan flera organisationer som har en viss överlappning men som till största del fungerar som separata affärsenheter.
    
Här är kraven för en isolerad webbplats:
  
- Bara SharePoint Online-administratörer kan utföra webbplatsadministration, vilket omfattar gruppmedlemskap för åtkomst till webbplatsen och konfigurering av anpassade behörigheter.
    
- Webbplatsens medlemmar kan inte bjuda in andra medlemmar till gruppwebbplatsen.
    
- Användare som inte är medlem i den isolerade webbplatsen kan inte begära åtkomst till webbplatsen. För dem visas en åtkomst nekas-webbsida när de försöker öppna en webbadress kopplad till webbplatsen.
    
Kompromissen med att kräva centraliserad åtkomstkontroll och anpassade behörigheter av SharePoint Online-administratören är att webbplatsen förblir isolerad med tiden. Till exempel kan inte nuvarande medlemmar inte avsiktligt eller oavsiktligt, bjuda in eller konfigurera anpassade behörigheter för andra användare i Office 365-prenumerationer som inte ska vara medlemmar i webbplatsen.
  
En isolerad webbplats kan användas med andra funktioner, till exempel:
  
- IRM (Information Rights Management) för att se till att resurserna på webbplatsen förblir krypterade, även om de laddas ned lokalt och laddas upp på en annan webbplats som tillgänglig för hela organisationen.
    
- Skydd mot dataförlust för att förhindra att användare skickar webbplatsens resurser, till exempel filer, i e-post.
    
## <a name="next-steps"></a>Nästa steg

Om du vill prova en isolerad SharePoint Online-gruppwebbplats i en utvärderingsprenumeration läser du de stegvisa anvisningarna i [Miljö för utveckling/testning för isolerad SharePoint Online-gruppwebbplats](isolated-sharepoint-online-team-site-dev-test-environment.md).
  
När du är redo att distribuera en isolerad SharePoint Online-gruppwebbplats i produktion kan du läsa de steg för steg-informationen om utformning i [Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Se även

[Utforma en isolerad SharePoint Online-gruppwebbplats](design-an-isolated-sharepoint-online-team-site.md)
  
[Hantera en isolerad SharePoint Online-gruppwebbplats](manage-an-isolated-sharepoint-online-team-site.md)

[Distribuera en isolerad SharePoint Online-gruppwebbplats](deploy-an-isolated-sharepoint-online-team-site.md)


