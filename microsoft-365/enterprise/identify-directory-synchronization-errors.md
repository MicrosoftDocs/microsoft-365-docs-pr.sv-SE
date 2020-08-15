---
title: Visa synkroniseringsfel i Microsoft 365
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
description: Lär dig mer om hur du visar synkroniseringsfel och möjliga korrigeringar i Microsoft 365 Admin Center.
ms.openlocfilehash: 5103b1f8a8f0514ca30fd71b94dee2530f0b082f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694791"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Visa synkroniseringsfel i Microsoft 365

Du kan visa synkroniseringsfel i Microsoft 365 Admin Center. Det är bara användarobjektet som visas. Information om hur du visar fel med PowerShell finns i [identifiera objekt med DirSyncProvisioningErrors](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Visa synkroniseringsfel i Microsoft 365 Admin Center

Så här visar du eventuella fel i Microsoft 365 Admin Center:
  
1. Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) med ett globalt administratörs konto. 
    
2. På **Start** sidan visas **användar hanterings** kortet. 
    
    ![Användar hanterings kortet i administrations centret för Microsoft 365](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. På kortet väljer du **synkroniseringsfel** under **Azure AD Connect** för att se felen på sidan katalog- **Synkroniseringsproblem** .   
    
    ![Ett exempel på sidan katalog synkroniseringsfel](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. Välj något av felen för att Visa informations fönstret med information om felet och tips om hur du åtgärdar det.

   ![Exempel på information om ett katalog synkroniseringsfel](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
Efter visning läser du [åtgärda problem med profilsynkronisering för Microsoft 365](fix-problems-with-directory-synchronization.md) för att åtgärda eventuella identifierade problem.

