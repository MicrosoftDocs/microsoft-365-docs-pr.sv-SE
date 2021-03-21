---
title: Konfigurera katalogsynkronisering för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Lär dig konfigurera katalogsynkronisering mellan Microsoft 365 och din lokala Active Directory.
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924910"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="cf8b6-103">Konfigurera katalogsynkronisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf8b6-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="cf8b6-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="cf8b6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="cf8b6-105">Microsoft 365 använder en Azure Active Directory-klientorganisation (Azure AD) för att lagra och hantera identiteter för autentisering och behörigheter för åtkomst till molnbaserade resurser.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="cf8b6-106">Om du har en lokal AD DS-domän (Active Directory Domain Services) eller skog kan du synkronisera dina AD DS-användarkonton, grupper och kontakter med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-106">If you have an on-premises Active Directory Domain Services (AD DS) domain or forest, you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="cf8b6-107">Det här är en hybrididentitet för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="cf8b6-108">Här är dess komponenter.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-108">Here are its components.</span></span>

![Komponenter i katalogsynkronisering för Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="cf8b6-110">Azure AD Connect körs på en lokal server och synkroniserar din AD DS med Azure AD-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="cf8b6-111">Tillsammans med katalogsynkronisering kan du också ange följande autentiseringsalternativ:</span><span class="sxs-lookup"><span data-stu-id="cf8b6-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="cf8b6-112">Synkronisering av lösenordshashar (PHS)</span><span class="sxs-lookup"><span data-stu-id="cf8b6-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="cf8b6-113">Azure AD utför själva autentiseringen.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="cf8b6-114">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="cf8b6-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="cf8b6-115">Azure AD har AD DS som utför autentiseringen.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="cf8b6-116">Federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="cf8b6-116">Federated authentication</span></span>

  <span data-ttu-id="cf8b6-117">Azure AD refererar klientdatorn och begär autentisering till en annan identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-117">Azure AD refers the client computer requesting authentication to another identity provider.</span></span>

<span data-ttu-id="cf8b6-118">Mer information [finns i Hybrididentiteter.](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="cf8b6-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="cf8b6-119">1. Granska kraven för Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="cf8b6-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="cf8b6-120">Du får en kostnadsfri Azure AD-prenumeration med din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="cf8b6-121">När du installerar katalogsynkronisering installerar du Azure AD Connect på någon av dina lokala servrar.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="cf8b6-122">För Microsoft 365 måste du:</span><span class="sxs-lookup"><span data-stu-id="cf8b6-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="cf8b6-123">Verifiera din lokala domän.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-123">Verify your on-premises domain.</span></span> <span data-ttu-id="cf8b6-124">Azure AD Connect-guiden vägleder dig genom detta.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="cf8b6-125">Få användarnamn och lösenord för administratörskontona för din Microsoft 365-klientorganisation och AD DS.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="cf8b6-126">För den lokala server där du installerar Azure AD Connect behöver du:</span><span class="sxs-lookup"><span data-stu-id="cf8b6-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="cf8b6-127">**Serveroperativsystem**</span><span class="sxs-lookup"><span data-stu-id="cf8b6-127">**Server OS**</span></span>|<span data-ttu-id="cf8b6-128">**Annan programvara**</span><span class="sxs-lookup"><span data-stu-id="cf8b6-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf8b6-129">Windows Server 2012 R2 och senare</span><span class="sxs-lookup"><span data-stu-id="cf8b6-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="cf8b6-130">- PowerShell installeras som standard, ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="cf8b6-131">- Net 4.5.1 och senare versioner erbjuds via Windows Update.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="cf8b6-132">Kontrollera att du har installerat de senaste uppdateringarna för Windows Server i Kontrollpanelen.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="cf8b6-133">Windows Server 2008 R2 med Service Pack 1 (SP1)\*\* eller Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="cf8b6-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="cf8b6-134">– Den senaste versionen av PowerShell är tillgänglig i Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="cf8b6-135">Sök efter den på [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="cf8b6-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="cf8b6-136">- .Net 4.5.1 och senare versioner finns på [Microsoft Download Center.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="cf8b6-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="cf8b6-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="cf8b6-137">Windows Server 2008</span></span> | <span data-ttu-id="cf8b6-138">- Den senaste versionen av PowerShell som stöds finns i Windows Management Framework 3.0, tillgänglig på [Microsoft Download Center.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="cf8b6-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="cf8b6-139">- .Net 4.5.1 och senare versioner finns på [Microsoft Download Center.](https://go.microsoft.com/fwlink/p/?LinkId=717996)</span><span class="sxs-lookup"><span data-stu-id="cf8b6-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="cf8b6-140">Se Krav för Azure Active Directory Connect för information om maskinvara, programvara, konto- och [behörighetskrav,](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) SSL-certifikatkrav och objektbegränsningar för Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-140">See [Prerequisites for Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="cf8b6-141">Du kan också läsa versionshistoriken för Azure AD Connect [om](/azure/active-directory/hybrid/reference-connect-version-history) du vill se vad som ingår och korrigerats i varje version.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-141">You can also review the Azure AD Connect [version release history](/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="cf8b6-142">2. Installera Azure AD Connect och konfigurera katalogsynkronisering</span><span class="sxs-lookup"><span data-stu-id="cf8b6-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="cf8b6-143">Innan du börjar kontrollerar du att du har:</span><span class="sxs-lookup"><span data-stu-id="cf8b6-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="cf8b6-144">Användarnamn och lösenord för en global Microsoft 365-administratör</span><span class="sxs-lookup"><span data-stu-id="cf8b6-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="cf8b6-145">Användarnamnet och lösenordet för en AD DS-domänadministratör</span><span class="sxs-lookup"><span data-stu-id="cf8b6-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="cf8b6-146">Vilken autentiseringsmetod (PHS, PTA, federerad)</span><span class="sxs-lookup"><span data-stu-id="cf8b6-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="cf8b6-147">Om du vill använda [sömlös enkel inloggning (SSO) i Azure AD](/azure/active-directory/hybrid/how-to-connect-sso)</span><span class="sxs-lookup"><span data-stu-id="cf8b6-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="cf8b6-148">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="cf8b6-148">Follow these steps:</span></span>

1. <span data-ttu-id="cf8b6-149">Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com) ( https://admin.microsoft.com) och välj Aktiva **användare** \> **i** det vänstra navigeringsfältet.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="cf8b6-150">På sidan **Aktiva användare** väljer du **Mer** (tre punkter) \> **Katalogsynkronisering**.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="cf8b6-151">På **förberedelsesidan för Azure Active Directory** väljer du Gå till Download Center för att få länken till Azure AD **Connect-verktyget** för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="cf8b6-152">Följ stegen i [installationsöversikten för Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-roadmap)och Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="cf8b6-153">3. Slutföra domäninstallationen</span><span class="sxs-lookup"><span data-stu-id="cf8b6-153">3. Finish setting up domains</span></span>

<span data-ttu-id="cf8b6-154">Följ stegen i Skapa [DNS-poster för Microsoft 365 när](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) du hanterar dina DNS-poster för att slutföra domänerna.</span><span class="sxs-lookup"><span data-stu-id="cf8b6-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="cf8b6-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="cf8b6-155">Next step</span></span>

[<span data-ttu-id="cf8b6-156">Tilldela licenser till användarkonton</span><span class="sxs-lookup"><span data-stu-id="cf8b6-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)