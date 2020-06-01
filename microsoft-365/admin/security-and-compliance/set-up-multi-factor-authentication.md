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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Lär dig hur du konfigurerar multifaktorautentisering för din organisation.
monikerRange: o365-worldwide
ms.openlocfilehash: c84c66cc051363fbc582abfb5521f922440b6801
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432385"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="b94f7-103">Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="b94f7-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="b94f7-104">Baserat på din förståelse av [MFA (Multi Factor Authentication) och dess stöd i Microsoft 365](multi-factor-authentication-microsoft-365.md)är det dags att konfigurera den och distribuera den till din organisation.</span><span class="sxs-lookup"><span data-stu-id="b94f7-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="b94f7-105">Innan du börjar, ta reda på om dessa särskilda villkor gäller för dig och vidta lämpliga åtgärder:</span><span class="sxs-lookup"><span data-stu-id="b94f7-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="b94f7-106">Om du har Office 2013-klienter på Windows-enheter [aktiverar du Modern autentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="b94f7-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="b94f7-107">Om du har katalogtjänster från tredje part med Active Directory Federation Services (AD FS) konfigurerar du Azure MFA Server.</span><span class="sxs-lookup"><span data-stu-id="b94f7-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="b94f7-108">Mer information finns i [avancerade scenarier med Azure Multi-Factor Authentication och VPN-lösningar från tredje part.](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)</span><span class="sxs-lookup"><span data-stu-id="b94f7-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="b94f7-109">Steg 1: Bestäm metoden för att kräva att användarna använder MFA</span><span class="sxs-lookup"><span data-stu-id="b94f7-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="b94f7-110">Du måste vara global administratör för att kunna konfigurera eller ändra MFA.</span><span class="sxs-lookup"><span data-stu-id="b94f7-110">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="b94f7-111">Det finns tre sätt att kräva att användarna använder MFA för inloggningar. Mer information finns [i MFA-supporten i Microsoft 365.](multi-factor-authentication-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="b94f7-111">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="b94f7-112">Standardvärden för säkerhet (rekommenderas för småföretag)</span><span class="sxs-lookup"><span data-stu-id="b94f7-112">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="b94f7-113">Om du har köpt din prenumeration eller utvärderingsversion efter den 21 oktober 2019 och du oväntat uppmanas att ange MFA har [säkerhetsinställningarna aktiverats](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatiskt för din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="b94f7-113">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="b94f7-114">Varje ny Microsoft 365-prenumeration har automatiskt aktiverat säkerhetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="b94f7-114">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="b94f7-115">Det innebär att alla användare måste konfigurera MFA och installera Microsoft Authenticator-appen på sin mobila enhet.</span><span class="sxs-lookup"><span data-stu-id="b94f7-115">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="b94f7-116">Alla användare måste använda Microsoft Authenticator-appen eftersom deras ytterligare verifieringsmetod och äldre autentisering blockeras.</span><span class="sxs-lookup"><span data-stu-id="b94f7-116">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="b94f7-117">Principer för villkorlig åtkomst (rekommenderas för företag)</span><span class="sxs-lookup"><span data-stu-id="b94f7-117">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="b94f7-118">Användare väljer ytterligare verifieringsmetod under MFA-registrering.</span><span class="sxs-lookup"><span data-stu-id="b94f7-118">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="b94f7-119">Per användarkonto (rekommenderas inte)</span><span class="sxs-lookup"><span data-stu-id="b94f7-119">Per-user account (not recommended)</span></span>

  <span data-ttu-id="b94f7-120">Användare väljer ytterligare verifieringsmetod under MFA-registrering.</span><span class="sxs-lookup"><span data-stu-id="b94f7-120">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="b94f7-121">Steg 2.</span><span class="sxs-lookup"><span data-stu-id="b94f7-121">Step 2.</span></span> <span data-ttu-id="b94f7-122">Testa MFA på dina pilotanvändare</span><span class="sxs-lookup"><span data-stu-id="b94f7-122">Test MFA on your pilot users</span></span>

<span data-ttu-id="b94f7-123">Om du använder principer för villkorlig åtkomst eller MFA (rekommenderas inte för användare) väljer du pilotanvändare i ditt företag eller din organisation för att testa MFA-registrering och inloggningar. Till exempel:</span><span class="sxs-lookup"><span data-stu-id="b94f7-123">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="b94f7-124">För principer för villkorlig åtkomst skapar du en pilotanvändargrupp och en princip som kräver MFA för medlemmarna i gruppen och för alla appar.</span><span class="sxs-lookup"><span data-stu-id="b94f7-124">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="b94f7-125">Lägg sedan till pilotanvändarens konton i gruppen.</span><span class="sxs-lookup"><span data-stu-id="b94f7-125">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="b94f7-126">För MFA per användare aktiverar du MFA för pilotanvändarnas användarkonton en gång.</span><span class="sxs-lookup"><span data-stu-id="b94f7-126">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="b94f7-127">Arbeta med pilotanvändarna för att ta itu med frågor och problem för att förbereda en smidig utrullning till din organisation.</span><span class="sxs-lookup"><span data-stu-id="b94f7-127">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="b94f7-128">Steg 3.</span><span class="sxs-lookup"><span data-stu-id="b94f7-128">Step 3.</span></span> <span data-ttu-id="b94f7-129">Informera din organisation om att MFA kommer</span><span class="sxs-lookup"><span data-stu-id="b94f7-129">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="b94f7-130">Använd e-postaviseringar, hallaffischer, gruppmöten eller formell utbildning för att se till att dina anställda förstår:</span><span class="sxs-lookup"><span data-stu-id="b94f7-130">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="b94f7-131">Varför MFA krävs för inloggningar</span><span class="sxs-lookup"><span data-stu-id="b94f7-131">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="b94f7-132">Så här registrerar du dig för ytterligare verifieringsmetod</span><span class="sxs-lookup"><span data-stu-id="b94f7-132">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="b94f7-133">Så här loggar du in efter registreringen</span><span class="sxs-lookup"><span data-stu-id="b94f7-133">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="b94f7-134">Så här ändrar du sin ytterligare verifieringsmetod</span><span class="sxs-lookup"><span data-stu-id="b94f7-134">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="b94f7-135">Hur man hanterar situationer som en ny smart telefon</span><span class="sxs-lookup"><span data-stu-id="b94f7-135">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="b94f7-136">Viktigast av allt, se till att dina anställda förstår ***när MFA kravet kommer att införas*** så att det inte förvånar dem.</span><span class="sxs-lookup"><span data-stu-id="b94f7-136">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="b94f7-137">Steg 4.</span><span class="sxs-lookup"><span data-stu-id="b94f7-137">Step 4.</span></span> <span data-ttu-id="b94f7-138">Distribuera MFA-kravet till din organisation eller användare</span><span class="sxs-lookup"><span data-stu-id="b94f7-138">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="b94f7-139">Baserat på din valda MFA-kravmetod, distribuera MFA-autentisering till de anställda utanför dina pilottestare.</span><span class="sxs-lookup"><span data-stu-id="b94f7-139">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="b94f7-140">Standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="b94f7-140">Security defaults</span></span>

<span data-ttu-id="b94f7-141">Du aktiverar eller inaktiverar säkerhetsstandarder från **egenskapsfönstret** för Azure Active Directory (Azure AD) i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="b94f7-141">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="b94f7-142">Logga in på [Microsoft 365-administrationscentret](https://admin.microsoft.com) med globala administratörsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="b94f7-142">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="b94f7-143">Gå till [sidan Azure Active Directory - Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="b94f7-143">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="b94f7-144">Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.</span><span class="sxs-lookup"><span data-stu-id="b94f7-144">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="b94f7-145">Välj **Ja** om du vill aktivera standardvärden för säkerhet och **Nej** om du vill inaktivera standardvärden för säkerhet och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b94f7-145">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="b94f7-146">Om du har använt [grundläggande principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)går du vidare till att använda säkerhetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="b94f7-146">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="b94f7-147">Gå till [sidan Villkorlig åtkomst - Principer](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="b94f7-147">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="b94f7-148">Välj varje baslinjeprincip som är **På** och ange **Aktivera princip** till **Av**.</span><span class="sxs-lookup"><span data-stu-id="b94f7-148">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="b94f7-149">Gå till [sidan Azure Active Directory - Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="b94f7-149">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="b94f7-150">Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.</span><span class="sxs-lookup"><span data-stu-id="b94f7-150">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="b94f7-151">Välj **Ja** om du vill aktivera standardvärden för säkerhet och **Nej** om du vill inaktivera standardvärden för säkerhet och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b94f7-151">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="b94f7-152">Principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="b94f7-152">Conditional Access policies</span></span>

<span data-ttu-id="b94f7-153">Skapa, konfigurera och aktivera lämpliga principer som innehåller den grupp användare som kräver MFA för inloggning.</span><span class="sxs-lookup"><span data-stu-id="b94f7-153">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="b94f7-154">MFA per användare (rekommenderas inte)</span><span class="sxs-lookup"><span data-stu-id="b94f7-154">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="b94f7-155">Aktivera användarkonton för MFA som motsvarar din distribution.</span><span class="sxs-lookup"><span data-stu-id="b94f7-155">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="b94f7-156">Stöd till dina anställda</span><span class="sxs-lookup"><span data-stu-id="b94f7-156">Supporting your employees</span></span>

<span data-ttu-id="b94f7-157">När dina anställda registrerar sig och börjar logga in med MFA, se till att dina IT-specialister, IT-avdelning eller helpdesk kan svara på frågor och åtgärda problem snabbt.</span><span class="sxs-lookup"><span data-stu-id="b94f7-157">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="b94f7-158">I den här artikeln finns [information om felsökning av MFA-inloggningar](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="b94f7-158">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


