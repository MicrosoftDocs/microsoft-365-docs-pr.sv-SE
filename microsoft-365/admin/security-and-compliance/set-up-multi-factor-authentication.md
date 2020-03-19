---
title: Konfigurera multifaktorautentisering för Office 365-användare
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Lär dig hur du använder säkerhetsstandarder för att konfigurera multifaktorautentisering för Office 365-användare.
monikerRange: o365-worldwide
ms.openlocfilehash: 4dc52c25c3a9351be1a9f4d094d664bc4ed527f9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42810167"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="131b8-103">Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="131b8-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="131b8-104">Alla nya Office 365 för företag- och Microsoft 365 Business-prenumerationer har automatiskt säkerhetsstandarder aktiverade.</span><span class="sxs-lookup"><span data-stu-id="131b8-104">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="131b8-105">Det innebär att alla användare måste konfigurera multifaktorautentisering (MFA) och installera Authenticator-appen på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="131b8-105">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="131b8-106">Mer information finns i [Konfigurera tvåstegsverifiering för Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="131b8-106">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="131b8-107">Följande nio administratörsroller måste utföra ytterligare autentisering varje gång de loggar in:</span><span class="sxs-lookup"><span data-stu-id="131b8-107">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="131b8-108">Global administratör</span><span class="sxs-lookup"><span data-stu-id="131b8-108">Global administrator</span></span>
- <span data-ttu-id="131b8-109">SharePoint-administratör</span><span class="sxs-lookup"><span data-stu-id="131b8-109">SharePoint administrator</span></span>
- <span data-ttu-id="131b8-110">Exchange-administratör</span><span class="sxs-lookup"><span data-stu-id="131b8-110">Exchange administrator</span></span>
- <span data-ttu-id="131b8-111">Administratör för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="131b8-111">Conditional Access administrator</span></span>
- <span data-ttu-id="131b8-112">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="131b8-112">Security administrator</span></span>
- <span data-ttu-id="131b8-113">Kundtjänstadministratör eller lösenordsadministratör</span><span class="sxs-lookup"><span data-stu-id="131b8-113">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="131b8-114">Faktureringsadministratör</span><span class="sxs-lookup"><span data-stu-id="131b8-114">Billing administrator</span></span>
- <span data-ttu-id="131b8-115">Användaradministratör</span><span class="sxs-lookup"><span data-stu-id="131b8-115">User administrator</span></span>
- <span data-ttu-id="131b8-116">Administratör av autentisering</span><span class="sxs-lookup"><span data-stu-id="131b8-116">Authentication administrator</span></span>

<span data-ttu-id="131b8-117">Alla andra användare kommer att ombes utföra ytterligare autentisering när det behövs.</span><span class="sxs-lookup"><span data-stu-id="131b8-117">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="131b8-118">Mer information finns i [Vad är säkerhetsstandarder?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="131b8-118">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="131b8-p103">Du måste vara global Office 365-administratör för att konfigurera eller ändra multifaktorautentisering. </span><span class="sxs-lookup"><span data-stu-id="131b8-p103">You must be an Office 365 global admin to set up or modify multi-factor authentication. </span></span><br><br>
> <span data-ttu-id="131b8-120">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="131b8-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="131b8-121">Om du tidigare har konfigurerat MFA med riktlinjer [måste du inaktivera och aktivera säkerhetsstandarder](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="131b8-121">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="131b8-122">Men om du har Microsoft 365 Business eller om din prenumeration omfattar [Azure Active Directory Premium 1 eller Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/)kan du även konfigurera riktlinjerna [villkorad åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="131b8-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="131b8-123">Om du vill använda riktlinjerna för villkorad åtkomst måste du kontrollera att [modern autentisering är aktiverat](#enable-multi-factor-authentication-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="131b8-123">To use conditional access policies, you need to make sure [modern authentication is enabled](#enable-multi-factor-authentication-for-your-organization).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="131b8-124">Hantera säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="131b8-124">Manage security defaults</span></span>

1. <span data-ttu-id="131b8-125">Logga in på [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="131b8-125">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="131b8-126">Gå till [Azure Active Directory egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="131b8-126">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="131b8-127">Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.</span><span class="sxs-lookup"><span data-stu-id="131b8-127">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="131b8-128">Välj **Ja** för att aktivera säkerhetsstandardinställningar och **Nej** för att inaktivera dem.</span><span class="sxs-lookup"><span data-stu-id="131b8-128">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="131b8-129">Flytta från baslinje riktlinjer till säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="131b8-129">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="131b8-130">I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) väljer du **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="131b8-130">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="131b8-131">Bredvid **Inloggning och säkerhet** väljer du **Visa** för **Gör inloggningen säkrare**.</span><span class="sxs-lookup"><span data-stu-id="131b8-131">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="131b8-132">Under **Gör inloggningen säkrare** väljer du **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="131b8-132">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="131b8-133">På sidan **Villkorad åtkomst till Azure portal – riktlinjer** väljer du varje baslinje-policy som är **På** och ställ dem på **Av**.</span><span class="sxs-lookup"><span data-stu-id="131b8-133">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="131b8-134">Gå till sidan [Azure Active Directory egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="131b8-134">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="131b8-135">Gå till slutet av sidan och välj **Hantera säkerhetsstandarder**och i fönstret **Aktivera säkerhetsstandarder** och ställer**Aktiverar säkerhetsstandarder** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="131b8-135">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="131b8-136">Aktivera modern autentisering för din organisation</span><span class="sxs-lookup"><span data-stu-id="131b8-136">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="131b8-137">Alla Office 2016-klientprogrammen har stöd för MFA genom användning av ADAL (Active Directory Authentication Library).</span><span class="sxs-lookup"><span data-stu-id="131b8-137">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="131b8-138">Det innebär att programlösenord inte är nödvändiga för Office 2016-klienter.</span><span class="sxs-lookup"><span data-stu-id="131b8-138">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="131b8-139">Du måste kontrollera att din Office 365-prenumeration är aktiverad för ADAL eller modern autentisering.</span><span class="sxs-lookup"><span data-stu-id="131b8-139">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="131b8-140">Om du vill aktivera modern autentisering väljer du **Inställningar** \> **Inställningar** i [administrationscentrat](https://go.microsoft.com/fwlink/p/?linkid=834822) och **Modern autentisering** i listan på fliken **Tjänster**.</span><span class="sxs-lookup"><span data-stu-id="131b8-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="131b8-141">Markera rutan **Aktivera modern autentisering** i panelen **Modern autentisering**.</span><span class="sxs-lookup"><span data-stu-id="131b8-141">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![Panelen Modern autentisering med kryssrutan Aktivera markerad.](../../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a><span data-ttu-id="131b8-143">Aktivera multifaktorautentisering för din organisation</span><span class="sxs-lookup"><span data-stu-id="131b8-143">Enable multi-factor authentication for your organization</span></span>
    
1. <span data-ttu-id="131b8-144">Välj **Användare** och aktiva **användare**i [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822).</span><span class="sxs-lookup"><span data-stu-id="131b8-144">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Users** and **Active Users**.</span></span>

2. <span data-ttu-id="131b8-145">Klicka på **multifaktorautentisering**i avsnittet **Aktiva användare** .</span><span class="sxs-lookup"><span data-stu-id="131b8-145">In the **Active Users** section, Click on  **multi-factor authentication**.</span></span>

3. <span data-ttu-id="131b8-146">På sidan **Multifaktorautentisering** väljer du **användare** om du aktiverar detta för en användare eller väljer **Massuppdatering** för att aktivera flera användare.</span><span class="sxs-lookup"><span data-stu-id="131b8-146">On the **Multi-factor authentication** page, select **user** if you are enabling this for one user or select **Bulk Update** to enable multiple users.</span></span>

4. <span data-ttu-id="131b8-147">CLick på **Aktivera** under **Snabbsteg**.</span><span class="sxs-lookup"><span data-stu-id="131b8-147">CLick on **Enable** under **Quick Steps**.</span></span>

5. <span data-ttu-id="131b8-148">Klicka på **Aktivera multifaktorautentisering**i popup-fönstret .</span><span class="sxs-lookup"><span data-stu-id="131b8-148">In the Pop-up window, Click on **Enable Multi-Factor Authentication**.</span></span>

<span data-ttu-id="131b8-149">När du har konfigurerat multifaktorautentisering för din organisation måste dina användare konfigurera tvåstegsverifiering på sina enheter.</span><span class="sxs-lookup"><span data-stu-id="131b8-149">After you set up multi-factor authentication for your organization, your users will be required to set up two-step verification on their devices.</span></span> <span data-ttu-id="131b8-150">Mer information finns i [Konfigurera tvåstegsverifiering för Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="131b8-150">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>
    
> [!TIP]
> <span data-ttu-id="131b8-151">För att kunna förklara för användarna hur de konfigurerar Authenticator-appen kan du besöka [Använd Microsoft Authenticator med Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="131b8-151">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="131b8-152">Från och med augusti 2017 är modern autentisering aktiverat som standard för alla nya Office 365-klientorganisationer som inkluderar Skype för företag – Online och Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="131b8-152">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="131b8-153">Om du vill kontrollera status för modern autentisering i Skype för företag – Online kan du använda Skype för företag – Online PowerShell med globala administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="131b8-153">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="131b8-154">Kör Get-CsOAuthConfiguration när du vill kontrollera utdata för -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="131b8-154">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="131b8-155">Om -ClientADALAuthOverride är Allowed är modern autentisering aktiverat.</span><span class="sxs-lookup"><span data-stu-id="131b8-155">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="131b8-156">Om du vill kontrollera MA-status för Exchange Online går du till [Aktivera modern autentisering i Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="131b8-156">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="131b8-157">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="131b8-157">Related articles</span></span>

[<span data-ttu-id="131b8-158">De 10 bästa sätten att skydda Office 365 och Microsoft 365 Business-abonnemang</span><span class="sxs-lookup"><span data-stu-id="131b8-158">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="131b8-159">Aktivera modern autentisering för Office 2013 på Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="131b8-159">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
