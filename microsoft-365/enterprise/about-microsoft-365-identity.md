---
title: Microsoft 365-Identity-modeller och Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Lär dig hur du hanterar Azure AD User Identity-tjänsten i Microsoft 365 med moln-eller hybrid identitets modeller.
ms.openlocfilehash: 6b5b80584408671a1925e32df1fbf458b7c16139
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327957"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="6987f-103">Microsoft 365-Identity-modeller och Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6987f-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="6987f-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6987f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6987f-105">Microsoft 365 använder Azure Active Directory (Azure AD), en molnbaserad användar identitets-och autentiseringstjänst som ingår i ditt Microsoft 365-abonnemang, för att hantera identiteter och inloggningsautentisering för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6987f-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="6987f-106">Att få din identitets infrastruktur konfigurerad korrekt är viktig för att hantera Microsoft 365-användarnas åtkomst och behörigheter för din organisation.</span><span class="sxs-lookup"><span data-stu-id="6987f-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="6987f-107">Innan du börjar kan du titta på den här videon för att få en översikt över identitets modeller och för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6987f-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="6987f-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="6987f-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="6987f-109">Ditt första planerings val är Microsoft 365-Identity-modellen.</span><span class="sxs-lookup"><span data-stu-id="6987f-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="6987f-110">Microsoft 365-ID-modeller</span><span class="sxs-lookup"><span data-stu-id="6987f-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="6987f-111">För att planera för användar konton måste du först förstå de två identitets modellerna i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6987f-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="6987f-112">Du kan endast underhålla organisationens identiteter i molnet, eller så kan du underhålla dina lokala Active Directory Domain Services-identiteter (AD DS) och använda dem för att verifiera när användare har åtkomst till Microsoft 365-moln tjänster.</span><span class="sxs-lookup"><span data-stu-id="6987f-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="6987f-113">Här är de två typerna av identitet och deras bästa passning och fördelar.</span><span class="sxs-lookup"><span data-stu-id="6987f-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="6987f-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="6987f-114">Attribute</span></span> | <span data-ttu-id="6987f-115">Identitet endast för molnet</span><span class="sxs-lookup"><span data-stu-id="6987f-115">Cloud-only identity</span></span> | <span data-ttu-id="6987f-116">Hybrididentitet</span><span class="sxs-lookup"><span data-stu-id="6987f-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="6987f-117">**Definition**</span><span class="sxs-lookup"><span data-stu-id="6987f-117">**Definition**</span></span> | <span data-ttu-id="6987f-118">Användar kontot finns bara i Azure AD-innehavaren för ditt Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="6987f-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="6987f-119">Användar kontot finns i AD DS och en kopia finns också i Azure AD-innehavaren för ditt Microsoft 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="6987f-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="6987f-120">Användar kontot i Azure AD kan också innehålla en hash-version av det redan hashade lösen ordet för AD DS-användarkontot.</span><span class="sxs-lookup"><span data-stu-id="6987f-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="6987f-121">**Hur Microsoft 365 verifierar användarautentiseringsuppgifter**</span><span class="sxs-lookup"><span data-stu-id="6987f-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="6987f-122">Azure AD-klientaren för din Microsoft 365-prenumeration utför autentiseringsprocessen med moln identitets kontot.</span><span class="sxs-lookup"><span data-stu-id="6987f-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="6987f-123">Azure AD-klientaren för din Microsoft 365-prenumeration hanterar antingen autentiseringsprocessen eller omdirigerar användaren till en annan identitets leverantör.</span><span class="sxs-lookup"><span data-stu-id="6987f-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="6987f-124">**Bäst för**</span><span class="sxs-lookup"><span data-stu-id="6987f-124">**Best for**</span></span> | <span data-ttu-id="6987f-125">Organisationer som inte har eller behöver en lokal AD DS.</span><span class="sxs-lookup"><span data-stu-id="6987f-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="6987f-126">Organisationer som använder AD DS eller en annan identitets leverantör.</span><span class="sxs-lookup"><span data-stu-id="6987f-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="6987f-127">**Största fördelen**</span><span class="sxs-lookup"><span data-stu-id="6987f-127">**Greatest benefit**</span></span> | <span data-ttu-id="6987f-128">Lätt att använda.</span><span class="sxs-lookup"><span data-stu-id="6987f-128">Simple to use.</span></span> <span data-ttu-id="6987f-129">Inga extra katalog verktyg eller servrar behövs.</span><span class="sxs-lookup"><span data-stu-id="6987f-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="6987f-130">Användare kan använda samma inloggnings uppgifter när de använder lokala eller molnbaserade resurser.</span><span class="sxs-lookup"><span data-stu-id="6987f-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="6987f-131">Identitet endast för molnet</span><span class="sxs-lookup"><span data-stu-id="6987f-131">Cloud-only identity</span></span>

