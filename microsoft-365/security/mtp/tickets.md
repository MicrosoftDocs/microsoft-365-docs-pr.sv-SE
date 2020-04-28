---
title: Skapa och spåra biljetter via ServiceNow
description: Microsoft 365 security center förbättras med möjlighet att skapa och spåra biljetter i ServiceNow. Säkerhetsadministratörer kan skicka en rekommendation om säker poäng direkt till ServiceNow och skapa en biljett.
keywords: säkerhet, Microsoft 365, M365, säker poäng, säkerhetscenter, ServiceNow, biljetter, uppgifter
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
ms.openlocfilehash: eb6af6b11d2d932f3bd2165aa3f597c14feb5ae8
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901028"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="86da6-105">Hantera biljetter via ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86da6-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="86da6-106">ServiceNow är en populär molnbaserad datorplattform som hjälper företag att hantera digitala arbetsflöden för företagsverksamhet.</span><span class="sxs-lookup"><span data-stu-id="86da6-106">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="86da6-107">Deras Now-plattform har IT-arbetsflöden, medarbetararbetsflöden och kundarbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="86da6-107">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> <span data-ttu-id="86da6-108">Microsoft samarbetar med ServiceNow för att göra det enklare för IT-administratörer att hantera sina biljetter och uppgifter på båda plattformarna.</span><span class="sxs-lookup"><span data-stu-id="86da6-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> [<span data-ttu-id="86da6-109">Läs mer om ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86da6-109">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="86da6-110">Microsoft 365 security center utökas nu med möjlighet att skapa och spåra biljetter i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86da6-110">Microsoft 365 security center is now enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="86da6-111">Säkerhetsadministratörer kan skicka en förbättringsåtgärd för [Microsoft Secure Score](microsoft-secure-score.md) direkt till ServiceNow och skapa en biljett.</span><span class="sxs-lookup"><span data-stu-id="86da6-111">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="86da6-112">Både incidenthantering och ändringshanteringsbiljetter kan skapas.</span><span class="sxs-lookup"><span data-stu-id="86da6-112">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="86da6-113">De kan sedan spåras på startsidan för Microsofts säkerhetscenter och ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86da6-113">They can then be tracked in the Microsoft security center home page, and ServiceNow.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86da6-114">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="86da6-114">Prerequisites</span></span>

<span data-ttu-id="86da6-115">Ha tillgång till Microsoft 365-säkerhetscentret och en ServiceNow-instans med:</span><span class="sxs-lookup"><span data-stu-id="86da6-115">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="86da6-116">Kingston eller högre version</span><span class="sxs-lookup"><span data-stu-id="86da6-116">Kingston or higher version</span></span>
* <span data-ttu-id="86da6-117">Har administratör HI-autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="86da6-117">Have admin HI credentials</span></span>
* <span data-ttu-id="86da6-118">Ha administratörsbehörighet för din målleverantörsinstans</span><span class="sxs-lookup"><span data-stu-id="86da6-118">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="86da6-119">ServiceNow rekommenderar att användarna behåller standardinställningarna i din ServiceNow-instans.</span><span class="sxs-lookup"><span data-stu-id="86da6-119">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="86da6-120">Om du har anpassningar kan det orsaka fel när du slutför installationschecklistan och integreringen med säkerhetscentret Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86da6-120">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="86da6-121">Utbyte av uppgifter</span><span class="sxs-lookup"><span data-stu-id="86da6-121">Data exchange</span></span>

<span data-ttu-id="86da6-122">När du ansluter Microsoft 365-säkerhetscentret till ServiceNow tar Microsoft emot följande ytterligare data:</span><span class="sxs-lookup"><span data-stu-id="86da6-122">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="86da6-123">Instansnamn för ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86da6-123">ServiceNow instance name</span></span>
* <span data-ttu-id="86da6-124">ServiceNow-klient-ID</span><span class="sxs-lookup"><span data-stu-id="86da6-124">ServiceNow client ID</span></span>
* <span data-ttu-id="86da6-125">ServiceNow-klienthemlighet</span><span class="sxs-lookup"><span data-stu-id="86da6-125">ServiceNow client secret</span></span>
* <span data-ttu-id="86da6-126">ServiceNow-åtkomst & uppdateringstoken</span><span class="sxs-lookup"><span data-stu-id="86da6-126">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="86da6-127">När du skapar en ServiceNow-biljett från Microsoft 365-säkerhetscentret skickas följande data till ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="86da6-127">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="86da6-128">Användar-ID som initierar skapandet av biljetten</span><span class="sxs-lookup"><span data-stu-id="86da6-128">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="86da6-129">Uppgiftsnamn</span><span class="sxs-lookup"><span data-stu-id="86da6-129">Task name</span></span>
* <span data-ttu-id="86da6-130">Beskrivning av uppgift</span><span class="sxs-lookup"><span data-stu-id="86da6-130">Task description</span></span>
* <span data-ttu-id="86da6-131">Priority</span><span class="sxs-lookup"><span data-stu-id="86da6-131">Priority</span></span>
* <span data-ttu-id="86da6-132">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="86da6-132">Due date</span></span>
* <span data-ttu-id="86da6-133">Rekommendationskälla (Användarrekommendation eller Microsoft-rekommendation)</span><span class="sxs-lookup"><span data-stu-id="86da6-133">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="86da6-134">Kategorin Rekommendation (enheter, data, appar, identitet, infrastruktur)</span><span class="sxs-lookup"><span data-stu-id="86da6-134">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="86da6-135">Ansluta Microsoft 365-säkerhetscenter till ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86da6-135">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="86da6-136">Gå till startsidan för Microsoft 365-säkerhetscentret för att se ServiceNow-anslutningskortet.</span><span class="sxs-lookup"><span data-stu-id="86da6-136">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Använder du ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="86da6-138">Välj "Anslut till ServiceNow" för att gå till inställningssidan för ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86da6-138">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="86da6-139">Följ instruktionerna för att auktorisera Microsoft 365 Connector-appen.</span><span class="sxs-lookup"><span data-stu-id="86da6-139">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="86da6-140">Innan du godkänner anslutningen mellan Microsoft 365 security center och ServiceNow ska du se till att du använder den användarinloggning och lösenord för integrering som du skapade i installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="86da6-140">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="86da6-141">Använd inte dina personliga inloggningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="86da6-141">Do not use your personal credentials.</span></span>

<span data-ttu-id="86da6-142">När du har följt anvisningarna och auktoriserat anslutningen kan du visa anslutningsstatusen på både anslutningssidan för Microsoft 365-säkerhetscenter och i ServiceNow Microsoft 365 Ticketing Connector App-upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="86da6-142">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="86da6-143">Nu är du redo att börja skapa uppgifter!</span><span class="sxs-lookup"><span data-stu-id="86da6-143">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="86da6-144">Skapa en uppgift och dela den till ServiceNow</span><span class="sxs-lookup"><span data-stu-id="86da6-144">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="86da6-145">När integreringen har konfigurerats skapar du ServiceNow-uppgifter baserat på specifika microsoft secure score-förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="86da6-145">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="86da6-146">Gå till alla förbättringsåtgärder i Secure Score i Microsoft 365 security center-portalen och välj ikonen "dela".</span><span class="sxs-lookup"><span data-stu-id="86da6-146">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="86da6-147">Ett av listrutan är ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86da6-147">One of the dropdown options is ServiceNow.</span></span>

![ServiceNow-delning i Secure Score](../../media/servicenow-share.png)

<span data-ttu-id="86da6-149">En aktivitet genereras där du kan ange prioritet och redigera namn, beskrivning eller förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="86da6-149">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="86da6-150">När alla obligatoriska fält har fyllts i skickar du uppgiften till ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86da6-150">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="86da6-151">Uppgiften visas i ServiceNow som en Microsoft 365-begäran om säkerhet och konfigurationsändring.</span><span class="sxs-lookup"><span data-stu-id="86da6-151">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="86da6-152">Spåra biljetter</span><span class="sxs-lookup"><span data-stu-id="86da6-152">Track tickets</span></span>

<span data-ttu-id="86da6-153">När ServiceNow-biljetter för ändringshantering och incidenthantering har skapats visas de på kort på startsidan för Microsoft 365-säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="86da6-153">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="86da6-154">Från dessa kort kan du skapa en biljett, visa alla biljetter eller hantera ServiceNow-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="86da6-154">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow ändringshanteringsbiljetter](../../media/change-management-375.png)  ![ServiceNow incidenthanteringsbiljetter](../../media/incident-management-375.png)

