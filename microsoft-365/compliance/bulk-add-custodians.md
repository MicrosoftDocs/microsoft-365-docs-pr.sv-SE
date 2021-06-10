---
title: Importera biblioteks till ett Advanced eDiscovery ärende
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Med importverktyget kan du snabbt lägga till flera objekt och deras associerade datakällor till ett ärende i Advanced eDiscovery.
ms.openlocfilehash: 98ff3690fe7fd8c956fce436585014ef0db82a26
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "52161802"
---
# <a name="import-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="65532-103">Importera biblioteks till ett Advanced eDiscovery ärende</span><span class="sxs-lookup"><span data-stu-id="65532-103">Import custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="65532-104">I Advanced eDiscovery fall där många dokumentrepresentanter ingår kan du importera flera dokumentrepresentanter samtidigt genom att använda en CSV-fil som innehåller den information som behövs för att lägga till dem i ett ärende.</span><span class="sxs-lookup"><span data-stu-id="65532-104">For Advanced eDiscovery cases that involve many custodians, you can import multiple custodians at once by using a CSV file that contains the information necessary to add them to a case.</span></span>

## <a name="import-custodians"></a><span data-ttu-id="65532-105">Importera sn3:ar</span><span class="sxs-lookup"><span data-stu-id="65532-105">Import custodians</span></span>

1. <span data-ttu-id="65532-106">Öppna Advanced eDiscovery och välj **fliken Datakällor.**</span><span class="sxs-lookup"><span data-stu-id="65532-106">Open the Advanced eDiscovery case and select the **Data sources** tab.</span></span>

2. <span data-ttu-id="65532-107">Klicka på **Lägg till datakälla** Importera  >  **snianer**.</span><span class="sxs-lookup"><span data-stu-id="65532-107">Click **Add data source** > **Import custodians**.</span></span>

3. <span data-ttu-id="65532-108">På den **utfällsbara sidan Importera** dokumentrepresentanter klickar du på Ladda ned en **tom mall för** att ladda ned en dokumentmall i CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="65532-108">On the **Import custodians** flyout page, click **Download a blank template** to download a custodian template CSV file.</span></span>

   ![Ladda ned en CSV-mall från den utfällsbara sidan Importera dokumentrepresentanter](../media/ImportCustodians1.png)

