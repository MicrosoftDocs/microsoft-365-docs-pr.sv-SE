---
title: Hantera lösen ord för Microsoft 365-användarkonto
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Lär dig mer om hur du hanterar lösen ord för användar konton i Microsoft 365.
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328543"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="8aee9-103">Hantera lösen ord för Microsoft 365-användarkonto</span><span class="sxs-lookup"><span data-stu-id="8aee9-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="8aee9-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8aee9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8aee9-105">Du kan hantera lösen ord för Microsoft 365-konto på flera olika sätt, beroende på din identitets konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8aee9-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="8aee9-106">Du kan hantera användar konton i [administrations centret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/), i AD DS (Active Directory Domain Services) eller i administrations centret för Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8aee9-106">You can manage user accounts in the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="8aee9-107">Planera var och hur du ska hantera lösen ord för ditt användar konto</span><span class="sxs-lookup"><span data-stu-id="8aee9-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="8aee9-108">Var och hur du kan hantera dina användar konton beror på vilken identitets modell du vill använda för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8aee9-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="8aee9-109">De två modellerna är enbart molnbaserade och hybrid.</span><span class="sxs-lookup"><span data-stu-id="8aee9-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="8aee9-110">Endast molnet</span><span class="sxs-lookup"><span data-stu-id="8aee9-110">Cloud-only</span></span>

<span data-ttu-id="8aee9-111">Du hanterar lösen ord för användar konton i:</span><span class="sxs-lookup"><span data-stu-id="8aee9-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="8aee9-112">Administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8aee9-112">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- <span data-ttu-id="8aee9-113">Administrations centret för Azure AD</span><span class="sxs-lookup"><span data-stu-id="8aee9-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="8aee9-114">Hybrid</span><span class="sxs-lookup"><span data-stu-id="8aee9-114">Hybrid</span></span>

