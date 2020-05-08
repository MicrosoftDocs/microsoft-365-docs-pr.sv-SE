---
title: Samarbeta med gäster i ett dokument
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- M365solutions
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: I den här artikeln får du lära dig hur du samarbetar med gäster i ett dokument i SharePoint och OneDrive.
ms.openlocfilehash: 82b9d6356144d6d465c7c94f58ec60fe96a1397a
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159997"
---
# <a name="collaborate-with-guests-on-a-document"></a><span data-ttu-id="8a778-103">Samarbeta med gäster i ett dokument</span><span class="sxs-lookup"><span data-stu-id="8a778-103">Collaborate with guests on a document</span></span>

<span data-ttu-id="8a778-104">Om du behöver samarbeta med personer utanför organisationen i dokument i SharePoint eller OneDrive kan du skicka en delningslänk till dokumentet.</span><span class="sxs-lookup"><span data-stu-id="8a778-104">If you need to collaborate with people outside your organization on documents in SharePoint or OneDrive, you can send them a sharing link to the document.</span></span> <span data-ttu-id="8a778-105">I den här artikeln går vi igenom de konfigurationssteg för Microsoft 365 som krävs för att konfigurera delningslänkar för SharePoint och OneDrive för din organisations behov.</span><span class="sxs-lookup"><span data-stu-id="8a778-105">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up sharing links for SharePoint and OneDrive for the needs of your organization.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="8a778-106">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="8a778-106">Video demonstration</span></span>

<span data-ttu-id="8a778-107">I det här videoklippet visas de konfigurationssteg som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="8a778-107">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="8a778-108">Inställningar för Azure-organisationsrelationer</span><span class="sxs-lookup"><span data-stu-id="8a778-108">Azure Organizational relationships settings</span></span>

<span data-ttu-id="8a778-109">Delning i Microsoft 365 styrs på högsta nivå av organisationsrelationerinställningarna i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8a778-109">Sharing in Microsoft 365 is governed at its highest level by the organizational relationships settings in Azure Active Directory.</span></span> <span data-ttu-id="8a778-110">Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter detta alla delningsinställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a778-110">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="8a778-111">Kontrollera inställningarna för organisationsrelationer för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="8a778-111">Check the organizational relationships settings to ensure that sharing with guests is not blocked.</span></span>

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="8a778-113">Så här anger du inställningar för organisationsrelationer</span><span class="sxs-lookup"><span data-stu-id="8a778-113">To set organizational relationship settings</span></span>

