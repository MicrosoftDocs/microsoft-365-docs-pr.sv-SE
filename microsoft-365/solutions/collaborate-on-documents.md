---
title: Samar beta med gäster i ett dokument
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
localization_priority: Normal
f1.keywords: NOCSH
description: I den här artikeln får du lära dig hur du samarbetar med gäster i ett dokument i SharePoint och OneDrive.
ms.openlocfilehash: 1b2fe003902b69e4c0c58852af67862ce6f2eb34
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663517"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="fc144-103">Samar beta med gäster i ett dokument</span><span class="sxs-lookup"><span data-stu-id="fc144-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="fc144-104">Om du behöver samar beta med personer utanför organisationen för dokument i SharePoint eller OneDrive kan du skicka dem en delning – länka till dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fc144-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="fc144-105">I den här artikeln går vi igenom konfigurations stegen för Microsoft 365 som behövs för att konfigurera delning – Länkar för SharePoint och OneDrive för organisationen.</span><span class="sxs-lookup"><span data-stu-id="fc144-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="fc144-106">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="fc144-106">Video demonstration</span></span>

<span data-ttu-id="fc144-107">I den här videon visas de konfigurations steg som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="fc144-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="fc144-108">Inställningar för extern samarbete i Azure</span><span class="sxs-lookup"><span data-stu-id="fc144-108">Azure external collaboration settings</span></span>

