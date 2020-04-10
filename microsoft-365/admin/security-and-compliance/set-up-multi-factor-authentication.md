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
ms.openlocfilehash: 5f468f040ca88ab4ab2bc198d0d7550bf2e7f4af
ms.sourcegitcommit: 8a88b7526e6a3a907f33a8567e0d25b74fe60d80
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43204028"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="be99a-103">Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="be99a-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="be99a-104">Om du har köpt din prenumeration eller utvärderingsversion efter den 21 oktober 2019 och du oväntat uppmanas att korrigera flera faktorer har [säkerhetsinställningarna aktiverats](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatiskt för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="be99a-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="be99a-105">Alla nya Office 365 för företag- och Microsoft 365 Business-prenumerationer har automatiskt säkerhetsstandarder aktiverade.</span><span class="sxs-lookup"><span data-stu-id="be99a-105">Every new Office 365 for business or Microsoft 365 Business subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="be99a-106">Det innebär att alla användare måste konfigurera MFA och installera Microsoft Authenticator-appen på sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="be99a-106">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="be99a-107">Mer information finns i [Konfigurera tvåstegsverifiering för Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="be99a-107">For more information, see [Set up 2-step verification for Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="be99a-108">Följande nio administratörsroller måste utföra ytterligare autentisering varje gång de loggar in:</span><span class="sxs-lookup"><span data-stu-id="be99a-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>
- <span data-ttu-id="be99a-109">Global administratör</span><span class="sxs-lookup"><span data-stu-id="be99a-109">Global administrator</span></span>
- <span data-ttu-id="be99a-110">SharePoint-administratör</span><span class="sxs-lookup"><span data-stu-id="be99a-110">SharePoint administrator</span></span>
- <span data-ttu-id="be99a-111">Exchange-administratör</span><span class="sxs-lookup"><span data-stu-id="be99a-111">Exchange administrator</span></span>
- <span data-ttu-id="be99a-112">Administratör för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="be99a-112">Conditional Access administrator</span></span>
- <span data-ttu-id="be99a-113">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="be99a-113">Security administrator</span></span>
- <span data-ttu-id="be99a-114">Kundtjänstadministratör eller lösenordsadministratör</span><span class="sxs-lookup"><span data-stu-id="be99a-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="be99a-115">Faktureringsadministratör</span><span class="sxs-lookup"><span data-stu-id="be99a-115">Billing administrator</span></span>
- <span data-ttu-id="be99a-116">Användaradministratör</span><span class="sxs-lookup"><span data-stu-id="be99a-116">User administrator</span></span>
- <span data-ttu-id="be99a-117">Administratör av autentisering</span><span class="sxs-lookup"><span data-stu-id="be99a-117">Authentication administrator</span></span>

<span data-ttu-id="be99a-118">Alla andra användare kommer att ombes utföra ytterligare autentisering när det behövs.</span><span class="sxs-lookup"><span data-stu-id="be99a-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="be99a-119">Mer information finns i [Vad är säkerhetsstandarder?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="be99a-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

> [!NOTE]
> <span data-ttu-id="be99a-120">Du måste vara en global Office 365-administratör för att kunna konfigurera eller ändra MFA.</span><span class="sxs-lookup"><span data-stu-id="be99a-120">You must be an Office 365 global admin to set up or modify MFA.</span></span> <br><br>
> <span data-ttu-id="be99a-121">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="be99a-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="be99a-122">Om du tidigare har konfigurerat MFA med riktlinjer [måste du inaktivera och aktivera säkerhetsstandarder](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="be99a-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="be99a-123">Men om du har Microsoft 365 Business eller din prenumeration innehåller [Azure Active Directory Premium P1 eller Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)kan du också ställa in principer för villkorlig [åtkomst.](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="be99a-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="be99a-124">Om du vill använda principer för villkorlig åtkomst måste du se till att [modern autentisering](#enable-modern-authentication-for-your-organization) är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="be99a-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="be99a-125">För att kunna förklara för användarna hur de konfigurerar Authenticator-appen kan du besöka [Använd Microsoft Authenticator med Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="be99a-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="be99a-126">Hantera säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="be99a-126">Manage security defaults</span></span>

1. <span data-ttu-id="be99a-127">Logga in på [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="be99a-127">Sign in to [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="be99a-128">Gå till [Azure Active Directory egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="be99a-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>

3. <span data-ttu-id="be99a-129">Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.</span><span class="sxs-lookup"><span data-stu-id="be99a-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="be99a-130">Välj **Ja** om du vill aktivera standardinställningar för säkerhet eller **Nej** om du vill inaktivera standardvärden för säkerhet och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="be99a-130">Choose **Yes** to enable security defaults or **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="be99a-131">Flytta från baslinje riktlinjer till säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="be99a-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="be99a-132">I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822)väljer du **Visa alla**och sedan Azure **Active Directory** under **Administrationscenter**.</span><span class="sxs-lookup"><span data-stu-id="be99a-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Show all**, and then **Azure Active Directory** under **Admin centers**.</span></span>

2. <span data-ttu-id="be99a-133">Välj **Azure Active Directory** > **Security**i **Administrationscentret för Azure** Active Directory .</span><span class="sxs-lookup"><span data-stu-id="be99a-133">In the  **Azure Active Directory admin center** choose **Azure Active Directory** > **Security**.</span></span>

3. <span data-ttu-id="be99a-134">Om **säkerheten | Komma** igång-sidan, välj **Villkorlig åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="be99a-134">On the **Security | Getting started** page, choose **Conditional Access**.</span></span> 

4. <span data-ttu-id="be99a-135">På sidan **Villkorad åtkomst till Azure portal – riktlinjer** väljer du varje baslinje-policy som är **På** och ställ dem på **Av**.</span><span class="sxs-lookup"><span data-stu-id="be99a-135">On the **Azure portal Conditional Access - Policies** page,  choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="be99a-136">Gå till sidan [Azure Active Directory egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="be99a-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="be99a-137">Gå till slutet av sidan och välj **Hantera säkerhetsstandarder**och i fönstret **Aktivera säkerhetsstandarder** och ställer**Aktiverar säkerhetsstandarder** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="be99a-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="be99a-138">Aktivera modern autentisering för din organisation</span><span class="sxs-lookup"><span data-stu-id="be99a-138">Enable Modern authentication for your organization</span></span>

<span data-ttu-id="be99a-139">Alla Office 2016-klientprogrammen har stöd för MFA genom användning av ADAL (Active Directory Authentication Library).</span><span class="sxs-lookup"><span data-stu-id="be99a-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="be99a-140">Det innebär att programlösenord inte är nödvändiga för Office 2016-klienter.</span><span class="sxs-lookup"><span data-stu-id="be99a-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="be99a-141">Du måste kontrollera att din Office 365-prenumeration är aktiverad för ADAL eller modern autentisering.</span><span class="sxs-lookup"><span data-stu-id="be99a-141">However, you need to make sure your Office 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="be99a-142">Om du vill aktivera modern autentisering väljer du **Inställningar** \> **Inställningar** i [administrationscentrat](https://go.microsoft.com/fwlink/p/?linkid=834822) och **Modern autentisering** i listan på fliken **Tjänster**.</span><span class="sxs-lookup"><span data-stu-id="be99a-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="be99a-143">Markera rutan **Aktivera modern autentisering** i panelen **Modern autentisering**.</span><span class="sxs-lookup"><span data-stu-id="be99a-143">Check the **Enable modern authentication** box in the **Modern authentication** panel.</span></span> 

    ![Panelen Modern autentisering med kryssrutan Aktivera markerad.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="be99a-145">Från och med augusti 2017 är modern autentisering aktiverat som standard för alla nya Office 365-klientorganisationer som inkluderar Skype för företag – Online och Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="be99a-145">As of August of 2017, all new Office 365 tenants that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="be99a-146">Om du vill kontrollera status för modern autentisering i Skype för företag – Online kan du använda Skype för företag – Online PowerShell med globala administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="be99a-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="be99a-147">Kör Get-CsOAuthConfiguration när du vill kontrollera utdata för -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="be99a-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="be99a-148">Om -ClientADALAuthOverride är Allowed är modern autentisering aktiverat.</span><span class="sxs-lookup"><span data-stu-id="be99a-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="be99a-149">Om du vill kontrollera MA-status för Exchange Online går du till [Aktivera modern autentisering i Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="be99a-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="be99a-150">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="be99a-150">Related articles</span></span>

[<span data-ttu-id="be99a-151">De 10 bästa sätten att skydda Office 365 och Microsoft 365 Business-abonnemang</span><span class="sxs-lookup"><span data-stu-id="be99a-151">Top 10 ways to secure Office 365 and Microsoft 365 Business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="be99a-152">Aktivera modern autentisering för Office 2013 på Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="be99a-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
