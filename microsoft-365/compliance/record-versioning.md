---
title: Använd versionshantering för att uppdatera arkivhandlingar som lagras i SharePoint eller OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Läs mer om arkivhandlingar som hjälper dig att implementera en lösning för hantering av arkivhandlingar i Microsoft 365.
ms.openlocfilehash: 5c828f06f2ce9e2bd18869f897f1f372c1a62f21
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "52162605"
---
# <a name="use-record-versioning-to-update-records-stored-in-sharepoint-or-onedrive"></a><span data-ttu-id="08fad-103">Använd versionshantering för att uppdatera arkivhandlingar som lagras i SharePoint eller OneDrive</span><span class="sxs-lookup"><span data-stu-id="08fad-103">Use record versioning to update records stored in SharePoint or OneDrive</span></span>

><span data-ttu-id="08fad-104">*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="08fad-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

>[!NOTE] 
> <span data-ttu-id="08fad-105">Eftersom regelbaserade arkivhandlingar blockerar redigering är inte versionshantering tillgänglig för regelbaserade arkivhandlingar.</span><span class="sxs-lookup"><span data-stu-id="08fad-105">Because regulatory records block editing, record versioning is not available for regulatory records.</span></span>

<span data-ttu-id="08fad-106">Möjligheten att markera ett dokument som en [arkivhandling](records-management.md#records) och begränsa åtgärder som kan utföras för den är ett viktigt mål för alla lösningar för hantering av arkivhandlingar.</span><span class="sxs-lookup"><span data-stu-id="08fad-106">The ability to mark a document as a [record](records-management.md#records) and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="08fad-107">Dock kan det även behövas samarbete för att skapa senare versioner.</span><span class="sxs-lookup"><span data-stu-id="08fad-107">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="08fad-108">Du kan till exempel markera ett säljavtal som en arkivhandling, men sedan måste du uppdatera avtalet med nya villkor och markera den senaste versionen som en ny arkivhandling samtidigt som du behåller den tidigare versionen.</span><span class="sxs-lookup"><span data-stu-id="08fad-108">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="08fad-109">För de här typerna av scenarier har SharePoint och OneDrive stöd för *versionshantering av arkivhandlingar*.</span><span class="sxs-lookup"><span data-stu-id="08fad-109">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="08fad-110">Mappar i OneNote-anteckningsböcker har inte stöd för versionshantering av arkivhandlingar.</span><span class="sxs-lookup"><span data-stu-id="08fad-110">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="08fad-111">Om du vill använda versionshantering för arkivhandlingar [namnger du först dokumentet och markerar det som en arkivhandling](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="08fad-111">To use record versioning, you first [label the document and mark it as a record](declare-records.md).</span></span> <span data-ttu-id="08fad-112">I det här skedet visas en dokumentegenskap som kallas *Arkivhandlingsstatus* bredvid bevarandeetiketten och den första statusen är **Låst**.</span><span class="sxs-lookup"><span data-stu-id="08fad-112">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="08fad-113">Nu kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="08fad-113">You can now do the following things:</span></span>

  - <span data-ttu-id="08fad-114">**Redigera kontinuerligt och behåll enskilda versioner av dokumentet som arkivhandlingar genom att låsa upp och låsa egenskapen Arkivhandlingsstatus.**</span><span class="sxs-lookup"><span data-stu-id="08fad-114">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="08fad-115">Endast när egenskapen **Arkivhandlingsstatus** är inställd på **Låst** kan en ny version av arkivhandlingen behållas.</span><span class="sxs-lookup"><span data-stu-id="08fad-115">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="08fad-116">Genom att växla mellan låsta och olåsta dokument minskar risken att onödiga versioner och kopior behålls av dokumentet.</span><span class="sxs-lookup"><span data-stu-id="08fad-116">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="08fad-117">**Lagra arkivhandlingarna automatiskt i en lagringsplats för arkivhandlingar på plats inom webbplatssamlingen.**</span><span class="sxs-lookup"><span data-stu-id="08fad-117">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="08fad-118">Varje webbplatssamling i SharePoint och OneDrive bevarar innehållet i sitt bibliotek för bevarande av dokument.</span><span class="sxs-lookup"><span data-stu-id="08fad-118">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="08fad-119">Arkivhandlingsversioner lagras i mappen Arkivhandlingar i det här biblioteket.</span><span class="sxs-lookup"><span data-stu-id="08fad-119">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="08fad-120">**Bevara ett evighetsdokument som innehåller alla versioner.**</span><span class="sxs-lookup"><span data-stu-id="08fad-120">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="08fad-121">Som standard har varje SharePoint- och OneDrive-dokument en versionshistorik tillgänglig på objektmenyn.</span><span class="sxs-lookup"><span data-stu-id="08fad-121">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="08fad-122">I den här versionshistoriken kan du enkelt se vilka versioner som är arkivhandlingar och visa dessa dokument.</span><span class="sxs-lookup"><span data-stu-id="08fad-122">In this version history, you can easily see which versions are records and view those documents.</span></span>

> [!TIP]
> <span data-ttu-id="08fad-123">När du använder versionshantering för arkivhandlingar med en bevarandeetikett som har en borttagningsåtgärd kan du konfigurera bevarandeinställningen **Starta bevarandetiden baserat på:** till **När objekt har etiketter**.</span><span class="sxs-lookup"><span data-stu-id="08fad-123">When you use record versioning with a retention label that has a delete action, consider configuring the retention setting **Start the retention period based on:** to be **When items were labeled**.</span></span> <span data-ttu-id="08fad-124">Med den här etikettinställningen återställs bevarandetidens början för varje ny arkivhandlingsversion, vilket säkerställer att äldre versioner tas bort innan nyare versioner.</span><span class="sxs-lookup"><span data-stu-id="08fad-124">With this label setting, the start of the retention period is reset for each new record version, which ensures that older versions will be deleted before newer versions.</span></span>

<span data-ttu-id="08fad-125">Versionshantering för arkivhandlingar är automatiskt tillgängligt för alla dokument som har en bevarandeetikett som markerar objektet som en arkivhandling.</span><span class="sxs-lookup"><span data-stu-id="08fad-125">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="08fad-126">När en användare visar dokumentegenskaperna med hjälp av informationsfönstret kan de växla **Status** från **Låst** till **Olåst**.</span><span class="sxs-lookup"><span data-stu-id="08fad-126">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="08fad-127">Den här åtgärden skapar en arkivhandling i mappen Arkivhandlingar i biblioteket för bevarande av dokument, där den finns i resten av bevarandeperioden.</span><span class="sxs-lookup"><span data-stu-id="08fad-127">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="08fad-128">Även om dokumentet är olåst kan alla användare med standardredigeringsbehörighet redigera filen.</span><span class="sxs-lookup"><span data-stu-id="08fad-128">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="08fad-129">Användare kan dock inte ta bort filen eftersom det fortfarande är en arkivhandling.</span><span class="sxs-lookup"><span data-stu-id="08fad-129">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="08fad-130">När redigeringen är klar kan en användare sedan växla **Status** från **Olåst** till **Låst**, vilket förhindrar ytterligare redigeringar när denna status har valts.</span><span class="sxs-lookup"><span data-stu-id="08fad-130">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Egenskapen arkivhandlingsstatus på dokumentet som taggats som arkivhandling](../media/recordversioning8.png)

