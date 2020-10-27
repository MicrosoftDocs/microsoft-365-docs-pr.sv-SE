---
title: Integrera ServiceNow biljetter i säkerhets Center och Compliance Center för Microsoft 365
description: Lär dig hur du skapar och spårar biljetter i ServiceNow från säkerhets Center och Center för Microsoft 365.
keywords: säkerhet, Microsoft 365, M365, efterlevnad, Compliance Center, säkerhets Center, ServiceNow, biljetter, uppgifter, snö, anslutning
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: a2650efbac0966b84e6fbfd6ce78cb732f4933b3
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769659"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="d6d46-104">Integrera ServiceNow biljetter i säkerhets Center och Compliance Center för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d6d46-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="d6d46-105">**Förhands gransknings perioden för ServiceNow-kopplingen slutar**</span><span class="sxs-lookup"><span data-stu-id="d6d46-105">**The preview period for the ServiceNow connector is ending**</span></span><br>
><span data-ttu-id="d6d46-106">Denna funktion kommer inte längre att vara tillgänglig i slutet av november 2020.</span><span class="sxs-lookup"><span data-stu-id="d6d46-106">This capability will no longer available by the end of November 2020.</span></span> <span data-ttu-id="d6d46-107">Tack för din feedback och fortsatta support medan vi bestämmer nästa steg.</span><span class="sxs-lookup"><span data-stu-id="d6d46-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="d6d46-108">ServiceNow är en populär plattform för moln datorer som hjälper företag att hantera digitala arbets flöden för företag.</span><span class="sxs-lookup"><span data-stu-id="d6d46-108">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="d6d46-109">Deras plattform har arbets flöden, arbets flöden och kund arbets flöden.</span><span class="sxs-lookup"><span data-stu-id="d6d46-109">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="d6d46-110">Lär dig mer om ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d6d46-110">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="d6d46-111">Microsoft samarbetar med ServiceNow för att göra det lättare för IT-administratörer att hantera sina biljetter och uppgifter på båda plattformarna.</span><span class="sxs-lookup"><span data-stu-id="d6d46-111">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="d6d46-112">[Microsoft 365 säkerhets Center](overview-security-center.md) och [Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) förbättras med möjligheten att skapa och spåra biljetter i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d6d46-112">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="d6d46-113">**Hantera ServiceNow biljetter i säkerhets Center**</span><span class="sxs-lookup"><span data-stu-id="d6d46-113">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="d6d46-114">**Hantera ServiceNow biljetter i överensstämmelse Center** (kommer snart)</span><span class="sxs-lookup"><span data-stu-id="d6d46-114">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6d46-115">Krav</span><span class="sxs-lookup"><span data-stu-id="d6d46-115">Prerequisites</span></span>

<span data-ttu-id="d6d46-116">Åtkomst till Microsoft 365 säkerhets Center eller Compliance Center och en ServiceNow-instans med:</span><span class="sxs-lookup"><span data-stu-id="d6d46-116">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="d6d46-117">Kingston eller senare version</span><span class="sxs-lookup"><span data-stu-id="d6d46-117">Kingston or higher version</span></span>
* <span data-ttu-id="d6d46-118">Ha administratörs behörighet</span><span class="sxs-lookup"><span data-stu-id="d6d46-118">Have admin HI credentials</span></span>
* <span data-ttu-id="d6d46-119">Ha administratörs behörighet för din mål leverantörs instans</span><span class="sxs-lookup"><span data-stu-id="d6d46-119">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="d6d46-120">ServiceNow rekommenderar att användarna behåller standardinställningarna i din ServiceNow-förekomst.</span><span class="sxs-lookup"><span data-stu-id="d6d46-120">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="d6d46-121">Det kan orsaka fel när du har anpassat installations check lista och integrering med Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="d6d46-121">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="d6d46-122">Data Exchange</span><span class="sxs-lookup"><span data-stu-id="d6d46-122">Data exchange</span></span>

