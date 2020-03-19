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
ms.openlocfilehash: 904c1a019c55cabce6856a7caaca73d08d6db3f7
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836886"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="bc683-105">Hantera biljetter via ServiceNow</span><span class="sxs-lookup"><span data-stu-id="bc683-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="bc683-106">Microsoft 365 security center förbättras med möjlighet att skapa och spåra biljetter i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bc683-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="bc683-107">Säkerhetsadministratörer kan skicka en förbättringsåtgärd för [Microsoft Secure Score](microsoft-secure-score.md) direkt till ServiceNow och skapa en biljett.</span><span class="sxs-lookup"><span data-stu-id="bc683-107">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="bc683-108">Både incidenthantering och ändringshanteringsbiljetter kan skapas.</span><span class="sxs-lookup"><span data-stu-id="bc683-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bc683-109">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="bc683-109">Prerequisites</span></span>

<span data-ttu-id="bc683-110">Ha tillgång till Microsoft 365-säkerhetscentret och en ServiceNow-instans med:</span><span class="sxs-lookup"><span data-stu-id="bc683-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="bc683-111">Kingston eller högre version</span><span class="sxs-lookup"><span data-stu-id="bc683-111">Kingston or higher version</span></span>
* <span data-ttu-id="bc683-112">Har administratör HI-autentiseringsuppgifter</span><span class="sxs-lookup"><span data-stu-id="bc683-112">Have admin HI credentials</span></span>
* <span data-ttu-id="bc683-113">Ha administratörsbehörighet för din målleverantörsinstans</span><span class="sxs-lookup"><span data-stu-id="bc683-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="bc683-114">ServiceNow rekommenderar att användarna behåller standardinställningarna i din ServiceNow-instans.</span><span class="sxs-lookup"><span data-stu-id="bc683-114">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="bc683-115">Om du har anpassningar kan det orsaka fel när du slutför installationschecklistan och integreringen med säkerhetscentret Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bc683-115">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="bc683-116">Utbyte av uppgifter</span><span class="sxs-lookup"><span data-stu-id="bc683-116">Data exchange</span></span>

<span data-ttu-id="bc683-117">När du ansluter Microsoft 365-säkerhetscentret till ServiceNow tar Microsoft emot följande ytterligare data:</span><span class="sxs-lookup"><span data-stu-id="bc683-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="bc683-118">Instansnamn för ServiceNow</span><span class="sxs-lookup"><span data-stu-id="bc683-118">ServiceNow instance name</span></span>
* <span data-ttu-id="bc683-119">ServiceNow-klient-ID</span><span class="sxs-lookup"><span data-stu-id="bc683-119">ServiceNow client ID</span></span>
* <span data-ttu-id="bc683-120">ServiceNow-klienthemlighet</span><span class="sxs-lookup"><span data-stu-id="bc683-120">ServiceNow client secret</span></span>
* <span data-ttu-id="bc683-121">ServiceNow-åtkomst & uppdateringstoken</span><span class="sxs-lookup"><span data-stu-id="bc683-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="bc683-122">När du skapar en ServiceNow-biljett från Microsoft 365-säkerhetscentret skickas följande data till ServiceNow:</span><span class="sxs-lookup"><span data-stu-id="bc683-122">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="bc683-123">Användar-ID som initierar skapandet av biljetten</span><span class="sxs-lookup"><span data-stu-id="bc683-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="bc683-124">Uppgiftsnamn</span><span class="sxs-lookup"><span data-stu-id="bc683-124">Task name</span></span>
* <span data-ttu-id="bc683-125">Beskrivning av uppgift</span><span class="sxs-lookup"><span data-stu-id="bc683-125">Task description</span></span>
* <span data-ttu-id="bc683-126">Prioritet</span><span class="sxs-lookup"><span data-stu-id="bc683-126">Priority</span></span>
* <span data-ttu-id="bc683-127">Förfallodatum</span><span class="sxs-lookup"><span data-stu-id="bc683-127">Due date</span></span>
* <span data-ttu-id="bc683-128">Rekommendationskälla (Användarrekommendation eller Microsoft-rekommendation)</span><span class="sxs-lookup"><span data-stu-id="bc683-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="bc683-129">Kategorin Rekommendation (enheter, data, appar, identitet, infrastruktur)</span><span class="sxs-lookup"><span data-stu-id="bc683-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="bc683-130">Ansluta Microsoft 365-säkerhetscenter till ServiceNow</span><span class="sxs-lookup"><span data-stu-id="bc683-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="bc683-131">Gå till startsidan för Microsoft 365-säkerhetscentret för att se ServiceNow-anslutningskortet.</span><span class="sxs-lookup"><span data-stu-id="bc683-131">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Använder du ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="bc683-133">Välj "Anslut till ServiceNow" för att gå till inställningssidan för ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bc683-133">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="bc683-134">Följ instruktionerna för att auktorisera Microsoft 365 Connector-appen.</span><span class="sxs-lookup"><span data-stu-id="bc683-134">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="bc683-135">Innan du godkänner anslutningen mellan Microsoft 365 security center och ServiceNow ska du se till att du använder den användarinloggning och lösenord för integrering som du skapade i installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="bc683-135">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="bc683-136">Använd inte dina personliga inloggningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="bc683-136">Do not use your personal credentials.</span></span>

