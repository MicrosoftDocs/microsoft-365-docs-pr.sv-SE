---
title: 'Steg 7: Konfigurera hantering av privilegierad åtkomst för Office 365'
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
description: Förstå och konfigurera hantering av privilegierad åtkomst för Office 365.
ms.openlocfilehash: f29b1e0934a4b9a6d4e3347584f39423d446ed58
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811101"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="d027f-103">Steg 7: Konfigurera hantering av privilegierad åtkomst för Office 365</span><span class="sxs-lookup"><span data-stu-id="d027f-103">Step 7: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="d027f-104">*Det här steget är valfritt och gäller endast E5- och Advanced Compliance-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="d027f-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="d027f-106">Hantering av privilegierad åtkomst aktiveras genom att konfigurera principer som anger just-in-time-åtkomst för uppgiftsbaserade aktiviteter i office 365-klienten.</span><span class="sxs-lookup"><span data-stu-id="d027f-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant.</span></span> <span data-ttu-id="d027f-107">Det kan hjälpa till att skydda din organisation från överträdelser som kan använda befintliga privilegierade administratörskonton med stående åtkomst till känsliga data eller åtkomst till viktiga konfigurationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="d027f-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="d027f-108">Du kan till exempel konfigurera en princip för hantering av privilegierad åtkomst som kräver uttryckligt godkännande för åtkomst till och ändring av inställningar för organisationspostlådan i office 365-klienten.</span><span class="sxs-lookup"><span data-stu-id="d027f-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="d027f-109">I det här steget aktiverar du hantering av privilegierad åtkomst i office 365-klienten och konfigurerar principer för privilegierad åtkomst som ger ytterligare säkerhet för uppgiftsbaserad åtkomst till Office 365-data och konfigurationsinställningar för din organisation.</span><span class="sxs-lookup"><span data-stu-id="d027f-109">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization.</span></span> <span data-ttu-id="d027f-110">Det finns tre grundläggande steg för att komma igång med privilegierad åtkomst i office 365-organisationen:</span><span class="sxs-lookup"><span data-stu-id="d027f-110">There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="d027f-111">Skapa en godkännargrupp</span><span class="sxs-lookup"><span data-stu-id="d027f-111">Creating an approver's group</span></span>
- <span data-ttu-id="d027f-112">Aktivera privilegierad åtkomst</span><span class="sxs-lookup"><span data-stu-id="d027f-112">Enabling privileged access</span></span>
- <span data-ttu-id="d027f-113">Skapa principer för godkännande</span><span class="sxs-lookup"><span data-stu-id="d027f-113">Creating approval policies</span></span>

<span data-ttu-id="d027f-114">En konfigurerad, privilegierad åtkomsthantering gör det möjligt för din organisation att arbeta med noll stående privilegier och tillhandahålla ett lager av försvar mot sårbarheter som uppstår på grund av sådan stående administrativ åtkomst.</span><span class="sxs-lookup"><span data-stu-id="d027f-114">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> <span data-ttu-id="d027f-115">Privilegierad åtkomst kräver godkännanden för att utföra en aktivitet som har en associerad godkännandeprincip definierad.</span><span class="sxs-lookup"><span data-stu-id="d027f-115">Privileged access requires approvals for executing any task that has an associated approval policy defined.</span></span> <span data-ttu-id="d027f-116">Användare som behöver utföra uppgifter som ingår i en godkännandeprincip måste begära och beviljas åtkomstgodkännande för att ha behörigheter som krävs för att utföra uppgifter som definierats i principen.</span><span class="sxs-lookup"><span data-stu-id="d027f-116">Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="d027f-117">Om du vill aktivera hantering av privilegierad åtkomst för Office 365 läser du [avsnittet Konfigurera privilegierad åtkomsthantering i Office 365.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)</span><span class="sxs-lookup"><span data-stu-id="d027f-117">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="d027f-118">Mer information finns [i avsnittet Privilegierad åtkomsthantering i Office 365.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)</span><span class="sxs-lookup"><span data-stu-id="d027f-118">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Testlabbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="d027f-120">Mer om du vill öva den här konfigurationen i en testlabbmiljö finns i [testlabbguiden för hantering av privilegierad åtkomst](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d027f-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="d027f-121">Som en interimskontrollpunkt, se [exitkriterier som](infoprotect-exit-criteria.md#crit-infoprotect-step7) motsvarar detta steg.</span><span class="sxs-lookup"><span data-stu-id="d027f-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="d027f-122">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d027f-122">Next Step</span></span>

[<span data-ttu-id="d027f-123">Exitkriterier för informationsskyddsinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="d027f-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
