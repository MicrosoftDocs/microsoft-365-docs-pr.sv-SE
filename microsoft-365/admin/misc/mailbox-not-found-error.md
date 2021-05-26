---
title: Få ett felmeddelande om att postlådan inte hittades i Outlook på webben
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Felmeddelandet **Det gick inte att hitta postlådan för** innebär att kontot du använde för att ansluta till Outlook på webben inte har en licens för Exchange Online.
ms.openlocfilehash: cb82f917adca8f1fc183fd9516321a524c63eb69
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635792"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a>Får du ett felmeddelande om att postlådan inte hittades i Outlook på webben?

Om du använder Outlook på webben och du får felmeddelandet **Det inte gick att hitta postlådan för**, så har kontot som du använde för att ansluta till Outlook på webben inte en licens för Exchange Online och därför är ingen postlåda kopplad till kontot. 

## <a name="assign-a-license-to-your-account"></a>Tilldela en licens till kontot

Administratören kan tilldela en licens till kontot genom att göra följande:

1. Öppna [Administrationscenter för Microsoft 365](https://portal.office.com/adminportal/home#/homepage)  och gå till  **Aktiva användare**  i avsnittet  **Users**  och välj den användare som får felmeddelandet.
1. På sidan för användare som öppnas går du till avsnittet **Licenser och program**, väljer lämpligt värde för **Plats** och tilldelar en licens som innehåller Exchange Online (expandera licensen för att visa dess information). 
1. När du är klar klickar du på **Spara ändringar**.

## <a name="related-content"></a>Relaterat innehåll

[Lägga till ytterligare ett e-postalias för en användare](../email/add-another-email-alias-for-a-user.md) (artikel)\
[Konfigurera vidarebefordran av e-post i Microsoft 365](../email/configure-email-forwarding.md) (artikel)\
[Skapa en delad postlåda](../email/create-a-shared-mailbox.md) (artikel)