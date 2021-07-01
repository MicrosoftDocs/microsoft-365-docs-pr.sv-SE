---
title: Konfigurera teams med grundläggande skydd
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
description: Lär dig hur du distribuerar team med en grundläggande nivå av skydd.
ms.openlocfilehash: bf95c26a9bf724aaddae8321022ecdfceae82d1a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229065"
---
# <a name="configure-teams-with-baseline-protection"></a><span data-ttu-id="20918-103">Konfigurera teams med grundläggande skydd</span><span class="sxs-lookup"><span data-stu-id="20918-103">Configure teams with baseline protection</span></span>

<span data-ttu-id="20918-104">I den här artikeln tittar vi på hur du distribuerar team med en grundläggande nivå av skydd.</span><span class="sxs-lookup"><span data-stu-id="20918-104">In this article, we look at how to deploy teams with a baseline level of protection.</span></span> <span data-ttu-id="20918-105">Den här nivån ger användare ett stort utbud av alternativ för samarbete medan det förbättrar av behörighetshantering och ger grundläggande skydd mot överdelning.</span><span class="sxs-lookup"><span data-stu-id="20918-105">This level allows users a wide range of options for collaboration while enhancing permissions management and providing basic protection against oversharing.</span></span> <span data-ttu-id="20918-106">Rekommenderade skydd för denna nivå inkluderar principer för identitets- och enhetsåtkomst och skydd mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="20918-106">Recommended protections for this level include identity and device access policies and protection against malware.</span></span> <span data-ttu-id="20918-107">Du kan också använda principer för villkorlig åtkomst och skydd mot dataförlust efter behov.</span><span class="sxs-lookup"><span data-stu-id="20918-107">Additionally, you can apply conditional access policies and data loss protections as needed.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="20918-108">Initiala skydd</span><span class="sxs-lookup"><span data-stu-id="20918-108">Initial protections</span></span>