4. <span data-ttu-id="65532-110">Lägg till ljudinformation i CSV-filen och spara den på din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="65532-110">Add the custodial information to the CSV file and save it to your local computer.</span></span> <span data-ttu-id="65532-111">Mer information om vilka egenskaper som krävs i [CSV-filen](#custodian-csv-file) finns i csv-filens insv-fil.</span><span class="sxs-lookup"><span data-stu-id="65532-111">See the [Custodian CSV file](#custodian-csv-file) section for information about the required properties in the CSV file.</span></span>

5. <span data-ttu-id="65532-112">När du har förberett CSV-filen med den dokumentade informationen går du tillbaka till fliken **Datakällor** och klickar på Lägg till **datakälla**  >  **Importera dokumentianer** igen.</span><span class="sxs-lookup"><span data-stu-id="65532-112">After you've prepared the CSV file with the custodian information, go back to the **Data sources** tab, and click **Add data source** > **Import custodians** again.</span></span>

6. <span data-ttu-id="65532-113">På den **utfällliga** sidan  Importera dokumentrepresentanter klickar du på Bläddra och laddar sedan upp CSV-filen som innehåller den dokumentade informationen.</span><span class="sxs-lookup"><span data-stu-id="65532-113">On the **Import custodians** flyout page, click **Browse** and then upload the CSV file that contains the custodian information.</span></span>

   <span data-ttu-id="65532-114">När CSV-filen har laddats  upp skapas och visas på fliken  Jobb. Jobbet validerar de registrerades och deras associerade datakällor och lägger sedan till dem på **sidan Datakällor** för ärendet.</span><span class="sxs-lookup"><span data-stu-id="65532-114">After the CSV file is uploaded, a job named **BulkAddCustodian** is created and displayed on the **Jobs** tab. The job validates the custodians and their associated data sources and then adds them to the **Data sources** page of the case.</span></span>

## <a name="custodian-csv-file"></a><span data-ttu-id="65532-115">Csv-fil för dokument</span><span class="sxs-lookup"><span data-stu-id="65532-115">Custodian CSV file</span></span>

<span data-ttu-id="65532-116">När du har laddat ned MALLEN CSV-dokument kan du lägga till dokumentrepresentanter och deras datakälla i varje rad.</span><span class="sxs-lookup"><span data-stu-id="65532-116">After you download the CSV custodian template, you can add custodians and their data source in each row.</span></span> <span data-ttu-id="65532-117">Se till att du inte ändrar kolumnnamnen i rubrikraden.</span><span class="sxs-lookup"><span data-stu-id="65532-117">Be sure not to change the column names in the header row.</span></span> <span data-ttu-id="65532-118">Använd kolumnerna typ av arbetsbelastning och arbetsbelastning för att koppla andra datakällor till en vårdnadshavare.</span><span class="sxs-lookup"><span data-stu-id="65532-118">Use the workload type and workload location columns to associate other data sources to a custodian.</span></span>

| <span data-ttu-id="65532-119">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="65532-119">Column name</span></span>|<span data-ttu-id="65532-120">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="65532-120">Description</span></span>|
|:------- |:------------------------------------------------------------|
|<span data-ttu-id="65532-121">**10-postkontakt**</span><span class="sxs-lookup"><span data-stu-id="65532-121">**Custodian contactEmail**</span></span>     |<span data-ttu-id="65532-122">Den insertsiskans UPN-e-postadress.</span><span class="sxs-lookup"><span data-stu-id="65532-122">The custodian's UPN email address.</span></span> <span data-ttu-id="65532-123">Till exempel sarad@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="65532-123">For example, sarad@contoso.onmicrosoft.com.</span></span>           |
|<span data-ttu-id="65532-124">**Exchange Aktiverad**</span><span class="sxs-lookup"><span data-stu-id="65532-124">**Exchange Enabled**</span></span> | <span data-ttu-id="65532-125">SANT/FALSKT-värde för att inkludera eller inte inkludera den som är den som förser postlådan med sitt namn.</span><span class="sxs-lookup"><span data-stu-id="65532-125">TRUE/FALSE value to include or not include the custodian's mailbox.</span></span>      |
|<span data-ttu-id="65532-126">**OneDrive Aktiverad**</span><span class="sxs-lookup"><span data-stu-id="65532-126">**OneDrive Enabled**</span></span> | <span data-ttu-id="65532-127">SANT/FALSKT-värde om du vill inkludera eller inte inkludera den som har OneDrive för företag konto.</span><span class="sxs-lookup"><span data-stu-id="65532-127">TRUE/FALSE value to include or not included the custodian's OneDrive for Business account.</span></span> |
|<span data-ttu-id="65532-128">**Is OnHold**</span><span class="sxs-lookup"><span data-stu-id="65532-128">**Is OnHold**</span></span>        | <span data-ttu-id="65532-129">SANT/FALSKT anger om de verkliga datakällorna ska vara i förvaring.</span><span class="sxs-lookup"><span data-stu-id="65532-129">TRUE/FALSE value to indicate whether to place the custodian data sources on hold.</span></span> <span data-ttu-id="65532-130"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="65532-130"><sup>1</sup></span></span>     |
|<span data-ttu-id="65532-131">**Typ av arbetsbelastning1**</span><span class="sxs-lookup"><span data-stu-id="65532-131">**Workload1 Type**</span></span>         |<span data-ttu-id="65532-132">Strängvärde som anger vilken typ av datakälla som ska associeras med den som ska associeras.</span><span class="sxs-lookup"><span data-stu-id="65532-132">String value indicating the type of data source to associate with the custodian.</span></span> <span data-ttu-id="65532-133">Möjliga värden inkluderar:</span><span class="sxs-lookup"><span data-stu-id="65532-133">Possible values include:</span></span> <br/><span data-ttu-id="65532-134">- ExchangeMailbox</span><span class="sxs-lookup"><span data-stu-id="65532-134">- ExchangeMailbox</span></span><br/> <span data-ttu-id="65532-135">- SharePointSite</span><span class="sxs-lookup"><span data-stu-id="65532-135">- SharePointSite</span></span><br/><span data-ttu-id="65532-136">- TeamsMailbox</span><span class="sxs-lookup"><span data-stu-id="65532-136">- TeamsMailbox</span></span><br/><span data-ttu-id="65532-137">- TeamsSite</span><span class="sxs-lookup"><span data-stu-id="65532-137">- TeamsSite</span></span><br/> <span data-ttu-id="65532-138">- YammerMailbox</span><span class="sxs-lookup"><span data-stu-id="65532-138">- YammerMailbox</span></span><br/><span data-ttu-id="65532-139">- Yammer-webbplats</span><span class="sxs-lookup"><span data-stu-id="65532-139">- YammerSite</span></span> |
|<span data-ttu-id="65532-140">**Workload1 Location**</span><span class="sxs-lookup"><span data-stu-id="65532-140">**Workload1 Location**</span></span>     | <span data-ttu-id="65532-141">Beroende på typ av arbetsbelastning är det här datakällans plats.</span><span class="sxs-lookup"><span data-stu-id="65532-141">Depending on your workload type, this would be the location of the data source.</span></span> <span data-ttu-id="65532-142">Till exempel e-postadressen för en Exchange postlåda eller URL-adressen för en SharePoint webbplats.</span><span class="sxs-lookup"><span data-stu-id="65532-142">For example, the email address for an Exchange mailbox or the URL for a SharePoint site.</span></span> |
|||

> [!NOTE]
> <span data-ttu-id="65532-143"><sup>1</sup> Du kan placera högst 1 000 postlådor och 100 platser i förvaring med hjälp av importprocessen och CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="65532-143"><sup>1</sup> You can place a maximum of 1,000 mailboxes and 100 sites on hold by using the custodian import process and CSV file.</span></span> <span data-ttu-id="65532-144">Du kan använda den här processen för att lägga till fler än 1 000 personer till ett ärende, men begränsningarna för förvaring gäller fortfarande.</span><span class="sxs-lookup"><span data-stu-id="65532-144">You can use this process to add more than 1,000 custodians to a case, but the hold limits still apply.</span></span> <span data-ttu-id="65532-145">Mer information om begränsningar för begränsningar av begränsningar för [begränsningar finns i Advanced eDiscovery](limits-ediscovery20.md#hold-limits).</span><span class="sxs-lookup"><span data-stu-id="65532-145">For more information about hold limits, see [Limits in Advanced eDiscovery](limits-ediscovery20.md#hold-limits).</span></span>

<span data-ttu-id="65532-146">Här är ett exempel på en CSV-fil med dokumentinformation:</span><span class="sxs-lookup"><span data-stu-id="65532-146">Here's an example of a CSV file with custodian information:</span></span><br/><br/>

|<span data-ttu-id="65532-147">10-postkontakt</span><span class="sxs-lookup"><span data-stu-id="65532-147">Custodian contactEmail</span></span>      | <span data-ttu-id="65532-148">Exchange Aktiverad</span><span class="sxs-lookup"><span data-stu-id="65532-148">Exchange Enabled</span></span> | <span data-ttu-id="65532-149">OneDrive Aktiverad</span><span class="sxs-lookup"><span data-stu-id="65532-149">OneDrive Enabled</span></span> | <span data-ttu-id="65532-150">Is OnHold</span><span class="sxs-lookup"><span data-stu-id="65532-150">Is OnHold</span></span> | <span data-ttu-id="65532-151">Typ av arbetsbelastning1</span><span class="sxs-lookup"><span data-stu-id="65532-151">Workload1 Type</span></span> | <span data-ttu-id="65532-152">Workload1 Location</span><span class="sxs-lookup"><span data-stu-id="65532-152">Workload1 Location</span></span>             |
| ----------------- | ---------------- | ---------------- | --------- | -------------- | ------------------------------ |
|<span data-ttu-id="65532-153">robinc@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65532-153">robinc@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="65532-154">TRUE</span><span class="sxs-lookup"><span data-stu-id="65532-154">TRUE</span></span>             | <span data-ttu-id="65532-155">TRUE</span><span class="sxs-lookup"><span data-stu-id="65532-155">TRUE</span></span>             | <span data-ttu-id="65532-156">TRUE</span><span class="sxs-lookup"><span data-stu-id="65532-156">TRUE</span></span>      | <span data-ttu-id="65532-157">SharePointSite</span><span class="sxs-lookup"><span data-stu-id="65532-157">SharePointSite</span></span> | https://contoso.sharepoint.com |
|<span data-ttu-id="65532-158">pillarp@onmicrosoft.contoso.com</span><span class="sxs-lookup"><span data-stu-id="65532-158">pillarp@onmicrosoft.contoso.com</span></span> | <span data-ttu-id="65532-159">TRUE</span><span class="sxs-lookup"><span data-stu-id="65532-159">TRUE</span></span>             | <span data-ttu-id="65532-160">TRUE</span><span class="sxs-lookup"><span data-stu-id="65532-160">TRUE</span></span>             | <span data-ttu-id="65532-161">TRUE</span><span class="sxs-lookup"><span data-stu-id="65532-161">TRUE</span></span>      | |  |
||||||

## <a name="custodian-and-data-source-validation"></a><span data-ttu-id="65532-162">Kontroll av datakälla och datakälla</span><span class="sxs-lookup"><span data-stu-id="65532-162">Custodian and data source validation</span></span>

<span data-ttu-id="65532-163">När du har laddat upp den uppsvända CSV Advanced eDiscovery filen gör du följande:</span><span class="sxs-lookup"><span data-stu-id="65532-163">After you upload the custodian CSV file, Advanced eDiscovery does the following things:</span></span>

1. <span data-ttu-id="65532-164">Verifierar de som har godkänt den och deras datakällor.</span><span class="sxs-lookup"><span data-stu-id="65532-164">Validates the custodians and their data sources.</span></span>

2. <span data-ttu-id="65532-165">Indexerar alla datakällor för varje dokumentägare och placerar dem i förvaring (om egenskapen **Is OnHold** i CSV-filen är inställd på SANT).</span><span class="sxs-lookup"><span data-stu-id="65532-165">Indexes all data sources for each custodian and places them on hold (if the **Is OnHold** property in the CSV file is set to TRUE).</span></span>

### <a name="custodian-validation"></a><span data-ttu-id="65532-166">Insidningsvalidering</span><span class="sxs-lookup"><span data-stu-id="65532-166">Custodian validation</span></span>

<span data-ttu-id="65532-167">För närvarande stöder vi endast import av biblioteksmedlemmar som ingår i organisationens Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="65532-167">Currently, we only support importing custodians that are included in your organization's Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="65532-168">Det dokumentariska importverktyget söker efter och verifierar dokumentrepresentanter med HJÄLP av UPN-värdet i kolumnen **Förnamnkontaktepost** i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="65532-168">The custodian import tool finds and validates custodians using the UPN value in the **Custodian contactEmail** column in the CSV file.</span></span> <span data-ttu-id="65532-169">Om någon har verifierat en datakälla läggs den till automatiskt i ärendet och listas på fliken **Datakällor** för ärendet.</span><span class="sxs-lookup"><span data-stu-id="65532-169">Custodians that are validated are automatically added to the case and listed on the **Data sources** tab of the case.</span></span> <span data-ttu-id="65532-170">Om en vårdnadshavare inte kan verifieras visas de i felloggen för det BulkAddCustodian-jobb som finns på fliken Jobb för ärendet. </span><span class="sxs-lookup"><span data-stu-id="65532-170">If a custodian can't be validated, they are listed in the error log for the BulkAddCustodian job that is listed on the **Jobs** tab in the case.</span></span> <span data-ttu-id="65532-171">Ej registrerade bibliotek läggs inte till i ärendet eller visas på **fliken Datakällor.**</span><span class="sxs-lookup"><span data-stu-id="65532-171">Unvalidated custodians are not added to the case or listed on the **Data sources** tab.</span></span>

### <a name="data-source-validation"></a><span data-ttu-id="65532-172">Datakällverifiering</span><span class="sxs-lookup"><span data-stu-id="65532-172">Data source validation</span></span>

<span data-ttu-id="65532-173">När brevlådor valideras och läggs till i ärendet läggs varje primär postlåda och OneDrive konto som är kopplat till en vårdnadshavare till.</span><span class="sxs-lookup"><span data-stu-id="65532-173">After custodians are validated and added to the case, each primary mailbox and OneDrive account that's associated with a custodian is added.</span></span>

<span data-ttu-id="65532-174">Men om någon av de andra datakällorna (t.ex. SharePoint-webbplatser, Microsoft Teams-, Microsoft 365-grupper eller Yammer-grupper) som är kopplade till en användare inte kan hittas, tilldelas inga av dem till den verifieradeianen och värdet Verifierad visas i kolumnen **Status** bredvid den som är godkänd på fliken **Datakällor.** </span><span class="sxs-lookup"><span data-stu-id="65532-174">However, if any of the other data sources (such as SharePoint sites, Microsoft Teams, Microsoft 365 Groups, or Yammer groups) associated with a custodian can't be found, none of them are assigned to the custodian and the value **Not validated** is displayed in the **Status** column next to the custodian on the **Data sources** tab.</span></span>

<span data-ttu-id="65532-175">Så här lägger du till verifierade datakällor för en vårdnadshavare:</span><span class="sxs-lookup"><span data-stu-id="65532-175">To add validated data sources for a custodian:</span></span>

1. <span data-ttu-id="65532-176">På fliken **Datakällor** väljer du en dokumenterare som innehåller datakällor som inte är verifierade.</span><span class="sxs-lookup"><span data-stu-id="65532-176">On the **Data sources** tab, select a custodian that contains data sources that aren't validated.</span></span>

2. <span data-ttu-id="65532-177">På den utfällliga sidan  för den verifierade person som ingår bläddrar du till avsnittet Förfallna platser för att visa både verifierade och icke verifierade datakällor som är associerade med verifierare.</span><span class="sxs-lookup"><span data-stu-id="65532-177">On the custodian flyout page, scroll to the **Custodial locations** section to view both validated and unvalidated data sources that are associated with custodian.</span></span>

3. <span data-ttu-id="65532-178">Klicka **på** Redigera högst upp på den utfällliga sidan om du vill ta bort ogiltiga datakällor eller lägga till nya.</span><span class="sxs-lookup"><span data-stu-id="65532-178">Click **Edit** at the top of the flyout page to remove invalid data sources or add new ones.</span></span>

4. <span data-ttu-id="65532-179">När du tar bort oberäknade datakällor eller  lägger till en ny, visas värdet Aktiv i kolumnen **Status** för den vårdnadshavare som inte har något värde på **fliken Datakällor.** Om du vill lägga till källor som tidigare såg ut att vara ogiltiga följer du åtgärdsstegen nedan för att manuellt lägga till dem till en vårdnadshavare.</span><span class="sxs-lookup"><span data-stu-id="65532-179">After you remove unvalidated data sources or add a new one, the value **Active** is displayed in **Status** column for the custodian on the **Data sources** tab. To add sources that previously appeared to be invalid, follow the remediation steps below to manually add them to a custodian.</span></span>

### <a name="remediating-invalid-data-sources"></a><span data-ttu-id="65532-180">Åtgärda ogiltiga datakällor</span><span class="sxs-lookup"><span data-stu-id="65532-180">Remediating invalid data sources</span></span>

<span data-ttu-id="65532-181">Så här lägger du till och associerar en datakälla som tidigare var ogiltig:</span><span class="sxs-lookup"><span data-stu-id="65532-181">To manually add and associate a data source that was previously invalid:</span></span>

1. <span data-ttu-id="65532-182">På fliken **Datakällor väljer** du en vårdnadshavare att manuellt lägga till och associera en datakälla som tidigare var ogiltig.</span><span class="sxs-lookup"><span data-stu-id="65532-182">On the **Data sources** tab, select a custodian to manually add and associate a data source that was previously invalid.</span></span>

2. <span data-ttu-id="65532-183">Klicka **på** Redigera högst upp på den utfällliga sidan om du vill associera postlådor, webbplatser, Teams eller Yammer postgrupper med den tor just nu.</span><span class="sxs-lookup"><span data-stu-id="65532-183">Click **Edit** at the top of the flyout page to associate mailboxes, sites, Teams, or Yammer groups to the custodian.</span></span> <span data-ttu-id="65532-184">Det gör du genom **att** klicka på Redigera bredvid rätt dataplatstyp.</span><span class="sxs-lookup"><span data-stu-id="65532-184">Do this by clicking **Edit** next to the appropriate data location type.</span></span>

3. <span data-ttu-id="65532-185">Klicka **på** Nästa för att visa **sidan Inställningar för** håll och konfigurera inställningen för att vänta för de datakällor du lagt till.</span><span class="sxs-lookup"><span data-stu-id="65532-185">Click **Next** to display the **Hold settings** page and configure the hold setting for the data sources you added.</span></span>

4. <span data-ttu-id="65532-186">Klicka **på Nästa** för att visa sidan Granska **granskare** och klicka sedan på **Skicka för** att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="65532-186">Click **Next** to display the **Review custodians** page, and then click **Submit** to save your changes.</span></span>
