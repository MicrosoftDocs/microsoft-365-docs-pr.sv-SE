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
description: Lär dig hur du återställer dina lösen ord med standard verktyget för återställning av lösen ord.
ms.openlocfilehash: 1684afd1baf32acc6c4245938b2ac7ee024d7374
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361813"
---
# <a name="let-users-reset-their-own-passwords"></a>Låt användare återställa sina egna lösenord

Som Microsoft 365-administratör kan du låta andra använda [standard verktyget för återställning av lösen ord](https://go.microsoft.com/fwlink/p/?LinkId=522677) så att du inte behöver återställa lösen ord för dem. Det innebär mindre jobb för dig!
  
## <a name="before-you-begin"></a>Innan du börjar
  
- Du får själv återställning av lösen ord för moln användare **utan kostnad** för Microsoft 365-verksamhet, utbildning eller ideell betalning. Den fungerar inte med utvärderings versionen av Microsoft 365.

- Tjänsten använder Azure. Du får automatiskt den här funktionen **kostnadsfritt** när du utför de här stegen. Det kostar dig ingenting att aktivera självbetjäning för återställning av lösenord om du inte använder andra Azure-funktioner.

- **Om du använder Active Directory lokalt** gäller inte de två punkterna ovan. Du kan du konfigurera det här, men **det kräver en betald prenumeration på Azure AD Premium**.

Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening. För att utföra de här stegen måste du logga in med ditt Microsoft 365-administratörs konto. [Vad är ett administratörs konto?](../admin-overview/admin-overview.md)

Du måste vara [Global administratör eller lösen ords administratör](about-admin-roles.md) för att utföra de här stegen.

## <a name="watch-let-users-reset-their-own-passwords"></a>Titta: Låt användare återställa sina egna lösen ord

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="steps-let-people-reset-their-own-passwords"></a>Steg: Låt andra återställa sina egna lösen ord

Anvisningarna aktiverar Självbetjäning för återställning av lösenord för alla i organisationen.
  
::: moniker range="o365-worldwide"

1. Gå till sidan **Inställningar** organisations inställningar i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrations centret</a> > **Org settings** .

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrations centret</a>går du till sidan **Inställningar** för \> **säkerhets &amp; Sekretess** .

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrations centret</a>går du till sidan **Inställningar** för \> **Settings** \> **säkerhets &amp; Sekretess** .

::: moniker-end

2. Högst upp på sidan **organisations inställningar** väljer du fliken **säkerhet & sekretess** .
  
3. Välj **självbetjäning för återställning av lösen ord**.

4. Under **Automatisk återställning av lösen ord**väljer **du gå till Azure-portalen för att aktivera automatisk återställning av lösen ord**.

5. I det vänstra navigerings fönstret väljer **du användare**och sedan, på **användare | Sidan alla användare** väljer du **Återställ lösen ord**.
  
6. På sidan **Egenskaper** väljer du **alla** för att aktivera det för alla i företaget och väljer sedan **Spara**.
  
7. När användarna loggar in uppmanas de att ange ytterligare kontakt information som hjälper dem att återställa lösen ordet i framtiden.

## <a name="related-content"></a>Relaterat innehåll

[Ange förfalloprincip för lösenord i organisationen](../manage/set-password-expiration-policy.md)

[Ange att en enskild användares lösenord aldrig ska förfalla](set-password-to-never-expire.md)

[Utbildningsvideor för Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