1. <span data-ttu-id="8a778-114">Logga in på [https://portal.azure.com](https://portal.azure.com)Microsoft Azure på .</span><span class="sxs-lookup"><span data-stu-id="8a778-114">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="8a778-115">Klicka på Azure **Active Directory**i den vänstra navigeringen .</span><span class="sxs-lookup"><span data-stu-id="8a778-115">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="8a778-116">Klicka på **Organisationsrelationer**i **fönstret Översikt.**</span><span class="sxs-lookup"><span data-stu-id="8a778-116">In the **Overview** pane, click **Organizational relationships**.</span></span>
4. <span data-ttu-id="8a778-117">Klicka på **Inställningar**i fönstret **Organisationsrelationer** .</span><span class="sxs-lookup"><span data-stu-id="8a778-117">In the **Organizational relationships** pane, click **Settings**.</span></span>
5. <span data-ttu-id="8a778-118">Se till att **administratörer och användare i gäst inbjudna roll kan bjuda in** och medlemmar kan bjuda **in** är båda inställda på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8a778-118">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="8a778-119">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8a778-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="8a778-120">Observera inställningarna i avsnittet **Samarbetsbegränsningar.**</span><span class="sxs-lookup"><span data-stu-id="8a778-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="8a778-121">Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="8a778-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="8a778-122">Delningsinställningar för SharePoint-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="8a778-122">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="8a778-123">För att personer utanför organisationen ska ha åtkomst till ett dokument i SharePoint eller OneDrive måste delningsinställningarna för SharePoint och OneDrive-organisationsnivå tillåta delning med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="8a778-123">In order for people outside your organization to have access to a document in SharePoint or OneDrive, the SharePoint and OneDrive organization-level sharing settings must allow for sharing with people outside your organization.</span></span>

<span data-ttu-id="8a778-124">Inställningarna på organisationsnivå för SharePoint avgör vilka inställningar som är tillgängliga för enskilda SharePoint-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="8a778-124">The organization-level settings for SharePoint determine what settings are available for individual SharePoint sites.</span></span> <span data-ttu-id="8a778-125">Webbplatsinställningarna kan inte vara mer tillåtande än inställningarna på organisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="8a778-125">Site settings cannot be more permissive than the organization-level settings.</span></span> <span data-ttu-id="8a778-126">Inställningen på organisationsnivå för OneDrive avgör vilken delningsnivå som är tillgänglig i användarnas OneDrive-bibliotek.</span><span class="sxs-lookup"><span data-stu-id="8a778-126">The organization-level setting for OneDrive determines what level of sharing is available in users' OneDrive libraries.</span></span>

<span data-ttu-id="8a778-127">Om du vill tillåta oautentiserade fil- och mappdelning för SharePoint och OneDrive väljer du **Alla**.</span><span class="sxs-lookup"><span data-stu-id="8a778-127">For SharePoint and OneDrive, if you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="8a778-128">Om du vill vara säkra på att personer utanför organisationen måste autentisera väljer du **Nya och befintliga gäster.**</span><span class="sxs-lookup"><span data-stu-id="8a778-128">If you want to ensure that people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="8a778-129">*Alla* länkar är det enklaste sättet att dela: personer utanför organisationen kan öppna länken utan autentisering och är fria att vidarebefordra den till andra.</span><span class="sxs-lookup"><span data-stu-id="8a778-129">*Anyone* links are the easiest way to share: people outside your organization can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="8a778-130">För SharePoint väljer du den mest tillåtande inställningen som behövs av en webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8a778-130">For SharePoint, choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="8a778-132">Så här anger du delningsinställningar för SharePoint-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="8a778-132">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="8a778-133">Klicka på **SharePoint**under **Administrationscenter i administrationscentret**för Microsoft 365, i den vänstra navigeringen.</span><span class="sxs-lookup"><span data-stu-id="8a778-133">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="8a778-134">I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="8a778-134">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="8a778-135">Kontrollera att extern delning för SharePoint eller OneDrive är inställt på **Alla** eller **Nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="8a778-135">Ensure that external sharing for SharePoint or OneDrive is set to **Anyone** or **New and existing guests**.</span></span> <span data-ttu-id="8a778-136">(Observera att OneDrive-inställningen inte kan vara mer tillåtande än SharePoint-inställningen.)</span><span class="sxs-lookup"><span data-stu-id="8a778-136">(Note that the OneDrive setting cannot be more permissive than the SharePoint setting.)</span></span>
4. <span data-ttu-id="8a778-137">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8a778-137">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="8a778-138">Standardlänkinställningar för sharepoint-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="8a778-138">SharePoint organization level default link settings</span></span>

<span data-ttu-id="8a778-139">Standardinställningarna för fil- och mapplänk avgör vilket länkalternativ som visas för användaren som standard när de delar en fil eller mapp.</span><span class="sxs-lookup"><span data-stu-id="8a778-139">The default file and folder link settings determine which link option is shown to the user by default when they share a file or folder.</span></span> <span data-ttu-id="8a778-140">Användare kan ändra länktypen till ett av de andra alternativen innan de delar om så önskas.</span><span class="sxs-lookup"><span data-stu-id="8a778-140">Users can change the link type to one of the other options before sharing if desired.</span></span>

<span data-ttu-id="8a778-141">Tänk på att den här inställningen påverkar SharePoint-webbplatser i organisationen och OneDrive.</span><span class="sxs-lookup"><span data-stu-id="8a778-141">Keep in mind that this setting affects SharePoint sites in your organization, as well as OneDrive.</span></span>

<span data-ttu-id="8a778-142">Välj den typ av länk som är markerad som standard när användare delar filer och mappar:</span><span class="sxs-lookup"><span data-stu-id="8a778-142">Choose the type of link that's selected by default when users share files and folders:</span></span>

- <span data-ttu-id="8a778-143">**Alla med länken** - Välj det här alternativet om du förväntar dig att göra en hel del oautentiserade fil- och mappdelning.</span><span class="sxs-lookup"><span data-stu-id="8a778-143">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated file and folder sharing.</span></span> <span data-ttu-id="8a778-144">Om du vill tillåta *någon* länkar men är oroliga för oavsiktlig oautentiserade delning, överväga ett av de andra alternativen som standard.</span><span class="sxs-lookup"><span data-stu-id="8a778-144">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="8a778-145">Den här länktypen är bara tillgänglig om du har aktiverat **Alla delar.**</span><span class="sxs-lookup"><span data-stu-id="8a778-145">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="8a778-146">**Endast personer i organisationen** – Välj det här alternativet om du förväntar dig att de flesta fil- och mappdelning ska vara med personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="8a778-146">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="8a778-147">**Specifika personer** - Tänk på det här alternativet om du förväntar dig att göra en hel del fil- och mappdelning med gäster.</span><span class="sxs-lookup"><span data-stu-id="8a778-147">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="8a778-148">Denna typ av länk fungerar med gäster och kräver att de autentisera.</span><span class="sxs-lookup"><span data-stu-id="8a778-148">This type of link works with guests and requires them to authenticate.</span></span>
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="8a778-150">Så här anger du standardlänkinställningar för Standardlänkinställningar för SharePoint- och OneDrive-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="8a778-150">To set the SharePoint and OneDrive organization level default link settings</span></span>

1. <span data-ttu-id="8a778-151">Navigera till sidan Delning i administrationscentret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a778-151">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="8a778-152">Under **Fil- och mapplänkar**väljer du den standarddelningslänk som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="8a778-152">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="8a778-153">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8a778-153">If you made changes, click **Save**.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="8a778-154">Delningsinställningar för SharePoint-webbplatsnivå</span><span class="sxs-lookup"><span data-stu-id="8a778-154">SharePoint site level sharing settings</span></span>

<span data-ttu-id="8a778-155">Om du delar filer och fodlers på en SharePoint-webbplats måste du också kontrollera delningsinställningarna på webbplatsnivå för den webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8a778-155">If you're sharing files and fodlers that are in a SharePoint site, you also need to check the site-level sharing settings for that site.</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="8a778-157">Så här anger du delningsinställningar på webbplatsnivå</span><span class="sxs-lookup"><span data-stu-id="8a778-157">To set site-level sharing settings</span></span>
1. <span data-ttu-id="8a778-158">I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="8a778-158">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="8a778-159">Välj den webbplats som du just skapade.</span><span class="sxs-lookup"><span data-stu-id="8a778-159">Select the site that you just created.</span></span>
3. <span data-ttu-id="8a778-160">Klicka på **Delning** i menyfliksområdet.</span><span class="sxs-lookup"><span data-stu-id="8a778-160">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="8a778-161">Se till att delning är inställt **på Vem som helst** eller Nya och befintliga **gäster**.</span><span class="sxs-lookup"><span data-stu-id="8a778-161">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="8a778-162">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8a778-162">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="8a778-163">Bjud in användare</span><span class="sxs-lookup"><span data-stu-id="8a778-163">Invite users</span></span>

<span data-ttu-id="8a778-164">Gästdelningsinställningarna är nu konfigurerade, så att användarna nu kan dela filer och mappar med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="8a778-164">Guest sharing settings are now configured, so users can now share files and folders with people outside your organization.</span></span> <span data-ttu-id="8a778-165">Mer information finns i [Dela OneDrive-filer och -mappar](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) och [Dela SharePoint-filer eller sharepoint-mappar.](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c)</span><span class="sxs-lookup"><span data-stu-id="8a778-165">See [Share OneDrive files and folders](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) and [Share SharePoint files or folders](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a778-166">Se även</span><span class="sxs-lookup"><span data-stu-id="8a778-166">See Also</span></span>

[<span data-ttu-id="8a778-167">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="8a778-167">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="8a778-168">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="8a778-168">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)