---
title: Konfigurera team med skydd för mycket känslig data
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
description: Lär dig hur du distribuerar team med skydd för mycket känslig data.
ms.openlocfilehash: 3e98b1a52e698d52eba16d4296c062d7347759d0
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788361"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a><span data-ttu-id="7bb48-103">Konfigurera team med skydd för mycket känslig data</span><span class="sxs-lookup"><span data-stu-id="7bb48-103">Configure teams with protection for highly sensitive data</span></span>

<span data-ttu-id="7bb48-104">I den här artikeln ska vi titta närmare på hur du konfigurerar ett team för en mycket känslig skyddsnivå.</span><span class="sxs-lookup"><span data-stu-id="7bb48-104">In this article, we look at setting up a team for a highly sensitive level of protection.</span></span> <span data-ttu-id="7bb48-105">Kontrollera att du har slutfört stegen i [Distribuera teams med grundskydd](configure-teams-baseline-protection.md) innan du följer anvisningarna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="7bb48-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span>

<span data-ttu-id="7bb48-106">För den här skyddsnivån skapar vi en känslighetsetikett som kan användas i hela organisationen för mycket känsliga team och filer.</span><span class="sxs-lookup"><span data-stu-id="7bb48-106">For this tier of protection, we create a sensitivity label that can be used across your organization for highly sensitive teams and files.</span></span> <span data-ttu-id="7bb48-107">Endast medlemmar i din organisation och gäster som du har angett kan dekryptera filer som använder den här etiketten.</span><span class="sxs-lookup"><span data-stu-id="7bb48-107">Only members of your organization and guests that you have specified will be able to decrypt files that use this label.</span></span> <span data-ttu-id="7bb48-108">Om du behöver isolera behörigheter ytterligare så att endast medlemmar i ett angivet team kan dekryptera filer kan du läsa [Distribuera ett team med säkerhetsisolering](secure-teams-security-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="7bb48-108">If you need to further isolate permissions so that only members of a specific team can decrypt files, see  [Deploy a team with security isolation](secure-teams-security-isolation.md).</span></span>

<span data-ttu-id="7bb48-109">Den mycket känsliga nivån erbjuder följande ytterligare skydd över grundnivån:</span><span class="sxs-lookup"><span data-stu-id="7bb48-109">The highly sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="7bb48-p103">En känslighetsetikett för teamet som gör att du kan aktivera eller inaktivera gästdelning samt begränsar åtkomst till SharePoint-innehåll för ohanterade enheter. Etiketten kan även användas för att klassificera och kryptera filer.</span><span class="sxs-lookup"><span data-stu-id="7bb48-p103">A sensitivity label for the team that allows you to turn guest sharing on or off and blocks access to SharePoint content for unmanaged devices. This label can also be used to classify and encrypt files.</span></span>
- <span data-ttu-id="7bb48-112">En mer restriktiv länktyp för standarddelning</span><span class="sxs-lookup"><span data-stu-id="7bb48-112">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="7bb48-113">Endast teamägare kan skapa privata kanaler.</span><span class="sxs-lookup"><span data-stu-id="7bb48-113">Only team owners can create private channels.</span></span>
- <span data-ttu-id="7bb48-114">Åtkomstförfrågningar för den associerade SharePoint-webbplatsen är inaktiverade.</span><span class="sxs-lookup"><span data-stu-id="7bb48-114">Access requests for the associated SharePoint site are turned off.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="7bb48-115">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="7bb48-115">Video demonstration</span></span>

<span data-ttu-id="7bb48-116">Titta på den här videon för en genomgång av procedurerna som beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="7bb48-116">Watch this video for a walkthrough of the procedures described in this article.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NzI7]

## <a name="guest-sharing"></a><span data-ttu-id="7bb48-117">Gästdelning</span><span class="sxs-lookup"><span data-stu-id="7bb48-117">Guest sharing</span></span>