<span data-ttu-id="8aee9-115">Med hybrid identitet lagras lösen ord i AD DS så du måste använda lokala AD DS-verktyg för att hantera lösen ord för användar konton.</span><span class="sxs-lookup"><span data-stu-id="8aee9-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="8aee9-116">Även när du använder Lösenordssynkronisering (PHS), där Azure AD lagrar en hash-version av den redan hashade versionen i AD DS, måste du och användare hantera sina lösen ord i AD DS.</span><span class="sxs-lookup"><span data-stu-id="8aee9-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="8aee9-117">Med [Lösenordssynkronisering](#pw_writeback)kan användarna ändra sina AD DS-lösenord via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8aee9-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="8aee9-118">Förhindra svaga lösenord</span><span class="sxs-lookup"><span data-stu-id="8aee9-118">Prevent bad passwords</span></span>

<span data-ttu-id="8aee9-119">Alla dina användare bör följa [Microsofts lösenordsvägledning](https://www.microsoft.com/research/publication/password-guidance) när de skapar lösenord till sina användarkonton.</span><span class="sxs-lookup"><span data-stu-id="8aee9-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="8aee9-120">Hindra användarna från att skapa svaga lösenord genom att använda Azure AD-lösenordsskydd, som tillämpar både en global lista med blockerade lösenord och en valfri lista med blockerade lösenord som du väljer.</span><span class="sxs-lookup"><span data-stu-id="8aee9-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="8aee9-121">Du kan till exempel välja ord som gäller specifikt för din organisation, som:</span><span class="sxs-lookup"><span data-stu-id="8aee9-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="8aee9-122">Varumärken</span><span class="sxs-lookup"><span data-stu-id="8aee9-122">Brand names</span></span>
- <span data-ttu-id="8aee9-123">Produktnamn</span><span class="sxs-lookup"><span data-stu-id="8aee9-123">Product names</span></span>
- <span data-ttu-id="8aee9-124">Platser (till exempel företagets huvudkontor)</span><span class="sxs-lookup"><span data-stu-id="8aee9-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="8aee9-125">Företagsspecifik, intern terminologi</span><span class="sxs-lookup"><span data-stu-id="8aee9-125">Company-specific internal terms</span></span>
- <span data-ttu-id="8aee9-126">Förkortningar med särskild betydelse för företaget</span><span class="sxs-lookup"><span data-stu-id="8aee9-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="8aee9-127">Du kan förbjuda Felaktiga lösen ord [i molnet](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) och för din [lokala AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span><span class="sxs-lookup"><span data-stu-id="8aee9-127">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="8aee9-128">Enklare inloggning för användare</span><span class="sxs-lookup"><span data-stu-id="8aee9-128">Simplify user sign-in</span></span>

<span data-ttu-id="8aee9-129">Azure AD-sömlös enkel inloggning (Azure AD sömlös SSO) fungerar med PHS och direktautentisering (PTA), så att användarna kan logga in på tjänster som använder Azure AD-användarkonton utan att behöva ange deras lösen ord, och i många fall, deras användar namn.</span><span class="sxs-lookup"><span data-stu-id="8aee9-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="8aee9-130">Det gör att användarna lättare kommer åt molnbaserade program, till exempel Office 365, utan att behöva några ytterligare lokala komponenter som identitetsservrar.</span><span class="sxs-lookup"><span data-stu-id="8aee9-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="8aee9-131">Du konfigurerar Azure AD Seamless SSO med Azure AD Connect-verktyget.</span><span class="sxs-lookup"><span data-stu-id="8aee9-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="8aee9-132">Se [anvisningarna för att konfigurera Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="8aee9-132">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="8aee9-133">Förenkla lösen ords uppdateringar till AD DS</span><span class="sxs-lookup"><span data-stu-id="8aee9-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="8aee9-134">Med lösen ords försök kan du tillåta att användare återställer sina lösen ord via Azure AD som sedan replikeras till AD DS.</span><span class="sxs-lookup"><span data-stu-id="8aee9-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="8aee9-135">Användarna behöver inte komma åt sin lokala AD DS för att uppdatera sina lösen ord.</span><span class="sxs-lookup"><span data-stu-id="8aee9-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="8aee9-136">Det här är värdefullt vid nätverksväxling och för fjärranvändare som inte har någon fjärråtkomstanslutning till det lokala nätverket.</span><span class="sxs-lookup"><span data-stu-id="8aee9-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="8aee9-137">Tillbakaskrivning av lösenord krävs för att fullt ut använda skyddsfunktioner för Azure AD, t. ex. för att begära att användare ska ändra sina lokala lösenord när en stor risk för kontointrång har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="8aee9-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="8aee9-138">Mer information och anvisningar för konfiguration finns i [Azure AD SSPR med tillbakaskrivning av lösenord](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="8aee9-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="8aee9-139">Uppgradera till den senaste versionen av Azure AD Connect för att säkerställa bästa möjliga upplevelse och nya funktioner när de släpps.</span><span class="sxs-lookup"><span data-stu-id="8aee9-139">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released.</span></span> <span data-ttu-id="8aee9-140">Mer information finns i [Anpassad installation av Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="8aee9-140">For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="8aee9-141">Enklare återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="8aee9-141">Simplify password resets</span></span>

<span data-ttu-id="8aee9-142">Med självbetjäning för återställning av lösen ord (SSPR) kan användarna återställa eller låsa upp sina lösen ord eller konton.</span><span class="sxs-lookup"><span data-stu-id="8aee9-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="8aee9-143">Du kan få varningar om missbruk eller felanvändning genom att använda den detaljerade rapporteringen som spårar när användare har åtkomst till systemet, tillsammans med meddelanden.</span><span class="sxs-lookup"><span data-stu-id="8aee9-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="8aee9-144">Du måste aktivera [Ångra lösen ord](#pw_writeback) innan du kan distribuera Återställ lösen ord.</span><span class="sxs-lookup"><span data-stu-id="8aee9-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="8aee9-145">Se [anvisningarna för att distribuera återställning av lösenord](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="8aee9-145">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