<span data-ttu-id="6987f-132">En endast moln identitet använder användar konton som bara finns i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6987f-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="6987f-133">Moln-Only-identitet används vanligt vis av små organisationer som inte har lokala servrar eller som inte använder AD DS för att hantera lokal identitet.</span><span class="sxs-lookup"><span data-stu-id="6987f-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="6987f-134">Här är de grundläggande komponenterna i moln-Only-identitet.</span><span class="sxs-lookup"><span data-stu-id="6987f-134">Here are the basic components of cloud-only identity.</span></span>
 
![Bas komponenter i moln-Only-identitet](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="6987f-136">Både lokala och fjärranslutna användare använder sina Azure AD-användarkonton och lösen ord för att komma åt Microsoft 365-moln tjänster.</span><span class="sxs-lookup"><span data-stu-id="6987f-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="6987f-137">Azure AD autentiserar användarautentiseringsuppgifter baserat på dess lagrade användar konton och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="6987f-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="6987f-138">Administration</span><span class="sxs-lookup"><span data-stu-id="6987f-138">Administration</span></span>
<span data-ttu-id="6987f-139">Eftersom användar konton bara lagras i Azure AD hanterar du moln identiteter med verktyg som [Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/add-users/) och [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6987f-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="6987f-140">Hybrididentitet</span><span class="sxs-lookup"><span data-stu-id="6987f-140">Hybrid identity</span></span>

<span data-ttu-id="6987f-141">Hybrid identitet använder konton som kommer från en lokal AD DS och har en kopia i Azure AD-klient organisationen för en Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="6987f-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="6987f-142">De flesta ändringar är dock bara ett sätt.</span><span class="sxs-lookup"><span data-stu-id="6987f-142">However, most changes only flow one way.</span></span> <span data-ttu-id="6987f-143">Ändringar som du gör i AD DS-användarkonton synkroniseras till deras kopia i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6987f-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="6987f-144">Men ändringar av molnbaserade konton i Azure AD, till exempel nya användar konton, synkroniseras inte med AD DS.</span><span class="sxs-lookup"><span data-stu-id="6987f-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="6987f-145">Azure AD Connect tillhandahåller den pågående synkroniseringen av kontot.</span><span class="sxs-lookup"><span data-stu-id="6987f-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="6987f-146">Den körs på en lokal server, söker efter ändringar i AD DS och vidarebefordrar dessa ändringar till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6987f-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="6987f-147">Azure AD Connect ger möjlighet att filtrera fram vilka konton som ska synkroniseras och om du vill synkronisera en hashad version av användar lösen ord, som kallas Lösenordssynkronisering för lösen ord (PHS).</span><span class="sxs-lookup"><span data-stu-id="6987f-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="6987f-148">När du implementerar hybrid identitet är din lokala AD DS auktoritär källa för konto information.</span><span class="sxs-lookup"><span data-stu-id="6987f-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="6987f-149">Det innebär att du utför administrations uppgifter mest lokalt, vilka sedan synkroniseras till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6987f-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="6987f-150">Här är komponenterna i hybrid identiteten.</span><span class="sxs-lookup"><span data-stu-id="6987f-150">Here are the components of hybrid identity.</span></span>

![Komponenter för Hybrid identitet](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="6987f-152">Azure AD-innehavaren har en kopia av AD DS-kontona.</span><span class="sxs-lookup"><span data-stu-id="6987f-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="6987f-153">I den här konfigurationen verifierar både lokala och fjärran vändare åtkomst till Microsoft 365-molntjänster för Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6987f-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="6987f-154">Du behöver alltid använda Azure AD Connect för att synkronisera användar konton för Hybrid identitet.</span><span class="sxs-lookup"><span data-stu-id="6987f-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="6987f-155">Du behöver synkroniserade användar konton i Azure AD för att utföra licens tilldelning och grupp hantering, konfigurera behörigheter och andra administrativa uppgifter som inbegriper användar konton.</span><span class="sxs-lookup"><span data-stu-id="6987f-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="6987f-156">Administration</span><span class="sxs-lookup"><span data-stu-id="6987f-156">Administration</span></span>

<span data-ttu-id="6987f-157">Eftersom de ursprungliga och auktoritativa användar kontona lagras i den lokala AD DS hanterar du dina identiteter med samma verktyg som du hanterar din AD DS.</span><span class="sxs-lookup"><span data-stu-id="6987f-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="6987f-158">Du använder inte Microsoft 365 Admin Center eller PowerShell för Microsoft 365 för att hantera synkroniserade användar konton i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6987f-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="6987f-159">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6987f-159">Next step</span></span>

<span data-ttu-id="6987f-160">Om du behöver den molnbaserade identitets modellen kan du läsa den här [moln identiteten](cloud-only-identities.md).</span><span class="sxs-lookup"><span data-stu-id="6987f-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="6987f-161">Om du behöver hybrid identitets modellen, se [hybrid identitet](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="6987f-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="6987f-162">Se även</span><span class="sxs-lookup"><span data-stu-id="6987f-162">See also</span></span>

[<span data-ttu-id="6987f-163">Översikt över Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6987f-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
