---
title: Samar beta med gäster i ett team
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
description: Lär dig mer om de Microsoft 365-konfigurations steg som behövs för att skapa ett team för aktivitet, konversation och dokument samarbete med gäster i Teams.
ms.openlocfilehash: 34b7d5d47d7fb0c9196beda70184fa6510b6cc33
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780550"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="772bd-103">Samar beta med gäster i ett team</span><span class="sxs-lookup"><span data-stu-id="772bd-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="772bd-104">Om du behöver samar beta med gäster mellan dokument, uppgifter och konversationer rekommenderar vi att du använder Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="772bd-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="772bd-105">Teams innehåller alla samarbets funktioner som är tillgängliga i Office och SharePoint med beständig chatt och en anpassningsbar och en utökning av samarbets verktyg i enhetlig användar upplevelse.</span><span class="sxs-lookup"><span data-stu-id="772bd-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="772bd-106">I den här artikeln går vi igenom de Microsoft 365-inställningar som behövs för att skapa ett team för samarbete med gäster.</span><span class="sxs-lookup"><span data-stu-id="772bd-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="772bd-107">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="772bd-107">Video demonstration</span></span>

<span data-ttu-id="772bd-108">I den här videon visas de konfigurations steg som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="772bd-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="772bd-109">Inställningar för extern samarbete i Azure</span><span class="sxs-lookup"><span data-stu-id="772bd-109">Azure External collaboration settings</span></span>

