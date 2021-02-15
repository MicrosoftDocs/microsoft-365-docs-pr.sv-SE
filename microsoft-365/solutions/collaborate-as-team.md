---
title: Samarbeta med gäster i ett team
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
description: Läs mer om de konfigurationssteg för Microsoft 365 som krävs för att skapa ett team för uppgift, konversation och dokumentation med gäster i Teams.
ms.openlocfilehash: 66c5692dd8cd233d8b3639f8ce0755ce51b60c0a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233080"
---
# <a name="collaborate-with-guests-in-a-team"></a><span data-ttu-id="e1980-103">Samarbeta med gäster i ett team</span><span class="sxs-lookup"><span data-stu-id="e1980-103">Collaborate with guests in a team</span></span>

<span data-ttu-id="e1980-104">Om du behöver samarbeta med gäster i dokument, uppgifter och konversationer rekommenderar vi att du använder Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e1980-104">If you need to collaborate with guests across documents, tasks, and conversations, we recommend using Microsoft Teams.</span></span> <span data-ttu-id="e1980-105">Teams innehåller alla samarbetsfunktioner som är tillgängliga i Office och SharePoint med fortlöpande chatt och en anpassningsbar och utökningsbar uppsättning samarbetsverktyg i en enhetlig användarupplevelse.</span><span class="sxs-lookup"><span data-stu-id="e1980-105">Teams provides all of the collaboration features available in Office and SharePoint with persistent chat and a customizable and extensible set of collaboration tools in a unified user experience.</span></span>

<span data-ttu-id="e1980-106">I den här artikeln går vi igenom de konfigurationssteg för Microsoft 365 som krävs för att skapa ett team för samarbete med gäster.</span><span class="sxs-lookup"><span data-stu-id="e1980-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a team for collaboration with guests.</span></span> <span data-ttu-id="e1980-107">När du har konfigurerat gäståtkomst kan du bjuda in gäster till team genom att följa stegen i Lägga till [gäster i ett team i Teams.](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="e1980-107">Once you have configured guest access, you can invite guests to teams by following the steps in [Add guests to a team in Teams](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="e1980-108">Videodemonstration</span><span class="sxs-lookup"><span data-stu-id="e1980-108">Video demonstration</span></span>

<span data-ttu-id="e1980-109">Den här videon visar konfigurationsstegen som beskrivs i det här dokumentet.</span><span class="sxs-lookup"><span data-stu-id="e1980-109">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a><span data-ttu-id="e1980-110">Inställningar för externt samarbete i Azure</span><span class="sxs-lookup"><span data-stu-id="e1980-110">Azure External collaboration settings</span></span>