<span data-ttu-id="7bb48-118">Beroende på företagets natur kan du kanske inte aktivera gästdelning för team som innehåller mycket känslig data.</span><span class="sxs-lookup"><span data-stu-id="7bb48-118">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain highly sensitive data.</span></span> <span data-ttu-id="7bb48-119">Om du tänker samarbeta med personer utanför organisationen i teamet, rekommenderar vi att du aktiverar gästdelning.</span><span class="sxs-lookup"><span data-stu-id="7bb48-119">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="7bb48-120">Microsoft 365 innehåller en mängd olika funktioner för säkerhet och efterlevnad som hjälper dig att dela känsligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="7bb48-120">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="7bb48-121">Det här är vanligtvis ett säkrare alternativ än att skicka innehåll direkt till personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="7bb48-121">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="7bb48-122">Information om hur du delar med gäster säkert finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="7bb48-122">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="7bb48-123">Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="7bb48-123">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="7bb48-124">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="7bb48-124">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="7bb48-125">För att tillåta eller blockera gästdelning använder vi en kombination av känslighetsetiketter för teamet och delning på webbplats nivå för den associerade SharePoint-webbplatsen, som vi ser senare.</span><span class="sxs-lookup"><span data-stu-id="7bb48-125">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="7bb48-126">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="7bb48-126">Sensitivity labels</span></span>

