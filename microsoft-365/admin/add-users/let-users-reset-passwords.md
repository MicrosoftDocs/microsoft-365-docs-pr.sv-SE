---
title: Låt användare återställa sina egna lösenord
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
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Lär dig hur du återställer dina lösenord med självbetjäningsverktyget för återställning av lösenord.
ms.openlocfilehash: f43c409e98aa98e942bd7c7cbb15302422df241d
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222129"
---
# <a name="let-users-reset-their-own-passwords"></a>Låt användare återställa sina egna lösenord

Som Microsoft 365-administratör kan du [](https://go.microsoft.com/fwlink/p/?LinkId=522677) låta personer använda självbetjäningsverktyget för återställning av lösenord så att du inte behöver återställa lösenord åt dem. Det innebär mindre jobb för dig!
  
## <a name="before-you-begin"></a>Innan du börjar
  
- Självbetjäning för återställning av  lösenord för molnanvändare krävs kostnadsfritt i alla betalabonnemang för Microsoft 365 Business, Education eller Office 365 för ideella föreningar. Det fungerar inte med utvärderingsversionen av Microsoft 365.

- Tjänsten använder Azure. Du får automatiskt den här funktionen **kostnadsfritt** när du utför de här stegen. Det kostar dig ingenting att aktivera självbetjäning för återställning av lösenord om du inte använder andra Azure-funktioner.

- **Om du använder Active Directory lokalt** gäller inte de två punkterna ovan. Du kan du konfigurera det här, men **det kräver en betald prenumeration på Azure AD Premium**.

Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening. Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen. [Vad är ett administratörskonto?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

Du måste vara global [administratör eller lösenordsadministratör för att](about-admin-roles.md) utföra de här stegen.

## <a name="watch-let-users-reset-their-own-passwords"></a>Titta: Låt användare återställa sina egna lösenord

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="steps-let-people-reset-their-own-passwords"></a>Steg: Låt användare återställa sina egna lösenord

Anvisningarna aktiverar Självbetjäning för återställning av lösenord för alla i organisationen.
  
::: moniker range="o365-worldwide"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret går</a>du till sidan **Inställningar** > **för** organisationen.

::: moniker-end

::: moniker range="o365-germany"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret går</a>du till sidan **Sekretess för** \> **&amp; inställningar.**

::: moniker-end

::: moniker range="o365-21vianet"

1. I <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret går</a>du till sidan **Inställningar för** \>  \> **sekretesssäkerhet. &amp;**

::: moniker-end

2. Högst upp på sidan **Organisationsinställningar** väljer du fliken **Säkerhet &** Sekretess.
  
3. Välj **Självbetjäning för återställning av lösenord.**

4. Under **Självbetjäning för återställning av** lösenord väljer du Gå till Azure Portal för att aktivera **självbetjäning för återställning av lösenord.**

5. I det vänstra navigeringsfönstret väljer **du** Användare och går sedan till **fliken | Alla användare** väljer **lösenordsåterställning.**
  
6. På sidan **Egenskaper** väljer du **Alla för** att aktivera det för alla i företaget. Välj sedan **Spara**.
  
7. När användarna loggar in uppmanas de att ange ytterligare kontaktinformation som hjälper dem att återställa lösenordet i framtiden.

## <a name="related-content"></a>Relaterat innehåll

[Ange förfalloprincip för lösenord i organisationen](../manage/set-password-expiration-policy.md)

[Ange att en enskild användares lösenord aldrig ska förfalla](set-password-to-never-expire.md)

[Utbildningsvideor för Microsoft 365 Business](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
