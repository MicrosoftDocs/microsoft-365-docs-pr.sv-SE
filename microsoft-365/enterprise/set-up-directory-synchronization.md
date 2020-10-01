---
title: Konfigurera profilsynkronisering för Microsoft 365
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
description: Lär dig hur du konfigurerar profilsynkronisering mellan Microsoft 365 och din lokala Active Directory.
ms.openlocfilehash: 308774dcdbaffc1096ab6ad144484e6920accdfa
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327099"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="2d99c-103">Konfigurera profilsynkronisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d99c-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="2d99c-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2d99c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2d99c-105">I Microsoft 365 används en Azure Active Directory-klient (Azure AD) för att lagra och hantera identiteter för att få åtkomst till molnbaserade resurser.</span><span class="sxs-lookup"><span data-stu-id="2d99c-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="2d99c-106">Om du har en lokal AD DS-domän (Active Directory Domain Services) eller en skog kan du synkronisera dina AD DS-användarkonton, grupper och kontakter med Azure AD-klient organisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="2d99c-106">If you have an on-premises Active Directory Domain Services (AD DS) domain or forest, you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="2d99c-107">Det här är hybrid identitet för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d99c-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="2d99c-108">Här är dess komponenter.</span><span class="sxs-lookup"><span data-stu-id="2d99c-108">Here are its components.</span></span>

