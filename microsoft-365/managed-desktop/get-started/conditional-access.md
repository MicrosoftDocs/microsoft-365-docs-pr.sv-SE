---
title: Justera villkorlig åtkomst
description: Så här utesluter du vissa Microsoft-konton
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1bc5d937616cba60c5af43fe22a7c4dccf89a55e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806478"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="1c457-104">Justera villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="1c457-104">Adjust conditional access</span></span>

<span data-ttu-id="1c457-105">Om du använder [principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) i organisationen måste du ange att de ska utesluta vissa konton så att Microsoft Managed Desktop kan fungera korrekt.</span><span class="sxs-lookup"><span data-stu-id="1c457-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="1c457-106">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="1c457-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="1c457-107">Se avsnittet "Återställ steg" i [Så här planerar du distributionen för villkorlig åtkomst i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span><span class="sxs-lookup"><span data-stu-id="1c457-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="1c457-108">Följ stegen där för att utesluta gruppen *Moderna arbetsplatstjänstkonton* för alla principer.</span><span class="sxs-lookup"><span data-stu-id="1c457-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="1c457-109">Om du har några problem med villkorlig åtkomst kontaktar du [administratörssupporten](../working-with-managed-desktop/admin-support.md).</span><span class="sxs-lookup"><span data-stu-id="1c457-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="1c457-110">Steg för att komma igång med Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="1c457-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="1c457-111">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="1c457-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="1c457-112">Justera villkorlig åtkomst (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="1c457-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="1c457-113">Tilldela licenser</span><span class="sxs-lookup"><span data-stu-id="1c457-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="1c457-114">Distribuera Intune-företagsportal</span><span class="sxs-lookup"><span data-stu-id="1c457-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="1c457-115">Aktivera roaming i företagstillstånd</span><span class="sxs-lookup"><span data-stu-id="1c457-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="1c457-116">Konfigurera enheter</span><span class="sxs-lookup"><span data-stu-id="1c457-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="1c457-117">Gör användarna redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="1c457-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="1c457-118">Distribuera appar</span><span class="sxs-lookup"><span data-stu-id="1c457-118">Deploy apps</span></span>](deploy-apps.md)
