---
title: Microsoft 365-integrering med lokala miljöer
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2019
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
ms.openlocfilehash: 46f0fab6396dd1db82524ea1aeedc6894ce7ab70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694882"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="1c709-103">Microsoft 365-integrering med lokala miljöer</span><span class="sxs-lookup"><span data-stu-id="1c709-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="1c709-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1c709-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1c709-105">Du kan integrera Microsoft 365 med dina befintliga katalog tjänster och med en lokal installation av Exchange Server, Skype för företag – Server 2015 eller SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="1c709-105">You can integrate Microsoft 365 with your existing directory services and with an on-premises installation of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="1c709-106">När du integrerar med katalog tjänster kan du synkronisera och hantera användar konton för båda miljöerna.</span><span class="sxs-lookup"><span data-stu-id="1c709-106">When you integrate with directory services, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="1c709-107">Du kan också lägga till hash-synkronisering eller enkel inloggning (SSO) så att användarna kan logga in på båda miljöerna med sina lokala autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="1c709-107">You can also add password hash synchronization or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="1c709-108">När du integrerar med lokala server produkter skapar du en hybrid miljö.</span><span class="sxs-lookup"><span data-stu-id="1c709-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="1c709-109">En hybrid miljö kan hjälpa dig när du migrerar användare eller information till Microsoft 365, eller så kan du fortsätta att ha vissa användare eller viss information lokalt och i molnet.</span><span class="sxs-lookup"><span data-stu-id="1c709-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="1c709-110">Mer information om hybrid miljöer finns i [hybrid moln översikt](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="1c709-110">For more information about hybrid environments, see [Hybrid cloud overview](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span></span>

<span data-ttu-id="1c709-111">Du kan också använda Azure Active Directory-rådgivarena för anpassade installations anvisningar (du måste vara inloggad i Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="1c709-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="1c709-112">Synkronisera användare från organisationens katalog</span><span class="sxs-lookup"><span data-stu-id="1c709-112">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="1c709-113">Distributions rådgivare för AD FS</span><span class="sxs-lookup"><span data-stu-id="1c709-113">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
- [<span data-ttu-id="1c709-114">Konfigurations guide för Azure AD</span><span class="sxs-lookup"><span data-stu-id="1c709-114">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="1c709-115">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="1c709-115">Before you begin</span></span>

<span data-ttu-id="1c709-116">Innan du integrerar Microsoft 365 och en lokal miljö måste du även delta i [nätverks planering och prestanda justering](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="1c709-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to attend to [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="1c709-117">Du ska också förstå de tillgängliga [identitets modellerna](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="1c709-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="1c709-118">Information [om hur du hanterar microsoft 365-konton](manage-microsoft-365-accounts.md) för en lista över verktyg som du kan använda för att hantera Microsoft 365-användare och-konton.</span><span class="sxs-lookup"><span data-stu-id="1c709-118">See [where to manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 users and accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-directory-services"></a><span data-ttu-id="1c709-119">Integrera Microsoft 365 med katalog tjänster</span><span class="sxs-lookup"><span data-stu-id="1c709-119">Integrate Microsoft 365 with directory services</span></span>
<span data-ttu-id="1c709-120">Om du har befintliga användar konton i en lokal katalog vill du inte återskapa alla konton i Microsoft 365 och riskera att upptäcka skillnader eller fel mellan miljöerna.</span><span class="sxs-lookup"><span data-stu-id="1c709-120">If you have existing user accounts in an on-premises directory, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="1c709-121">Med katalog-synkronisering kan du spegla dessa konton mellan online och lokala miljöer.</span><span class="sxs-lookup"><span data-stu-id="1c709-121">Directory synchronization helps you mirror those accounts between your online and on-premises environments.</span></span> <span data-ttu-id="1c709-122">Med katalog synkronisering behöver dina användare inte komma ihåg ny information för varje miljö, och du behöver inte skapa eller uppdatera konton två gånger.</span><span class="sxs-lookup"><span data-stu-id="1c709-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="1c709-123">Du måste [förbereda den lokala katalogen](prepare-for-directory-synchronization.md) för Active Directory-synkronisering.</span><span class="sxs-lookup"><span data-stu-id="1c709-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Använda katalog-synkronisering för att hålla lokala uppgifter synkroniserade och online](../media/a64af0d0-9be6-46b1-8727-277e683abf5e.png)
  
<span data-ttu-id="1c709-125">Om du vill att användarna ska kunna logga in på Microsoft 365 med sina lokala autentiseringsuppgifter kan du också konfigurera SSO.</span><span class="sxs-lookup"><span data-stu-id="1c709-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="1c709-126">Med SSO är Microsoft 365 konfigurerat för att lita på den lokala miljön för användarautentisering.</span><span class="sxs-lookup"><span data-stu-id="1c709-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Med enkel inloggning är samma konto tillgängligt i både lokala och Online-miljöer](../media/d76235f2-8a53-405e-b8ef-dfa4cfc208b8.png)
  
<span data-ttu-id="1c709-128">Olika användar konto hanterings tekniker ger olika upplevelser för användarna, vilket visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="1c709-128">Different user account management techniques provide different experiences for your users, as shown in the following table.</span></span>
 
### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication"></a><span data-ttu-id="1c709-129">Katalog-synkronisering med eller utan lösen ord-hash-synkronisering eller vidarekoppling</span><span class="sxs-lookup"><span data-stu-id="1c709-129">Directory synchronization with or without password hash synchronization or pass-through authentication</span></span>

<span data-ttu-id="1c709-130">En användare loggar in på den lokala miljön med sitt användar konto (domän \ användar namn).</span><span class="sxs-lookup"><span data-stu-id="1c709-130">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="1c709-131">När de går till Microsoft 365 måste de logga in igen med sitt arbets-eller skol konto (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="1c709-131">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="1c709-132">Användar namnet är detsamma i båda miljöerna.</span><span class="sxs-lookup"><span data-stu-id="1c709-132">The user name is the same in both environments.</span></span> <span data-ttu-id="1c709-133">När du lägger till hash-synkronisering eller vidarekoppling av lösen ord har användaren samma lösen ord för båda miljöerna, men kommer att behöva uppge dessa autentiseringsuppgifter igen när de loggar in i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1c709-133">When you add password hash sync or pass-through authentication, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="1c709-134">Katalog-synkronisering med hash för lösen ord är det vanligaste scenariot för katalog synkronisering.</span><span class="sxs-lookup"><span data-stu-id="1c709-134">Directory synchronization with password hash sync is the most commonly used directory sync scenario.</span></span>

<span data-ttu-id="1c709-135">Om du vill konfigurera profilsynkronisering använder du Azure Active Directory Connect.</span><span class="sxs-lookup"><span data-stu-id="1c709-135">To set up directory synchronization, use Azure Active Directory Connect.</span></span> <span data-ttu-id="1c709-136">Anvisningar finns i [Konfigurera katalog synkronisering för Microsoft 365](set-up-directory-synchronization.md)och [Azure AD Connect med snabb inställningar](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span><span class="sxs-lookup"><span data-stu-id="1c709-136">For instructions, read [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md), and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="1c709-137">Läs mer om [att förbereda en katalog-synkronisering till Microsoft 365](prepare-for-directory-synchronization.md) och [att integrera lokala identifierings instruktioner med Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span><span class="sxs-lookup"><span data-stu-id="1c709-137">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md) and [integrating your on-premises identifies with Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="1c709-138">Katalog-synkronisering med SSO</span><span class="sxs-lookup"><span data-stu-id="1c709-138">Directory synchronization with SSO</span></span>

<span data-ttu-id="1c709-139">En användare loggar in på sin lokala miljö med sitt användar konto.</span><span class="sxs-lookup"><span data-stu-id="1c709-139">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="1c709-140">När de går till Microsoft 365 är de antingen loggade in automatiskt, eller så loggar de in med samma inloggnings uppgifter som de använder för sin lokala miljö (domän \ användar namn).</span><span class="sxs-lookup"><span data-stu-id="1c709-140">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="1c709-141">För att ställa in SSO kan du även använda Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="1c709-141">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="1c709-142">Anvisningar finns [i anpassad installation av Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="1c709-142">For instructions, read [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="1c709-143">Läs mer om [enkel inloggning till program i Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="1c709-143">Learn more about [single sign-on to applications in Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="1c709-144">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="1c709-144">Azure AD Connect</span></span>

<span data-ttu-id="1c709-145">Azure AD Connect ersätter äldre versioner av verktyg för identitets integrering, till exempel DirSync och Azure AD-synkronisering. Mer information finns i [Vad är hybrid identitet med Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span><span class="sxs-lookup"><span data-stu-id="1c709-145">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. For more information, see [What is hybrid identity with Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span></span> <span data-ttu-id="1c709-146">Om du vill uppdatera från Azure Active Directory-synkronisering till Azure AD Connect kan du läsa [uppgraderings anvisningarna](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="1c709-146">If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

<span data-ttu-id="1c709-147">Se även [distribuera Microsoft 365-profilsynkronisering i Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span><span class="sxs-lookup"><span data-stu-id="1c709-147">Also see [Deploy Microsoft 365 Directory Synchronization in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c709-148">Se även</span><span class="sxs-lookup"><span data-stu-id="1c709-148">See also</span></span>

[<span data-ttu-id="1c709-149">Översikt över Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1c709-149">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
