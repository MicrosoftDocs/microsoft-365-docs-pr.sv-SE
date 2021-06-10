---
title: Läs mer om standardprincipen för dataförlustskydd i Microsoft Teams (förhandsversion)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Läs mer om standardprincipen för skydd mot dataförlust i Microsoft Teams
ms.openlocfilehash: 0663c370373708009346d4f858729e17436f0f62
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52163000"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="d8b1d-103">Läs mer om standardprincipen för dataförlustskydd i Microsoft Teams (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="d8b1d-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="d8b1d-104">[Funktioner för skydd mot](dlp-learn-about-dlp.md) dataförlust har utökats så att de omfattar Microsoft Teams och kanalmeddelanden, inklusive meddelanden i privata kanaler.</span><span class="sxs-lookup"><span data-stu-id="d8b1d-104">[Data loss prevention](dlp-learn-about-dlp.md) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="d8b1d-105">Som en del av den här versionen skapade vi en standard-DLP-princip för första gången kunder till efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="d8b1d-105">As a part of this release, we created a default DLP policy for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="d8b1d-106">Gäller för</span><span class="sxs-lookup"><span data-stu-id="d8b1d-106">Applies to</span></span>

<span data-ttu-id="d8b1d-107">Alla klientorganisationar som är licensierade med en eller flera av licenserna nedan och har aktiva Teams användare</span><span class="sxs-lookup"><span data-stu-id="d8b1d-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="d8b1d-108">ME5</span><span class="sxs-lookup"><span data-stu-id="d8b1d-108">ME5,</span></span> 
- <span data-ttu-id="d8b1d-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="d8b1d-109">MA5,</span></span> 
- <span data-ttu-id="d8b1d-110">Efterlevnad i E5/A5</span><span class="sxs-lookup"><span data-stu-id="d8b1d-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="d8b1d-111">IP+G</span><span class="sxs-lookup"><span data-stu-id="d8b1d-111">IP+G,</span></span> 
- <span data-ttu-id="d8b1d-112">OE5</span><span class="sxs-lookup"><span data-stu-id="d8b1d-112">OE5,</span></span> 
- <span data-ttu-id="d8b1d-113">O365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="d8b1d-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="d8b1d-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="d8b1d-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="d8b1d-115">Vad innebär standardprincipen?</span><span class="sxs-lookup"><span data-stu-id="d8b1d-115">What does the default policy do?</span></span>

<span data-ttu-id="d8b1d-116">Med standardprincipen för DLP spårar du alla kreditkortsnummer som delas internt och externt i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d8b1d-116">The default DLP policy tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="d8b1d-117">Den här principen är som standardinställning för alla användare av klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="d8b1d-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="d8b1d-118">Inga principtips skapas för slutanvändarna, men en aviseringshändelse skapas och ett meddelande med låg allvarlighetsgrad utlöses för administratören (som läggs till i principen).</span><span class="sxs-lookup"><span data-stu-id="d8b1d-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="d8b1d-119">Administratören kan visa aktiviteterna och redigera policyinformationen genom att logga in på efterlevnadscentret.</span><span class="sxs-lookup"><span data-stu-id="d8b1d-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="d8b1d-120">Administratörer kan visa den här principen i [efterlevnadscentret >](https://compliance.microsoft.com/compliancesettings) sidan Principer för skydd mot dataförlust.</span><span class="sxs-lookup"><span data-stu-id="d8b1d-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="d8b1d-121">![DLP Teams standardprincip](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="d8b1d-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="d8b1d-122">Redigera eller ta bort standardprincipen</span><span class="sxs-lookup"><span data-stu-id="d8b1d-122">Edit or delete the default policy</span></span>

<span data-ttu-id="d8b1d-123">Om [du vill redigera standardprincipen för bättre prestanda eller ta bort den](create-test-tune-dlp-policy.md#tune-a-dlp-policy)använder du bara ett konto med behörigheter för **DLP-efterlevnadshantering.**</span><span class="sxs-lookup"><span data-stu-id="d8b1d-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="d8b1d-124">Mer information finns i [Behörigheter](create-test-tune-dlp-policy.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="d8b1d-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

