---
title: Metodtips för oautentiserad delning
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: I den här artikeln får du lära dig mer om metodtips för att dela filer och mappar med oautentiserade användare.
ms.openlocfilehash: eeee1ca0ddbb37525c86f44a3d02ab95de20e9fc
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030071"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a><span data-ttu-id="d5e40-103">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="d5e40-103">Best practices for sharing files and folders with unauthenticated users</span></span>

<span data-ttu-id="d5e40-104">Oautentiserad delning ( *Alla* -länkar) kan vara smidigt och användbart i olika scenarier.</span><span class="sxs-lookup"><span data-stu-id="d5e40-104">Unauthenticated sharing ( *Anyone* links) can be convenient and is useful in various scenarios.</span></span> <span data-ttu-id="d5e40-105">*Alla* -länkar är det enklaste sättet att dela: personer kan öppna länken utan autentisering och kan skicka den vidare till andra.</span><span class="sxs-lookup"><span data-stu-id="d5e40-105">*Anyone* links are the easiest way to share: people can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="d5e40-106">Vanligtvis är inte allt innehåll i en organisation lämpligt för oautentiserad delning.</span><span class="sxs-lookup"><span data-stu-id="d5e40-106">Usually, not all content in an organization is appropriate for unauthenticated sharing.</span></span> <span data-ttu-id="d5e40-107">I den här artikeln beskrivs de alternativ som är tillgängliga för att hjälpa dig att skapa en miljö där dina användare kan använda oautentiserad delning av filer och mappar, men där det finns säkerhetsåtgärder för att skydda organisationens innehåll.</span><span class="sxs-lookup"><span data-stu-id="d5e40-107">This article covers the options available to help you create an environment where your users can use unauthenticated sharing of files and folders, but where there are safeguards in place to help protect your organization's content.</span></span>

> [!NOTE]
> <span data-ttu-id="d5e40-108">För att oautentiserad delning ska fungera måste du aktivera den för din organisation och för den enskilda webbplatsen eller det team som du ska använda.</span><span class="sxs-lookup"><span data-stu-id="d5e40-108">For unauthenticated sharing to work, you must enable it for your organization and for the individual site or team that you'll be using.</span></span> <span data-ttu-id="d5e40-109">Se [Samarbeta med personer utanför organisationen](collaborate-with-people-outside-your-organization.md) för det scenario du vill aktivera.</span><span class="sxs-lookup"><span data-stu-id="d5e40-109">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for the scenario that you want to enable.</span></span>

## <a name="set-an-expiration-date-for-anyone-links"></a><span data-ttu-id="d5e40-110">Ange ett utgångsdatum för Alla-länkar</span><span class="sxs-lookup"><span data-stu-id="d5e40-110">Set an expiration date for Anyone links</span></span>

<span data-ttu-id="d5e40-111">Filer lagras ofta på webbplatser, i grupper och team under långa tidsperioder.</span><span class="sxs-lookup"><span data-stu-id="d5e40-111">Files are often stored in sites, groups, and teams for long periods of time.</span></span> <span data-ttu-id="d5e40-112">Ibland finns det datakvarhållningsprinciper som kräver att filer bevaras i flera år.</span><span class="sxs-lookup"><span data-stu-id="d5e40-112">Occasionally there are data retention policies that require files to be retained for years.</span></span> <span data-ttu-id="d5e40-113">Om de här filerna delas med oautentiserade personer kan detta leda till oväntad åtkomst och framtida ändringar i filerna.</span><span class="sxs-lookup"><span data-stu-id="d5e40-113">If such files are shared with unauthenticated people, this could lead to unexpected access and changes to files in the future.</span></span> <span data-ttu-id="d5e40-114">Om du vill minska risken för detta kan du konfigurera en förfallotid för *Alla* -länkar.</span><span class="sxs-lookup"><span data-stu-id="d5e40-114">To mitigate this possibility, you can configure an expiration time for *Anyone* links.</span></span>

<span data-ttu-id="d5e40-115">När en *Alla* -länk går ut kan den inte längre användas för att få åtkomst till innehåll.</span><span class="sxs-lookup"><span data-stu-id="d5e40-115">Once an *Anyone* link expires, it can no longer be used to access content.</span></span>

