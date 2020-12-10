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
ms.openlocfilehash: bb97beaacf6a433e4fc5c38a897327d1e359ffb1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613520"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="40c11-103">Samar beta med gäster i ett dokument</span><span class="sxs-lookup"><span data-stu-id="40c11-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="40c11-104">Om du behöver samar beta med personer utanför organisationen för dokument i SharePoint eller OneDrive kan du skicka dem en delning – länka till dokumentet.</span><span class="sxs-lookup"><span data-stu-id="40c11-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="40c11-105">I den här artikeln går vi igenom konfigurations stegen för Microsoft 365 som behövs för att konfigurera delning – Länkar för SharePoint och OneDrive för organisationen.</span><span class="sxs-lookup"><span data-stu-id="40c11-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="40c11-106">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="40c11-106">Video demonstration</span></span>

<span data-ttu-id="40c11-107">I den här videon visas de konfigurations steg som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="40c11-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="40c11-108">Inställningar för Azure organisations relationer</span><span class="sxs-lookup"><span data-stu-id="40c11-108">Azure organizational relationships settings</span></span>

<span data-ttu-id="40c11-109">Delning i Microsoft 365 regleras på högsta nivå av [organisations Relations inställningarna i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="40c11-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="40c11-110">Om gäst delning är inaktiverat eller begränsat i Azure AD åsidosätter den här inställningen eventuella delnings inställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="40c11-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="40c11-111">Kontrol lera inställningarna för organisations relationer för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="40c11-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="40c11-113">Så här anger du inställningar för organisations relationer</span><span class="sxs-lookup"><span data-stu-id="40c11-113">To set organizational relationship settings</span></span>

<span data-ttu-id="40c11-114">Så här anger du inställningar för extern samarbete</span><span class="sxs-lookup"><span data-stu-id="40c11-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="40c11-115">Logga in på Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="40c11-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="40c11-116">I det vänstra navigerings fönstret klickar du på **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="40c11-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="40c11-117">Klicka på **externa identiteter**.</span><span class="sxs-lookup"><span data-stu-id="40c11-117">Click **External identities**.</span></span>
4. <span data-ttu-id="40c11-118">Klicka på **Inställningar för extern samarbete** i det vänstra navigerings fönstret på skärmen **Kom igång** .</span><span class="sxs-lookup"><span data-stu-id="40c11-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="40c11-119">Kontrol lera att **Administratörer och användare i rollen för att bjuda in gäst kan bjuda** in och **medlemmar kan bjuda** in till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="40c11-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="40c11-120">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="40c11-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="40c11-121">Observera inställningarna i avsnittet **samarbets begränsningar** .</span><span class="sxs-lookup"><span data-stu-id="40c11-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="40c11-122">Kontrol lera att domänerna för de gäster som du vill samar beta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="40c11-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="40c11-123">Om du arbetar med gäster från flera organisationer kan det vara bra att begränsa deras möjligheter att komma åt katalog data.</span><span class="sxs-lookup"><span data-stu-id="40c11-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="40c11-124">Detta hindrar dem från att se vem som är gäst i katalogen.</span><span class="sxs-lookup"><span data-stu-id="40c11-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="40c11-125">För att göra det, under **gäst användares restriktioner**, väljer du **gäst användare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalog objekt** eller **gäst användares åtkomst är begränsad till egenskaper och medlemskap i deras egna katalog objekt**.</span><span class="sxs-lookup"><span data-stu-id="40c11-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="40c11-126">Delnings inställningar för SharePoint på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="40c11-126">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="40c11-127">För att personer utanför din organisation ska ha till gång till ett dokument i SharePoint eller OneDrive måste delnings inställningarna för SharePoint och OneDrive tillåta delning med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="40c11-127">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="40c11-128">Inställningarna på organisations nivå för SharePoint avgör vilka inställningar som är tillgängliga för enskilda SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="40c11-128">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="40c11-129">Webbplats inställningarna kan inte vara mer tillåtna än inställningarna på organisations nivå.</span><span class="sxs-lookup"><span data-stu-id="40c11-129">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="40c11-130">Inställningen på organisations nivå för OneDrive bestämmer vilken nivå av delning som ska vara tillgänglig i användarnas OneDrive-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="40c11-130">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="40c11-131">Om du vill tillåta icke verifierade fil-och mappdelning för SharePoint och OneDrive väljer du **vem som helst**.</span><span class="sxs-lookup"><span data-stu-id="40c11-131">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="40c11-132">Om du vill vara säker på att personer utanför din organisation måste autentisera, väljer du **nytt och befintligt gäster**.</span><span class="sxs-lookup"><span data-stu-id="40c11-132">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="40c11-133">*Alla* länkar är det enklaste sättet att dela: personer utanför din organisation kan öppna länken utan att det är möjligt att överföra den till andra.</span><span class="sxs-lookup"><span data-stu-id="40c11-133">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="40c11-134">För SharePoint väljer du den mest krävda inställning som behövs av någon webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="40c11-134">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="40c11-136">Så här anger du delnings inställningar för SharePoint på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="40c11-136">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="40c11-137">Klicka på **SharePoint** i det vänstra navigerings fältet **i administrations** centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="40c11-137">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="40c11-138">Klicka på **delning** **i det** vänstra navigerings fältet i administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="40c11-138">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="40c11-139">Kontrol lera att extern delning för SharePoint eller OneDrive är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="40c11-139">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="40c11-140">(Observera att OneDrive-inställningen inte kan bli mer tillåtna än SharePoint-inställningen.)</span><span class="sxs-lookup"><span data-stu-id="40c11-140">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="40c11-141">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="40c11-141">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="40c11-142">Inställningar för SharePoint-standardinställningar på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="40c11-142">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="40c11-143">Standardinställningen för fil-och mappikonen styr det länk alternativ som visas för användarna som standard när de delar en fil eller mapp.</span><span class="sxs-lookup"><span data-stu-id="40c11-143">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="40c11-144">Användare kan ändra länktyp till något av de andra alternativen innan de delas, om så önskas.</span><span class="sxs-lookup"><span data-stu-id="40c11-144">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="40c11-145">Tänk på att den här inställningen påverkar SharePoint-webbplatser i din organisation samt OneDrive.</span><span class="sxs-lookup"><span data-stu-id="40c11-145">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="40c11-146">Välj en länk från någon av följande typer som sedan är markerad som standard när användare delar filer och mappar:</span><span class="sxs-lookup"><span data-stu-id="40c11-146">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="40c11-147">**Vem som helst med länken** – Välj det här alternativet om du förväntar dig att göra mängder av overifierade fil-och mappdelning.</span><span class="sxs-lookup"><span data-stu-id="40c11-147">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="40c11-148">Om du vill tillåta *alla* länkar, men är bekymrad över oavsiktlig autentisering, bör du överväga något av de andra alternativen som standard.</span><span class="sxs-lookup"><span data-stu-id="40c11-148">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="40c11-149">Den här länk typen är bara tillgänglig om du har aktiverat **någon** delning.</span><span class="sxs-lookup"><span data-stu-id="40c11-149">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="40c11-150">**Endast personer i organisationen** – Välj det här alternativet om du tror att de flesta fil-och mappdelning är med i din organisation.</span><span class="sxs-lookup"><span data-stu-id="40c11-150">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="40c11-151">**Vissa personer** -Överväg det här alternativet om du förväntar dig att göra många fil-och mappdelning med gästerna.</span><span class="sxs-lookup"><span data-stu-id="40c11-151">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="40c11-152">Den här typen av länk fungerar med gäster och kräver att de autentiseras.</span><span class="sxs-lookup"><span data-stu-id="40c11-152">This type of link works with guests and requires them to authenticate.</span></span>
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="40c11-154">Så här anger du inställningar för SharePoint-och OneDrive-standardinställningar på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="40c11-154">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="40c11-155">Gå till sidan delning i administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="40c11-155">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="40c11-156">Under **fil-och mappaktiviteter** väljer du den standard delnings länk som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="40c11-156">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="40c11-157">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="40c11-157">If you made changes, click **Save**.</span></span>

<span data-ttu-id="40c11-158">Om du vill ange behörighet för delnings länken under **Välj den behörighet som är markerad som standard för delning av länkar.**</span><span class="sxs-lookup"><span data-stu-id="40c11-158">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="40c11-159">Välj **Visa** om du inte vill att oautentiserade användare ska kunna ändra filerna och mapparna.</span><span class="sxs-lookup"><span data-stu-id="40c11-159">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="40c11-160">Välj **Redigera** om du vill tillåta att overifierade användare gör ändringar i filerna och mapparna.</span><span class="sxs-lookup"><span data-stu-id="40c11-160">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="40c11-161">Observera att ovanstående två försändnings alternativ kan tillämpas inte enbart för gäster och externa användare utan även för interna användare.</span><span class="sxs-lookup"><span data-stu-id="40c11-161">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="40c11-162">Det behörighets alternativ du väljer avgörs av själv.</span><span class="sxs-lookup"><span data-stu-id="40c11-162">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="40c11-163">Så här anger du behörigheter för länkar som tillåter delning med vem som helst</span><span class="sxs-lookup"><span data-stu-id="40c11-163">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="40c11-164">Under de **här länkarna kan du ge behörigheterna:** under fönster rutan</span><span class="sxs-lookup"><span data-stu-id="40c11-164">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="40c11-165">Från List rutan **filer**</span><span class="sxs-lookup"><span data-stu-id="40c11-165">From the **Files** drop-down list,</span></span> 
        1. <span data-ttu-id="40c11-166">Välj **Visa och redigera** om du vill tillåta att overifierade användare gör ändringar i filerna.</span><span class="sxs-lookup"><span data-stu-id="40c11-166">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        2. <span data-ttu-id="40c11-167">Välj **Visa** om du inte vill att overifierade användare ska kunna göra ändringar i filerna.</span><span class="sxs-lookup"><span data-stu-id="40c11-167">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="40c11-168">Från List rutan **mappar**</span><span class="sxs-lookup"><span data-stu-id="40c11-168">From the **Folders** drop-down list,</span></span>
        1. <span data-ttu-id="40c11-169">Välj **Visa, redigera och ladda upp** om du vill tillåta att overifierade användare gör ändringar i mapparna.</span><span class="sxs-lookup"><span data-stu-id="40c11-169">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        2. <span data-ttu-id="40c11-170">Välj **Visa** om du inte vill att overifierade användare ska kunna göra ändringar i mapparna.</span><span class="sxs-lookup"><span data-stu-id="40c11-170">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="40c11-171">Delnings inställningar på SharePoint-webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="40c11-171">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="40c11-172">Om du delar filer och mappar på en SharePoint-webbplats måste du också kontrol lera delnings inställningarna för webbplatsen på webbplats nivå.</span><span class="sxs-lookup"><span data-stu-id="40c11-172">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="40c11-174">Ange delnings inställningar på webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="40c11-174">To set site-level sharing settings</span></span>

1. <span data-ttu-id="40c11-175">I administrations centret för SharePoint, i det vänstra navigerings fönstret, expanderar du **webbplatser** och klickar på **aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="40c11-175">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="40c11-176">Välj den webbplats där du vill dela filer och mappar med gäster.</span><span class="sxs-lookup"><span data-stu-id="40c11-176">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="40c11-177">Bläddra till höger på raden (där den valda webbplatsen finns) och klicka någonstans i kolumnen **extern delning** .</span><span class="sxs-lookup"><span data-stu-id="40c11-177">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="40c11-178">Klicka på fliken **principer** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="40c11-178">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="40c11-179">Klicka på **Redigera** under fönstret **extern delning** .</span><span class="sxs-lookup"><span data-stu-id="40c11-179">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="40c11-180">Kontrol lera att delning är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="40c11-180">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="40c11-181">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="40c11-181">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="40c11-182">Bjuda in användare</span><span class="sxs-lookup"><span data-stu-id="40c11-182">Invite users</span></span>

<span data-ttu-id="40c11-183">Inställningar för gäst delning är nu konfigurerade; användare kan nu dela filer och mappar med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="40c11-183">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="40c11-184">Mer information finns i [dela OneDrive-filer och-mappar](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) och [dela SharePoint-filer eller-mappar](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="40c11-184">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="40c11-185">Se även</span><span class="sxs-lookup"><span data-stu-id="40c11-185">See also</span></span>

[<span data-ttu-id="40c11-186">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="40c11-186">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="40c11-187">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="40c11-187">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="40c11-188">SharePoint och OneDrive-integrering med Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="40c11-188">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
