---
title: Hybrid identitet och katalog synkronisering för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 06/09/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Beskriver profilsynkronisering med Microsoft 365, Active Directory Domain Services Cleanup och Azure Active Directory Connect Tool.
ms.openlocfilehash: 2d3161fb835073a22743ea4f3b00ac508479f0f2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694571"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="dfe2a-103">Hybrid identitet och katalog synkronisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="dfe2a-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="dfe2a-104">*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="dfe2a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dfe2a-105">Beroende på företagets behov och tekniska krav är hybrid Identity Model och katalog synkronisering det vanligaste alternativet för företags kunder som använder Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="dfe2a-106">Med katalog-synkronisering kan du hantera identiteter i AD DS (Active Directory Domain Services) och alla uppdateringar av användar konton, grupper och kontakter synkroniseras till Azure Active Directory (Azure AD)-klient organisationen för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="dfe2a-107">När AD DS-användarkonton synkroniseras för första gången är de inte automatiskt kopplade till en Microsoft 365-licens och kan inte använda Microsoft 365-tjänster, till exempel e-post.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="dfe2a-108">Du måste först tilldela dem en användnings plats.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-108">You must first assign them a usage location.</span></span> <span data-ttu-id="dfe2a-109">Tilldela sedan en licens till dessa användar konton antingen individuellt eller dynamiskt via grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="dfe2a-110">Identifiering för Hybrid identitet</span><span class="sxs-lookup"><span data-stu-id="dfe2a-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="dfe2a-111">Det finns två typer av autentiseringsmetoder vid användning av hybrid identitets modellen:</span><span class="sxs-lookup"><span data-stu-id="dfe2a-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="dfe2a-112">Hanterad verifikation</span><span class="sxs-lookup"><span data-stu-id="dfe2a-112">Managed authentication</span></span>

  <span data-ttu-id="dfe2a-113">Azure AD hanterar autentiseringsprocessen med en lokalt lagrad hash-version av lösen ordet eller skickar autentiseringsuppgifterna till en lokal program agent för att autentiseras av den lokala AD DS-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="dfe2a-114">Federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="dfe2a-114">Federated authentication</span></span>

  <span data-ttu-id="dfe2a-115">Azure AD dirigerar om klient datorn till en annan identitets leverantör.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="dfe2a-116">Hanterad verifikation</span><span class="sxs-lookup"><span data-stu-id="dfe2a-116">Managed authentication</span></span>