<span data-ttu-id="d6d46-123">När du ansluter Microsoft 365 säkerhets Center eller Compliance Center till ServiceNow, får Microsoft följande ytterligare data:</span><span class="sxs-lookup"><span data-stu-id="d6d46-123">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="d6d46-124">ServiceNow instans namn</span><span class="sxs-lookup"><span data-stu-id="d6d46-124">ServiceNow instance name</span></span>
* <span data-ttu-id="d6d46-125">ServiceNow klient-ID</span><span class="sxs-lookup"><span data-stu-id="d6d46-125">ServiceNow client ID</span></span>
* <span data-ttu-id="d6d46-126">ServiceNow klient hemlighet</span><span class="sxs-lookup"><span data-stu-id="d6d46-126">ServiceNow client secret</span></span>
* <span data-ttu-id="d6d46-127">ServiceNow åtkomst & uppdaterings-token</span><span class="sxs-lookup"><span data-stu-id="d6d46-127">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="d6d46-128">När du skapar en ServiceNow-biljett från Microsoft 365 Security Center eller Compliance Center skickas följande data till ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="d6d46-128">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="d6d46-129">Användar-ID som initierar biljett skapandet</span><span class="sxs-lookup"><span data-stu-id="d6d46-129">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="d6d46-130">Aktivitets namn</span><span class="sxs-lookup"><span data-stu-id="d6d46-130">Task name</span></span>
* <span data-ttu-id="d6d46-131">Beskrivning av uppgift</span><span class="sxs-lookup"><span data-stu-id="d6d46-131">Task description</span></span>
* <span data-ttu-id="d6d46-132">Priority</span><span class="sxs-lookup"><span data-stu-id="d6d46-132">Priority</span></span>
* <span data-ttu-id="d6d46-133">Förfallo datum</span><span class="sxs-lookup"><span data-stu-id="d6d46-133">Due date</span></span>
* <span data-ttu-id="d6d46-134">Rekommendations källa (användar rekommendation eller Microsoft-rekommendation)</span><span class="sxs-lookup"><span data-stu-id="d6d46-134">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="d6d46-135">Rekommendations kategori (enheter, data, appar, identitet, infrastruktur)</span><span class="sxs-lookup"><span data-stu-id="d6d46-135">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="d6d46-136">Anslut till ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d6d46-136">Connect to ServiceNow</span></span>

<span data-ttu-id="d6d46-137">Gå till [skapa och spåra ServiceNow biljetter i Microsoft 365 säkerhets Center](tickets-security-center.md) för att lära dig hur du ansluter till ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d6d46-137">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="d6d46-138">Att ansluta från Microsoft 365 Compliance Center kommer snart.</span><span class="sxs-lookup"><span data-stu-id="d6d46-138">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="d6d46-139">Felsökning</span><span class="sxs-lookup"><span data-stu-id="d6d46-139">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="d6d46-140">Du får ett fel meddelande i det första steget i installations check listan (OAuth-skapande)</span><span class="sxs-lookup"><span data-stu-id="d6d46-140">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="d6d46-141">**Fel meddelande** : Läs åtgärd mot ' oauth_entity ' från omfattning ' x_mioms_m365ticket ' har nekats på grund av tabellens åtkomst policy för kors omfånget</span><span class="sxs-lookup"><span data-stu-id="d6d46-141">**Error Message** : Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused because of the table's cross-scope access policy</span></span>

<span data-ttu-id="d6d46-142">Programmet förutsätter att en administratör på ServiceNow-instansen kan skapa och läsa OAuth-enheter.</span><span class="sxs-lookup"><span data-stu-id="d6d46-142">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="d6d46-143">Det här felet kan orsakas av en anpassning i din instans av ServiceNow som begränsar vem som kan skapa eller läsa OAuth-enheter.</span><span class="sxs-lookup"><span data-stu-id="d6d46-143">This error could be caused by a customization in your instance of ServiceNow that restricts who can create or read OAuth entities.</span></span>

