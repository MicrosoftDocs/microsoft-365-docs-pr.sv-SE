---
title: Konfigurera principer för villkorlig åtkomst
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Läs om hur du kräver MFA och konfigurerar principer för villkorlig åtkomst för Microsoft 365 Business.
ms.openlocfilehash: 7898ded24bb66545b903ab98f3c7aa78d95860f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811470"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a><span data-ttu-id="c9175-103">Kräv multifaktorautentisering och konfigurera principer för villkorlig åtkomst</span><span class="sxs-lookup"><span data-stu-id="c9175-103">Require multi-factor authentication and set up conditional access policies</span></span>

<span data-ttu-id="c9175-104">Du skyddar åtkomsten till dina data med principer för multifaktorautentisering och villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="c9175-104">You protect access to your data with multi-factor authentication and conditional access policies.</span></span> <span data-ttu-id="c9175-105">Dessa ger betydande ytterligare säkerhet.</span><span class="sxs-lookup"><span data-stu-id="c9175-105">These add substantial additional security.</span></span> <span data-ttu-id="c9175-106">Microsoft tillhandahåller en uppsättning principer för villkorlig åtkomst vid originalplan som rekommenderas för alla kunder.</span><span class="sxs-lookup"><span data-stu-id="c9175-106">Microsoft provides a set of baseline conditional access policies that are recommended for all customers.</span></span> <span data-ttu-id="c9175-107">Originalprinciper är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker.</span><span class="sxs-lookup"><span data-stu-id="c9175-107">Baseline policies are a set of predefined policies that help protect organizations against many common attacks.</span></span> <span data-ttu-id="c9175-108">Dessa vanliga attacker kan omfatta lösenordsspray, repris och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="c9175-108">These common attacks can include password spray, replay, and phishing.</span></span>

<span data-ttu-id="c9175-109">Dessa principer kräver att administratörer och användare anger en andra form av autentisering (kallas multifaktorautentisering eller MFA) när vissa villkor är uppfyllda.</span><span class="sxs-lookup"><span data-stu-id="c9175-109">These policies require admins and users to enter a second form of authentication (called multi-factor authentication, or MFA) when certain conditions are met.</span></span> <span data-ttu-id="c9175-110">Om en användare i organisationen till exempel försöker logga in på Microsoft 365 från ett annat land eller från en okänd enhet kan inloggningen anses riskabel.</span><span class="sxs-lookup"><span data-stu-id="c9175-110">For example, if a user in your organization tries to sign in to Microsoft 365 from a different country or from an unknown device, the sign-in might be considered risky.</span></span> <span data-ttu-id="c9175-111">Användaren måste tillhandahålla en extra form av autentisering (t.ex. ett fingeravtryck eller en kod) för att bevisa sin identitet.</span><span class="sxs-lookup"><span data-stu-id="c9175-111">The user must provide an extra form of authentication (such as a fingerprint or a code) to prove their identity.</span></span> 

<span data-ttu-id="c9175-112">För närvarande innehåller baslinjeprinciper följande:</span><span class="sxs-lookup"><span data-stu-id="c9175-112">Currently, baseline policies include the following:</span></span>
- <span data-ttu-id="c9175-113">Konfigurera i Microsoft 365 administrationscenter:</span><span class="sxs-lookup"><span data-stu-id="c9175-113">Set up in Microsoft 365 admin center:</span></span>
    - <span data-ttu-id="c9175-114">**Kräv MFA för administratörer** – Kräver multifaktorautentisering för de mest privilegierade administratörsrollerna, inklusive global administratör.</span><span class="sxs-lookup"><span data-stu-id="c9175-114">**Require MFA for admins** — Requires multi-factor authentication for the most privileged administrator roles, including global administrator.</span></span>
    - <span data-ttu-id="c9175-115">**Skydd för slutanvändare** – Kräver multifaktorautentisering endast för användare när en inloggning är riskabel.</span><span class="sxs-lookup"><span data-stu-id="c9175-115">**End user protection** — Requires multi-factor authentication for users only when a sign-in is risky.</span></span> 
- <span data-ttu-id="c9175-116">Konfigurera i Azure Active Directory-portal:</span><span class="sxs-lookup"><span data-stu-id="c9175-116">Set up in Azure Active Directory portal:</span></span>
    - <span data-ttu-id="c9175-117">**Blockera äldre autentisering** – Äldre klientappar och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="c9175-117">**Block legacy authentication** — Older client apps and some new apps don't use newer, more secure, authentication protocols.</span></span> <span data-ttu-id="c9175-118">Dessa äldre appar kan kringgå principer för villkorlig åtkomst och få obehörig åtkomst till din miljö.</span><span class="sxs-lookup"><span data-stu-id="c9175-118">These older apps can bypass conditional access policies and gain unauthorized access to your environment.</span></span> <span data-ttu-id="c9175-119">Den här principen blockerar åtkomst från klienter som inte stöder villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="c9175-119">This policy blocks access from clients that don't support conditional access.</span></span> 
    - <span data-ttu-id="c9175-120">**Kräv MFA för servicehantering** – Kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portal (där du konfigurerar baslinjeprinciper).</span><span class="sxs-lookup"><span data-stu-id="c9175-120">**Require MFA for Service Management** — Requires multi-factor authentication for access to management tools, including Azure portal (where you configure baseline policies).</span></span> 

