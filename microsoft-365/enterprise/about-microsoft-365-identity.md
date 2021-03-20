---
title: Identitetsmodeller i Microsoft 365 och Azure Active Directory
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
description: Lär dig hur du hanterar Azure AD-användaridentitetstjänsten i Microsoft 365 med hjälp av modeller för endast molnet eller hybrididentitet.
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905710"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="dc958-103">Identitetsmodeller i Microsoft 365 och Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="dc958-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="dc958-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="dc958-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dc958-105">Microsoft 365 använder Azure Active Directory (Azure AD), en molnbaserad användaridentitets- och autentiseringstjänst som ingår i Microsoft 365-prenumerationen, för att hantera identiteter och autentisering för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc958-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="dc958-106">Att konfigurera identitetsinfrastrukturen på rätt sätt är viktigt för att hantera Microsoft 365-användares åtkomst och behörigheter för din organisation.</span><span class="sxs-lookup"><span data-stu-id="dc958-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="dc958-107">Innan du börjar kan du titta på den här videon för att få en översikt över identitetsmodeller och autentisering för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc958-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="dc958-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="dc958-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="dc958-109">Ditt första planeringsval är Microsoft 365-identitetsmodellen.</span><span class="sxs-lookup"><span data-stu-id="dc958-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="dc958-110">Identitetsmodeller i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dc958-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="dc958-111">För att du ska kunna planera för användarkonton måste du först förstå de två identitetsmodellerna i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc958-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="dc958-112">Du kan endast underhålla organisationens identiteter i molnet, eller så kan du underhålla dina lokala AD DS-identiteter (Active Directory Domain Services) och använda dem för autentisering när användare använder Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="dc958-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="dc958-113">Här är de två typerna av identitet och deras bästa form och fördelar.</span><span class="sxs-lookup"><span data-stu-id="dc958-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="dc958-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="dc958-114">Attribute</span></span> | <span data-ttu-id="dc958-115">Identitet endast för molnet</span><span class="sxs-lookup"><span data-stu-id="dc958-115">Cloud-only identity</span></span> | <span data-ttu-id="dc958-116">Hybrididentitet</span><span class="sxs-lookup"><span data-stu-id="dc958-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="dc958-117">**Definition**</span><span class="sxs-lookup"><span data-stu-id="dc958-117">**Definition**</span></span> | <span data-ttu-id="dc958-118">Användarkontot finns bara i Azure AD-klientorganisationen för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="dc958-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="dc958-119">Användarkontot finns i AD DS och en kopia finns också i Azure AD-klientorganisationen för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="dc958-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="dc958-120">Användarkontot i Azure AD kan också innehålla en hashtaggad version av det redan hashtaggade lösenordet för AD DS-användarkontot.</span><span class="sxs-lookup"><span data-stu-id="dc958-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="dc958-121">**Så här autentiserar Microsoft 365 användarautentiseringsuppgifter**</span><span class="sxs-lookup"><span data-stu-id="dc958-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="dc958-122">Azure AD-klientorganisationen för Microsoft 365-prenumerationen utför autentiseringen med molnidentitetskontot.</span><span class="sxs-lookup"><span data-stu-id="dc958-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="dc958-123">Azure AD-klientorganisationen för Microsoft 365-prenumerationen hanterar antingen autentiseringsprocessen eller omdirigerar användaren till en annan identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="dc958-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="dc958-124">**Bäst för**</span><span class="sxs-lookup"><span data-stu-id="dc958-124">**Best for**</span></span> | <span data-ttu-id="dc958-125">Organisationer som inte har eller behöver en lokal AD DS.</span><span class="sxs-lookup"><span data-stu-id="dc958-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="dc958-126">Organisationer som använder AD DS eller en annan identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="dc958-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="dc958-127">**Största förmånen**</span><span class="sxs-lookup"><span data-stu-id="dc958-127">**Greatest benefit**</span></span> | <span data-ttu-id="dc958-128">Enkel att använda.</span><span class="sxs-lookup"><span data-stu-id="dc958-128">Simple to use.</span></span> <span data-ttu-id="dc958-129">Inga extra katalogverktyg eller servrar krävs.</span><span class="sxs-lookup"><span data-stu-id="dc958-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="dc958-130">Användarna kan använda samma autentiseringsuppgifter när de använder lokala eller molnbaserade resurser.</span><span class="sxs-lookup"><span data-stu-id="dc958-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="dc958-131">Identitet endast för molnet</span><span class="sxs-lookup"><span data-stu-id="dc958-131">Cloud-only identity</span></span>

<span data-ttu-id="dc958-132">En identitet som bara är molnbaserad använder användarkonton som bara finns i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc958-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="dc958-133">Identitet endast i molnet används vanligtvis av små organisationer som inte har lokala servrar eller inte använder AD DS för att hantera lokala identiteter.</span><span class="sxs-lookup"><span data-stu-id="dc958-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="dc958-134">Här är de grundläggande komponenterna i identiteter som bara är molnbaserade.</span><span class="sxs-lookup"><span data-stu-id="dc958-134">Here are the basic components of cloud-only identity.</span></span>
 
