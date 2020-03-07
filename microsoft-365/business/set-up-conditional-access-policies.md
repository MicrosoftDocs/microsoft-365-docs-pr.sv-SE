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
description: Läs om hur du ställer in principer för villkorlig åtkomst för Microsoft 365-kampanjer för att lägga till ytterligare säkerhet.
ms.openlocfilehash: eda65e335df2a7c2c443d7095f7b35b5c1cf27e4
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561229"
---
# <a name="set-up-conditional-access-policies"></a><span data-ttu-id="c96c0-103">Konfigurera principer för villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="c96c0-103">Set up conditional access policies</span></span>

<span data-ttu-id="c96c0-104">[Principer](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) för villkorlig åtkomst ger betydande ytterligare säkerhet.</span><span class="sxs-lookup"><span data-stu-id="c96c0-104">[Conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies add substantial additional security.</span></span> <span data-ttu-id="c96c0-105">Microsoft tillhandahåller en uppsättning principer för villkorlig åtkomst vid originalplan som rekommenderas för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="c96c0-105">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="c96c0-106">Originalprinciper är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="c96c0-106">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="c96c0-107">Dessa vanliga attacker kan omfatta lösenordsspray, repris och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c96c0-107">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="c96c0-108">Dessa principer kräver att administratörer och användare anger en andra form av autentisering (kallas multifaktorautentisering eller MFA) när vissa villkor är uppfyllda.</span><span class="sxs-lookup"><span data-stu-id="c96c0-108">These policies require admins and users to enter a second form of authentication (called multifactor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="c96c0-109">Om en användare till exempel loggar in från ett annat land kan inloggning betraktas som riskabel och användaren måste tillhandahålla ytterligare en form av autentisering.</span><span class="sxs-lookup"><span data-stu-id="c96c0-109">For example, if a user is signing in from a different country, the sign-in might be considered risky and the user must provide an additional form of authentication.</span></span> 

<span data-ttu-id="c96c0-110">För närvarande innehåller baslinjeprinciper följande:</span><span class="sxs-lookup"><span data-stu-id="c96c0-110">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="c96c0-111">**Kräv MFA för administratörer** &ndash; Kräver multifaktorautentisering för de mest privilegierade administratörsrollerna, inklusive global administratör.</span><span class="sxs-lookup"><span data-stu-id="c96c0-111">**Require MFA for admins** &ndash; Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
- <span data-ttu-id="c96c0-112">**Slutanvändarskydd** &ndash; Kräver multifaktorautentisering endast för användare när en inloggning är riskabel.</span><span class="sxs-lookup"><span data-stu-id="c96c0-112">**End user protection** &ndash; Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="c96c0-113">**Blockera äldre autentisering** &ndash; Äldre klientappar och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="c96c0-113">**Block legacy authentication** &ndash; Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="c96c0-114">Dessa äldre appar kan kringgå principer för villkorlig åtkomst och få obehörig åtkomst till din miljö.</span><span class="sxs-lookup"><span data-stu-id="c96c0-114">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="c96c0-115">Den här principen blockerar åtkomst från klienter som inte stöder villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="c96c0-115">This policy blocks access from clients that don't support conditional access.</span></span> 
- <span data-ttu-id="c96c0-116">**Kräv MFA för servicehantering** &ndash; Kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portal (där du konfigurerar baslinjeprinciper).</span><span class="sxs-lookup"><span data-stu-id="c96c0-116">**Require MFA for Service Management** &ndash; Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="c96c0-117">Microsoft rekommenderar att du aktiverar alla dessa baslinjeprinciper.</span><span class="sxs-lookup"><span data-stu-id="c96c0-117">Microsoft recommends you enable all of these baseline policies.</span></span> <span data-ttu-id="c96c0-118">När dessa principer är aktiverade uppmanas administratörer och användare att registrera sig för Azure Multii-Factor-autentisering.</span><span class="sxs-lookup"><span data-stu-id="c96c0-118">After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.</span></span>

<span data-ttu-id="c96c0-119">Mer information om dessa principer finns i [Vad är originalprinciper?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="c96c0-119">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="set-up-baseline-policies"></a><span data-ttu-id="c96c0-120">Ställ in baslinjeprinciper</span><span class="sxs-lookup"><span data-stu-id="c96c0-120">Set up baseline policies</span></span>

1. <span data-ttu-id="c96c0-121">Gå till [Azure-portalen](https://portal.azure.com)och navigera sedan till **Azure Active Directory** \> **Villkorlig åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="c96c0-121">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="c96c0-122">Originalplansprinciperna visas på sidan.</span><span class="sxs-lookup"><span data-stu-id="c96c0-122">The baseline policies are listed on the page.</span></span> <br/> <br/>
    <span data-ttu-id="c96c0-123">![Sida som visar originalprinciper för villkorlig åtkomst.](../media/baslinepolicies.png)</span><span class="sxs-lookup"><span data-stu-id="c96c0-123">![Page that lists baseline policies for conditional access.](../media/baslinepolicies.png)</span></span>
1. <span data-ttu-id="c96c0-124">Se följande specifika instruktioner för varje princip:</span><span class="sxs-lookup"><span data-stu-id="c96c0-124">See the following specific instructions for each policy:</span></span>

  - [<span data-ttu-id="c96c0-125">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="c96c0-125">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [<span data-ttu-id="c96c0-126">Kräv MFA för användare</span><span class="sxs-lookup"><span data-stu-id="c96c0-126">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [<span data-ttu-id="c96c0-127">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="c96c0-127">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [<span data-ttu-id="c96c0-128">Kräv MFA för servicehantering</span><span class="sxs-lookup"><span data-stu-id="c96c0-128">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="c96c0-129">Du kan ställa in många ytterligare principer, till exempel kräva godkända klientappar.</span><span class="sxs-lookup"><span data-stu-id="c96c0-129">You can set up many additional policies, such as requiring approved client apps.</span></span> <span data-ttu-id="c96c0-130">Mer information finns i [dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="c96c0-130">For more information, see the [Conditional Access Documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
