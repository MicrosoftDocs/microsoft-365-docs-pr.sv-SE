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
localization_priority: Priority
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
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083544"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="4d704-103">Konfigurera multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="4d704-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="4d704-104">Eftersom du har kunskap om [multifaktorautentisering (MFA) och dess stöd i Microsoft 365](multi-factor-authentication-microsoft-365.md) är det dags att konfigurera och distribuera det i din organisation.</span><span class="sxs-lookup"><span data-stu-id="4d704-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="4d704-105">Innan du börjar kontrollerar du om dessa särskilda villkor gäller för dig och vidtar lämpliga åtgärder:</span><span class="sxs-lookup"><span data-stu-id="4d704-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="4d704-106">Om du har Office 2013-klienter på Windows-enheter kan du [aktivera modern autentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="4d704-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="4d704-107">Om du har katalogtjänster från tredje part med Active Directory Federation Services (AD FS) konfigurerar du Microsoft Azure MFA-servern.</span><span class="sxs-lookup"><span data-stu-id="4d704-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="4d704-108">Mer information finns i [avancerade scenarier med Azure multifaktorautentisering och VPN-lösningar från tredje part](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).</span><span class="sxs-lookup"><span data-stu-id="4d704-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="4d704-109">Alla andra användare kommer att ombes utföra ytterligare autentisering vid behov.</span><span class="sxs-lookup"><span data-stu-id="4d704-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="4d704-110">Gå till [metod och inställningar för tvåfaktorsautentisering](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device) för mer information.</span><span class="sxs-lookup"><span data-stu-id="4d704-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="4d704-111">Steg 1: Bestäm med vilken metod användarna ska uppmanas att använda MFA. </span><span class="sxs-lookup"><span data-stu-id="4d704-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="4d704-112">Du måste vara global administratör för att kunna konfigurera eller ändra MFA.</span><span class="sxs-lookup"><span data-stu-id="4d704-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="4d704-113">Det finns tre sätt att kräva att användarna använder MFA för inloggning. Mer information finns i [MFA-support i Microsoft 365](multi-factor-authentication-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="4d704-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="4d704-114">Standardinställningar för säkerhet (rekommenderas för små företag)</span><span class="sxs-lookup"><span data-stu-id="4d704-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="4d704-115">Om du har köpt din prenumeration eller utvärderingsversion efter den 21 oktober 2019 och plötsligt uppmanas att använda MFA, betyder det att [säkerhetsstandarder](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) har aktiverats automatiskt för prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="4d704-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="4d704-116">Säkerhetsstandarder aktiveras automatiskt för alla nya Microsoft 365-prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="4d704-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="4d704-117">Det innebär att alla användare måste konfigurera multifaktorautentisering (MFA) och installera Microsoft Authenticator-appen på deras mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="4d704-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="4d704-118">Alla användare måste använda Microsoft Authenticator-appen som en extra autentiseringsmetod och äldre autentisering blockeras.</span><span class="sxs-lookup"><span data-stu-id="4d704-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="4d704-119">Principer för villkorsstyrd åtkomst (rekommenderas för företag)</span><span class="sxs-lookup"><span data-stu-id="4d704-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="4d704-120">Användare väljer den extra verifieringsmetoden när de registrerar sig för MFA.</span><span class="sxs-lookup"><span data-stu-id="4d704-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="4d704-121">Konto per användare (rekommenderas inte)</span><span class="sxs-lookup"><span data-stu-id="4d704-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="4d704-122">Användare väljer den extra verifieringsmetoden när de registrerar sig för MFA.</span><span class="sxs-lookup"><span data-stu-id="4d704-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="4d704-123">Steg 2.</span><span class="sxs-lookup"><span data-stu-id="4d704-123">Step 2.</span></span> <span data-ttu-id="4d704-124">Testa MFA med dina pilotanvändare</span><span class="sxs-lookup"><span data-stu-id="4d704-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="4d704-125">Om du använder villkorsstyrda åtkomstprinciper eller MFA per användare (rekommenderas inte) kan du välja pilotanvändare i ditt företag eller din organisation för att testa registrering och inloggning med MFA. Exempel:</span><span class="sxs-lookup"><span data-stu-id="4d704-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="4d704-126">För villkorsstyrda åtkomstprinciper kan du skapa en grupp med pilotanvändare och en princip som kräver MFA för gruppmedlemmarna och för alla appar.</span><span class="sxs-lookup"><span data-stu-id="4d704-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="4d704-127">Lägg sedan till pilotanvändarnas användarkonton i gruppen.</span><span class="sxs-lookup"><span data-stu-id="4d704-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="4d704-128">För MFA per användare kan du aktivera MFA för pilotanvändarnas användarkonton ett i taget.</span><span class="sxs-lookup"><span data-stu-id="4d704-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="4d704-129">Arbeta tillsammans med dina pilotanvändare för att ta itu med frågor och problem och förbered för en smidig distribution i organisationen.</span><span class="sxs-lookup"><span data-stu-id="4d704-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="4d704-130">Steg 3.</span><span class="sxs-lookup"><span data-stu-id="4d704-130">Step 3.</span></span> <span data-ttu-id="4d704-131">Informera din organisation om att MFA kommer att tas i bruk</span><span class="sxs-lookup"><span data-stu-id="4d704-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="4d704-132">Använd e-postmeddelanden, affischer i korridorerna, gruppmöten eller officiella utbildningar för att säkerställa att dina anställda förstår:</span><span class="sxs-lookup"><span data-stu-id="4d704-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="4d704-133">Varför MFA krävs för inloggning</span><span class="sxs-lookup"><span data-stu-id="4d704-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="4d704-134">Så här registrerar du dig för den extra autentiseringsmetoden</span><span class="sxs-lookup"><span data-stu-id="4d704-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="4d704-135">Så här loggar du in efter registrering</span><span class="sxs-lookup"><span data-stu-id="4d704-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="4d704-136">Så här ändrar du den extra autentiseringsmetoden</span><span class="sxs-lookup"><span data-stu-id="4d704-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="4d704-137">Så här hanterar du situationer som exempelvis en ny smartphone</span><span class="sxs-lookup"><span data-stu-id="4d704-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="4d704-138">Det viktigaste är att se till att dina anställda förstår ***när MFA-kravet kommer att införas*** så att de inte blir överraskade.</span><span class="sxs-lookup"><span data-stu-id="4d704-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="4d704-139">Steg 4.</span><span class="sxs-lookup"><span data-stu-id="4d704-139">Step 4.</span></span> <span data-ttu-id="4d704-140">Distribuera kravet på MFA i din organisation eller till användarna</span><span class="sxs-lookup"><span data-stu-id="4d704-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="4d704-141">Distribuera multifaktorautentisering till de anställda utöver pilotanvändarna utifrån den metod du valt för MFA-kravet.</span><span class="sxs-lookup"><span data-stu-id="4d704-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="4d704-142">Standardinställningar för säkerhet</span><span class="sxs-lookup"><span data-stu-id="4d704-142">Security defaults</span></span>

<span data-ttu-id="4d704-143">Du aktiverar eller inaktiverar säkerhetsinställningar för Azure Active Directory (Azure AD) i Microsoft Azure-portalen från fönstret **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="4d704-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="4d704-144">Logga in som global administratör på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4d704-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="4d704-145">Gå till sidan [Azure Active Directory – Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="4d704-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="4d704-146">Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.</span><span class="sxs-lookup"><span data-stu-id="4d704-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="4d704-147">Välj **Ja** för att aktivera standardinställningar för säkerhet och **Nej** för att inaktivera dem och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4d704-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="4d704-148">Om du har använt [originalprinciper för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) gör du så här för att gå över till att använda säkerhetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="4d704-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="4d704-149">Gå till sidan [principer för villkorsstyrd åtkomst](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="4d704-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="4d704-150">Välj alla originalprinciper som är **På** och ändra **Aktivera princip** till **Av**.</span><span class="sxs-lookup"><span data-stu-id="4d704-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="4d704-151">Gå till sidan [Azure Active Directory – Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="4d704-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="4d704-152">Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.</span><span class="sxs-lookup"><span data-stu-id="4d704-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="4d704-153">Välj **Ja** för att aktivera standardinställningar för säkerhet och **Nej** för att inaktivera dem och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="4d704-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="4d704-154">Principer för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="4d704-154">Conditional Access policies</span></span>

<span data-ttu-id="4d704-155">Skapa, konfigurera och aktivera lämpliga principer som inkluderar den grupp användare som kräver MFA vid inloggning.</span><span class="sxs-lookup"><span data-stu-id="4d704-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="4d704-156">Multifaktorautentisering per användare (rekommenderas inte)</span><span class="sxs-lookup"><span data-stu-id="4d704-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="4d704-157">Aktivera användarkonton för MFA som motsvarar distributionen.</span><span class="sxs-lookup"><span data-stu-id="4d704-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="4d704-158">Stöd till dina anställda</span><span class="sxs-lookup"><span data-stu-id="4d704-158">Supporting your employees</span></span>

<span data-ttu-id="4d704-159">När dina medarbetare har registrerat sig och börjat logga in med MFA, behöver du se till att IT-experterna, IT-avdelningen och kundtjänsten kan besvara frågor och åtgärda problem snabbt.</span><span class="sxs-lookup"><span data-stu-id="4d704-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="4d704-160">I den här artikeln finns [information om hur du felsöker MFA-inloggning](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="4d704-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


