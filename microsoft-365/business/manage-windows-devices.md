---
title: Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Lär dig hur du aktiverar Microsoft 365 för att skydda lokala Windows 10-enheter med Active-Directory i bara några få steg.
ms.openlocfilehash: 8d7caefa1ddcadf684fdb5b712601b1bdd4fb5bd
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550256"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="8aab2-103">Aktivera domänanslutna Windows 10-enheter för hantering i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="8aab2-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="8aab2-104">Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.</span><span class="sxs-lookup"><span data-stu-id="8aab2-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="8aab2-105">Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter**.</span><span class="sxs-lookup"><span data-stu-id="8aab2-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="8aab2-106">Dessa enheter är anslutna till både din lokala Active Directory och din Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8aab2-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="8aab2-107">I det här videoklippet beskrivs stegen för hur du ställer in detta för det vanligaste scenariot, som också beskrivs i de steg som följer.</span><span class="sxs-lookup"><span data-stu-id="8aab2-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="8aab2-108">1. Förbered för katalogsynkronisering</span><span class="sxs-lookup"><span data-stu-id="8aab2-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="8aab2-109">Innan du synkroniserar användarna och datorerna från den lokala Active Directory-domänen läser du [Förbered för katalogsynkronisering till Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="8aab2-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="8aab2-110">I synnerhet gäller följande:</span><span class="sxs-lookup"><span data-stu-id="8aab2-110">In particular:</span></span>

   - <span data-ttu-id="8aab2-111">Kontrollera att det inte finns några dubbletter i katalogen för följande attribut: **e-post,** **proxyAdresser**och **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="8aab2-111">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="8aab2-112">Dessa värden måste vara unika och alla dubbletter måste tas bort.</span><span class="sxs-lookup"><span data-stu-id="8aab2-112">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="8aab2-113">Vi rekommenderar att du konfigurerar UPN-attributet **userPrincipalName** (UPN) för varje lokalt användarkonto så att den matchar den primära e-postadressen som motsvarar den licensierade Microsoft 365-användaren.</span><span class="sxs-lookup"><span data-stu-id="8aab2-113">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="8aab2-114">Till exempel: *mary.shelley@contoso.com* snarare än *mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="8aab2-114">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="8aab2-115">Om Active Directory-domänen slutar i ett icke-dirigerat suffix som *.local* eller *.lan*, i stället för ett internetroutable suffix som *.com* eller *.org,* justerar DU UPN-suffixet för de lokala användarkontona först enligt beskrivningen i [Förbered en domän som inte är dirigerbar för katalogsynkronisering](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="8aab2-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="8aab2-116">2. Installera och konfigurera Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="8aab2-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="8aab2-117">Om du vill synkronisera användarna, grupperna och kontakterna från den lokala Active Directory till Azure Active Directory installerar du Azure Active Directory Connect och konfigurerar katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="8aab2-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="8aab2-118">Mer information [finns i Konfigurera katalogsynkronisering för Office 365.](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)</span><span class="sxs-lookup"><span data-stu-id="8aab2-118">See [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="8aab2-119">Stegen är exakt desamma för Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="8aab2-119">The steps are exactly the same for Microsoft 365 Business.</span></span> 

<span data-ttu-id="8aab2-120">När du konfigurerar dina alternativ för Azure AD Connect rekommenderar vi att du aktiverar **lösenordssynkronisering,** **sömlös enkel inloggning**och **funktionen för tillbakaskrivning av lösenord,** vilket också stöds i Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="8aab2-120">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 Business.</span></span>

> [!NOTE]
> <span data-ttu-id="8aab2-121">Det finns ytterligare några steg för lösenordsavskrivning utöver kryssrutan i Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="8aab2-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="8aab2-122">Mer information finns i Så här konfigurerar du [lösenordsavskrivning](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="8aab2-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="8aab2-123">3. Konfigurera Hybrid Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="8aab2-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="8aab2-124">Innan du aktiverar Windows 10-enheter som Hybrid Azure AD-sammanfogade kontrollerar du att du uppfyller följande förutsättningar:</span><span class="sxs-lookup"><span data-stu-id="8aab2-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="8aab2-125">Du kör den senaste versionen av Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="8aab2-125">You're running the latest version of Azure AD Connect.</span></span>

   - <span data-ttu-id="8aab2-126">Azure AD connect har synkroniserat alla datorobjekt för de enheter som du vill vara hybrid Azure AD ansluten.</span><span class="sxs-lookup"><span data-stu-id="8aab2-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="8aab2-127">Om datorobjekten tillhör specifika organisationsenheter (OU) kontrollerar du att dessa organisationsenheter också är inställda för synkronisering i Azure AD connect.</span><span class="sxs-lookup"><span data-stu-id="8aab2-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="8aab2-128">Så här registrerar du befintliga domänanslutna Windows 10-enheter som Hybrid Azure AD som är sammanfogat i [självstudiekursen: Konfigurera hybrid Azure Active Directory-koppling för hanterade domäner](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span><span class="sxs-lookup"><span data-stu-id="8aab2-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="8aab2-129">Den här hybriden gör att din befintliga lokala Active Directory anslöt till Windows 10-datorer och gör dem till molnet redo.</span><span class="sxs-lookup"><span data-stu-id="8aab2-129">This hybrid-enables your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="8aab2-130">4. Aktivera automatisk registrering för Windows 10</span><span class="sxs-lookup"><span data-stu-id="8aab2-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="8aab2-131">Information om hur du registrerar Windows 10-enheter automatiskt för hantering av mobila enheter i Intune finns i [Registrera en Windows 10-enhet automatiskt med grupprincipen](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span><span class="sxs-lookup"><span data-stu-id="8aab2-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="8aab2-132">Du kan ange grupprincipen på lokal datornivå eller för massåtgärder kan du använda grupprinciphanteringskonsolen och ADMX-mallarna för att skapa den här grupprincipinställningen på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="8aab2-132">You can set the Group Policy at a local computer level, or for bulk operations, you can use the Group Policy Management Console and ADMX templates to create this Group Policy setting on your Domain Controller.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="8aab2-133">5. Konfigurera sömlös enkel inloggning</span><span class="sxs-lookup"><span data-stu-id="8aab2-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="8aab2-134">Sömlössa SSO loggar automatiskt in användare i sina Microsoft 365-molnresurser när de använder företagsdatorer.</span><span class="sxs-lookup"><span data-stu-id="8aab2-134">Seamless SSO automatically signs users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="8aab2-135">Distribuera helt enkelt ett av de två grupprincipalternativ som beskrivs i [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span><span class="sxs-lookup"><span data-stu-id="8aab2-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="8aab2-136">**Grupprincipalternativet** tillåter inte användare att ändra sina inställningar, medan alternativet **Grupprincippreferens** anger värdena men också lämnar dem användarkonfigurerbara.</span><span class="sxs-lookup"><span data-stu-id="8aab2-136">The **Group Policy** option doesn't allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="8aab2-137">6. Konfigurera Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="8aab2-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="8aab2-138">Windows Hello for Business ersätter lösenord med stark tvåfaktorsautentisering (2FA) för att logga in på en lokal dator.</span><span class="sxs-lookup"><span data-stu-id="8aab2-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="8aab2-139">En faktor är ett asymmetriskt nyckelpar, och det andra är en PIN-kod eller annan lokal gest, till exempel fingeravtryck eller ansiktsigenkänning om enheten stöder den.</span><span class="sxs-lookup"><span data-stu-id="8aab2-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="8aab2-140">Vi rekommenderar att du ersätter lösenord med 2FA och Windows Hello for Business där det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="8aab2-140">We recommend that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="8aab2-141">Om du vill konfigurera Hybrid Windows Hello for Business läser du [hybridnyckeln sett till Windows Hello for Business-förutsättningar](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span><span class="sxs-lookup"><span data-stu-id="8aab2-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="8aab2-142">Följ sedan instruktionerna i [Konfigurera Hybrid Windows Hello for Business-knappförtroendeinställningar](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span><span class="sxs-lookup"><span data-stu-id="8aab2-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
