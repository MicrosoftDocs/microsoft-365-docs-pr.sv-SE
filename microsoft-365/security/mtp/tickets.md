---
title: Integrera ServiceNow-biljetter i Microsoft 365-säkerhetscentret och efterlevnadscentret
description: Lär dig hur du skapar och spårar biljetter i ServiceNow från Säkerhetscentret för Microsoft 365 och efterlevnadscenter.
keywords: säkerhet, Microsoft 365, M365, efterlevnad, efterlevnadscenter, säkerhetscenter, ServiceNow, biljetter, uppgifter, SNOW, anslutning
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
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086673"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="2520c-104">Integrera ServiceNow-biljetter i Microsoft 365-säkerhetscentret och efterlevnadscentret</span><span class="sxs-lookup"><span data-stu-id="2520c-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2520c-105">ServiceNow är en populär molnbaserad datorplattform som hjälper företag att hantera digitala arbetsflöden för företagsverksamhet.</span><span class="sxs-lookup"><span data-stu-id="2520c-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="2520c-106">Deras Now-plattform har IT-arbetsflöden, medarbetararbetsflöden och kundarbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="2520c-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="2520c-107">Läs mer om ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2520c-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="2520c-108">Microsoft samarbetar med ServiceNow för att göra det enklare för IT-administratörer att hantera sina biljetter och uppgifter på båda plattformarna.</span><span class="sxs-lookup"><span data-stu-id="2520c-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="2520c-109">[Microsoft 365 security center](overview-security-center.md) och [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) förbättras med möjligheten att skapa och spåra biljetter i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2520c-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="2520c-110">**Hantera ServiceNow-biljetter i säkerhetscentret**</span><span class="sxs-lookup"><span data-stu-id="2520c-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="2520c-111">**Hantera ServiceNow-biljetter i efterlevnadscentret** (kommer snart)</span><span class="sxs-lookup"><span data-stu-id="2520c-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2520c-112">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="2520c-112">Prerequisites</span></span>

<span data-ttu-id="2520c-113">Ha tillgång till Microsoft 365-säkerhetscentret eller efterlevnadscentret och en ServiceNow-instans med:</span><span class="sxs-lookup"><span data-stu-id="2520c-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="2520c-114">Kingston eller högre version</span><span class="sxs-lookup"><span data-stu-id="2520c-114">Kingston or higher version</span></span>
* <span data-ttu-id="2520c-115">Har administratör HI-autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="2520c-115">Have admin HI credentials</span></span>
* <span data-ttu-id="2520c-116">Ha administratörsbehörighet för din målleverantörsinstans</span><span class="sxs-lookup"><span data-stu-id="2520c-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="2520c-117">ServiceNow rekommenderar att användarna behåller standardinställningarna i din ServiceNow-instans.</span><span class="sxs-lookup"><span data-stu-id="2520c-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="2520c-118">Om du har anpassningar kan det orsaka fel när du slutför installationschecklistan och integreringen med säkerhetscentret Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2520c-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="2520c-119">Utbyte av uppgifter</span><span class="sxs-lookup"><span data-stu-id="2520c-119">Data exchange</span></span>

<span data-ttu-id="2520c-120">När du ansluter Microsoft 365-säkerhetscentret eller efterlevnadscentret till ServiceNow tar Microsoft emot följande ytterligare data:</span><span class="sxs-lookup"><span data-stu-id="2520c-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="2520c-121">Instansnamn för ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2520c-121">ServiceNow instance name</span></span>
* <span data-ttu-id="2520c-122">ServiceNow-klient-ID</span><span class="sxs-lookup"><span data-stu-id="2520c-122">ServiceNow client ID</span></span>
* <span data-ttu-id="2520c-123">ServiceNow-klienthemlighet</span><span class="sxs-lookup"><span data-stu-id="2520c-123">ServiceNow client secret</span></span>
* <span data-ttu-id="2520c-124">ServiceNow-åtkomst & uppdateringstoken</span><span class="sxs-lookup"><span data-stu-id="2520c-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="2520c-125">När du skapar en ServiceNow-biljett från Microsoft 365-säkerhetscentret eller efterlevnadscentret skickas följande data till ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="2520c-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="2520c-126">Användar-ID som initierar skapandet av biljetten</span><span class="sxs-lookup"><span data-stu-id="2520c-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="2520c-127">Uppgiftsnamn</span><span class="sxs-lookup"><span data-stu-id="2520c-127">Task name</span></span>
* <span data-ttu-id="2520c-128">Beskrivning av uppgift</span><span class="sxs-lookup"><span data-stu-id="2520c-128">Task description</span></span>
* <span data-ttu-id="2520c-129">Prioritet</span><span class="sxs-lookup"><span data-stu-id="2520c-129">Priority</span></span>
* <span data-ttu-id="2520c-130">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="2520c-130">Due date</span></span>
* <span data-ttu-id="2520c-131">Rekommendationskälla (Användarrekommendation eller Microsoft-rekommendation)</span><span class="sxs-lookup"><span data-stu-id="2520c-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="2520c-132">Kategorin Rekommendation (enheter, data, appar, identitet, infrastruktur)</span><span class="sxs-lookup"><span data-stu-id="2520c-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="2520c-133">Anslut till ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2520c-133">Connect to ServiceNow</span></span>

