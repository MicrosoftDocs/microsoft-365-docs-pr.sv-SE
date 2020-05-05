---
title: Konfigurera team med skydd för känslig data
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
description: Lär dig hur du distribuerar team med skydd för känslig data.
ms.openlocfilehash: 6c3d79e212a1a0333a7262b72ae0f1db8597096f
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003414"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="639d8-103">Konfigurera team med skydd för känslig data</span><span class="sxs-lookup"><span data-stu-id="639d8-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="639d8-104">I den här artikeln ska vi titta närmare på hur du konfigurerar ett team för en känslig skyddsnivå.</span><span class="sxs-lookup"><span data-stu-id="639d8-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="639d8-105">Kontrollera att du har slutfört stegen i [distribuera teams med grundskydd](configure-teams-baseline-protection.md) innan du följer anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="639d8-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="639d8-106">Den känsliga nivån erbjuder följande ytterligare skydd över grundnivån:</span><span class="sxs-lookup"><span data-stu-id="639d8-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="639d8-107">En känslighetsetikett för teamet som gör att du kan aktivera eller inaktivera gästdelning och begränsar åtkomst till SharePoint-innehåll till webben endast för ostyrda enheter.</span><span class="sxs-lookup"><span data-stu-id="639d8-107">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices.</span></span> <span data-ttu-id="639d8-108">Du kan också använda den här etiketten för att klassificera filer.</span><span class="sxs-lookup"><span data-stu-id="639d8-108">This label can also be used to classify files.</span></span>
- <span data-ttu-id="639d8-109">En mer restriktiv länktyp för standarddelning</span><span class="sxs-lookup"><span data-stu-id="639d8-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="639d8-110">Endast teamägare kan skapa privata kanaler.</span><span class="sxs-lookup"><span data-stu-id="639d8-110">Only team owners can create private channels.</span></span>

## <a name="guest-sharing"></a><span data-ttu-id="639d8-111">Gästdelning</span><span class="sxs-lookup"><span data-stu-id="639d8-111">Guest sharing</span></span>

<span data-ttu-id="639d8-112">Beroende på företagets natur kan du kanske inte aktivera gästdelning för team som innehåller känsliga data.</span><span class="sxs-lookup"><span data-stu-id="639d8-112">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="639d8-113">Om du tänker samarbeta med personer utanför organisationen i teamet, rekommenderar vi att du aktiverar gästdelning.</span><span class="sxs-lookup"><span data-stu-id="639d8-113">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="639d8-114">Microsoft 365 innehåller en mängd olika funktioner för säkerhet och efterlevnad som hjälper dig att dela känsligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="639d8-114">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="639d8-115">Det här är vanligtvis ett säkrare alternativ än att skicka innehåll direkt till personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="639d8-115">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="639d8-116">Information om hur du delar med gäster säkert finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="639d8-116">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="639d8-117">Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="639d8-117">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="639d8-118">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="639d8-118">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="639d8-119">För att tillåta eller blockera gästdelning använder vi en kombination av känslighetsetiketter för teamet och delning på webbplats nivå för den associerade SharePoint-webbplatsen, som vi ser senare.</span><span class="sxs-lookup"><span data-stu-id="639d8-119">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="639d8-120">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="639d8-120">Sensitivity labels</span></span>

<span data-ttu-id="639d8-121">För den känsliga skyddsnivån använder vi en känslighetsetikett för att klassificera teamet.</span><span class="sxs-lookup"><span data-stu-id="639d8-121">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="639d8-122">Den här etiketten kan också användas för att klassificera enskilda filer i detta eller andra team, eller på andra filplatser som SharePoint eller OneDrive.</span><span class="sxs-lookup"><span data-stu-id="639d8-122">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="639d8-123">Som ett första steg måste du aktivera känslighetsetiketter för Teams.</span><span class="sxs-lookup"><span data-stu-id="639d8-123">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="639d8-124">Mer information finns i [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Office 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="639d8-124">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) for details.</span></span>

