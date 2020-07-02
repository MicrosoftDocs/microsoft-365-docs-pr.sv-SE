---
title: 'Steg 4: Lägga till användarkonton'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Lägg till användarkonton och grupper direkt i molnet eller genom att synkronisera med din lokala katalog.
ms.openlocfilehash: 2a54044737f5b924bd619d5a6c7c72091dc7a0d1
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005840"
---
# <a name="step-4-add-your-user-accounts"></a><span data-ttu-id="388d9-103">Steg 4: Lägga till användarkonton</span><span class="sxs-lookup"><span data-stu-id="388d9-103">Step 4: Add your user accounts</span></span>

![Fas 2 – Identitet ](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-cloud-only"></a>
## <a name="create-your-user-accounts-for-cloud-only-identity"></a><span data-ttu-id="388d9-105">Skapa användarkonton för helt molnbaserad identitet</span><span class="sxs-lookup"><span data-stu-id="388d9-105">Create your user accounts for cloud-only identity</span></span>

<span data-ttu-id="388d9-106">Skapa dina användare och grupper i Azure Active Directory (Azure AD) för en helt molnbaserad identitet.</span><span class="sxs-lookup"><span data-stu-id="388d9-106">For cloud-only identity, create your users and groups in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="388d9-107">Du kan använda:</span><span class="sxs-lookup"><span data-stu-id="388d9-107">You can use:</span></span>

- <span data-ttu-id="388d9-108">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="388d9-108">The Microsoft 365 admin center</span></span>
- <span data-ttu-id="388d9-109">Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="388d9-109">The Azure portal</span></span>
- <span data-ttu-id="388d9-110">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="388d9-110">Azure PowerShell</span></span>

<a name="identity-sync"></a>
## <a name="synchronize-identities-for-hybrid-identity"></a><span data-ttu-id="388d9-111">Synkronisera identiteter för hybrididentitet</span><span class="sxs-lookup"><span data-stu-id="388d9-111">Synchronize identities for hybrid identity</span></span>

<span data-ttu-id="388d9-112">*Det här är obligatoriskt för hybridmiljöer och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="388d9-112">*This is required for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="388d9-113">I det här avsnittet ska du synkronisera din lokala Active Directory Domain Services (AD DS) med Azure AD-klienten som används av Office 365, Microsoft Intune och andra molnbaserade tjänster som ingår i Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="388d9-113">In this section, you'll synchronize your on-premises Active Directory Domain Services (AD DS) with the Azure AD tenant used by Office 365, Microsoft Intune, and other cloud-based services included with Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="388d9-114">Azure AD Connect är det Microsoft-verktyg som stöds, och vägleder dig genom att enbart synkronisera de identiteter du verkligen behöver i AD DS-miljöer med en eller flera skogar till din Azure AD-klient.</span><span class="sxs-lookup"><span data-stu-id="388d9-114">Azure AD Connect is the supported Microsoft tool that guides you through synchronizing only the identities you really need from single or multi-forest AD DS environments to your Azure AD tenant.</span></span> <span data-ttu-id="388d9-115">Följande bild visar grundprocessen för Azure AD Connect-synkronisering.</span><span class="sxs-lookup"><span data-stu-id="388d9-115">The following figure shows the basic process for Azure AD Connect synchronization.</span></span>

![Så synkroniserar Azure AD Connect din lokala katalog med Azure AD](../media/identity-add-user-accounts/azure-ad-connect.png)

1. <span data-ttu-id="388d9-117">Azure AD Connect körs på en server och avsöker AD DS för ändringar i konton, grupper och kontakter.</span><span class="sxs-lookup"><span data-stu-id="388d9-117">Azure AD Connect running on a server polls AD DS for changes in accounts, groups, and contacts.</span></span>
2. <span data-ttu-id="388d9-118">Azure AD Connect skickar ändringarna till Azure AD-klienten för din Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="388d9-118">Azure AD Connect sends those changes to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="388d9-119">Det första beslutet i din hybrididentitetslösning gäller autentiseringskravet.</span><span class="sxs-lookup"><span data-stu-id="388d9-119">The first decision in your hybrid identity solution is your authentication requirement.</span></span> <span data-ttu-id="388d9-120">Följande alternativ är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="388d9-120">The following options are options:</span></span>

- <span data-ttu-id="388d9-121">Med **hanterad autentisering** hanteras autentiseringsprocessen för användarnas inloggning av Azure AD.</span><span class="sxs-lookup"><span data-stu-id="388d9-121">With **managed authentication**, Azure AD handles the authentication process for user sign-in.</span></span> <span data-ttu-id="388d9-122">Det finns två metoder för hanterad autentisering:</span><span class="sxs-lookup"><span data-stu-id="388d9-122">There are two methods for managed authentication:</span></span> 
    - <span data-ttu-id="388d9-123">**PHS (Password Hash Sync)** [rekommenderas och krävs för vissa premiumfunktioner].</span><span class="sxs-lookup"><span data-stu-id="388d9-123">**Password Hash Sync (PHS)** [Recommended and required for some premium features].</span></span> <span data-ttu-id="388d9-124">Det här är det enklaste sättet att aktivera autentisering för lokala katalogobjekt i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="388d9-124">This is the simplest way to enable authentication for on-premises directory objects in Azure AD.</span></span> <span data-ttu-id="388d9-125">Azure AD Connect extraherar det hash-kodade lösenordet från AD DS, utför extra säkerhetsbearbetning för lösenordshashvärdet och synkroniserar det med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="388d9-125">Azure AD Connect extracts the hashed password from AD DS, does extra security processing on the password hash, and synchronizes it to Azure AD.</span></span> <span data-ttu-id="388d9-126">Mer information finns i [Implementera synkronisering av lösenordshash med Azure AD Connect-synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="388d9-126">For more information, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
    - <span data-ttu-id="388d9-127">**Direktautentisering (PTA)** ger en enkel lösning för lösenordsverifiering för Azure AD-baserade tjänster.</span><span class="sxs-lookup"><span data-stu-id="388d9-127">**Pass-through Authentication (PTA)** provides a simple password validation solution for Azure AD-based services.</span></span> <span data-ttu-id="388d9-128">PTA använder en agent som körs på en eller flera lokala servrar för att verifiera användarautentiseringarna direkt i din lokala AD DS.</span><span class="sxs-lookup"><span data-stu-id="388d9-128">PTA uses an agent running on one or more on-premises servers to validate the user authentications directly with your on-premises AD DS.</span></span> <span data-ttu-id="388d9-129">Mer information finns i [användarinloggning med Azure Active Directory – direktautentisering](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span><span class="sxs-lookup"><span data-stu-id="388d9-129">For more information, see [User sign-in with Azure Active Directory Pass-through Authentication](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).</span></span>
- <span data-ttu-id="388d9-130">Med **federerad autentisering** omdirigeras autentiseringsprocessen till en annan identitetsleverantör via en server för identitetsfederation, till exempel Active Directory Federation Services (AD FS), för en användares inloggning.</span><span class="sxs-lookup"><span data-stu-id="388d9-130">With **federated authentication**, the authentication process is redirected to another identity provider through an identity federation server, such as Active Directory Federation Services (AD FS), for a user’s sign-in.</span></span> <span data-ttu-id="388d9-131">Identitetsleverantören kan tillhandahålla ytterligare autentiseringsmetoder, t. ex. smartkortsbaserad autentisering.</span><span class="sxs-lookup"><span data-stu-id="388d9-131">The identity provider can provide additional authentication methods, such as smartcard-based authentication.</span></span> <span data-ttu-id="388d9-132">Mer information finns i [Välja rätt autentiseringsmetod för din hybrididentitetslösning i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn).</span><span class="sxs-lookup"><span data-stu-id="388d9-132">For more information, see [Choosing the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn).</span></span>

<span data-ttu-id="388d9-133">I den här videon finns en översikt över identitetsmodeller och autentisering för Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="388d9-133">Watch this video for an overview of identity models and authentication for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="388d9-134"><p> </p></span><span class="sxs-lookup"><span data-stu-id="388d9-134"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="388d9-135">När du har fastställt din hybrididentitetslösning laddar du ned och kör [IdFix-verktyget för reparation av katalogsynkroniseringsfel](https://www.microsoft.com/download/details.aspx?id=36832) för att analysera eventuella problem med AD DS.</span><span class="sxs-lookup"><span data-stu-id="388d9-135">After you've determined your hybrid identity solution, download and run the [IdFix Directory Synchronization Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) to analyze your AD DS for issues.</span></span>

<span data-ttu-id="388d9-136">När du har åtgärdat alla problem som identifierats av IdFix-verktyget kan du läsa i [Implementera synkronisering av lösenordshash](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization), som innehåller vägledning för hur du installerar Azure AD Connect-verktyget och konfigurerar katalogsynkronisering mellan din lokala AD DS och Azure AD-klienten för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="388d9-136">After resolving all of the issues identified by the IdFix tool, see [Implement password hash synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) for guidance on installing the Azure AD Connect tool and configuring directory synchronization between your on-premises AD DS and the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="388d9-137">När synkroniseringen startar ska du underhålla dina användarkonton och grupper med din lokala identitetsleverantör, t. ex. AD DS.</span><span class="sxs-lookup"><span data-stu-id="388d9-137">After synchronization starts, you'll maintain your user accounts and groups with your on-premises identity provider, such as AD DS.</span></span>

<span data-ttu-id="388d9-138">Microsoft tillhandahåller en uppsättning rekommendationer för [identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) för att säkerställa en säker och produktiv arbetsstyrka.</span><span class="sxs-lookup"><span data-stu-id="388d9-138">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> 

- <span data-ttu-id="388d9-139">Rekommenderade krav för hybridmiljöer beskrivs i kolumnen **Active Directory-synkronisering med hash-synkronisering** i [förutsättningar](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="388d9-139">For recommended requirements for hybrid environments, see the **Active Directory with password hash sync** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span> 

- <span data-ttu-id="388d9-140">Rekommenderade krav för miljöer med endast moln beskrivs i kolumnen **endast molnet** i [förutsättningar](identity-access-prerequisites.md#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="388d9-140">For recommended requirements for cloud only environments, see the **Cloud only** column in [prerequisites](identity-access-prerequisites.md#prerequisites).</span></span>

<span data-ttu-id="388d9-141">När dina lokala användare och grupper finns i Azure AD kan du börja tilldela licenser och använda produktivitetsarbetsbelastningar, t. ex. OneDrive för företag och Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="388d9-141">Once your on-premises users and groups are present in Azure AD, you can start assigning licenses and using productivity workloads such as OneDrive for Business and Exchange Online.</span></span>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="388d9-143">Testlabbguide: Synkronisering av lösenordshash</span><span class="sxs-lookup"><span data-stu-id="388d9-143">Test Lab Guide: Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)<br> [<span data-ttu-id="388d9-144">Testlabbguide: Direktautentisering</span><span class="sxs-lookup"><span data-stu-id="388d9-144">Test Lab Guide: Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md) |
|||

<span data-ttu-id="388d9-145">Som en mellanliggande kontrollpunkt kan du se vilka [avslutsvillkor](identity-exit-criteria.md#crit-identity-sync) som motsvarar det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="388d9-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync) corresponding to this section.</span></span>

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a><span data-ttu-id="388d9-146">Övervaka synkroniseringshälsa</span><span class="sxs-lookup"><span data-stu-id="388d9-146">Monitor synchronization health</span></span>

<span data-ttu-id="388d9-147">*Det här är valfritt och gäller både E3- och E5-versionerna av Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="388d9-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365*</span></span>

<span data-ttu-id="388d9-148">I det här avsnittet installerar du en Azure AD Connect Health-agent på var och en av dina lokala AD DS-domänkontrollanter för att övervaka din identitetsinfrastruktur och de synkroniseringstjänster som tillhandahålls av Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="388d9-148">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="388d9-149">Övervakningsinformationen visas i en Azure AD Connect Health-portal, där du kan se varningar, prestandaövervakning, användningsanalys och annan information.</span><span class="sxs-lookup"><span data-stu-id="388d9-149">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Komponenter i Azure AD Connect Health](../media/identity-add-user-accounts/identity-azure-ad-connect-health.png)

<span data-ttu-id="388d9-151">Det viktiga beslutet för hur du ska använda Azure AD Connect Health, baseras på hur du använder Azure AD Connect:</span><span class="sxs-lookup"><span data-stu-id="388d9-151">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="388d9-152">Om du använder **hanterad autentisering** börjar du med [Använda Azure AD Connect Health med synkronisering](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) för att förstå och konfigurera Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="388d9-152">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="388d9-153">Om du bara synkroniserar namnen på de konton och grupper som använder **federerad autentisering** med Active Directory Federation Services (AD FS), börjar du med [Använda Azure AD Connect Health med AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) för att förstå och konfigurera Azure AD Connect Health.</span><span class="sxs-lookup"><span data-stu-id="388d9-153">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="388d9-154">När du har slutfört det här avsnittet har du:</span><span class="sxs-lookup"><span data-stu-id="388d9-154">When you complete this section, you’ll have:</span></span>

- <span data-ttu-id="388d9-155">Azure AD Connect Health-agenten installerad på dina lokala identitetsproviderservrar.</span><span class="sxs-lookup"><span data-stu-id="388d9-155">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="388d9-156">Azure AD Connect Health-portalen visar aktuell status för lokal infrastruktur och synkronisering med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="388d9-156">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

<span data-ttu-id="388d9-157">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-sync-health) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="388d9-157">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this section.</span></span>



<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="388d9-158">Enklare uppdatering av lösenord</span><span class="sxs-lookup"><span data-stu-id="388d9-158">Simplify password updates</span></span>

<span data-ttu-id="388d9-159">*Det här är valfritt för hybridversioner och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="388d9-159">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="388d9-160">I det här avsnittet ska du ge användare möjlighet att återställa sina lösenord via Azure Active Directory (Azure AD), som sedan replikeras till din lokala Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="388d9-160">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="388d9-161">Processen kallas för tillbakaskrivning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="388d9-161">This process is known as password writeback.</span></span> <span data-ttu-id="388d9-162">Med funktionen för tillbakaskrivning av lösenord behöver användarna inte uppdatera sina lösenord via den lokala AD DS där användarkontona och tillhörande attribut lagras.</span><span class="sxs-lookup"><span data-stu-id="388d9-162">With password writeback, users don’t need to update their passwords through the on-premises AD DS where user accounts and their attributes are stored.</span></span> <span data-ttu-id="388d9-163">Det här är värdefullt vid nätverksväxling och för fjärranvändare som inte har någon fjärråtkomstanslutning till det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="388d9-163">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="388d9-164">Tillbakaskrivning av lösenord krävs för att fullt ut använda skyddsfunktioner för Azure AD, t. ex. för att begära att användare ska ändra sina lokala lösenord när en stor risk för kontointrång har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="388d9-164">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="388d9-165">Mer information och anvisningar för konfiguration finns i [Azure AD SSPR med tillbakaskrivning av lösenord](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="388d9-165">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="388d9-166">Uppgradera till den senaste versionen av Azure AD Connect för att säkerställa bästa möjliga upplevelse och nya funktioner när de släpps.</span><span class="sxs-lookup"><span data-stu-id="388d9-166">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="388d9-167">Mer information finns i [Anpassad installation av Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="388d9-167">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="388d9-169">Testlabbguide: Tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="388d9-169">Test Lab Guide: Password writeback</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="388d9-170">Som en mellanliggande kontrollpunkt kan du läsa [avslutsvillkoren](identity-exit-criteria.md#crit-identity-pw-writeback) för det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="388d9-170">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this section.</span></span>

|||
|:-------|:-----|
|![Steg 5](../media/stepnumbers/Step5.png)| [<span data-ttu-id="388d9-172">Använda grupper för hantering</span><span class="sxs-lookup"><span data-stu-id="388d9-172">Use groups for management</span></span>](identity-use-group-management.md) |
