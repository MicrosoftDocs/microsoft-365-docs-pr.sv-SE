---
title: 'Steg 1: definiera säkerhets- och informationsskyddsnivåer'
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
description: Förstå och konfigurera säkerhets- och informationsskyddsnivåer för din organisation.
ms.openlocfilehash: 0fa3e9fa11070ea505752d781ecdd21b344c8222
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636970"
---
# <a name="step-1-define-security-and-information-protection-levels"></a><span data-ttu-id="0545e-103">Steg 1: definiera säkerhets- och informationsskyddsnivåer</span><span class="sxs-lookup"><span data-stu-id="0545e-103">Step 1: Define security and information protection levels</span></span>

<span data-ttu-id="0545e-104">*Det här steget är obligatoriskt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="0545e-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="0545e-106">I det här steget definierar du säkerhets- och skyddsnivåerna för din organisation.</span><span class="sxs-lookup"><span data-stu-id="0545e-106">In this step, you'll define the levels of security and protection for your organization.</span></span> <span data-ttu-id="0545e-107">Säljavdelningen kanske till exempel bara behöver låg säkerhetsnivå.</span><span class="sxs-lookup"><span data-stu-id="0545e-107">For example, your sales department might only require a low security level.</span></span> <span data-ttu-id="0545e-108">Men din forskningsavdelning och dess mycket värdefull intellektuella egendom kräver en hög säkerhetsnivå som krypterar filer och begränsar åtkomsten endast till forskningspersonalen.</span><span class="sxs-lookup"><span data-stu-id="0545e-108">However, your research department and its highly valuable intellectual property might require a high security level that encrypts files and limits access to only research staff.</span></span>

<span data-ttu-id="0545e-109">Även om du kan definiera dina egna säkerhetsnivåer och eventuellt redan har en del på plats, rekommenderar Microsoft att du utvecklar en plan för att använda minst tre olika säkerhetsnivåer som kan appliceras.</span><span class="sxs-lookup"><span data-stu-id="0545e-109">Although you can define your own security levels and might already have some in place, Microsoft recommends that you develop a plan to use at least three different levels of security and protection that can be applied.</span></span> <span data-ttu-id="0545e-110">Här är en lista som du kan använda för att komma igång:</span><span class="sxs-lookup"><span data-stu-id="0545e-110">Here is a list to get you started:</span></span> 

- <span data-ttu-id="0545e-111">**Grundläggande:** det här är en minimal standard för att skydda data och identiteter och enheter som har åtkomst till dina data.</span><span class="sxs-lookup"><span data-stu-id="0545e-111">**Baseline:** This is a minimum standard for protecting data and for the identities and devices that access your data.</span></span> <span data-ttu-id="0545e-112">Du kan följa grundläggande säkerhets- och skyddsrekommendationer för att ge ett starkt standardskydd som uppfyller behoven för många organisationer och deras avdelningar.</span><span class="sxs-lookup"><span data-stu-id="0545e-112">You can follow baseline security and protection recommendations to provide strong default protection that meets the needs of many organizations or their departments.</span></span>
- <span data-ttu-id="0545e-113">**Känslig:** det här är ytterligare skydd för en underuppsättning av dina data som måste skyddas mer än på grundläggande nivå.</span><span class="sxs-lookup"><span data-stu-id="0545e-113">**Sensitive:** This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="0545e-114">Du kan använda det här utökade skyddet för specifika datauppsättningar i Microsoft 365-miljön.</span><span class="sxs-lookup"><span data-stu-id="0545e-114">You can apply this increased protection to specific data sets in your Microsoft 365 environment.</span></span> <span data-ttu-id="0545e-115">Microsoft rekommenderar också att du använder den känsliga säkerhetsnivån för identiteter och enheter som har åtkomst till känslig data.</span><span class="sxs-lookup"><span data-stu-id="0545e-115">Microsoft also recommends applying the sensitive security level to identities and devices that access sensitive data.</span></span>
- <span data-ttu-id="0545e-116">**Högt reglerad:** Det här är den högsta skyddsnivån för organisationer som vanligtvis har en mycket liten mängd data som är mycket sekretessbelagda, som är intellektuella egendomar eller affärshemligheter eller data som måste följa strikta säkerhetsföreskrifter.</span><span class="sxs-lookup"><span data-stu-id="0545e-116">**Highly regulated:** This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations.</span></span> <span data-ttu-id="0545e-117">Microsoft 365 Enterprise har möjligheter att hjälpa organisationer att uppfylla de här höga säkerhetskraven, inklusive likvärdigt skydd för identiteter och enheter.</span><span class="sxs-lookup"><span data-stu-id="0545e-117">Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span>

<span data-ttu-id="0545e-118">Mer information finns i [Tre nivåer av säkerhet](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span><span class="sxs-lookup"><span data-stu-id="0545e-118">For more information, see [Three tiers of protection](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span></span>

<span data-ttu-id="0545e-119">Som en mellanliggande kontrollpunkt kan du se [avslutsvillkoren](infoprotect-exit-criteria.md#crit-infoprotect-step1) som motsvarar det här steget.</span><span class="sxs-lookup"><span data-stu-id="0545e-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="0545e-120">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0545e-120">Next step</span></span>

|||
|:-------|:-----|
|![Steg 2](../media/stepnumbers/Step2.png)|[<span data-ttu-id="0545e-122">Konfigurera klassificering för din miljö</span><span class="sxs-lookup"><span data-stu-id="0545e-122">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
