---
title: Integrera Microsoft Teams klasser med Blackboard Learn Ultra
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrera Microsoft Teams klasser med Blackboard Learn Ultra
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314501"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="41366-103">Använda Microsoft Teams-klasser med Blackboard Learn Ultra</span><span class="sxs-lookup"><span data-stu-id="41366-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="41366-104">Samarbete är kärnan i alla moderna organisationer.</span><span class="sxs-lookup"><span data-stu-id="41366-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="41366-105">Genom att främja samarbete är det ett definierande kännetecken för varje framgångsrik institution.</span><span class="sxs-lookup"><span data-stu-id="41366-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="41366-106">Du kan förbättra alla funktioner i Blackboard Learn Ultra genom att koppla ihop dem med Microsoft Teams klasser.</span><span class="sxs-lookup"><span data-stu-id="41366-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="41366-107">Kurserna kan innehålla realtidskonversationer, videomöten eller asynkrona interaktioner.</span><span class="sxs-lookup"><span data-stu-id="41366-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="41366-108">Du kan lägga till fildelning och samskapning för eleverna på ett och samma ställe.</span><span class="sxs-lookup"><span data-stu-id="41366-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="41366-109">Microsoft Teams klassen med Lär dig Ultra omdefiniera hur dynamics det finns att lära ut och vad effektivt lärande innebär.</span><span class="sxs-lookup"><span data-stu-id="41366-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41366-110">Kontrollera att du har ställt in fältet Institution Email i SIS (Student Information System) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span><span class="sxs-lookup"><span data-stu-id="41366-110">Ensure that you have successfully set up the Institution Email field in your Student Information System (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span></span>
>
><span data-ttu-id="41366-111">Integreringen Microsoft Teams klasser använder institutionens e-postfält i SIS för att mappa till rätt UPN (User Principal Name) för Microsoft Azure Active Directory (Microsoft Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="41366-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) User Principal Name (UPN).</span></span> <span data-ttu-id="41366-112">Om inga institutions-e-postmeddelanden har etablerats används den befintliga e-postadressen som standard.</span><span class="sxs-lookup"><span data-stu-id="41366-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="41366-113">Vi rekommenderar att det här fältet ställs in för alla användare för att säkerställa att deras data synkroniseras korrekt och att det inte finns någon konflikt mellan e-postdata mellan Microsoft AAD och Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="41366-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between Microsoft AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="41366-114">Om du inte har angett det här fältet på rätt sätt i SIS-mappningen kommer integreringen fortsätta att fungera, men användare kanske inte visas i Teams-klasserna som skapats och fel kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="41366-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="41366-115">Stöd för institutionsdatamappning – SIS-fältet institution-e-post</span><span class="sxs-lookup"><span data-stu-id="41366-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="41366-116">Som en del av utvecklingen med molnleverantörsintegrationer har  Blackboard Learn Ultra skapat ett nytt institution-e-postfält, både i integreringen av Student Information System Framework och offentliga REST API:er, så att institutioner kan hantera datasynkroniseringsprocessen effektivt mellan Blackboard Learn Ultra och Microsoft AAD.</span><span class="sxs-lookup"><span data-stu-id="41366-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and Microsoft AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="41366-117">Vad innebär institutionens e-post och vad har det stöd för?</span><span class="sxs-lookup"><span data-stu-id="41366-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="41366-118">Fältet **Institution Email** tillåter anpassade fältmappningar mellan en klients externt stödda datakällor och Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="41366-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="41366-119">Om datakällor är molntjänster, till exempel Microsoft, är UPN (User Principle Name) en primär unik identifierare för varje användare som består av ett UPN-prefix (användarens kontonamn) och ett UPN-suffix (ett DNS-domännamn) samman med en @-symbol.</span><span class="sxs-lookup"><span data-stu-id="41366-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="41366-120">Då skapas en unik e-postadress för varje enskild användare i Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="41366-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="41366-121">För att säkerställa att data är korrekta och registreringar eller medlemskap mellan Blackboard Learn Ultra och Microsoft Teams-klasser kan uppnås korrekt måste en användares e-postadress matcha mellan båda systemen.</span><span class="sxs-lookup"><span data-stu-id="41366-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="41366-122">I Blackboard Learn Ultra kan användare ändra eller åsidosätta sin befintliga e-postadress i användargränssnittet, vilket kan leda till synkroniseringsfel som uppstår och användaren inte läggs till i ett klassteam.</span><span class="sxs-lookup"><span data-stu-id="41366-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="41366-123">Med **fältmappningen** Avbildning av institution-e-post säkerställer du att den här nivån av säkerhets- och valideringskontroll kan hanteras korrekt, oavsett om användarna har ändrat sin e-post i Blackboard Learn Ultra eller inte.</span><span class="sxs-lookup"><span data-stu-id="41366-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="41366-124">När två e-postadresser skiljer sig åt, antingen:</span><span class="sxs-lookup"><span data-stu-id="41366-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="41366-125">Ett beslut måste fattas om vilken källa som har företräde och kommer att tas som både person- och institution-e-post.</span><span class="sxs-lookup"><span data-stu-id="41366-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="41366-126">Eller</span><span class="sxs-lookup"><span data-stu-id="41366-126">Or</span></span>
- <span data-ttu-id="41366-127">En institution kan ange en anpassad fältmappning i sin institution-e-post, vilket kan lösa en möjlig konflikt.</span><span class="sxs-lookup"><span data-stu-id="41366-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="41366-128">**Fältmappningen för** institution-e-post är nu tillgänglig för alla befintliga SIS-integreringstyper **i Avancerad konfiguration Inställningar** Användare lär  >  **sig fältmappning av**  >  **objekttyp.**</span><span class="sxs-lookup"><span data-stu-id="41366-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="41366-129">Det är viktigt att observera att  Som standard har e-postadressen för institutionen angetts till Person-e-post för alla SIS-format och måste vara unik för varje person. </span><span class="sxs-lookup"><span data-stu-id="41366-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="41366-130">Alla befintliga integreringar som har ställts in och körs har den här datamappningen på plats eftersom SIS misslyckas med att importera användare om deras e-post dupliceras.</span><span class="sxs-lookup"><span data-stu-id="41366-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="41366-131">Om en institution kräver att institutionen ska kunna ändra e-post för institutionen till anpassad måste den hantera detta via den avancerade **Inställningar** i SIS.</span><span class="sxs-lookup"><span data-stu-id="41366-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="41366-132">Krav</span><span class="sxs-lookup"><span data-stu-id="41366-132">Requirements</span></span>

<span data-ttu-id="41366-133">Integrering Microsoft Teams de här klasserna är endast tillgängligt **för Ultra Course View-kurser.**</span><span class="sxs-lookup"><span data-stu-id="41366-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="41366-134">Institutionen måste uppfylla följande krav för att kunna använda den:</span><span class="sxs-lookup"><span data-stu-id="41366-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="41366-135">Ha Blackboard Lär dig Ultra SaaS med Ultra Base-navigering aktiverad</span><span class="sxs-lookup"><span data-stu-id="41366-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

- <span data-ttu-id="41366-136">Aktivera LTI för användning i kurser.</span><span class="sxs-lookup"><span data-stu-id="41366-136">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="41366-137">a.</span><span class="sxs-lookup"><span data-stu-id="41366-137">a.</span></span> <span data-ttu-id="41366-138">Gå till **Administratörspanelens**  >  **LTI-verktygsleverantörer**  >  **för att hantera globala egenskaper.**</span><span class="sxs-lookup"><span data-stu-id="41366-138">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="41366-139">b.</span><span class="sxs-lookup"><span data-stu-id="41366-139">b.</span></span> <span data-ttu-id="41366-140">Välj **LTI aktiverat i kurser** och om du vill väljer du Aktiverad i **organisationer.**</span><span class="sxs-lookup"><span data-stu-id="41366-140">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="41366-141">c.</span><span class="sxs-lookup"><span data-stu-id="41366-141">c.</span></span> <span data-ttu-id="41366-142">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="41366-142">Select **Submit**.</span></span>

- <span data-ttu-id="41366-143">LTI måste vara konfigurerat</span><span class="sxs-lookup"><span data-stu-id="41366-143">Must have LTI configured</span></span>

- <span data-ttu-id="41366-144">Lägga till Blackboard Learn Ultra Teams Classes LTI-integrering</span><span class="sxs-lookup"><span data-stu-id="41366-144">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="41366-145">Lägga Microsoft Teams klasserna LTI 1.3-verktyget</span><span class="sxs-lookup"><span data-stu-id="41366-145">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="41366-146">Lägga till REST API-verktyget och resursdelning mellan ursprung</span><span class="sxs-lookup"><span data-stu-id="41366-146">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="41366-147">Konfigurera och godkänna Microsoft Teams klassintegrering</span><span class="sxs-lookup"><span data-stu-id="41366-147">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="41366-148">Lägg till Blackboard Learn Ultra Teams Classes LTI 1.3-verktyget</span><span class="sxs-lookup"><span data-stu-id="41366-148">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="41366-149">I **administratörspanelen väljer** du **LTI-verktygsproviders**.</span><span class="sxs-lookup"><span data-stu-id="41366-149">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="41366-150">Välj **registrera LTI 1.3 Tool**.</span><span class="sxs-lookup"><span data-stu-id="41366-150">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="41366-151">I fältet **Klient-ID** skriver du in, eller kopierar och klistrar in, detta ID:</span><span class="sxs-lookup"><span data-stu-id="41366-151">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="41366-152">Granska alla inställningar som har fyllts i på förhand och i **Verktygsstatus** och välj sedan **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="41366-152">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="41366-153">Välj **Roll i** **Kurs, Namn och E-postadress** i **Institutionsprinciper** och välj sedan **Ja för** båda.</span><span class="sxs-lookup"><span data-stu-id="41366-153">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="41366-154">Välj **Tillåt betygstjänståtkomst och** Tillåt åtkomst till **medlemskapstjänst.**</span><span class="sxs-lookup"><span data-stu-id="41366-154">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="41366-155">Lägga till Microsoft Teams Classes LTI 1.3 Tool</span><span class="sxs-lookup"><span data-stu-id="41366-155">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="41366-156">I **administratörspanelen väljer** du **LTI-verktygsproviders**.</span><span class="sxs-lookup"><span data-stu-id="41366-156">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="41366-157">Välj **registrera LTI 1.3 Tool**.</span><span class="sxs-lookup"><span data-stu-id="41366-157">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="41366-158">I fältet **Klient-ID** skriver du in, eller kopierar och klistrar in, detta ID:</span><span class="sxs-lookup"><span data-stu-id="41366-158">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="41366-159">Granska alla inställningar som har redan fyllts i och välj *Aktiverad* i *Verktygsstatus.*</span><span class="sxs-lookup"><span data-stu-id="41366-159">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="41366-160">I **Principer för institutionen** väljer du Roll i **Kurs, Namn och** **E-postadress.**</span><span class="sxs-lookup"><span data-stu-id="41366-160">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="41366-161">Välj **Ja** för båda.</span><span class="sxs-lookup"><span data-stu-id="41366-161">Select **Yes** for both.</span></span>

6. <span data-ttu-id="41366-162">Välj **Tillåt betygstjänståtkomst och** Tillåt åtkomst till **medlemskapstjänst.**</span><span class="sxs-lookup"><span data-stu-id="41366-162">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="41366-163">Lägga till REST API-verktyget</span><span class="sxs-lookup"><span data-stu-id="41366-163">Add the REST API tool</span></span>

1. <span data-ttu-id="41366-164">Från **administratörspanelen** går du till **Integrationer** och väljer **Rest API-integrationer.**</span><span class="sxs-lookup"><span data-stu-id="41366-164">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="41366-165">Välj **Skapa integration.**</span><span class="sxs-lookup"><span data-stu-id="41366-165">Select **Create Integration**.</span></span>

3. <span data-ttu-id="41366-166">I fältet **Program-ID** skriver du in, eller kopierar och klistrar in, detta ID:</span><span class="sxs-lookup"><span data-stu-id="41366-166">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="41366-167">Skriv en användare för den här integreringen.</span><span class="sxs-lookup"><span data-stu-id="41366-167">Type a user for this integration.</span></span>

   <span data-ttu-id="41366-168">Den här användaren är den med home API-åtkomst som programmet är kopplat till.</span><span class="sxs-lookup"><span data-stu-id="41366-168">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="41366-169">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="41366-169">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="41366-170">Lägga till resursdelning mellan ursprung</span><span class="sxs-lookup"><span data-stu-id="41366-170">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="41366-171">Från **administratörspanelen** går du till **Integrationer** och väljer \**Resursdelning mellan ursprung.*</span><span class="sxs-lookup"><span data-stu-id="41366-171">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="41366-172">Välj **Skapa konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="41366-172">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="41366-173">I fältet **Ursprung skriver** du kopiera och klistra in url:en:</span><span class="sxs-lookup"><span data-stu-id="41366-173">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="41366-174">I fältet **Tillåtna rubriker** skriver du **Auktorisering**.</span><span class="sxs-lookup"><span data-stu-id="41366-174">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="41366-175">Ange **Tillgänglig** till **Ja.**</span><span class="sxs-lookup"><span data-stu-id="41366-175">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="41366-176">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="41366-176">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="41366-177">Konfigurera och godkänna Microsoft Teams klassintegrering</span><span class="sxs-lookup"><span data-stu-id="41366-177">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="41366-178">Om du vill integrera din Blackboard Learn Ultra-instans med Microsoft Teams-klasser måste du se till att programmet Blackboard Learn Ultra har godkänts för åtkomst inom Microsoft Azure klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="41366-178">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="41366-179">Det här är en process som måste slutföras av institutionens globala Microsoft 365 administratör.</span><span class="sxs-lookup"><span data-stu-id="41366-179">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="41366-180">Den här processen kan göras antingen före eller efter att du har konfigurerat LTI-programmen i din Blackboard Learn Ultra Instance.</span><span class="sxs-lookup"><span data-stu-id="41366-180">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="41366-181">Innan du konfigurerar LTI-programmen</span><span class="sxs-lookup"><span data-stu-id="41366-181">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="41366-182">Om du väljer att godkänna Blackboard Learn Ultra Teams Classes Azure-appen innan du konfigurerar LTI-integrationerna måste du omdirigera till slutpunkten för administratörsmedgivande för **Microsoft-identitetsplattformen.**</span><span class="sxs-lookup"><span data-stu-id="41366-182">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="41366-183">URL:en visas:</span><span class="sxs-lookup"><span data-stu-id="41366-183">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="41366-184">Du ersätter **{Tenant} med ditt** specifika institutions- Microsoft Azure-ID.</span><span class="sxs-lookup"><span data-stu-id="41366-184">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="41366-185">När du har konfigurerat LTI-programmen</span><span class="sxs-lookup"><span data-stu-id="41366-185">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="41366-186">På **administratörspanelen** går du till **Verktyg och verktyg och** väljer Sedan Microsoft Teams Integration **Admin.**</span><span class="sxs-lookup"><span data-stu-id="41366-186">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="41366-187">Välj **Aktivera Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="41366-187">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="41366-188">Lägg till ditt **Klientorganisations-ID** för Microsoft i det tillgängliga textfältet.</span><span class="sxs-lookup"><span data-stu-id="41366-188">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="41366-189">Välj något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="41366-189">Choose one of the following options:</span></span>

   - <span data-ttu-id="41366-190">Om appen har förmedgivande visas en liten bockmarkering.</span><span class="sxs-lookup"><span data-stu-id="41366-190">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="41366-191">Om bockmarkeringen visas väljer du **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="41366-191">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="41366-192">Om medgivandet inte har godkänts följer du anvisningarna som beskrivs för att generera webbadressen för medgivande och skicka den till den globala Microsoft 365 för godkännande.</span><span class="sxs-lookup"><span data-stu-id="41366-192">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="41366-193">När du har bekräftat att du godkänner väljer **du Försök igen** för att bekräfta och väljer sedan **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="41366-193">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>
