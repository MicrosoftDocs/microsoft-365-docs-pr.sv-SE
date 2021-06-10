---
title: Microsoft 365 med lokala miljöer
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
description: I den här artikeln lär du dig att Microsoft 365 med befintliga katalogtjänster och lokala miljöer.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923972"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="c9572-103">Microsoft 365 med lokala miljöer</span><span class="sxs-lookup"><span data-stu-id="c9572-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="c9572-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c9572-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c9572-105">Du kan Microsoft 365 med din befintliga lokala AD DS (Active Directory Domain Services) och med lokala installationer av Exchange Server, Skype för företag – Server 2015 eller SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="c9572-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="c9572-106">När du integrerar AD DS kan du synkronisera och hantera användarkonton för båda miljöerna.</span><span class="sxs-lookup"><span data-stu-id="c9572-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="c9572-107">Du kan också lägga till synkronisering av lösenordshashar (PHS) eller enkel inloggning (SSO) så att användarna kan logga in på båda miljöerna med sina lokala inloggningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c9572-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="c9572-108">När du integrerar med lokala serverprodukter skapar du en hybridmiljö.</span><span class="sxs-lookup"><span data-stu-id="c9572-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="c9572-109">En hybridmiljö kan vara till hjälp när du migrerar användare eller information till Microsoft 365, eller så kan du fortsätta att låta vissa användare eller viss information vara lokalt medan en del finns i molnet.</span><span class="sxs-lookup"><span data-stu-id="c9572-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="c9572-110">Mer information om hybridmiljöer finns i [hybridmoln](../solutions/cloud-architecture-models.md#hybrid).</span><span class="sxs-lookup"><span data-stu-id="c9572-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="c9572-111">Du kan också använda Azure Active Directory-rådgivare (Azure AD) för anpassad konfigurationsvägledning i administrationscentret för Microsoft 365 (du måste vara inloggad på Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="c9572-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="c9572-112">Konfigurationsguide för Azure AD</span><span class="sxs-lookup"><span data-stu-id="c9572-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="c9572-113">Synkronisera användare från organisationens katalog</span><span class="sxs-lookup"><span data-stu-id="c9572-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="c9572-114">Distributionsrådgivaren för AD FS (Active Directory Federation Services)</span><span class="sxs-lookup"><span data-stu-id="c9572-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="c9572-115">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="c9572-115">Before you begin</span></span>

<span data-ttu-id="c9572-116">Innan du Microsoft 365 nätverksplanering och en lokal miljö måste du också planera [och finjustera nätverksprestanda.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="c9572-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="c9572-117">Du bör också förstå vilka [identitetsmodeller som är tillgängliga.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="c9572-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="c9572-118">I [Hantera Microsoft 365-konton](manage-microsoft-365-accounts.md) finns en lista över verktyg som du kan använda för Microsoft 365-användarkonton.</span><span class="sxs-lookup"><span data-stu-id="c9572-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="c9572-119">Integrera Microsoft 365 med AD DS</span><span class="sxs-lookup"><span data-stu-id="c9572-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="c9572-120">Om du har befintliga användarkonton i AD DS vill du inte skapa alla dessa konton på nytt i Microsoft 365 och riskera att introducera skillnader eller fel mellan miljöerna.</span><span class="sxs-lookup"><span data-stu-id="c9572-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="c9572-121">Katalogsynkronisering hjälper dig att spegla dessa konton mellan dina lokala miljöer och onlinemiljöer.</span><span class="sxs-lookup"><span data-stu-id="c9572-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="c9572-122">Med katalogsynkronisering behöver användarna inte komma ihåg ny information för varje miljö, och du behöver inte skapa eller uppdatera konton två gånger.</span><span class="sxs-lookup"><span data-stu-id="c9572-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="c9572-123">Du måste förbereda [den lokala katalogen för katalogsynkronisering.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="c9572-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Använda katalogsynkronisering för att hålla lokal information synkroniserad med information för onlineanvändarkontot](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="c9572-125">Om du vill att användarna ska kunna logga in på Microsoft 365 med sina lokala autentiseringsuppgifter kan du också konfigurera SSO.</span><span class="sxs-lookup"><span data-stu-id="c9572-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="c9572-126">Med SSO Microsoft 365 att lita på den lokala miljön för användarautentisering.</span><span class="sxs-lookup"><span data-stu-id="c9572-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Med enkel inloggning är samma konto tillgängligt i både lokal miljö och online](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="c9572-128">Katalogsynkronisering med eller utan synkronisering av lösenordshashar eller direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="c9572-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="c9572-129">Användarna loggar in i den lokala miljön med sitt användarkonto (domän\användarnamn).</span><span class="sxs-lookup"><span data-stu-id="c9572-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="c9572-130">När de går till Microsoft 365 måste de logga in igen med sitt arbets- eller skolkonto (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="c9572-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="c9572-131">Användarnamnet är samma i båda miljöerna.</span><span class="sxs-lookup"><span data-stu-id="c9572-131">The user name is the same in both environments.</span></span> <span data-ttu-id="c9572-132">När du lägger till PHS eller PTA har användaren samma lösenord för båda miljöerna, men kommer att behöva ange de uppgifterna igen när du loggar in på Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9572-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="c9572-133">Katalogsynkronisering med PHS är den vanligaste katalogsynkroniseringen.</span><span class="sxs-lookup"><span data-stu-id="c9572-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="c9572-134">Om du vill konfigurera katalogsynkronisering använder du Azure AD Anslut.</span><span class="sxs-lookup"><span data-stu-id="c9572-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="c9572-135">Anvisningar finns i Konfigurera [katalogsynkronisering för Microsoft 365](set-up-directory-synchronization.md) och [Azure AD Anslut med standardinställningar.](/azure/active-directory/hybrid/how-to-connect-install-express)</span><span class="sxs-lookup"><span data-stu-id="c9572-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

<span data-ttu-id="c9572-136">Läs mer om att [förbereda för katalogsynkronisering för Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="c9572-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="c9572-137">Katalogsynkronisering med SSO</span><span class="sxs-lookup"><span data-stu-id="c9572-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="c9572-138">Användarna loggar in i den lokala miljön med sitt användarkonto.</span><span class="sxs-lookup"><span data-stu-id="c9572-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="c9572-139">När de går till Microsoft 365 loggas de antingen in automatiskt eller så loggar de in med samma inloggningsuppgifter som de använder för den lokala miljön (domän\användarnamn).</span><span class="sxs-lookup"><span data-stu-id="c9572-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="c9572-140">Om du vill konfigurera SSO använder du även Azure AD Anslut.</span><span class="sxs-lookup"><span data-stu-id="c9572-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="c9572-141">Anvisningar finns i Anpassad [installation av Azure AD Anslut.](/azure/active-directory/hybrid/how-to-connect-install-custom)</span><span class="sxs-lookup"><span data-stu-id="c9572-141">For instructions, see [Custom installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>

<span data-ttu-id="c9572-142">Mer information finns i [enkel inloggning](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="c9572-142">For more information, see [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="c9572-143">Azure AD-Anslut</span><span class="sxs-lookup"><span data-stu-id="c9572-143">Azure AD Connect</span></span>

<span data-ttu-id="c9572-144">Azure AD Anslut äldre versioner av identitetsintegreringsverktyg, till exempel DirSync och Azure AD Sync. Om du vill uppdatera från Azure Active Directory till Azure AD Anslut följer [du uppgraderingsanvisningarna](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span><span class="sxs-lookup"><span data-stu-id="c9572-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span></span> 

## <a name="see-also"></a><span data-ttu-id="c9572-145">Se även</span><span class="sxs-lookup"><span data-stu-id="c9572-145">See also</span></span>

[<span data-ttu-id="c9572-146">Microsoft 365 Enterprise översikt</span><span class="sxs-lookup"><span data-stu-id="c9572-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)