<span data-ttu-id="bc683-137">När du har följt anvisningarna och auktoriserat anslutningen kan du visa anslutningsstatusen på både anslutningssidan för Microsoft 365-säkerhetscenter och i ServiceNow Microsoft 365 Ticketing Connector App-upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="bc683-137">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="bc683-138">Nu är du redo att börja skapa uppgifter!</span><span class="sxs-lookup"><span data-stu-id="bc683-138">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="bc683-139">Skapa en uppgift och dela den till ServiceNow</span><span class="sxs-lookup"><span data-stu-id="bc683-139">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="bc683-140">När integreringen har konfigurerats skapar du ServiceNow-uppgifter baserat på specifika microsoft secure score-förbättringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="bc683-140">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="bc683-141">Gå till alla förbättringsåtgärder i Secure Score i Microsoft 365 security center-portalen och välj ikonen "dela".</span><span class="sxs-lookup"><span data-stu-id="bc683-141">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="bc683-142">Ett av listrutan är ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bc683-142">One of the dropdown options is ServiceNow.</span></span>

![ServiceNow-delning i Secure Score](../../media/servicenow-share.png)

<span data-ttu-id="bc683-144">En aktivitet genereras där du kan ange prioritet och redigera namn, beskrivning eller förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="bc683-144">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="bc683-145">När alla obligatoriska fält har fyllts i skickar du uppgiften till ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bc683-145">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="bc683-146">Uppgiften visas i ServiceNow som en Microsoft 365-begäran om säkerhet och konfigurationsändring.</span><span class="sxs-lookup"><span data-stu-id="bc683-146">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="bc683-147">Spåra biljetter</span><span class="sxs-lookup"><span data-stu-id="bc683-147">Track tickets</span></span>

<span data-ttu-id="bc683-148">När ServiceNow-biljetter för ändringshantering och incidenthantering har skapats visas de på kort på startsidan för Microsoft 365-säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="bc683-148">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="bc683-149">Från dessa kort kan du skapa en biljett, visa alla biljetter eller hantera ServiceNow-konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="bc683-149">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow ändringshanteringsbiljetter](../../media/change-management-375.png)  ![ServiceNow incidenthanteringsbiljetter](../../media/incident-management-375.png)