## <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="08fad-132">Låsa och låsa upp en arkivhandling</span><span class="sxs-lookup"><span data-stu-id="08fad-132">Locking and unlocking a record</span></span>

<span data-ttu-id="08fad-133">När en bevarandeetikett som markerar innehåll som en arkivhandling tillämpas på ett dokument kan alla användare med behörigheten Delta eller mer begränsad behörighetsnivå låsa upp eller låsa en olåst arkivhandling.</span><span class="sxs-lookup"><span data-stu-id="08fad-133">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![Status visar att arkivhandlingsdokumentet är olåst](../media/recordversioning9.png)

<span data-ttu-id="08fad-135">När en användare låser upp en arkivhandling sker följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="08fad-135">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="08fad-136">Om den aktuella webbplatssamlingen inte har ett bibliotek för bevarande av dokument skapas ett sådant.</span><span class="sxs-lookup"><span data-stu-id="08fad-136">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="08fad-137">Om biblioteket för bevarande av dokument inte har någon Arkivhandlingar-mapp skapas en sådan.</span><span class="sxs-lookup"><span data-stu-id="08fad-137">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="08fad-138">Åtgärden **Kopiera till** kopierar den senaste versionen av dokumentet till mappen Arkivhandlingar.</span><span class="sxs-lookup"><span data-stu-id="08fad-138">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="08fad-139">Åtgärden **Kopiera till** inkluderar bara den senaste versionen och inga tidigare versioner.</span><span class="sxs-lookup"><span data-stu-id="08fad-139">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="08fad-140">Det kopierade dokumentet anses nu vara en arkivhandlingsversion av dokumentet och filnamnet har formatet: \[Rubrik GUID version\#\]</span><span class="sxs-lookup"><span data-stu-id="08fad-140">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="08fad-141">Kopian som skapas i mappen Arkivhandlingar läggs till i versionshistoriken för det ursprungliga dokumentet och i den här versionen visas ordet **Arkivhandling** i kommentarsfältet.</span><span class="sxs-lookup"><span data-stu-id="08fad-141">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="08fad-142">Originaldokumentet är en ny version som kan redigeras, men inte tas bort.</span><span class="sxs-lookup"><span data-stu-id="08fad-142">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="08fad-143">Kolumnen Dokumentbibliotek **Objektet är en arkivhandling** visar fortfarande värdet **Ja** eftersom dokumentet fortfarande är en arkivhandling, även om det nu kan redigeras.</span><span class="sxs-lookup"><span data-stu-id="08fad-143">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="08fad-144">När en användare låser en arkivhandling kan det ursprungliga dokumentet inte redigeras igen.</span><span class="sxs-lookup"><span data-stu-id="08fad-144">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="08fad-145">Men det är åtgärden att låsa upp en arkivhandling som kopierar en version till mappen Arkivhandlingar i biblioteket för bevarande av dokument.</span><span class="sxs-lookup"><span data-stu-id="08fad-145">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

## <a name="record-versions"></a><span data-ttu-id="08fad-146">Arkivhandlingsversioner</span><span class="sxs-lookup"><span data-stu-id="08fad-146">Record versions</span></span>

<span data-ttu-id="08fad-147">Varje gång en användare låser upp en arkivhandling kopieras den senaste versionen till biblioteket för bevarande av dokument och den versionen innehåller värdet för **Arkivhandling** i fältet **Kommentarer** i versionshistoriken.</span><span class="sxs-lookup"><span data-stu-id="08fad-147">Each time a user unlocks a record, the latest version is copied to the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Arkivhandling som visas i biblioteket för bevarande av dokument](../media/recordversioning10.png)

