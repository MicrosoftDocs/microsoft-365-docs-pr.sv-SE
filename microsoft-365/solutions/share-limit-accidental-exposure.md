---
title: Begränsa oavsiktlig exponering
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
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
description: Lär dig hur du begränsar oavsiktlig exponering av information när du delar filer med personer utanför organisationen.
ms.openlocfilehash: 430c00d46fa3801d0869b05a651fadd3bf5dea28
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49029975"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a><span data-ttu-id="57edb-103">Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="57edb-103">Limit accidental exposure to files when sharing with people outside your organization</span></span>

<span data-ttu-id="57edb-104">När du delar filer och mappar med personer utanför organisationen finns det en mängd olika alternativ som du kan använda för att minska risken för att någon oavsiktligt delar känslig information.</span><span class="sxs-lookup"><span data-stu-id="57edb-104">When sharing files and folders with people outside your organization, there are a variety of options to reduce the chances of accidentally sharing sensitive information.</span></span> <span data-ttu-id="57edb-105">Du kan välja bland alternativen i den här artikeln för att uppfylla organisationens behov på bästa sätt.</span><span class="sxs-lookup"><span data-stu-id="57edb-105">You can choose from the options in this article to best meet the needs of your organization.</span></span>

## <a name="use-best-practices-for-anyone-links"></a><span data-ttu-id="57edb-106">Använda bästa metoder för Alla-länkar</span><span class="sxs-lookup"><span data-stu-id="57edb-106">Use best practices for Anyone links</span></span>

<span data-ttu-id="57edb-107">Om personer i organisationen behöver göra oautentiserad delning, men du är bekymrad över att oautentiserade personer ska ändra innehållet, läser du [Metodtips för oautentiserad delning](best-practices-anonymous-sharing.md) för att få vägledning om hur du ska arbeta med oautentiserad delning i organisationen.</span><span class="sxs-lookup"><span data-stu-id="57edb-107">If people in your organization need to do unauthenticated sharing, but you're concerned about unauthenticated people modifying content, read [Best practices for unauthenticated sharing](best-practices-anonymous-sharing.md) for guidance on how to work with unauthenticated sharing in your organization.</span></span>

## <a name="turn-off-anyone-links"></a><span data-ttu-id="57edb-108">Inaktivera Alla-länkar</span><span class="sxs-lookup"><span data-stu-id="57edb-108">Turn off Anyone links</span></span>

<span data-ttu-id="57edb-109">Vi rekommenderar att du lämnar *Alla* -länkar aktiverade för lämpligt innehåll, eftersom det är det enklaste sättet att dela och hjälper till att minska risken för att användare tar till andra lösningar som ligger utanför IT-avdelningens kontroll.</span><span class="sxs-lookup"><span data-stu-id="57edb-109">We recommend leaving *Anyone* links enabled for appropriate content because it's the easiest way to share and can help reduce the risk of users seeking other solutions that are outside the control of your IT department.</span></span> <span data-ttu-id="57edb-110">*Alla* -länkar kan vidarebefordras till andra, men filåtkomst är bara tillgänglig för dem som har länken.</span><span class="sxs-lookup"><span data-stu-id="57edb-110">*Anyone* links can be forwarded to others, but file access is only available to those who have the link.</span></span>

<span data-ttu-id="57edb-111">Om du alltid vill att personer utanför organisationen ska autentiseras vid åtkomst till innehåll i SharePoint, Grupper eller Teams, kan du inaktivera *Alla* -delningen.</span><span class="sxs-lookup"><span data-stu-id="57edb-111">If you always want people outside your organization to authenticate when accessing content in SharePoint, Groups, or Teams, you can turn off *Anyone* sharing.</span></span> <span data-ttu-id="57edb-112">Det hindrar användare från oautentiserad delning av innehåll.</span><span class="sxs-lookup"><span data-stu-id="57edb-112">This will prevent users from unauthenticated sharing of content.</span></span>