<span data-ttu-id="d6d46-144">**ServiceNow rekommenderar att användarna behåller standardinställningarna.**</span><span class="sxs-lookup"><span data-stu-id="d6d46-144">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="d6d46-145">Ange konfigureringen av tabellen "program register" till standard:</span><span class="sxs-lookup"><span data-stu-id="d6d46-145">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="d6d46-146">Label = program register</span><span class="sxs-lookup"><span data-stu-id="d6d46-146">Label = Application Registeries</span></span>
* <span data-ttu-id="d6d46-147">Namn = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="d6d46-147">Name = oauth_entity</span></span>
* <span data-ttu-id="d6d46-148">Tillgänglig från = alla program omfattningar</span><span class="sxs-lookup"><span data-stu-id="d6d46-148">Accessible from = All application scopes</span></span>
* <span data-ttu-id="d6d46-149">Kryss rutan kan läsa = markerad</span><span class="sxs-lookup"><span data-stu-id="d6d46-149">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="d6d46-150">Verifiera den OAuth-enhet som har skapats för Microsoft 365 Security & Compliance Connector</span><span class="sxs-lookup"><span data-stu-id="d6d46-150">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="d6d46-151">Gå till tabellen program register ( **meny > systemet OAuth > program register** ) i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d6d46-151">Go to application registries table ( **Menu > System OAuth > Application Registry** ) in ServiceNow.</span></span> <span data-ttu-id="d6d46-152">Hitta den OAuth-enhet som skapades av dig, med det namn som du har tilldelat den.</span><span class="sxs-lookup"><span data-stu-id="d6d46-152">Find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="signing-in-as-the-integration-user"></a><span data-ttu-id="d6d46-153">Logga in som integrations användare</span><span class="sxs-lookup"><span data-stu-id="d6d46-153">Signing in as the integration user</span></span>

<span data-ttu-id="d6d46-154">Innan du godkänner anslutningen mellan Microsoft 365 säkerhets Center och ServiceNow bör du kontrol lera att du använder användar inloggning och lösen ord som du skapade i installations stegen.</span><span class="sxs-lookup"><span data-stu-id="d6d46-154">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user sign in and password you created in the installation steps.</span></span> <span data-ttu-id="d6d46-155">Använd inte dina personliga autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="d6d46-155">Don't use your personal credentials.</span></span>

1. <span data-ttu-id="d6d46-156">Gå till sidan verifiering i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d6d46-156">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="d6d46-157">Om du är inloggad med dina personliga autentiseringsuppgifter väljer **du länken inte** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="d6d46-157">If you're signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="d6d46-158">Logga in på ServiceNow som integrations användaren som du skapade tidigare från check lista för installation.</span><span class="sxs-lookup"><span data-stu-id="d6d46-158">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="d6d46-159">Välj **Tillåt** på ServiceNow-sidan som frågar om säkerhet + kompatibilitetskontrollen kan ansluta till ditt ServiceNow-konto.</span><span class="sxs-lookup"><span data-stu-id="d6d46-159">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="d6d46-160">Fortsätt med konfigurations stegen.</span><span class="sxs-lookup"><span data-stu-id="d6d46-160">Continue with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="d6d46-161">Så här verifierar du integrations användaren som har skapats med check lista för installation för Microsoft 365 Security & Compliance Connector</span><span class="sxs-lookup"><span data-stu-id="d6d46-161">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="d6d46-162">Gå till tabellen användare **(meny > användar Administration > användare** ) i ServiceNow och leta reda på den integrations användare som du har skapat, med det namn som du har tilldelat.</span><span class="sxs-lookup"><span data-stu-id="d6d46-162">Go to Users Table **(Menu > User Administration > Users** ) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="d6d46-163">Ditt företag har en enkel inloggning som hindrar dig från att ansluta till ServiceNow via Microsoft 365 säkerhets Center</span><span class="sxs-lookup"><span data-stu-id="d6d46-163">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="d6d46-164">Om ditt företag har aktiverat enkel inloggning och du får ett fel meddelande eller att inloggningen Miss lyckas följer du en av de två lösningarna.</span><span class="sxs-lookup"><span data-stu-id="d6d46-164">If your company has enabled single sign-on and you receive an error or sign in is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a><span data-ttu-id="d6d46-165">Logga in på ServiceNow som integrations användare</span><span class="sxs-lookup"><span data-stu-id="d6d46-165">Sign in to ServiceNow as the integration user</span></span>

