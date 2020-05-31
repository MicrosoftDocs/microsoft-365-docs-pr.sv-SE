---
title: 'Fas 2: Identitet'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Steg för att distribuera din identitets infrastruktur för Microsoft 365 Enterprise.
ms.openlocfilehash: 6f237f779df16f2a2a03eab29af78a89c5f7a5ae
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371424"
---
# <a name="phase-2-identity"></a><span data-ttu-id="49d38-103">Fas 2: Identitet</span><span class="sxs-lookup"><span data-stu-id="49d38-103">Phase 2: Identity</span></span>

![Fas 2: Identitet](../media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="49d38-105">I Microsoft 365 Enterprise banar en välplanerad och körd identitetsinfrastruktur vägen för bättre säkerhet och åtkomst till dina produktivitetsarbetsbelastningar och deras data endast med autentiserade användare och enheter.</span><span class="sxs-lookup"><span data-stu-id="49d38-105">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="49d38-106">I den här videon finns en översikt över identitetsmodeller och autentisering för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="49d38-106">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="49d38-107"><p> </p></span><span class="sxs-lookup"><span data-stu-id="49d38-107"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="49d38-108">Om du redan har distribuerat en identitetsinfrastruktur läser du [villkoren för identitetsavslutning](identity-exit-criteria.md) för att kontrollera att du uppfyller kraven och valfria villkor för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="49d38-108">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="49d38-109">För de olika funktionerna i varje Microsoft 365 Enterprise-abonnemang finns rollerna i Azure Active Directory (Azure AD), lokala och molnbaserade komponenter samt de vanligaste autentiseringarna i [Identitetsinfrastruktur (affisch)](../media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="49d38-109">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](../media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="49d38-110">[![Identitetsinfrastruktur (affisch)](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="49d38-110">[![The Identity Infrastructure poster](../media/identity-infrastructure/m365e-identity-arch-poster.png)](../media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="49d38-111">Med den här affischen på två sidor kan du snabbt förstärka identitetskoncept och konfigurationer för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="49d38-111">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="49d38-112">Du kan också [ladda ner denna affisch](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/identity-infrastructure/M365E-ID-Infra.pdf) och skriva ut den i formaten Letter, Legal och tabloid (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="49d38-112">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="49d38-113">Planera och distribuera din identitetsinfrastruktur för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="49d38-113">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="49d38-114">Använd följande steg för att planera och distribuera din nya identitetsinfrastruktur i molnet.</span><span class="sxs-lookup"><span data-stu-id="49d38-114">Use the following steps to plan and deploy your new identity infrastructure in the cloud.</span></span> <span data-ttu-id="49d38-115">Du kan också använda de här stegen för att anpassa din befintliga lokala eller hybrididentitetsinfrastruktur för att fungera med Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="49d38-115">You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![Steg 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="49d38-117">Skapa och skydda dina globala administratörskonton</span><span class="sxs-lookup"><span data-stu-id="49d38-117">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![Steg 2](../media/stepnumbers/Step2.png)| [<span data-ttu-id="49d38-119">Skydda dina lösenord</span><span class="sxs-lookup"><span data-stu-id="49d38-119">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![Steg 3](../media/stepnumbers/Step3.png)| [<span data-ttu-id="49d38-121">Skydda och hantera användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="49d38-121">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![Steg 4](../media/stepnumbers/Step4.png)| [<span data-ttu-id="49d38-123">Lägga till användarkonton</span><span class="sxs-lookup"><span data-stu-id="49d38-123">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![Steg 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="49d38-125">Använda grupper för hantering</span><span class="sxs-lookup"><span data-stu-id="49d38-125">Use groups for management</span></span>](identity-use-group-management.md) |
|![Steg 6](../media/stepnumbers/Step6.png)| [<span data-ttu-id="49d38-127">Konfigurera identitetsstyrning</span><span class="sxs-lookup"><span data-stu-id="49d38-127">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="49d38-128">När du har utfört de här stegen går du till [avslutsvillkoret](identity-exit-criteria.md) i den här fasen för att säkerställa att du uppfyller kraven och valfria villkor för Microsoft 365 Enterprise-identitet.</span><span class="sxs-lookup"><span data-stu-id="49d38-128">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise identity.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="49d38-129">Rekommendationer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="49d38-129">Identity and device access recommendations</span></span>

<span data-ttu-id="49d38-130">Microsoft tillhandahåller en uppsättning rekommendationer för [identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) för att säkerställa en säker och produktiv arbetsstyrka.</span><span class="sxs-lookup"><span data-stu-id="49d38-130">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="49d38-131">Använd rekommendationer och inställningar för identitet i följande artiklar tillsammans med stegen i den här fasen:</span><span class="sxs-lookup"><span data-stu-id="49d38-131">For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="49d38-132">Krav</span><span class="sxs-lookup"><span data-stu-id="49d38-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="49d38-133">Vanliga principer för identitets- och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="49d38-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="49d38-134">Så här används Microsoft 365 Enterprise på Microsoft</span><span class="sxs-lookup"><span data-stu-id="49d38-134">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="49d38-135">Lär dig hur IT-experter på Microsoft [hanterar identiteter och säker åtkomst](https://www.microsoft.com/sv-SE/itshowcase/managing-user-identities-and-secure-access-at-microsoft).</span><span class="sxs-lookup"><span data-stu-id="49d38-135">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/sv-SE/itshowcase/managing-user-identities-and-secure-access-at-microsoft).</span></span>

>[!Note]
><span data-ttu-id="49d38-136">Den här IT-showcaseresurs är endast tillgänglig på engelska.</span><span class="sxs-lookup"><span data-stu-id="49d38-136">This IT Showcase resource is only available in English.</span></span>
>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="49d38-137">Så här använder Contoso Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="49d38-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="49d38-138">Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [distribuerade en hybrididentitetsinfrastruktur](contoso-identity.md) för Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="49d38-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="49d38-140">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="49d38-140">Next step</span></span>

|||
|:-------|:-----|
|![Steg 1](../media/stepnumbers/Step1.png)| [<span data-ttu-id="49d38-142">Skapa och skydda dina globala administratörskonton</span><span class="sxs-lookup"><span data-stu-id="49d38-142">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