<span data-ttu-id="57edb-113">Om du inaktiverar *Alla* -länkar kan användare trots det enkelt dela med gäster genom att använda *Specifika personer* -länkar.</span><span class="sxs-lookup"><span data-stu-id="57edb-113">If you disable *Anyone* links, users can still easily share with guests using *Specific people* links.</span></span> <span data-ttu-id="57edb-114">I det här fallet måste alla personer utanför organisationen autentiseras innan de kan få åtkomst till det delade innehållet.</span><span class="sxs-lookup"><span data-stu-id="57edb-114">In this case, all people outside your organization will be required to authenticate before they can access the shared content.</span></span>

<span data-ttu-id="57edb-115">Beroende på behoven kan du inaktivera *Alla* -länkar för specifika webbplatser eller för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="57edb-115">Depending on your needs, you can disable *Anyone* links for specific sites, or for your whole organization.</span></span>

<span data-ttu-id="57edb-116">Inaktivera *Alla* -länkar för organisationen</span><span class="sxs-lookup"><span data-stu-id="57edb-116">To turn off *Anyone* links for your organization</span></span>
1. <span data-ttu-id="57edb-117">I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="57edb-117">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="57edb-118">Sätt inställningen för extern delning för SharePoint på **Nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="57edb-118">Set the SharePoint external sharing settings to **New and existing guests**.</span></span>

   ![Skärmbild av inställningar på organisationsnivå för extern delning för SharePoint](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. <span data-ttu-id="57edb-120">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="57edb-120">Click **Save**.</span></span>

<span data-ttu-id="57edb-121">Inaktivera *Alla* -länkar för en webbplats</span><span class="sxs-lookup"><span data-stu-id="57edb-121">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="57edb-122">I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="57edb-122">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="57edb-123">Välj den webbplats du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="57edb-123">Select the site that you want to configure.</span></span>
3. <span data-ttu-id="57edb-124">Klicka på **Delning** i menyfliksområdet.</span><span class="sxs-lookup"><span data-stu-id="57edb-124">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="57edb-125">Kontrollera att delning är inställt på **Nya och befintligt gäster**.</span><span class="sxs-lookup"><span data-stu-id="57edb-125">Ensure that sharing is set to **New and existing guests**.</span></span>

   ![Skärmbild av inställningar på webbplatsnivå för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

5. <span data-ttu-id="57edb-127">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="57edb-127">If you made changes, click **Save**.</span></span>

## <a name="domain-filtering"></a><span data-ttu-id="57edb-128">Domänfiltrering</span><span class="sxs-lookup"><span data-stu-id="57edb-128">Domain filtering</span></span>

<span data-ttu-id="57edb-129">Du kan använda listor över tillåtna eller nekade domäner för att ange de domäner som dina användare kan dela med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="57edb-129">You can use domain allow or deny lists to specify which domains your users can use when sharing with people outside your organization.</span></span>

<span data-ttu-id="57edb-130">Med en tillåt-lista kan du ange en lista över domäner där användarna i organisationen kan dela med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="57edb-130">With an allow list, you can specify a list of domains where users in your organization can share with people outside your organization.</span></span> <span data-ttu-id="57edb-131">Delning med andra domäner är blockerad.</span><span class="sxs-lookup"><span data-stu-id="57edb-131">Sharing with to other domains is blocked.</span></span> <span data-ttu-id="57edb-132">Om din organisation bara samarbetar med personer i en lista med specifika domäner kan du använda den här funktionen för att förhindra delning med andra domäner.</span><span class="sxs-lookup"><span data-stu-id="57edb-132">If your organization only collaborates with people from a list of specific domains, you can use this feature to prevent sharing with other domains.</span></span>

<span data-ttu-id="57edb-133">Med en neka-lista kan du ange en lista över domäner från vilken användarna i organisationen inte kan dela med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="57edb-133">With a deny list, you can specify a list of domains from which users in your organization cannot share with people outside your organization.</span></span> <span data-ttu-id="57edb-134">Delning med angivna domäner är blockerad.</span><span class="sxs-lookup"><span data-stu-id="57edb-134">Sharing with the listed domains is blocked.</span></span> <span data-ttu-id="57edb-135">Det här kan vara användbart om du exempelvis har konkurrenter som du vill hindra från att komma åt innehåll i din organisation.</span><span class="sxs-lookup"><span data-stu-id="57edb-135">This can be useful if you have competitors, for example, who you want to prevent from accessing content in your organization.</span></span>

<span data-ttu-id="57edb-136">Listorna över tillåtna och nekade domäner påverkar bara delning med gäster.</span><span class="sxs-lookup"><span data-stu-id="57edb-136">The allow and deny lists only affect sharing with guests.</span></span> <span data-ttu-id="57edb-137">Användare kan fortfarande dela med personer från förbjudna domäner genom att använda *Alla* -länkar om du inte har inaktiverat dem.</span><span class="sxs-lookup"><span data-stu-id="57edb-137">Users can still share with people from prohibited domains by using *Anyone* links if you haven't disabled them.</span></span> <span data-ttu-id="57edb-138">Om du vill få bäst resultat med listor över tillåtna eller nekade domäner kan du inaktivera *Alla* -länkar enligt beskrivningen ovan.</span><span class="sxs-lookup"><span data-stu-id="57edb-138">For best results with domain allow and deny lists, consider disabling *Anyone* links as described above.</span></span>

<span data-ttu-id="57edb-139">Konfigurera en lista över tillåtna eller nekade domäner</span><span class="sxs-lookup"><span data-stu-id="57edb-139">To set up a domain allow or deny list</span></span>
1. <span data-ttu-id="57edb-140">I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="57edb-140">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="57edb-141">Under **Avancerade inställningar för extern delning** markerar du kryssrutan **Begränsa extern delning per domän**.</span><span class="sxs-lookup"><span data-stu-id="57edb-141">Under **Advanced settings for external sharing** , select the **Limit external sharing by domain** check box.</span></span>
3. <span data-ttu-id="57edb-142">Klicka på **Lägg till domäner**.</span><span class="sxs-lookup"><span data-stu-id="57edb-142">Click **Add domains**.</span></span>
4. <span data-ttu-id="57edb-143">Välj om du vill blockera domäner, ange domänerna och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="57edb-143">Select whether you want to block domains, type the domains, and click **OK**.</span></span>

   ![Skärmbild av inställningen för att begränsa extern delning per domän för SharePoint](../media/sharepoint-sharing-block-domain.png)

5. <span data-ttu-id="57edb-145">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="57edb-145">Click **Save**.</span></span>

<span data-ttu-id="57edb-146">Om du vill begränsa delningen per domän på en högre nivå än SharePoint och OneDrive kan du [tillåta eller blockera inbjudningar för B2B-användare från specifika organisationer](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="57edb-146">If you want to limit sharing by domain at a higher level than SharePoint and OneDrive, you can [allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list) in Azure Active Directory.</span></span> <span data-ttu-id="57edb-147">(Du måste konfigurera [SharePoint- och OneDrive-integreringen med Azure AD B2B förhandsversion](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) för att de här inställningarna ska påverka SharePoint och OneDrive.)</span><span class="sxs-lookup"><span data-stu-id="57edb-147">(You must configure the [SharePoint and OneDrive integration with Azure AD B2B Preview](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) for these settings to affect SharePoint and OneDrive.)</span></span>

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a><span data-ttu-id="57edb-148">Begränsa delning av filer, mappar och webbplatser med personer utanför organisationen till angivna säkerhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="57edb-148">Limit sharing of files, folders, and sites with people outside your organization to specified security groups</span></span>

<span data-ttu-id="57edb-149">Du kan begränsa delning av filer, mappar och webbplatser med personer utanför organisationen till medlemmar i en specifik säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="57edb-149">You can restrict sharing of files, folders, and sites with people outside your organization to members of a specific security group.</span></span> <span data-ttu-id="57edb-150">Det här är användbart om du vill aktivera extern delning, men med ett arbetsflöde för godkännande eller en process för begäran.</span><span class="sxs-lookup"><span data-stu-id="57edb-150">This is useful if you want to enable external sharing, but with an approval workflow or request process.</span></span> <span data-ttu-id="57edb-151">Du kan även kräva att användarna ska genomgå en utbildning innan de läggs till i säkerhetsgruppen och får dela externt.</span><span class="sxs-lookup"><span data-stu-id="57edb-151">Alternatively, you might require your users to complete a training course before they're added to the security group and are allowed to share externally.</span></span>

<span data-ttu-id="57edb-152">Begränsa extern delning till medlemmar i en säkerhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="57edb-152">To limit external sharing to members of a security group</span></span>
1. <span data-ttu-id="57edb-153">I navigeringsfönstret till vänster i [administrationscentret för SharePoint](https://admin.microsoft.com/sharepoint) går du till **Principer** och klickar på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="57edb-153">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), in the left navigation, under **Policies** , click **Sharing**.</span></span>
2. <span data-ttu-id="57edb-154">Under **Extern delning** väljer du **Fler inställningar för extern delning**.</span><span class="sxs-lookup"><span data-stu-id="57edb-154">Under **External sharing** , expand **More external sharing settings**.</span></span>

3. <span data-ttu-id="57edb-155">Välj **Tillåt endast användare i vissa säkerhetsgrupper att dela externt** och därefter **Hantera säkerhetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="57edb-155">Select **Allow only users in specific security groups to share externally** , and then select **Manage security groups**.</span></span>

    ![Skärmbild av panelen Hantera säkerhetsgrupper](https://docs.microsoft.com/sharepoint/sharepointonline/media/manage-security-groups.png)

4. <span data-ttu-id="57edb-157">I rutan **Lägg till en säkerhetsgrupp** anger du ett namn på en säkerhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="57edb-157">In the **Add a security group** box, enter a name for a security group.</span></span> <span data-ttu-id="57edb-158">Rutan för säkerhetsgrupper öppnas.</span><span class="sxs-lookup"><span data-stu-id="57edb-158">The security group box appears.</span></span>

5. <span data-ttu-id="57edb-159">Bredvid säkerhetsgruppens namn går du till listrutan **Kan dela med** och väljer något av följande:</span><span class="sxs-lookup"><span data-stu-id="57edb-159">Next to the security group name, from the **Can share with** dropdown, select either:</span></span>

    - <span data-ttu-id="57edb-160">**Endast autentiserade gäster** (standard)</span><span class="sxs-lookup"><span data-stu-id="57edb-160">**Authenticated guests only** (default)</span></span>
    - <span data-ttu-id="57edb-161">**Alla**</span><span class="sxs-lookup"><span data-stu-id="57edb-161">**Anyone**</span></span>

6. <span data-ttu-id="57edb-162">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="57edb-162">Select **Save**.</span></span>

<span data-ttu-id="57edb-163">Observera att det här påverkar filer, mappar och webbplatser, men inte Microsoft 365-grupper eller Teams.</span><span class="sxs-lookup"><span data-stu-id="57edb-163">Note that this affects files, folders, and sites, but not Microsoft 365 groups or Teams.</span></span> <span data-ttu-id="57edb-164">När medlemmar bjuder in gäster till en privat Microsoft 365-grupp eller ett privat team i Microsoft Teams skickas inbjudan till grupp- eller teamägaren för godkännande.</span><span class="sxs-lookup"><span data-stu-id="57edb-164">When members invite guests to a private Microsoft 365 group or a private team in Microsoft Teams, the invitation is sent to the group or team owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="57edb-165">Se även</span><span class="sxs-lookup"><span data-stu-id="57edb-165">See Also</span></span>

[<span data-ttu-id="57edb-166">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="57edb-166">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="57edb-167">Metodtips för att dela filer och mappar med anonyma användare</span><span class="sxs-lookup"><span data-stu-id="57edb-167">Best practices for sharing files and folders with anonymous users</span></span>](best-practices-anonymous-sharing.md)
