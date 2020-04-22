---
title: 'Steg 7: Konfigurera hantering av privilegierad åtkomst'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Förstå och konfigurera hantering av privilegierad åtkomst.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636994"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="1d313-103">Steg 7: Konfigurera hantering av privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="1d313-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="1d313-104">*Det här steget är valfritt och gäller endast E5- och Advanced Compliance-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="1d313-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="1d313-106">Hantering av privilegierad åtkomst aktiveras genom att konfigurera principer som anger just-in-time-åtkomst för aktivitetsbaserade aktiviteter i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="1d313-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="1d313-107">Det kan hjälpa dig att skydda din organisation från intrång som kan använda befintliga privilegierade administratörskonton med ständig åtkomst till känsliga data eller åtkomst till kritiska konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="1d313-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="1d313-108">Du kan till exempel konfigurera en princip för hantering av privilegierad åtkomst som kräver uttryckligt godkännande för åtkomst och ändring av inställningar för organisationspostlådan i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="1d313-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="1d313-109">I det här steget aktiverar du hantering av privilegierad åtkomst i din klientorganisation och konfigurerar principer för privilegierad åtkomst som ger ytterligare säkerhet för uppgiftsbaserad åtkomst till data- och konfigurationsinställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="1d313-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="1d313-110">Det finns tre grundläggande steg för att komma igång med privilegierad åtkomst i organisationen:</span><span class="sxs-lookup"><span data-stu-id="1d313-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="1d313-111">Skapa en godkännargrupp</span><span class="sxs-lookup"><span data-stu-id="1d313-111">Creating an approver's group</span></span>
- <span data-ttu-id="1d313-112">Aktivera privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="1d313-112">Enabling privileged access</span></span>
- <span data-ttu-id="1d313-113">Skapa godkännandeprinciper</span><span class="sxs-lookup"><span data-stu-id="1d313-113">Creating approval policies</span></span>

<span data-ttu-id="1d313-114">När du har konfigurerat Privileged Access Management kan din organisation fungera helt utan ständiga privilegier, och ger ett skydd mot säkerhetsproblem som uppstår på grund av sådan ständig administratörsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="1d313-114">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="1d313-115">Privilegierad åtkomst kräver godkännanden för att kunna utföra en aktivitet som har en kopplad och definierad godkännandeprincip.</span><span class="sxs-lookup"><span data-stu-id="1d313-115">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="1d313-116">Användare som behöver utföra aktiviteter som ingår i en godkännandeprincip måste begära och beviljas åtkomstgodkännande för att få behörigheter för att utföra aktiviteter som definierats i principen.</span><span class="sxs-lookup"><span data-stu-id="1d313-116">Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="1d313-117">Om du vill aktivera hantering av privilegierad åtkomst finns i avsnittet [Konfigurera privilegierad åtkomsthantering.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)</span><span class="sxs-lookup"><span data-stu-id="1d313-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="1d313-118">Mer information finns i avsnittet [Hantering av privilegierad åtkomst.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)</span><span class="sxs-lookup"><span data-stu-id="1d313-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="1d313-120">Information om hur du testar den här konfigurationen i en testlabbmiljö finns i [Privileged Access Management – testlabbguide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1d313-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="1d313-121">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](infoprotect-exit-criteria.md#crit-infoprotect-step7) som motsvarar det här steget.</span><span class="sxs-lookup"><span data-stu-id="1d313-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="1d313-122">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="1d313-122">Next Step</span></span>

[<span data-ttu-id="1d313-123">Avslutsvillkor för informationsskyddets infrastruktur</span><span class="sxs-lookup"><span data-stu-id="1d313-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
