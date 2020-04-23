---
title: 'Fas 6: Informationsskydd'
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
description: Stegen för att distribuera infrastrukturen för informationsskydd för Microsoft 365 Enterprise.
ms.openlocfilehash: 0e6fdf1a9c63200bfb57fc9f833515553c1609f4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631627"
---
# <a name="phase-6-information-protection"></a><span data-ttu-id="65d2c-103">Fas 6: Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="65d2c-103">Phase 6: Information protection</span></span>

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon.png)

<span data-ttu-id="65d2c-105">Informationsskydd är en uppsättning principer och tekniker som definierar hur du överför, lagrar och bearbetar känslig information.</span><span class="sxs-lookup"><span data-stu-id="65d2c-105">Information protection is a set of policies and technologies that define how you transmit, store, and process sensitive information.</span></span> <span data-ttu-id="65d2c-106">I fas 6 går du igenom inställningar och funktioner för informationsskydd i Microsoft 365 Enterprise som hjälper dig att skydda data för molnbaserade arbetsbelastningar och scenarier.</span><span class="sxs-lookup"><span data-stu-id="65d2c-106">In Phase 6, you step through information protection settings and features of Microsoft 365 Enterprise that help you secure data for your cloud-based workloads and scenarios.</span></span>

>[!Note]
><span data-ttu-id="65d2c-107">Om du redan har distribuerat informationsskydd går du till [avslutsvillkoren](infoprotect-exit-criteria.md) i den här fasen för att kontrollera att det uppfyller kraven och valfria villkor för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="65d2c-107">If you already have already deployed information protection, please see the [exit criteria](infoprotect-exit-criteria.md) for this phase to make sure that it meets the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-information-protection-infrastructure"></a><span data-ttu-id="65d2c-108">Planera och distribuera din infrastruktur för informationsskydd för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="65d2c-108">Plan and deploy your Microsoft 365 Enterprise information protection infrastructure</span></span> 

<span data-ttu-id="65d2c-109">Det är viktigt att arbeta med dina team för lag- och regelefterlevnad om din organisation behöver uppfylla standarder som HIPPA, CJIS eller GDPR.</span><span class="sxs-lookup"><span data-stu-id="65d2c-109">It’s important to work with your legal and compliance teams to determine if your organization needs to meet compliance standards such as HIPPA, CJIS, or GDPR.</span></span> <span data-ttu-id="65d2c-110">Du bör även arbeta med din säkerhetsgrupp och fastställa målen för informationsskyddet i din organisation och för avdelningar eller grupper som kräver ytterligare säkerhet.</span><span class="sxs-lookup"><span data-stu-id="65d2c-110">You should also work with your security group to determine the objectives for information protection for your organization and for departments or groups that require additional security.</span></span>

<span data-ttu-id="65d2c-111">Använd sedan följande steg för att bygga ut informationsskydd för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="65d2c-111">Next, use the following steps to build out information protection for Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
|![Steg 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="65d2c-113">Definiera säkerhets- och informationsskyddsnivåer</span><span class="sxs-lookup"><span data-stu-id="65d2c-113">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|
|![Steg 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="65d2c-115">Konfigurera klassificering för din miljö</span><span class="sxs-lookup"><span data-stu-id="65d2c-115">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
|![Steg 3](../media/stepnumbers/Step3.png)|[<span data-ttu-id="65d2c-117">Konfigurera ökad säkerhet för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65d2c-117">Configure increased security for Microsoft 365</span></span>](infoprotect-configure-increased-security-office-365.md)|
|![Steg 4](../media/stepnumbers/Step4.png)|[<span data-ttu-id="65d2c-119">Konfigurera Windows informationsskydd</span><span class="sxs-lookup"><span data-stu-id="65d2c-119">Configure Windows Information Protection</span></span>](infoprotect-deploy-windows-information-protection.md)|
|![Steg 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="65d2c-121">Konfigurera dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="65d2c-121">Configure Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|
|![Steg 6](../media/stepnumbers/Step6.png)|[<span data-ttu-id="65d2c-123">Konfigurera e-postkryptering</span><span class="sxs-lookup"><span data-stu-id="65d2c-123">Configure email encryption</span></span>](infoprotect-email-encryption.md)|
|![Steg 7](../media/stepnumbers/Step7.png)|[<span data-ttu-id="65d2c-125">Konfigurera Privileged Access Management i Office 365</span><span class="sxs-lookup"><span data-stu-id="65d2c-125">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
|||

<span data-ttu-id="65d2c-126">När du har utfört de här stegen går du till [avslutsvillkoret](infoprotect-exit-criteria.md) i den här fasen för att säkerställa att du uppfyller kraven och valfria villkor för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="65d2c-126">When you've completed these steps, go to the [exit criteria](infoprotect-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="65d2c-127">Hur Microsoft använder Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="65d2c-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="65d2c-128">Lär dig hur IT-experter på Microsoft använder [Azure Information Protection och skyddar data](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span><span class="sxs-lookup"><span data-stu-id="65d2c-128">Learn how IT experts at Microsoft use [Azure Information Protection and safeguard data](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR9).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="65d2c-129">Hur Contoso använder Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="65d2c-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="65d2c-130">Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [implementerade informationsskydd](contoso-info-protect.md) med Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="65d2c-130">See how the Contoso Corporation, a fictional but representative multi-national business, [implemented information protection](contoso-info-protect.md) with Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="65d2c-132">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="65d2c-132">Next step</span></span>

|||
|:-------|:-----|
|![Steg 1](../media/stepnumbers/Step1.png)|[<span data-ttu-id="65d2c-134">Definiera säkerhets- och informationsskyddsnivåer</span><span class="sxs-lookup"><span data-stu-id="65d2c-134">Define security and information protection levels</span></span>](infoprotect-define-sec-infoprotect-levels.md)|