<span data-ttu-id="639d8-125">Om du redan har känslighetsetiketter distribuerade i din organisation, bör du överväga hur denna etikett passar med din övergripande etikettstrategi.</span><span class="sxs-lookup"><span data-stu-id="639d8-125">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="639d8-126">Du kan ändra namn eller inställningar om det behövs för att uppfylla organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="639d8-126">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="639d8-127">När du har aktiverat känslighetsetiketter för Teams är nästa steg att skapa etiketten.</span><span class="sxs-lookup"><span data-stu-id="639d8-127">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="639d8-128">Att skapa en känslighetsetikett</span><span class="sxs-lookup"><span data-stu-id="639d8-128">To create a sensitivity label</span></span>
1. <span data-ttu-id="639d8-129">Öppna [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="639d8-129">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="639d8-130">Under **Lösningar**klickar du på **Informationsskydd**.</span><span class="sxs-lookup"><span data-stu-id="639d8-130">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="639d8-131">Klicka på **Skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="639d8-131">Click **Create a label**.</span></span>
4. <span data-ttu-id="639d8-132">Namnge etiketten.</span><span class="sxs-lookup"><span data-stu-id="639d8-132">Give the label a name.</span></span> <span data-ttu-id="639d8-133">Vi föreslår **känslig**, men du kan välja ett annat namn om denna redan används.</span><span class="sxs-lookup"><span data-stu-id="639d8-133">We suggest **sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="639d8-134">Lägg till ett knapptips och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="639d8-134">Add a tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="639d8-135">På sidan **kryptering** klickar du på **nästa**.</span><span class="sxs-lookup"><span data-stu-id="639d8-135">On the **Encryption** page, click **Next**.</span></span>
7. <span data-ttu-id="639d8-136">Om du vill lägga till ett sidhuvud, en sidfot eller en vattenstämpel automatiskt i filer som klassificeras med den här etiketten går du till sidan **Markering av innehåll**.</span><span class="sxs-lookup"><span data-stu-id="639d8-136">On the **Content marking** page, turn on content marking if you want to automatically add a header, footer, or watermark to files that are classified with this label.</span></span>
8. <span data-ttu-id="639d8-137">På sidan **Inställningar för webbplatser och grupper** ställer du **inställningar för webbplatser och grupper** till **På**.</span><span class="sxs-lookup"><span data-stu-id="639d8-137">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
9. <span data-ttu-id="639d8-138">I listrutan **Sekretess för gruppanslutna teamwebbplatser i Office 365** väljer du **Privat – endast användare kan komma åt webbplatsen**.</span><span class="sxs-lookup"><span data-stu-id="639d8-138">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
10. <span data-ttu-id="639d8-139">Om du vill tillåta gäståtkomst markerar du kryssrutan **Låt gruppägarna för Office 365 lägga till personer utanför organisationen i gruppen**.</span><span class="sxs-lookup"><span data-stu-id="639d8-139">If you want to allow guest access, select the **Let Office 365 group owners add people outside the organization to the group** check box.</span></span> 
11. <span data-ttu-id="639d8-140">Under **ohanterade enheter**väljer du **tillåta begränsad åtkomst**via webben.</span><span class="sxs-lookup"><span data-stu-id="639d8-140">Under **Unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
12. <span data-ttu-id="639d8-141">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="639d8-141">Click **Next**.</span></span>
13. <span data-ttu-id="639d8-142">På sidan **Auto-etiketting för Office-program** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="639d8-142">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
14. <span data-ttu-id="639d8-143">Klicka på **Skicka** och klicka sedan **Klart**.</span><span class="sxs-lookup"><span data-stu-id="639d8-143">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="639d8-144">När du har skapat en etikett måste du publicera den till de användare som ska använda den.</span><span class="sxs-lookup"><span data-stu-id="639d8-144">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="639d8-145">För känsligt skydd gör vi etiketterna tillgängliga för alla användare.</span><span class="sxs-lookup"><span data-stu-id="639d8-145">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="639d8-146">Du publicerar etiketten i Microsoft 365 Efterlevnadscenter på fliken **Etikettprinciper** på sidan **Informationskydd**.</span><span class="sxs-lookup"><span data-stu-id="639d8-146">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="639d8-147">Om du har en befintlig princip som gäller för alla användare kan du lägga till den här etiketten i principen.</span><span class="sxs-lookup"><span data-stu-id="639d8-147">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="639d8-148">Om du behöver skapa en ny princip kan du läsa [Publicera känsliga etiketter genom att skapa en etikettpolicy](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="639d8-148">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="639d8-149">Skapa ett team</span><span class="sxs-lookup"><span data-stu-id="639d8-149">Create a team</span></span>

<span data-ttu-id="639d8-150">Ytterligare konfiguration av det känsliga scenariot görs på SharePoint-webbplatsen som är kopplad till teamet, så nästa steg är att skapa ett team.</span><span class="sxs-lookup"><span data-stu-id="639d8-150">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="639d8-151">Skapa en team för känslig information</span><span class="sxs-lookup"><span data-stu-id="639d8-151">To create a team for sensitive information</span></span>
1. <span data-ttu-id="639d8-152">I Teams klickar du på **Teams** till vänster i programmet och sedan på **gå med i eller skapa en teams** längst ned i grupplistan.</span><span class="sxs-lookup"><span data-stu-id="639d8-152">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="639d8-153">Klicka på **Skapa team** (första kortet, övre vänstra hörnet).</span><span class="sxs-lookup"><span data-stu-id="639d8-153">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="639d8-154">Välj **Skapa ett team från början**.</span><span class="sxs-lookup"><span data-stu-id="639d8-154">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="639d8-155">I listan **känslighet** väljer du **känslighetsetiketten** som du precis har skapat.</span><span class="sxs-lookup"><span data-stu-id="639d8-155">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="639d8-156">Under **Sekretess**klickar du på **Privat**.</span><span class="sxs-lookup"><span data-stu-id="639d8-156">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="639d8-157">Skriv in ett namn på teamet och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="639d8-157">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="639d8-158">Lägg till användare i teamet och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="639d8-158">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="639d8-159">Inställningar för privata kanaler</span><span class="sxs-lookup"><span data-stu-id="639d8-159">Private channel settings</span></span>

<span data-ttu-id="639d8-160">På denna nivå begränsar vi skapandet av privata kanaler till teamägare.</span><span class="sxs-lookup"><span data-stu-id="639d8-160">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="639d8-161">För att begränsa skapandet av en privat kanal</span><span class="sxs-lookup"><span data-stu-id="639d8-161">To restrict private channel creation</span></span>
1. <span data-ttu-id="639d8-162">Klicka på **Fler alternativ**i teamet och klicka sedan på **Hantera team**.</span><span class="sxs-lookup"><span data-stu-id="639d8-162">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="639d8-163">På fliken **Inställningar**, expandera **medlemsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="639d8-163">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="639d8-164">Avmarkera kryssrutan **Tillåt att medlemmar skapar privata kanaler**.</span><span class="sxs-lookup"><span data-stu-id="639d8-164">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="639d8-165">Du kan också använda [teamprinciper](https://docs.microsoft.com/MicrosoftTeams/teams-policies) för att styra vem som kan skapa privata kanaler.</span><span class="sxs-lookup"><span data-stu-id="639d8-165">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="639d8-166">SharePoint-inställningar</span><span class="sxs-lookup"><span data-stu-id="639d8-166">SharePoint settings</span></span>

<span data-ttu-id="639d8-167">Varje gång du skapar ett ny team med känslighetsetiketten finns det två steg att utföra i SharePoint:</span><span class="sxs-lookup"><span data-stu-id="639d8-167">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="639d8-168">Uppdatera inställningarna för gästdelning för webbplatsen i SharePoint Online Administrationscenter för att matcha det du valde när du skapade etiketten och uppdatera sedan standard delningslänken till *Vissa personer*.</span><span class="sxs-lookup"><span data-stu-id="639d8-168">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="639d8-169">Uppdatera inställningarna för webbplatsdelning på själva webbplatsen och förhindra att medlemmar kan webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="639d8-169">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-guest-sharing-settings"></a><span data-ttu-id="639d8-170">Inställningar för gästdelning av webbplatsen</span><span class="sxs-lookup"><span data-stu-id="639d8-170">Site guest sharing settings</span></span>

<span data-ttu-id="639d8-171">Den inställning för gästdelning som du valde när du skapade etiketten (som bara påverkar teammedlemskap) ska matcha inställningarna för gästdelning för den associerade SharePoint-webbplatsen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="639d8-171">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="639d8-172">Etikettinställning</span><span class="sxs-lookup"><span data-stu-id="639d8-172">Label setting</span></span>|<span data-ttu-id="639d8-173">Inställning för SharePoint-webbplats</span><span class="sxs-lookup"><span data-stu-id="639d8-173">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="639d8-174">**Låt Office 365-gruppägare lägga till personer utanför organisationen i gruppen** markerad</span><span class="sxs-lookup"><span data-stu-id="639d8-174">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="639d8-175">**Nya och befintliga gäster** (standard för nya grupper)</span><span class="sxs-lookup"><span data-stu-id="639d8-175">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="639d8-176">**Låt Office 365-gruppägare lägga till personer utanför organisationen i gruppen** inte markerad</span><span class="sxs-lookup"><span data-stu-id="639d8-176">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="639d8-177">**Endast personer i organisationen**</span><span class="sxs-lookup"><span data-stu-id="639d8-177">**Only people in your organization**</span></span>|

<span data-ttu-id="639d8-178">Uppdatera webbplatsinställningar</span><span class="sxs-lookup"><span data-stu-id="639d8-178">To update site settings</span></span>
1. <span data-ttu-id="639d8-179">Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="639d8-179">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="639d8-180">Under **Webbplatser**klickar du på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="639d8-180">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="639d8-181">Klicka på den webbplats som är kopplad till teamet.</span><span class="sxs-lookup"><span data-stu-id="639d8-181">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="639d8-182">Klicka på **Redigera** under **Extern delning** på fliken **Principer**.</span><span class="sxs-lookup"><span data-stu-id="639d8-182">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="639d8-183">Om du tillät gästdelning när du skapade känslighetsetiketten ska du kontrollera att **Nya och befintligt gäster** har markerats.</span><span class="sxs-lookup"><span data-stu-id="639d8-183">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="639d8-184">Om du inte tillåter delning när du skapade etiketten väljer du **Bara personer i organisationen**.</span><span class="sxs-lookup"><span data-stu-id="639d8-184">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="639d8-185">Avmarkera kryssrutan **Samma som organisationsnivå** under standardtyp av delningslänk och välj **Vissa personer 8endast de personer som användaren anger**.</span><span class="sxs-lookup"><span data-stu-id="639d8-185">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
7. <span data-ttu-id="639d8-186">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="639d8-186">Click **Save**.</span></span>

<span data-ttu-id="639d8-187">Om du vill skapa ett skript som en del av processen för att skapa ett team kan du använda [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) med följande parametrar:</span><span class="sxs-lookup"><span data-stu-id="639d8-187">If you want to script this as part of your team creation process, you can use [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) with the following parameters:</span></span>

- <span data-ttu-id="639d8-188">`-SharingCapability Disabled` Inaktivera gästdelning (det är aktiverat som standard)</span><span class="sxs-lookup"><span data-stu-id="639d8-188">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="639d8-189">`-DefaultSharingLinkType Internal` ändra standard delningslänk till *Vissa personer*</span><span class="sxs-lookup"><span data-stu-id="639d8-189">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

#### <a name="private-channels"></a><span data-ttu-id="639d8-190">Privata kanaler</span><span class="sxs-lookup"><span data-stu-id="639d8-190">Private channels</span></span>

<span data-ttu-id="639d8-191">Om du lägger till privata kanaler i teamet skapas en ny SharePoint-webbplats med standard delningsinställningar.</span><span class="sxs-lookup"><span data-stu-id="639d8-191">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="639d8-192">De här webbplatserna visas inte i SharePoint Online Administrationscenter. Du måste därför använda Windows PowerShell-cmdleten set-SPOSite för att uppdatera inställningarna för gästdelning.</span><span class="sxs-lookup"><span data-stu-id="639d8-192">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="639d8-193">Inställningar för webbplatsdelning</span><span class="sxs-lookup"><span data-stu-id="639d8-193">Site sharing settings</span></span>

<span data-ttu-id="639d8-194">För att se till att SharePoint-webbplatsen inte delas med personer som inte är medlemmar i teamet kan vi begränsa delning till ägare.</span><span class="sxs-lookup"><span data-stu-id="639d8-194">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="639d8-195">Konfigurera webbplatsdelning endast för ägare</span><span class="sxs-lookup"><span data-stu-id="639d8-195">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="639d8-196">Gå till fliken **Allmänt** i teamet som du vill uppdatera i Teams.</span><span class="sxs-lookup"><span data-stu-id="639d8-196">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="639d8-197">I verktygsfältet för teamet klickar du på **Filer**.</span><span class="sxs-lookup"><span data-stu-id="639d8-197">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="639d8-198">Klicka på ellipsen och sedan på **Öppna i SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="639d8-198">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="639d8-199">Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="639d8-199">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="639d8-200">I fönstret Webbplatsbehörigheter under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="639d8-200">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="639d8-201">Under **Delningsbehörigheter** väljer du **Webbplatsägare och medlemmar, och personer med redigeringsbehörighet kan dela filer och mappar, men endast webbplatsägare kan dela webbplatsen** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="639d8-201">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="639d8-202">Se även</span><span class="sxs-lookup"><span data-stu-id="639d8-202">See Also</span></span>

[<span data-ttu-id="639d8-203">Skapa och konfigurera känslighetsetiketter och deras principer</span><span class="sxs-lookup"><span data-stu-id="639d8-203">Create and configure sensitivity labels and their policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)


