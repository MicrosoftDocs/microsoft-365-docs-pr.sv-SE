---
title: Microsoft 365-integrering med lokala miljöer
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: I den här artikeln lär du dig hur du integrerar Microsoft 365 med dina befintliga katalog tjänster och lokala miljöer.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384868"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="5491a-103">Microsoft 365-integrering med lokala miljöer</span><span class="sxs-lookup"><span data-stu-id="5491a-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="5491a-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5491a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5491a-105">Du kan integrera Microsoft 365 med din befintliga lokala Active Directory Domain Services (AD DS) och med lokala installationer av Exchange Server, Skype för företag – Server 2015 eller SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="5491a-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="5491a-106">När du integrerar AD DS kan du synkronisera och hantera användar konton i båda miljöerna.</span><span class="sxs-lookup"><span data-stu-id="5491a-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="5491a-107">Du kan också lägga till hash-synkronisering (PHS) eller enkel inloggning (SSO) så att användare kan logga in i båda miljöerna med sina lokala autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="5491a-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="5491a-108">När du integrerar med lokala server produkter skapar du en hybrid miljö.</span><span class="sxs-lookup"><span data-stu-id="5491a-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="5491a-109">En hybrid miljö kan hjälpa dig när du migrerar användare eller information till Microsoft 365, eller så kan du fortsätta att ha vissa användare eller viss information lokalt och i molnet.</span><span class="sxs-lookup"><span data-stu-id="5491a-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="5491a-110">Mer information om hybrid miljöer finns i [hybrid moln](../solutions/cloud-architecture-models.md#hybrid).</span><span class="sxs-lookup"><span data-stu-id="5491a-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="5491a-111">Du kan också använda Azure Active Directory-rådgivarena (Azure AD) för anpassade installations guider i administrations centret för Microsoft 365 (du måste vara inloggad på Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="5491a-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="5491a-112">Konfigurations guide för Azure AD</span><span class="sxs-lookup"><span data-stu-id="5491a-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="5491a-113">Synkronisera användare från organisationens katalog</span><span class="sxs-lookup"><span data-stu-id="5491a-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="5491a-114">Distributions rådgivare för Active Directory Federation Services (AD FS)</span><span class="sxs-lookup"><span data-stu-id="5491a-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="5491a-115">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="5491a-115">Before you begin</span></span>

<span data-ttu-id="5491a-116">Innan du integrerar Microsoft 365 och en lokal miljö måste du också [planera nätverks planering och prestanda justering](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="5491a-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="5491a-117">Du ska också förstå de tillgängliga [identitets modellerna](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="5491a-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="5491a-118">Se [Hantera microsoft 365-konton](manage-microsoft-365-accounts.md) för en lista med verktyg som du kan använda för att hantera Microsoft 365-användarkonton.</span><span class="sxs-lookup"><span data-stu-id="5491a-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="5491a-119">Integrera Microsoft 365 med AD DS</span><span class="sxs-lookup"><span data-stu-id="5491a-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="5491a-120">Om du har befintliga användar konton i AD DS vill du inte återskapa alla konton i Microsoft 365 och riskera att upptäcka skillnader eller fel mellan miljöerna.</span><span class="sxs-lookup"><span data-stu-id="5491a-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="5491a-121">Med katalog-synkronisering kan du spegla dessa konton mellan dina lokala och Online-miljöer.</span><span class="sxs-lookup"><span data-stu-id="5491a-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="5491a-122">Med katalog synkronisering behöver dina användare inte komma ihåg ny information för varje miljö, och du behöver inte skapa eller uppdatera konton två gånger.</span><span class="sxs-lookup"><span data-stu-id="5491a-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="5491a-123">Du måste [förbereda den lokala katalogen](prepare-for-directory-synchronization.md) för Active Directory-synkronisering.</span><span class="sxs-lookup"><span data-stu-id="5491a-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Använda katalog-synkronisering för att hålla lokala uppgifter synkroniserade och online](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="5491a-125">Om du vill att användarna ska kunna logga in på Microsoft 365 med sina lokala autentiseringsuppgifter kan du också konfigurera SSO.</span><span class="sxs-lookup"><span data-stu-id="5491a-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="5491a-126">Med SSO är Microsoft 365 konfigurerat för att lita på den lokala miljön för användarautentisering.</span><span class="sxs-lookup"><span data-stu-id="5491a-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Med enkel inloggning är samma konto tillgängligt i både lokala och Online-miljöer](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="5491a-128">Katalog-synkronisering med eller utan hashvärden för lösen ord eller direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="5491a-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="5491a-129">En användare loggar in på den lokala miljön med sitt användar konto (domän \ användar namn).</span><span class="sxs-lookup"><span data-stu-id="5491a-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="5491a-130">När de går till Microsoft 365 måste de logga in igen med sitt arbets-eller skol konto (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="5491a-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="5491a-131">Användar namnet är detsamma i båda miljöerna.</span><span class="sxs-lookup"><span data-stu-id="5491a-131">The user name is the same in both environments.</span></span> <span data-ttu-id="5491a-132">När du lägger till PHS eller PTA har användaren samma lösen ord för båda miljöerna, men kommer att behöva uppge dessa autentiseringsuppgifter igen när de loggar in i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5491a-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="5491a-133">Katalog-synkronisering med PHS är den vanligaste katalog synkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="5491a-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="5491a-134">Om du vill konfigurera profilsynkronisering använder du Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="5491a-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="5491a-135">Anvisningar finns i [Konfigurera katalog synkronisering för Microsoft 365](set-up-directory-synchronization.md) och [Azure AD Connect med snabb inställningar](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span><span class="sxs-lookup"><span data-stu-id="5491a-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="5491a-136">Läs mer om [att förbereda en katalog-synkronisering till Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="5491a-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="5491a-137">Katalog-synkronisering med SSO</span><span class="sxs-lookup"><span data-stu-id="5491a-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="5491a-138">En användare loggar in på sin lokala miljö med sitt användar konto.</span><span class="sxs-lookup"><span data-stu-id="5491a-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="5491a-139">När de går till Microsoft 365 är de antingen loggade in automatiskt, eller så loggar de in med samma inloggnings uppgifter som de använder för sin lokala miljö (domän \ användar namn).</span><span class="sxs-lookup"><span data-stu-id="5491a-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="5491a-140">För att ställa in SSO kan du även använda Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="5491a-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="5491a-141">Anvisningar finns i [anpassad installation av Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="5491a-141">For instructions, see [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="5491a-142">Mer information finns i [enkel inloggning](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="5491a-142">For more information, see [single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="5491a-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="5491a-143">Azure AD Connect</span></span>

<span data-ttu-id="5491a-144">Azure AD Connect ersätter äldre versioner av verktyg för identitets integrering, till exempel DirSync och Azure AD-synkronisering. Om du vill uppdatera från Azure Active Directory-synkronisering till Azure AD Connect kan du läsa [uppgraderings anvisningarna](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="5491a-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

## <a name="see-also"></a><span data-ttu-id="5491a-145">Se även</span><span class="sxs-lookup"><span data-stu-id="5491a-145">See also</span></span>

[<span data-ttu-id="5491a-146">Översikt över Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5491a-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