<span data-ttu-id="e1980-111">Delning i Microsoft 365 styrs på högsta nivå av [inställningarna för B2B externt samarbete i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="e1980-111">Sharing in Microsoft 365 is governed at its highest level by the [B2B external collaboration settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="e1980-112">Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter den här inställningen alla delningsinställningar som du konfigurerar i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1980-112">If guest sharing is disabled or restricted in Azure AD, this setting overrides any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="e1980-113">Kontrollera inställningarna för B2B externt samarbete för att säkerställa att delning med gäster inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="e1980-113">Check the B2B external collaboration settings settings to ensure that sharing with guests is not blocked.</span></span>

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="e1980-115">Så här ställer du in inställningar för externt samarbete</span><span class="sxs-lookup"><span data-stu-id="e1980-115">To set external collaboration settings</span></span>

1. <span data-ttu-id="e1980-116">Logga in på Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="e1980-116">Log in to Azure Active Directory at [https://aad.portal.azure.com](https://aad.portal.azure.com).</span></span>
2. <span data-ttu-id="e1980-117">Klicka på Azure Active Directory i det **vänstra navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="e1980-117">In the left navigation pane, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="e1980-118">Klicka **på Externa identiteter.**</span><span class="sxs-lookup"><span data-stu-id="e1980-118">Click **External identities**.</span></span>
4. <span data-ttu-id="e1980-119">Klicka på **Inställningar för externt** samarbete i det vänstra navigeringsfönstret på kom **igång-skärmen.**</span><span class="sxs-lookup"><span data-stu-id="e1980-119">On the **Get started** screen, in the left navigation pane, click **External collaboration settings**.</span></span>
5. <span data-ttu-id="e1980-120">Se till **att administratörer och användare med gästrollen som** inbjudna kan bjuda in och att medlemmar kan bjuda **in** är båda inställda på **Ja.**</span><span class="sxs-lookup"><span data-stu-id="e1980-120">Ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
6. <span data-ttu-id="e1980-121">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e1980-121">If you made changes, click **Save**.</span></span>

<span data-ttu-id="e1980-122">Observera inställningarna i avsnittet **Begränsningar för** samarbete.</span><span class="sxs-lookup"><span data-stu-id="e1980-122">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="e1980-123">Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.</span><span class="sxs-lookup"><span data-stu-id="e1980-123">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="e1980-124">Om du arbetar med gäster från flera organisationer kanske du vill begränsa deras möjlighet att komma åt katalogdata.</span><span class="sxs-lookup"><span data-stu-id="e1980-124">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="e1980-125">Det gör att de inte kan se vilka andra som är gäster i katalogen.</span><span class="sxs-lookup"><span data-stu-id="e1980-125">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="e1980-126">Det gör du genom att **välja** Gästanvändare har begränsad åtkomst till egenskaper och medlemskap i katalogobjektsinställningar under begränsningar för gästanvändaråtkomst, och åtkomsten till gästanvändare begränsas till egenskaper och medlemskap i egna **katalogobjekt.** </span><span class="sxs-lookup"><span data-stu-id="e1980-126">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="teams-guest-access-settings"></a><span data-ttu-id="e1980-127">Inställningar för gäståtkomst i Teams</span><span class="sxs-lookup"><span data-stu-id="e1980-127">Teams guest access settings</span></span>

<span data-ttu-id="e1980-128">Teams har en master på/av-knapp för gäståtkomst och en mängd olika inställningar som är tillgängliga för att styra vad gäster kan göra i ett team.</span><span class="sxs-lookup"><span data-stu-id="e1980-128">Teams has a master on/off switch for guest access and a variety of settings available to control what guests can do in a team.</span></span> <span data-ttu-id="e1980-129">Huvudväxeln, **Tillåt gäståtkomst i Teams måste** vara **på** för att gäståtkomst ska fungera i Teams.</span><span class="sxs-lookup"><span data-stu-id="e1980-129">The master switch, **Allow guest access in Teams** must be **On** for guest access to work in Teams.</span></span>

<span data-ttu-id="e1980-130">Kontrollera att gäståtkomst är aktiverat i Teams och gör eventuella justeringar i gästinställningarna utifrån dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="e1980-130">Check to ensure that guest access is enabled in Teams and make any adjustment to the guest settings based on your business needs.</span></span> <span data-ttu-id="e1980-131">Tänk på att de här inställningarna påverkar alla team.</span><span class="sxs-lookup"><span data-stu-id="e1980-131">Keep in mind that these settings affect all teams.</span></span>

![Skärmbild av växling för gäståtkomst i Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="e1980-133">Att ange inställningar för gäståtkomst i Teams</span><span class="sxs-lookup"><span data-stu-id="e1980-133">To set Teams guest access settings</span></span>

1. <span data-ttu-id="e1980-134">Logga in på Administrationscenter för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e1980-134">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="e1980-135">Klicka på Visa alla i **navigeringsrutan till vänster.**</span><span class="sxs-lookup"><span data-stu-id="e1980-135">In the left navigation pane, click **Show all**.</span></span>
3. <span data-ttu-id="e1980-136">Under **Administrationscenter** klickar du på **Teams**.</span><span class="sxs-lookup"><span data-stu-id="e1980-136">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="e1980-137">I det vänstra navigeringsfönstret i administrationscentret för Teams expanderar du **organisationsomfattande inställningar och** klickar på **Gäståtkomst.**</span><span class="sxs-lookup"><span data-stu-id="e1980-137">In the Teams admin center, in the left navigation pane, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="e1980-138">Kontrollera att **Tillåt gäståtkomst i Teams** är inställt på **På**.</span><span class="sxs-lookup"><span data-stu-id="e1980-138">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="e1980-139">Gör önskade ändringar i de ytterligare gästinställningarna och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e1980-139">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

<span data-ttu-id="e1980-140">När gäståtkomst i Teams har aktiverats kan du, om du vill, styra gäståtkomsten till enskilda team och deras associerade SharePoint-webbplatser med hjälp av känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="e1980-140">Once Teams guest access is turned on, you can optionally control guest access to individual teams and their associated SharePoint sites using sensitivity labels.</span></span> <span data-ttu-id="e1980-141">Mer information finns i [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="e1980-141">For more information, see [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

> [!NOTE]
> <span data-ttu-id="e1980-142">Det kan ta upp till 24 timmar innan Teams gästinställningar aktiveras när du aktiverar det.</span><span class="sxs-lookup"><span data-stu-id="e1980-142">It may take up to twenty-four hours for the Teams guest settings to become active after you turn it on.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="e1980-143">Gästinställningar i Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="e1980-143">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="e1980-144">Teams använder Microsoft 365-grupper för teammedlemskap.</span><span class="sxs-lookup"><span data-stu-id="e1980-144">Teams uses Microsoft 365 Groups for team membership.</span></span> <span data-ttu-id="e1980-145">Gästinställningarna i Microsoft 365 Groups måste vara aktiverat för att gäståtkomst i Teams ska fungera.</span><span class="sxs-lookup"><span data-stu-id="e1980-145">The Microsoft 365 Groups guest settings must be turned on in order for guest access in Teams to work.</span></span>

![Skärmbild av gästinställningarna för Microsoft 365-grupper i administrationscenter för Microsoft 365](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="e1980-147">Så här anger du gästinställningar för Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="e1980-147">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="e1980-148">I det vänstra navigeringsfönstret i administrationscentret för Microsoft 365 expanderar du **Inställningar.**</span><span class="sxs-lookup"><span data-stu-id="e1980-148">In the Microsoft 365 admin center, in the left navigation pane, expand **Settings**.</span></span>
2. <span data-ttu-id="e1980-149">Klicka **på Organisationsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="e1980-149">Click **Org settings**.</span></span>
3. <span data-ttu-id="e1980-150">Klicka på **Microsoft 365-grupper i listan.**</span><span class="sxs-lookup"><span data-stu-id="e1980-150">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="e1980-151">Kontrollera att kryssrutorna Låt gruppägare lägga till personer utanför  organisationen i **Microsoft 365-grupper** som gäster och låt gästgruppmedlemmar få åtkomst till gruppinnehållskryssrutor är markerade.</span><span class="sxs-lookup"><span data-stu-id="e1980-151">Ensure that the **Let group owners add people outside your organization to Microsoft 365 Groups as guests** and **Let guest group members access group content** check boxes are both checked.</span></span>
5. <span data-ttu-id="e1980-152">Klicka på Spara ändringar om du **har gjort ändringar.**</span><span class="sxs-lookup"><span data-stu-id="e1980-152">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="e1980-153">Delningsinställningar på SharePoint-organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="e1980-153">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="e1980-154">Teams-innehåll, till exempel filer, mappar och listor, lagras i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1980-154">Teams content such as files, folders, and lists are all stored in SharePoint.</span></span> <span data-ttu-id="e1980-155">För att gäster ska ha åtkomst till dessa objekt i Teams måste delningsinställningarna på SharePoint-organisationsnivå tillåta delning med gäster.</span><span class="sxs-lookup"><span data-stu-id="e1980-155">In order for guests to have access to these items in Teams, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="e1980-156">Inställningarna på organisationsnivå avgör vilka inställningar som är tillgängliga för enskilda webbplatser, inklusive webbplatser som är kopplade till grupper.</span><span class="sxs-lookup"><span data-stu-id="e1980-156">The organization-level settings determine what settings are available for individual sites, including sites associated with teams.</span></span> <span data-ttu-id="e1980-157">Webbplatsinställningarna får inte vara mer tillåtande än inställningarna på organisationsnivå.</span><span class="sxs-lookup"><span data-stu-id="e1980-157">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="e1980-158">Välj Alla om du vill tillåta fil- och mappdelning med oauticerade **personer.**</span><span class="sxs-lookup"><span data-stu-id="e1980-158">If you want to allow file and folder sharing with unauthenticated people, choose **Anyone**.</span></span> <span data-ttu-id="e1980-159">Om du vill säkerställa att alla gäster måste autentisera väljer du **Nya och befintliga gäster.**</span><span class="sxs-lookup"><span data-stu-id="e1980-159">If you want to ensure that all guests have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="e1980-160">Välj den mest tillåtande inställningen som kommer att behövas av någon webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e1980-160">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="e1980-162">Så här anger du delningsinställningar på organisationsnivå i SharePoint</span><span class="sxs-lookup"><span data-stu-id="e1980-162">To set SharePoint organization-level sharing settings</span></span>

1. <span data-ttu-id="e1980-163">Klicka på **SharePoint** i det vänstra navigeringsfönstret i administrationscentret **för** Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1980-163">In the Microsoft 365 admin center, in the left navigation pane, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="e1980-164">Expandera Principer i det vänstra navigeringsfönstret i administrationscentret för SharePoint och **klicka** sedan på **Delning.**</span><span class="sxs-lookup"><span data-stu-id="e1980-164">In the SharePoint admin center, in the left navigation pane, expand **Policies** and then click **Sharing**.</span></span>
3. <span data-ttu-id="e1980-165">Kontrollera att extern delning för SharePoint är inställt på **Alla** eller **Nya och befintliga gäster.**</span><span class="sxs-lookup"><span data-stu-id="e1980-165">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="e1980-166">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e1980-166">If you made changes, click **Save**.</span></span>


## <a name="sharepoint-organization-level-default-link-settings"></a><span data-ttu-id="e1980-167">Standardinställningar för SharePoint-länkar på organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="e1980-167">SharePoint organization-level default link settings</span></span>

<span data-ttu-id="e1980-168">Standardinställningarna för fil- och mapplänk bestämmer vilket länkalternativ som ska visas för användare som standard när de delar en fil eller mapp.</span><span class="sxs-lookup"><span data-stu-id="e1980-168">The default file and folder link settings determine the link option that will be shown to users by default when they share a file or folder.</span></span> <span data-ttu-id="e1980-169">Användare kan ändra länktypen till något av de andra alternativen innan de delar, om du vill.</span><span class="sxs-lookup"><span data-stu-id="e1980-169">Users can change the link type to one of the other options before sharing, if desired.</span></span>

<span data-ttu-id="e1980-170">Tänk på att den här inställningen påverkar alla team och SharePoint-webbplatser i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e1980-170">Keep in mind that this setting affects all teams and SharePoint sites in your organization.</span></span>

<span data-ttu-id="e1980-171">Välj någon av följande länktyper som väljs som standard när användare delar filer och mappar:</span><span class="sxs-lookup"><span data-stu-id="e1980-171">Choose any one of the following link-types which will be selected by default when users share files and folders:</span></span>

- <span data-ttu-id="e1980-172">**Alla som har** länken – Välj det här alternativet om du förväntar dig att göra mycket oauticerad delning av filer och mappar.</span><span class="sxs-lookup"><span data-stu-id="e1980-172">**Anyone with the link** - Choose this option if you expect to do a lot of unauthenticated sharing of files and folders.</span></span> <span data-ttu-id="e1980-173">Om du vill tillåta *alla länkar* men är orolig för oautisk delning av misstag kan du betrakta ett av de andra alternativen som standardalternativ.</span><span class="sxs-lookup"><span data-stu-id="e1980-173">If you want to allow *Anyone* links but are concerned about accidental unauthenticated sharing, consider one of the other options as the default.</span></span> <span data-ttu-id="e1980-174">Den här länktypen är bara tillgänglig om du har aktiverat **delning för alla.**</span><span class="sxs-lookup"><span data-stu-id="e1980-174">This link type is only available if you've enabled **Anyone** sharing.</span></span>
- <span data-ttu-id="e1980-175">**Endast personer i organisationen –** Välj det här alternativet om du förväntar dig att de flesta fil- och mappdelningar ska vara med personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e1980-175">**Only people in your organization** - Choose this option if you expect most file and folder sharing to be with people inside your organization.</span></span>
- <span data-ttu-id="e1980-176">**Specifika personer** – Tänk på det här alternativet om du förväntar dig att göra mycket fil- och mappdelning med gäster.</span><span class="sxs-lookup"><span data-stu-id="e1980-176">**Specific people** - Consider this option if you expect to do a lot of file and folder sharing with guests.</span></span> <span data-ttu-id="e1980-177">Den här typen av länk fungerar med gäster och kräver att de autentiseras.</span><span class="sxs-lookup"><span data-stu-id="e1980-177">This type of link works with guests and requires them to authenticate.</span></span>
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


<span data-ttu-id="e1980-179">Så här ställer du in standardinställningar för SharePoint-länkar på organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="e1980-179">To set the SharePoint organization-level default link settings</span></span>

1. <span data-ttu-id="e1980-180">Gå till sidan Delning i administrationscentret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e1980-180">Navigate to the Sharing page in the SharePoint admin center.</span></span>
2. <span data-ttu-id="e1980-181">Välj **den standarddelningslänk** som du vill använda under Fil- och mapplänkar.</span><span class="sxs-lookup"><span data-stu-id="e1980-181">Under **File and folder links**, select the default sharing link that you want to use.</span></span>
3. <span data-ttu-id="e1980-182">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e1980-182">If you made changes, click **Save**.</span></span>

## <a name="create-a-team"></a><span data-ttu-id="e1980-183">Skapa ett team</span><span class="sxs-lookup"><span data-stu-id="e1980-183">Create a team</span></span>

<span data-ttu-id="e1980-184">Nästa steg är att skapa det team som du planerar att använda för att samarbeta med gäster.</span><span class="sxs-lookup"><span data-stu-id="e1980-184">The next step is to create the team that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="e1980-185">Skapa ett team</span><span class="sxs-lookup"><span data-stu-id="e1980-185">To create a team</span></span>
1. <span data-ttu-id="e1980-186">I Teams klickar du **på** Gå med i **eller skapa ett team längst** ned i den vänstra rutan på fliken Team.</span><span class="sxs-lookup"><span data-stu-id="e1980-186">In Teams, on the **Teams** tab, click **Join or create a team** at the bottom of the left pane.</span></span>
2. <span data-ttu-id="e1980-187">Klicka **på Skapa ett team.**</span><span class="sxs-lookup"><span data-stu-id="e1980-187">Click **Create a team**.</span></span>
3. <span data-ttu-id="e1980-188">Klicka **på Skapa ett team från grunden.**</span><span class="sxs-lookup"><span data-stu-id="e1980-188">Click **Build a team from scratch**.</span></span>
4. <span data-ttu-id="e1980-189">Välj **Privat** eller **Offentlig.**</span><span class="sxs-lookup"><span data-stu-id="e1980-189">Choose **Private** or **Public**.</span></span>
5. <span data-ttu-id="e1980-190">Skriv ett namn och en beskrivning för gruppen och klicka sedan på **Skapa.**</span><span class="sxs-lookup"><span data-stu-id="e1980-190">Type a name and description for the team, and then click **Create**.</span></span>
6. <span data-ttu-id="e1980-191">Klicka **på Hoppa över.**</span><span class="sxs-lookup"><span data-stu-id="e1980-191">Click **Skip**.</span></span>

<span data-ttu-id="e1980-192">Vi bjuder in användare senare.</span><span class="sxs-lookup"><span data-stu-id="e1980-192">We'll invite users later.</span></span> <span data-ttu-id="e1980-193">Sedan är det viktigt att kontrollera delningsinställningarna på webbplatsnivå för den SharePoint-webbplats som är kopplad till gruppen.</span><span class="sxs-lookup"><span data-stu-id="e1980-193">Next, it's important to check the site-level sharing settings for the SharePoint site that is associated with the team.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="e1980-194">Delningsinställningar på webbplatsnivå i SharePoint</span><span class="sxs-lookup"><span data-stu-id="e1980-194">SharePoint site-level sharing settings</span></span>

<span data-ttu-id="e1980-195">Kontrollera inställningarna för delning på webbplatsnivå för att kontrollera att de tillåter den typ av åtkomst som du vill använda för det här teamet.</span><span class="sxs-lookup"><span data-stu-id="e1980-195">Check the site-level sharing settings to make sure that they allow the type of access that you want for this team.</span></span> <span data-ttu-id="e1980-196">Om du till exempel anger inställningar på organisationsnivå till **Alla,** men du vill att alla gäster ska autentiseras för teamet, kontrollerar du att delningsinställningarna på webbplatsnivå är inställda på Nya och **befintliga gäster.**</span><span class="sxs-lookup"><span data-stu-id="e1980-196">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this team, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="e1980-198">Så här anger du delningsinställningar på webbplatsnivå</span><span class="sxs-lookup"><span data-stu-id="e1980-198">To set site-level sharing settings</span></span>
1. <span data-ttu-id="e1980-199">I det vänstra navigeringsfönstret i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar **på Aktiva webbplatser.**</span><span class="sxs-lookup"><span data-stu-id="e1980-199">In the SharePoint admin center, in the left navigation pane, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="e1980-200">Välj webbplatsen för det team som du just har skapat.</span><span class="sxs-lookup"><span data-stu-id="e1980-200">Select the site for the team that you just created.</span></span>
3. <span data-ttu-id="e1980-201">Klicka på ... och väljer **Delning.**</span><span class="sxs-lookup"><span data-stu-id="e1980-201">Click ... and choose **Sharing**.</span></span>
4. <span data-ttu-id="e1980-202">Kontrollera att delning är inställt **på Alla** eller Nya och **befintliga gäster.**</span><span class="sxs-lookup"><span data-stu-id="e1980-202">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="e1980-203">Om du har gjort ändringar klickar du på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e1980-203">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="e1980-204">Bjud in användare</span><span class="sxs-lookup"><span data-stu-id="e1980-204">Invite users</span></span>

<span data-ttu-id="e1980-205">Inställningarna för gästdelning är nu konfigurerade så att du kan börja lägga till interna användare och gäster i teamet.</span><span class="sxs-lookup"><span data-stu-id="e1980-205">Guest sharing settings are now configured, so you can start adding internal users and guests to your team.</span></span> 

<span data-ttu-id="e1980-206">Så här bjuder du in interna användare till ett team</span><span class="sxs-lookup"><span data-stu-id="e1980-206">To invite internal users to a team</span></span>
1. <span data-ttu-id="e1980-207">Klicka på Fler alternativ ( **) i** gruppen och klicka sedan på Lägg **\*\*\*** till **medlem.**</span><span class="sxs-lookup"><span data-stu-id="e1980-207">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="e1980-208">Skriv namnet på den person som du vill bjuda in.</span><span class="sxs-lookup"><span data-stu-id="e1980-208">Type the name of the person who you want to invite.</span></span>
3. <span data-ttu-id="e1980-209">Klicka **på Lägg** till och sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="e1980-209">Click **Add**, and then click **Close**.</span></span>

<span data-ttu-id="e1980-210">Bjuda in gäster till ett team</span><span class="sxs-lookup"><span data-stu-id="e1980-210">To invite guests to a team</span></span>
1. <span data-ttu-id="e1980-211">Klicka på Fler alternativ ( **) i** gruppen och klicka sedan på Lägg **\*\*\*** till **medlem.**</span><span class="sxs-lookup"><span data-stu-id="e1980-211">In the team, click **More options** (**\*\*\***), and then click **Add member**.</span></span>
2. <span data-ttu-id="e1980-212">Skriv e-postadressen till gästen som du vill bjuda in.</span><span class="sxs-lookup"><span data-stu-id="e1980-212">Type the email address of the guest whom you want to invite.</span></span>
3. <span data-ttu-id="e1980-213">Klicka **på Redigera gästinformation.**</span><span class="sxs-lookup"><span data-stu-id="e1980-213">Click **Edit guest information**.</span></span>
4. <span data-ttu-id="e1980-214">Skriv gästens fullständiga namn och klicka på bockmarkeringen.</span><span class="sxs-lookup"><span data-stu-id="e1980-214">Type the guest's full name and click the check mark.</span></span>
5. <span data-ttu-id="e1980-215">Klicka **på Lägg** till och sedan på **Stäng.**</span><span class="sxs-lookup"><span data-stu-id="e1980-215">Click **Add**, and then click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1980-216">Se även</span><span class="sxs-lookup"><span data-stu-id="e1980-216">See also</span></span>

[<span data-ttu-id="e1980-217">Metodtips för att dela filer och mappar med oautentiserade användare</span><span class="sxs-lookup"><span data-stu-id="e1980-217">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="e1980-218">Begränsa oavsiktlig exponering för filer när de delas med gäster</span><span class="sxs-lookup"><span data-stu-id="e1980-218">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="e1980-219">Skapa en säker miljö för gästdelning</span><span class="sxs-lookup"><span data-stu-id="e1980-219">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="e1980-220">Skapa ett B2B-extranät med hanterade gäster</span><span class="sxs-lookup"><span data-stu-id="e1980-220">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)

[<span data-ttu-id="e1980-221">SharePoint- och OneDrive-integrering med Azure AD B2B</span><span class="sxs-lookup"><span data-stu-id="e1980-221">SharePoint and OneDrive integration with Azure AD B2B</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[<span data-ttu-id="e1980-222">Delningsalternativ är nedtonade när du delar från SharePoint eller OneDrive</span><span class="sxs-lookup"><span data-stu-id="e1980-222">Sharing options are greyed out when sharing from SharePoint or OneDrive</span></span>](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