<span data-ttu-id="20918-109">Som ett första steg rekommenderar vi att du konfigurerar principer för grundläggande principer för identitets- och enhetsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="20918-109">As a first step, we recommend that you configure basic identity and device-access policies.</span></span> <span data-ttu-id="20918-110">Mer information finns i [Principrekommendationer för att skydda Teams-chattar, grupper och filer](../security/office-365-security/teams-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="20918-110">See [Policy recommendations for securing Teams chats, groups, and files](../security/office-365-security/teams-access-policies.md) for details.</span></span>

<span data-ttu-id="20918-111">Vi rekommenderar även att du aktiverar grundläggande Defender för Office 365-funktioner för att skydda mot skadlig programvara i dokument, bilagor och länkar.</span><span class="sxs-lookup"><span data-stu-id="20918-111">We also recommend turning on basic Defender for Office 365 features to guard against malware in documents, attachments, and links.</span></span> <span data-ttu-id="20918-112">Vi rekommenderar att du aktiverar vart och ett av alternativen i tabellen nedan.</span><span class="sxs-lookup"><span data-stu-id="20918-112">We recommend turning on each of the options in the following table.</span></span>

|<span data-ttu-id="20918-113">Alternativ</span><span class="sxs-lookup"><span data-stu-id="20918-113">Option</span></span>|<span data-ttu-id="20918-114">Information </span><span class="sxs-lookup"><span data-stu-id="20918-114">Information</span></span>|
|:------|:-----------|
|<span data-ttu-id="20918-115">Säkra bilagor för SPO, OneDrive och Teams</span><span class="sxs-lookup"><span data-stu-id="20918-115">Safe Attachments for SPO, OneDrive and Teams</span></span>|[<span data-ttu-id="20918-116">Säkra bifogade filer</span><span class="sxs-lookup"><span data-stu-id="20918-116">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md) <p> [<span data-ttu-id="20918-117">Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="20918-117">Defender for Office 365 - SharePoint, OneDrive, and Microsoft Teams</span></span>](../security/office-365-security/mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="20918-118">Säkra dokument</span><span class="sxs-lookup"><span data-stu-id="20918-118">Safe Documents</span></span>|[<span data-ttu-id="20918-119">Säkra dokument i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="20918-119">Safe Documents in Microsoft Defender for Office 365</span></span>](../security/office-365-security/safe-docs.md)|
|<span data-ttu-id="20918-120">Säkra länkar för Teams</span><span class="sxs-lookup"><span data-stu-id="20918-120">Safe Links for Teams</span></span>|[<span data-ttu-id="20918-121">Office 365 säkra länkar i Teams</span><span class="sxs-lookup"><span data-stu-id="20918-121">Office 365 Safe Links in Teams</span></span>](../security/office-365-security/safe-links.md) <p> [<span data-ttu-id="20918-122">Säkra länkar</span><span class="sxs-lookup"><span data-stu-id="20918-122">Safe Links</span></span>](../security/office-365-security/safe-links.md)|

## <a name="teams-guest-sharing"></a><span data-ttu-id="20918-123">Gästdelning i Teams</span><span class="sxs-lookup"><span data-stu-id="20918-123">Teams guest sharing</span></span>

<span data-ttu-id="20918-124">I respektive lager har vi alternativet att dela med personer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="20918-124">In each of the tiers, we have the option of sharing with people outside your organization.</span></span> <span data-ttu-id="20918-125">I känsliga och mycket känsliga lager kan vi välja att inaktivera gästdelning på gruppnivå genom att använda känslighetsetiketter.</span><span class="sxs-lookup"><span data-stu-id="20918-125">For the sensitive and highly sensitive tiers, we will have the option to turn guest sharing off at the team level by using sensitivity labels.</span></span> <span data-ttu-id="20918-126">Men inställning av gästdelning på organisationsnivå måste aktiveras för att gästdelning ska fungera över huvud taget i Teams.</span><span class="sxs-lookup"><span data-stu-id="20918-126">But the organization-level guest sharing setting must be turned on for guest sharing to work at all in Teams.</span></span>

![Skärmbild av växling för gäståtkomst i Teams](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="20918-128">Att ange inställningar för gäståtkomst i Teams</span><span class="sxs-lookup"><span data-stu-id="20918-128">To set Teams guest access settings</span></span>

1. <span data-ttu-id="20918-129">Logga in på Administrationscenter för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="20918-129">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="20918-130">Klicka på **Visa alla** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20918-130">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="20918-131">Under **Administrationscenter** klickar du på **Teams**.</span><span class="sxs-lookup"><span data-stu-id="20918-131">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="20918-132">Expandera **Inställningar för hela organisationen** och klicka på **Gäståtkomst** i Teams Administrationscenter i vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="20918-132">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="20918-133">Kontrollera att **Tillåt gäståtkomst i Teams** är inställt på **På**.</span><span class="sxs-lookup"><span data-stu-id="20918-133">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="20918-134">Gör önskade ändringar i de ytterligare gästinställningarna och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20918-134">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="20918-135">Det kan ta upp till 24 timmar för gästinställningar i Teams att bli aktiva när du har aktiverat det.</span><span class="sxs-lookup"><span data-stu-id="20918-135">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

<span data-ttu-id="20918-136">Gästdelning är aktiverad som standard för Office 365-grupper och SharePoint, men om du tidigare har ändrat gästdelningsinställningarna för din organisation rekommenderar vi att du går igenom [Samarbeta med gäster i ett team](./collaborate-as-team.md) för att säkerställa att gästdelning blir tillgängligt i Teams.</span><span class="sxs-lookup"><span data-stu-id="20918-136">Guest sharing is turned on by default for Office 365 groups and SharePoint, however if you have previously changed any of the guest sharing settings for your organization, we recommend that you review [Collaborate with guests in a team](./collaborate-as-team.md) to ensure that guest sharing will be available in Teams.</span></span>

## <a name="site-and-file-sharing"></a><span data-ttu-id="20918-137">Delning av webbplatser och filer</span><span class="sxs-lookup"><span data-stu-id="20918-137">Site and file sharing</span></span>

<span data-ttu-id="20918-138">Om du vill minska risken för att oavsiktligt dela filer eller mappar med personer utanför organisationen rekommenderar vi att du ändrar den förvalda delningslänken för SharePoint till *Endast personer i organisationen*.</span><span class="sxs-lookup"><span data-stu-id="20918-138">To reduce the risk of accidentally sharing files or folders with people outside your organization, we recommend changing the default sharing link for SharePoint to *Only people in your organization*.</span></span> <span data-ttu-id="20918-139">(Om användare måste dela externt, och du har aktiverat gästdelning, kan de fortfarande ändra länktypen när de delar.)</span><span class="sxs-lookup"><span data-stu-id="20918-139">(If users need to share externally, and you have enabled guest sharing, they can still change the link type when they share.)</span></span>

<span data-ttu-id="20918-140">Ändra standardlänken för delning</span><span class="sxs-lookup"><span data-stu-id="20918-140">To change the default sharing link</span></span>
1. <span data-ttu-id="20918-141">Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="20918-141">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="20918-142">Under **Principer** klickar du på **Delning**.</span><span class="sxs-lookup"><span data-stu-id="20918-142">Under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="20918-143">Under **Fil- och mapplänkar** väljer du **Endast personer i organisationen**.</span><span class="sxs-lookup"><span data-stu-id="20918-143">Under **File and folder links**, select **Only people in your organization**.</span></span>
4. <span data-ttu-id="20918-144">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20918-144">Click **Save**.</span></span>

<span data-ttu-id="20918-145">Vi rekommenderar även att du aktiverar [SharePoint- och OneDrive-integrering med Azure Active Directory B2B](/sharepoint/sharepoint-azureb2b-integration-preview) om du vill ha bästa möjliga gästdelning.</span><span class="sxs-lookup"><span data-stu-id="20918-145">For the best guest sharing experience, we also recommend that you enable [SharePoint and OneDrive integration with Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="20918-146">Skapa ett team</span><span class="sxs-lookup"><span data-stu-id="20918-146">Create a team</span></span>

<span data-ttu-id="20918-147">Ytterligare konfiguration av grundläggande nivå av skydd görs på den SharePoint-webbplats som är kopplad till ett team.</span><span class="sxs-lookup"><span data-stu-id="20918-147">Additional configuration for the baseline level of protection is done in the SharePoint site associated with a team.</span></span> <span data-ttu-id="20918-148">[Skapa ett offentligt eller privat team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) innan du går vidare till nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="20918-148">[Create a public or private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) before proceeding to the next section.</span></span>

## <a name="site-sharing-settings"></a><span data-ttu-id="20918-149">Inställningar för webbplatsdelning</span><span class="sxs-lookup"><span data-stu-id="20918-149">Site sharing settings</span></span>

<span data-ttu-id="20918-150">Som standard kan medlemmar i en SharePoint-webbplats bjuda in andra till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="20918-150">By default, members of a SharePoint site can invite others to the site.</span></span> <span data-ttu-id="20918-151">När en webbplats är en del av ett team inkluderas gruppmedlemmarna som webbplatsmedlemmar.</span><span class="sxs-lookup"><span data-stu-id="20918-151">When a site is part of a team, team members are included as site members.</span></span> <span data-ttu-id="20918-152">Personer som lagts till direkt i webbplatsen har dock inte tillgång till resten av gruppen.</span><span class="sxs-lookup"><span data-stu-id="20918-152">However, people added directly to the site don't have access to the rest of the team.</span></span> <span data-ttu-id="20918-153">Därför rekommenderar vi att du hanterar behörigheter exklusivt via gruppen.</span><span class="sxs-lookup"><span data-stu-id="20918-153">For this reason, we recommend managing permissions exclusively through the team.</span></span>

<span data-ttu-id="20918-154">Om du vill ha hjälp med hantering av behörigheter rekommenderar vi att du konfigurerar den kopplade webbplatsen så att ägaren bara kan dela webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="20918-154">To help with permissions management, we recommend configuring the associated site to only allow owners to share the site by itself.</span></span> <span data-ttu-id="20918-155">Det förenklar hantering av behörigheter och hindrar åtkomst av personer utan att gruppägarens kunskap.</span><span class="sxs-lookup"><span data-stu-id="20918-155">This simplifies permissions management and helps prevent access by people without a team owner's knowledge.</span></span> <span data-ttu-id="20918-156">Gör detta för varje team som kräver grundläggande skydd.</span><span class="sxs-lookup"><span data-stu-id="20918-156">Do this for each team that requires baseline protection.</span></span>

<span data-ttu-id="20918-157">Uppdatera inställningarna för webbplatsdelning</span><span class="sxs-lookup"><span data-stu-id="20918-157">To update the site sharing settings</span></span>
1. <span data-ttu-id="20918-158">I verktygsfältet för teamet klickar du på **Filer**.</span><span class="sxs-lookup"><span data-stu-id="20918-158">In the tool bar for the team, click **Files**.</span></span>
2. <span data-ttu-id="20918-159">Klicka sedan **Öppna i SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="20918-159">Click **Open in SharePoint**.</span></span>
3. <span data-ttu-id="20918-160">Klicka på inställningsikonen i verktygsfältet på SharePoint-gruppwebbplatsen och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="20918-160">In the tool bar of the SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
4. <span data-ttu-id="20918-161">I fönstret **Webbplatsbehörigheter**, under **webbplatsdelning**, klickar du på **Ändra hur medlemmar kan dela**.</span><span class="sxs-lookup"><span data-stu-id="20918-161">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
5. <span data-ttu-id="20918-162">Under **Delningsbehörigheter** väljer du **Webbplatsägare och medlemmar, och personer med redigeringsbehörighet kan dela filer och mappar, men endast webbplatsägare kan dela webbplatsen** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="20918-162">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="20918-163">Ytterligare skydd</span><span class="sxs-lookup"><span data-stu-id="20918-163">Additional protections</span></span>

<span data-ttu-id="20918-164">Microsoft 365 tillhandahåller fler metoder för att skydda innehållet.</span><span class="sxs-lookup"><span data-stu-id="20918-164">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="20918-165">Överväg att använda följande alternativ för att förbättra säkerheten för din organisation.</span><span class="sxs-lookup"><span data-stu-id="20918-165">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="20918-166">Låt gästanvändaren godkänna [användningsvillkor](/azure/active-directory/conditional-access/terms-of-use).</span><span class="sxs-lookup"><span data-stu-id="20918-166">Have guests agree to a [terms of use](/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="20918-167">Konfigurera en [princip om tidsgräns för sessioner](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) för gäster.</span><span class="sxs-lookup"><span data-stu-id="20918-167">Configure a [session timeout policy](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="20918-168">Skapa [känslig informationstyper](../compliance/sensitive-information-type-learn-about.md) och Använd [skydd mot dataförlust](../compliance/dlp-learn-about-dlp.md) för att ange principer för åtkomst av känslig information.</span><span class="sxs-lookup"><span data-stu-id="20918-168">Create [sensitive information types](../compliance/sensitive-information-type-learn-about.md) and use [data loss protection](../compliance/dlp-learn-about-dlp.md) to set policies around accessing sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="20918-169">Se även</span><span class="sxs-lookup"><span data-stu-id="20918-169">See Also</span></span>

<span data-ttu-id="20918-170">Få mer information om hur du [hanterar mötesprinciper i Teams](/microsoftteams/meeting-policies-in-teams).</span><span class="sxs-lookup"><span data-stu-id="20918-170">[Manage meeting policies in Teams](/microsoftteams/meeting-policies-in-teams)</span></span>

[<span data-ttu-id="20918-171">Komma igång med hantering av Insider-riskhantering</span><span class="sxs-lookup"><span data-stu-id="20918-171">Get started with insider risk management</span></span>](../compliance/insider-risk-management-configure.md)