<span data-ttu-id="d5e40-116">Ange ett utgångsdatum för Alla-länkar i organisationen</span><span class="sxs-lookup"><span data-stu-id="d5e40-116">To set an expiration date for Anyone links across the organization</span></span>

1. <span data-ttu-id="d5e40-117">Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="d5e40-117">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="d5e40-118">Klicka på **Delning** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d5e40-118">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="d5e40-119">Markera kryssrutan **Länkarna måste upphöra att gälla inom så här många dagar** under **Välj behörigheter och giltighetsalternativ för Alla-länkar**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-119">Under **Choose expiration and permissions options for Anyone links** , select the **These links must expire within this many days** check box.</span></span></br>
   <span data-ttu-id="d5e40-120">![Skärmbild av inställningar för utgången av Alla-länkar för SharePoint på organisationsnivå](../media/sharepoint-organization-anyone-link-expiration.png)</span><span class="sxs-lookup"><span data-stu-id="d5e40-120">![Screenshot of SharePoint organization-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration.png)</span></span>
4. <span data-ttu-id="d5e40-121">Skriv ett antal dagar i rutan och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-121">Type a number of days in the box, and then click **Save**.</span></span>

<span data-ttu-id="d5e40-122">Ange ett utgångsdatum för Alla-länkar på en särskild webbplats</span><span class="sxs-lookup"><span data-stu-id="d5e40-122">To set an expiration date for Anyone links on a specific site</span></span>

1. <span data-ttu-id="d5e40-123">Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="d5e40-123">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="d5e40-124">I det vänstra navigeringsfältet expanderar du **Webbplatser** och klickar sedan på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-124">In the left navigation, expand **Sites** , and then click **Active sites**.</span></span>
3. <span data-ttu-id="d5e40-125">Välj webbplatsen som du vill ändra och klicka sedan på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-125">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="d5e40-126">Under **Avancerade inställningar för alla länkar** kan du under **Sista giltighetstiden för alla länkar** avmarkera kryssrutan **Samma som inställningen på organisationsnivå**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-126">Under **Advanced settings for Anyone links** , under **Expiration of Anyone links** , clear the **Same as organization-level setting** check box.</span></span></br>
   <span data-ttu-id="d5e40-127">![Skärmbild av inställningar för utgången av Alla-länkar för SharePoint på webbplatsnivå](../media/sharepoint-organization-anyone-link-expiration-site.png)</span><span class="sxs-lookup"><span data-stu-id="d5e40-127">![Screenshot of SharePoint site-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration-site.png)</span></span>
5. <span data-ttu-id="d5e40-128">Välj **Dessa länkar måste upphöra inom detta antal dagar** alternativ och ange ett antal dagar i rutan.</span><span class="sxs-lookup"><span data-stu-id="d5e40-128">Select the **These links must expire within this many days** option, and type a number of days in the box.</span></span>
6. <span data-ttu-id="d5e40-129">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-129">Click **Save**.</span></span>

<span data-ttu-id="d5e40-130">Tänk på att när en *Alla* -länk går ut kan filen eller mappen delas igen med en ny *Alla* -länk.</span><span class="sxs-lookup"><span data-stu-id="d5e40-130">Note that once an *Anyone* link expires, the file or folder can be re-shared with a new *Anyone* link.</span></span>

<span data-ttu-id="d5e40-131">Du kan ange *vem som helst* för länkens utgång för en specifik OneDrive med hjälp av [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite).</span><span class="sxs-lookup"><span data-stu-id="d5e40-131">You can set *Anyone* link expiration for a specific OneDrive by using [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite).</span></span>

## <a name="set-link-permissions"></a><span data-ttu-id="d5e40-132">Ange behörigheter för länk</span><span class="sxs-lookup"><span data-stu-id="d5e40-132">Set link permissions</span></span>

