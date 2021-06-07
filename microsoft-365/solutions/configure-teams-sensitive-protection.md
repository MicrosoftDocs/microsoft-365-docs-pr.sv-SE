---
title: Konfigurera team med skydd för känslig data
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: Lär dig hur du distribuerar team med skydd för känslig data.
ms.openlocfilehash: a3f715cb05ad1d5acf3c93c58959f12ebec46978
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788349"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="74867-103">Konfigurera team med skydd för känslig data</span><span class="sxs-lookup"><span data-stu-id="74867-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="74867-104">I den här artikeln ska vi titta närmare på hur du konfigurerar ett team för en känslig skyddsnivå.</span><span class="sxs-lookup"><span data-stu-id="74867-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="74867-105">Kontrollera att du har slutfört stegen i [distribuera teams med grundskydd](configure-teams-baseline-protection.md) innan du följer anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="74867-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="74867-106">Den känsliga nivån erbjuder följande ytterligare skydd över grundnivån:</span><span class="sxs-lookup"><span data-stu-id="74867-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="74867-p102">En känslighetsetikett för teamet som gör att du kan aktivera eller inaktivera gästdelning samt begränsa åtkomst till SharePoint-innehåll till endast webben för ohanterade enheter. Etiketten kan även användas till att klassificera filer.</span><span class="sxs-lookup"><span data-stu-id="74867-p102">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices. This label can also be used to classify files.</span></span>
- <span data-ttu-id="74867-109">En mer restriktiv länktyp för standarddelning</span><span class="sxs-lookup"><span data-stu-id="74867-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="74867-110">Endast teamägare kan skapa privata kanaler.</span><span class="sxs-lookup"><span data-stu-id="74867-110">Only team owners can create private channels.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="74867-111">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="74867-111">Video demonstration</span></span>

<span data-ttu-id="74867-112">Titta på den här videon för en genomgång av procedurerna som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="74867-112">Watch this video for a walkthrough of the procedures described in this article.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a><span data-ttu-id="74867-113">Gästdelning</span><span class="sxs-lookup"><span data-stu-id="74867-113">Guest sharing</span></span>

<span data-ttu-id="74867-114">Beroende på företagets natur kan du kanske inte aktivera gästdelning för team som innehåller känsliga data.</span><span class="sxs-lookup"><span data-stu-id="74867-114">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="74867-115">Om du tänker samarbeta med personer utanför organisationen i teamet, rekommenderar vi att du aktiverar gästdelning.</span><span class="sxs-lookup"><span data-stu-id="74867-115">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="74867-116">Microsoft 365 innehåller en mängd olika funktioner för säkerhet och efterlevnad som hjälper dig att dela känsligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="74867-116">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="74867-117">Det här är vanligtvis ett säkrare alternativ än att skicka innehåll direkt till personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="74867-117">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="74867-118">Information om hur du delar med gäster säkert finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="74867-118">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="74867-119">Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="74867-119">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="74867-120">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="74867-120">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="74867-121">För att tillåta eller blockera gästdelning använder vi en kombination av känslighetsetiketter för teamet och delning på webbplats nivå för den associerade SharePoint-webbplatsen, som vi ser senare.</span><span class="sxs-lookup"><span data-stu-id="74867-121">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="74867-122">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="74867-122">Sensitivity labels</span></span>

