---
title: Konfigurera Övrig e-post för organisationen
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Lär dig att aktivera eller inaktivera övrig e-post för alla eller specifika användare i organisationen med Hjälp av Exchange PowerShell. '
ms.openlocfilehash: 65aa614095ecbebaad3d7eb38af1e74166ce20ac
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42808717"
---
# <a name="configure-clutter-for-your-organization"></a>Konfigurera Övrig e-post för organisationen

> [!TIP]
> [Prioriterad inkorg](../setup/configure-focused-inbox.md) kommer att ersätta Övrig e-post. Läs mer: [Uppdatera om fokuserad inkorg och våra planer för Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Som administratör kan du behöva hantera övrig övrig övrig e-post i Office 365. Om du vill aktivera/inaktivera funktionen Övrig e-post för användare i organisationen måste du använda Exchange PowerShell. (Enskilda användare kan aktivera/inaktivera med hjälp av de här anvisningarna: [Aktivera/inaktivera Övrig e-post i Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).) 
  
Läs artikeln [Använd PowerShell med Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) och [Ansluta till Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) för information om hur du använder Exchange PowerShell. Du måste ha ett konto som har minst rollen Exchange Service-administratör och möjligheten att ansluta till Exchange Online med PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Aktivera Övrig e-post med Exchange PowerShell

Du kan manuellt aktivera Övrig e-post för en postlåda genom att köra cmdleten [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Du kan också visa inställningar för Övrig e-post för postlådor i din organisation genom att köra cmdleten [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759). 
  
Aktivera Övrig e-post för en enskild användare med namnet Diana Bergqvist
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Inaktivera Övrig e-post med Exchange PowerShell

Du kan manuellt inaktivera Övrig e-post för en postlåda genom att köra cmdleten [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446). Du kan också visa inställningarna för **Övrig e-post** för postlådor i din organisation genom att köra cmdleten [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759). 
  
Inaktivera Övrig e-post för en enskild användare med namnet Diana Bergqvist:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Om du använder PowerShell för att skapa flera användare samtidigt måste du köra [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) mot varje användares postlåda för att hantera Övrig e-post. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>När visas alternativet för att aktivera/inaktivera Övrig e-post för användare i Outlook på webben?
<a name="bkmk_onoff"> </a>

Som administratör kan du återaktivera övrig e-post med Exchange PowerShell. När du gjort detta inaktiveras Prioriterad inkorg och Övrig e-post aktiveras igen. 
  
 **Om du använder Outlook på webben med Office 365 Business-abonnemang:**
  
- Om användaren har aktiverat Övrig e-post: 
    
  - Inställningar för Övrig e-post visas
    
- Om användaren har aktiverat Prioriterad inkorg: 
    
  - Inställningarna för Övrig e-post visas inte
    
- Om varken Övrig e-post eller Prioriterad inkorg har aktiverats: 
    
  - Både Övrig e-post och Prioriterad inkorg visas som alternativ i användarens e-postinställningar
    
 **Om du använder Outlook.com:**
  
- Om användaren har aktiverat Övrig e-post: 
    
  - Inställningar för Övrig e-post visas
    
- Om användaren har aktiverat Prioriterad inkorg: 
    
  - Inställningarna för Övrig e-post visas inte
    
- Om varken Övrig e-post eller Prioriterad inkorg har aktiverats: 
    
  - Både Övrig e-post och Prioriterad inkorg visas som alternativ i användarens e-postinställningar
    
- Om användaren har aktiverat Prioriterad inkorg tidigare:
    
  - Inställningarna för Övrig e-post visas aldrig
    
    I annat fall 
    
  - Övrig e-post visas
    
## <a name="related-articles"></a>Relaterade artiklar
<a name="bkmk_onoff"> </a>

[Använd Övrig e-post för att sortera meddelanden med låg prioritet i Outlook](https://support.office.com/article/7755ebf5-4585-469b-b1ab-8b12425c6b6b.aspx)
    
[Använd Övrig e-post för att sortera meddelanden med låg prioritet i OWA](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[Stänga av Övrig e-post i Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