<span data-ttu-id="d5e40-133">*Alla* -länkar för en fil tillåter som standard personer att redigera filen, och *Alla* -länkar för en mapp tillåter personer att redigera och visa filer samt att ladda upp nya filer till mappen.</span><span class="sxs-lookup"><span data-stu-id="d5e40-133">By default, *Anyone* links for a file allow people to edit the file, and *Anyone* links for a folder allow people to edit and view files, and upload new files to the folder.</span></span> <span data-ttu-id="d5e40-134">Du kan ändra de här behörigheterna till endast visning för filer och mappar oberoende av varandra.</span><span class="sxs-lookup"><span data-stu-id="d5e40-134">You can change these permissions for files and for folders independently to view-only.</span></span>

<span data-ttu-id="d5e40-135">Om du vill tillåta oautentiserad delning, men är orolig för att oautentiserade personer ska ändra organisationens innehåll, bör du överväga att ställa in behörigheterna för filer och mappar till **Visa**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-135">If you want to allow unauthenticated sharing, but are concerned about unauthenticated people modifying your organization's content, consider setting the file and folder permissions to **View**.</span></span>

<span data-ttu-id="d5e40-136">Ange behörigheter för Alla-länkar i organisationen</span><span class="sxs-lookup"><span data-stu-id="d5e40-136">To set permissions for Anyone links across the organization</span></span>

1. <span data-ttu-id="d5e40-137">Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="d5e40-137">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="d5e40-138">Klicka på **Delning** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d5e40-138">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="d5e40-139">Under **Avancerade inställningar för "Alla"-länkar** väljer du de fil- och mappbehörigheter som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="d5e40-139">Under **Advanced settings for "Anyone" links** , select the file and folder permissions that you want to use.</span></span></br>
   <span data-ttu-id="d5e40-140">![Skärmbild av behörighetsinställningar för Alla-länkar för SharePoint på organisationsnivå](../media/sharepoint-organization-anyone-link-permissions.png)</span><span class="sxs-lookup"><span data-stu-id="d5e40-140">![Screenshot of SharePoint organization-level Anyone link permissions settings](../media/sharepoint-organization-anyone-link-permissions.png)</span></span>

<span data-ttu-id="d5e40-141">Med *Alla* -länkar inställda på **Visa** kan användare fortfarande dela filer och mappar med gäster och ge dem redigeringsbehörighet genom att använda *Specifika personer* -länkar.</span><span class="sxs-lookup"><span data-stu-id="d5e40-141">With *Anyone* links set to **View** , users can still share files and folders with guests and give them edit permissions by using *Specific people* links.</span></span> <span data-ttu-id="d5e40-142">Med dessa länkar måste personer utanför organisationen autentiseras som gäster, och du kan spåra och granska gästaktiviteten i filer och mappar som delas med dessa länkar.</span><span class="sxs-lookup"><span data-stu-id="d5e40-142">These links require people outside your organization to authenticate as guests, and you can track and audit guest activity on files and folders shared with these links.</span></span>

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a><span data-ttu-id="d5e40-143">Ställa in standardlänktypen till att endast fungera för personer i organisationen</span><span class="sxs-lookup"><span data-stu-id="d5e40-143">Set default link type to only work for people in your organization</span></span>

<span data-ttu-id="d5e40-144">När *Alla* -delning aktiveras för organisationen anges normalt delningslänken till **Alla**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-144">When *Anyone* sharing is enabled for your organization, the default sharing link is normally set to **Anyone**.</span></span> <span data-ttu-id="d5e40-145">Det kan vara praktiskt för användarna, men kan öka risken för oavsiktlig oautentiserad delning.</span><span class="sxs-lookup"><span data-stu-id="d5e40-145">While this can be convenient for users, it can increase the risk of unintentional unauthenticated sharing.</span></span> <span data-ttu-id="d5e40-146">Om en användare glömmer att ändra länktypen vid delning av ett känsligt dokument, kan det hända att de oavsiktligt skapar en delningslänk som inte kräver autentisering.</span><span class="sxs-lookup"><span data-stu-id="d5e40-146">If a user forgets to change the link type while sharing a sensitive document, they might accidentally create a sharing link that doesn't require authentication.</span></span>

