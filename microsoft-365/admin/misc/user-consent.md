---
title: Hantera användar medgivande till program i Microsoft 365
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
description: Lär dig mer om användarens medgivande till appar och hur du aktiverar dem så att program från tredje part kan komma åt användarnas Microsoft 365-information.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999589"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Hantera användar medgivande till program i Microsoft 365

Den här inställningen styr om användare kan ge tillstånd till program som använder OpenID Connect och OAuth 2,0 för inloggning och förfrågningar om att få åtkomst till data. En app kan skapas i din egen organisation eller så kan den komma från en annan Office 365-organisation eller tredje part.

Om du aktiverar den här inställningen ber dessa appar användare att få åtkomst till organisationens data och användare kan välja om de vill tillåta det. Om du inaktiverar den här inställningen måste administratörer godkänna dessa appar innan användarna kan använda dem. I det här fallet kan du skapa ett arbets flöde för administratörs medgivande i Azure-portalen så att användare får skicka en begäran om administratörs godkännande för att använda blockerade appar.

Det går bara att ge behörighet till sin egen Office 365-information. Det går inte att ge åtkomst till andra användares information.

## <a name="turning-user-consent-on-or-off"></a>Aktivera eller inaktivera användar medgivande
<a name="__toc379982114"> </a>

Så här aktiverar eller inaktiverar du användar medgivande för appar.

1. I administrations centret går du till sidan **Inställningar** \> **organisations inställningar**  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) och väljer sedan **användarens medgivande till appar**.

2. På sidan **användare medgivande till program** markerar du alternativet för att aktivera eller inaktivera användar medgivande.

## <a name="more-info"></a>Mer information
<a name="__toc379982114"> </a>

Om du vill veta mer om hur du konfigurerar medgivande inställningar i Azure Active Directory läser du [Konfigurera arbets flödet för administratörs godkännande](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Om du vill veta mer om hur du hanterar användarens medgivande till appar läser du [Hantera medgivande till program och utvärdering av medgivande förfrågningar](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).