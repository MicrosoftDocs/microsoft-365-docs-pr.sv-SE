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
ms.openlocfilehash: c4ea6037b34d29f2d1e05e248e03e49ee6b06f56
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262381"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="aaeea-103">Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="aaeea-103">Set up multi-factor authentication</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="aaeea-104">Om du har köpt din prenumeration eller utvärderingsversion efter den 21 oktober 2019 och du oväntat uppmanas att korrigera flera faktorer har [säkerhetsinställningarna aktiverats](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatiskt för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="aaeea-104">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for multi-factor authentication (MFA), [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>

<span data-ttu-id="aaeea-105">Varje ny Microsoft 365-prenumeration har automatiskt [aktiverat säkerhetsstandarder.](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="aaeea-105">Every new Microsoft 365 subscription will automatically have [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) turned on.</span></span> <span data-ttu-id="aaeea-106">Det innebär att alla användare måste konfigurera MFA (Multi Factor Authentication) och installera Microsoft Authenticator-appen på sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="aaeea-106">This means that every user will have to set up multi-factor authentication (MFA) and install the Microsoft Authenticator app on their mobile device.</span></span> <span data-ttu-id="aaeea-107">Mer information finns i [Konfigurera MFA för ett Microsoft 365-konto](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span><span class="sxs-lookup"><span data-stu-id="aaeea-107">For more information, see [Set up MFA for a Microsoft 365 account](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).</span></span>

<span data-ttu-id="aaeea-108">Följande nio administratörsroller måste utföra ytterligare autentisering varje gång de loggar in:</span><span class="sxs-lookup"><span data-stu-id="aaeea-108">The following nine administrator roles will be required to perform additional authentication every time they sign in:</span></span>

- <span data-ttu-id="aaeea-109">Global administratör</span><span class="sxs-lookup"><span data-stu-id="aaeea-109">Global administrator</span></span>
- <span data-ttu-id="aaeea-110">SharePoint-administratör</span><span class="sxs-lookup"><span data-stu-id="aaeea-110">SharePoint administrator</span></span>
- <span data-ttu-id="aaeea-111">Exchange-administratör</span><span class="sxs-lookup"><span data-stu-id="aaeea-111">Exchange administrator</span></span>
- <span data-ttu-id="aaeea-112">Administratör för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="aaeea-112">Conditional Access administrator</span></span>
- <span data-ttu-id="aaeea-113">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="aaeea-113">Security administrator</span></span>
- <span data-ttu-id="aaeea-114">Kundtjänstadministratör eller lösenordsadministratör</span><span class="sxs-lookup"><span data-stu-id="aaeea-114">Helpdesk administrator or password administrator</span></span>
- <span data-ttu-id="aaeea-115">Faktureringsadministratör</span><span class="sxs-lookup"><span data-stu-id="aaeea-115">Billing administrator</span></span>
- <span data-ttu-id="aaeea-116">Användaradministratör</span><span class="sxs-lookup"><span data-stu-id="aaeea-116">User administrator</span></span>
- <span data-ttu-id="aaeea-117">Administratör av autentisering</span><span class="sxs-lookup"><span data-stu-id="aaeea-117">Authentication administrator</span></span>

<span data-ttu-id="aaeea-118">Alla andra användare kommer att ombes utföra ytterligare autentisering när det behövs.</span><span class="sxs-lookup"><span data-stu-id="aaeea-118">All other users will be asked to perform additional authentication when needed.</span></span>

> [!NOTE]
> <span data-ttu-id="aaeea-119">Du måste vara global administratör för att kunna konfigurera eller ändra MFA</span><span class="sxs-lookup"><span data-stu-id="aaeea-119">You must be a global admin to set up or modify MFA</span></span> <br><br>
> <span data-ttu-id="aaeea-120">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="aaeea-120">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

<span data-ttu-id="aaeea-121">Om du tidigare har ställt in MFA med baslinjeprinciper [måste du inaktivera dem för att aktivera säkerhetsstandarder](#move-from-baseline-policies-to-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="aaeea-121">If you have previously set up MFA with baseline policies, [you must turn them off to turn on security defaults](#move-from-baseline-policies-to-security-defaults).</span></span> <span data-ttu-id="aaeea-122">Men om du har Microsoft 365 Business eller din prenumeration innehåller [Azure Active Directory Premium P1 eller Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/)kan du också ställa in principer för villkorlig [åtkomst.](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="aaeea-122">However, if you have Microsoft 365 Business or your subscription includes [Azure Active Directory Premium P1 or Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), you can also set up [Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies.</span></span> <span data-ttu-id="aaeea-123">Om du vill använda principer för villkorlig åtkomst måste du se till att säkerhetsinställningarna är inaktiverade och [att modern autentisering](#enable-modern-authentication-for-your-organization) är aktiverad.</span><span class="sxs-lookup"><span data-stu-id="aaeea-123">To use Conditional Access policies, you need to make sure security defaults are disabled and [modern authentication](#enable-modern-authentication-for-your-organization) is enabled.</span></span>

> [!TIP]
> <span data-ttu-id="aaeea-124">Mer om hur du konfigurerar Microsoft Authenticator-appen finns i [Använda Microsoft Authenticator med Office 365.](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411)</span><span class="sxs-lookup"><span data-stu-id="aaeea-124">To explain to your users how to set up the Microsoft Authenticator app, see [Use Microsoft Authenticator with Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).</span></span>

## <a name="manage-security-defaults"></a><span data-ttu-id="aaeea-125">Hantera säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="aaeea-125">Manage security defaults</span></span>

1. <span data-ttu-id="aaeea-126">Logga in på [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=834822) som global administratör.</span><span class="sxs-lookup"><span data-stu-id="aaeea-126">Sign in to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822) with global admin credentials.</span></span>
2. <span data-ttu-id="aaeea-127">Gå till [sidan Azure Active Directory - Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="aaeea-127">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3. <span data-ttu-id="aaeea-128">Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.</span><span class="sxs-lookup"><span data-stu-id="aaeea-128">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4. <span data-ttu-id="aaeea-129">Välj **Ja** om du vill aktivera standardvärden för säkerhet och **Nej** om du vill inaktivera standardvärden för säkerhet och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="aaeea-129">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

## <a name="move-from-baseline-policies-to-security-defaults"></a><span data-ttu-id="aaeea-130">Flytta från baslinje riktlinjer till säkerhetsstandarder</span><span class="sxs-lookup"><span data-stu-id="aaeea-130">Move from baseline policies to security defaults</span></span>

1. <span data-ttu-id="aaeea-131">Gå till [sidan Villkorlig åtkomst - Principer](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="aaeea-131">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2. <span data-ttu-id="aaeea-132">Välj varje baslinjeprincip som är **På** och ange **Aktivera princip** till **Av**.</span><span class="sxs-lookup"><span data-stu-id="aaeea-132">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
3. <span data-ttu-id="aaeea-133">Gå till [sidan Azure Active Directory - Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="aaeea-133">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4. <span data-ttu-id="aaeea-134">Längst ned på sidan väljer du **Hantera standardvärden för säkerhet**och i fönstret Aktivera säkerhet som **standard** anger du Växla till **Ja**för **säkerhet** och väljer sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="aaeea-134">On the bottom of the page, choose **Manage Security defaults**, and in the **Enable Security defaults** pane, set **Enable Security defaults** toggle to **Yes**, and then choose **Save**.</span></span> 

## <a name="enable-modern-authentication-for-your-organization"></a><span data-ttu-id="aaeea-135">Aktivera modern autentisering för din organisation</span><span class="sxs-lookup"><span data-stu-id="aaeea-135">Enable modern authentication for your organization</span></span>

<span data-ttu-id="aaeea-136">Alla Office 2016-klientprogrammen har stöd för MFA genom användning av ADAL (Active Directory Authentication Library).</span><span class="sxs-lookup"><span data-stu-id="aaeea-136">All Office 2016 client applications support MFA through the use of the Active Directory Authentication Library (ADAL).</span></span> <span data-ttu-id="aaeea-137">Det innebär att programlösenord inte är nödvändiga för Office 2016-klienter.</span><span class="sxs-lookup"><span data-stu-id="aaeea-137">This means that app passwords aren't required for Office 2016 clients.</span></span> <span data-ttu-id="aaeea-138">Se [den här artikeln](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) för mer information.</span><span class="sxs-lookup"><span data-stu-id="aaeea-138">See [this article](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) for more information.</span></span>

<span data-ttu-id="aaeea-139">Du måste dock se till att din Microsoft 365-prenumeration är aktiverad för ADAL eller modern autentisering.</span><span class="sxs-lookup"><span data-stu-id="aaeea-139">However, you need to make sure your Microsoft 365 subscription is enabled for ADAL, or modern authentication.</span></span>

1. <span data-ttu-id="aaeea-140">Om du vill aktivera modern autentisering **väljer** du Moderna autentisering i listan i [administrationscentret.](https://go.microsoft.com/fwlink/p/?linkid=834822) \> **Org Settings** **Services** **Modern authentication**</span><span class="sxs-lookup"><span data-stu-id="aaeea-140">To enable modern authentication, from the [admin center](https://go.microsoft.com/fwlink/p/?linkid=834822), select **Settings** \> **Org Settings** and then in the **Services** tab, choose **Modern authentication** from the list.</span></span>

2. <span data-ttu-id="aaeea-141">Markera rutan **Aktivera modern autentisering (rekommenderas)** på panelen **Modern autentisering** och välj sedan **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="aaeea-141">Check the **Enable modern authentication (recommended)** box in the **Modern authentication** panel, and then choose **Save changes**.</span></span> 

    ![Panelen Modern autentisering med kryssrutan Aktivera markerad.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> <span data-ttu-id="aaeea-143">Från och med augusti 2017 har alla nya Microsoft 365-prenumerationer som inkluderar Skype för företag online och Exchange online modern autentisering aktiverade som standard.</span><span class="sxs-lookup"><span data-stu-id="aaeea-143">As of August of 2017, all new Microsoft 365 subscriptions that include Skype for Business online and Exchange online have modern authentication enabled by default.</span></span> <span data-ttu-id="aaeea-144">Om du vill kontrollera status för modern autentisering i Skype för företag – Online kan du använda Skype för företag – Online PowerShell med globala administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="aaeea-144">To check your modern authentication status for Skype for Business online, you can use Skype for Business online PowerShell with Global Admin credentials.</span></span> <span data-ttu-id="aaeea-145">Kör Get-CsOAuthConfiguration när du vill kontrollera utdata för -ClientADALAuthOverride.</span><span class="sxs-lookup"><span data-stu-id="aaeea-145">Run Get-CsOAuthConfiguration to check the output of -ClientADALAuthOverride.</span></span> <span data-ttu-id="aaeea-146">Om -ClientADALAuthOverride är Allowed är modern autentisering aktiverat.</span><span class="sxs-lookup"><span data-stu-id="aaeea-146">If -ClientADALAuthOverride is 'Allowed', modern authentication is on.</span></span>
<span data-ttu-id="aaeea-147">Om du vill kontrollera MA-status för Exchange Online går du till [Aktivera modern autentisering i Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="aaeea-147">To check your MA status for Exchange Online, please visit [Enable modern authentication in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).</span></span>

## <a name="related-articles"></a><span data-ttu-id="aaeea-148">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="aaeea-148">Related articles</span></span>

[<span data-ttu-id="aaeea-149">Topp 10 sätt att säkra Microsoft 365 för affärsplaner</span><span class="sxs-lookup"><span data-stu-id="aaeea-149">Top 10 ways to secure Microsoft 365 for business plans</span></span>](secure-your-business-data.md)

[<span data-ttu-id="aaeea-150">Aktivera modern autentisering för Office 2013 på Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="aaeea-150">Enable Modern Authentication for Office 2013 on Windows devices</span></span>](enable-modern-authentication.md)