<span data-ttu-id="2520c-134">Gå till [Skapa och spåra ServiceNow-biljetter i Microsoft 365-säkerhetscentret](tickets-security-center.md) för att lära dig hur du ansluter till ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2520c-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="2520c-135">Anslutningen från Microsoft 365 compliance center kommer snart.</span><span class="sxs-lookup"><span data-stu-id="2520c-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2520c-136">Felsökning</span><span class="sxs-lookup"><span data-stu-id="2520c-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="2520c-137">Ett felmeddelande visas i det första steget i installationschecklistan (OAuth creation)</span><span class="sxs-lookup"><span data-stu-id="2520c-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="2520c-138">**Felmeddelande:** Läs åtgärder mot "oauth_entity" från scopet "x_mioms_m365ticket" har avslagits på grund av tabellens åtkomstprincip för korsförfattning</span><span class="sxs-lookup"><span data-stu-id="2520c-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="2520c-139">Appen förutsätter att alla administratörer i ServiceNow-instansen kan skapa och läsa OAuth-entiteter.</span><span class="sxs-lookup"><span data-stu-id="2520c-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="2520c-140">Det här felet kan orsakas på grund av en anpassning på din instans av ServiceNow, vilket begränsar vem som kan skapa/läsa OAuth-entiteter.</span><span class="sxs-lookup"><span data-stu-id="2520c-140">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="2520c-141">**ServiceNow rekommenderar att användarna behåller standardfunktionerna.**</span><span class="sxs-lookup"><span data-stu-id="2520c-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="2520c-142">Ange tabellkonfigurationerna "programregister" till standard:</span><span class="sxs-lookup"><span data-stu-id="2520c-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="2520c-143">Etikett = Programregister</span><span class="sxs-lookup"><span data-stu-id="2520c-143">Label = Application Registeries</span></span>
* <span data-ttu-id="2520c-144">Namn = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="2520c-144">Name = oauth_entity</span></span>
* <span data-ttu-id="2520c-145">Tillgänglig från = Alla programomfattningar</span><span class="sxs-lookup"><span data-stu-id="2520c-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="2520c-146">Kan läsa = kryssrutan markerad</span><span class="sxs-lookup"><span data-stu-id="2520c-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="2520c-147">Validera oauth-entiteten som skapats för Microsoft 365 Security & Compliance-anslutningsappen</span><span class="sxs-lookup"><span data-stu-id="2520c-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="2520c-148">Gå till tabellen programregister (**Meny > System OAuth > Application Registry)** i ServiceNow och leta reda på den OAuth-entitet som skapats av dig, med det namn som du tilldelade den.</span><span class="sxs-lookup"><span data-stu-id="2520c-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="2520c-149">Logga in som integrationsanvändare</span><span class="sxs-lookup"><span data-stu-id="2520c-149">Logging in as the integration user</span></span>

