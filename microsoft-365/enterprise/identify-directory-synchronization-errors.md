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
description: Lär dig hur du visar katalogsynkroniseringsfel och möjliga korrigeringar Microsoft 365 administrationscentret.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907510"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="a9f9a-103">Visa katalogsynkroniseringsfel i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9f9a-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="a9f9a-104">Du kan visa katalogsynkroniseringsfel i Microsoft 365 administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a9f9a-105">Endast användarobjektfel visas.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="a9f9a-106">Information om hur du visar fel med PowerShell [finns i Identifiera objekt med DirSyncProvisioningErrors.](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)</span><span class="sxs-lookup"><span data-stu-id="a9f9a-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a9f9a-107">Visa katalogsynkroniseringsfel i Microsoft 365 administrationscenter</span><span class="sxs-lookup"><span data-stu-id="a9f9a-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a9f9a-108">Så här visar du eventuella fel Microsoft 365 administrationscentret:</span><span class="sxs-lookup"><span data-stu-id="a9f9a-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="a9f9a-109">Logga in på [Microsoft 365 med](https://admin.microsoft.com) ett globalt administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="a9f9a-110">På **startsidan** visas kortet **Användarhantering.**</span><span class="sxs-lookup"><span data-stu-id="a9f9a-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![Användarhanteringskortet i Microsoft 365 administrationscenter](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="a9f9a-112">På kortet väljer du **Synkronisera fel** under Azure **AD Anslut** för att visa felen på **sidan Katalogsynkroniseringsfel.**</span><span class="sxs-lookup"><span data-stu-id="a9f9a-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![Ett exempel på sidan Katalogsynkroniseringsfel](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="a9f9a-114">Välj något av felen om du vill visa informationsfönstret med information om felet och tips om hur du åtgärdar det.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![Exempel på information om ett katalogsynkroniseringsfel](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="a9f9a-116">Läs åtgärda problem med [katalogsynkronisering efter visningen för att Microsoft 365](fix-problems-with-directory-synchronization.md) korrigera eventuella identifierade problem.</span><span class="sxs-lookup"><span data-stu-id="a9f9a-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>