<span data-ttu-id="d5e40-147">Du kan minska den här risken genom att ändra standardlänkinställningen till en länk som bara fungerar för personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="d5e40-147">You can mitigate this risk by changing the default link setting to a link that only works for people inside your organization.</span></span> <span data-ttu-id="d5e40-148">Användare som vill dela med oautentiserade personer måste då specifikt välja det alternativet.</span><span class="sxs-lookup"><span data-stu-id="d5e40-148">Users who want to share with unauthenticated people would then have to specifically select that option.</span></span>

<span data-ttu-id="d5e40-149">Ange standarddelningslänken för filer och mappar för organisationen</span><span class="sxs-lookup"><span data-stu-id="d5e40-149">To set the default file and folder sharing link for the organization</span></span>
1. <span data-ttu-id="d5e40-150">Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="d5e40-150">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="d5e40-151">Klicka på **Delning** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d5e40-151">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="d5e40-152">Under **Fil- och mapplänkar** väljer du **Endast personer i organisationen**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-152">Under **File and folder links** , select **Only people in your organization**.</span></span>

   ![Skärmbild av inställning för standardlänktyp för SharePoint](../media/sharepoint-default-sharing-link-company-link.png)

4. <span data-ttu-id="d5e40-154">Klicka på **Spara**</span><span class="sxs-lookup"><span data-stu-id="d5e40-154">Click **Save**</span></span>

<span data-ttu-id="d5e40-155">Ange standarddelningslänken för filer och mappar för den särskilda webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d5e40-155">To set the default file and folder sharing link for a specific site</span></span>
1. <span data-ttu-id="d5e40-156">Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="d5e40-156">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="d5e40-157">I det vänstra navigeringsfältet expanderar du **Webbplatser** och klickar sedan på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-157">In the left navigation, expand **Sites** , and then click **Active sites**.</span></span>
3. <span data-ttu-id="d5e40-158">Välj webbplatsen som du vill ändra och klicka sedan på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-158">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="d5e40-159">Avmarkera kryssrutan **Samma som organisationsnivå** under **Standardtyp av delningslänk**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-159">Under **Default sharing link type** ,  clear the **Same as organization-level setting** check box.</span></span>

   ![Skärmbild av inställning för standardlänktyp för SharePoint på webbplatsnivå](../media/sharepoint-organization-anyone-link-permissions-site.png)

5. <span data-ttu-id="d5e40-161">Välj alternativet **Bara personer i organisationen** och klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-161">Select the **Only people in your organization** option and click **Save**.</span></span>

## <a name="prevent-unauthenticated-sharing-of-sensitive-content"></a><span data-ttu-id="d5e40-162">Förhindra oautentiserad delning av känsligt innehåll</span><span class="sxs-lookup"><span data-stu-id="d5e40-162">Prevent unauthenticated sharing of sensitive content</span></span>

