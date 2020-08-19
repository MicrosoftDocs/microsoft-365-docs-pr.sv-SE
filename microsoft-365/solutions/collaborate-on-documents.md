---
title: Samar beta med gäster i ett dokument
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: I den här artikeln får du lära dig hur du samarbetar med gäster i ett dokument i SharePoint och OneDrive.
ms.openlocfilehash: 98eea8fe9c613aef3e24f9e4bb6746ddc9a527ab
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798276"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="7fbe8-103">Samar beta med gäster i ett dokument</span><span class="sxs-lookup"><span data-stu-id="7fbe8-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="7fbe8-104">Om du behöver samar beta med personer utanför organisationen för dokument i SharePoint eller OneDrive kan du skicka en delnings länk till dokumentet.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing link to the document.</span></span> <span data-ttu-id="7fbe8-105">I den här artikeln går vi igenom de Microsoft 365-inställningar som krävs för att konfigurera delnings Länkar för SharePoint och OneDrive för organisationen.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="7fbe8-106">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="7fbe8-106">Video demonstration</span></span>

<span data-ttu-id="7fbe8-107">I den här videon visas de konfigurations steg som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="7fbe8-108">Inställningar för Azure organisations relationer</span><span class="sxs-lookup"><span data-stu-id="7fbe8-108">Azure Organizational relationships settings</span></span>