![Komponenter i Active Directory-synkronisering för Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="2d99c-110">Azure AD Connect körs på en lokal server och synkroniserar AD DS med Azure AD-klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="2d99c-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="2d99c-111">Tillsammans med profilsynkronisering kan du även ange följande autentiseringsalternativ:</span><span class="sxs-lookup"><span data-stu-id="2d99c-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="2d99c-112">Lösenordssynkronisering för lösen ord (PHS)</span><span class="sxs-lookup"><span data-stu-id="2d99c-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="2d99c-113">Azure AD utför själva autentiseringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="2d99c-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="2d99c-114">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="2d99c-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="2d99c-115">Azure AD har AD DS utför verifikationen.</span><span class="sxs-lookup"><span data-stu-id="2d99c-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="2d99c-116">Federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="2d99c-116">Federated authentication</span></span>

  <span data-ttu-id="2d99c-117">Azure AD refererar den klient dator som begär klientautentisering till en annan identitets leverantör.</span><span class="sxs-lookup"><span data-stu-id="2d99c-117">Azure AD refers the client computer requesting authentication to another identity provider.</span></span>

<span data-ttu-id="2d99c-118">Se [Hybrid identiteter](plan-for-directory-synchronization.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="2d99c-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="2d99c-119">1. granska förutsättningar för Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="2d99c-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="2d99c-120">Du får en gratis Azure AD-prenumeration med ditt Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="2d99c-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="2d99c-121">När du ställer in profilsynkronisering kommer du att installera Azure AD Connect på en av dina lokala servrar.</span><span class="sxs-lookup"><span data-stu-id="2d99c-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="2d99c-122">För Microsoft 365 måste du:</span><span class="sxs-lookup"><span data-stu-id="2d99c-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="2d99c-123">Verifiera din lokala domän.</span><span class="sxs-lookup"><span data-stu-id="2d99c-123">Verify your on-premises domain.</span></span> <span data-ttu-id="2d99c-124">Guiden för Azure AD Connect hjälper dig med detta.</span><span class="sxs-lookup"><span data-stu-id="2d99c-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="2d99c-125">Skaffa användar namn och lösen ord för administratörs kontona för din Microsoft 365-klient organisation och AD DS.</span><span class="sxs-lookup"><span data-stu-id="2d99c-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="2d99c-126">För den lokala server där du installerar Azure AD Connect behöver du:</span><span class="sxs-lookup"><span data-stu-id="2d99c-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="2d99c-127">**Server OS**</span><span class="sxs-lookup"><span data-stu-id="2d99c-127">**Server OS**</span></span>|<span data-ttu-id="2d99c-128">**Annan program vara**</span><span class="sxs-lookup"><span data-stu-id="2d99c-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2d99c-129">Windows Server 2012 R2 och senare</span><span class="sxs-lookup"><span data-stu-id="2d99c-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="2d99c-130">-PowerShell är installerat som standard, ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="2d99c-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="2d99c-131">-NET 4.5.1 och senare versioner erbjuds via Windows Update.</span><span class="sxs-lookup"><span data-stu-id="2d99c-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="2d99c-132">Kontrol lera att du har installerat de senaste uppdateringarna för Windows Server i kontroll panelen.</span><span class="sxs-lookup"><span data-stu-id="2d99c-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="2d99c-133">Windows Server 2008 R2 med Service Pack 1 (SP1) \* \* eller Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="2d99c-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="2d99c-134">-Den senaste versionen av PowerShell finns i Windows Management Framework 4,0.</span><span class="sxs-lookup"><span data-stu-id="2d99c-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="2d99c-135">Sök efter den i [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="2d99c-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="2d99c-136">– .NET 4.5.1 och senare versioner finns på [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="2d99c-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="2d99c-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="2d99c-137">Windows Server 2008</span></span> | <span data-ttu-id="2d99c-138">-Den senaste versionen av PowerShell som stöds finns i Windows Management Framework 3,0, som är tillgänglig i [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="2d99c-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="2d99c-139">– .NET 4.5.1 och senare versioner finns på [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="2d99c-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="2d99c-140">Se [förutsättningar för Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) för information om maskin vara, program vara, konto och behörigheter, SSL-certifikat, krav och objekt gränser för Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="2d99c-140">See [Prerequisites for Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="2d99c-141">Du kan också kontrol lera [versions historiken](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) för Azure AD Connect för att se vad som ingår och åtgärdat i varje utgåva.</span><span class="sxs-lookup"><span data-stu-id="2d99c-141">You can also review the Azure AD Connect [version release history](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="2d99c-142">2. Installera Azure AD Connect och konfigurera Directory-synkronisering</span><span class="sxs-lookup"><span data-stu-id="2d99c-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="2d99c-143">Innan du börjar ska du kontrol lera att du har:</span><span class="sxs-lookup"><span data-stu-id="2d99c-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="2d99c-144">Användar namn och lösen ord för en global administratör för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2d99c-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="2d99c-145">Användar namn och lösen ord för en AD DS-domän administratör</span><span class="sxs-lookup"><span data-stu-id="2d99c-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="2d99c-146">Vilken autentiseringsmetod (PHS, PTA, federerad)</span><span class="sxs-lookup"><span data-stu-id="2d99c-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="2d99c-147">Om du vill använda [Azure AD-sömlös enkel inloggning (SSO)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)</span><span class="sxs-lookup"><span data-stu-id="2d99c-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="2d99c-148">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="2d99c-148">Follow these steps:</span></span>

1. <span data-ttu-id="2d99c-149">Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) ( https://admin.microsoft.com) och välj **användare** \> **aktiva användare** i det vänstra navigerings fältet.</span><span class="sxs-lookup"><span data-stu-id="2d99c-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="2d99c-150">Välj **fler** (tre punkter) katalog synkronisering på sidan **aktiva användare** \> **Directory synchronization**.</span><span class="sxs-lookup"><span data-stu-id="2d99c-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="2d99c-151">På sidan **Azure Active Directory-förberedelse** väljer du **gå till Download Center för att hämta länken för Azure AD Connect-verktyget** för att komma igång.</span><span class="sxs-lookup"><span data-stu-id="2d99c-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="2d99c-152">Följ stegen i [översikten för installation av Azure AD Connect och Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span><span class="sxs-lookup"><span data-stu-id="2d99c-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="2d99c-153">3. Slutför konfigureringen av domäner</span><span class="sxs-lookup"><span data-stu-id="2d99c-153">3. Finish setting up domains</span></span>

<span data-ttu-id="2d99c-154">Följ stegen i [Skapa DNS-poster för Microsoft 365 när du hanterar dina DNS-poster](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) för att slutföra konfigurationen av dina domäner.</span><span class="sxs-lookup"><span data-stu-id="2d99c-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="2d99c-155">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2d99c-155">Next step</span></span>

[<span data-ttu-id="2d99c-156">Tilldela licenser till användarkonton</span><span class="sxs-lookup"><span data-stu-id="2d99c-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
