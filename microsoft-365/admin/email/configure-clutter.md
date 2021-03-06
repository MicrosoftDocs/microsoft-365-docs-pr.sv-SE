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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Lär dig att aktivera eller inaktivera funktionen Övrig e-post för alla eller vissa användare i organisationen, med hjälp Exchange PowerShell. '
ms.openlocfilehash: 059fb8e626a0b05e0224fc89931453aaae43be0b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706123"
---
# <a name="configure-clutter-for-your-organization"></a>Konfigurera Övrig e-post för organisationen

> [!TIP]
> [Prioriterad inkorg](../setup/configure-focused-inbox.md) kommer att ersätta Övrig e-post. Läs mer: [Uppdaterad information om Prioriterad inkorg och våra planer för Övrig e-post](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)
  
Som administratör kan du behöva hantera funktionen Övrig e-post i Microsoft 365. Om du vill aktivera/inaktivera funktionen Övrig e-post för användare i organisationen måste du använda Exchange PowerShell. (Enskilda användare kan aktivera/inaktivera med hjälp av de här anvisningarna: [Aktivera/inaktivera Övrig e-Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).
  
Läs artikeln [Använd PowerShell med Exchange Online](/powershell/exchange/exchange-online-powershell) och [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) för information om hur du använder Exchange PowerShell. Du måste ha ett konto som har minst rollen Exchange tjänstadministratör och möjlighet att ansluta till Exchange Online med PowerShell. 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a>Aktivera Övrig e-post med Exchange PowerShell

Du kan manuellt aktivera Övrig e-post för en postlåda genom att köra cmdleten [Set-Clutter](/powershell/module/exchange/set-clutter). Du kan också visa inställningar för Övrig e-post för postlådor i din organisation genom att köra cmdleten [Get-Clutter](/powershell/module/exchange/get-clutter). 
  
Aktivera Övrig e-post för en enskild användare med namnet Diana Bergqvist
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a>Inaktivera Övrig e-post med Exchange PowerShell

Du kan manuellt inaktivera Övrig e-post för en postlåda genom att köra cmdleten [Set-Clutter](/powershell/module/exchange/set-clutter). Du kan också visa inställningarna för **Övrig e-post** för postlådor i din organisation genom att köra cmdleten [Get-Clutter](/powershell/module/exchange/get-clutter). 
  
Inaktivera Övrig e-post för en enskild användare med namnet Diana Bergqvist:
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

Om du använder PowerShell för att skapa flera användare samtidigt måste du köra [Set-Clutter](/powershell/module/exchange/set-clutter) mot varje användares postlåda för att hantera Övrig e-post. 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a>När visas alternativet för att aktivera/inaktivera Övrig e-post för användare i Outlook på webben?
<a name="bkmk_onoff"> </a>

Som administratör kan du återaktivera Övrig e-post med Exchange PowerShell. När du gjort detta inaktiveras Prioriterad inkorg och Övrig e-post aktiveras igen. 
  
 **Om du använder en Outlook på webben med en Microsoft 365 Business Premium prenumeration:**
  
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
    
## <a name="related-content"></a>Relaterat innehåll

[Använd Övrig e-post för att sortera meddelanden med låg prioritet Outlook](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0) (artikel)\
[Använd Övrig e-post för att sortera meddelanden med låg prioritet i OWA](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce) (artikel)\
[Inaktivera Övrig e-post i Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c) (artikel)