<span data-ttu-id="dfe2a-117">Det finns två typer av hanterad verifikation:</span><span class="sxs-lookup"><span data-stu-id="dfe2a-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="dfe2a-118">Lösenordssynkronisering för lösen ord (PHS)</span><span class="sxs-lookup"><span data-stu-id="dfe2a-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="dfe2a-119">Azure AD utför själva autentiseringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="dfe2a-120">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="dfe2a-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="dfe2a-121">Azure AD har AD DS utför verifikationen.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="dfe2a-122">Lösenordssynkronisering för lösen ord (PHS)</span><span class="sxs-lookup"><span data-stu-id="dfe2a-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="dfe2a-123">Med PHS synkroniserar du dina AD DS-användarkonton med Microsoft 365 och hanterar användarna lokalt.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="dfe2a-124">Hashar av användar lösen ord synkroniseras från AD DS till Azure AD så att användare har samma lösen ord och i molnet.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="dfe2a-125">Det är det enklaste sättet att aktivera auktorisering för AD DS-identiteter i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Lösenordssynkronisering för lösen ord (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="dfe2a-127">När lösen ord ändras eller återställs lokalt synkroniseras de nya lösen ords-hasharna till Azure AD så att användarna kan alltid använda samma lösen ord för moln resurser och lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="dfe2a-128">Användarens lösen ord skickas aldrig till Azure AD eller lagras i en ren text i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="dfe2a-129">I vissa Premium-funktioner i Azure AD, till exempel identitets skydd, krävs PHS oavsett vilken autentiseringsmetod som är vald.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="dfe2a-130">Se [välja rätt autentiseringsmetod](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-130">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="dfe2a-131">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="dfe2a-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="dfe2a-132">PTA ger enkel lösen ords verifiering för Azure AD Domain Domain Services med en program agent som körs på en eller flera lokala servrar för att verifiera användare direkt med AD DS.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="dfe2a-133">Med PTA synkroniserar du AD DS-användarkonton med Microsoft 365 och hanterar användarna lokalt.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Direktautentisering (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="dfe2a-135">Med PTA kan användarna logga in på både lokala och Microsoft 365-resurser och-program med sitt lokala konto och lösen ord.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="dfe2a-136">Denna konfiguration verifierar användarnas lösen ord direkt mot din lokala AD DS utan att lagra lösen ord-hashar i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="dfe2a-137">PTA är också för organisationer med ett säkerhets krav för att omedelbart upprätthålla lokala användar konto tillstånd, lösen ords principer och inloggnings tider.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="dfe2a-138">Se [välja rätt autentiseringsmetod](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-138">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="dfe2a-139">Federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="dfe2a-139">Federated authentication</span></span>

<span data-ttu-id="dfe2a-140">Federerad nätverksautentisering är främst avsedd för stora företags organisationer med mer komplexa autentiseringskrav.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="dfe2a-141">AD DS-identiteter synkroniseras med Microsoft 365-och användare-konton hanteras lokalt.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="dfe2a-142">Med federerad inloggningsautentisering har användare samma lösen ord lokalt och i molnet och de behöver inte logga in igen för att använda Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="dfe2a-143">Federerad inloggningsautentisering har stöd för ytterligare autentiseringskrav, till exempel smartcard-baserad eller multifaktorautentisering, och krävs normalt när organisationer har ett autentiseringskrav som inte stöds av Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="dfe2a-144">Se [välja rätt autentiseringsmetod](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-144">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="dfe2a-145">Tredjeparts-och identitets leverantörer</span><span class="sxs-lookup"><span data-stu-id="dfe2a-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="dfe2a-146">Lokala katalog objekt kan synkroniseras till Microsoft 365 och åtkomst till moln resurser hanteras främst av en tredjeparts identitets leverantör (IdP).</span><span class="sxs-lookup"><span data-stu-id="dfe2a-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="dfe2a-147">Om din organisation använder en tredjeparts-lösning kan du konfigurera inloggning med den lösningen för Microsoft 365 förutsatt att den tredje partens Federations lösning är kompatibel med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="dfe2a-148">Mer information finns i [listan över kompatibla Azure AD-listor](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) .</span><span class="sxs-lookup"><span data-stu-id="dfe2a-148">See the [Azure AD federation compatibility list](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="dfe2a-149">AD DS-förberedelse</span><span class="sxs-lookup"><span data-stu-id="dfe2a-149">AD DS Preparation</span></span>

<span data-ttu-id="dfe2a-150">För att säkerställa en smidig över gång till Microsoft 365 genom att använda synkronisering måste du förbereda AD DS-skogen innan du påbörjar distribution av Microsoft 365-katalog.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="dfe2a-151">För att förbereda din katalog bör du fokusera på följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="dfe2a-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="dfe2a-152">Ta bort dubblerade **proxyAddress** och **userPrincipalName** -attribut.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="dfe2a-153">Uppdatera tomma och ogiltiga **userPrincipalName** -attribut med giltiga **userPrincipalName** -attribut.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="dfe2a-154">Ta bort ogiltiga och ifrågasatta tecken i attributen **givenName**, efter namn ( **SN** ), **sAMAccountName**, **DisplayName**, **e-post**, **proxyAddresses**, **smek namn**och **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="dfe2a-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="dfe2a-155">Information om hur du förbereder attribut finns i [lista över attribut som synkroniserats med Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span><span class="sxs-lookup"><span data-stu-id="dfe2a-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="dfe2a-156">Det här är samma attribut som Azure AD Connect-synkroniseringar.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="dfe2a-157">Överväganden vid distribution av flera skogar</span><span class="sxs-lookup"><span data-stu-id="dfe2a-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="dfe2a-158">För flera skogar och SSO-alternativ använder du en [anpassad installation av Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span><span class="sxs-lookup"><span data-stu-id="dfe2a-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>
  
<span data-ttu-id="dfe2a-159">Om organisationen har flera skogar för inloggningsautentisering (inloggnings skogar) rekommenderar vi följande:</span><span class="sxs-lookup"><span data-stu-id="dfe2a-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="dfe2a-160">**Överväg att konsolidera dina skogar.**</span><span class="sxs-lookup"><span data-stu-id="dfe2a-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="dfe2a-161">Vanligt vis är det mer nödvändigt att underhålla flera skogar.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="dfe2a-162">Om inte din organisation har säkerhets begränsningar som avgör behovet av separata skogar, bör du förenkla din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="dfe2a-163">**Använd endast i din primära inloggnings skog.**</span><span class="sxs-lookup"><span data-stu-id="dfe2a-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="dfe2a-164">Överväg att bara distribuera Microsoft 365 i din primära inloggnings skog för din första installation av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="dfe2a-165">Om du inte kan konsolidera AD DS-distributionen med flera skogar eller använder andra katalog tjänster för att hantera identiteter kanske du kan synkronisera dessa med hjälp av Microsoft eller en partner.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="dfe2a-166">Se [topologier för Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) för mer information.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-166">See [Topologies for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="dfe2a-167">Funktioner som är beroende av profilsynkronisering</span><span class="sxs-lookup"><span data-stu-id="dfe2a-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="dfe2a-168">Katalog-synkronisering krävs för följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="dfe2a-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="dfe2a-169">Enkel inloggning (SSO) för Azure AD</span><span class="sxs-lookup"><span data-stu-id="dfe2a-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="dfe2a-170">Skype-samexistens</span><span class="sxs-lookup"><span data-stu-id="dfe2a-170">Skype coexistence</span></span>
- <span data-ttu-id="dfe2a-171">Exchange hybrid distribution, inklusive:</span><span class="sxs-lookup"><span data-stu-id="dfe2a-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="dfe2a-172">Fullständig delad global adress lista mellan den lokala Exchange-miljön och Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="dfe2a-173">Synkronisera GAL-information från olika e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="dfe2a-174">Möjlighet att lägga till och ta bort användare från Microsoft 365-tjänst.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="dfe2a-175">Detta kräver följande:</span><span class="sxs-lookup"><span data-stu-id="dfe2a-175">This requires the following:</span></span>
  - <span data-ttu-id="dfe2a-176">Dubbelriktad synkronisering måste konfigureras under installationen av katalog synkronisering.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="dfe2a-177">Som standard skriver Directory-synkroniseringsfunktionen bara katalog information till molnet.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="dfe2a-178">När du konfigurerar dubbelriktad synkronisering kan du aktivera funktionen för att skriva tillbaka så att ett begränsat antal objektattribut kopieras från molnet och sedan skrivas tillbaka till din lokala AD DS.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="dfe2a-179">Åter Skriv tillbaka kallas även för Exchange hybrid-läge.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="dfe2a-180">En lokal Exchange hybrid distribution</span><span class="sxs-lookup"><span data-stu-id="dfe2a-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="dfe2a-181">Möjlighet att flytta vissa användar post lådor till Microsoft 365 samtidigt som du håller andra användar post lådor lokalt.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="dfe2a-182">Betrodda avsändare och spärrade avsändare replikeras till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="dfe2a-183">Grundläggande delegering och skicka med e-post.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="dfe2a-184">Du har en integrerad lokal smart kort-eller Multi-Factor-autentiseringstjänst.</span><span class="sxs-lookup"><span data-stu-id="dfe2a-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="dfe2a-185">Synkronisering av foton, miniatyrer, konferens rum och säkerhets grupper</span><span class="sxs-lookup"><span data-stu-id="dfe2a-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="dfe2a-186">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="dfe2a-186">Next step</span></span>

<span data-ttu-id="dfe2a-187">När du är redo att distribuera Hybrid identiteter läser du [förbereda för att etablera användare](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="dfe2a-187">When you are ready to deploy hybrid identity, see [prepare to provision users](prepare-for-directory-synchronization.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dfe2a-188">Se även</span><span class="sxs-lookup"><span data-stu-id="dfe2a-188">See also</span></span>

[<span data-ttu-id="dfe2a-189">Översikt över Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dfe2a-189">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)

