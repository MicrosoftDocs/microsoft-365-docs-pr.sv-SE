---
title: Justera villkorsstyrd åtkomst
description: Så här utesluter du vissa Microsoft-konton
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8844c50f5faba609b3f5f53adc5ab45ba1dbaa74
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529689"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="d630f-104">Justera villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="d630f-104">Adjust conditional access</span></span>

<span data-ttu-id="d630f-105">Om du använder [principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) i organisationen måste du ange att de ska utesluta vissa konton så att Microsoft Managed Desktop kan fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="d630f-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="d630f-106">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="d630f-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="d630f-107">Se avsnittet "Återställ steg" i [Så här planerar du distributionen för villkorlig åtkomst i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span><span class="sxs-lookup"><span data-stu-id="d630f-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="d630f-108">Följ stegen där för att utesluta gruppen *Moderna arbetsplatstjänstkonton* för alla principer.</span><span class="sxs-lookup"><span data-stu-id="d630f-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="d630f-109">Om du har några problem med villkorlig åtkomst kontaktar du [administratörssupporten](../working-with-managed-desktop/admin-support.md).</span><span class="sxs-lookup"><span data-stu-id="d630f-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="d630f-110">Steg för att komma igång med Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="d630f-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="d630f-111">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="d630f-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="d630f-112">Justera villkorlig åtkomst (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="d630f-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="d630f-113">Koppla licenser</span><span class="sxs-lookup"><span data-stu-id="d630f-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="d630f-114">Distribuera Intune-företagsportalen</span><span class="sxs-lookup"><span data-stu-id="d630f-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="d630f-115">Aktivera Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="d630f-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="d630f-116">Konfigurera enheter</span><span class="sxs-lookup"><span data-stu-id="d630f-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="d630f-117">Gör användarna redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="d630f-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="d630f-118">Distribuera appar</span><span class="sxs-lookup"><span data-stu-id="d630f-118">Deploy apps</span></span>](deploy-apps.md)
