---
title: 'Steg 4: Konfigurera Windows-informationsskydd'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Förstå och distribuera Windows informationsskydd i Microsoft 365.
ms.openlocfilehash: 655ff33c3fd1bba822937618d801db76b7881977
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805639"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="23515-103">Steg 4: Konfigurera Windows-informationsskydd</span><span class="sxs-lookup"><span data-stu-id="23515-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="23515-104">*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="23515-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="23515-106">Med fler personliga enheter som används för arbete finns det en ökad risk för att appar och enheter ska läcka privata organisationsdata.</span><span class="sxs-lookup"><span data-stu-id="23515-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="23515-107">En anställd skickar exempelvis av misstag en bild av en marknadsföringsplan för en kommande produkt till en social mediefil eller sparar en fil som innehåller känslig information i molnet.</span><span class="sxs-lookup"><span data-stu-id="23515-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="23515-108">Windows information Protection (WIP) hjälper till att skydda mot den här typen av dataläckage på Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="23515-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="23515-109">Mer information finns i [Skydda ditt företags data med hjälp av WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="23515-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="23515-110">I Microsoft 365 Enterprise är WIP en kombination av Windows 10 Enterprise och Microsoft Intune, som ingår i prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="23515-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="23515-111">Så här distribuerar du WIP i din organisation med Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="23515-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="23515-112">Registrera dina Windows-enheter i Intune.</span><span class="sxs-lookup"><span data-stu-id="23515-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="23515-113">Du bör ha gjort detta i [steg 5: Hantering av mobila enhet](mobility-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="23515-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="23515-114">Skapa en [Intune-princip för WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span><span class="sxs-lookup"><span data-stu-id="23515-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="23515-115">Kontrollera att du har fyllt i listan med skyddade appar.</span><span class="sxs-lookup"><span data-stu-id="23515-115">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="23515-116">Välj nivån för ditt WIP-skydd.</span><span class="sxs-lookup"><span data-stu-id="23515-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="23515-117">Du kan också använda WIP med [Konfigurationshanteraren för Microsoft Endpoint](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span><span class="sxs-lookup"><span data-stu-id="23515-117">You can also use WIP with [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="23515-118">Mer information finns i [metodtips för WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).</span><span class="sxs-lookup"><span data-stu-id="23515-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="23515-119">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](infoprotect-exit-criteria.md#crit-infoprotect-step4) som motsvarar det här steget.</span><span class="sxs-lookup"><span data-stu-id="23515-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="23515-120">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="23515-120">Next step</span></span>

|||
|:-------|:-----|
|![Steg 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="23515-122">Konfigurera dataförlustskydd i Office 365</span><span class="sxs-lookup"><span data-stu-id="23515-122">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