<span data-ttu-id="86da6-157">Om du vill återetablera eller hantera din ServiceNow-integrering i Microsoft 365-säkerhetscentret väljer du **Hantera ServiceNow-konfiguration** på något av korten.</span><span class="sxs-lookup"><span data-stu-id="86da6-157">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="86da6-158">Därifrån tar du bort den aktuella ServiceNow-anslutningen och anpassar biljetttillståndsnamn.</span><span class="sxs-lookup"><span data-stu-id="86da6-158">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="86da6-159">Med ServiceNow-biljetter synliga i Microsoft 365-säkerhetscentret bor dina uppgifter på en plats där de kan spåras och hanteras tillsammans med dina andra säkerhetsinstrumentpanelobjekt.</span><span class="sxs-lookup"><span data-stu-id="86da6-159">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="86da6-160">Felsökning</span><span class="sxs-lookup"><span data-stu-id="86da6-160">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="86da6-161">Ett felmeddelande visas i det första steget i installationschecklistan (OAuth creation)</span><span class="sxs-lookup"><span data-stu-id="86da6-161">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="86da6-162">**Felmeddelande:** Läs åtgärder mot "oauth_entity" från scopet "x_mioms_m365ticket" har avslagits på grund av tabellens åtkomstprincip för korsförfattning</span><span class="sxs-lookup"><span data-stu-id="86da6-162">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="86da6-163">Appen förutsätter att alla administratörer i TjänstenNow-instansen kan skapa och läsa OAuth-entiteter.</span><span class="sxs-lookup"><span data-stu-id="86da6-163">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="86da6-164">Det här felet kan bero på en anpassning på din instans av ServiceNow, vilket begränsar vem som kan skapa/läsa OAuth-entiteter.</span><span class="sxs-lookup"><span data-stu-id="86da6-164">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="86da6-165">**ServiceNow rekommenderar att användarna behåller standardfunktionerna.**</span><span class="sxs-lookup"><span data-stu-id="86da6-165">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="86da6-166">Ange tabellkonfigurationerna "programregister" till standard:</span><span class="sxs-lookup"><span data-stu-id="86da6-166">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="86da6-167">Etikett = Programregister</span><span class="sxs-lookup"><span data-stu-id="86da6-167">Label = Application Registeries</span></span>
* <span data-ttu-id="86da6-168">Namn = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="86da6-168">Name = oauth_entity</span></span>
* <span data-ttu-id="86da6-169">Tillgänglig från = Alla programomfattningar</span><span class="sxs-lookup"><span data-stu-id="86da6-169">Accessible from = All application scopes</span></span>
* <span data-ttu-id="86da6-170">Kan läsa = kryssrutan markerad</span><span class="sxs-lookup"><span data-stu-id="86da6-170">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="86da6-171">Validera oauth-entiteten som skapats för Microsoft 365 Security & Compliance-anslutningsappen</span><span class="sxs-lookup"><span data-stu-id="86da6-171">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="86da6-172">Gå till tabellen programregister (**Meny > System OAuth > Application Registry)** i ServiceNow och leta reda på den OAuth-entitet som skapats av dig, med det namn som du har tilldelat den.</span><span class="sxs-lookup"><span data-stu-id="86da6-172">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="86da6-173">Logga in som integrationsanvändare</span><span class="sxs-lookup"><span data-stu-id="86da6-173">Logging in as the integration user</span></span>

