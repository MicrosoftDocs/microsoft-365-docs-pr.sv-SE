---
title: Hybrididentitet och katalogsynkronisering för Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
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
description: Här beskrivs katalogsynkronisering Microsoft 365, Rensning av Active Directory Domain Services och Azure Active Directory Anslut katalogverktyget.
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927550"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="265d6-103">Hybrididentitet och katalogsynkronisering för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="265d6-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="265d6-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="265d6-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="265d6-105">Beroende på dina affärsbehov och tekniska krav är hybrididentitetsmodellen och katalogsynkroniseringen det vanligaste valet för företagskunder som inför Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="265d6-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="265d6-106">Med katalogsynkronisering kan du hantera identiteter i AD DS (Active Directory Domain Services) och alla uppdateringar av användarkonton, grupper och kontakter synkroniseras till Azure Active Directory-klientorganisationen (Azure AD) för Microsoft 365-prenumerationen.</span><span class="sxs-lookup"><span data-stu-id="265d6-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="265d6-107">När AD DS-användarkonton synkroniseras för första gången tilldelas de inte automatiskt en Microsoft 365-licens och kan inte komma åt Microsoft 365 tjänster, till exempel e-post.</span><span class="sxs-lookup"><span data-stu-id="265d6-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="265d6-108">Du måste först tilldela dem en användningsplats.</span><span class="sxs-lookup"><span data-stu-id="265d6-108">You must first assign them a usage location.</span></span> <span data-ttu-id="265d6-109">Tilldela sedan en licens till dessa användarkonton, antingen individuellt eller dynamiskt genom gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="265d6-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="265d6-110">Autentisering för hybrididentitet</span><span class="sxs-lookup"><span data-stu-id="265d6-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="265d6-111">Det finns två typer av autentisering när du använder hybrididentitetsmodellen:</span><span class="sxs-lookup"><span data-stu-id="265d6-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="265d6-112">Hanterad autentisering</span><span class="sxs-lookup"><span data-stu-id="265d6-112">Managed authentication</span></span>

  <span data-ttu-id="265d6-113">Azure AD hanterar autentiseringsprocessen med hjälp av en lokalt lagrad hash-version av lösenordet eller skickar autentiseringsuppgifterna till en lokal programvaruagent som ska autentiseras av den lokala AD DS.</span><span class="sxs-lookup"><span data-stu-id="265d6-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="265d6-114">Federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="265d6-114">Federated authentication</span></span>

  <span data-ttu-id="265d6-115">Azure AD omdirigerar klientdatorn och begär autentisering till en annan identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="265d6-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="265d6-116">Hanterad autentisering</span><span class="sxs-lookup"><span data-stu-id="265d6-116">Managed authentication</span></span>

<span data-ttu-id="265d6-117">Det finns två typer av hanterad autentisering:</span><span class="sxs-lookup"><span data-stu-id="265d6-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="265d6-118">Synkronisering av lösenordshashar (PHS)</span><span class="sxs-lookup"><span data-stu-id="265d6-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="265d6-119">Azure AD utför själva autentiseringen.</span><span class="sxs-lookup"><span data-stu-id="265d6-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="265d6-120">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="265d6-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="265d6-121">Azure AD har AD DS som utför autentiseringen.</span><span class="sxs-lookup"><span data-stu-id="265d6-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="265d6-122">Synkronisering av lösenordshashar (PHS)</span><span class="sxs-lookup"><span data-stu-id="265d6-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="265d6-123">Med PHS synkroniserar du dina AD DS-användarkonton med Microsoft 365 och hanterar användarna lokalt.</span><span class="sxs-lookup"><span data-stu-id="265d6-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="265d6-124">Hash-koderna för användarlösenord synkroniseras från din AD DS till Azure AD så att användarna har samma lösenord lokalt och i molnet.</span><span class="sxs-lookup"><span data-stu-id="265d6-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="265d6-125">Det här är det enklaste sättet att aktivera autentisering för AD DS-identiteter i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="265d6-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Synkronisering av lösenordshashar (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="265d6-127">När lösenord ändras eller återställs lokalt synkroniseras de nya lösenordshashararna till Azure AD så att användarna alltid kan använda samma lösenord för molnresurser och lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="265d6-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="265d6-128">Användarlösenorden skickas aldrig till Azure AD eller lagras i Azure AD i klartext.</span><span class="sxs-lookup"><span data-stu-id="265d6-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="265d6-129">Vissa premiumfunktioner i Azure AD, till exempel Identity Protection, kräver PHS oavsett vilken autentiseringsmetod som valts.</span><span class="sxs-lookup"><span data-stu-id="265d6-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="265d6-130">Mer [information finns i Välja rätt autentiseringsmetod.](/azure/active-directory/hybrid/choose-ad-authn)</span><span class="sxs-lookup"><span data-stu-id="265d6-130">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="265d6-131">Direktautentisering (PTA)</span><span class="sxs-lookup"><span data-stu-id="265d6-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="265d6-132">PTA tillhandahåller en enkel lösenordsverifiering för Azure AD-autentiseringstjänster med en programagent som körs på en eller flera lokala servrar för att verifiera användare direkt med din AD DS.</span><span class="sxs-lookup"><span data-stu-id="265d6-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="265d6-133">Med PTA synkroniserar du AD DS-användarkonton med Microsoft 365 och hanterar användarna lokalt.</span><span class="sxs-lookup"><span data-stu-id="265d6-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Direktautentisering (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="265d6-135">Med PTA kan användarna logga in både lokalt och via Microsoft 365 och program med sina lokala konton och lösenord.</span><span class="sxs-lookup"><span data-stu-id="265d6-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="265d6-136">Den här konfigurationen validerar användarnas lösenord direkt mot din lokala AD DS utan att lagra lösenordshashar i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="265d6-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="265d6-137">PTA är även för organisationer med säkerhetskrav att omedelbart framtvinga lokala användarkonton, lösenordsprinciper och inloggningstimmar.</span><span class="sxs-lookup"><span data-stu-id="265d6-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="265d6-138">Mer [information finns i Välja rätt autentiseringsmetod.](/azure/active-directory/hybrid/choose-ad-authn)</span><span class="sxs-lookup"><span data-stu-id="265d6-138">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="265d6-139">Federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="265d6-139">Federated authentication</span></span>

