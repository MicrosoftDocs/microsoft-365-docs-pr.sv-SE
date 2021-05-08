---
title: Steg 6 - Ta bort och radera Microsoft 365 från en tidigare anställd
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Följ dessa steg om du vill Microsoft 365 en tidigare anställds licens.
ms.openlocfilehash: ed86eb28cc6d4996f7def8cb567f0e4085e67624
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244276"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a>Steg 6 – Ta bort Microsoft 365 från en tidigare anställd

Om du inte vill betala för en licens när någon lämnar organisationen måste du ta bort deras Microsoft 365-licens och sedan ta bort den från prenumerationen. Du kan tilldela en licens till en annan användare om du inte tar bort den.
  
När du tar bort licensen bevaras användarens alla data i 30 dagar. Du kan [komma åt](get-access-to-and-back-up-a-former-user-s-data.md) alla data, eller [återställa](restore-user.md) kontot om användaren kommer tillbaka. Efter 30 dagar tas alla användarens data (utom dokument som lagras på SharePoint Online) permanent bort från Microsoft 365 och kan inte återställas.

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.
2. Markera namnet på den anställda som du vill blockera och välj sedan **fliken Licenser och** appar.
3. Avmarkera kryssrutorna för den eller de licenser du vill ta bort och välj sedan **Spara ändringar.**

**Om du vill minska antalet licenser som du betalar för tills** du anställer en annan person gör du följande:

1. I administrationscentret går du till **sidan** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Fakturering dina</a> produkter och väljer **fliken** Produkter.
2. Välj den prenumeration som du vill ta bort licenser från.
3. Välj Ta bort licenser på **informationssidan.**
4. I fönstret **Ta bort** licenser, under  Nytt antal, i rutan Totalt antal licenser anger du det totala antalet licenser som du vill använda för prenumerationen. Om du till exempel har 25 licenser och vill ta bort en av dem anger du 24.
5. Välj **Spara**.

När [du lägger till](add-users.md) ytterligare en person i företaget uppmanas du samtidigt att köpa en licens med bara ett steg!

Mer information om hur du hanterar användarlicenser för Microsoft 365 för företag finns i Tilldela användare licenser i [Microsoft 365](../manage/assign-licenses-to-users.md)för företag och Ta bort licenser från användare i [Microsoft 365 för företag.](../manage/remove-licenses-from-users.md)
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Så här påverkas Skype för företag när en anställds konto tas bort

När du tar bort en användares licens från Office 365 frigörs PSTN-telefonnumret som är kopplat till användaren. Du kan tilldela det till en annan användare.
  
Om användaren tillhör en kögrupp är användaren inte längre ett möjligt mål för agenter från samtalskön. Därför rekommenderar vi att användaren också tas bort från de grupper som är kopplade till samtalskön.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>Konfigurera vidareringning av samtal till personer i organisationen

Om du behöver ställa in vidareringning av den uppsagda medarbetarens telefonnummer kan inställningen för vidareringning under samtalsprinciper ställa in vidarebefordran där inkommande samtal kan vidarebefordras till andra användare eller ringa upp en annan person samtidigt. Mer information finns i [Samtalsprinciper i Microsoft Teams](/microsoftteams/teams-calling-policy).
