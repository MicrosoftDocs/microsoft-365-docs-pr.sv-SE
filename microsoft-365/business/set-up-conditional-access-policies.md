---
title: Ställ in principer för villkorlig åtkomst för Microsoft 365-kampanjer
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du ställer in principer för villkorlig åtkomst för Microsoft 365-kampanjer.
ms.openlocfilehash: aebdb733c2dd9a05947335ad4f151104d801568e
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2019
ms.locfileid: "38718838"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="dcf1a-103">Ställ in principer för villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="dcf1a-103">Set up conditional access policies</span></span>

<span data-ttu-id="dcf1a-104">Principer för [villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) lägga till betydande ytterligare säkerhet.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="dcf1a-105">Microsoft tillhandahåller en uppsättning principer för villkorlig åtkomst Vidbaslinjen som rekommenderas för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="dcf1a-106">Baslinje principer är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="dcf1a-107">Dessa vanliga attacker kan omfatta lösenord spray, Replay och phishing.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="dcf1a-108">Dessa principer kräver administratörer och användare att ange en andra form av autentisering (kallas multifaktorautentisering eller MFA) när vissa villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="dcf1a-109">Till exempel om en användare loggar in från ett annat land, kan inloggningen anses vara riskabelt och användaren måste tillhandahålla ytterligare en form av autentisering.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="dcf1a-110">För närvarande omfattar baslinje principer följande:</span><span class="sxs-lookup"><span data-stu-id="dcf1a-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="dcf1a-111">**Kräv MFA för administratörer** &ndash; kräver multifaktorautentisering för de mest privilegierade administratörsrollerna, inklusive global administratör.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="dcf1a-112">**användarskydd** &ndash; kräver multifaktorautentisering för användare endast när en inloggning är riskabelt.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="dcf1a-113">**Block äldre autentisering** &ndash; äldre klientappar och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="dcf1a-114">Dessa äldre appar kan kringgå principer för villkorlig åtkomst och få obehörig åtkomst till din miljö.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="dcf1a-115">Den här principen blockerar åtkomsten från klienter som inte stöder villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="dcf1a-116">**Kräv MFA för Service Management** &ndash; kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure Portal (där du konfigurerar principer för baslinje).</span><span class="sxs-lookup"><span data-stu-id="dcf1a-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="dcf1a-117">Microsoft rekommenderar att du aktiverar alla dessa baslinje principer.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="dcf1a-118">När dessa principer har aktiverats uppmanas administratörer och användare att registrera för Azure Multii-Factor-autentisering.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="dcf1a-119">Mer information om dessa principer finns i [Vad är baslinje principer](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="dcf1a-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="dcf1a-120">Ställ in principer för originalplan</span><span class="sxs-lookup"><span data-stu-id="dcf1a-120">Set up baseline policies</span></span>

1. <span data-ttu-id="dcf1a-121">Gå till [Azure-portalen](https://portal.azure.com), och sedan gå **till Azure Active Directory** \> **villkorlig åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="dcf1a-122">Baslinje principerna visas på sidan.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="dcf1a-123">![Sida som listar baslinje principer för villkorlig åtkomst.](media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="dcf1a-123">![Page that lists baseline policies for conditional access.](media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="dcf1a-124">Se följande specifika instruktioner för varje princip:</span><span class="sxs-lookup"><span data-stu-id="dcf1a-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="dcf1a-125">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="dcf1a-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="dcf1a-126">Kräv MFA för användare</span><span class="sxs-lookup"><span data-stu-id="dcf1a-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="dcf1a-127">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="dcf1a-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="dcf1a-128">Kräv MFA för servicehantering</span><span class="sxs-lookup"><span data-stu-id="dcf1a-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="dcf1a-129">Du kan ställa in många ytterligare principer, till exempel kräver godkända klientappar.</span><span class="sxs-lookup"><span data-stu-id="dcf1a-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="dcf1a-130">Mer information finns i dokumentationen för [villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="dcf1a-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
