---
title: Aktivera Enterprise State Roaming
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 61b84b3c7b6550a8ce426a3e41630a0d3e269c41
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921960"
---
# <a name="enable-enterprise-state-roaming"></a><span data-ttu-id="b8fd5-103">Aktivera Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="b8fd5-103">Enable Enterprise State Roaming</span></span>

<span data-ttu-id="b8fd5-104">För att få den bästa upplevelsen med Microsoft Managed Desktop kan du aktivera [Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview), som gör att användarna säkert kan synkronisera användar- och programinställningar till molnet.</span><span class="sxs-lookup"><span data-stu-id="b8fd5-104">For the best experience with Microsoft Managed Desktop, enable [Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview), which lets users securely synchronize user and application settings data to the cloud.</span></span> <span data-ttu-id="b8fd5-105">Det innebär att de har samma upplevelse oavsett vilken Windows-enhet de loggar in på.</span><span class="sxs-lookup"><span data-stu-id="b8fd5-105">This means they'll have the same experience no matter which Windows device they sign into.</span></span> <span data-ttu-id="b8fd5-106">Om du till exempel ersätter en av deras Microsoft Managed Desktop-enheter med en ny kommer den att se ut och fungera på exakt samma sätt som den sista.</span><span class="sxs-lookup"><span data-stu-id="b8fd5-106">For example, if you replace one of their Microsoft Managed Desktop devices with a new one, it will look and behave exactly the same as the last one.</span></span>

<span data-ttu-id="b8fd5-107">Om du vill aktivera State Roaming för företag följer du stegen i Aktivera state Roaming för företag [i Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable)och återgår sedan till den här dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="b8fd5-107">To enable Enterprise State Roaming, follow the steps in [Enable Enterprise State Roaming in Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable), and then return to this documentation.</span></span>

<span data-ttu-id="b8fd5-108">Om du har problem med Roaming i Enterprise State Roaming kontaktar du [administratörssupport.](../working-with-managed-desktop/admin-support.md)</span><span class="sxs-lookup"><span data-stu-id="b8fd5-108">If you have any difficulty with Enterprise State Roaming, contact Admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="b8fd5-109">Steg för att komma igång med Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="b8fd5-109">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="b8fd5-110">Lägga till och verifiera administratörskontakter i administratörsportalen</span><span class="sxs-lookup"><span data-stu-id="b8fd5-110">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="b8fd5-111">Justera villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="b8fd5-111">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="b8fd5-112">Koppla licenser</span><span class="sxs-lookup"><span data-stu-id="b8fd5-112">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="b8fd5-113">Distribuera Intune-företagsportalen</span><span class="sxs-lookup"><span data-stu-id="b8fd5-113">Deploy Intune Company Portal</span></span>](company-portal.md)
5. <span data-ttu-id="b8fd5-114">Aktivera roaming i företagstillstånd (det här avsnittet)</span><span class="sxs-lookup"><span data-stu-id="b8fd5-114">Enable Enterprise State Roaming (this topic)</span></span>
6. [<span data-ttu-id="b8fd5-115">Konfigurera enheter</span><span class="sxs-lookup"><span data-stu-id="b8fd5-115">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="b8fd5-116">Gör användarna redo att använda enheter</span><span class="sxs-lookup"><span data-stu-id="b8fd5-116">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="b8fd5-117">Distribuera appar</span><span class="sxs-lookup"><span data-stu-id="b8fd5-117">Deploy apps</span></span>](deploy-apps.md)