1. <span data-ttu-id="d6d46-166">Gå tillbaka till sidan för auktorisering i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d6d46-166">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="d6d46-167">Markera länken **inte** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="d6d46-167">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="d6d46-168">Logga in på ServiceNow som integrations användaren som du skapade tidigare från check lista för installation.</span><span class="sxs-lookup"><span data-stu-id="d6d46-168">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="d6d46-169">Välj **Tillåt** på ServiceNow-sidan som frågar om säkerhet + kompatibilitetskontrollen kan ansluta till ditt ServiceNow-konto.</span><span class="sxs-lookup"><span data-stu-id="d6d46-169">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="d6d46-170">Fortsätt med konfigurations stegen.</span><span class="sxs-lookup"><span data-stu-id="d6d46-170">Continue with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="d6d46-171">Skapa en säkerhets administratörs användare</span><span class="sxs-lookup"><span data-stu-id="d6d46-171">Create a security admin user</span></span>

1. <span data-ttu-id="d6d46-172">Skapa en användare med administratörs privilegier i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d6d46-172">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="d6d46-173">Användaren måste ha samma namn och e-postadress som integrations användaren som du skapade från check lista för installation.</span><span class="sxs-lookup"><span data-stu-id="d6d46-173">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="d6d46-174">Du kan ta bort rollen som säkerhets administratör när inloggningen är klar.</span><span class="sxs-lookup"><span data-stu-id="d6d46-174">You can remove the security admin role once sign-in and connection has been completed.</span></span>
2. <span data-ttu-id="d6d46-175">Logga in på Microsoft 365 säkerhets Center som användare och följ anvisningarna nedan.</span><span class="sxs-lookup"><span data-stu-id="d6d46-175">Sign in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="d6d46-176">IP-filtrering</span><span class="sxs-lookup"><span data-stu-id="d6d46-176">IP filtering</span></span>

<span data-ttu-id="d6d46-177">Om du har aktiverat IP-filtrering kan du behöva uttryckligen tillåta IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="d6d46-177">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="d6d46-178">Se [åtkomst kontroll för IP-adresser](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) för information om hur du tillåter IP-intervall i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="d6d46-178">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="d6d46-179">Se [Azure IP-adressintervall och service märken-offentliga moln](https://www.microsoft.com/en-us/download/details.aspx?id=56519) för en lista med IP-adresser att tillåta.</span><span class="sxs-lookup"><span data-stu-id="d6d46-179">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="d6d46-180">Installationen är klar men inte biljetter och kan inte dela</span><span class="sxs-lookup"><span data-stu-id="d6d46-180">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="d6d46-181">Om installations-och konfigurations stegen har genomförts men du inte ser ServiceNow-korten på Start sidan och inte kan dela till ServiceNow från Microsofts säkra Poäng kan du kontrol lera status för etablerings sidan på https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="d6d46-181">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="d6d46-182">Välj **Godkänn** och gå tillbaka till start sidan.</span><span class="sxs-lookup"><span data-stu-id="d6d46-182">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="d6d46-183">Korten ska visas.</span><span class="sxs-lookup"><span data-stu-id="d6d46-183">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="d6d46-184">Resurser</span><span class="sxs-lookup"><span data-stu-id="d6d46-184">Resources</span></span>

- [<span data-ttu-id="d6d46-185">Hantera ServiceNow biljetter i säkerhets Center</span><span class="sxs-lookup"><span data-stu-id="d6d46-185">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)