<span data-ttu-id="c9175-121">Microsoft rekommenderar att du aktiverar alla dessa baslinjeprinciper.</span><span class="sxs-lookup"><span data-stu-id="c9175-121">Microsoft recommends that you enable all of these baseline policies.</span></span> <span data-ttu-id="c9175-122">När dessa principer är aktiverade uppmanas administratörer och användare att registrera sig för Azure Multi-Factor-autentisering.</span><span class="sxs-lookup"><span data-stu-id="c9175-122">After these policies are enabled, admins and users will be prompted to register for Azure Multi-Factor authentication.</span></span>

<span data-ttu-id="c9175-123">Mer information om dessa principer finns i [Vad är originalprinciper?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)</span><span class="sxs-lookup"><span data-stu-id="c9175-123">For more information about these policies, see [What are baseline policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?</span></span>


## <a name="require-mfa"></a><span data-ttu-id="c9175-124">Kräv MFA</span><span class="sxs-lookup"><span data-stu-id="c9175-124">Require MFA</span></span>

<span data-ttu-id="c9175-125">Så här kräver du att alla användare loggar in med en andra form av ID:</span><span class="sxs-lookup"><span data-stu-id="c9175-125">To require that all users sign in with a second form of ID:</span></span>

1. <span data-ttu-id="c9175-126">Gå till administrationscentret och <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> välj **Installationsprogram**.</span><span class="sxs-lookup"><span data-stu-id="c9175-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> and choose **Setup**.</span></span>

2. <span data-ttu-id="c9175-127">På sidan Inställningar väljer du **Visa** på det **säkrare kortet Gör inloggning.**</span><span class="sxs-lookup"><span data-stu-id="c9175-127">On the Setup page, choose **View** in the **Make sign-in more secure** card.</span></span>


    ![Gör inloggning säkrare kort.](../media/setupmfa.png)
3. <span data-ttu-id="c9175-129">På sidan Gör inloggning säkrare väljer du **Kom igång**.</span><span class="sxs-lookup"><span data-stu-id="c9175-129">On the Make sign-in more secure page, choose **Get started**.</span></span>
 
4. <span data-ttu-id="c9175-130">Markera kryssrutorna bredvid **Kräv multifaktorautentisering för administratörer** i säkerhetsfönstret Stärka inloggning **och blockera åtkomst om risken upptäcks**.</span><span class="sxs-lookup"><span data-stu-id="c9175-130">On the Strengthen sign-in security pane, select the check boxes next to **Require multi-factor authentication for admins** and **Require users to register for multi-factor authentication and block access if risk is detected**.</span></span>
    <span data-ttu-id="c9175-131">Var noga med att utesluta [administrationskontot](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) för nödsituationer eller "break-glass" från MFA-kravet i rutan **Hitta användare.**</span><span class="sxs-lookup"><span data-stu-id="c9175-131">Be sure to exclude the [emergency](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) or "break-glass" admin account from the MFA requirement in the **Find users** box.</span></span>
    
    ![Stärka sing-in säkerhetssida.](../media/requiremfa.png)

5. <span data-ttu-id="c9175-133">Välj **Skapa princip** längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="c9175-133">Choose **Create policy** on the bottom of the page.</span></span>

## <a name="set-up-baseline-policies"></a><span data-ttu-id="c9175-134">Ställ in baslinjeprinciper</span><span class="sxs-lookup"><span data-stu-id="c9175-134">Set up baseline policies</span></span>

1. <span data-ttu-id="c9175-135">Gå till [Azure-portalen](https://portal.azure.com)och navigera sedan till **Azure Active Directory** \> **Villkorlig åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="c9175-135">Go to [Azure portal](https://portal.azure.com), and then navigate to **Azure Active Directory** \> **Conditional Access**.</span></span>
    
    <span data-ttu-id="c9175-136">Baslinjeprinciperna visas på sidan och du kan se att **Kräv MFA för administratörer** och **skydd för slutanvändare** redan är aktiverade när du har slutfört stegen i [kräver MFA](#require-mfa).</span><span class="sxs-lookup"><span data-stu-id="c9175-136">The baseline policies are listed on the page, and you can see that **Require MFA for admins** and **End user protection** are already enabled after you completed the steps in [require MFA](#require-mfa).</span></span>

    ![Sida som visar originalprinciper för villkorlig åtkomst.](../media/casettings.png)
2. <span data-ttu-id="c9175-138">Se följande specifika instruktioner för varje princip:</span><span class="sxs-lookup"><span data-stu-id="c9175-138">See the following specific instructions for each policy:</span></span>

    - [<span data-ttu-id="c9175-139">Kräv MFA för administratörer</span><span class="sxs-lookup"><span data-stu-id="c9175-139">Require MFA for admins</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [<span data-ttu-id="c9175-140">Kräv MFA för användare</span><span class="sxs-lookup"><span data-stu-id="c9175-140">Require MFA for users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [<span data-ttu-id="c9175-141">Blockera äldre autentisering</span><span class="sxs-lookup"><span data-stu-id="c9175-141">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [<span data-ttu-id="c9175-142">Kräv MFA för servicehantering</span><span class="sxs-lookup"><span data-stu-id="c9175-142">Require MFA for service management</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

<span data-ttu-id="c9175-143">Du kan ställa in extra principer, till exempel kräva godkända klientappar.</span><span class="sxs-lookup"><span data-stu-id="c9175-143">You can set up extra policies, such as requiring approved client apps.</span></span> <span data-ttu-id="c9175-144">Mer information finns i [dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span><span class="sxs-lookup"><span data-stu-id="c9175-144">For more information, see the [Conditional Access documentation](https://docs.microsoft.com/azure/active-directory/conditional-access/).</span></span>
