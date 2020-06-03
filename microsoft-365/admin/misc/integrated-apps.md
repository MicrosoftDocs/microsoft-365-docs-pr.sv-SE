---
title: Hantera användarens medgivande till appar i Microsoft 365
f1.keywords:
- CSH
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Läs mer om användarens medgivande till appar och hur du aktiverar dem så att appar från tredje part kan komma åt användarnas Microsoft 365-information.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498323"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Hantera användarens medgivande till appar i Microsoft 365

Den här inställningen styr om användare kan ge det medgivandet till appar som använder OpenID Connect och OAuth 2.0 för inloggning och begäranden om åtkomst till data. En app kan skapas inifrån din egen organisation eller komma från en annan Office 365-organisation eller en tredje part.

Om du aktiverar den här inställningen ber dessa appar användarna om tillåtelse att komma åt organisationens data och användarna kan välja om de vill tillåta det. Om du inaktiverar den här inställningen måste administratörerna samtycka till dessa appar innan användarna kan använda dem. I det här fallet bör du överväga att konfigurera ett arbetsflöde för administratörsgodkännande i Azure-portalen så att användarna kan skicka en begäran om administratörsgodkännande för att använda en blockerad app.

Det går bara att ge behörighet till sin egen Office 365-information. Det går inte att ge åtkomst till andra användares information.

## <a name="turning-user-consent-on-or-off"></a>Aktivera eller inaktivera användarens medgivande
<a name="__toc379982114"> </a>

Så här aktiverar eller inaktiverar du Användarens medgivande till appar.

1. Gå till sidan **Inställningar** Org settings Services i administrationscentret \> **Org settings**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) och välj sedan **Användarens medgivande till appar**.

2. På sidan **Användarens medgivande till appar** väljer du alternativet att aktivera eller inaktivera användarens medgivande.

## <a name="more-info"></a>Mer information
<a name="__toc379982114"> </a>

Mer information om hur du konfigurerar dina inställningar för medgivande i Azure active directory läser [du Konfigurera arbetsflödet för administratörssamtycke](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Om du vill veta mer om hur du hanterar användarens medgivande till appar läser du [Hantera samtycke till program och utvärdera samtyckesbegäranden](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).