---
title: Samarbeta med gäster i ett dokument
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
ms.openlocfilehash: 9158ec7692ef90eb2e270242472fceb10d0e60b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920234"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="575ed-103">Samarbeta med gäster i ett dokument</span><span class="sxs-lookup"><span data-stu-id="575ed-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="575ed-104">Om du behöver samarbeta med personer utanför organisationen med dokument i SharePoint eller OneDrive kan du skicka dem en delningslänk till dokumentet.</span><span class="sxs-lookup"><span data-stu-id="575ed-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing-link to the document.</span></span> <span data-ttu-id="575ed-105">I den här artikeln går vi igenom konfigurationsstegen för Microsoft 365 som krävs för att konfigurera delningslänkar för SharePoint och OneDrive för organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="575ed-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing-links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="575ed-106">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="575ed-106">Video demonstration</span></span>

<span data-ttu-id="575ed-107">I den här videon visas konfigurationsstegen som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="575ed-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="575ed-108">Inställningar för externt Samarbete i Azure</span><span class="sxs-lookup"><span data-stu-id="575ed-108">Azure external collaboration settings</span></span>

<span data-ttu-id="575ed-109">Delning i Microsoft 365 styrs på sin högsta nivå av inställningarna för [B2B-externt samarbete i Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="575ed-109">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="575ed-110">Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter den här inställningen alla delningsinställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="575ed-110">If guest-sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="575ed-111">Kontrollera inställningarna för B2B externt samarbete för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="575ed-111">Check the B2B external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="575ed-113">Inställningar för externt samarbete</span><span class="sxs-lookup"><span data-stu-id="575ed-113">To set external collaboration settings</span></span>

1. <span data-ttu-id="575ed-114">Logga in till Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="575ed-114">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="575ed-115">I det vänstra navigeringsfönstret klickar du på **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="575ed-115">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="575ed-116">Klicka på **Externa identiteter**.</span><span class="sxs-lookup"><span data-stu-id="575ed-116">Click **External identities**.</span></span>
4. <span data-ttu-id="575ed-117">På skärmen **Kom igång** i det vänstra navigeringsfönstret klickar du på **inställningar för externt samarbete**.</span><span class="sxs-lookup"><span data-stu-id="575ed-117">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="575ed-118">Se till **administratörer och användare i gästens inbjudna roll kan bjuda in** och **Medlemmar kan bjuda in** är båda inställda på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="575ed-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="575ed-119">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="575ed-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="575ed-120">Observera inställningarna i avsnittet **Begränsningar för samarbete**.</span><span class="sxs-lookup"><span data-stu-id="575ed-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="575ed-121">Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="575ed-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="575ed-122">Om du arbetar med gäster från flera organisationer kanske du vill begränsa deras åtkomst till katalogdata.</span><span class="sxs-lookup"><span data-stu-id="575ed-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="575ed-123">Det gör att de inte kan se vem mer som är gäst i katalogen.</span><span class="sxs-lookup"><span data-stu-id="575ed-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="575ed-124">**Under begränsningar för gästanvändaråtkomst** kan du göra det genom att välja **Gästanvändare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalogobjekt** eller **Gästanvändaråtkomst begränsas till egenskaper och medlemskap i sina egna katalogobjekt**.</span><span class="sxs-lookup"><span data-stu-id="575ed-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="575ed-125">Delningsinställningar på organisationsnivå i SharePoint</span><span class="sxs-lookup"><span data-stu-id="575ed-125">SharePoint organization-level sharing settings</span></span>

<span data-ttu-id="575ed-126">För att personer utanför organisationen ska ha tillgång till ett dokument i SharePoint eller OneDrive måste delningsinställningarna på SharePoint- och OneDrive-organisationsnivå tillåta delning med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="575ed-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="575ed-127">Inställningarna på organisationsnivå för SharePoint avgör vilka inställningar som ska vara tillgängliga för enskilda SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="575ed-127">The organization-level settings for SharePoint determine the settings that will be available for individual SharePoint sites.</span></span> <span data-ttu-id="575ed-128">Webbplatsinställningar får inte vara mer tillåtande än inställningarna på organisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="575ed-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="575ed-129">Inställningen på organisationsnivå för OneDrive avgör vilken delningsnivå som är tillgänglig i användarnas OneDrive-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="575ed-129">The organization-level setting for OneDrive determines the level of sharing that will be available in users' OneDrive libraries.</span></span>

<span data-ttu-id="575ed-130">För SharePoint och OneDrive väljer du Alla om du vill tillåta icke-synkroniserad fil- och **mappdelning.**</span><span class="sxs-lookup"><span data-stu-id="575ed-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="575ed-131">Om du vill säkerställa att personer utanför organisationen måste autentisera väljer du **Nya och befintliga gäster.**</span><span class="sxs-lookup"><span data-stu-id="575ed-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="575ed-132">*Länkar* för alla är det enklaste sättet att dela: personer utanför organisationen kan öppna länken utan autentisering och kan överföra den till andra.</span><span class="sxs-lookup"><span data-stu-id="575ed-132">*Anyone* links is the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="575ed-133">För SharePoint väljer du den mest tillåtande inställningen som behövs av alla webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="575ed-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="575ed-135">För att ange delningsinställningar för SharePoint på organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="575ed-135">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="575ed-136">I det vänstra navigeringsfönstret i administrationscentret för Microsoft 365 går du till **Administrationscenter** och klickar på **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="575ed-136">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="575ed-137">I det vänstra navigeringsfönstret i administrationscentret för SharePoint, under **Principer,** klickar du på **Delning.**</span><span class="sxs-lookup"><span data-stu-id="575ed-137">In the SharePoint admin center, in the left navigation pane, under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="575ed-138">Kontrollera att extern delning för SharePoint eller OneDrive är inställt på **Alla** eller **Nya och befintliga gäster.**</span><span class="sxs-lookup"><span data-stu-id="575ed-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="575ed-139">(Observera att OneDrive-inställningen inte kan vara mer tillåtande än SharePoint-inställningen.)</span><span class="sxs-lookup"><span data-stu-id="575ed-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="575ed-140">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="575ed-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="575ed-141">Standardinställningar för länkar på organisationsnivå i SharePoint</span><span class="sxs-lookup"><span data-stu-id="575ed-141">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="575ed-142">Standardinställningarna för filer och mappar avgör vilket länkalternativ som visas för användarna när de delar en fil eller mapp.</span><span class="sxs-lookup"><span data-stu-id="575ed-142">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="575ed-143">Användare kan ändra länktypen till något av de andra alternativen innan de delar om de vill.</span><span class="sxs-lookup"><span data-stu-id="575ed-143">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="575ed-144">Tänk på att den här inställningen påverkar SharePoint-webbplatser i organisationen och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="575ed-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="575ed-145">Välj en länk från någon av följande typer som sedan väljs som standard när användare delar filer och mappar:</span><span class="sxs-lookup"><span data-stu-id="575ed-145">Choose a link from any of the following types which is then selected by default when users share files and folders:</span></span>

- <span data-ttu-id="575ed-146">**Alla som har länken** – Välj det här alternativet om du förväntar dig att göra många oautherade fil- och mappdelningar.</span><span class="sxs-lookup"><span data-stu-id="575ed-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="575ed-147">Om du vill tillåta att *Alla* -länkar men är bekymrad över oavsiktlig overifierad delning kan du överväga något av de andra alternativen som standard.</span><span class="sxs-lookup"><span data-stu-id="575ed-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="575ed-148">Den här länktypen är bara tillgänglig om du har aktiverat **Alla** delning.</span><span class="sxs-lookup"><span data-stu-id="575ed-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="575ed-149">**Endast personer i organisationen** – Välj det här alternativet om du förväntar dig att de flesta fil- och mappdelningar ska vara med personer inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="575ed-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="575ed-150">**Vissa personer** – Överväg det här alternativet om du förväntar dig att göra mycket fil- och mappdelning med gäster.</span><span class="sxs-lookup"><span data-stu-id="575ed-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="575ed-151">Den här länktypen fungerar med gäster och kräver att de verifieras.</span><span class="sxs-lookup"><span data-stu-id="575ed-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="575ed-153">Så här anger du standardlänkinställningar för SharePoint och OneDrive på organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="575ed-153">To set the SharePoint and OneDrive organization-level default link settings</span></span>

1. <span data-ttu-id="575ed-154">Gå till sidan Delning i administrationscentret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="575ed-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="575ed-155">Välj den standard delningslänk du vill använda under **Fil- och mapplänkar**.</span><span class="sxs-lookup"><span data-stu-id="575ed-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="575ed-156">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="575ed-156">If you made changes, click **Save**.</span></span>

<span data-ttu-id="575ed-157">Om du vill ange behörighet för delningslänken går du till Välj den **behörighet som är markerad som standard för delningslänkar.**</span><span class="sxs-lookup"><span data-stu-id="575ed-157">To set the permission for the sharing link, under **Choose the permission that's selected by default for sharing links.**</span></span>

1. <span data-ttu-id="575ed-158">Välj **Visa** om du inte vill att obehöriga användare ska kunna göra ändringar i filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="575ed-158">Select **View** if you do not want unauthenticated users to make changes to the files and folders.</span></span>
2. <span data-ttu-id="575ed-159">Välj **Redigera** om du vill tillåta att obehöriga användare gör ändringar i filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="575ed-159">Select **Edit** if you want to allow unauthenticated users to make changes to the files and folders.</span></span>

<span data-ttu-id="575ed-160">Observera att ovanstående två förinsändningsalternativ inte bara kan tillämpas för gäster/externa användare utan även för interna användare.</span><span class="sxs-lookup"><span data-stu-id="575ed-160">Note that the above two premission-options can be applied not only for guests/external users but also for internal users.</span></span> <span data-ttu-id="575ed-161">Vilket behörighetsalternativ du väljer avgörs av eget gottfinnande.</span><span class="sxs-lookup"><span data-stu-id="575ed-161">The permission-option you choose is determined by self-discretion.</span></span>

<span data-ttu-id="575ed-162">Ange behörigheter för länkar som tillåter delning med alla</span><span class="sxs-lookup"><span data-stu-id="575ed-162">To set permissions for links that allow sharing with anyone</span></span>

1. <span data-ttu-id="575ed-163">Under de **här länkarna kan ge följande behörigheter:** underfönstret</span><span class="sxs-lookup"><span data-stu-id="575ed-163">Under the **These links can give these permissions:** sub-pane,</span></span> 
    1. <span data-ttu-id="575ed-164">I **listrutan** Filer</span><span class="sxs-lookup"><span data-stu-id="575ed-164">From the **Files** drop-down list,</span></span> 
        - <span data-ttu-id="575ed-165">Välj **Visa och** redigera om du vill tillåta oauthenticerade användare att göra ändringar i filerna.</span><span class="sxs-lookup"><span data-stu-id="575ed-165">Select **View and edit** if you want to allow unauthenticated users to make changes to the files.</span></span>
        - <span data-ttu-id="575ed-166">Välj **Visa** om du inte vill att oauthenticerade användare ska göra ändringar i filerna.</span><span class="sxs-lookup"><span data-stu-id="575ed-166">Select **View** if you do not want unauthenticated users to make changes to the files.</span></span>
    2. <span data-ttu-id="575ed-167">I **listrutan** Mappar</span><span class="sxs-lookup"><span data-stu-id="575ed-167">From the **Folders** drop-down list,</span></span>
        - <span data-ttu-id="575ed-168">Välj **Visa, redigera och ladda** upp om du vill tillåta att icke-obehöriga användare gör ändringar i mapparna.</span><span class="sxs-lookup"><span data-stu-id="575ed-168">Select **View, edit, and upload** if you want to allow unauthenticated users to make changes to the folders.</span></span>
        - <span data-ttu-id="575ed-169">Välj **Visa** om du inte vill att obehöriga användare ska göra ändringar i mapparna.</span><span class="sxs-lookup"><span data-stu-id="575ed-169">Select **View** if you do not want unauthenticated users to make changes to the folders.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="575ed-170">Delningsinställningar på webbplatsnivå i SharePoint</span><span class="sxs-lookup"><span data-stu-id="575ed-170">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="575ed-171">Om du delar filer och mappar som finns på en SharePoint-webbplats måste du kontrollera inställningarna för delning på webbplatsnivå för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="575ed-171">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="575ed-173">Så här anger du delningsinställningar på webbplatsnivå</span><span class="sxs-lookup"><span data-stu-id="575ed-173">To set site-level sharing settings</span></span>

1. <span data-ttu-id="575ed-174">I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="575ed-174">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="575ed-175">Välj den webbplats där du vill dela filer och mappar med gäster.</span><span class="sxs-lookup"><span data-stu-id="575ed-175">Select the site on which you want to share files and folders with guests.</span></span>
3. <span data-ttu-id="575ed-176">Bläddra åt höger på raden (där den valda webbplatsen finns) och klicka någonstans i kolumnen **Extern** delning.</span><span class="sxs-lookup"><span data-stu-id="575ed-176">Scroll right across the row (in which the selected site is present) and click anywhere in the **External sharing** column.</span></span>
4. <span data-ttu-id="575ed-177">På den sida som visas klickar du på **fliken** Principer.</span><span class="sxs-lookup"><span data-stu-id="575ed-177">From the page that pops up, click **Policies** tab.</span></span>
5. <span data-ttu-id="575ed-178">Under fönstret **Extern delning** klickar du på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="575ed-178">Under the **External sharing** pane, click **Edit**.</span></span>
6. <span data-ttu-id="575ed-179">Kontrollera att delning är inställt på **Alla** eller **Nya och befintligt gäster**.</span><span class="sxs-lookup"><span data-stu-id="575ed-179">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
7. <span data-ttu-id="575ed-180">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="575ed-180">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="575ed-181">Bjuda in användare</span><span class="sxs-lookup"><span data-stu-id="575ed-181">Invite users</span></span>

<span data-ttu-id="575ed-182">Inställningarna för gästdelning är nu konfigurerade. så att användare nu kan dela filer och mappar med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="575ed-182">Guest-sharing settings are now configured; so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="575ed-183">Mer information [finns i Dela Filer och mappar i OneDrive](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) och Dela [SharePoint-filer](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) och -mappar.</span><span class="sxs-lookup"><span data-stu-id="575ed-183">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="575ed-184">Se även</span><span class="sxs-lookup"><span data-stu-id="575ed-184">See also</span></span>

[<span data-ttu-id="575ed-185">Metodtips för att dela filer och mappar med overifierade användare</span><span class="sxs-lookup"><span data-stu-id="575ed-185">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="575ed-186">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="575ed-186">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="575ed-187">SharePoint- och OneDrive-integrering med Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="575ed-187">SharePoint and OneDrive integration with Azure AD B2B</span></span>](/sharepoint/sharepoint-azureb2b-integration-preview)