<span data-ttu-id="7bb48-127">För den mycket känsliga skyddsnivån använder vi en känslighetsetikett för att klassificera teamet.</span><span class="sxs-lookup"><span data-stu-id="7bb48-127">For the highly sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="7bb48-128">Den här etiketten kan också användas för att klassificera och kryptera enskilda filer i detta eller andra team eller på andra filplatser som SharePoint eller OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7bb48-128">This label can also be used to classify and encrypt individual files in this or other teams or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="7bb48-129">Som ett första steg måste du aktivera känslighetsetiketter för Teams.</span><span class="sxs-lookup"><span data-stu-id="7bb48-129">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="7bb48-130">Mer information finns i [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Office 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="7bb48-130">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="7bb48-131">Om du redan har känslighetsetiketter distribuerade i din organisation, bör du överväga hur denna etikett passar med din övergripande etikettstrategi.</span><span class="sxs-lookup"><span data-stu-id="7bb48-131">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="7bb48-132">Du kan ändra namn eller inställningar om det behövs för att uppfylla organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="7bb48-132">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="7bb48-133">När du har aktiverat känslighetsetiketter för Teams är nästa steg att skapa etiketten.</span><span class="sxs-lookup"><span data-stu-id="7bb48-133">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="7bb48-134">Att skapa en känslighetsetikett</span><span class="sxs-lookup"><span data-stu-id="7bb48-134">To create a sensitivity label</span></span>
1. <span data-ttu-id="7bb48-135">Öppna [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7bb48-135">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="7bb48-136">Under **Lösningar** klickar du på **Informationsskydd**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-136">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="7bb48-137">Klicka på **Skapa en etikett**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-137">Click **Create a label**.</span></span>
4. <span data-ttu-id="7bb48-138">Namnge etiketten.</span><span class="sxs-lookup"><span data-stu-id="7bb48-138">Give the label a name.</span></span> <span data-ttu-id="7bb48-139">Vi föreslår **Mycket känslig**, men du kan välja ett annat namn om denna redan används.</span><span class="sxs-lookup"><span data-stu-id="7bb48-139">We suggest **Highly sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="7bb48-140">Lägg till ett visningsnamn och en beskrivning och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-140">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="7bb48-141">På sidan **Definiera omfång för etikett** väljer du **filer och e-postmeddelanden** samt **grupper och webbplatser** och klickar på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-141">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="7bb48-142">På sidan **Välj säkerhetsinställningar för filer och e-postmeddelanden** väljer du **Kryptera filer och e-postmeddelande** och klickar på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-142">On the **Choose protection settings for files and emails** page, select **Encrypt files and emails**, and then click **Next**.</span></span>
8. <span data-ttu-id="7bb48-143">På sidan **Kryptering** väljer du **Konfigurera krypteringsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-143">On the **Encryption** page, choose **Configure encryption settings**.</span></span>
9. <span data-ttu-id="7bb48-144">Under **Tilldela behörigheter för vissa användare och grupper** klickar du på **Tilldela behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-144">Under **Assign permissions to specific users and groups**, click **Assign permissions**.</span></span>
10. <span data-ttu-id="7bb48-145">Klicka på **Lägga till alla användare och grupper i organisationen**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-145">Click **Add all users and groups in your organization**.</span></span>
11. <span data-ttu-id="7bb48-146">Om det finns gästanvändare som ska ha behörighet att dekryptera filer klickar du på **Lägga till användare eller grupper** och lägger till dem.</span><span class="sxs-lookup"><span data-stu-id="7bb48-146">If there are guests who should have permissions to decrypt files, click **Add users or groups** and add them.</span></span>
12.  <span data-ttu-id="7bb48-147">Klicka på **Spara** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-147">Click **Save**, and then click **Next**.</span></span>
13. <span data-ttu-id="7bb48-148">På sidan *Auto-etiketting för filer och e-postmeddelanden*\* klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-148">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
14. <span data-ttu-id="7bb48-149">På sidan **Definiera säkerhetsinställningar för grupper och webbplatser** väljer du **Inställningar för sekretess och extern användaråtkomst** samt **Inställningar för enhetsåtkomst och extern delning** och klickar på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-149">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
15. <span data-ttu-id="7bb48-150">Välj alternativet **Privat** under **Sekretess** på sidan **Definiera inställningar för sekretess och extern användaråtkomst**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-150">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
16. <span data-ttu-id="7bb48-151">Om du vill tillåta gäståtkomst väljer du **Låt Microsoft 365-gruppägare lägga till personer utanför organisationen i gruppen som gäster** under **Extern användaråtkomst**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-151">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
17. <span data-ttu-id="7bb48-152">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-152">Click **Next**.</span></span>
18. <span data-ttu-id="7bb48-153">På sidan **Definiera inställningar för extern delning och enhetsåtkomst** väljer du **Styra extern delning från etiketterade SharePoint-webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-153">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
19. <span data-ttu-id="7bb48-154">Under **Innehåll kan delas med** väljer du **Nya och befintliga gäster** om du vill tillåta gäståtkomst eller **Endast personer i organisationen**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-154">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
20. <span data-ttu-id="7bb48-155">Under **Åtkomst från ohanterade enheter** väljer du **Blockera åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-155">Under **Access from unmanaged devices**, choose **Block access**.</span></span> <span data-ttu-id="7bb48-156">(Om du tillåter gäster och de har inte hanterade enheter vill du kanske välja **Tillåt begränsad åtkomst på webben**.)</span><span class="sxs-lookup"><span data-stu-id="7bb48-156">(If you're allowing guests and they don't have managed devices, you may want to choose **Allow limited, web-only access**.)</span></span>
21. <span data-ttu-id="7bb48-157">Klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-157">Click **Next**.</span></span>
22. <span data-ttu-id="7bb48-158">På sidan **Auto-etiketting för databaskolumner** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-158">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
23. <span data-ttu-id="7bb48-159">Klicka på **Skapa etikett** och sedan på **Klart**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-159">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="7bb48-160">När du har skapat en etikett måste du publicera den till de användare som ska använda den.</span><span class="sxs-lookup"><span data-stu-id="7bb48-160">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="7bb48-161">För känsligt skydd gör vi etiketterna tillgängliga för alla användare.</span><span class="sxs-lookup"><span data-stu-id="7bb48-161">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="7bb48-162">Du publicerar etiketten i Microsoft 365 Efterlevnadscenter på fliken **Etikettprinciper** på sidan **Informationskydd**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-162">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="7bb48-163">Om du har en befintlig princip som gäller för alla användare kan du lägga till den här etiketten i principen.</span><span class="sxs-lookup"><span data-stu-id="7bb48-163">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="7bb48-164">Om du behöver skapa en ny princip kan du läsa [Publicera känsliga etiketter genom att skapa en etikettpolicy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="7bb48-164">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="7bb48-165">Skapa ett team</span><span class="sxs-lookup"><span data-stu-id="7bb48-165">Create a team</span></span>

<span data-ttu-id="7bb48-166">Ytterligare konfiguration av det mycket känsliga scenariot görs på SharePoint-webbplatsen som är kopplad till teamet, så nästa steg är att skapa ett team.</span><span class="sxs-lookup"><span data-stu-id="7bb48-166">Further configuration of the highly sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="7bb48-167">Skapa en team för mycket känslig information</span><span class="sxs-lookup"><span data-stu-id="7bb48-167">To create a team for highly sensitive information</span></span>
1. <span data-ttu-id="7bb48-168">I Teams klickar du på **Teams** till vänster i programmet och sedan på **gå med i eller skapa en teams** längst ned i grupplistan.</span><span class="sxs-lookup"><span data-stu-id="7bb48-168">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="7bb48-169">Klicka på **Skapa team** (första kortet, övre vänstra hörnet).</span><span class="sxs-lookup"><span data-stu-id="7bb48-169">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="7bb48-170">Välj **Skapa ett team från början**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-170">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="7bb48-171">I listan **Känslighet** väljer du etiketten **Mycket känslig** som du precis har skapat.</span><span class="sxs-lookup"><span data-stu-id="7bb48-171">In the **Sensitivity** list, choose the **Highly sensitive** label that you just created.</span></span>
5. <span data-ttu-id="7bb48-172">Under **Sekretess** klickar du på **Privat**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-172">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="7bb48-173">Skriv in ett namn på teamet och klicka sedan på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-173">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="7bb48-174">Lägg till användare i teamet och klicka sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-174">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="7bb48-175">Inställningar för privata kanaler</span><span class="sxs-lookup"><span data-stu-id="7bb48-175">Private channel settings</span></span>

<span data-ttu-id="7bb48-176">På denna nivå begränsar vi skapandet av privata kanaler till teamägare.</span><span class="sxs-lookup"><span data-stu-id="7bb48-176">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="7bb48-177">För att begränsa skapandet av en privat kanal</span><span class="sxs-lookup"><span data-stu-id="7bb48-177">To restrict private channel creation</span></span>
1. <span data-ttu-id="7bb48-178">Klicka på **Fler alternativ** i teamet och klicka sedan på **Hantera team**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-178">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="7bb48-179">På fliken **Inställningar**, expandera **medlemsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-179">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="7bb48-180">Avmarkera kryssrutan **Tillåt att medlemmar skapar privata kanaler**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-180">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="7bb48-181">Du kan också använda [teamprinciper](/MicrosoftTeams/teams-policies) för att styra vem som kan skapa privata kanaler.</span><span class="sxs-lookup"><span data-stu-id="7bb48-181">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="7bb48-182">SharePoint-inställningar</span><span class="sxs-lookup"><span data-stu-id="7bb48-182">SharePoint settings</span></span>

<span data-ttu-id="7bb48-183">Varje gång du skapar ett ny team med etiketten mycket känslig finns det två steg att utföra i SharePoint:</span><span class="sxs-lookup"><span data-stu-id="7bb48-183">Each time you create a new team with the highly sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="7bb48-184">Uppdatera inställningarna för gästdelning för webbplatsen i SharePoint Online Administrationscenter för att uppdatera standard delningslänken till *Personer med befintlig åtkomst*.</span><span class="sxs-lookup"><span data-stu-id="7bb48-184">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="7bb48-185">Uppdatera inställningarna för webbplatsdelning på själva webbplatsen och förhindra att medlemmar kan dela filer, mappar eller webbplatsen och inaktivera åtkomstförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="7bb48-185">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="7bb48-186">Webbplats standardinställningar för delningslänk</span><span class="sxs-lookup"><span data-stu-id="7bb48-186">Site default sharing link settings</span></span>

<span data-ttu-id="7bb48-187">Uppdatera webbplats standardinställningar för typ av delningslänk</span><span class="sxs-lookup"><span data-stu-id="7bb48-187">To update the site default sharing link type</span></span>

1. <span data-ttu-id="7bb48-188">Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="7bb48-188">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="7bb48-189">Under **Webbplatser** klickar du på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-189">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="7bb48-190">Klicka på den webbplats som är kopplad till teamet.</span><span class="sxs-lookup"><span data-stu-id="7bb48-190">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="7bb48-191">Klicka på **Redigera** under **Extern delning** på fliken **Principer**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-191">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="7bb48-192">Avmarkera kryssrutan **Samma som organisationsnivå** under standardtyp av delningslänk och välj **Personer med befintlig åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-192">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
6. <span data-ttu-id="7bb48-193">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-193">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="7bb48-194">Privata kanaler</span><span class="sxs-lookup"><span data-stu-id="7bb48-194">Private channels</span></span>

<span data-ttu-id="7bb48-195">Om du lägger till privata kanaler i teamet skapas en ny SharePoint-webbplats med standard delningsinställningar.</span><span class="sxs-lookup"><span data-stu-id="7bb48-195">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="7bb48-196">De här webbplatserna visas inte i SharePoint Online Administrationscenter. Du måste därför använda Windows PowerShell-cmdleten set-SPOSite för att uppdatera inställningarna för gästdelning.</span><span class="sxs-lookup"><span data-stu-id="7bb48-196">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="7bb48-197">Inställningar för webbplatsdelning</span><span class="sxs-lookup"><span data-stu-id="7bb48-197">Site sharing settings</span></span>

<span data-ttu-id="7bb48-198">För att se till att SharePoint-webbplatsen inte delas med personer som inte är medlemmar i teamet kan vi begränsa delning till ägare.</span><span class="sxs-lookup"><span data-stu-id="7bb48-198">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="7bb48-199">Vi begränsar även delning av filer och mappar till teamägare.</span><span class="sxs-lookup"><span data-stu-id="7bb48-199">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="7bb48-200">På så sätt ser du till att ägare känner till när en fil delas med någon utanför teamet.</span><span class="sxs-lookup"><span data-stu-id="7bb48-200">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="7bb48-201">Konfigurera webbplatsdelning endast för ägare</span><span class="sxs-lookup"><span data-stu-id="7bb48-201">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="7bb48-202">Gå till fliken **Allmänt** i teamet som du vill uppdatera i Teams.</span><span class="sxs-lookup"><span data-stu-id="7bb48-202">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="7bb48-203">I verktygsfältet för teamet klickar du på **Filer**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-203">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="7bb48-204">Klicka på ellipsen och sedan på **Öppna i SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-204">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="7bb48-205">Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-205">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="7bb48-206">I fönstret **Webbplatsbehörigheter**, under **webbplatsdelning**, klickar du på **Ändra hur medlemmar kan dela**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-206">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="7bb48-207">Under **Delningsbehörigheter** väljer du **Endast webbplatsägare kan dela filer, mappar och webbplats**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-207">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
7. <span data-ttu-id="7bb48-208">Ställ **Tillåt åtkomstbegäranden** till **Av** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7bb48-208">Set **Allow access requests** to **Off**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bb48-209">Se även</span><span class="sxs-lookup"><span data-stu-id="7bb48-209">See Also</span></span>

[<span data-ttu-id="7bb48-210">Skapa och konfigurera känslighetsetiketter och deras principer</span><span class="sxs-lookup"><span data-stu-id="7bb48-210">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