![Grundläggande komponenter i identiteter med endast molnet](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="dc958-136">Både lokala användare och fjärranvändare (online) använder sina Azure AD-användarkonton och lösenord för att få åtkomst till Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="dc958-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="dc958-137">Azure AD autentiserar användarautentiseringsuppgifter baserat på dess lagrade användarkonton och lösenord.</span><span class="sxs-lookup"><span data-stu-id="dc958-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="dc958-138">Administration</span><span class="sxs-lookup"><span data-stu-id="dc958-138">Administration</span></span>
<span data-ttu-id="dc958-139">Eftersom användarkonton endast lagras i Azure AD hanterar du molnidentiteter med verktyg som administrationscentret för [Microsoft 365](../admin/add-users/index.yml) och [Windows PowerShell.](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="dc958-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](../admin/add-users/index.yml) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="dc958-140">Hybrididentitet</span><span class="sxs-lookup"><span data-stu-id="dc958-140">Hybrid identity</span></span>

<span data-ttu-id="dc958-141">Hybrididentitet använder konton som har sitt ursprung i en lokal AD DS och har en kopia i Azure AD-klientorganisationen för en Microsoft 365-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="dc958-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="dc958-142">Men de flesta ändringar flödar bara på ett sätt.</span><span class="sxs-lookup"><span data-stu-id="dc958-142">However, most changes only flow one way.</span></span> <span data-ttu-id="dc958-143">Ändringar som du gör i AD DS-användarkonton synkroniseras till deras kopia i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc958-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="dc958-144">Men ändringar som görs i molnbaserade konton i Azure AD, till exempel nya användarkonton, synkroniseras inte med AD DS.</span><span class="sxs-lookup"><span data-stu-id="dc958-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="dc958-145">Med Azure AD Connect får du löpande kontosynkronisering.</span><span class="sxs-lookup"><span data-stu-id="dc958-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="dc958-146">Den körs på en lokal server, söker efter ändringar i AD DS och vidarebefordrar ändringarna till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc958-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="dc958-147">Med Azure AD Connect kan du filtrera vilka konton som synkroniseras och om du vill synkronisera en hashtaggad version av användarlösenord, så kallad synkronisering av lösenordshashar (PHS).</span><span class="sxs-lookup"><span data-stu-id="dc958-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="dc958-148">När du implementerar hybrididentitet är din lokala AD DS den auktoritativa källan för kontoinformation.</span><span class="sxs-lookup"><span data-stu-id="dc958-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="dc958-149">Det innebär att du oftast utför administrativa uppgifter lokalt, som sedan synkroniseras till Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc958-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="dc958-150">Här är komponenterna i hybrididentitet.</span><span class="sxs-lookup"><span data-stu-id="dc958-150">Here are the components of hybrid identity.</span></span>

![Komponenter i hybrididentitet](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="dc958-152">Azure AD-klientorganisationen har en kopia av AD DS-kontona.</span><span class="sxs-lookup"><span data-stu-id="dc958-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="dc958-153">I den här konfigurationen autentiseras både lokala användare och fjärranvändare som använder Microsoft 365-molntjänster mot Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc958-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="dc958-154">Du måste alltid använda Azure AD Connect för att synkronisera användarkonton för hybrididentitet.</span><span class="sxs-lookup"><span data-stu-id="dc958-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="dc958-155">Du behöver de synkroniserade användarkontona i Azure AD för att utföra licenstilldelning och grupphantering, konfigurera behörigheter och andra administrativa uppgifter som omfattar användarkonton.</span><span class="sxs-lookup"><span data-stu-id="dc958-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="dc958-156">Administration</span><span class="sxs-lookup"><span data-stu-id="dc958-156">Administration</span></span>

<span data-ttu-id="dc958-157">Eftersom de ursprungliga och auktoritativa användarkontona lagras i den lokala AD DS hanterar du dina identiteter med samma verktyg som du hanterar dina AD DS.</span><span class="sxs-lookup"><span data-stu-id="dc958-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="dc958-158">Du använder inte administrationscentret för Microsoft 365 eller PowerShell för Microsoft 365 för att hantera synkroniserade användarkonton i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc958-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="dc958-159">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="dc958-159">Next step</span></span>

<span data-ttu-id="dc958-160">Om du behöver den molnbaserade identitetsmodellen kan du [gå till Molnidentitet.](cloud-only-identities.md)</span><span class="sxs-lookup"><span data-stu-id="dc958-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="dc958-161">Om du behöver hybrididentitetsmodellen kan du gå till [Hybrididentitet](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="dc958-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="dc958-162">Se även</span><span class="sxs-lookup"><span data-stu-id="dc958-162">See also</span></span>

[<span data-ttu-id="dc958-163">Microsoft 365 Enterprise – översikt</span><span class="sxs-lookup"><span data-stu-id="dc958-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)