<span data-ttu-id="7fbe8-109">Delning i Microsoft 365 regleras på högsta nivå av [organisations Relations inställningarna i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="7fbe8-109">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="7fbe8-110">Om gäst delning är inaktiverat eller begränsat i Azure AD åsidosätter detta eventuella delnings inställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-110">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="7fbe8-111">Kontrol lera inställningarna för organisations relationer för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="7fbe8-113">Så här anger du inställningar för organisations relationer</span><span class="sxs-lookup"><span data-stu-id="7fbe8-113">To set organizational relationship settings</span></span>

1. <span data-ttu-id="7fbe8-114">Logga in på Microsoft Azure på [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="7fbe8-114">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="7fbe8-115">I det vänstra navigerings fältet klickar du på **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-115">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="7fbe8-116">I fönstret **Översikt** klickar du på **organisations relationer**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-116">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="7fbe8-117">Klicka på **Inställningar**i fönstret **organisations relationer** .</span><span class="sxs-lookup"><span data-stu-id="7fbe8-117">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="7fbe8-118">Kontrol lera att **Administratörer och användare i rollen för att bjuda in gäst kan bjuda** in och **medlemmar kan bjuda** in till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="7fbe8-119">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="7fbe8-120">Observera inställningarna i avsnittet **samarbets begränsningar** .</span><span class="sxs-lookup"><span data-stu-id="7fbe8-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="7fbe8-121">Kontrol lera att domänerna för de gäster som du vill samar beta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="7fbe8-122">Om du arbetar med gäster från flera organisationer kan det vara bra att begränsa deras möjligheter att komma åt katalog data.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="7fbe8-123">Detta hindrar dem från att se vem som är gäst i katalogen.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="7fbe8-124">För att göra det, under **gäst användares restriktioner**, väljer du **gäst användare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalog objekt** eller **gäst användares åtkomst är begränsad till egenskaper och medlemskap i deras egna katalog objekt**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="7fbe8-125">Delnings inställningar för SharePoint-organisationnivå</span><span class="sxs-lookup"><span data-stu-id="7fbe8-125">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="7fbe8-126">För att personer utanför din organisation ska ha till gång till ett dokument i SharePoint eller OneDrive måste delnings inställningarna för SharePoint och OneDrive tillåta delning med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-126">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="7fbe8-127">Inställningarna på organisations nivå för SharePoint avgör vilka inställningar som är tillgängliga för enskilda SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-127">The organization-level settings for SharePoint determine what settings are available for individual SharePoint sites.</span></span> <span data-ttu-id="7fbe8-128">Webbplats inställningarna kan inte vara mer tillåtna än inställningarna på organisations nivå.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-128">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="7fbe8-129">Inställningen på organisations nivå för OneDrive bestämmer vilken delnings nivå som är tillgänglig i användarnas OneDrive-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-129">The organization-level setting for OneDrive determines what level of sharing is available in users' OneDrive libraries.</span></span>

<span data-ttu-id="7fbe8-130">Om du vill tillåta icke verifierade fil-och mappdelning för SharePoint och OneDrive väljer du **vem som helst**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-130">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="7fbe8-131">Om du vill vara säker på att personer utanför din organisation måste autentisera, väljer du **nytt och befintligt gäster**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-131">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="7fbe8-132">*Alla* länkar är det enklaste sättet att dela: personer utanför din organisation kan öppna länken utan att det är möjligt att överföra den till andra.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-132">*Anyone* links are the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="7fbe8-133">För SharePoint väljer du den mest krävda inställning som behövs av någon webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-133">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="7fbe8-135">Så här anger du delnings inställningar för SharePoint-organisationnivå</span><span class="sxs-lookup"><span data-stu-id="7fbe8-135">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="7fbe8-136">Klicka på **SharePoint**i det vänstra navigerings fältet **i administrations**centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-136">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="7fbe8-137">I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-137">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="7fbe8-138">Kontrol lera att extern delning för SharePoint eller OneDrive är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-138">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="7fbe8-139">(Observera att OneDrive-inställningen inte kan bli mer tillåtna än SharePoint-inställningen.)</span><span class="sxs-lookup"><span data-stu-id="7fbe8-139">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="7fbe8-140">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-140">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="7fbe8-141">Standardinställningar för inställningar för SharePoint-organisations nivå</span><span class="sxs-lookup"><span data-stu-id="7fbe8-141">SharePoint organization level default link settings</span></span>

<span data-ttu-id="7fbe8-142">Standardinställningen för fil-och mappikonen bestämmer vilken länk som visas som standard för användaren när de delar en fil eller mapp.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-142">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="7fbe8-143">Användare kan ändra länktyp till något av de andra alternativen innan de delas om så önskas.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-143">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="7fbe8-144">Tänk på att den här inställningen påverkar SharePoint-webbplatser i din organisation samt OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-144">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="7fbe8-145">Välj den typ av länk som är markerad som standard när användarna delar filer och mappar:</span><span class="sxs-lookup"><span data-stu-id="7fbe8-145">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="7fbe8-146">**Vem som helst med länken** – Välj det här alternativet om du förväntar dig att göra mängder av overifierade fil-och mappdelning.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-146">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="7fbe8-147">Om du vill tillåta *alla* länkar, men är bekymrad över oavsiktlig autentisering, bör du överväga något av de andra alternativen som standard.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-147">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="7fbe8-148">Den här länk typen är bara tillgänglig om du har aktiverat **någon** delning.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-148">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="7fbe8-149">**Endast personer i organisationen** – Välj det här alternativet om du tror att de flesta fil-och mappdelning är med i din organisation.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-149">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="7fbe8-150">**Vissa personer** -Överväg det här alternativet om du förväntar dig att göra många fil-och mappdelning med gästerna.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-150">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="7fbe8-151">Den här typen av länk fungerar med gäster och kräver att de autentiseras.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-151">This type of link works with guests and requires them to authenticate.</span></span>
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="7fbe8-153">Så här anger du inställningar för SharePoint-och OneDrive-organisations nivå</span><span class="sxs-lookup"><span data-stu-id="7fbe8-153">To set the SharePoint and OneDrive organization level default link settings</span></span>

1. <span data-ttu-id="7fbe8-154">Gå till sidan delning i administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-154">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="7fbe8-155">Under **fil-och mappaktiviteter**väljer du den standard delnings länk som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-155">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="7fbe8-156">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-156">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="7fbe8-157">Delnings inställningar för SharePoint-webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="7fbe8-157">SharePoint site level sharing settings</span></span>

<span data-ttu-id="7fbe8-158">Om du delar filer och mappar på en SharePoint-webbplats måste du också kontrol lera delnings inställningarna för webbplatsen på webbplats nivå.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-158">If you're sharing files and folders that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="7fbe8-160">Ange delnings inställningar på webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="7fbe8-160">To set site-level sharing settings</span></span>
1. <span data-ttu-id="7fbe8-161">I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-161">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="7fbe8-162">Välj den webbplats du just har skapat.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-162">Select the site that you just created.</span></span>
3. <span data-ttu-id="7fbe8-163">Klicka på **Delning** i menyfliksområdet.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-163">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="7fbe8-164">Kontrol lera att delning är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-164">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="7fbe8-165">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-165">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="7fbe8-166">Bjuda in användare</span><span class="sxs-lookup"><span data-stu-id="7fbe8-166">Invite users</span></span>

<span data-ttu-id="7fbe8-167">Inställningar för gäst delning är nu konfigurerade så att användarna kan nu dela filer och mappar med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="7fbe8-167">Guest sharing settings are now configured, so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="7fbe8-168">Mer information finns i [dela OneDrive-filer och-mappar](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) och [dela SharePoint-filer eller-mappar](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) .</span><span class="sxs-lookup"><span data-stu-id="7fbe8-168">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fbe8-169">Se även</span><span class="sxs-lookup"><span data-stu-id="7fbe8-169">See Also</span></span>

[<span data-ttu-id="7fbe8-170">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="7fbe8-170">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="7fbe8-171">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="7fbe8-171">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)
