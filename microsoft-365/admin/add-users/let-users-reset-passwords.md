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
description: Lär dig hur du kan ställa in en princip så att användarna kan återställa sina egna lösenord med verktyget för återställning av självbetjäningslösenord.
ms.openlocfilehash: 2c79d5611ab2db00f4de5f227b0ec2f411955558
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571859"
---
# <a name="let-users-reset-their-own-passwords"></a>Låt användare återställa sina egna lösenord

Som Microsoft 365 administratör kan du låta människor använda [verktyget för återställning av självbetjäningslösenord](https://go.microsoft.com/fwlink/p/?LinkId=522677) så att du inte behöver återställa lösenord för dem. Det innebär mindre jobb för dig!
  
## <a name="before-you-begin"></a>Innan du börjar
  
- Du får självbetjäningslösenordsåterställning för **molnanvändare** gratis med Microsoft 365, utbildning eller ideell betald plan. Det fungerar inte med Microsoft 365 rättegång.

- Tjänsten använder Azure. Du får automatiskt den här funktionen **kostnadsfritt** när du utför de här stegen. Det kostar dig ingenting att aktivera självbetjäning för återställning av lösenord om du inte använder andra Azure-funktioner.

- **Om du använder Active Directory lokalt** gäller inte de två punkterna ovan. Du kan du konfigurera det här, men **det kräver en betald prenumeration på Azure AD Premium**.

Den här artikeln är avsedd för personer som anger en förfalloprincip för lösenord för ett företag, en skola eller en ideell förening. Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen. [Vad är ett administratörskonto?](../../business-video/admin-center-overview.md)

Du måste vara global [administratör eller lösenordsadministratör för](about-admin-roles.md) att kunna utföra dessa steg.

## <a name="watch-let-users-reset-their-own-passwords"></a>Titta: Låt användare återställa sina egna lösenord

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](../../business-video/index.yml).

## <a name="steps-let-people-reset-their-own-passwords"></a>Steg: Låt människor återställa sina egna lösenord

Anvisningarna aktiverar Självbetjäning för återställning av lösenord för alla i organisationen.

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">sidan Inställningar</a>för Inställningar org **i**  >  **administrationscentret.**

2. Högst upp på sidan **Organisationsinställningar** väljer du fliken **& sekretess.**
  
3. Välj **Återställning av självbetjäningslösenord**.

4. Under **Återställning av självbetjäningslösenord** **väljer du Gå till Azure Portal för att aktivera återställning av självbetjäningslösenord**.

5. I det vänstra navigeringsfönstret **väljer du** Användare och sedan på **| Alla användare** väljer du Återställ **lösenord**.
  
6. På sidan **Egenskaper** väljer du **Alla för** att aktivera den för alla i ditt företag och väljer sedan **Spara**.
  
7. När användarna loggar in uppmanas de att ange ytterligare kontaktinformation som hjälper dem att återställa sitt lösenord i framtiden.

## <a name="related-content"></a>Relaterat innehåll

[Ange principen för förfallodatum för lösenord för din organisation](../manage/set-password-expiration-policy.md) (artikel)

[Ange att en enskild användares lösenord aldrig ska förfalla](set-password-to-never-expire.md)(artikel)

[Microsoft 365 Business utbildningsvideor](../../business-video/index.yml) (länksida)