<span data-ttu-id="74867-123">För den känsliga skyddsnivån använder vi en känslighetsetikett för att klassificera teamet.</span><span class="sxs-lookup"><span data-stu-id="74867-123">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="74867-124">Den här etiketten kan också användas för att klassificera enskilda filer i detta eller andra team, eller på andra filplatser som SharePoint eller OneDrive.</span><span class="sxs-lookup"><span data-stu-id="74867-124">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="74867-125">Som ett första steg måste du aktivera känslighetsetiketter för Teams.</span><span class="sxs-lookup"><span data-stu-id="74867-125">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="74867-126">Mer information finns i [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Office 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="74867-126">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="74867-127">Om du redan har känslighetsetiketter distribuerade i din organisation, bör du överväga hur denna etikett passar med din övergripande etikettstrategi.</span><span class="sxs-lookup"><span data-stu-id="74867-127">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="74867-128">Du kan ändra namn eller inställningar om det behövs för att uppfylla organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="74867-128">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="74867-129">När du har aktiverat känslighetsetiketter för Teams är nästa steg att skapa etiketten.</span><span class="sxs-lookup"><span data-stu-id="74867-129">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="74867-130">Att skapa en känslighetsetikett</span><span class="sxs-lookup"><span data-stu-id="74867-130">To create a sensitivity label</span></span>
1. <span data-ttu-id="74867-131">Öppna [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="74867-131">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="74867-132">Under **Lösningar** klickar du på **Informationsskydd**.</span><span class="sxs-lookup"><span data-stu-id="74867-132">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="74867-133">Klicka på **Skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="74867-133">Click **Create a label**.</span></span>
4. <span data-ttu-id="74867-134">Namnge etiketten.</span><span class="sxs-lookup"><span data-stu-id="74867-134">Give the label a name.</span></span> <span data-ttu-id="74867-135">Vi föreslår **Känslig**, men du kan välja ett annat namn om det redan används.</span><span class="sxs-lookup"><span data-stu-id="74867-135">We suggest **Sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="74867-136">Lägg till ett visningsnamn och en beskrivning och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74867-136">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="74867-137">På sidan **Definiera omfång för etikett** väljer du **filer och e-postmeddelanden** samt **grupper och webbplatser** och klickar på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74867-137">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="74867-138">På sidan **Välj säkerhetsinställningar för filer och e-postmeddelanden** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74867-138">On the **Choose protection settings for files and emails** page, click **Next**.</span></span>
8. <span data-ttu-id="74867-139">På sidan *Auto-etiketting för filer och e-postmeddelanden*\* klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74867-139">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
9. <span data-ttu-id="74867-140">På sidan **Definiera säkerhetsinställningar för grupper och webbplatser** väljer du **Inställningar för sekretess och extern användaråtkomst** samt **Inställningar för enhetsåtkomst och extern delning** och klickar på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74867-140">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
10. <span data-ttu-id="74867-141">Välj alternativet **Privat** under **Sekretess** på sidan **Definiera inställningar för sekretess och extern användaråtkomst**.</span><span class="sxs-lookup"><span data-stu-id="74867-141">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
11. <span data-ttu-id="74867-142">Om du vill tillåta gäståtkomst väljer du **Låt Microsoft 365-gruppägare lägga till personer utanför organisationen i gruppen som gäster** under **Extern användaråtkomst**.</span><span class="sxs-lookup"><span data-stu-id="74867-142">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
12. <span data-ttu-id="74867-143">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74867-143">Click **Next**.</span></span>
13. <span data-ttu-id="74867-144">På sidan **Definiera inställningar för extern delning och enhetsåtkomst** väljer du **Styra extern delning från etiketterade SharePoint-webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="74867-144">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
14. <span data-ttu-id="74867-145">Under **Innehåll kan delas med** väljer du **Nya och befintliga gäster** om du vill tillåta gäståtkomst eller **Endast personer i organisationen**.</span><span class="sxs-lookup"><span data-stu-id="74867-145">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
15. <span data-ttu-id="74867-146">Under **Åtkomst från ohanterade enheter** väljer du **Tillåt begränsad åtkomst via webben**.</span><span class="sxs-lookup"><span data-stu-id="74867-146">Under **Access from unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
16. <span data-ttu-id="74867-147">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74867-147">Click **Next**.</span></span>
17. <span data-ttu-id="74867-148">På sidan **Auto-etiketting för databaskolumner** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="74867-148">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
18. <span data-ttu-id="74867-149">Klicka på **Skapa etikett** och sedan på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="74867-149">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="74867-150">När du har skapat en etikett måste du publicera den till de användare som ska använda den.</span><span class="sxs-lookup"><span data-stu-id="74867-150">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="74867-151">För känsligt skydd gör vi etiketterna tillgängliga för alla användare.</span><span class="sxs-lookup"><span data-stu-id="74867-151">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="74867-152">Du publicerar etiketten i Microsoft 365 Efterlevnadscenter på fliken **Etikettprinciper** på sidan **Informationskydd**.</span><span class="sxs-lookup"><span data-stu-id="74867-152">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="74867-153">Om du har en befintlig princip som gäller för alla användare kan du lägga till den här etiketten i principen.</span><span class="sxs-lookup"><span data-stu-id="74867-153">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="74867-154">Om du behöver skapa en ny princip kan du läsa [Publicera känsliga etiketter genom att skapa en etikettpolicy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="74867-154">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="74867-155">Skapa ett team</span><span class="sxs-lookup"><span data-stu-id="74867-155">Create a team</span></span>

<span data-ttu-id="74867-156">Ytterligare konfiguration av det känsliga scenariot görs på SharePoint-webbplatsen som är kopplad till teamet, så nästa steg är att skapa ett team.</span><span class="sxs-lookup"><span data-stu-id="74867-156">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="74867-157">Skapa en team för känslig information</span><span class="sxs-lookup"><span data-stu-id="74867-157">To create a team for sensitive information</span></span>
1. <span data-ttu-id="74867-158">I Teams klickar du på **Teams** till vänster i programmet och sedan på **gå med i eller skapa en teams** längst ned i grupplistan.</span><span class="sxs-lookup"><span data-stu-id="74867-158">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="74867-159">Klicka på **Skapa team** (första kortet, övre vänstra hörnet).</span><span class="sxs-lookup"><span data-stu-id="74867-159">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="74867-160">Välj **Skapa ett team från början**.</span><span class="sxs-lookup"><span data-stu-id="74867-160">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="74867-161">I listan **känslighet** väljer du **känslighetsetiketten** som du precis har skapat.</span><span class="sxs-lookup"><span data-stu-id="74867-161">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="74867-162">Under **Sekretess** klickar du på **Privat**.</span><span class="sxs-lookup"><span data-stu-id="74867-162">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="74867-163">Skriv in ett namn på teamet och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="74867-163">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="74867-164">Lägg till användare i teamet och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="74867-164">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="74867-165">Inställningar för privata kanaler</span><span class="sxs-lookup"><span data-stu-id="74867-165">Private channel settings</span></span>

<span data-ttu-id="74867-166">På denna nivå begränsar vi skapandet av privata kanaler till teamägare.</span><span class="sxs-lookup"><span data-stu-id="74867-166">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="74867-167">För att begränsa skapandet av en privat kanal</span><span class="sxs-lookup"><span data-stu-id="74867-167">To restrict private channel creation</span></span>
1. <span data-ttu-id="74867-168">Klicka på **Fler alternativ** i teamet och klicka sedan på **Hantera team**.</span><span class="sxs-lookup"><span data-stu-id="74867-168">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="74867-169">På fliken **Inställningar**, expandera **medlemsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="74867-169">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="74867-170">Avmarkera kryssrutan **Tillåt att medlemmar skapar privata kanaler**.</span><span class="sxs-lookup"><span data-stu-id="74867-170">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="74867-171">Du kan också använda [teamprinciper](/MicrosoftTeams/teams-policies) för att styra vem som kan skapa privata kanaler.</span><span class="sxs-lookup"><span data-stu-id="74867-171">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="74867-172">SharePoint-inställningar</span><span class="sxs-lookup"><span data-stu-id="74867-172">SharePoint settings</span></span>

<span data-ttu-id="74867-173">Varje gång du skapar ett ny team med känslighetsetiketten finns det två steg att utföra i SharePoint:</span><span class="sxs-lookup"><span data-stu-id="74867-173">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="74867-174">Uppdatera inställningarna för gästdelning för webbplatsen i SharePoint Online Administrationscenter för att uppdatera standard delningslänken till *Vissa personer*.</span><span class="sxs-lookup"><span data-stu-id="74867-174">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="74867-175">Uppdatera inställningarna för webbplatsdelning på själva webbplatsen och förhindra att medlemmar kan webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="74867-175">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="74867-176">Webbplats inställningar för den standard delningslänken</span><span class="sxs-lookup"><span data-stu-id="74867-176">Site default sharing link settings</span></span>

<span data-ttu-id="74867-177">Uppdatera webbplats standardinställningar för typ av delningslänk</span><span class="sxs-lookup"><span data-stu-id="74867-177">To update the site default sharing link type</span></span>

1. <span data-ttu-id="74867-178">Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="74867-178">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="74867-179">Under **Webbplatser** klickar du på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="74867-179">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="74867-180">Klicka på den webbplats som är kopplad till teamet.</span><span class="sxs-lookup"><span data-stu-id="74867-180">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="74867-181">Klicka på **Redigera** under **Extern delning** på fliken **Principer**.</span><span class="sxs-lookup"><span data-stu-id="74867-181">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="74867-182">Avmarkera kryssrutan **Samma som organisationsnivå** under standardtyp av delningslänk och välj **Vissa personer 8endast de personer som användaren anger**.</span><span class="sxs-lookup"><span data-stu-id="74867-182">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
6. <span data-ttu-id="74867-183">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="74867-183">Click **Save**.</span></span>

<span data-ttu-id="74867-184">Om du vill skapa skript som en del av din team skapande process kan du använda [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) med `-DefaultSharingLinkType Direct` parametern för att ändra standard delningslänken för *Vissa personer*.</span><span class="sxs-lookup"><span data-stu-id="74867-184">If you want to script this as part of your team creation process, you can use [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) with the `-DefaultSharingLinkType Direct` parameter to change the default sharing link to *Specific people*.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="74867-185">Privata kanaler</span><span class="sxs-lookup"><span data-stu-id="74867-185">Private channels</span></span>

<span data-ttu-id="74867-186">Om du lägger till privata kanaler i teamet skapas en ny SharePoint-webbplats med standard delningsinställningar.</span><span class="sxs-lookup"><span data-stu-id="74867-186">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="74867-187">De här webbplatserna visas inte i SharePoint Online Administrationscenter. Du måste därför använda Windows PowerShell-cmdleten set-SPOSite för att uppdatera inställningarna för gästdelning.</span><span class="sxs-lookup"><span data-stu-id="74867-187">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="74867-188">Inställningar för webbplatsdelning</span><span class="sxs-lookup"><span data-stu-id="74867-188">Site sharing settings</span></span>

<span data-ttu-id="74867-189">För att se till att SharePoint-webbplatsen inte delas med personer som inte är medlemmar i teamet kan vi begränsa delning till ägare.</span><span class="sxs-lookup"><span data-stu-id="74867-189">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="74867-190">Konfigurera webbplatsdelning endast för ägare</span><span class="sxs-lookup"><span data-stu-id="74867-190">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="74867-191">Gå till fliken **Allmänt** i teamet som du vill uppdatera i Teams.</span><span class="sxs-lookup"><span data-stu-id="74867-191">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="74867-192">I verktygsfältet för teamet klickar du på **Filer**.</span><span class="sxs-lookup"><span data-stu-id="74867-192">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="74867-193">Klicka på ellipsen och sedan på **Öppna i SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="74867-193">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="74867-194">Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="74867-194">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="74867-195">I fönstret **Webbplatsbehörigheter**, under **webbplatsdelning**, klickar du på **Ändra hur medlemmar kan dela**.</span><span class="sxs-lookup"><span data-stu-id="74867-195">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="74867-196">Under **Delningsbehörigheter** väljer du **Webbplatsägare och medlemmar, och personer med redigeringsbehörighet kan dela filer och mappar, men endast webbplatsägare kan dela webbplatsen** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="74867-196">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="74867-197">Se även</span><span class="sxs-lookup"><span data-stu-id="74867-197">See Also</span></span>

[<span data-ttu-id="74867-198">Skapa och konfigurera känslighetsetiketter och deras principer</span><span class="sxs-lookup"><span data-stu-id="74867-198">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
