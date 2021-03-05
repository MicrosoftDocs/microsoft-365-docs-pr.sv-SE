---
title: Konfigurera villkorsstyrda åtkomstprinciper
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
description: Lär dig hur du kräver MFA och konfigurera villkorsstyrda åtkomstprinciper för Microsoft 365 för företag.
ms.openlocfilehash: e16b7f4ff7d215ee749435806be214a807cc60a4
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453675"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="859bd-103">Kräv multifaktorautentisering och konfigurera villkorsstyrda åtkomstprinciper</span><span class="sxs-lookup"><span data-stu-id="859bd-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="859bd-104">Du skyddar åtkomsten till dina data med principer för multifaktorautentisering och villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="859bd-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="859bd-105">Dessa ger betydande ytterligare säkerhet.</span><span class="sxs-lookup"><span data-stu-id="859bd-105">These add substantial additional security.</span></span> <span data-ttu-id="859bd-106">Microsoft tillhandahåller en uppsättning grundläggande villkorsstyrda åtkomstprinciper som rekommenderas för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="859bd-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="859bd-107">Baslinjeprinciper är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="859bd-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="859bd-108">Dessa vanliga attacker kan vara lösenordsattacker, uppspelning och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="859bd-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="859bd-109">Dessa principer kräver att administratörer och användare anger en andra form av autentisering (kallas multifaktorautentisering eller MFA) under vissa förhållanden.</span><span class="sxs-lookup"><span data-stu-id="859bd-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) under certain conditions.</span></span> <span data-ttu-id="859bd-110">Om en användare i organisationen till exempel försöker logga in på Microsoft 365 från ett annat land eller från en okänd enhet kan inloggningen vara riskabel.</span><span class="sxs-lookup"><span data-stu-id="859bd-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="859bd-111">Användaren måste tillhandahålla en extra autentiseringsform (t.ex. fingeravtryck eller kod) för att bevisa sin identitet.</span><span class="sxs-lookup"><span data-stu-id="859bd-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span>

<span data-ttu-id="859bd-112">För närvarande innehåller baslinjeprinciperna följande principer:</span><span class="sxs-lookup"><span data-stu-id="859bd-112">Currently, the baseline policies include the following policies:</span></span>

- <span data-ttu-id="859bd-113">Konfigurera i administrationscentret för Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="859bd-113">Set up in Microsoft 365 admin center:</span></span>
  - <span data-ttu-id="859bd-114">**Kräv MFA för administratörer: Kräver** multifaktorautentisering för de mest behöriga administratörsrollerna, inklusive global administratör.</span><span class="sxs-lookup"><span data-stu-id="859bd-114">**Require MFA for admins**: Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
  - <span data-ttu-id="859bd-115">**Slutanvändarskydd:** Kräver multifaktorautentisering för användarna endast när en inloggning är riskabel.</span><span class="sxs-lookup"><span data-stu-id="859bd-115">**End-user protection**: Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="859bd-116">Konfigurera i Azure Active Directory-portalen:</span><span class="sxs-lookup"><span data-stu-id="859bd-116">Set up in Azure Active Directory portal:</span></span>
  - <span data-ttu-id="859bd-117">**Blockera äldre autentisering:** Äldre klientappar och vissa nya program använder inte nyare, säkrare autentiseringsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="859bd-117">**Block legacy authentication**: Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="859bd-118">Dessa äldre appar kan kringgå villkorsstyrda åtkomstprinciper och få obehörig åtkomst till din miljö.</span><span class="sxs-lookup"><span data-stu-id="859bd-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="859bd-119">Den här principen blockerar åtkomst från klienter som inte stöder villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="859bd-119">This policy blocks access from clients that don't support conditional access.</span></span> 
  - <span data-ttu-id="859bd-120">**Kräv MFA för tjänsthantering:** Kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portalen (där du konfigurerar baslinjeprinciper).</span><span class="sxs-lookup"><span data-stu-id="859bd-120">**Require MFA for Service Management**: Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span>

