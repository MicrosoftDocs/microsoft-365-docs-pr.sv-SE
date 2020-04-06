---
title: Konfigurera principer för villkorlig åtkomst för Microsoft 365-kampanjer
f1.keywords:
- NOCSH
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du ställer in principer för villkorlig åtkomst för Microsoft 365-kampanjer för att lägga till betydande ytterligare säkerhet.
ms.openlocfilehash: 26fadecc69486d7931dac069d8f53061592f397f
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153775"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="390d8-103">Ställ in principer för villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="390d8-103">Set up Conditional Access policies</span></span>

<span data-ttu-id="390d8-104">[Principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) ger betydande ytterligare säkerhet.</span><span class="sxs-lookup"><span data-stu-id="390d8-104">[Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="390d8-105">Microsoft tillhandahåller en uppsättning grundläggande principer för villkorlig åtkomst som rekommenderas för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="390d8-105">Microsoft provides a set of baseline Conditional Access policies that are recommended for all customers.</span></span> <span data-ttu-id="390d8-106">Baslinjeprinciper är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="390d8-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="390d8-107">Dessa vanliga attacker kan omfatta lösenordsspray, uppspelning och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="390d8-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="390d8-108">Dessa principer kräver att administratörer och användare anger en andra form av autentisering (kallas multifaktorautentisering eller MFA) när vissa villkor är uppfyllda.</span><span class="sxs-lookup"><span data-stu-id="390d8-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="390d8-109">Om en användare till exempel loggar in från ett annat land kan inloggningen anses vara riskabel och användaren måste tillhandahålla ytterligare en form av autentisering.</span><span class="sxs-lookup"><span data-stu-id="390d8-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="390d8-110">För närvarande omfattar baslinjeprinciper följande:</span><span class="sxs-lookup"><span data-stu-id="390d8-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="390d8-111">**Kräv MFA för administratörer** &ndash; Kräver multifaktorautentisering för de mest privilegierade administratörsrollerna, inklusive global administratör.</span><span class="sxs-lookup"><span data-stu-id="390d8-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="390d8-112">**Skydd för slutanvändare** &ndash; kräver multifaktorautentisering endast för användare när en inloggning är riskabel.</span><span class="sxs-lookup"><span data-stu-id="390d8-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="390d8-113">**Blockera äldre autentisering** &ndash; Äldre klientappar och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="390d8-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="390d8-114">Dessa äldre appar kan kringgå principer för villkorlig åtkomst och få obehörig åtkomst till din miljö.</span><span class="sxs-lookup"><span data-stu-id="390d8-114">These older apps can bypass Conditional Access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="390d8-115">Den här principen blockerar åtkomst från klienter som inte stöder villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="390d8-115">This policy blocks access from clients that don't support Conditional Access.</span></span> 
- <span data-ttu-id="390d8-116">**Kräv MFA för tjänsthantering** &ndash; Kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portal (där du konfigurerar originalprinciper).</span><span class="sxs-lookup"><span data-stu-id="390d8-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="390d8-117">Microsoft rekommenderar att du aktiverar alla dessa grundläggande principer.</span><span class="sxs-lookup"><span data-stu-id="390d8-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="390d8-118">När dessa principer har aktiverats uppmanas administratörer och användare att registrera sig för Azure Multii-Factor-autentisering.</span><span class="sxs-lookup"><span data-stu-id="390d8-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="390d8-119">Mer information om dessa principer finns i [Vad är baslinjeprinciper?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="390d8-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="390d8-120">Ställ in originalprinciper</span><span class="sxs-lookup"><span data-stu-id="390d8-120">Set up baseline policies</span></span>

1. <span data-ttu-id="390d8-121">Gå till [Azure-portalen](https://portal.azure.com)och navigera sedan till **Azure Active Directory** \> **Villkorlig åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="390d8-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="390d8-122">Originalprinciperna visas på sidan.</span><span class="sxs-lookup"><span data-stu-id="390d8-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="390d8-123">![Sida som visar originalprinciper för villkorlig åtkomst.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="390d8-123">![Page that lists baseline policies for Conditional Access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="390d8-124">Se följande specifika instruktioner för varje policy:</span><span class="sxs-lookup"><span data-stu-id="390d8-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="390d8-125">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="390d8-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="390d8-126">Kräv MFA för användare</span><span class="sxs-lookup"><span data-stu-id="390d8-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="390d8-127">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="390d8-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="390d8-128">Kräv MFA för tjänsthantering</span><span class="sxs-lookup"><span data-stu-id="390d8-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="390d8-129">Du kan ställa in många ytterligare principer, till exempel kräver godkända klientappar.</span><span class="sxs-lookup"><span data-stu-id="390d8-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="390d8-130">Mer information finns i [dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="390d8-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
