---
title: Konfigurera multifaktorautentisering för användare
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
description: Lär dig hur du använder standardvärden för säkerhet för att konfigurera multifaktorautentisering för användare.
monikerRange: o365-worldwide
ms.openlocfilehash: 4a829aa597596564b9c2f468e72f3a766b198372
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627686"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="6d0c2-103">Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="6d0c2-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6d0c2-104">Om du har köpt din prenumeration eller utvärderingsversion efter den 21 oktober 2019 och du oväntat uppmanas att ange MFA har [säkerhetsinställningarna aktiverats](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatiskt för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="6d0c2-105">Varje ny Microsoft 365-prenumeration har automatiskt aktiverat säkerhetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-105">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="6d0c2-106">Det innebär att alla användare måste konfigurera multifaktorautentisering (MFA) och installera Authenticator-appen på en mobil enhet.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Authenticator app on their mobile device.</span></span> <span data-ttu-id="6d0c2-107">Mer information finns i [Konfigurera tvåstegsverifiering för Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="6d0c2-107">For more information, see [Set up 2-step verification for Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>  

<span data-ttu-id="6d0c2-108">Följande nio administratörsroller måste utföra ytterligare autentisering varje gång de loggar in:</span><span class="sxs-lookup"><span data-stu-id="6d0c2-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="6d0c2-109">Global administratör</span><span class="sxs-lookup"><span data-stu-id="6d0c2-109">Global administrator</span></span>
- <span data-ttu-id="6d0c2-110">SharePoint-administratör</span><span class="sxs-lookup"><span data-stu-id="6d0c2-110">SharePoint administrator</span></span>
- <span data-ttu-id="6d0c2-111">Exchange-administratör</span><span class="sxs-lookup"><span data-stu-id="6d0c2-111">Exchange administrator</span></span>
- <span data-ttu-id="6d0c2-112">Administratör för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="6d0c2-112">Conditional Access administrator</span></span>
- <span data-ttu-id="6d0c2-113">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="6d0c2-113">Security administrator</span></span>
- <span data-ttu-id="6d0c2-114">Kundtjänstadministratör eller lösenordsadministratör</span><span class="sxs-lookup"><span data-stu-id="6d0c2-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="6d0c2-115">Faktureringsadministratör</span><span class="sxs-lookup"><span data-stu-id="6d0c2-115">Billing administrator</span></span>
- <span data-ttu-id="6d0c2-116">Användaradministratör</span><span class="sxs-lookup"><span data-stu-id="6d0c2-116">User administrator</span></span>
- <span data-ttu-id="6d0c2-117">Administratör av autentisering</span><span class="sxs-lookup"><span data-stu-id="6d0c2-117">Authentication administrator</span></span>

<span data-ttu-id="6d0c2-118">Alla andra användare kommer att ombes utföra ytterligare autentisering när det behövs.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-118">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="6d0c2-119">Mer information finns i [Vad är standardinställningar för säkerhet?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="6d0c2-119">For more information, see [What are security defaults?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

> [!NOTE]
> <span data-ttu-id="6d0c2-120">Du måste vara global administratör för att kunna konfigurera eller ändra multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-120">You must be a global admin to set up or modify multi-factor authentication.</span></span> <br><br>
> <span data-ttu-id="6d0c2-121">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="6d0c2-122">Om du tidigare har konfigurerat MFA med riktlinjer [måste du inaktivera och aktivera säkerhetsstandarder](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="6d0c2-122">If you have previously set up MFA with baseline policies, [you must turn them off and turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="6d0c2-123">Men om du har Microsoft 365 Business eller om din prenumeration omfattar [Azure Active Directory Premium 1 eller Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/)kan du även konfigurera riktlinjerna [villkorad åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="6d0c2-123">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium 1, or Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="6d0c2-124">Om du vill använda principer för villkorlig åtkomst måste du se till att [modern autentisering](#enable-modern-authentication-for-your-organization) är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-124">To use conditional access policies, you need to make sure [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="6d0c2-125">För att kunna förklara för användarna hur de konfigurerar Authenticator-appen kan du besöka [Använd Microsoft Authenticator med Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span><span class="sxs-lookup"><span data-stu-id="6d0c2-125">To explain to your users how to set up the Authenticator app, please visit [Use Microsoft Authenticator with office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="6d0c2-126">Hantera säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="6d0c2-126">Manage security defaults</span></span>

1. <span data-ttu-id="6d0c2-127">Logga in på [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-127">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with your Global admin credentials.</span></span>
2. <span data-ttu-id="6d0c2-128">Gå till [egenskaper för Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="6d0c2-128">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="6d0c2-129">Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-129">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="6d0c2-130">Välj **Ja** för att aktivera säkerhetsstandardinställningar och **Nej** för att inaktivera dem.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-130">Choose **Yes** to enable security defaults and **No** to disable security defaults.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="6d0c2-131">Flytta från baslinje riktlinjer till säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="6d0c2-131">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="6d0c2-132">I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) väljer du **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-132">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Setup**.</span></span>

2. <span data-ttu-id="6d0c2-133">Bredvid **Inloggning och säkerhet** väljer du **Visa** för **Gör inloggningen säkrare**.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-133">Next to **Sign-in and security**, under **Make sign-in more secure**, select **View**.</span></span>

3. <span data-ttu-id="6d0c2-134">Under **Gör inloggningen säkrare** väljer du **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-134">Under **Make sign-in more secure**, select **Manage**.</span></span> 

4. <span data-ttu-id="6d0c2-135">På sidan **Villkorlig åtkomst - Principer** väljer du varje originalprincip som är **På**och ställer in dem på **Av**.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-135">On the **Conditional Access - Policies** page, choose each Baseline policy that is **On**, and set them to **Off**.</span></span>
5. <span data-ttu-id="6d0c2-136">Gå till sidan [Azure Active Directory egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="6d0c2-136">Go to [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) page.</span></span>
6. <span data-ttu-id="6d0c2-137">Längst ned på sidan väljer du **Hantera standardvärden för säkerhet**och i fönstret Aktivera säkerhet som **standard** anger du Växla till **Ja**för **säkerhet** och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-137">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="6d0c2-138">Aktivera modern autentisering för din organisation</span><span class="sxs-lookup"><span data-stu-id="6d0c2-138">Enable modern authentication for your organization</span></span>

<span data-ttu-id="6d0c2-139">Alla Office 2016-klientprogrammen har stöd för MFA genom användning av ADAL (Active Directory Authentication Library).</span><span class="sxs-lookup"><span data-stu-id="6d0c2-139">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="6d0c2-140">Det innebär att programlösenord inte är nödvändiga för Office 2016-klienter.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-140">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="6d0c2-141">Du måste dock se till att din Microsoft 365-prenumeration är aktiverad för ADAL eller modern autentisering.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-141">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="6d0c2-142">Om du vill aktivera modern autentisering väljer du **Inställningar** \> **Inställningar** i [administrationscentrat](https://go.microsoft.com/fwlink/p/?linkid=834822) och **Modern autentisering** i listan på fliken **Tjänster**.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-142">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="6d0c2-143">Markera rutan **Aktivera modern autentisering (rekommenderas)** på panelen **Modern autentisering** och välj sedan **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-143">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Panelen Modern autentisering med kryssrutan Aktivera markerad.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="6d0c2-145">Från och med augusti 2017 har alla nya Microsoft 365-prenumerationer som inkluderar Skype för företag online och Exchange online modern autentisering aktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-145">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="6d0c2-146">Om du vill kontrollera status för modern autentisering i Skype för företag – Online kan du använda Skype för företag – Online PowerShell med globala administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-146">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="6d0c2-147">Kör Get-CsOAuthConfiguration när du vill kontrollera utdata för -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-147">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="6d0c2-148">Om -ClientADALAuthOverride är Allowed är modern autentisering aktiverat.</span><span class="sxs-lookup"><span data-stu-id="6d0c2-148">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="6d0c2-149">Om du vill kontrollera MA-status för Exchange Online går du till [Aktivera modern autentisering i Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="6d0c2-149">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="6d0c2-150">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6d0c2-150">Related articles</span></span>

[<span data-ttu-id="6d0c2-151">Topp 10 sätt att säkra Microsoft 365 för affärsplaner</span><span class="sxs-lookup"><span data-stu-id="6d0c2-151">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="6d0c2-152">Aktivera modern autentisering för Office 2013 på Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="6d0c2-152">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