<span data-ttu-id="859bd-121">Vi rekommenderar att du aktiverar alla dessa baslinjeprinciper.</span><span class="sxs-lookup"><span data-stu-id="859bd-121">We recommend that you enable all of these baseline policies.</span></span> <span data-ttu-id="859bd-122">När dessa principer har aktiverats uppmanas administratörer och användare att registrera sig för Azure AD Multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="859bd-122">After these policies are enabled, admins and users will be prompted to register for Azure AD Multifactor Authentication.</span></span>

<span data-ttu-id="859bd-123">Mer information om dessa principer finns i Vad [är baslinjeprinciper?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="859bd-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>

## <a name="require-mfa"></a><span data-ttu-id="859bd-124">Kräv MFA</span><span class="sxs-lookup"><span data-stu-id="859bd-124">Require MFA</span></span>

<span data-ttu-id="859bd-125">Så här kräver du att alla användare loggar in med en andra form av ID:</span><span class="sxs-lookup"><span data-stu-id="859bd-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="859bd-126">Gå till administrationscentret och <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> välj **Installation.**</span><span class="sxs-lookup"><span data-stu-id="859bd-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="859bd-127">Välj Visa i **inloggningskortet** för **att göra inloggningen** säkrare på sidan Inställningar.</span><span class="sxs-lookup"><span data-stu-id="859bd-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>

    ![Gör inloggningskortet säkrare.](../media/setupmfa.png)
3. <span data-ttu-id="859bd-129">Välj Kom igång på sidan Gör **inloggningen säkrare.**</span><span class="sxs-lookup"><span data-stu-id="859bd-129">On the Make sign-in more secure page, choose **Get started**.</span></span>

4. <span data-ttu-id="859bd-130">I fönstret Förstärka **inloggningssäkerhet** markerar du kryssrutorna bredvid Kräv multifaktorautentisering för administratörer och Kräv att användare registrerar sig för multifaktorautentisering och blockera åtkomst om **risker identifieras.**</span><span class="sxs-lookup"><span data-stu-id="859bd-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="859bd-131">Se till att utesluta det [akuta](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) administratörskontot eller "break-glass"-administratörskontot från MFA-kravet i **rutan Hitta** användare.</span><span class="sxs-lookup"><span data-stu-id="859bd-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>

    ![Förstärka säkerhetssidan.](../media/requiremfa.png)

5. <span data-ttu-id="859bd-133">Välj **Skapa princip** längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="859bd-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="859bd-134">Konfigurera baslinjeprinciper</span><span class="sxs-lookup"><span data-stu-id="859bd-134">Set up baseline policies</span></span>

1. <span data-ttu-id="859bd-135">Gå till [Azure-portalen och](https://portal.azure.com)gå sedan till villkorsstyrd åtkomst för **Azure Active** \>  \> **Directory-säkerhet** för att skapa **en ny princip.**</span><span class="sxs-lookup"><span data-stu-id="859bd-135">Go to the [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Security** \> **Conditional Access** to create a **new policy**.</span></span>

<span data-ttu-id="859bd-136">Se följande specifika anvisningar för varje princip:</span><span class="sxs-lookup"><span data-stu-id="859bd-136">See the following specific instructions for each policy:</span></span> <br>
    - [<span data-ttu-id="859bd-137">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="859bd-137">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [<span data-ttu-id="859bd-138">Kräv MFA för användare</span><span class="sxs-lookup"><span data-stu-id="859bd-138">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [<span data-ttu-id="859bd-139">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="859bd-139">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [<span data-ttu-id="859bd-140">Kräv MFA för tjänsthantering</span><span class="sxs-lookup"><span data-stu-id="859bd-140">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> <span data-ttu-id="859bd-141">Förhandsgranskningsprinciperna finns inte längre och användarna måste skapa sina egna principer.</span><span class="sxs-lookup"><span data-stu-id="859bd-141">Preview policies no longer exist and users will need to create their own policies.</span></span>

<span data-ttu-id="859bd-142">Du kan konfigurera extra principer, till exempel krav på godkända klientprogram.</span><span class="sxs-lookup"><span data-stu-id="859bd-142">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="859bd-143">Mer information finns i dokumentationen för [villkorsstyrd åtkomst.](https://docs.microsoft.com/azure/active-directory/conditional-access/)</span><span class="sxs-lookup"><span data-stu-id="859bd-143">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
