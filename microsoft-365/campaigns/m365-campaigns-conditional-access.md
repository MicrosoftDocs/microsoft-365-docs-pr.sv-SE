---
title: Konfigurera regler för villkorsstyrd åtkomst
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
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du begär MFA och konfigurerar principer för villkorsstyrd åtkomst för Microsoft 365 för företag.
ms.openlocfilehash: 5908a36f09753cd8f66169c6a67be45c748807b7
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071507"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="6749f-103">Kräv multifaktorautentisering och konfigurera principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="6749f-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="6749f-104">Du skyddar åtkomsten till dina data med principer för multifaktorautentisering och villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="6749f-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="6749f-105">Dessa tillägg till ökad säkerhet.</span><span class="sxs-lookup"><span data-stu-id="6749f-105">These add substantial additional security.</span></span> <span data-ttu-id="6749f-106">Microsoft tillhandahåller en uppsättning principer för villkorsstyrd åtkomst enligt grundläggande som rekommenderas för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="6749f-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="6749f-107">Rikt linjer är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga angrepp.</span><span class="sxs-lookup"><span data-stu-id="6749f-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="6749f-108">Dessa vanliga angrepp kan inkludera lösen ord, Replay och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="6749f-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="6749f-109">Dessa principer kräver att administratörer och användare anger en andra form av autentiseringsprocessen (kallas multifaktorautentisering) när vissa villkor uppfylls.</span><span class="sxs-lookup"><span data-stu-id="6749f-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="6749f-110">Om en användare i din organisation till exempel försöker logga in på Microsoft 365 från ett annat land eller från en okänd enhet kan inloggningen betraktas som riskfylld.</span><span class="sxs-lookup"><span data-stu-id="6749f-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="6749f-111">Användaren måste tillhandahålla en extra form av auktorisering (till exempel ett finger avtryck eller en kod) för att bevisa sin identitet.</span><span class="sxs-lookup"><span data-stu-id="6749f-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="6749f-112">För närvarande inkluderar grundläggande principer följande:</span><span class="sxs-lookup"><span data-stu-id="6749f-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="6749f-113">Konfigurera i Microsoft 365 Admin Center:</span><span class="sxs-lookup"><span data-stu-id="6749f-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="6749f-114">**KRÄV MFA för administratörer** – kräver multifaktorautentisering för de mest privilegierade administratörs rollerna, inklusive global administratör.</span><span class="sxs-lookup"><span data-stu-id="6749f-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="6749f-115">**Slutanvändarens skydd** – kräver multifaktorautentisering för användare endast när en inloggning är riskabel.</span><span class="sxs-lookup"><span data-stu-id="6749f-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="6749f-116">Konfigurera i Azure Active Directory-portalen:</span><span class="sxs-lookup"><span data-stu-id="6749f-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="6749f-117">**Blockera äldre verifierare** – äldre klient program och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="6749f-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="6749f-118">Dessa äldre appar kan kringgå villkorsstyrda åtkomst principer och få obehörig åtkomst till din miljö.</span><span class="sxs-lookup"><span data-stu-id="6749f-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="6749f-119">Denna princip blockerar åtkomst från klienter som inte stöder villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="6749f-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="6749f-120">**KRÄV MFA för tjänst hantering** – kräver multifaktorautentisering för åtkomst till hanterings verktyg, inklusive Azure Portal (där du konfigurerar rikt linjer för principer).</span><span class="sxs-lookup"><span data-stu-id="6749f-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="6749f-121">Microsoft rekommenderar att du aktiverar alla dessa rikt linjer.</span><span class="sxs-lookup"><span data-stu-id="6749f-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="6749f-122">Efter att dessa principer har Aktiver ATS uppmanas administratörer och användare att registrera sig för Azure Multi-Factor User.</span><span class="sxs-lookup"><span data-stu-id="6749f-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="6749f-123">Mer information om dessa principer finns i [Vad är rikt linjer](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span><span class="sxs-lookup"><span data-stu-id="6749f-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="6749f-124">Kräv MFA</span><span class="sxs-lookup"><span data-stu-id="6749f-124">Require MFA</span></span>

<span data-ttu-id="6749f-125">Om du vill att alla användare ska logga in med en andra form av ID:</span><span class="sxs-lookup"><span data-stu-id="6749f-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="6749f-126">Gå till administrations centret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> och välj **installation**.</span><span class="sxs-lookup"><span data-stu-id="6749f-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="6749f-127">På sidan Inställningar väljer du **Visa** i det **säkra kortet gör inloggning mer** .</span><span class="sxs-lookup"><span data-stu-id="6749f-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![Logga in mer skyddat kort.](../media/setupmfa.png)
3. <span data-ttu-id="6749f-129">På sidan gör inloggning säkrare väljer du **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="6749f-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="6749f-130">Markera kryss rutorna bredvid **Kräv multifaktorautentisering för administratörer** i fönstret Förstärk inloggnings säkerhet och **Kräv att användare registrerar multifaktorautentisering och blockera åtkomst om risken upptäcks**.</span><span class="sxs-lookup"><span data-stu-id="6749f-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="6749f-131">Se till att exkludera [katastrof](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) -eller "brytar glas"-kontot från MFA-kravet i rutan **Sök efter användare** .</span><span class="sxs-lookup"><span data-stu-id="6749f-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![Förstärka sidan för att skydda dig.](../media/requiremfa.png)

5. <span data-ttu-id="6749f-133">Välj **Skapa princip** längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="6749f-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="6749f-134">Konfigurera rikt linjer</span><span class="sxs-lookup"><span data-stu-id="6749f-134">Set up baseline policies</span></span>

1. <span data-ttu-id="6749f-135">Gå till [Azure-portalen](https://portal.azure.com)och gå till villkorlig åtkomst för **Azure Active Directory** \> **Conditional Access** för att skapa en **ny princip**.</span><span class="sxs-lookup"><span data-stu-id="6749f-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="6749f-136">Se följande anvisningar för varje princip:</span><span class="sxs-lookup"><span data-stu-id="6749f-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="6749f-137">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="6749f-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="6749f-138">Kräv MFA för användare</span><span class="sxs-lookup"><span data-stu-id="6749f-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="6749f-139">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="6749f-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="6749f-140">Kräv MFA för tjänst hantering</span><span class="sxs-lookup"><span data-stu-id="6749f-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)
    
> [!NOTE]
> <span data-ttu-id="6749f-141">För hands versions principer finns inte längre och användarna måste skapa sina egna principer.</span><span class="sxs-lookup"><span data-stu-id="6749f-141">Preview policies no longer exist and users will need to create their own policies.</span></span>


<span data-ttu-id="6749f-142">Du kan konfigurera ytterligare principer, till exempel för godkända klient program.</span><span class="sxs-lookup"><span data-stu-id="6749f-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="6749f-143">Mer information finns i dokumentationen för [villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="6749f-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
