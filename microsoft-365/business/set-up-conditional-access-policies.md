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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du ställer in principer för villkorlig åtkomst för Microsoft 365-kampanjer för att lägga till betydande ytterligare säkerhet.
ms.openlocfilehash: 58ee760877ee2fd7e53ef9463242657ab66a2b6e
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470656"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="f7fad-103">Ställ in principer för villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="f7fad-103">Set up conditional access policies</span></span>

<span data-ttu-id="f7fad-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="f7fad-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="f7fad-105">[Principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) ger betydande ytterligare säkerhet.</span><span class="sxs-lookup"><span data-stu-id="f7fad-105">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="f7fad-106">Microsoft tillhandahåller en uppsättning principer för grundläggande villkorlig åtkomst som rekommenderas för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="f7fad-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="f7fad-107">Baslinjeprinciper är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="f7fad-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="f7fad-108">Dessa vanliga attacker kan omfatta lösenordsspray, uppspelning och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f7fad-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="f7fad-109">Dessa principer kräver att administratörer och användare anger en andra form av autentisering (kallas multifaktorautentisering eller MFA) när vissa villkor är uppfyllda.</span><span class="sxs-lookup"><span data-stu-id="f7fad-109">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="f7fad-110">Om en användare till exempel loggar in från ett annat land kan inloggningen anses vara riskabel och användaren måste tillhandahålla ytterligare en form av autentisering.</span><span class="sxs-lookup"><span data-stu-id="f7fad-110">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="f7fad-111">För närvarande omfattar baslinjeprinciper följande:</span><span class="sxs-lookup"><span data-stu-id="f7fad-111">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="f7fad-112">**Kräv MFA för administratörer** &ndash; Kräver multifaktorautentisering för de mest privilegierade administratörsrollerna, inklusive den globala administratören.</span><span class="sxs-lookup"><span data-stu-id="f7fad-112">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="f7fad-113">**Skydd för** &ndash; slutanvändare Kräver multifaktorautentisering endast för användare när en inloggning är riskabel.</span><span class="sxs-lookup"><span data-stu-id="f7fad-113">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="f7fad-114">**Blockera äldre autentisering** &ndash; Äldre klientappar och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="f7fad-114">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="f7fad-115">Dessa äldre appar kan kringgå principer för villkorlig åtkomst och få obehörig åtkomst till din miljö.</span><span class="sxs-lookup"><span data-stu-id="f7fad-115">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="f7fad-116">Den här principen blockerar åtkomst från klienter som inte stöder villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="f7fad-116">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="f7fad-117">**Kräv MFA för servicehantering** &ndash; Kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portal (där du konfigurerar originalprinciper).</span><span class="sxs-lookup"><span data-stu-id="f7fad-117">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="f7fad-118">Microsoft rekommenderar att du aktiverar alla dessa grundläggande principer.</span><span class="sxs-lookup"><span data-stu-id="f7fad-118">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="f7fad-119">När dessa principer har aktiverats uppmanas administratörer och användare att registrera sig för Azure Multii-Factor-autentisering.</span><span class="sxs-lookup"><span data-stu-id="f7fad-119">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="f7fad-120">Mer information om dessa principer finns i [Vad är baslinjeprinciper?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="f7fad-120">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="f7fad-121">Ställ in originalprinciper</span><span class="sxs-lookup"><span data-stu-id="f7fad-121">Set up baseline policies</span></span>

1. <span data-ttu-id="f7fad-122">Gå till [Azure-portalen](https://portal.azure.com)och navigera sedan till **Azure Active Directory** Villkorlig \> **åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="f7fad-122">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="f7fad-123">Originalprinciperna visas på sidan.</span><span class="sxs-lookup"><span data-stu-id="f7fad-123">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="f7fad-124">![Sida som visar baslinjeprinciper för villkorlig åtkomst.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="f7fad-124">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="f7fad-125">Se följande specifika instruktioner för varje policy:</span><span class="sxs-lookup"><span data-stu-id="f7fad-125">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="f7fad-126">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="f7fad-126">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="f7fad-127">Kräv MFA för användare</span><span class="sxs-lookup"><span data-stu-id="f7fad-127">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="f7fad-128">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="f7fad-128">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="f7fad-129">Kräv MFA för tjänsthantering</span><span class="sxs-lookup"><span data-stu-id="f7fad-129">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="f7fad-130">Du kan ställa in många ytterligare principer, till exempel kräver godkända klientappar.</span><span class="sxs-lookup"><span data-stu-id="f7fad-130">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="f7fad-131">Mer information finns i [dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="f7fad-131">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