<span data-ttu-id="265d6-140">Federerad autentisering är främst för stora företag med mer komplexa autentiseringskrav.</span><span class="sxs-lookup"><span data-stu-id="265d6-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="265d6-141">AD DS-identiteter synkroniseras Microsoft 365 användarnas konton hanteras lokalt.</span><span class="sxs-lookup"><span data-stu-id="265d6-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="265d6-142">Med federerad autentisering har användarna samma lösenord lokalt och i molnet och de behöver inte logga in igen för att använda Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="265d6-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="265d6-143">Federerad autentisering kan ha stöd för ytterligare autentiseringskrav, till exempel smartkortsbaserad autentisering eller multifaktorautentisering från tredje part, och krävs vanligtvis om organisationer har ett autentiseringskrav som inte stöds inbyggt av Azure AD.</span><span class="sxs-lookup"><span data-stu-id="265d6-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="265d6-144">Mer [information finns i Välja rätt autentiseringsmetod.](/azure/active-directory/hybrid/choose-ad-authn)</span><span class="sxs-lookup"><span data-stu-id="265d6-144">See [choosing the right authentication method](/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="265d6-145">Autentisering och identitetsproviders från tredje part</span><span class="sxs-lookup"><span data-stu-id="265d6-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="265d6-146">Lokala katalogobjekt kan synkroniseras med hjälp Microsoft 365 och tillgång till molnresurser hanteras främst av en tredjepartsidentitetsleverantör (IdP).</span><span class="sxs-lookup"><span data-stu-id="265d6-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="265d6-147">Om organisationen använder en federeringslösning från tredje part kan du konfigurera inloggningen med lösningen för Microsoft 365 förutsatt att federeringslösningen från tredje part är kompatibel med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="265d6-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="265d6-148">Se Azure [AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span><span class="sxs-lookup"><span data-stu-id="265d6-148">See the [Azure AD federation compatibility list](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="265d6-149">Förberedelse av AD DS</span><span class="sxs-lookup"><span data-stu-id="265d6-149">AD DS Preparation</span></span>

<span data-ttu-id="265d6-150">För att säkerställa en smidig övergång till Microsoft 365 med hjälp av synkronisering måste du förbereda AD DS-skogen innan du påbörjar distributionen Microsoft 365 katalogsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="265d6-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="265d6-151">Katalogförberedelser bör fokusera på följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="265d6-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="265d6-152">Ta bort **dubbletter av proxyAddress-** **och userPrincipalName-attribut.**</span><span class="sxs-lookup"><span data-stu-id="265d6-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="265d6-153">Uppdatera tomma och **ogiltiga userPrincipalName-attribut** med giltiga **userPrincipalName-attribut.**</span><span class="sxs-lookup"><span data-stu-id="265d6-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="265d6-154">Ta bort ogiltiga och tveksamma tecken i attributen **givenName**, efternamn ( **sn** ), **sAMAccountName**, **displayName,** **mail,** **proxyAddresses,** **mailNickname** och **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="265d6-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="265d6-155">Mer information om hur du förbereder attribut finns i listan över attribut som [synkroniseras av Azure Active Directory synkroniseringsverktyget.](https://go.microsoft.com/fwlink/p/?LinkId=396719)</span><span class="sxs-lookup"><span data-stu-id="265d6-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="265d6-156">Det här är samma attribut som Azure AD Anslut synkroniserar.</span><span class="sxs-lookup"><span data-stu-id="265d6-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="265d6-157">Distributionsöverväganden för flera skogar</span><span class="sxs-lookup"><span data-stu-id="265d6-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="265d6-158">För flera skogar och SSO-alternativ använder du [en anpassad installation av Azure AD Anslut.](/azure/active-directory/hybrid/how-to-connect-install-custom)</span><span class="sxs-lookup"><span data-stu-id="265d6-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>
  
<span data-ttu-id="265d6-159">Om din organisation har flera skogar för autentisering (skogar för inloggning) rekommenderar vi följande:</span><span class="sxs-lookup"><span data-stu-id="265d6-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="265d6-160">**Överväg att konsolidera dina skogar.**</span><span class="sxs-lookup"><span data-stu-id="265d6-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="265d6-161">I allmänhet går det att underhålla flera skogar omkostnader.</span><span class="sxs-lookup"><span data-stu-id="265d6-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="265d6-162">Om organisationen inte har säkerhetsbegränsningar som kräver separata skogar kan du överväga att förenkla din lokala miljö.</span><span class="sxs-lookup"><span data-stu-id="265d6-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="265d6-163">**Använd endast i din primära skog för inloggning.**</span><span class="sxs-lookup"><span data-stu-id="265d6-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="265d6-164">Överväg att Microsoft 365 endast i din primära skog för inloggning för din inledande distribution av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="265d6-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="265d6-165">Om du inte kan konsolidera din AD DS-distribution med flera skogar eller använder andra katalogtjänster för att hantera identiteter kan du eventuellt synkronisera dessa med hjälp av Microsoft eller en partner.</span><span class="sxs-lookup"><span data-stu-id="265d6-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="265d6-166">Mer information [finns i Topologier för Azure AD Anslut](/azure/active-directory/hybrid/plan-connect-topologies) mer information.</span><span class="sxs-lookup"><span data-stu-id="265d6-166">See [Topologies for Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="265d6-167">Funktioner som är beroende av katalogsynkronisering</span><span class="sxs-lookup"><span data-stu-id="265d6-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="265d6-168">Katalogsynkronisering krävs för följande funktioner och funktioner:</span><span class="sxs-lookup"><span data-stu-id="265d6-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="265d6-169">Smidig och enkel Sign-On i Azure AD (SSO)</span><span class="sxs-lookup"><span data-stu-id="265d6-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="265d6-170">Skype samexistens</span><span class="sxs-lookup"><span data-stu-id="265d6-170">Skype coexistence</span></span>
- <span data-ttu-id="265d6-171">Exchange till hybriddistribution, inklusive:</span><span class="sxs-lookup"><span data-stu-id="265d6-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="265d6-172">Fullständigt delad global adresslista (GAL) mellan din lokala Exchange och Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="265d6-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="265d6-173">Synkronisera GAL-information från olika e-postsystem.</span><span class="sxs-lookup"><span data-stu-id="265d6-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="265d6-174">Möjligheten att lägga till och ta bort användare Microsoft 365 tjänsterbjudanden.</span><span class="sxs-lookup"><span data-stu-id="265d6-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="265d6-175">Det kräver följande:</span><span class="sxs-lookup"><span data-stu-id="265d6-175">This requires the following:</span></span>
  - <span data-ttu-id="265d6-176">Tvåvägssynkronisering måste konfigureras under katalogsynkroniseringskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="265d6-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="265d6-177">Som standard skriver katalogsynkroniseringsverktyg bara kataloginformation till molnet.</span><span class="sxs-lookup"><span data-stu-id="265d6-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="265d6-178">När du konfigurerar tvåvägssynkronisering kan du aktivera återskrivningsfunktioner så att ett begränsat antal objektattribut kopieras från molnet och sedan skrivs tillbaka till din lokala AD DS.</span><span class="sxs-lookup"><span data-stu-id="265d6-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="265d6-179">Återskrivning kallas även för Exchange-hybridläge.</span><span class="sxs-lookup"><span data-stu-id="265d6-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="265d6-180">En lokal Exchange hybriddistribution</span><span class="sxs-lookup"><span data-stu-id="265d6-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="265d6-181">Möjligheten att flytta vissa användarpostlådor till Microsoft 365 samtidigt som andra användarpostlådor finns kvar lokalt.</span><span class="sxs-lookup"><span data-stu-id="265d6-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="265d6-182">Valv lokala avsändare och spärrade avsändare replikeras till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="265d6-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="265d6-183">Grundläggande delegering och e-postfunktioner för att skicka för.</span><span class="sxs-lookup"><span data-stu-id="265d6-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="265d6-184">Du har ett integrerat lokalt smartkort eller en multifaktorautentiseringslösning.</span><span class="sxs-lookup"><span data-stu-id="265d6-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="265d6-185">Synkronisering av foton, miniatyrer, konferensrum och säkerhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="265d6-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="265d6-186">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="265d6-186">Next step</span></span>

<span data-ttu-id="265d6-187">När du är redo att distribuera hybrididentitet kan du gå till [förbereda för katalogsynkronisering.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="265d6-187">When you are ready to deploy hybrid identity, see [prepare for directory synchronization](prepare-for-directory-synchronization.md).</span></span>