<span data-ttu-id="772bd-110">Delning i Microsoft 365 regleras på högsta nivå av [B2B-inställningen för externt samarbete i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="772bd-110">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="772bd-111">Om gäst delning är inaktiverat eller begränsat i Azure AD åsidosätter den här inställningen eventuella delnings inställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="772bd-111">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="772bd-112">Kontrol lera inställningarna för externt samarbete för B2B för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="772bd-112">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="772bd-114">Så här anger du inställningar för extern samarbete</span><span class="sxs-lookup"><span data-stu-id="772bd-114">To set external collaboration settings</span></span>

1. <span data-ttu-id="772bd-115">Logga in på Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="772bd-115">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="772bd-116">I det vänstra navigerings fönstret klickar du på **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="772bd-116">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="772bd-117">Klicka på **externa identiteter**.</span><span class="sxs-lookup"><span data-stu-id="772bd-117">Click **External identities**.</span></span>
4. <span data-ttu-id="772bd-118">Klicka på **Inställningar för extern samarbete** i det vänstra navigerings fönstret på skärmen **Kom igång** .</span><span class="sxs-lookup"><span data-stu-id="772bd-118">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="772bd-119">Kontrol lera att **Administratörer och användare i rollen för att bjuda in gäst kan bjuda** in och **medlemmar kan bjuda** in till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="772bd-119">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="772bd-120">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="772bd-120">If you made changes, click **Save**.</span></span>

<span data-ttu-id="772bd-121">Observera inställningarna i avsnittet **samarbets begränsningar** .</span><span class="sxs-lookup"><span data-stu-id="772bd-121">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="772bd-122">Kontrol lera att domänerna för de gäster som du vill samar beta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="772bd-122">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="772bd-123">Om du arbetar med gäster från flera organisationer kan det vara bra att begränsa deras möjligheter att komma åt katalog data.</span><span class="sxs-lookup"><span data-stu-id="772bd-123">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="772bd-124">Detta hindrar dem från att se vem som är gäst i katalogen.</span><span class="sxs-lookup"><span data-stu-id="772bd-124">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="772bd-125">För att göra det, under **gäst användares restriktioner**, väljer du **gäst användare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalog objekt** eller **gäst användares åtkomst är begränsad till egenskaper och medlemskap i deras egna katalog objekt**.</span><span class="sxs-lookup"><span data-stu-id="772bd-125">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="772bd-126">Inställningar för gäst åtkomst för Teams</span><span class="sxs-lookup"><span data-stu-id="772bd-126">Teams guest access settings</span></span>

<span data-ttu-id="772bd-127">Teams har en Master på/av-knapp för gäst åtkomst och en mängd olika inställningar som är tillgängliga för att kontrol lera vad gäster kan göra i ett team.</span><span class="sxs-lookup"><span data-stu-id="772bd-127">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="772bd-128">Huvud växeln, **Tillåt gäst åtkomst i teamen** måste vara **aktive** ras för att gäst åtkomst ska fungera i Teams.</span><span class="sxs-lookup"><span data-stu-id="772bd-128">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="772bd-129">Kontrol lera att gäst åtkomst är aktive rad i Teams och gör eventuella justeringar av gäst inställningarna utifrån dina företags behov.</span><span class="sxs-lookup"><span data-stu-id="772bd-129">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="772bd-130">Tänk på att dessa inställningar påverkar alla team.</span><span class="sxs-lookup"><span data-stu-id="772bd-130">Keep in mind that these settings affect all teams.</span></span>

![Skärmbild av växling för gäståtkomst i Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="772bd-132">Att ange inställningar för gäståtkomst i Teams</span><span class="sxs-lookup"><span data-stu-id="772bd-132">To set Teams guest access settings</span></span>

1. <span data-ttu-id="772bd-133">Logga in på Administrationscenter för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="772bd-133">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="772bd-134">I det vänstra navigerings fönstret klickar du på **Visa alla**.</span><span class="sxs-lookup"><span data-stu-id="772bd-134">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="772bd-135">Under **Administrationscenter** klickar du på **Teams**.</span><span class="sxs-lookup"><span data-stu-id="772bd-135">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="772bd-136">I administrations centret för Teams, i det vänstra navigerings fönstret, expanderar du **Inställningar för hela organisationen** och klickar på **gäst åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="772bd-136">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="772bd-137">Kontrollera att **Tillåt gäståtkomst i Teams** är inställt på **På**.</span><span class="sxs-lookup"><span data-stu-id="772bd-137">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="772bd-138">Gör önskade ändringar i de ytterligare gästinställningarna och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="772bd-138">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="772bd-139">När gästen är aktive rad kan du välja att kontrol lera gäst åtkomsten till enskilda team och deras tillhör ande SharePoint-webbplatser med känslighets etiketter.</span><span class="sxs-lookup"><span data-stu-id="772bd-139">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="772bd-140">Mer information finns i [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="772bd-140">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="772bd-141">Det kan ta upp till 24 timmar innan gäst inställningarna blir aktiva när du har aktiverat det.</span><span class="sxs-lookup"><span data-stu-id="772bd-141">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="772bd-142">Inställningar för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="772bd-142">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="772bd-143">Teams använder Microsoft 365 Groups för grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="772bd-143">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="772bd-144">Inställningarna för gruppen Microsoft 365-grupper måste aktive ras för att gäst åtkomst ska fungera.</span><span class="sxs-lookup"><span data-stu-id="772bd-144">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Skärmbild av gästinställningarna för Microsoft 365-grupper i administrationscenter för Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="772bd-146">Ange inställningar för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="772bd-146">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="772bd-147">Expandera **Inställningar** i det vänstra navigerings fönstret i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="772bd-147">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="772bd-148">Klicka på **org Settings**.</span><span class="sxs-lookup"><span data-stu-id="772bd-148">Click **Org settings**.</span></span>
3. <span data-ttu-id="772bd-149">I listan klickar du på **Microsoft 365 Groups**.</span><span class="sxs-lookup"><span data-stu-id="772bd-149">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="772bd-150">Kontrol lera att **gruppen låt grupp ägarna lägger till personer utanför organisationen till Microsoft 365-grupper som gäster** och **Låt grupp medlemmarna i gruppen för gäst grupps medlemmar** vara markerade.</span><span class="sxs-lookup"><span data-stu-id="772bd-150">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="772bd-151">Om du har gjort ändringarna klickar du på **Spara ändringar**.</span><span class="sxs-lookup"><span data-stu-id="772bd-151">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="772bd-152">Delnings inställningar för SharePoint-organisationnivå</span><span class="sxs-lookup"><span data-stu-id="772bd-152">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="772bd-153">Team innehåll som filer, mappar och listor lagras i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="772bd-153">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="772bd-154">För att gäster ska få till gång till dessa objekt i Teams måste delnings inställningarna för SharePoint på organisations nivå tillåta delning med gäster.</span><span class="sxs-lookup"><span data-stu-id="772bd-154">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="772bd-155">Inställningarna på organisations nivå bestämmer vilka inställningar som är tillgängliga för enskilda webbplatser, till exempel webbplatser som är kopplade till Teams.</span><span class="sxs-lookup"><span data-stu-id="772bd-155">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="772bd-156">Webbplats inställningarna kan inte vara mer tillåtna än inställningarna på organisations nivå.</span><span class="sxs-lookup"><span data-stu-id="772bd-156">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="772bd-157">Om du vill tillåta fil-och mappdelning med oautentiserade personer väljer du **vem som helst**.</span><span class="sxs-lookup"><span data-stu-id="772bd-157">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="772bd-158">Om du vill vara säker på att alla gäster måste autentisera, väljer du **nytt och befintligt gäster**.</span><span class="sxs-lookup"><span data-stu-id="772bd-158">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="772bd-159">Välj den mest tillåtna inställningen som behövs för en webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="772bd-159">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="772bd-161">Så här anger du delnings inställningar för SharePoint på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="772bd-161">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="772bd-162">Klicka på **SharePoint** i det vänstra navigerings fältet **i administrations** centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="772bd-162">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="772bd-163">Expandera **principer** i det vänstra navigerings fönstret i administrations centret för SharePoint och klicka sedan på **delning**.</span><span class="sxs-lookup"><span data-stu-id="772bd-163">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="772bd-164">Kontrol lera att extern delning för SharePoint är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="772bd-164">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="772bd-165">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="772bd-165">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="772bd-166">Inställningar för SharePoint-standardinställningar på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="772bd-166">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="772bd-167">Standardinställningen för fil-och mappikonen styr det länk alternativ som visas för användarna som standard när de delar en fil eller mapp.</span><span class="sxs-lookup"><span data-stu-id="772bd-167">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="772bd-168">Användare kan ändra länktyp till något av de andra alternativen innan de delas, om så önskas.</span><span class="sxs-lookup"><span data-stu-id="772bd-168">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="772bd-169">Tänk på att den här inställningen påverkar alla team och SharePoint-webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="772bd-169">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="772bd-170">Välj någon av följande länk typer som visas som standard när användare delar filer och mappar:</span><span class="sxs-lookup"><span data-stu-id="772bd-170">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="772bd-171">**Vem som helst med länken** – Välj det här alternativet om du förväntar dig att göra en massa delning av filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="772bd-171">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="772bd-172">Om du vill tillåta *alla* länkar, men är bekymrad över oavsiktlig autentisering, bör du överväga något av de andra alternativen som standard.</span><span class="sxs-lookup"><span data-stu-id="772bd-172">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="772bd-173">Den här länk typen är bara tillgänglig om du har aktiverat **någon** delning.</span><span class="sxs-lookup"><span data-stu-id="772bd-173">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="772bd-174">**Endast personer i organisationen** – Välj det här alternativet om du tror att de flesta fil-och mappdelning är med i din organisation.</span><span class="sxs-lookup"><span data-stu-id="772bd-174">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="772bd-175">**Vissa personer** -Överväg det här alternativet om du förväntar dig att göra många fil-och mappdelning med gästerna.</span><span class="sxs-lookup"><span data-stu-id="772bd-175">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="772bd-176">Den här typen av länk fungerar med gäster och kräver att de autentiseras.</span><span class="sxs-lookup"><span data-stu-id="772bd-176">This type of link works with guests and requires them to authenticate.</span></span>
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="772bd-178">Så här anger du inställningar för standard länken för SharePoint på organisations nivå</span><span class="sxs-lookup"><span data-stu-id="772bd-178">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="772bd-179">Gå till sidan delning i administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="772bd-179">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="772bd-180">Under **fil-och mappaktiviteter** väljer du den standard delnings länk som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="772bd-180">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="772bd-181">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="772bd-181">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="772bd-182">Skapa ett team</span><span class="sxs-lookup"><span data-stu-id="772bd-182">Create a team</span></span>

<span data-ttu-id="772bd-183">Nästa steg är att skapa teamet som du planerar att använda för att samar beta med gäster.</span><span class="sxs-lookup"><span data-stu-id="772bd-183">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="772bd-184">Skapa ett team</span><span class="sxs-lookup"><span data-stu-id="772bd-184">To create a team</span></span>
1. <span data-ttu-id="772bd-185">I Teams klickar du på **Anslut eller skapa ett team** längst ned i den vänstra rutan på fliken **team** .</span><span class="sxs-lookup"><span data-stu-id="772bd-185">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="772bd-186">Klicka på **skapa ett team**.</span><span class="sxs-lookup"><span data-stu-id="772bd-186">Click **Create a team**.</span></span>
3. <span data-ttu-id="772bd-187">Klicka på **skapa ett team från början**.</span><span class="sxs-lookup"><span data-stu-id="772bd-187">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="772bd-188">Välj **privat** eller **offentlig**.</span><span class="sxs-lookup"><span data-stu-id="772bd-188">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="772bd-189">Ange ett namn och en beskrivning för gruppen och klicka sedan på **skapa**.</span><span class="sxs-lookup"><span data-stu-id="772bd-189">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="772bd-190">Klicka på **hoppa över**.</span><span class="sxs-lookup"><span data-stu-id="772bd-190">Click **Skip**.</span></span>

<span data-ttu-id="772bd-191">Vi bjuder in användare senare.</span><span class="sxs-lookup"><span data-stu-id="772bd-191">We'll invite users later.</span></span> <span data-ttu-id="772bd-192">Sedan är det viktigt att kontrol lera delnings inställningarna på webbplats nivå för SharePoint-webbplatsen som är kopplad till gruppen.</span><span class="sxs-lookup"><span data-stu-id="772bd-192">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="772bd-193">Delnings inställningar på SharePoint-webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="772bd-193">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="772bd-194">Kontrol lera inställningarna för delning av webbplats nivå för att se till att de tillåter åtkomst typen för det här teamet.</span><span class="sxs-lookup"><span data-stu-id="772bd-194">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="772bd-195">Om du till exempel ställer in inställningar på organisations nivå till **vem som helst**, men vill att alla gäster ska autentiseras för det här teamet, kontrollerar du att inställningarna för delning av webbplats nivå är inställda på **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="772bd-195">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="772bd-197">Ange delnings inställningar på webbplats nivå</span><span class="sxs-lookup"><span data-stu-id="772bd-197">To set site-level sharing settings</span></span>
1. <span data-ttu-id="772bd-198">I administrations centret för SharePoint, i det vänstra navigerings fönstret, expanderar du **webbplatser** och klickar på **aktiva webbplatser**.</span><span class="sxs-lookup"><span data-stu-id="772bd-198">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="772bd-199">Välj webbplatsen för det team som du just har skapat.</span><span class="sxs-lookup"><span data-stu-id="772bd-199">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="772bd-200">Klicka på... och välj **dela**.</span><span class="sxs-lookup"><span data-stu-id="772bd-200">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="772bd-201">Kontrol lera att delning är inställt på **vem som helst** eller **nya och befintliga gäster**.</span><span class="sxs-lookup"><span data-stu-id="772bd-201">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="772bd-202">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="772bd-202">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="772bd-203">Bjuda in användare</span><span class="sxs-lookup"><span data-stu-id="772bd-203">Invite users</span></span>

<span data-ttu-id="772bd-204">Inställningar för gäst delning är nu konfigurerade så att du kan börja lägga till interna användare och gäster i gruppen.</span><span class="sxs-lookup"><span data-stu-id="772bd-204">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="772bd-205">Bjuda in interna användare till ett team</span><span class="sxs-lookup"><span data-stu-id="772bd-205">To invite internal users to a team</span></span>
1. <span data-ttu-id="772bd-206">I gruppen klickar du på **fler alternativ** ( **\*\*\*** ) och sedan på **Lägg till medlem**.</span><span class="sxs-lookup"><span data-stu-id="772bd-206">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="772bd-207">Skriv namnet på den person som du vill bjuda in.</span><span class="sxs-lookup"><span data-stu-id="772bd-207">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="772bd-208">Klicka på **Lägg till** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="772bd-208">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="772bd-209">Så här bjuder du in gäster till ett team</span><span class="sxs-lookup"><span data-stu-id="772bd-209">To invite guests to a team</span></span>
1. <span data-ttu-id="772bd-210">I gruppen klickar du på **fler alternativ** ( **\*\*\*** ) och sedan på **Lägg till medlem**.</span><span class="sxs-lookup"><span data-stu-id="772bd-210">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="772bd-211">Skriv e-postadressen för den gäst som du vill bjuda in.</span><span class="sxs-lookup"><span data-stu-id="772bd-211">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="772bd-212">Klicka på **Redigera gäst information**.</span><span class="sxs-lookup"><span data-stu-id="772bd-212">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="772bd-213">Skriv in gästens namn och klicka på bock markeringen.</span><span class="sxs-lookup"><span data-stu-id="772bd-213">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="772bd-214">Klicka på **Lägg till** och sedan på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="772bd-214">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="772bd-215">Se även</span><span class="sxs-lookup"><span data-stu-id="772bd-215">See also</span></span>

[<span data-ttu-id="772bd-216">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="772bd-216">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="772bd-217">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="772bd-217">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="772bd-218">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="772bd-218">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="772bd-219">Skapa ett B2B-extranät med hanterade gäster</span><span class="sxs-lookup"><span data-stu-id="772bd-219">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="772bd-220">SharePoint och OneDrive-integrering med Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="772bd-220">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="772bd-221">Delnings alternativ är nedtonad när du delar från SharePoint eller OneDrive</span><span class="sxs-lookup"><span data-stu-id="772bd-221">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
