---
title: Hantera användarmedgivande till appar i Microsoft 365
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
description: Läs mer om användarens medgivande till appar och hur du aktiverar dem för att tillåta tredjepartsprogram att få åtkomst till information om Microsoft 365.
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914570"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Hantera användarmedgivande till appar i Microsoft 365

Den här inställningen styr om användare kan ge det medgivande till appar som använder OpenID Connect och OAuth 2.0 för inloggning och förfrågningar om åtkomst till data. Du kan skapa en app från din egen organisation eller så kan den komma från en annan Office 365-organisation eller tredje part.

Om du aktiverar den här inställningen ber de apparna om behörighet till organisationens data och användarna kan välja om de vill tillåta dem. Om du inaktiverar den här inställningen måste administratörer godkänna dessa appar innan användarna kan använda dem. I det här fallet kan du konfigurera ett arbetsflöde för administratörsmedgivande i Azure Portal så att användarna kan skicka en begäran om administratörsgodkännande för att använda en blockerad app.

Det går bara att ge behörighet till sin egen Office 365-information. Det går inte att ge åtkomst till andra användares information.

## <a name="turning-user-consent-on-or-off"></a>Aktivera eller inaktivera användarmedgivande
<a name="__toc379982114"> </a>

Så här aktiverar eller inaktiverar du användarmedgivande för appar.

1. I administrationscentret går du till sidan **Inställningar För** \> **organisationsinställningar** och väljer  >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) sedan **Användarens medgivande för appar.**

2. På sidan **Användarens medgivande till appar** väljer du alternativet att aktivera eller inaktivera användarens medgivande.

## <a name="more-info"></a>Mer information
<a name="__toc379982114"> </a>

Mer information om hur du konfigurerar dina medgivandeinställningar i Azure Active Directory finns i Konfigurera [arbetsflödet för administratörsmedgivande.](/azure/active-directory/manage-apps/configure-admin-consent-workflow)

Mer information om hur du hanterar användares medgivande för appar finns i [Hantera medgivande för program och utvärdera medgivandebegäranden.](/azure/active-directory/manage-apps/manage-consent-requests)