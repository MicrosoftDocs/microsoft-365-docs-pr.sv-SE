---
title: Låt användare återställa sina egna lösenord
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Läs om hur du kan återställa dina lösenord med hjälp av verktyget för återställning av lösenord med självbetjäning.
ms.openlocfilehash: 288613023ee61626bf12f7090ad0ff73139ef06d
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780595"
---
# <a name="let-users-reset-their-own-passwords"></a>Låt användare återställa sina egna lösenord

Står folk i kö och ber dig återställa deras lösenord? Som Microsoft 365-administratör kan du låta användarna använda [självbetjäningsverktyget](https://go.microsoft.com/fwlink/p/?LinkId=522677) för återställning av lösenord så att du inte behöver återställa lösenord för dem. Det innebär mindre jobb för dig! 
  
Här är några saker du kan behöva veta:
  
- Du får lösenordsåterställning med självbetjäning för molnanvändare **gratis** med alla Microsoft 365-företag, utbildningar eller avgiftsbetald ideella. Det fungerar inte med Microsoft 365 rättegång.

- Tjänsten använder Azure. Du får automatiskt den här funktionen **kostnadsfritt** när du utför de här stegen. Det kostar dig ingenting att aktivera självbetjäning för återställning av lösenord om du inte använder andra Azure-funktioner.

- **Om du använder Active Directory lokalt** gäller inte de två punkterna ovan. Du kan du konfigurera det här, men **det kräver en betald prenumeration på Azure AD Premium**.

Titta på en kort video om att låta användare återställa sina egna lösenord. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="let-people-reset-their-own-passwords"></a>Låt andra återställa sina egna lösenord

Anvisningarna aktiverar Självbetjäning för återställning av lösenord för alla i organisationen.
  
::: moniker range="o365-worldwide"

1. Gå till sidan **Inställningar** org i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret.</a> > **Org settings**

::: moniker-end

::: moniker range="o365-germany"

1. Gå till sekretesssidan **för Inställningars** säkerhet i <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret.</a> \> ** &amp; **

::: moniker-end

::: moniker range="o365-21vianet"

1. Gå till sekretesssidan **för** Inställningars säkerhet i <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret.</a> \> **Settings** \> ** &amp; **

::: moniker-end

2. Högst upp på sidan **Organisationsinställningar** väljer du fliken **Sekretess för säkerhet &.**
  
3. Välj **Självbetjäningslösenordsåterställning**.

4. Under **Återställning av lösenord för självbetjäning**väljer du Gå till **Azure-portalen för att aktivera återställning av lösenord för självbetjäning**.

5. I det vänstra navigeringsfönstret väljer du **Användare**och sedan på **användarna | Välj** **Återställ lösenord**för alla användare .
  
6. På sidan **Egenskaper** väljer du **Alla** för att aktivera det för alla i ditt företag och väljer sedan **Spara**.
  
7. När användarna loggar in uppmanas de att ange ytterligare kontaktinformation som hjälper dem att återställa sitt lösenord i framtiden.

## <a name="related-articles"></a>Relaterade artiklar

[Ange förfalloprincip för lösenord i organisationen](../manage/set-password-expiration-policy.md)
  
[Ange att en enskild användares lösenord aldrig ska förfalla](set-password-to-never-expire.md)

[Utbildningsvideor för Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
