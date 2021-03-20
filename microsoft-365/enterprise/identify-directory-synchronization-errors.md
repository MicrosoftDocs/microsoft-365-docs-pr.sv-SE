---
title: Visa katalogsynkroniseringsfel i Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: Lär dig hur du visar katalogsynkroniseringsfel och möjliga korrigeringar i administrationscentret för Microsoft 365.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907510"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Visa katalogsynkroniseringsfel i Microsoft 365

Du kan visa katalogsynkroniseringsfel i administrationscentret för Microsoft 365. Endast användarobjektfel visas. Information om hur du visar fel med PowerShell [finns i Identifiera objekt med DirSyncProvisioningErrors.](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Visa katalogsynkroniseringsfel i administrationscentret för Microsoft 365

Så här visar du eventuella fel i administrationscentret för Microsoft 365:
  
1. Logga in på [administrationscentret för Microsoft 365 med](https://admin.microsoft.com) ett globalt administratörskonto. 
    
2. På **startsidan** visas kortet **Användarhantering.** 
    
    ![Användarhanteringskortet i administrationscentret för Microsoft 365](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. På kortet väljer du **Synkroniseringsfel** under **Azure AD Connect** för att se felen på sidan **Katalogsynkroniseringsfel.**   
    
    ![Ett exempel på sidan Katalogsynkroniseringsfel](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. Välj något av felen om du vill visa informationsfönstret med information om felet och tips om hur du åtgärdar det.

   ![Exempel på information om ett katalogsynkroniseringsfel](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
Läs åtgärda problem [med katalogsynkronisering för Microsoft 365 efter](fix-problems-with-directory-synchronization.md) visning för att korrigera eventuella identifierade problem.