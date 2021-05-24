---
title: Hantera användarens medgivande för appar i Microsoft 365
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
description: Läs mer om användarens medgivande till appar och hur du aktiverar dem för att tillåta tredje parts appar att få åtkomst Microsoft 365 information.
ms.openlocfilehash: b8f65b50e50b0e0b4d978388463bbd380ca60d4e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624507"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Hantera användarens medgivande för appar i Microsoft 365

Den här inställningen styr om användare kan ge det medgivande till appar som använder OpenID Anslut och OAuth 2.0 för inloggning och förfrågningar om åtkomst till data. Du kan skapa en app inom din egen organisation eller så kan den komma från Office 365 annan organisation eller tredje part.

Om du aktiverar den här inställningen ber de apparna om behörighet till organisationens data och användarna kan välja om de vill tillåta dem. Om du inaktiverar den här inställningen måste administratörer godkänna dessa appar innan användarna kan använda dem. I det här fallet kan du konfigurera ett arbetsflöde för administratörsmedgivande i Azure Portal så att användarna kan skicka en begäran om administratörsgodkännande för att använda en blockerad app.

Det går bara att ge behörighet till sin egen Office 365-information. Det går inte att ge åtkomst till andra användares information.

## <a name="turning-user-consent-on-or-off"></a>Aktivera eller inaktivera användarmedgivande
<a name="__toc379982114"> </a>

Så här aktiverar eller inaktiverar du användarmedgivande för appar.

1. I administrationscentret går du till sidan **för Inställningar** \> **Organisationsinställningar** och väljer  >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) sedan **Användarens medgivande för appar**.

2. På sidan **Användarens medgivande till appar** väljer du alternativet att aktivera eller inaktivera användarens medgivande.

## <a name="related-content"></a>Relaterat innehåll 
<a name="__toc379982114"> </a>

[Konfigurera arbetsflödet för administratörsmedgivande](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (artikel)\
[Hantera medgivande för program och utvärdera medgivandeförfrågningar](/azure/active-directory/manage-apps/manage-consent-requests) (artikel)