<span data-ttu-id="86da6-174">Innan du godkänner anslutningen mellan Microsoft 365 security center och ServiceNow ska du se till att du använder den användarinloggning och lösenord för integrering som du skapade i installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="86da6-174">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="86da6-175">Använd inte dina personliga inloggningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="86da6-175">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="86da6-176">Gå till auktoriseringssidan i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86da6-176">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="86da6-177">Om du är inloggad med dina personliga autentiseringsuppgifter väljer du länken **Inte du** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="86da6-177">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="86da6-178">Logga in på ServiceNow som integrationsanvändare som du skapade tidigare från installationschecklistan.</span><span class="sxs-lookup"><span data-stu-id="86da6-178">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="86da6-179">Välj **Tillåt** på sidan ServiceNow som frågar om Security + Compliance Connector kan ansluta till ditt ServiceNow-konto.</span><span class="sxs-lookup"><span data-stu-id="86da6-179">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="86da6-180">Fortsätt med installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="86da6-180">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="86da6-181">Validerar integreringsanvändaren som skapats med installationschecklistan för Microsoft 365 Security & Compliance connector</span><span class="sxs-lookup"><span data-stu-id="86da6-181">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="86da6-182">Gå till Användartabell **(Meny > Användaradministration > Användare)** i ServiceNow och hitta integrationsanvändaren som skapats av dig, med det namn som du har tilldelat den.</span><span class="sxs-lookup"><span data-stu-id="86da6-182">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="86da6-183">Ditt företag har enkel inloggning aktiverad som hindrar dig från att ansluta till ServiceNow via Microsoft 365-säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="86da6-183">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="86da6-184">Om ditt företag har aktiverat enkel inloggning och du får ett felmeddelande eller inloggning misslyckas, följ en av de två lösningarna.</span><span class="sxs-lookup"><span data-stu-id="86da6-184">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="86da6-185">Logga in på ServiceNow som integrationsanvändare</span><span class="sxs-lookup"><span data-stu-id="86da6-185">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="86da6-186">Navigera tillbaka till auktoriseringssidan i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86da6-186">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="86da6-187">Välj länken **Inte du** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="86da6-187">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="86da6-188">Logga in på ServiceNow som integrationsanvändare som du skapade tidigare från installationschecklistan.</span><span class="sxs-lookup"><span data-stu-id="86da6-188">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="86da6-189">Välj **Tillåt** på sidan ServiceNow som frågar om Security + Compliance Connector kan ansluta till ditt ServiceNow-konto.</span><span class="sxs-lookup"><span data-stu-id="86da6-189">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="86da6-190">Fortsätt med installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="86da6-190">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="86da6-191">Skapa en användare av säkerhetsadministratörer</span><span class="sxs-lookup"><span data-stu-id="86da6-191">Create a security admin user</span></span>

