---
title: Teams för strikt reglerade data
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Skapa ett säkert team för att lagra dina mest värdefulla och känsliga filer.
ms.openlocfilehash: aeb3662d6c8a21cbd56d983515913750fd5259f1
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951976"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="77293-103">Teams för strikt reglerade data</span><span class="sxs-lookup"><span data-stu-id="77293-103">Teams for highly regulated data</span></span>

<span data-ttu-id="77293-104">I den här artikeln får du rekommendationer och anvisningar om hur du konfigurerar ett privat team i Microsoft Teams som låser åtkomsten till Teams-funktioner – till exempel chattar, möten och filer – till endast medlemmar och ägare av Office 365-gruppen för teamet.</span><span class="sxs-lookup"><span data-stu-id="77293-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="77293-105">Utöver den privata åtkomst som baseras på Office 365-gruppen beskrivs i artikeln hur du konfigurerar den underliggande privata SharePoint-gruppwebbplatsen, som du når via avsnittet **Filer** i en teamkanal, så att du får den extra säkerhet som krävs för lagring av strikt reglerade data.</span><span class="sxs-lookup"><span data-stu-id="77293-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="77293-106">På SharePoint-gruppwebbplatsen kan du lagra och jobba tillsammans med filer, sidor, en delad kalender, uppgifter, en anteckningsbok och listor.</span><span class="sxs-lookup"><span data-stu-id="77293-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

