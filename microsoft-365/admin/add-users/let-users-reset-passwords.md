---
title: Låt användare återställa sina egna lösenord i Office 365
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Läs om hur du kan återställa dina lösenord med hjälp av verktyget för återställning av lösenord med självbetjäning.
ms.openlocfilehash: 87accc393d08b922ebc3f75ef1aa5ddb2d0b2955
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42811536"
---
# <a name="let-users-reset-their-own-passwords"></a>Låt användare återställa sina egna lösenord

Står folk i kö och ber dig återställa deras lösenord? Som Microsoft 365-administratör kan du låta personer använda [verktyget för återställning av självbetjäning sÃ¤nsten,](https://go.microsoft.com/fwlink/p/?LinkId=522677) så att du inte behöver återställa lösenord för dem. Det innebär mindre jobb för dig! 
  
Här är några saker du kan behöva veta:
  
- Självbetjäning för återställning av lösenord för molnanvändare ingår **kostnadsfritt** i alla betalabonnemang för Office 365 Business, Education eller Office 365 för ideella föreningar. Det fungerar inte med utvärderingsversioner av Office 365. 
    
- Tjänsten använder Azure. Du får automatiskt den här funktionen **kostnadsfritt** när du utför de här stegen. Det kostar dig ingenting att aktivera självbetjäning för återställning av lösenord om du inte använder andra Azure-funktioner. 
    
- **Om du använder Active Directory lokalt** gäller inte de två punkterna ovan. Du kan du konfigurera det här, men **det kräver en betald prenumeration på Azure AD Premium**. 

Titta på en kort video om att låta användarna återställa sina egna lösenord. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="let-people-reset-their-own-passwords"></a>Låt människor återställa sina egna lösenord 

Anvisningarna aktiverar Självbetjäning för återställning av lösenord för alla i organisationen.
  
::: moniker range="o365-worldwide"
1.  Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">sekretesssidan</a> **Inställningar** \> & sekretess i administrationscentret.

::: moniker-end

::: moniker range="o365-germany"

1. Gå till **sekretesssidan &amp; ** **Inställningar** \> säkerhet i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a>

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till **sekretesssidan &amp; ** **Inställningar** \> säkerhet i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a>

::: moniker-end

   
2. Välj länken för **Azure AD-administrationscentret**under **Låt dina personer återställa sina egna lösenord**. Du får Azure kostnadsfritt!
  
3. Välj **Användare** i den vänstra navigeringen och välj sedan **Lösenordsåterställning**.
  
4. På sidan Egenskaper väljer du **Alla** för att aktivera den för alla i ditt företag och väljer sedan **Spara**.
  
5. När användarna loggar in på Office 365 uppmanas de ange ytterligare kontaktinformation så att de kan få hjälp med att återställa lösenordet i framtiden.

## <a name="related-articles"></a>Relaterade artiklar

[Ange förfalloprincip för lösenord i organisationen](../manage/set-password-expiration-policy.md)
  
[Ange att en enskild användares lösenord aldrig ska förfalla](set-password-to-never-expire.md)

[Utbildningsvideor för Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