1. <span data-ttu-id="86da6-192">Skapa en användare med behörighet för säkerhetsadministratörer i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="86da6-192">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="86da6-193">Användaren måste ha samma namn och e-postadress som den integrationsanvändare som du skapade från installationschecklistan.</span><span class="sxs-lookup"><span data-stu-id="86da6-193">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="86da6-194">Du kan ta bort säkerhetsadministratörsrollen när inloggningen och anslutningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="86da6-194">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="86da6-195">Logga in på Microsoft 365-säkerhetscentret som den här användaren och följ installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="86da6-195">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="86da6-196">IP-filtrering</span><span class="sxs-lookup"><span data-stu-id="86da6-196">IP filtering</span></span>

<span data-ttu-id="86da6-197">Om du har aktiverat IP-filtrering kan du behöva uttryckligen tillåta IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="86da6-197">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="86da6-198">Se [IP-adressåtkomstkontroll](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) för information om hur du tillåter IP-intervall i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="86da6-198">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="86da6-199">Se [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) för en lista över IP-adresser som ska tillåtas.</span><span class="sxs-lookup"><span data-stu-id="86da6-199">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="86da6-200">Installationen är klar men ser inte biljetter och kan inte dela</span><span class="sxs-lookup"><span data-stu-id="86da6-200">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="86da6-201">Om installations- och installationsstegen har slutförts, men du inte ser ServiceNow-korten på startsidan och inte kan dela till https://security.microsoft.com/ticketProvisioningServiceNow från Microsoft Secure Score, kontrollerar du statusen för etableringssidan på .</span><span class="sxs-lookup"><span data-stu-id="86da6-201">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="86da6-202">Välj **Auktorisera** och gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="86da6-202">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="86da6-203">Korten ska visas.</span><span class="sxs-lookup"><span data-stu-id="86da6-203">The cards should appear.</span></span>