<span data-ttu-id="2520c-150">Innan du godkänner anslutningen mellan Microsoft 365 security center och ServiceNow ska du se till att du använder den användarinloggning och lösenord för integrering som du skapade i installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="2520c-150">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="2520c-151">Använd inte dina personliga inloggningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="2520c-151">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="2520c-152">Gå till auktoriseringssidan i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2520c-152">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="2520c-153">Om du är inloggad med dina personliga inloggningsuppgifter väljer du länken **Inte du** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="2520c-153">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="2520c-154">Logga in på ServiceNow som integrationsanvändare som du skapade tidigare från installationschecklistan.</span><span class="sxs-lookup"><span data-stu-id="2520c-154">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="2520c-155">Välj **Tillåt** på sidan ServiceNow som frågar om Security + Compliance Connector kan ansluta till ditt ServiceNow-konto.</span><span class="sxs-lookup"><span data-stu-id="2520c-155">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="2520c-156">Fortsätt med installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="2520c-156">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="2520c-157">Validera integreringsanvändaren som skapats med installationschecklistan för Microsoft 365 Security & Compliance connector</span><span class="sxs-lookup"><span data-stu-id="2520c-157">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="2520c-158">Gå till Användartabell **(Meny > Användaradministration > Användare)** i ServiceNow och hitta den integrationsanvändare som skapats av dig, med det namn som du har tilldelat den.</span><span class="sxs-lookup"><span data-stu-id="2520c-158">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="2520c-159">Ditt företag har enkel inloggning aktiverad som hindrar dig från att ansluta till ServiceNow via Microsoft 365-säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="2520c-159">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="2520c-160">Om ditt företag har aktiverat enkel inloggning och du får ett felmeddelande eller inloggning misslyckas, följ en av de två lösningarna.</span><span class="sxs-lookup"><span data-stu-id="2520c-160">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="2520c-161">Logga in på ServiceNow som integrationsanvändare</span><span class="sxs-lookup"><span data-stu-id="2520c-161">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="2520c-162">Navigera tillbaka till auktoriseringssidan i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2520c-162">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="2520c-163">Välj länken **Inte du** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="2520c-163">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="2520c-164">Logga in på ServiceNow som integrationsanvändare som du skapade tidigare från installationschecklistan.</span><span class="sxs-lookup"><span data-stu-id="2520c-164">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="2520c-165">Välj **Tillåt** på sidan ServiceNow som frågar om Security + Compliance Connector kan ansluta till ditt ServiceNow-konto.</span><span class="sxs-lookup"><span data-stu-id="2520c-165">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="2520c-166">Fortsätt med installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="2520c-166">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="2520c-167">Skapa en användare av säkerhetsadministratörer</span><span class="sxs-lookup"><span data-stu-id="2520c-167">Create a security admin user</span></span>

1. <span data-ttu-id="2520c-168">Skapa en användare med behörighet för säkerhetsadministratörer i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2520c-168">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="2520c-169">Användaren måste ha samma namn och e-postadress som den integrationsanvändare som du skapade från installationschecklistan.</span><span class="sxs-lookup"><span data-stu-id="2520c-169">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="2520c-170">Du kan ta bort rollen säkerhetsadministratör när inloggningen och anslutningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="2520c-170">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="2520c-171">Logga in på Microsoft 365-säkerhetscentret som den här användaren och följ installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="2520c-171">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="2520c-172">IP-filtrering</span><span class="sxs-lookup"><span data-stu-id="2520c-172">IP filtering</span></span>

<span data-ttu-id="2520c-173">Om du har aktiverat IP-filtrering kan du behöva uttryckligen tillåta IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="2520c-173">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="2520c-174">Se [IP-adressåtkomstkontroll](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) för information om hur du tillåter IP-intervall i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2520c-174">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="2520c-175">Se [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) för en lista över IP-adresser som ska tillåtas.</span><span class="sxs-lookup"><span data-stu-id="2520c-175">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="2520c-176">Installationen är klar men ser inte biljetter och kan inte dela</span><span class="sxs-lookup"><span data-stu-id="2520c-176">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="2520c-177">Om installations- och installationsstegen har slutförts, men du inte ser ServiceNow-korten på startsidan och inte kan dela till ServiceNow från Microsoft Secure Score, kontrollerar du statusen för etableringssidan på https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="2520c-177">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="2520c-178">Välj **Auktorisera** och gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="2520c-178">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="2520c-179">Korten ska visas.</span><span class="sxs-lookup"><span data-stu-id="2520c-179">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="2520c-180">Resurser</span><span class="sxs-lookup"><span data-stu-id="2520c-180">Resources</span></span>

- [<span data-ttu-id="2520c-181">Hantera ServiceNow-biljetter i säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="2520c-181">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)