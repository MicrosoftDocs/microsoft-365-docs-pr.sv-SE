---
title: Förbereda katalogsynkronisering till Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Här beskrivs hur du förbereder för att tillhandahålla användare Microsoft 365 med hjälp av katalogsynkronisering och de långsiktiga fördelarna med den här metoden.
ms.openlocfilehash: 1fe99247a5c50c7bb8fc7eb1347ce6a4cd6aad94
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927330"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="d9eb3-103">Förbereda katalogsynkronisering till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d9eb3-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="d9eb3-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d9eb3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d9eb3-105">Fördelarna med hybrididentitet och katalogsynkronisering din organisation är:</span><span class="sxs-lookup"><span data-stu-id="d9eb3-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="d9eb3-106">Minska administratörsprogrammen i organisationen</span><span class="sxs-lookup"><span data-stu-id="d9eb3-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="d9eb3-107">Om du vill aktiverar du scenariot för enkel inloggning</span><span class="sxs-lookup"><span data-stu-id="d9eb3-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="d9eb3-108">Automatisera kontoändringar i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d9eb3-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="d9eb3-109">Mer information om fördelarna med att använda katalogsynkronisering finns i hybrididentitet med [Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) och [hybrididentitet för Microsoft 365.](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="d9eb3-109">For more information about the advantages of using directory synchronization, see [hybrid identity with Azure Active Directory (Azure AD)](/azure/active-directory/hybrid/whatis-hybrid-identity) and [hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="d9eb3-110">Men katalogsynkronisering kräver planering och förberedelse för att säkerställa att din AD DS (Active Directory Domain Services) synkroniserar till Azure AD-klientorganisationen för Microsoft 365-prenumerationen med så få fel som möjligt.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure AD tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="d9eb3-111">Följ de här anvisningarna för att uppnå bästa resultat.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="d9eb3-112">1. Katalogrensningsuppgifter</span><span class="sxs-lookup"><span data-stu-id="d9eb3-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="d9eb3-113">Innan du synkroniserar DIN AD DS till Azure AD-klientorganisationen måste du rensa dina AD DS.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d9eb3-114">Om du inte rensar AD DS innan du synkroniserar kan det leda till en betydande negativ inverkan på distributionsprocessen.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-114">If you don't perform AD DS cleanup before you synchronize, it can lead to a significant negative impact on the deployment process.</span></span> <span data-ttu-id="d9eb3-115">Det kan ta dagar eller veckor att gå igenom hela katalogsynkroniseringen, att identifiera fel och omsynkronisering.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="d9eb3-116">Utför följande rensningsuppgifter i AD DS för varje användarkonto som ska tilldelas en Microsoft 365-licens:</span><span class="sxs-lookup"><span data-stu-id="d9eb3-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="d9eb3-117">Kontrollera en giltig och unik e-postadress i **attributet proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="d9eb3-118">Ta bort alla dubblettvärden i **attributet proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="d9eb3-119">Om möjligt bör du säkerställa ett giltigt och unikt värde för **attributet userPrincipalName** i användarens **användarobjekt.**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="d9eb3-120">För bästa möjliga synkronisering ser du till att AD DS UPN matchar Azure AD UPN.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="d9eb3-121">Om en användare inte har något värde för **attributet userPrincipalName** måste användarobjektet innehålla ett giltigt och unikt värde för **attributet sAMAccountName.** </span><span class="sxs-lookup"><span data-stu-id="d9eb3-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="d9eb3-122">Ta bort alla dubblettvärden i **attributet userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="d9eb3-123">För optimal användning av den globala adresslistan (GAL) ser du till att informationen i följande attribut för AD DS-användarkontot är korrekt:</span><span class="sxs-lookup"><span data-stu-id="d9eb3-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="d9eb3-124">givenName</span><span class="sxs-lookup"><span data-stu-id="d9eb3-124">givenName</span></span>
   - <span data-ttu-id="d9eb3-125">efternamn</span><span class="sxs-lookup"><span data-stu-id="d9eb3-125">surname</span></span>
   - <span data-ttu-id="d9eb3-126">visningsNamn</span><span class="sxs-lookup"><span data-stu-id="d9eb3-126">displayName</span></span>
   - <span data-ttu-id="d9eb3-127">Befattning</span><span class="sxs-lookup"><span data-stu-id="d9eb3-127">Job Title</span></span>
   - <span data-ttu-id="d9eb3-128">Department</span><span class="sxs-lookup"><span data-stu-id="d9eb3-128">Department</span></span>
   - <span data-ttu-id="d9eb3-129">Office</span><span class="sxs-lookup"><span data-stu-id="d9eb3-129">Office</span></span>
   - <span data-ttu-id="d9eb3-130">Telefonnr till arbetet</span><span class="sxs-lookup"><span data-stu-id="d9eb3-130">Office Phone</span></span>
   - <span data-ttu-id="d9eb3-131">Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="d9eb3-131">Mobile Phone</span></span>
   - <span data-ttu-id="d9eb3-132">Faxnummer</span><span class="sxs-lookup"><span data-stu-id="d9eb3-132">Fax Number</span></span>
   - <span data-ttu-id="d9eb3-133">Gatuadress</span><span class="sxs-lookup"><span data-stu-id="d9eb3-133">Street Address</span></span>
   - <span data-ttu-id="d9eb3-134">Ort</span><span class="sxs-lookup"><span data-stu-id="d9eb3-134">City</span></span>
   - <span data-ttu-id="d9eb3-135">Region</span><span class="sxs-lookup"><span data-stu-id="d9eb3-135">State or Province</span></span>
   - <span data-ttu-id="d9eb3-136">Postnummer</span><span class="sxs-lookup"><span data-stu-id="d9eb3-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="d9eb3-137">Land eller region</span><span class="sxs-lookup"><span data-stu-id="d9eb3-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="d9eb3-138">2. Förberedelse av katalogobjekt och katalogattribut</span><span class="sxs-lookup"><span data-stu-id="d9eb3-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="d9eb3-139">För att synkroniseringen mellan AD DS och Microsoft 365 ska fungera måste AD DS-attributen vara ordentligt förberedda.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="d9eb3-140">Du måste till exempel se till att inga specifika tecken används i vissa attribut som synkroniseras med Microsoft 365-miljön.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="d9eb3-141">Katalogsynkroniseringen misslyckas inte om oväntade tecken visas, men kan returnera en varning.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="d9eb3-142">Ogiltiga tecken leder till att katalogsynkroniseringen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="d9eb3-143">Katalogsynkroniseringen misslyckas också om en del av DINA AD DS-användare har ett eller flera dubblettattribut.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="d9eb3-144">Varje användare måste ha unika attribut.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="d9eb3-145">Attributen du behöver förbereda visas här:</span><span class="sxs-lookup"><span data-stu-id="d9eb3-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="d9eb3-146">**visningsNamn**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-146">**displayName**</span></span>

  - <span data-ttu-id="d9eb3-147">Om attributet finns i användarobjektet synkroniseras det med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="d9eb3-148">Om det här attributet finns i användarobjektet måste det ha ett värde.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="d9eb3-149">Det innebär att attributet inte får vara tomt.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="d9eb3-150">Maximalt antal tecken: 256</span><span class="sxs-lookup"><span data-stu-id="d9eb3-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="d9eb3-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-151">**givenName**</span></span>

  - <span data-ttu-id="d9eb3-152">Om attributet finns i användarobjektet synkroniseras det med Microsoft 365, men det krävs eller används inte av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="d9eb3-153">Maximalt antal tecken: 64</span><span class="sxs-lookup"><span data-stu-id="d9eb3-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="d9eb3-154">**mail**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-154">**mail**</span></span>

  - <span data-ttu-id="d9eb3-155">Attributvärdet måste vara unikt i katalogen.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d9eb3-156">Om det finns dubblettvärden synkroniseras den första användaren med värdet.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="d9eb3-157">Efterföljande användare visas inte i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="d9eb3-158">Du måste antingen ändra värdet i Microsoft 365 eller båda värdena i AD DS för att båda användarna ska visas i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="d9eb3-159">**mailNickname** (Exchange-alias)</span><span class="sxs-lookup"><span data-stu-id="d9eb3-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="d9eb3-160">Attributvärdet kan inte börja med en punkt (.).</span><span class="sxs-lookup"><span data-stu-id="d9eb3-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="d9eb3-161">Attributvärdet måste vara unikt i katalogen.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d9eb3-162">Understreck ("_") i det synkroniserade namnet anger att det ursprungliga värdet för det här attributet innehåller ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="d9eb3-163">Mer information om det här attributet finns i [Exchange-aliasattributet](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="d9eb3-163">For more information on this attribute, see [Exchange alias attribute](/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="d9eb3-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="d9eb3-165">Attribut med flera värden</span><span class="sxs-lookup"><span data-stu-id="d9eb3-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="d9eb3-166">Maximalt antal tecken per värde: 256</span><span class="sxs-lookup"><span data-stu-id="d9eb3-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="d9eb3-167">Attributvärdet får inte innehålla blanksteg.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="d9eb3-168">Attributvärdet måste vara unikt i katalogen.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="d9eb3-169">Ogiltiga tecken: \< \> ( ) ; , [ ] " '</span><span class="sxs-lookup"><span data-stu-id="d9eb3-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>

    <span data-ttu-id="d9eb3-170">Observera att ogiltiga tecken gäller tecknen som kommer efter avgränsaren och ":", så att SMTP:User@contso.com är tillåtet, men SMTP:user:M@contoso.com är det inte.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d9eb3-171">Alla SMTP-adresser (Simple Mail Transport Protocol) ska följa e-poststandarderna.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="d9eb3-172">Ta bort dubbletter eller oönskade adresser om de finns.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-172">Remove duplicate or unwanted addresses if they exist.</span></span>

- <span data-ttu-id="d9eb3-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="d9eb3-174">Maximalt antal tecken: 20</span><span class="sxs-lookup"><span data-stu-id="d9eb3-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="d9eb3-175">Attributvärdet måste vara unikt i katalogen.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="d9eb3-176">Ogiltiga tecken: [ \ " | , / : \< \> + = ; ?</span><span class="sxs-lookup"><span data-stu-id="d9eb3-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="d9eb3-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="d9eb3-177">\* ']</span></span>
  - <span data-ttu-id="d9eb3-178">Om en användare har ett **ogiltigt sAMAccountName-attribut** men ett giltigt **userPrincipalName-attribut** skapas användarkontot i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="d9eb3-179">Om både **sAMAccountName** och **userPrincipalName** är ogiltiga måste AD DS-attributet **userPrincipalName** uppdateras.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="d9eb3-180">**sn** (efternamn)</span><span class="sxs-lookup"><span data-stu-id="d9eb3-180">**sn** (surname)</span></span>

  - <span data-ttu-id="d9eb3-181">Om attributet finns i användarobjektet synkroniseras det med Microsoft 365, men det krävs eller används inte av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="d9eb3-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-182">**targetAddress**</span></span>

    <span data-ttu-id="d9eb3-183">Attributet **targetAddress** (till exempel SMTP:tom@contoso.com) som fylls i för användaren måste visas i GAL i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="d9eb3-184">Vid migrering av tredjepartsmeddelanden kräver detta Microsoft 365-schematillägget för AD DS.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="d9eb3-185">Microsoft 365-schematillägget skulle också lägga till andra användbara attribut för att hantera Microsoft 365-objekt som fylls i med hjälp av ett katalogsynkroniseringsverktyg från AD DS.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="d9eb3-186">Till exempel läggs **attributet msExchHideFromAddressLists** till för att hantera dolda postlådor eller distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="d9eb3-187">Maximalt antal tecken: 256</span><span class="sxs-lookup"><span data-stu-id="d9eb3-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="d9eb3-188">Attributvärdet får inte innehålla blanksteg.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="d9eb3-189">Attributvärdet måste vara unikt i katalogen.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="d9eb3-190">Ogiltiga tecken: \ \< \> ( ) ; , [ ] "</span><span class="sxs-lookup"><span data-stu-id="d9eb3-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="d9eb3-191">Alla SMTP-adresser (Simple Mail Transport Protocol) ska följa e-poststandarderna.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="d9eb3-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="d9eb3-193">Attributet **userPrincipalName** måste vara i inloggningsformat på Internet, där användarnamnet följs av at-tecknet (@) och ett domännamn: till exempel user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="d9eb3-194">Alla SMTP-adresser (Simple Mail Transport Protocol) ska följa e-poststandarderna.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="d9eb3-195">Attributet **userPrincipalName** får ha högst 113 tecken.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-195">The maximum number of characters for the **userPrincipalName** attribute is 113.</span></span> <span data-ttu-id="d9eb3-196">Ett visst antal tecken tillåts före och efter at-tecknet (@), enligt följande:</span><span class="sxs-lookup"><span data-stu-id="d9eb3-196">A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="d9eb3-197">Maximalt antal tecken för användarnamnet som står framför at-tecknet (@): 64</span><span class="sxs-lookup"><span data-stu-id="d9eb3-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="d9eb3-198">Maximalt antal tecken för domännamnet som följer efter at-tecknet (@): 48</span><span class="sxs-lookup"><span data-stu-id="d9eb3-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="d9eb3-199">Ogiltiga tecken: \ % &amp; \* + / = ?</span><span class="sxs-lookup"><span data-stu-id="d9eb3-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="d9eb3-200">{ } | \< \> ( ) ; : , [ ] "</span><span class="sxs-lookup"><span data-stu-id="d9eb3-200">{ } | \< \> ( ) ; : , [ ] "</span></span>
  - <span data-ttu-id="d9eb3-201">Tillåtna tecken: A – Ö, a - z, 0 – 9, ' .</span><span class="sxs-lookup"><span data-stu-id="d9eb3-201">Characters allowed: A – Z, a - z, 0 – 9, ' .</span></span> <span data-ttu-id="d9eb3-202">- _ !</span><span class="sxs-lookup"><span data-stu-id="d9eb3-202">- _ !</span></span> <span data-ttu-id="d9eb3-203"># ^ ~</span><span class="sxs-lookup"><span data-stu-id="d9eb3-203"># ^ ~</span></span>
  - <span data-ttu-id="d9eb3-204">Bokstäver med diakritiska tecken som omljud, accenter och tilde är ogiltiga tecken.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-204">Letters with diacritical marks, such as umlauts, accents, and tildes, are invalid characters.</span></span>
  - <span data-ttu-id="d9eb3-205">Tecknet @ krävs i varje **userPrincipalName-värde.**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-205">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="d9eb3-206">Tecknet @ får inte vara det första tecknet i varje **userPrincipalName-värde.**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-206">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="d9eb3-207">Användarnamnet får inte sluta med punkt (.), et-tecken ( &amp; ), blanksteg eller at-tecken (@).</span><span class="sxs-lookup"><span data-stu-id="d9eb3-207">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="d9eb3-208">Användarnamnet får inte innehålla blanksteg.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-208">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="d9eb3-209">Dirigerbara domäner måste användas. Lokala eller interna domäner kan till exempel inte användas.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-209">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="d9eb3-210">Unicode konverteras till understreck.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-210">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="d9eb3-211">**userPrincipalName** får inte innehålla dubblettvärden i katalogen.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-211">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="d9eb3-212">3. Förbereda attributet userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d9eb3-212">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="d9eb3-213">Active Directory har utformats så att slutanvändarna i organisationen ska kunna logga in i katalogen med hjälp av **antingen sAMAccountName** eller **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-213">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="d9eb3-214">På samma sätt kan slutanvändarna logga in på Microsoft 365 med hjälp av huvudnamnet (UPN) för sitt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-214">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="d9eb3-215">Katalogsynkroniseringen försöker skapa nya användare i Azure Active Directory med samma UPN som finns i DIN AD DS.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-215">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="d9eb3-216">UPN är formaterat som en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-216">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="d9eb3-217">I Microsoft 365 är UPN standardattributet som används för att generera e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-217">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="d9eb3-218">Det är enkelt att ange olika värden för **userPrincipalName** (i AD DS och i Azure AD) och den primära e-postadressen i **proxyAddresses.**</span><span class="sxs-lookup"><span data-stu-id="d9eb3-218">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="d9eb3-219">De olika värdena kan vara förvirrande för administratörer och slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-219">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="d9eb3-220">Därför är det bäst att attributen stämmer överens.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-220">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="d9eb3-221">Om du vill uppfylla kraven för enkel inloggning med Active Directory Federation Services (AD FS) 2.0 måste du kontrollera att UPN-namn i Azure Active Directory och AD DS matchar och använder ett giltigt domännamnsområde.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-221">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="d9eb3-222">4. Lägg till ett alternativt UPN-suffix i AD DS</span><span class="sxs-lookup"><span data-stu-id="d9eb3-222">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="d9eb3-223">Du kan behöva lägga till ett alternativt UPN-suffix för att associera användarens företagsautentiseringsuppgifter med Microsoft 365-miljön.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-223">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="d9eb3-224">Ett UPN-suffix är den del av ett UPN som står till höger om @-tecknet.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-224">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="d9eb3-225">UPN-nummer som används för enkel inloggning får innehålla bokstäver, siffror, punkter, bindestreck och understreck, men inga andra typer av tecken.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-225">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="d9eb3-226">Mer information om hur du lägger till ett alternativt UPN-suffix i Active Directory finns i [Förbereda katalogsynkronisering.]( https://go.microsoft.com/fwlink/p/?LinkId=525430)</span><span class="sxs-lookup"><span data-stu-id="d9eb3-226">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="d9eb3-227">5. Matcha AD DS UPN med Microsoft 365 UPN</span><span class="sxs-lookup"><span data-stu-id="d9eb3-227">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="d9eb3-228">Om du redan har konfigurerat katalogsynkronisering kanske användarens UPN för Microsoft 365 inte överensstämmer med användarens AD DS UPN som definierats i AD DS.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-228">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="d9eb3-229">Detta kan inträffa när en användare har tilldelats en licens innan domänen verifierades.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-229">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="d9eb3-230">Lös det genom att använda [PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396730) för att åtgärda UPN-dubbletter och uppdatera användarens UPN så att MICROSOFT 365 UPN matchar företagets användarnamn och domän.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-230">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="d9eb3-231">Om du uppdaterar UPN i AD DS och vill att det synkroniseras med Azure Active Directory-identiteten måste du ta bort användarens licens i Microsoft 365 innan du gör ändringarna i AD DS.</span><span class="sxs-lookup"><span data-stu-id="d9eb3-231">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="d9eb3-232">Se även [Så här förbereder du en icke-dirigerbar domän (till exempel .local) för katalogsynkronisering.](prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="d9eb3-232">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d9eb3-233">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="d9eb3-233">Next steps</span></span>

<span data-ttu-id="d9eb3-234">Om du har utfört steg 1 till 5 ovan går du till [Konfigurera katalogsynkronisering](set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="d9eb3-234">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>