---
title: Konfigurera principer för villkorlig åtkomst för Microsoft 365 kampanjer
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du konfigurerar principer för villkorlig åtkomst för Microsoft 365 kampanjer.
ms.openlocfilehash: 7d8e1f16019d151478aae57b1593b0e0758e5b19
ms.sourcegitcommit: 7e46db0b35c188ee6a7b40ab3eb2d76ff6c101c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2019
ms.locfileid: "35086405"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="cd343-103">Konfigurera principer för villkorad tillgång</span><span class="sxs-lookup"><span data-stu-id="cd343-103">Set up conditional access policies</span></span>

<span data-ttu-id="cd343-104">Principer för [villkorad tillgång](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) lägga substancial ytterligare säkerhet.</span><span class="sxs-lookup"><span data-stu-id="cd343-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substancial additional security.</span></span> <span data-ttu-id="cd343-105">Microsoft tillhandahåller en uppsättning principer för villkorad tillgång originalplan som rekommenderas för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="cd343-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="cd343-106">Principer för originalplan är en uppsättning fördefinierade principer som skyddar organisationer mot många vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="cd343-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="cd343-107">Vanliga angrepp kan innehålla lösenord spray, replay och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="cd343-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="cd343-108">Dessa principer kräver att administratörer och användare att ange en andra form av autentisering (kallas flerfunktionsautentisering eller MFA) när vissa villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="cd343-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="cd343-109">Om en användare loggar in från ett annat land kan logga in kan betraktas som riskfyllda och användaren måste ange en ytterligare form av autentisering.</span><span class="sxs-lookup"><span data-stu-id="cd343-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="cd343-110">Originalplan principer är för närvarande följande:</span><span class="sxs-lookup"><span data-stu-id="cd343-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="cd343-111">**Kräver MFA för administratörer** , kräver autentisering på flera plan för de mest Privilegierade administratörsroller inklusive global administratör.</span><span class="sxs-lookup"><span data-stu-id="cd343-111">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="cd343-112">**Skydd för slutanvändaren** – kräver autentisering på flera plan för användarna endast när en inloggning är riskabelt.</span><span class="sxs-lookup"><span data-stu-id="cd343-112">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="cd343-113">**Blockera äldre autentisering** – äldre klientprogram och vissa nya program som inte använder nyare, säkrare autentiseringsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="cd343-113">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="cd343-114">Dessa äldre apps kan kringgå principer för villkorad tillgång och få otillåten åtkomst till din miljö.</span><span class="sxs-lookup"><span data-stu-id="cd343-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="cd343-115">Den här principen blockerar från klienter som inte stöder villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="cd343-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="cd343-116">**Kräver MFA för servicehantering** , kräver autentisering på flera plan för tillgång till verktyg, inklusive Azure portal (där du konfigurerar principer för originalplanen).</span><span class="sxs-lookup"><span data-stu-id="cd343-116">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="cd343-117">Microsoft rekommenderar att du aktiverar alla dessa principer för originalplan.</span><span class="sxs-lookup"><span data-stu-id="cd343-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="cd343-118">När dessa principer är aktiverat kan uppmanas administratörer och användare att registrera för Azure Multii-faktor autentisering.</span><span class="sxs-lookup"><span data-stu-id="cd343-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="cd343-119">Mer information om dessa principer finns i [Vad är baslinjen principer](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="cd343-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="cd343-120">Ställ in policyer för baslinje</span><span class="sxs-lookup"><span data-stu-id="cd343-120">Set up baseline policies</span></span>

1. <span data-ttu-id="cd343-121">Gå till [Azure portal](https://portal.azure.com)och navigera sedan till **Azure Active Directory** \> **Villkorad tillgång**.</span><span class="sxs-lookup"><span data-stu-id="cd343-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="cd343-122">Principer för originalplan visas på sidan.</span><span class="sxs-lookup"><span data-stu-id="cd343-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="cd343-123">![Sida med originalplan principer för villkorad tillgång.](media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="cd343-123">![Page that lists baseline policies for conditional access.](media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="cd343-124">Följande specifika instruktioner för varje princip finns:</span><span class="sxs-lookup"><span data-stu-id="cd343-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="cd343-125">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="cd343-125">Require MFA for admins</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="cd343-126">Reequire MFA för användare</span><span class="sxs-lookup"><span data-stu-id="cd343-126">Reequire MFA for users</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="cd343-127">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="cd343-127">Block legacy authentication</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="cd343-128">Kräv MFA för servicehantering</span><span class="sxs-lookup"><span data-stu-id="cd343-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="cd343-129">Du kan ställa in många ytterligare principer som kräver godkända klientprogram.</span><span class="sxs-lookup"><span data-stu-id="cd343-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="cd343-130">Finns i [Dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/) för mer information.</span><span class="sxs-lookup"><span data-stu-id="cd343-130">See the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/) for more information.</span></span>