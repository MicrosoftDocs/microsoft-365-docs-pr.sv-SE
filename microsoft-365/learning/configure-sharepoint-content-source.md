---
title: 'Kommer snart: Konfigurera SharePoint som en källa för utbildningsinnehåll för Microsoft Viva Learning (förhandsversion)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Lär dig hur du SharePoint som innehållskälla för utbildning för Microsoft Viva Learning (förhandsversion).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fc702f57b75b78ab523226ba7d8a8eb6505f2975
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244143"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="c80ea-103">Kommer snart: Konfigurera SharePoint som en källa för utbildningsinnehåll för Microsoft Viva Learning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="c80ea-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="c80ea-104">Informationen i den här artikeln gäller en förhandsversion av en produkt som kan komma att ändras väsentligt innan den släpps till kommersiellt bruk.</span><span class="sxs-lookup"><span data-stu-id="c80ea-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="c80ea-105">Du kan konfigurera SharePoint som en källa för utbildningsinnehåll för att göra organisationens eget innehåll tillgängligt i Viva Learning (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="c80ea-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="c80ea-106">Översikt</span><span class="sxs-lookup"><span data-stu-id="c80ea-106">Overview</span></span>

<span data-ttu-id="c80ea-107">Kunskapsadministratören (eller global administratör) tillhandahåller en webbplats-URL till där utbildningstjänsten kan skapa en tom centraliserad plats – lagringsplatsen för innehåll i utbildningsappen – i form av en strukturerad SharePoint lista.</span><span class="sxs-lookup"><span data-stu-id="c80ea-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="c80ea-108">Den här listan kan användas av din organisation för att hålla länkar till företagsbaserade SharePoint som innehåller utbildningsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="c80ea-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="c80ea-109">Administratörer ansvarar för att samla in och administrera en lista med URL:er för mappar.</span><span class="sxs-lookup"><span data-stu-id="c80ea-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="c80ea-110">De här mapparna bör endast innehålla innehåll som kan göras tillgängligt i Viva Learning (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="c80ea-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="c80ea-111">Viva Learning (förhandsversion) har stöd för följande dokumenttyper:</span><span class="sxs-lookup"><span data-stu-id="c80ea-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="c80ea-112">Word, PowerPoint, Excel PDF</span><span class="sxs-lookup"><span data-stu-id="c80ea-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="c80ea-113">Ljud (.m4a)</span><span class="sxs-lookup"><span data-stu-id="c80ea-113">Audio (.m4a)</span></span>
- <span data-ttu-id="c80ea-114">Video (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="c80ea-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="c80ea-115">Mer information finns i [SharePoint begränsningar](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span><span class="sxs-lookup"><span data-stu-id="c80ea-115">For more information, see [SharePoint limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="c80ea-116">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="c80ea-116">Permissions</span></span>

<span data-ttu-id="c80ea-117">URL-adresser för dokumentbiblioteksmappar kan samlas in från SharePoint webbplats i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c80ea-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="c80ea-118">Viva Learning (förhandsversion) följer alla befintliga innehållsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="c80ea-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="c80ea-119">Därför är endast innehåll där en användare har behörighet att komma åt sökbart och synligt i Viva Learning (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="c80ea-119">Therefore, only content for which a user has permission to access is searchable and visible within Viva Learning (Preview).</span></span> <span data-ttu-id="c80ea-120">Allt innehåll i de här mapparna är sökbart, men endast innehåll som de enskilda anställda har behörighet till kan användas.</span><span class="sxs-lookup"><span data-stu-id="c80ea-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="c80ea-121">Borttagning av innehåll från organisationens lagringsplats stöds inte för närvarande.</span><span class="sxs-lookup"><span data-stu-id="c80ea-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="c80ea-122">Gör så här om du vill ta bort innehåll som inte fick visas av dig:</span><span class="sxs-lookup"><span data-stu-id="c80ea-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="c80ea-123">Om du vill begränsa åtkomsten till dokumentbiblioteket **väljer du alternativet Visa** åtgärder och sedan Hantera **åtkomst.**</span><span class="sxs-lookup"><span data-stu-id="c80ea-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Dokumentbibliotekssidan i SharePoint visar alternativet Visa åtgärder med Hantera åtkomst högtryckt.](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="c80ea-125">Ta bort det ursprungliga dokumentet i dokumentbiblioteket.</span><span class="sxs-lookup"><span data-stu-id="c80ea-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="c80ea-126">Mer information finns i [Delning och behörigheter i den SharePoint moderna upplevelsen.](/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="c80ea-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="c80ea-127">Utbildningstjänst</span><span class="sxs-lookup"><span data-stu-id="c80ea-127">Learning Service</span></span>

<span data-ttu-id="c80ea-128">Tjänsten utbildning använder de angivna mapp-URL:erna för att hämta metadata från allt innehåll som lagras i de mapparna.</span><span class="sxs-lookup"><span data-stu-id="c80ea-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="c80ea-129">Inom 24 timmar efter att mapp-URL:en har levererats på den centrala lagringsplatsen kan anställda söka efter och använda organisationens innehåll i Viva Learning (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="c80ea-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="c80ea-130">Alla ändringar av innehåll, inklusive uppdaterade metadata och behörigheter, kommer också att tillämpas i utbildningstjänsten inom 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="c80ea-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="c80ea-131">Konfigurera SharePoint som en källa</span><span class="sxs-lookup"><span data-stu-id="c80ea-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="c80ea-132">Du måste vara global Microsoft 365, administratör SharePoint eller kunskapsadministratör för att kunna utföra de här uppgifterna.</span><span class="sxs-lookup"><span data-stu-id="c80ea-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="c80ea-133">Följ de SharePoint om du vill konfigurera SharePoint informationskällor för utbildningsinnehåll i för Viva Learning (förhandsversion):</span><span class="sxs-lookup"><span data-stu-id="c80ea-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="c80ea-134">I det vänstra navigeringsfältet i Microsoft 365 administrationscenter går du **till Inställningar**  >  **Organisationsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="c80ea-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="c80ea-135">Välj  **Viva Learning (förhandsversion)** **på** fliken Tjänster på sidan Organisationsinställningar.</span><span class="sxs-lookup"><span data-stu-id="c80ea-135">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![Inställningar på sidan Microsoft 365 administrationscenter som visar Viva Learning.](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="c80ea-137">På panelen **Viva Learning (förhandsversion)** under SharePoint hittar du webbplats-URL:en till den SharePoint-webbplats där du vill att Viva Learning (förhandsversion) ska skapa en central lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="c80ea-137">On the **Viva Learning (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning (Preview) to create a centralized repository.</span></span>

     ![Utbildningspanelen i administrationscentret Microsoft 365 som visar SharePoint markerat.](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="c80ea-139">En SharePoint skapas automatiskt på den angivna SharePoint webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="c80ea-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Nyligen SharePoint lista SharePoint webbplatsen.](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="c80ea-141">I det vänstra navigeringsfältet på SharePoint väljer du **Lagringsplats för**  >  **utbildningsappens innehåll för webbplatsinnehåll.**</span><span class="sxs-lookup"><span data-stu-id="c80ea-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![SharePoint över navigeringen för webbplatsinnehåll och lagringsplatsen för utbildningsappens innehåll.](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="c80ea-143">På sidan **Lagringsplats för innehåll i** utbildningsappar fyller du i SharePoint med WEBBADRESSer till mapparna med utbildningsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="c80ea-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="c80ea-144">Välj **Ny** för att visa **panelen Nytt** objekt.</span><span class="sxs-lookup"><span data-stu-id="c80ea-144">Select **New** to view the **New item** panel.</span></span> 

       ![Sidan Lagring för utbildningsinnehåll i SharePoint med alternativet Nytt.](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="c80ea-146">På panelen **Nytt objekt** går du till **fältet Rubrik** och lägger till ett valfri katalognamn.</span><span class="sxs-lookup"><span data-stu-id="c80ea-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="c80ea-147">Lägg till **URL:en** till mappen utbildningsinnehåll i fältet Mapp-URL.</span><span class="sxs-lookup"><span data-stu-id="c80ea-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="c80ea-148">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c80ea-148">Select **Save**.</span></span>

       ![Panelen Nytt objekt i SharePoint med fälten Rubrik och Mapp-URL.](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="c80ea-150">Sidan **lagringsplats för innehåll i utbildningsappen** uppdateras med det nya utbildningsinnehållet.</span><span class="sxs-lookup"><span data-stu-id="c80ea-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Sidan Lagringsplats för utbildningsinnehåll i SharePoint visar den uppdaterade informationen.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="c80ea-152">För att ge bredare åtkomst till lagringsplatsen för innehåll i utbildningsappen kommer en länk till listan snart att finnas i gränssnittet för Viva Learning (förhandsversion) där användare kan begära åtkomst och få hjälp med att fylla på listan.</span><span class="sxs-lookup"><span data-stu-id="c80ea-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="c80ea-153">Webbplatsägare och globala administratörer måste bevilja åtkomst till listan.</span><span class="sxs-lookup"><span data-stu-id="c80ea-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="c80ea-154">Access är bara specifikt för listan och gäller inte för webbplatsen där listan lagras.</span><span class="sxs-lookup"><span data-stu-id="c80ea-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="c80ea-155">Mer information finns i [Artikeln om att tillhandahålla organisationens innehåll](#provide-your-own-organizations-content) längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="c80ea-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="c80ea-156">Dokumentbiblioteks curation för mapp-URL</span><span class="sxs-lookup"><span data-stu-id="c80ea-156">Folder URL document library curation</span></span>

<span data-ttu-id="c80ea-157">Standardmetadata (t.ex. ändringsdatum, skapat av, dokumentnamn, innehållstyp och organisationsnamn) hämtas automatiskt till Viva Learning (förhandsversion) av Microsoft Graph API.</span><span class="sxs-lookup"><span data-stu-id="c80ea-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="c80ea-158">För att förbättra den övergripande identifieringen och sökrelevansen för innehållet rekommenderar vi att du lägger till **en beskrivningskolumn.**</span><span class="sxs-lookup"><span data-stu-id="c80ea-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="c80ea-159">Så här lägger **du** till en beskrivningskolumn på dokumentbibliotekssidan:</span><span class="sxs-lookup"><span data-stu-id="c80ea-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="c80ea-160">På sidan **Dokument** väljer du Lägg **till kolumn**.</span><span class="sxs-lookup"><span data-stu-id="c80ea-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="c80ea-161">Välj **alternativet Visa** åtgärder och välj sedan **Enskild rad med text.**</span><span class="sxs-lookup"><span data-stu-id="c80ea-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![Dokumentsidan i SharePoint visar alternativen Visa åtgärder med Enskild rad med text markerad.](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="c80ea-163">Lägg **till ett beskrivande** namn för **kolumnen i fältet** Namn på panelen Skapa en kolumn.</span><span class="sxs-lookup"><span data-stu-id="c80ea-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="c80ea-164">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c80ea-164">Select **Save**.</span></span>

     ![Skapa en kolumnpanel i SharePoint visar Namn och andra fält.](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="c80ea-166">Lägg **till anpassade** beskrivningar för **varje objekt** i kolumnen Beskrivning på sidan Dokument.</span><span class="sxs-lookup"><span data-stu-id="c80ea-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="c80ea-167">Om ingen beskrivning anges kommer Viva Learning (förhandsversion) att tillhandahålla ett standardmeddelande som markerar innehållet som att det kommer från ditt SharePoint bibliotek.</span><span class="sxs-lookup"><span data-stu-id="c80ea-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![Dokumentsidan i SharePoint beskrivningarna i kolumnen Beskrivning.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="c80ea-169">Tillhandahålla innehållet för din egen organisation</span><span class="sxs-lookup"><span data-stu-id="c80ea-169">Provide your own organization's content</span></span>

<span data-ttu-id="c80ea-170">Kunskapsadministratörer kan komma åt organisationens lagringsplats för innehåll i utbildningsappen i SharePoint, där de kan hänvisa till dokumentbibliotek mellan olika organisationer.</span><span class="sxs-lookup"><span data-stu-id="c80ea-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="c80ea-171">Innehåll i de här biblioteken visas sedan som utbildningsinnehåll i Viva Learning (förhandsversion).</span><span class="sxs-lookup"><span data-stu-id="c80ea-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="c80ea-172">I Viva Learning (förhandsversion) väljer **du Fler alternativ** (**...**) och väljer **sedan Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="c80ea-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![SharePoint visar fler alternativ och alternativ Inställningar bibliotekssidan.](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="c80ea-174">Under **Inställningar** väljer du **Behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="c80ea-174">Under **Settings**, select **Permissions**.</span></span>

     ![Inställningar alternativsidan i SharePoint med alternativen Behörigheter och Kontrollera åtkomst.](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="c80ea-176">Välj **Kontrollera åtkomst** för att ansluta till organisationens centrala bibliotek.</span><span class="sxs-lookup"><span data-stu-id="c80ea-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