<span data-ttu-id="bc683-152">Om du vill återetablera eller hantera din ServiceNow-integrering i Microsoft 365-säkerhetscentret väljer du **Hantera ServiceNow-konfiguration** på något av korten.</span><span class="sxs-lookup"><span data-stu-id="bc683-152">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="bc683-153">Därifrån tar du bort den aktuella ServiceNow-anslutningen och anpassar biljetttillståndsnamn.</span><span class="sxs-lookup"><span data-stu-id="bc683-153">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="bc683-154">Med ServiceNow-biljetter synliga i Microsoft 365-säkerhetscentret bor dina uppgifter på en plats där de kan spåras och hanteras tillsammans med dina andra säkerhetsinstrumentpanelobjekt.</span><span class="sxs-lookup"><span data-stu-id="bc683-154">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bc683-155">Felsökning</span><span class="sxs-lookup"><span data-stu-id="bc683-155">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="bc683-156">Ett felmeddelande visas i det första steget i installationschecklistan (OAuth creation)</span><span class="sxs-lookup"><span data-stu-id="bc683-156">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="bc683-157">**Felmeddelande:** Läs åtgärder mot "oauth_entity" från scopet "x_mioms_m365ticket" har avslagits på grund av tabellens åtkomstprincip för korsförfattning</span><span class="sxs-lookup"><span data-stu-id="bc683-157">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="bc683-158">Appen förutsätter att alla administratörer i TjänstenNow-instansen kan skapa och läsa OAuth-entiteter.</span><span class="sxs-lookup"><span data-stu-id="bc683-158">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="bc683-159">Det här felet kan bero på en anpassning på din instans av ServiceNow, vilket begränsar vem som kan skapa/läsa OAuth-entiteter.</span><span class="sxs-lookup"><span data-stu-id="bc683-159">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="bc683-160">**ServiceNow rekommenderar att användarna behåller standardfunktionerna.**</span><span class="sxs-lookup"><span data-stu-id="bc683-160">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="bc683-161">Ange tabellkonfigurationerna "programregister" till standard:</span><span class="sxs-lookup"><span data-stu-id="bc683-161">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="bc683-162">Etikett = Programregister</span><span class="sxs-lookup"><span data-stu-id="bc683-162">Label = Application Registeries</span></span>
* <span data-ttu-id="bc683-163">Namn = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="bc683-163">Name = oauth_entity</span></span>
* <span data-ttu-id="bc683-164">Tillgänglig från = Alla programomfattningar</span><span class="sxs-lookup"><span data-stu-id="bc683-164">Accessible from = All application scopes</span></span>
* <span data-ttu-id="bc683-165">Kan läsa = kryssrutan markerad</span><span class="sxs-lookup"><span data-stu-id="bc683-165">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="bc683-166">Validera oauth-entiteten som skapats för Microsoft 365 Security & Compliance-anslutningsappen</span><span class="sxs-lookup"><span data-stu-id="bc683-166">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="bc683-167">Gå till tabellen programregister (**Meny > System OAuth > Application Registry)** i ServiceNow och leta reda på den OAuth-entitet som skapats av dig, med det namn som du har tilldelat den.</span><span class="sxs-lookup"><span data-stu-id="bc683-167">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="bc683-168">Logga in som integrationsanvändare</span><span class="sxs-lookup"><span data-stu-id="bc683-168">Logging in as the integration user</span></span>