>[!Note]
> <span data-ttu-id="77293-107">Ett liknande scenario med SharePoint finns [här](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="77293-107">A similar scenario using SharePoint is [here](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
>

<span data-ttu-id="77293-108">De olika elementen för konfiguration av ett team för strikt reglerade data är:</span><span class="sxs-lookup"><span data-stu-id="77293-108">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="77293-109">Ett privat team med en motsvarande Office 365-grupp som har en ägare och medlemsanvändarkonton.</span><span class="sxs-lookup"><span data-stu-id="77293-109">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="77293-110">Ytterligare säkerhet på den underliggande SharePoint-webbplatsen för teamet som:</span><span class="sxs-lookup"><span data-stu-id="77293-110">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="77293-111">hindrar medlemmar av webbplatsen från att ge åtkomst till andra,</span><span class="sxs-lookup"><span data-stu-id="77293-111">Prevents members of the site from granting access to others.</span></span>
  - <span data-ttu-id="77293-112">hindrar icke-medlemmar av webbplatsen från att begära åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="77293-112">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="77293-113">En Office 365-kvarhållningsetikett för den underliggande SharePoint-webbplatsen som automatiskt tillämpas på nya filer på webbplatsen som standardmetod för att definiera kvarhållningsprinciper.</span><span class="sxs-lookup"><span data-stu-id="77293-113">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="77293-114">En DLP-princip (princip för dataförlustskydd) som använder kvarhållningsetiketten och blockerar användare från att dela eller skicka filer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="77293-114">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="77293-115">En Office 365-känslighetsetikett eller en underetikett för en strikt reglerad etikett som har kryptering aktiverat och samredigeringsbehörighet för teamets Office 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="77293-115">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="77293-116">Användare tillämpar etiketten eller underetiketten som lagras i avsnittet **Filer** för teamet via menyfältsalternativet **Känslighet** i Word, Excel och PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="77293-116">Users apply the label or sublabel to files stored in **Files** section of the team from the **Sensitivity** menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="77293-117">Här är den resulterande konfigurationen med en känslighetsetikett.</span><span class="sxs-lookup"><span data-stu-id="77293-117">Here is the resulting configuration with a sensitivity label.</span></span>

![Konfigurationen i scenariot för säkert team](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="77293-119">Titta på den här korta videon så får du en snabb översikt.</span><span class="sxs-lookup"><span data-stu-id="77293-119">For a quick overview, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> <span data-ttu-id="77293-120">En sammanfattning på en sida finns på [affischen Teams för strikt reglerade data](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf).</span><span class="sxs-lookup"><span data-stu-id="77293-120">For a 1-page summary of this scenario, see the [Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="77293-121">[![Teams för strikt reglerade data (affisch)](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="77293-121">[![Teams for highly regulated data poster](../media/secure-teams-highly-regulated-data-scenario/teams-highly-regulated-data-poster.png)](../media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="77293-122">Du kan också ladda ned den här affischen i [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf)- eller [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx)-format och skriva ut den i pappersstorleken letter, legal eller tabloid (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="77293-122">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/TeamsHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/secure-teams-highly-regulated-data-scenario/Teams-Highly-Regulated-Data-Poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>

## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="77293-123">Fas 1: Konfigurera ett team för strikt reglerade data</span><span class="sxs-lookup"><span data-stu-id="77293-123">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="77293-124">Konfigurationen från slutpunkt till slutpunkt består av följande steg:</span><span class="sxs-lookup"><span data-stu-id="77293-124">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="77293-125">Konfigurera identitet och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="77293-125">Configure identity and device access.</span></span>
2. <span data-ttu-id="77293-126">Skapa ett privat team.</span><span class="sxs-lookup"><span data-stu-id="77293-126">Create a private team.</span></span>
3. <span data-ttu-id="77293-127">Konfigurera den underliggande SharePoint-webbplatsen för ytterligare säkerhet.</span><span class="sxs-lookup"><span data-stu-id="77293-127">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="77293-128">Skapa en kvarhållningsetikett och DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="77293-128">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="77293-129">Skapa etiketten eller underetiketten för den strikt reglerade etiketten.</span><span class="sxs-lookup"><span data-stu-id="77293-129">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="77293-130">Steg 1: Konfigurera identitet och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="77293-130">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="77293-131">För att skydda åtkomsten till teamet och dess underliggande SharePoint-webbplats ska du se till att du har konfigurerat [principer för identitet och enhetsåtkomst](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) och de rekommenderade [principerna för SharePoint Online-åtkomst](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="77293-131">To protect access to the team and its underlying SharePoint site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the recommended [SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="77293-132">Steg 2: Skapa ett privat team</span><span class="sxs-lookup"><span data-stu-id="77293-132">Step 2: Create a private team</span></span>

<span data-ttu-id="77293-133">Skapa ett privat team med hjälp av [dessa instruktioner](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="77293-133">Use [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private team.</span></span>

<span data-ttu-id="77293-134">När du skapar ett privat team finns följande standardbehörigheter:</span><span class="sxs-lookup"><span data-stu-id="77293-134">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="77293-135">Office 365-gruppen för teamet (teamgruppen) har gruppägare och gruppmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="77293-135">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="77293-136">För den underliggande SharePoint-webbplatsen (gruppwebbplatsen):</span><span class="sxs-lookup"><span data-stu-id="77293-136">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="77293-137">Administratörerna för webbplatssamlingar konfigureras för teamgruppens ägare</span><span class="sxs-lookup"><span data-stu-id="77293-137">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="77293-138">För gruppwebbplatsen:</span><span class="sxs-lookup"><span data-stu-id="77293-138">For the Team Site:</span></span> 
    - <span data-ttu-id="77293-139">SharePoint-gruppen Gruppwebbplatsägare – med behörighetsnivån Fullständig kontroll – ställs in på teamgruppens ägare</span><span class="sxs-lookup"><span data-stu-id="77293-139">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="77293-140">SharePoint-gruppen Gruppwebbplatsmedlemmar – med behörighetsnivån Redigera – ställs in på teamgruppens medlemmar</span><span class="sxs-lookup"><span data-stu-id="77293-140">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="77293-141">SharePoint-gruppen Gruppwebbplatsbesökare – med behörighetsnivån Läsa – har inga grupper eller användarkonton</span><span class="sxs-lookup"><span data-stu-id="77293-141">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="77293-142">Här är standardbehörigheterna för gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="77293-142">Here are the default permissions for the Team Site.</span></span>

![Standardbehörigheterna för en gruppwebbplats](../media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="77293-144">Om du visar SharePoint-gruppen för ägare, \<teamets namn> för behörighetsnivån Redigera visas inte Ägare för \<teamets namn>.</span><span class="sxs-lookup"><span data-stu-id="77293-144">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="77293-145">De resulterande behörigheterna tillåter följande:</span><span class="sxs-lookup"><span data-stu-id="77293-145">The resulting permissions allow:</span></span>

- <span data-ttu-id="77293-146">Teamgruppens ägare kan administrera webbplatsen och har fullständig kontroll över webbplatsens innehåll.</span><span class="sxs-lookup"><span data-stu-id="77293-146">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="77293-147">Teamgruppens medlemmar kan skapa och redigera filer på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="77293-147">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="77293-148">Underhåll av behörigheter är samma som teammedlems- och ägarunderhåll.</span><span class="sxs-lookup"><span data-stu-id="77293-148">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="77293-149">Här är konfigurationsresultatet hittills.</span><span class="sxs-lookup"><span data-stu-id="77293-149">Here’s the resulting configuration so far.</span></span>

![Steg 2 av konfigurationen i scenariot för säkert team](../media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="77293-151">Steg 3: Konfigurera den underliggande SharePoint-webbplatsen för ytterligare säkerhet</span><span class="sxs-lookup"><span data-stu-id="77293-151">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="77293-152">Konfigurera dessa behörighetsinställningar på gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="77293-152">From the Team Site, configure these permission settings.</span></span>

1. <span data-ttu-id="77293-153">Klicka i verktygsfältet på inställningsikonen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="77293-153">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="77293-154">I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="77293-154">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="77293-155">Under **Delningsbehörigheter** väljer du **Endast webbplatsägare kan dela filer, mappar och webbplats**.</span><span class="sxs-lookup"><span data-stu-id="77293-155">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="77293-156">Inaktivera **Tillåt åtkomstbegäranden** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="77293-156">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="77293-157">Med de här inställningarna inaktiveras funktionen för teamgruppens medlemmar att dela gruppwebbplatsen med andra medlemmar eller för icke-medlemmar att begära åtkomst till gruppwebbplatsen.</span><span class="sxs-lookup"><span data-stu-id="77293-157">With these settings, the ability for Team Group members to share the Team Site with other members or for non-members to request access to the Team Site is disabled.</span></span>

<span data-ttu-id="77293-158">Här är konfigurationsresultatet hittills.</span><span class="sxs-lookup"><span data-stu-id="77293-158">Here’s the resulting configuration so far.</span></span>

![Steg 3 av konfigurationen i scenariot för säkert team](../media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="77293-160">Steg 4: Skapa en kvarhållningsetikett och DLP-princip</span><span class="sxs-lookup"><span data-stu-id="77293-160">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="77293-161">Med [dessa instruktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) gör du följande:</span><span class="sxs-lookup"><span data-stu-id="77293-161">Use [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp) to:</span></span>

1. <span data-ttu-id="77293-162">Skapar och publicerar en kvarhållningsetikett för strikt reglerade data (om det behövs).</span><span class="sxs-lookup"><span data-stu-id="77293-162">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="77293-163">Konfigurerar gruppwebbplatsen för kvarhållningsetiketten som skapats i steg 1.</span><span class="sxs-lookup"><span data-stu-id="77293-163">Configure the Team Site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="77293-164">Skapar en DLP-princip för strikt reglerade data som använder kvarhållningsetiketten som skapats i steg 2 och hindrar användare från att skicka filer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="77293-164">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization.</span></span> <span data-ttu-id="77293-165">Du kan också konfigurera principen för fler behov, till exempel för bestämmelser i hälsovårds- och finansbranschen, utifrån [DLP-principmallar](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="77293-165">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="77293-166">Här är konfigurationsresultatet hittills.</span><span class="sxs-lookup"><span data-stu-id="77293-166">Here’s the resulting configuration so far.</span></span>

![Steg 4 av konfigurationen i scenariot för säkert team](../media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-a-sensitivity-label-or-a-sublabel-of-the-highly-regulated-sensitivity-label"></a><span data-ttu-id="77293-168">Step 5: Skapa en känslighetsetikett eller en underetikett för känslighetsetiketten för strikt reglerade data</span><span class="sxs-lookup"><span data-stu-id="77293-168">Step 5: Create a sensitivity label or a sublabel of the highly regulated sensitivity label</span></span>

<span data-ttu-id="77293-169">Till skillnad från en känslighetsetikett för strikt reglerade data som alla kan tillämpa på valfri fil behöver ett säkert team en egen etikett eller underetikett så att tilldelade filer:</span><span class="sxs-lookup"><span data-stu-id="77293-169">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="77293-170">krypteras och krypteringen följer med filen,</span><span class="sxs-lookup"><span data-stu-id="77293-170">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="77293-171">innehåller anpassade behörigheter så att bara medlemmar i teamgruppen kan öppna den.</span><span class="sxs-lookup"><span data-stu-id="77293-171">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="77293-172">För att åstadkomma den här extra säkerhetsnivån för filer på gruppwebbplatsen måste du konfigurera en känslighetsetikett som antingen är en egen etikett eller en underetikett för den allmänna etiketten för strikt reglerade filer.</span><span class="sxs-lookup"><span data-stu-id="77293-172">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="77293-173">Det är bara teamgruppens medlemmar som ser den i listan med etiketter.</span><span class="sxs-lookup"><span data-stu-id="77293-173">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="77293-174">Använd en känslighetsetikett när du behöver ett litet antal etiketter för både global användning och enskilda privata team.</span><span class="sxs-lookup"><span data-stu-id="77293-174">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="77293-175">Använd en underetikett för känslighet när du har ett stort antal etiketter eller vill ordna etiketter för privata team under den strikt reglerade etiketten.</span><span class="sxs-lookup"><span data-stu-id="77293-175">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="77293-176">[Använd dessa instruktioner](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) när du konfigurerar en separat etikett eller en underetikett med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="77293-176">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="77293-177">Namnet på etiketten innehåller teamets namn</span><span class="sxs-lookup"><span data-stu-id="77293-177">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="77293-178">Kryptering är aktiverat</span><span class="sxs-lookup"><span data-stu-id="77293-178">Encryption is enabled</span></span>
- <span data-ttu-id="77293-179">Teamgruppen har samredigeringsbehörighet</span><span class="sxs-lookup"><span data-stu-id="77293-179">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="77293-180">Här är konfigurationsresultatet med den nya etiketten.</span><span class="sxs-lookup"><span data-stu-id="77293-180">Here’s the resulting configuration with the new label.</span></span>

![Steg 5 av konfigurationen i scenariot för säkert team](../media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="77293-182">Här är relationen mellan känslighetsetiketten och teamgruppen.</span><span class="sxs-lookup"><span data-stu-id="77293-182">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Relation mellan teamgruppen och etikettbehörigheterna](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="77293-184">Om du konfigurerar känslighetsetiketten eller underetiketten för användardefinierade behörigheter eller med ett utgångsdatum kan du inte öppna filen i Teams eller SharePoint.</span><span class="sxs-lookup"><span data-stu-id="77293-184">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="77293-185">Du måste använda en Office-app.</span><span class="sxs-lookup"><span data-stu-id="77293-185">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="77293-186">Anpassade behörigheter</span><span class="sxs-lookup"><span data-stu-id="77293-186">Custom permissions</span></span>

<span data-ttu-id="77293-187">Du kan även konfigurera anpassade SharePoint-webbplatsbehörigheter för gruppwebbplatsen och, om det behövs, motsvarande känslighetsetikett.</span><span class="sxs-lookup"><span data-stu-id="77293-187">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="77293-188">Här är två exempel.</span><span class="sxs-lookup"><span data-stu-id="77293-188">Here are two examples.</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="77293-189">Exempel 1: Delegera SharePoint-webbplatsens administration</span><span class="sxs-lookup"><span data-stu-id="77293-189">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="77293-190">Om teamägaren inte har erfarenhet av SharePoint-administration eller vill delegera administrationen av gruppwebbplatsen kan ägaren lägga till användarkontot för en SharePoint-administratör i listan över teamägare.</span><span class="sxs-lookup"><span data-stu-id="77293-190">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="77293-191">Men då har SharePoint-administratören fullständig åtkomst till teamet och alla dess resurser och skulle kunna öppna en fil med känslighetsetiketten.</span><span class="sxs-lookup"><span data-stu-id="77293-191">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="77293-192">För att förhindra överflödiga behörigheter lägger du till användarkontot för SharePoint-administratören i SharePoint-gruppen Gruppwebbplatsägare i webbplatsens avancerade behörighetsinställningar.</span><span class="sxs-lookup"><span data-stu-id="77293-192">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="77293-193">SharePoint-administratören kan administrera webbplatsen men kan inte komma åt teamet och några av dess resurser eller öppna filerna som tilldelats känslighetsetiketten.</span><span class="sxs-lookup"><span data-stu-id="77293-193">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="77293-194">Exempel 2: Tillåta åtkomst med endast visning av etiketterade filer</span><span class="sxs-lookup"><span data-stu-id="77293-194">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="77293-195">Om vissa i personalen behöver se innehållet i etiketterade filer på gruppwebbplatsen lägger du till deras användarkonton i:</span><span class="sxs-lookup"><span data-stu-id="77293-195">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="77293-196">SharePoint-gruppen Besökare av \<teamets namn>, vars standardinställning är läsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="77293-196">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="77293-197">Känslighetsetiketten med behörigheten Läsare.</span><span class="sxs-lookup"><span data-stu-id="77293-197">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="77293-198">Här är behörighetsresultatet för etiketten.</span><span class="sxs-lookup"><span data-stu-id="77293-198">Here are the resulting permissions on the label.</span></span>

![Exempel på anpassade behörigheter för visning av etiketterade filer](../media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="77293-200">Webbplatsbesökarna kommer åt gruppwebbplatsen direkt och kan visa innehållet som tilldelats underetiketten.</span><span class="sxs-lookup"><span data-stu-id="77293-200">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="77293-201">Men eftersom de inte är medlemmar i teamgruppen kan de inte komma åt teamet eller dess resurser.</span><span class="sxs-lookup"><span data-stu-id="77293-201">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="77293-202">Fas 2: Driva på teammedlemmarnas användning</span><span class="sxs-lookup"><span data-stu-id="77293-202">Phase 2: Drive user adoption for team members</span></span>

<span data-ttu-id="77293-203">Med teamet på plats är det dags att driva på teamets användning och den extra säkerheten för teammedlemmar.</span><span class="sxs-lookup"><span data-stu-id="77293-203">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="77293-204">Steg 1: Utbilda dina användare</span><span class="sxs-lookup"><span data-stu-id="77293-204">Step 1: Train your users</span></span>

<span data-ttu-id="77293-205">Medlemmar i teamgruppen kan komma åt teamet och alla dess resurser, inklusive chattar, möten och andra appar.</span><span class="sxs-lookup"><span data-stu-id="77293-205">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="77293-206">När de arbetar med filer i avsnittet **Filer** i en kanal måste medlemmarna i teamgruppen tilldela känslighetsetiketten eller underetiketten till filer som skapats för det säkra teamet.</span><span class="sxs-lookup"><span data-stu-id="77293-206">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="77293-207">Här följer ett exempel.</span><span class="sxs-lookup"><span data-stu-id="77293-207">Here’s an example.</span></span>

![Exempel på en etikett tillämpad på en fil i ett säkert team](../media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="77293-209">När etiketten tillämpas på filen så skyddas den.</span><span class="sxs-lookup"><span data-stu-id="77293-209">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="77293-210">Medlemmar i teamgruppen kan öppna den i Teams och samarbeta i realtid.</span><span class="sxs-lookup"><span data-stu-id="77293-210">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="77293-211">Den är krypterad och innehåller behörigheter för samredigering som angetts för teamgruppens medlemmar.</span><span class="sxs-lookup"><span data-stu-id="77293-211">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="77293-212">Om filen lämnar webbplatsen och vidarebefordras till en illvillig användare måste användaren ange autentiseringsuppgifterna för ett användarkonto som är medlem i teamgruppen för att öppna filen och visa innehållet.</span><span class="sxs-lookup"><span data-stu-id="77293-212">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="77293-213">Utbilda dina teammedlemmar i följande:</span><span class="sxs-lookup"><span data-stu-id="77293-213">Train your team members:</span></span>

- <span data-ttu-id="77293-214">Om vikten av att använda det nya teamet för chattar, möten, filer och andra resurser för gruppwebbplatsen och konsekvenserna av en läcka av strikt reglerade data, till exempel juridiska aspekter, tillsynsböter, utpressningstrojaner eller förlust av konkurrensfördelar.</span><span class="sxs-lookup"><span data-stu-id="77293-214">On the importance of using the new team for chats, meetings, files, and the other resources of the Team Site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="77293-215">Hur man får åtkomst till teamet.</span><span class="sxs-lookup"><span data-stu-id="77293-215">How to access the team.</span></span>
- <span data-ttu-id="77293-216">Hur man skapar nya filer på webbplatsen och laddar upp nya filer som lagras lokalt.</span><span class="sxs-lookup"><span data-stu-id="77293-216">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="77293-217">Hur DLP-principen förhindrar dem från att dela filer externt.</span><span class="sxs-lookup"><span data-stu-id="77293-217">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="77293-218">Hur man etiketterar filer med den anpassade etiketten eller underetiketten för teamet.</span><span class="sxs-lookup"><span data-stu-id="77293-218">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="77293-219">Hur etiketten eller underetiketten skyddar filer även när de läcker från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="77293-219">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="77293-220">I den här utbildningen ska det ingå praktiska övningar så att teamets medlemmar kan prova funktionerna och se deras resultat.</span><span class="sxs-lookup"><span data-stu-id="77293-220">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="77293-221">Steg 2: Utföra regelbundna granskningar av användning och hantera feedback för teammedlemmar</span><span class="sxs-lookup"><span data-stu-id="77293-221">Step 2: Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="77293-222">I veckorna efter utbildningen:</span><span class="sxs-lookup"><span data-stu-id="77293-222">In the weeks after training:</span></span>

- <span data-ttu-id="77293-223">Snabbt hantera feedback från teammedlemmar och finjustera principer och konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="77293-223">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="77293-224">Analysera teamets användning och jämföra med den förväntade användningen.</span><span class="sxs-lookup"><span data-stu-id="77293-224">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="77293-225">Kontrollera att strikt reglerade filer har etiketterats korrekt med den anpassade känslighetsetiketten eller underetiketten.</span><span class="sxs-lookup"><span data-stu-id="77293-225">Verify that highly regulated files have been properly labeled with the custom sensitivity label or sublabel.</span></span>

  <span data-ttu-id="77293-226">Du kan se vilka filer som har tilldelats genom att visa en mapp i SharePoint och lägga till kolumnen **Känslighet** genom alternativet **Visa/dölj kolumner** i **Lägg till kolumn**.</span><span class="sxs-lookup"><span data-stu-id="77293-226">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="77293-227">Vidareutbilda dina användare efter behov.</span><span class="sxs-lookup"><span data-stu-id="77293-227">Retrain your users as needed.</span></span>

## <a name="demonstrate-this-in-a-test-environment"></a><span data-ttu-id="77293-228">Visa det här i en testmiljö</span><span class="sxs-lookup"><span data-stu-id="77293-228">Demonstrate this in a test environment</span></span>

<span data-ttu-id="77293-229">Om du vill skapa en egen testmiljö för att testa teamens känslighet och mycket konfidentiella filer läser du [dessa instruktioner](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="77293-229">To build out your own test environment to test teams for sensitive and highly confidential files, see [these instructions](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-team-for-files-in-a-dev-test-environment).</span></span> 

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)

## <a name="how-the-contoso-corporation-used-a-secure-team-for-a-top-secret-project"></a><span data-ttu-id="77293-231">Så här använde Contoso Corporation ett säkert team för ett topphemligt projekt</span><span class="sxs-lookup"><span data-stu-id="77293-231">How the Contoso Corporation used a secure team for a top-secret project</span></span>

<span data-ttu-id="77293-232">Contoso Corporation är ett fiktivt men representativt globalt tillverkningskonglomerat.</span><span class="sxs-lookup"><span data-stu-id="77293-232">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="77293-233">Se hur Contoso konfigurerade och arbetade på införandet av ett [säkert team](contoso-team-for-top-secret-project.md) för ett topphemligt projekt för att utveckla och marknadsföra nya produkter och tjänster.</span><span class="sxs-lookup"><span data-stu-id="77293-233">See how Contoso configured and drove the adoption of a [secure team](contoso-team-for-top-secret-project.md) for a top secret project to develop and bring to market a new set of products and services.</span></span> 

## <a name="see-also"></a><span data-ttu-id="77293-234">Se även</span><span class="sxs-lookup"><span data-stu-id="77293-234">See also</span></span>

[<span data-ttu-id="77293-235">SharePoint-webbplatser för strikt reglerade data</span><span class="sxs-lookup"><span data-stu-id="77293-235">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="77293-236">Arbetsbelastningar och scenarier i Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="77293-236">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="77293-237">[Produktivitetsbiblioteket för Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="77293-237">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="77293-238">Distributionsguide</span><span class="sxs-lookup"><span data-stu-id="77293-238">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