<span data-ttu-id="d5e40-163">Du kan använda [Dataförlustskydd (DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)) för att förhindra oautentiserad delning av känsligt innehåll.</span><span class="sxs-lookup"><span data-stu-id="d5e40-163">You can use [data loss prevention (DLP)](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to prevent unauthenticated sharing of sensitive content.</span></span> <span data-ttu-id="d5e40-164">Dataförlustskydd kan utföra åtgärder baserat på en fils känslighetsetikett, kvarhållningsetikett eller känslig information i själva filen.</span><span class="sxs-lookup"><span data-stu-id="d5e40-164">Data loss prevention can take action based on a file's sensitivity label, retention label, or sensitive information in the file itself.</span></span>

<span data-ttu-id="d5e40-165">Skapa en DLP-regel</span><span class="sxs-lookup"><span data-stu-id="d5e40-165">To create a DLP rule</span></span>
1. <span data-ttu-id="d5e40-166">I Microsoft 365 Efterlevnadscenter, gå till sidan [Dataförlustskydd](https://compliance.microsoft.com/datalossprevention).</span><span class="sxs-lookup"><span data-stu-id="d5e40-166">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="d5e40-167">Klicka på **Skapa princip**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-167">Click **Create policy**.</span></span>
3. <span data-ttu-id="d5e40-168">Välj **Anpassad** och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-168">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="d5e40-169">Skriv ett namn för principen och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-169">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="d5e40-170">På **Platser för att tillämpa principen** Stäng av alla inställningar utom **SharePoint-webbplatser** och **OneDrive-konton** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-170">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts** , and then click **Next**.</span></span>
6. <span data-ttu-id="d5e40-171">På sidan **Definiera principinställningar** klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-171">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="d5e40-172">På sidan **Anpassa avancerade DLP-regler** klickar du på **Skapa regel** och anger ett namn på regeln.</span><span class="sxs-lookup"><span data-stu-id="d5e40-172">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="d5e40-173">Under **Villkor** klickar du på **Lägg till villkor** och väljer **Innehållet har**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-173">Under **Conditions** , click **Add condition** , and choose **Content contains**.</span></span>
9. <span data-ttu-id="d5e40-174">Klicka på **Lägg till** och välj vilken typ av information som du vill förhindra oautentiserad delning för.</span><span class="sxs-lookup"><span data-stu-id="d5e40-174">Click **Add** and choose the type of information for which you want to prevent unauthenticated sharing.</span></span>

   ![Skärmbild av alternativ för villkor,typer av känsliga information, känslighetsetiketter och kvarhållningsetiketter.](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="d5e40-176">Under **Åtgärder** klickar du på **Lägg till en åtgärd** och väljer **Begränsa åtkomst eller kryptera innehållet i Microsoft 365 platser**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-176">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="d5e40-177">Välj kryssrutan **Begränsa åtkomst eller kryptera innehållet på Microsoft 365 platser** och välj sedan **Bara personer som har fått åtkomst till innehållet via alternativen för “Alla som har länken "**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-177">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people who were given access to the content through the "Anyone withe the link" options** option.</span></span>

      ![Skärmbild av åtgärdsalternativ för DLP-regler](../media/limit-accidental-exposure-dlp-anyone-links.png)

12. <span data-ttu-id="d5e40-179">Klicka på **Spara** och sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-179">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="d5e40-180">Välj testalternativ och klicka på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-180">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="d5e40-181">Klicka på **Skicka** och klicka sedan **Klart**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-181">Click **Submit** , and then click **Done**.</span></span>

## <a name="protect-against-malicious-files"></a><span data-ttu-id="d5e40-182">Skydda mot skadliga filer</span><span class="sxs-lookup"><span data-stu-id="d5e40-182">Protect against malicious files</span></span>

<span data-ttu-id="d5e40-183">Om du tillåter anonyma användare att ladda upp filer ökar risken för att någon laddar upp en skadlig fil.</span><span class="sxs-lookup"><span data-stu-id="d5e40-183">When you allow anonymous users to upload files, you're at an increased risk of someone uploading a malicious file.</span></span> <span data-ttu-id="d5e40-184">I Microsoft 365 kan du använda funktionen för *säkra bifogade filer* i Defender för Office 365 för att automatiskt söka igenom uppladdade filer och sätta filer som kan vara osäkra i karantän.</span><span class="sxs-lookup"><span data-stu-id="d5e40-184">In Microsoft 365, you can use the *Safe Attachments* feature in Defender for Office 365 to automatically scan uploaded files and quarantine files that are found to be unsafe.</span></span>

<span data-ttu-id="d5e40-185">Aktivera säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="d5e40-185">To turn on safe attachments</span></span>
1. <span data-ttu-id="d5e40-186">Öppna sidan [ATP-säkra bifogade filer](https://protection.office.com/safeattachmentv2) i Säkerhets- och Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="d5e40-186">Open the [ATP Safe Attachments page](https://protection.office.com/safeattachmentv2) in the Security and Compliance admin center.</span></span>
2. <span data-ttu-id="d5e40-187">Klicka på **Globala inställningar**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-187">Click **Global settings**.</span></span>
3. <span data-ttu-id="d5e40-188">Aktivera ATP för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d5e40-188">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   ![Skärmbild av inställningen för säkra bifogade filer i Säkerhets- och efterlevnadscenter](../media/safe-attachments-setting.png)

4. <span data-ttu-id="d5e40-190">Om du vill kan du också aktivera säkert dokument och klicka på **Spara**</span><span class="sxs-lookup"><span data-stu-id="d5e40-190">Optionally turn on Safe Documents as well, and then click **Save**</span></span>

<span data-ttu-id="d5e40-191">Mer information finns i [ATP för SharePoint, OneDrive och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) och [Aktivera ATP för SharePoint, OneDrive, och Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="d5e40-191">See [ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams) for additional guidance.</span></span>

## <a name="add-copyright-information-to-your-files"></a><span data-ttu-id="d5e40-192">Lägga till copyrightinformation i dina filer</span><span class="sxs-lookup"><span data-stu-id="d5e40-192">Add copyright information to your files</span></span>

<span data-ttu-id="d5e40-193">Om du använder känslighetsetiketter i administrationscentret för Microsoft 365 Efterlevnad kan du konfigurera etiketterna för att automatiskt lägga till en vattenstämpel eller ett sidhuvud eller en sidfot i organisationens Office-dokument.</span><span class="sxs-lookup"><span data-stu-id="d5e40-193">If you use sensitivity labels in the Microsoft 365 Compliance admin center, you can configure your labels to add a watermark or a header or footer automatically to your organization's Office documents.</span></span> <span data-ttu-id="d5e40-194">På så sätt kan du se till att delade filer innehåller copyright- eller annan ägarskapsinformation.</span><span class="sxs-lookup"><span data-stu-id="d5e40-194">In this way, you can make sure that shared files contain copyright or other ownership information.</span></span>

<span data-ttu-id="d5e40-195">Lägga till en sidfot i en fil med en etikett</span><span class="sxs-lookup"><span data-stu-id="d5e40-195">To add a footer to a labeled file</span></span>

1. <span data-ttu-id="d5e40-196">Öppna [administrationscentret för Microsoft 365 Efterlevnad](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d5e40-196">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="d5e40-197">Under **Lösningar** klickar du på **Informationsskydd**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-197">In the left navigation, under **Solutions** , click **Information protection**.</span></span>
3. <span data-ttu-id="d5e40-198">Klicka på den etikett som du vill använda för att lägga till en sidfot och klicka sedan på **Redigera etikett**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-198">Click the label that you want to have add a footer, and then click **Edit label**.</span></span>
4. <span data-ttu-id="d5e40-199">Klicka på fliken **Nästa** för att nå **Märkning av innehåll** och sätt sedan **på** märkning av innehållet.</span><span class="sxs-lookup"><span data-stu-id="d5e40-199">Click **Next** to reach the **Content marking** tab, and then turn **On** content marking.</span></span>
5. <span data-ttu-id="d5e40-200">Markera kryssrutan för den typ av text som du vill lägga till och klicka sedan på **Anpassa text**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-200">Select the check box for the type of text you want to add, and then click **Customize text**.</span></span>
6. <span data-ttu-id="d5e40-201">Skriv den text du vill lägga till i dina dokument, markera de textalternativ som du vill använda och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-201">Type the text that you want added to your documents, select the text options that you want, and then click **Save**.</span></span></br>
   <span data-ttu-id="d5e40-202">![Skärmbild av inställningar för innehållsmärkning för en känslighetsetikett](../media/content-marking-for-anonymous-sharing.png)</span><span class="sxs-lookup"><span data-stu-id="d5e40-202">![Screenshot of the content marking settings for a sensitivity label](../media/content-marking-for-anonymous-sharing.png)</span></span>
7. <span data-ttu-id="d5e40-203">Gå till slutet av guiden genom att klicka på **Nästa** och klicka sedan på **Spara etikett**.</span><span class="sxs-lookup"><span data-stu-id="d5e40-203">Click **Next** to reach the end of the wizard, and then click **Save label**.</span></span>

<span data-ttu-id="d5e40-204">När du har aktiverat innehållsmärkning för etiketten läggs den text som du angett till i Office-dokument när en användare använder etiketten.</span><span class="sxs-lookup"><span data-stu-id="d5e40-204">With content marking enabled for the label, the text you specified will be added to Office documents when a user applies that label.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5e40-205">Se även</span><span class="sxs-lookup"><span data-stu-id="d5e40-205">See Also</span></span>

[<span data-ttu-id="d5e40-206">Översikt över känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="d5e40-206">Overview of sensitivity labels</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)

[<span data-ttu-id="d5e40-207">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="d5e40-207">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="d5e40-208">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="d5e40-208">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