<span data-ttu-id="bc683-169">Innan du godkänner anslutningen mellan Microsoft 365 security center och ServiceNow ska du se till att du använder den användarinloggning och lösenord för integrering som du skapade i installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="bc683-169">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="bc683-170">Använd inte dina personliga inloggningsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="bc683-170">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="bc683-171">Gå till auktoriseringssidan i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bc683-171">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="bc683-172">Om du är inloggad med dina personliga autentiseringsuppgifter väljer du länken **Inte du** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="bc683-172">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="bc683-173">Logga in på ServiceNow som integrationsanvändare som du skapade tidigare från installationschecklistan.</span><span class="sxs-lookup"><span data-stu-id="bc683-173">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="bc683-174">Välj **Tillåt** på sidan ServiceNow som frågar om Security + Compliance Connector kan ansluta till ditt ServiceNow-konto.</span><span class="sxs-lookup"><span data-stu-id="bc683-174">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="bc683-175">Fortsätt med installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="bc683-175">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="bc683-176">Validerar integreringsanvändaren som skapats med installationschecklistan för Microsoft 365 Security & Compliance connector</span><span class="sxs-lookup"><span data-stu-id="bc683-176">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="bc683-177">Gå till Användartabell **(Meny > Användaradministration > Användare)** i ServiceNow och hitta integrationsanvändaren som skapats av dig, med det namn som du har tilldelat den.</span><span class="sxs-lookup"><span data-stu-id="bc683-177">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="bc683-178">Ditt företag har enkel inloggning aktiverad som hindrar dig från att ansluta till ServiceNow via Microsoft 365-säkerhetscentret</span><span class="sxs-lookup"><span data-stu-id="bc683-178">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="bc683-179">Om ditt företag har aktiverat enkel inloggning och du får ett felmeddelande eller inloggning misslyckas, följ en av de två lösningarna.</span><span class="sxs-lookup"><span data-stu-id="bc683-179">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="bc683-180">Logga in på ServiceNow som integrationsanvändare</span><span class="sxs-lookup"><span data-stu-id="bc683-180">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="bc683-181">Navigera tillbaka till auktoriseringssidan i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bc683-181">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="bc683-182">Välj länken **Inte du** i det övre högra hörnet.</span><span class="sxs-lookup"><span data-stu-id="bc683-182">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="bc683-183">Logga in på ServiceNow som integrationsanvändare som du skapade tidigare från installationschecklistan.</span><span class="sxs-lookup"><span data-stu-id="bc683-183">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="bc683-184">Välj **Tillåt** på sidan ServiceNow som frågar om Security + Compliance Connector kan ansluta till ditt ServiceNow-konto.</span><span class="sxs-lookup"><span data-stu-id="bc683-184">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="bc683-185">Fortsätt med installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="bc683-185">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="bc683-186">Skapa en användare av säkerhetsadministratörer</span><span class="sxs-lookup"><span data-stu-id="bc683-186">Create a security admin user</span></span>

1. <span data-ttu-id="bc683-187">Skapa en användare med behörighet för säkerhetsadministratörer i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bc683-187">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="bc683-188">Användaren måste ha samma namn och e-postadress som den integrationsanvändare som du skapade från installationschecklistan.</span><span class="sxs-lookup"><span data-stu-id="bc683-188">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="bc683-189">Du kan ta bort säkerhetsadministratörsrollen när inloggningen och anslutningen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="bc683-189">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="bc683-190">Logga in på Microsoft 365-säkerhetscentret som den här användaren och följ installationsstegen.</span><span class="sxs-lookup"><span data-stu-id="bc683-190">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="bc683-191">IP-filtrering</span><span class="sxs-lookup"><span data-stu-id="bc683-191">IP filtering</span></span>

<span data-ttu-id="bc683-192">Om du har aktiverat IP-filtrering kan du behöva uttryckligen tillåta IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="bc683-192">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="bc683-193">Se [IP-adressåtkomstkontroll](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) för information om hur du tillåter IP-intervall i ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="bc683-193">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="bc683-194">Se [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) för en lista över IP-adresser som ska tillåtas.</span><span class="sxs-lookup"><span data-stu-id="bc683-194">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="bc683-195">Installationen är klar men ser inte biljetter och kan inte dela</span><span class="sxs-lookup"><span data-stu-id="bc683-195">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="bc683-196">Om installations- och installationsstegen har slutförts, men du inte ser ServiceNow-korten på startsidan och inte kan dela till https://security.microsoft.com/ticketProvisioningServiceNow från Microsoft Secure Score, kontrollerar du statusen för etableringssidan på .</span><span class="sxs-lookup"><span data-stu-id="bc683-196">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="bc683-197">Välj **Auktorisera** och gå tillbaka till startsidan.</span><span class="sxs-lookup"><span data-stu-id="bc683-197">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="bc683-198">Korten ska visas.</span><span class="sxs-lookup"><span data-stu-id="bc683-198">The cards should appear.</span></span>

