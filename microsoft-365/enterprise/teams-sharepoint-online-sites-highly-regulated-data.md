---
title: SharePoint-webbplatser för strikt reglerade data
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Skapa en säker SharePoint-gruppwebbplats för att lagra värdefulla och känsliga filer.
ms.openlocfilehash: bc1a84fa7437d9b2979e10b352f8a422c457e8a0
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951988"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="7a7ec-103">SharePoint-webbplatser för strikt reglerade data</span><span class="sxs-lookup"><span data-stu-id="7a7ec-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="7a7ec-104">*Det här scenariot gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7a7ec-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7a7ec-105">Microsoft 365 Enterprise innehåller en komplett uppsättning molnbaserade tjänster så att du kan skapa, lagra, skydda och hantera strikt reglerade data som lagras i filer.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-105">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, secure, and manage your highly regulated data stored in files.</span></span> <span data-ttu-id="7a7ec-106">Det inkluderar data som:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-106">This includes data that is:</span></span>

- <span data-ttu-id="7a7ec-107">Lyder under regionala bestämmelser.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="7a7ec-108">Är de mest värdefulla data för din organisation, t.ex. affärshemligheter, ekonomisk information och personalinformation samt organisationens strategi.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="7a7ec-109">Ett liknande scenario med Microsoft Teams finns [här](secure-teams-highly-regulated-data-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="7a7ec-109">A similar scenario using Microsoft Teams is [here](secure-teams-highly-regulated-data-scenario.md).</span></span>
>

<span data-ttu-id="7a7ec-110">Ett molnbaserat scenario för Microsoft 365 Enterprise som uppfyller detta affärsbehov kräver att du:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="7a7ec-111">Lagrar filer (dokument, bildspel, kalkylblad osv.) på en SharePoint-gruppwebbplats.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="7a7ec-112">Lås webbplatsen för att förhindra:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="7a7ec-113">Åtkomst av användare som inte är medlemmar i webbplatsens Office 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-113">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="7a7ec-114">Webbplatsmedlemmarna från att ge andra personer åtkomst.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="7a7ec-115">Icke-medlemmar av webbplatsen från att begära åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="7a7ec-116">Konfigurera en Office 365-kvarhållningsetikett för dina SharePoint-webbplatser som ett standardsätt att hindra användare från att skicka filer utanför organisationen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-116">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="7a7ec-117">Kryptera de känsligaste filerna på webbplatsen med kryptering som följer med filen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="7a7ec-118">Lägg till behörigheter för de känsligaste filerna så att giltiga inloggningsuppgifter för ett användarkonto som har behörighet måste anges även om de delas utanför webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="7a7ec-119">I följande tabell beskrivs kraven i det här scenariot för en funktion i Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="7a7ec-120">**Krav**</span><span class="sxs-lookup"><span data-stu-id="7a7ec-120">**Requirement**</span></span> | <span data-ttu-id="7a7ec-121">**Microsoft 365 Enterprise-funktion**</span><span class="sxs-lookup"><span data-stu-id="7a7ec-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="7a7ec-122">Lagra filer</span><span class="sxs-lookup"><span data-stu-id="7a7ec-122">Store files</span></span> | <span data-ttu-id="7a7ec-123">SharePoint-gruppwebbplatser</span><span class="sxs-lookup"><span data-stu-id="7a7ec-123">SharePoint team sites</span></span> |
| <span data-ttu-id="7a7ec-124">Lås webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-124">Lock down the site</span></span> | <span data-ttu-id="7a7ec-125">Office 365-grupper och behörigheter för SharePoint-gruppwebbplats</span><span class="sxs-lookup"><span data-stu-id="7a7ec-125">Office 365 groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="7a7ec-126">Etikettera filerna på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-126">Label the files of the site</span></span> | <span data-ttu-id="7a7ec-127">Kvarhållningsetiketter för Office 365</span><span class="sxs-lookup"><span data-stu-id="7a7ec-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="7a7ec-128">Blockera användare från att skicka filer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="7a7ec-129">DLP-principer (dataförlustskydd) i Office 365</span><span class="sxs-lookup"><span data-stu-id="7a7ec-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="7a7ec-130">Kryptera alla filer på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="7a7ec-131">Office 365-känslighetsetiketter eller underetiketter</span><span class="sxs-lookup"><span data-stu-id="7a7ec-131">Office 365 sensitivity labels or sublabels</span></span> |
| <span data-ttu-id="7a7ec-132">Lägg till behörigheter för webbplatsens filer</span><span class="sxs-lookup"><span data-stu-id="7a7ec-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="7a7ec-133">Office 365-känslighetsetiketter eller underetiketter</span><span class="sxs-lookup"><span data-stu-id="7a7ec-133">Office 365 sensitivity labels or sublabels</span></span> |
|||

<span data-ttu-id="7a7ec-134">Här är ett exempel på en konfiguration för en säker SharePoint-webbplats.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-134">Here is an example configuration for a secure SharePoint site.</span></span>

![Scenario för SharePoint-webbplatser för strikt reglerade data](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="7a7ec-136">Det här scenariot kräver att du redan har distribuerat:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="7a7ec-137">Fasen [Identitet](identity-infrastructure.md) och steg 1 och 2 av fasen [Informationsskydd](infoprotect-infrastructure.md) i den grundläggande infrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="7a7ec-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="7a7ec-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="7a7ec-139">I följande faser får du stegvisa instruktioner hur du utformar, konfigurerar och driver på användningen av SharePoint-webbplatser för strikt reglerade data.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<a name="poster"></a> <span data-ttu-id="7a7ec-140">En sammanfattning på en sida finns på [affischen SharePoint-webbplatser för strikt reglerade data](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span><span class="sxs-lookup"><span data-stu-id="7a7ec-140">For a 1-page summary of this scenario, see the [SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="7a7ec-141">[![SharePoint-webbplatser för strikt reglerade data (affisch)](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="7a7ec-141">[![SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="7a7ec-142">Du kan också ladda ned den här affischen i [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)- eller [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx)-format och skriva ut den i pappersstorleken letter, legal eller tabloid (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="7a7ec-142">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="7a7ec-143">Villkor för identitet och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="7a7ec-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="7a7ec-144">För att skydda åtkomsten till SharePoint-webbplatsen ska du se till att du har konfigurerat [principer för identitet och enhetsåtkomst](identity-access-policies.md) och de rekommenderade [principerna för SharePoint-åtkomst](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7a7ec-144">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="7a7ec-145">Fas 1: Utformning</span><span class="sxs-lookup"><span data-stu-id="7a7ec-145">Phase 1: Design</span></span>

<span data-ttu-id="7a7ec-146">När du vill skapa en SharePoint-webbplats för strikt reglerade data måste du först identifiera syftet med den.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-146">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="7a7ec-147">En forsknings- och utvecklingsavdelning i en tillverkningsorganisation kan till exempel behöva en SharePoint-webbplats för att lagra aktuella specifikationer för befintliga produkter och en plats för samarbete om nya produkter.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-147">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="7a7ec-148">Bara medlemmar på forsknings- och utvecklingsavdelningen och utvalda chefer får åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-148">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="7a7ec-149">Syftet avgör viktiga konfigurationselement som:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="7a7ec-150">Office 365-kvarhållningsetiketten som tilldelas dokumentavsnittet på webbplatsen och DLP-principerna för etiketten</span><span class="sxs-lookup"><span data-stu-id="7a7ec-150">The Office 365 retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="7a7ec-151">Inställningarna för en Office 365-underetikett för känslighet som användare tillämpar på mycket känsliga filer som lagras på webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-151">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="7a7ec-152">När du har fastställt detta använder du inställningarna för att konfigurera webbplatsen i fas 2.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-152">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="7a7ec-153">Steg 1 Office 365-kvarhållningsetiketter och DLP-principer</span><span class="sxs-lookup"><span data-stu-id="7a7ec-153">Step 1 Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="7a7ec-154">Office 365-kvarhållningsetiketter tillämpas på dokumentavsnittet på SharePoint-gruppwebbplatsen och är en standardmetod för att klassificera alla filer som lagras på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-154">When applied to the Documents portion of a SharePoint team site, Office 365 retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="7a7ec-155">För SharePoint-webbplatser för strikt reglerade data måste du avgöra vilken Office 365-kvarhållningsetikett som ska användas.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-155">For SharePoint sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="7a7ec-156">Information om utformning av Office 365-etiketter finns i [Klassificering och etiketter för Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="7a7ec-156">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="7a7ec-157">Använd DLP-principer för att skydda känslig information och förhindra att den avslöjas oavsiktligt eller avsiktligt.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-157">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies.</span></span> <span data-ttu-id="7a7ec-158">Mer information finns i denna [översikt](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="7a7ec-158">For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="7a7ec-159">För SharePoint-webbplatser måste du konfigurera en DLP-princip för Office 365-kvarhållningsetiketten som tilldelats webbplatsen så att användare förhindras att dela filer med externa användare.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-159">For SharePoint sites, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="7a7ec-160">Steg 2: Din underetikett för känslighet i Office 365</span><span class="sxs-lookup"><span data-stu-id="7a7ec-160">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="7a7ec-161">För att tillhandahålla kryptering och en uppsättning behörigheter till de känsligaste filerna måste användarna använda en Office 365-känslighetsetikett eller underetikett.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-161">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity label or sublabel.</span></span> <span data-ttu-id="7a7ec-162">En underetikett finns under en befintlig etikett.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-162">A sublabel exists under an existing label.</span></span> 

<span data-ttu-id="7a7ec-163">Använd en känslighetsetikett när du behöver ett litet antal etiketter för både global användning och enskilda privata team.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-163">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="7a7ec-164">Använd en underetikett för känslighet när du har ett stort antal etiketter eller vill ordna etiketter för säkra webbplatser under den strikt reglerade etiketten.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-164">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for secure sites the under your highly regulated label.</span></span> 

<span data-ttu-id="7a7ec-165">Inställningarna för etiketten eller underetiketten följer med filen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-165">The settings of the applied label or sublabel travel with the file.</span></span> <span data-ttu-id="7a7ec-166">Även om den läcks utanför webbplatsen kan bara autentiserade användarkonton som har behörighet öppna den.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-166">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="7a7ec-167">Resultat av utformningen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-167">Design results</span></span>

<span data-ttu-id="7a7ec-168">Du har fastställt följande:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-168">You have determined the following:</span></span>

- <span data-ttu-id="7a7ec-169">Lämplig Office 365-kvarhållningsetikett och DLP-principen som associeras med etiketten</span><span class="sxs-lookup"><span data-stu-id="7a7ec-169">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="7a7ec-170">Inställningarna för Office 365-underetiketten för känslighet som inkluderar kryptering och behörigheter</span><span class="sxs-lookup"><span data-stu-id="7a7ec-170">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="7a7ec-171">Fas 2: Konfigurera</span><span class="sxs-lookup"><span data-stu-id="7a7ec-171">Phase 2: Configure</span></span>

<span data-ttu-id="7a7ec-172">I den här fasen tar du inställningarna som fastställts i fas 1 och använder dem för att skapa en SharePoint-webbplats för strikt reglerade data.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-172">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="7a7ec-173">Steg 1: Skapa en privat SharePoint-gruppwebbplats med ägare och medlemmar i motsvarande Office 365-grupp</span><span class="sxs-lookup"><span data-stu-id="7a7ec-173">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="7a7ec-174">Skapa en privat SharePoint-gruppwebbplats genom att följa [dessa instruktioner]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8).</span><span class="sxs-lookup"><span data-stu-id="7a7ec-174">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="7a7ec-175">Steg 2: Konfigurera ytterligare behörighetsinställningar för SharePoint-gruppwebbplatsen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-175">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="7a7ec-176">Konfigurera dessa behörighetsinställningar på SharePoint-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-176">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="7a7ec-177">Klicka på inställningsikonen i verktygsfältet och klicka sedan på **Webbplatsbehörigheter**.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-177">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="7a7ec-178">I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-178">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="7a7ec-179">Under **Delningsbehörigheter** väljer du **Endast webbplatsägare kan dela filer, mappar och webbplats**.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-179">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="7a7ec-180">Inaktivera **Tillåt åtkomstbegäranden** och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-180">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="7a7ec-181">Med dessa inställningar inaktiveras funktionen för webbplatsgruppens medlemmar att dela webbplatsen med andra medlemmar eller för icke-medlemmar att begära åtkomst till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-181">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="7a7ec-182">Steg 3: Konfigurera webbplatsen för en Office 365-kvarhållningsetikett</span><span class="sxs-lookup"><span data-stu-id="7a7ec-182">Step 3: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="7a7ec-183">Följ anvisningarna i [Skydda SharePoint-filer med Office 365-etiketter och DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) när du:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-183">Use the instructions in [Protect SharePoint files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="7a7ec-184">Skapar och publicerar en kvarhållningsetikett för strikt reglerade data (om det behövs).</span><span class="sxs-lookup"><span data-stu-id="7a7ec-184">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="7a7ec-185">Konfigurerar webbplatsen för kvarhållningsetiketten som skapats i steg 1.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-185">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="7a7ec-186">Skapar en DLP-princip för strikt reglerade data som använder kvarhållningsetiketten som skapats i steg 2 och hindrar användare från att skicka filer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-186">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="7a7ec-187">Steg 4: Skapa en Office 365-underetikett för känslighet för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-187">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="7a7ec-188">Till skillnad från en känslighetsetikett för strikt reglerade data som alla kan tillämpa på valfri fil behöver en säker webbplats en egen underetikett så att filer som tilldelas underetiketten:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-188">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="7a7ec-189">krypteras och krypteringen följer med filen,</span><span class="sxs-lookup"><span data-stu-id="7a7ec-189">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="7a7ec-190">innehåller anpassade behörigheter så att bara medlemmar i webbplatsgruppen kan öppna den.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-190">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="7a7ec-191">För att åstadkomma den här extra säkerhetsnivån för filer på webbplatsen måste du konfigurera en ny känslighetsetikett eller en underetikett för den allmänna etiketten för strikt reglerade filer.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-191">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label or a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="7a7ec-192">Endast gruppmedlemmarna på webbplatsen ser den i listan med underetiketter för etiketten för strikt reglerade data.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-192">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="7a7ec-193">Följ anvisningarna [här](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) när du vill konfigurera en etikett eller en underetikett för etiketten som du använder för strikt reglerade filer med följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-193">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a label or a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="7a7ec-194">Namnet på etiketten eller underetiketten innehåller namnet på webbplatsen för enkel koppling när etiketten eller underetiketten tilldelas en fil.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-194">The name of the label or sublabel contains the name of the site for easy association when assigning the label or sublabel to a file.</span></span>
- <span data-ttu-id="7a7ec-195">Kryptering är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-195">Encryption is enabled.</span></span>
- <span data-ttu-id="7a7ec-196">Webbplatsgruppen har samredigeringsbehörighet</span><span class="sxs-lookup"><span data-stu-id="7a7ec-196">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="7a7ec-197">Konfigurationsresultat</span><span class="sxs-lookup"><span data-stu-id="7a7ec-197">Configuration results</span></span>

<span data-ttu-id="7a7ec-198">Du har konfigurerat följande:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-198">You have configured the following:</span></span>

- <span data-ttu-id="7a7ec-199">Striktare behörighetsinställningar på SharePoint-webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-199">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="7a7ec-200">En Office 365-kvarhållningsetikett som tilldelats dokumentavsnittet på SharePoint-webbplatsen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-200">An Office 365 retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="7a7ec-201">En DLP-princip för Office 365-kvarhållningsetiketten</span><span class="sxs-lookup"><span data-stu-id="7a7ec-201">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="7a7ec-202">En Office 365-känslighetsetikett eller en underetikett som användare kan tillämpa på de känsligaste filerna som lagras på webbplatsen. Den krypterar filer och tillåter bara samtidig redigering för medlemmar i webbplatsgruppen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-202">An Office 365 sensitivity label or sublabel that users can apply to the most sensitive files stored in the site, which encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="7a7ec-203">Här är en konfiguration som använder en underetikett av etiketten för strikt reglerade data.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-203">Here is the resulting configuration that uses a sublabel of the Highly regulated label.</span></span>

![Scenario för SharePoint-webbplatser för strikt reglerade data](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="7a7ec-205">Här är ett exempel på en användare som har tilldelat en underetikett till en fil som lagras på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-205">Here is an example of a user that has applied the sublabel to a file stored in the site.</span></span>

![Scenario för SharePoint-webbplatser för strikt reglerade data](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="7a7ec-207">Fas 3: Driva på användningen</span><span class="sxs-lookup"><span data-stu-id="7a7ec-207">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="7a7ec-208">En SharePoint-webbplats för strikt reglerade data kan bara skydda data om den används konsekvent för lagring och åtkomst till känsliga filer.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-208">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="7a7ec-209">Det här är den svåraste fasen eftersom den förlitar sig på att användarna ändrar sina vanor och inställningar.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-209">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="7a7ec-210">Anställda som till exempel lagrar känsliga filer på USB-enheter eller i privata molnbaserade lagringslösningar måste nu enbart lagra dem på en SharePoint-webbplats för strikt reglerade data.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-210">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="7a7ec-211">Steg 1: Utbilda dina användare</span><span class="sxs-lookup"><span data-stu-id="7a7ec-211">Step 1: Train your users</span></span>

<span data-ttu-id="7a7ec-212">När du har slutfört konfigurationen bör du utbilda användarna som är medlemmar av webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-212">After completing your configuration, train the set of users who are members of the site:</span></span>

- <span data-ttu-id="7a7ec-213">Om vikten av att använda den nya webbplatsen för att skydda värdefulla filer och konsekvenserna av en läcka av strikt reglerade data, till exempel juridiska aspekter, tillsynsböter, utpressningstrojaner eller förlust av konkurrensfördelar.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-213">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="7a7ec-214">Om åtkomst till webbplatsen och dess filer.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-214">How to access the site and its files.</span></span>
- <span data-ttu-id="7a7ec-215">Hur man skapar nya filer på webbplatsen och laddar upp nya filer som lagras lokalt.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-215">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="7a7ec-216">Hur DLP-principen förhindrar dem från att dela filer externt.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-216">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="7a7ec-217">Hur man förser de känsligaste filerna med etiketten eller underetiketten för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-217">How to label the most sensitive files with the label or sublabel for the site.</span></span>
- <span data-ttu-id="7a7ec-218">Hur etiketten eller underetiketten skyddar filer även när de läcker från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-218">How the label or sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="7a7ec-219">I den här utbildningen ska det ingå praktiska övningar så att användarna kan prova funktionerna och se deras resultat.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-219">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="7a7ec-220">Steg 2: Utföra regelbundna granskningar av användning och filer</span><span class="sxs-lookup"><span data-stu-id="7a7ec-220">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="7a7ec-221">Under veckorna efter utbildningen kan SharePoint-administratören för SharePoint-webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="7a7ec-221">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="7a7ec-222">Analysera webbplatsens användning och jämföra med den förväntade användningen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-222">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="7a7ec-223">Kontrollera att strikt reglerade filer har etiketterats korrekt med känslighetsetiketten eller underetiketten.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-223">Verify that highly sensitive files have been properly labeled with the sensitivity label or sublabel.</span></span>

  <span data-ttu-id="7a7ec-224">Du kan se vilka filer som har tilldelats en etikett genom att visa en mapp i SharePoint och lägga till kolumnen **Känslighet** genom alternativet **Visa/dölj kolumner** i **Lägg till kolumn**.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-224">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>


<span data-ttu-id="7a7ec-225">Vidareutbilda dina användare efter behov.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-225">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="7a7ec-226">Användningsresultat</span><span class="sxs-lookup"><span data-stu-id="7a7ec-226">User adoption results</span></span>

<span data-ttu-id="7a7ec-227">Strikt reglerade filer lagras enbart på SharePoint-webbplatser för strikt reglerade data och de känsligaste filerna har tilldelats känslighetsetiketten eller underetiketten för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-227">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity label or sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="7a7ec-228">Så här använde Contoso Corporation en SharePoint-webbplats för strikt reglerade data</span><span class="sxs-lookup"><span data-stu-id="7a7ec-228">How the Contoso Corporation used a SharePoint site for highly regulated data</span></span>

<span data-ttu-id="7a7ec-229">Contoso Corporation är ett fiktivt men representativt globalt tillverkningskonglomerat.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-229">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="7a7ec-230">Se hur Contoso skapade, konfigurerade och införde användningen av en [säker SharePoint-webbplats](contoso-sharepoint-online-site-for-highly-confidential-assets.md) för forskningsteamen i Paris, Moskva, New York, Beijing och Bangalore.</span><span class="sxs-lookup"><span data-stu-id="7a7ec-230">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="7a7ec-231">Se även</span><span class="sxs-lookup"><span data-stu-id="7a7ec-231">See also</span></span>

[<span data-ttu-id="7a7ec-232">Teams för strikt reglerade data</span><span class="sxs-lookup"><span data-stu-id="7a7ec-232">Teams for highly regulated data</span></span>](secure-teams-highly-regulated-data-scenario.md)

[<span data-ttu-id="7a7ec-233">Arbetsbelastningar och scenarier i Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7a7ec-233">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="7a7ec-234">[Produktivitetsbiblioteket för Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="7a7ec-234">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="7a7ec-235">Distributionsguide</span><span class="sxs-lookup"><span data-stu-id="7a7ec-235">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