<span data-ttu-id="fc144-109">Delning i Microsoft 365 regleras på högsta nivå av [B2B-inställningen för externt samarbete i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="fc144-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="fc144-110">Om gäst delning är inaktiverat eller begränsat i Azure AD åsidosätter den här inställningen eventuella delnings inställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fc144-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="fc144-111">Kontrol lera inställningarna för externt samarbete för B2B för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="fc144-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="fc144-113">Så här anger du inställningar för extern samarbete</span><span class="sxs-lookup"><span data-stu-id="fc144-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="fc144-114">Logga in på Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="fc144-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="fc144-115">I det vänstra navigerings fönstret klickar du på **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="fc144-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="fc144-116">Klicka på **externa identiteter**.</span><span class="sxs-lookup"><span data-stu-id="fc144-116">Click **External identities**.</span></span>
4. <span data-ttu-id="fc144-117">Klicka på **Inställningar för extern samarbete** i det vänstra navigerings fönstret på skärmen **Kom igång** .</span><span class="sxs-lookup"><span data-stu-id="fc144-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="fc144-118">Kontrol lera att **Administratörer och användare i rollen för att bjuda in gäst kan bjuda** in och **medlemmar kan bjuda** in till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="fc144-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="fc144-119">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fc144-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="fc144-120">Observera inställningarna i avsnittet **samarbets begränsningar** .</span><span class="sxs-lookup"><span data-stu-id="fc144-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="fc144-121">Kontrol lera att domänerna för de gäster som du vill samar beta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="fc144-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="fc144-122">Om du arbetar med gäster från flera organisationer kan det vara bra att begränsa deras möjligheter att komma åt katalog data.</span><span class="sxs-lookup"><span data-stu-id="fc144-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="fc144-123">Detta hindrar dem från att se vem som är gäst i katalogen.</span><span class="sxs-lookup"><span data-stu-id="fc144-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="fc144-124">För att göra det, under **gäst användares restriktioner**, väljer du **gäst användare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalog objekt** eller **gäst användares åtkomst är begränsad till egenskaper och medlemskap i deras egna katalog objekt**.</span><span class="sxs-lookup"><span data-stu-id="fc144-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="fc144-125">Delnings inställningar för SharePoint på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="fc144-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="fc144-126">För att personer utanför din organisation ska ha till gång till ett dokument i SharePoint eller OneDrive måste delnings inställningarna för SharePoint och OneDrive tillåta delning med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="fc144-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="fc144-127">Inställningarna på organisations nivå för SharePoint avgör vilka inställningar som är tillgängliga för enskilda SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="fc144-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="fc144-128">Webbplats inställningarna kan inte vara mer tillåtna än inställningarna på organisations nivå.</span><span class="sxs-lookup"><span data-stu-id="fc144-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="fc144-129">Inställningen på organisations nivå för OneDrive bestämmer vilken nivå av delning som ska vara tillgänglig i användarnas OneDrive-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="fc144-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="fc144-130">Om du vill tillåta icke verifierade fil-och mappdelning för SharePoint och OneDrive väljer du **vem som helst**.</span><span class="sxs-lookup"><span data-stu-id="fc144-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="fc144-131">Om du vill vara säker på att personer utanför din organisation måste autentisera, väljer du **nytt och befintligt gäster**.</span><span class="sxs-lookup"><span data-stu-id="fc144-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="fc144-132">*Alla* länkar är det enklaste sättet att dela: personer utanför din organisation kan öppna länken utan att det är möjligt att överföra den till andra.</span><span class="sxs-lookup"><span data-stu-id="fc144-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="fc144-133">För SharePoint väljer du den mest krävda inställning som behövs av någon webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="fc144-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="fc144-135">Så här anger du delnings inställningar för SharePoint på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="fc144-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="fc144-136">Klicka på **SharePoint** i det vänstra navigerings fältet **i administrations** centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fc144-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="fc144-137">Klicka på **delning** **i det** vänstra navigerings fältet i administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc144-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="fc144-138">Kontrol lera att extern delning för SharePoint eller OneDrive är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="fc144-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="fc144-139">(Observera att OneDrive-inställningen inte kan bli mer tillåtna än SharePoint-inställningen.)</span><span class="sxs-lookup"><span data-stu-id="fc144-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="fc144-140">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fc144-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="fc144-141">Inställningar för SharePoint-standardinställningar på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="fc144-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="fc144-142">Standardinställningen för fil-och mappikonen styr det länk alternativ som visas för användarna som standard när de delar en fil eller mapp.</span><span class="sxs-lookup"><span data-stu-id="fc144-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="fc144-143">Användare kan ändra länktyp till något av de andra alternativen innan de delas, om så önskas.</span><span class="sxs-lookup"><span data-stu-id="fc144-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="fc144-144">Tänk på att den här inställningen påverkar SharePoint-webbplatser i din organisation samt OneDrive.</span><span class="sxs-lookup"><span data-stu-id="fc144-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="fc144-145">Välj en länk från någon av följande typer som sedan är markerad som standard när användare delar filer och mappar:</span><span class="sxs-lookup"><span data-stu-id="fc144-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="fc144-146">**Vem som helst med länken** – Välj det här alternativet om du förväntar dig att göra mängder av overifierade fil-och mappdelning.</span><span class="sxs-lookup"><span data-stu-id="fc144-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="fc144-147">Om du vill tillåta *alla* länkar, men är bekymrad över oavsiktlig autentisering, bör du överväga något av de andra alternativen som standard.</span><span class="sxs-lookup"><span data-stu-id="fc144-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="fc144-148">Den här länk typen är bara tillgänglig om du har aktiverat **någon** delning.</span><span class="sxs-lookup"><span data-stu-id="fc144-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="fc144-149">**Endast personer i organisationen** – Välj det här alternativet om du tror att de flesta fil-och mappdelning är med i din organisation.</span><span class="sxs-lookup"><span data-stu-id="fc144-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="fc144-150">**Vissa personer** -Överväg det här alternativet om du förväntar dig att göra många fil-och mappdelning med gästerna.</span><span class="sxs-lookup"><span data-stu-id="fc144-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="fc144-151">Den här typen av länk fungerar med gäster och kräver att de autentiseras.</span><span class="sxs-lookup"><span data-stu-id="fc144-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="fc144-153">Så här anger du inställningar för SharePoint-och OneDrive-standardinställningar på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="fc144-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="fc144-154">Gå till sidan delning i administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc144-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="fc144-155">Under **fil-och mappaktiviteter** väljer du den standard delnings länk som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="fc144-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="fc144-156">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fc144-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="fc144-157">Om du vill ange behörighet för delnings länken under **Välj den behörighet som är markerad som standard för delning av länkar.**</span><span class="sxs-lookup"><span data-stu-id="fc144-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="fc144-158">Välj **Visa** om du inte vill att oautentiserade användare ska kunna ändra filerna och mapparna.</span><span class="sxs-lookup"><span data-stu-id="fc144-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="fc144-159">Välj **Redigera** om du vill tillåta att overifierade användare gör ändringar i filerna och mapparna.</span><span class="sxs-lookup"><span data-stu-id="fc144-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="fc144-160">Observera att ovanstående två försändnings alternativ kan tillämpas inte enbart för gäster och externa användare utan även för interna användare.</span><span class="sxs-lookup"><span data-stu-id="fc144-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="fc144-161">Det behörighets alternativ du väljer avgörs av själv.</span><span class="sxs-lookup"><span data-stu-id="fc144-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="fc144-162">Så här anger du behörigheter för länkar som tillåter delning med vem som helst</span><span class="sxs-lookup"><span data-stu-id="fc144-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="fc144-163">Under de **här länkarna kan du ge behörigheterna:** under fönster rutan</span><span class="sxs-lookup"><span data-stu-id="fc144-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="fc144-164">Från List rutan **filer**</span><span class="sxs-lookup"><span data-stu-id="fc144-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="fc144-165">Välj **Visa och redigera** om du vill tillåta att overifierade användare gör ändringar i filerna.</span><span class="sxs-lookup"><span data-stu-id="fc144-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="fc144-166">Välj **Visa** om du inte vill att overifierade användare ska kunna göra ändringar i filerna.</span><span class="sxs-lookup"><span data-stu-id="fc144-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="fc144-167">Från List rutan **mappar**</span><span class="sxs-lookup"><span data-stu-id="fc144-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="fc144-168">Välj **Visa, redigera och ladda upp** om du vill tillåta att overifierade användare gör ändringar i mapparna.</span><span class="sxs-lookup"><span data-stu-id="fc144-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="fc144-169">Välj **Visa** om du inte vill att overifierade användare ska kunna göra ändringar i mapparna.</span><span class="sxs-lookup"><span data-stu-id="fc144-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="fc144-170">Delnings inställningar på SharePoint-webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="fc144-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="fc144-171">Om du delar filer och mappar på en SharePoint-webbplats måste du också kontrol lera delnings inställningarna för webbplatsen på webbplats nivå.</span><span class="sxs-lookup"><span data-stu-id="fc144-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="fc144-173">Ange delnings inställningar på webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="fc144-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="fc144-174">I administrations centret för SharePoint, i det vänstra navigerings fönstret, expanderar du **webbplatser** och klickar på **aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="fc144-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="fc144-175">Välj den webbplats där du vill dela filer och mappar med gäster.</span><span class="sxs-lookup"><span data-stu-id="fc144-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="fc144-176">Bläddra till höger på raden (där den valda webbplatsen finns) och klicka någonstans i kolumnen **extern delning** .</span><span class="sxs-lookup"><span data-stu-id="fc144-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="fc144-177">Klicka på fliken **principer** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="fc144-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="fc144-178">Klicka på **Redigera** under fönstret **extern delning** .</span><span class="sxs-lookup"><span data-stu-id="fc144-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="fc144-179">Kontrol lera att delning är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="fc144-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="fc144-180">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="fc144-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="fc144-181">Bjuda in användare</span><span class="sxs-lookup"><span data-stu-id="fc144-181">Invite users</span></span>

<span data-ttu-id="fc144-182">Inställningar för gäst delning är nu konfigurerade; användare kan nu dela filer och mappar med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="fc144-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="fc144-183">Mer information finns i [dela OneDrive-filer och-mappar](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) och [dela SharePoint-filer eller-mappar](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="fc144-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc144-184">Se även</span><span class="sxs-lookup"><span data-stu-id="fc144-184">See also</span></span>

[<span data-ttu-id="fc144-185">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="fc144-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="fc144-186">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="fc144-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="fc144-187">SharePoint och OneDrive-integrering med Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="fc144-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