<span data-ttu-id="08fad-149">Om du vill visa versionshistoriken markerar du ett dokument i dokumentbiblioteket och klickar sedan på **Versionshistorik** i objektmenyn.</span><span class="sxs-lookup"><span data-stu-id="08fad-149">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

## <a name="where-records-are-stored"></a><span data-ttu-id="08fad-150">Var arkivhandlingar lagras</span><span class="sxs-lookup"><span data-stu-id="08fad-150">Where records are stored</span></span>

<span data-ttu-id="08fad-151">Arkivhandlingar lagras i mappen Arkivhandlingar i biblioteket för bevarande av dokument i webbplats på översta nivån i webbplatssamlingen.</span><span class="sxs-lookup"><span data-stu-id="08fad-151">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="08fad-152">I det vänstra navigeringsfältet på webbplatsen på översta nivån väljer du **Webbplatsinnehåll** för\> **bibliotek för bevarande av dokument**.</span><span class="sxs-lookup"><span data-stu-id="08fad-152">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Bibliotek för bevarande av dokument](../media/recordversioning11.png)

<br/><br/>

![Mappen Arkivhandlingar i biblioteket för bevarande av dokument](../media/recordversioning12.png)

<span data-ttu-id="08fad-155">Mer information om hur biblioteket för bevarande av dokument fungerar finns i [Hur bevarande fungerar för SharePoint och OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span><span class="sxs-lookup"><span data-stu-id="08fad-155">For more information about how the Preservation Hold library works, see [How retention works for SharePoint and OneDrive](retention-policies-sharepoint.md#how-retention-works-for-sharepoint-and-onedrive).</span></span>

## <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="08fad-156">Söka i granskningsloggen efter händelser för versionshantering av arkivhandlingar</span><span class="sxs-lookup"><span data-stu-id="08fad-156">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="08fad-157">Åtgärderna för att låsa och låsa upp arkivhandlingar loggas i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="08fad-157">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="08fad-158">Från **Fil- och sidaktiviteter** väljer du **Status för arkivhandlingar ändrad till låst** och **Status för arkivhandlingar ändrad till olåst**.</span><span class="sxs-lookup"><span data-stu-id="08fad-158">From **File and page activities**, select **Changed record status to locked** and **Changed record status to unlocked**.</span></span>

<span data-ttu-id="08fad-159">Mer information om hur du söker efter de här händelserna finns [Söka i granskningsloggen i Säkerhets- och efterlevnadscenter](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="08fad-159">For more information about searching for these events, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="08fad-160">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="08fad-160">Next steps</span></span>

<span data-ttu-id="08fad-161">Fler scenarier som stöds av hantering av arkivhandlingar hittar du här: [Vanliga scenarier för hantering av arkivhandlingar](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="08fad-161">For other scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>