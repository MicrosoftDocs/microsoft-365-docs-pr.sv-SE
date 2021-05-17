---
title: Kom igång med innehållsutforskaren
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Med innehållsutforskaren kan du se etiketterade objekt.
ms.openlocfilehash: b39dd09012e7cde6c19ea88a0915154da84c712a
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52163007"
---
# <a name="get-started-with-content-explorer"></a><span data-ttu-id="91df8-103">Kom igång med innehållsutforskaren</span><span class="sxs-lookup"><span data-stu-id="91df8-103">Get started with content explorer</span></span>

<span data-ttu-id="91df8-104">Med innehållsutforskaren för dataklassificering kan du se objekten som sammanfattas på översiktssidan.</span><span class="sxs-lookup"><span data-stu-id="91df8-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

![komprimerad skärmbild av innehållsutforskaren](../media/data-classification-content-explorer-1.png)

## <a name="prerequisites"></a><span data-ttu-id="91df8-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="91df8-106">Prerequisites</span></span>

<span data-ttu-id="91df8-107">Varje konto som har åtkomst till och använder dataklassificering, måste ha en tilldelad licens från någon av dessa prenumerationer:</span><span class="sxs-lookup"><span data-stu-id="91df8-107">Every account that accesses and uses data classification must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="91df8-108">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="91df8-108">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="91df8-109">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="91df8-109">Office 365 (E5)</span></span>
- <span data-ttu-id="91df8-110">Tillägget Advanced Compliance (E5)</span><span class="sxs-lookup"><span data-stu-id="91df8-110">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="91df8-111">Tillägget Advanced Threat Intelligence (E5)</span><span class="sxs-lookup"><span data-stu-id="91df8-111">Advanced Threat Intelligence (E5) add-on</span></span>
- <span data-ttu-id="91df8-112">Microsoft 365 E5/A5 – Informationsskydd och styrning</span><span class="sxs-lookup"><span data-stu-id="91df8-112">Microsoft 365 E5/A5 Info Protection & Governance</span></span>
- <span data-ttu-id="91df8-113">Microsoft 365 E5/A5 – Efterlevnad</span><span class="sxs-lookup"><span data-stu-id="91df8-113">Microsoft 365 E5/A5 Compliance</span></span>


### <a name="permissions"></a><span data-ttu-id="91df8-114">Behörigheter</span><span class="sxs-lookup"><span data-stu-id="91df8-114">Permissions</span></span>

<span data-ttu-id="91df8-115">För att få åtkomst till fliken Innehållsutforskare måste ett konto tilldelas medlemskap i någon av nedanstående roller eller rollgrupper.</span><span class="sxs-lookup"><span data-stu-id="91df8-115">In order to get access to the content explorer tab, an account must be assigned membership in any one of these roles or role groups.</span></span> 

<span data-ttu-id="91df8-116">**Microsoft 365-rollgrupper**</span><span class="sxs-lookup"><span data-stu-id="91df8-116">**Microsoft 365 role groups**</span></span>

- <span data-ttu-id="91df8-117">Global administratör</span><span class="sxs-lookup"><span data-stu-id="91df8-117">Global administrator</span></span>
- <span data-ttu-id="91df8-118">Efterlevnadsadministratör</span><span class="sxs-lookup"><span data-stu-id="91df8-118">Compliance administrator</span></span>
- <span data-ttu-id="91df8-119">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="91df8-119">Security administrator</span></span>
- <span data-ttu-id="91df8-120">Administratör för efterlevnadsdata</span><span class="sxs-lookup"><span data-stu-id="91df8-120">Compliance data administrator</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91df8-121">Medlemskapet i rollgrupperna tillåter inte att du visar listan med objekt eller innehållet i objekten i innehållsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="91df8-121">Membership in these role groups does not allow you to view the list of items in content explorer or to view the contents of the items in content explorer.</span></span>

### <a name="required-permissions-to-access-items-in-content-explorer"></a><span data-ttu-id="91df8-122">Behörigheter som krävs för åtkomst till objekt i innehållsutforskaren</span><span class="sxs-lookup"><span data-stu-id="91df8-122">Required permissions to access items in content explorer</span></span>

<span data-ttu-id="91df8-123">Åtkomsten till innehållsutforskaren är mycket begränsad eftersom den innebär att du kan läsa innehållet i genomsökta filer.</span><span class="sxs-lookup"><span data-stu-id="91df8-123">Access to content explorer is highly restricted because it lets you read the contents of scanned files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="91df8-124">Dessa behörigheter ersätter behörigheter som har tilldelats lokalt till objekten, vilket innebär att innehållet kan visas.</span><span class="sxs-lookup"><span data-stu-id="91df8-124">These permissions supercede permissions that are locally assigned to the items, which allows viewing of the content.</span></span> 

<span data-ttu-id="91df8-125">Det finns två roller som ger åtkomst till innehållsutforskaren och som tilldelas via [Microsofts säkerhets- och efterlevnadscenter](https://protection.office.com/permissions):</span><span class="sxs-lookup"><span data-stu-id="91df8-125">There are two roles that grant access to content explorer and it is granted using the [Microsoft Security & Compliance Center](https://protection.office.com/permissions):</span></span>

- <span data-ttu-id="91df8-126">**Listvy för innehållsutforskare**: Med ett medlemskap i den här rollgruppen kan du se alla objekt och deras platser i listvyn.</span><span class="sxs-lookup"><span data-stu-id="91df8-126">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location in list view.</span></span> <span data-ttu-id="91df8-127">Rollen `data classification list viewer` har tilldelats till rollgruppen i förväg.</span><span class="sxs-lookup"><span data-stu-id="91df8-127">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="91df8-128">**Innehållshanterare för innehållsutforskaren**: Med ett medlemskap i den här rollgruppen kan du se innehållet för alla objekt i listan.</span><span class="sxs-lookup"><span data-stu-id="91df8-128">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="91df8-129">Rollen `data classification content viewer` har tilldelats till rollgruppen i förväg.</span><span class="sxs-lookup"><span data-stu-id="91df8-129">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="91df8-130">Kontot som du använder för att komma åt innehållsutforskaren måste finnas i ena eller båda rollgrupperna.</span><span class="sxs-lookup"><span data-stu-id="91df8-130">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="91df8-131">Det här är fristående rollgrupper som inte är kumulativa.</span><span class="sxs-lookup"><span data-stu-id="91df8-131">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="91df8-132">Om du till exempel vill ge ett konto möjlighet att enbart se objekten och deras platser, beviljar du behörighet till innehållsutforskarens listvy.</span><span class="sxs-lookup"><span data-stu-id="91df8-132">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="91df8-133">Om du vill att samma konto också ska kunna se innehållet för objekten i listan, beviljar du även behörighet till innehållshanteraren för innehållsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="91df8-133">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="91df8-134">Du kan också tilldela den ena eller båda rollerna till en anpassad rollgrupp för att anpassa åtkomsten till innehållsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="91df8-134">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="91df8-135">En global administratör, efterlevnadsadministratör eller dataadministratör kan tilldela det nödvändiga medlemskapet i rollgruppen till innehållsutforskarens listvy eller innehållshanterare.</span><span class="sxs-lookup"><span data-stu-id="91df8-135">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="91df8-136">Innehållsutforskaren</span><span class="sxs-lookup"><span data-stu-id="91df8-136">Content explorer</span></span>

<span data-ttu-id="91df8-137">I innehållsutforskaren visas en aktuell ögonblicksbild av objekt som har en känslighetsetikett, en kvarhållningsetikett eller som har klassificeras med en typ av känslig information i organisationen.</span><span class="sxs-lookup"><span data-stu-id="91df8-137">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="91df8-138">Typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="91df8-138">Sensitive information types</span></span>

<span data-ttu-id="91df8-139">Med en [DLP-princip](dlp-learn-about-dlp.md) skyddar du känslig information som har definierats med en **typ av känslig information**.</span><span class="sxs-lookup"><span data-stu-id="91df8-139">A [DLP policy](dlp-learn-about-dlp.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="91df8-140">Microsoft 365 innehåller [definitioner av många vanliga typer av känslig information](sensitive-information-type-entity-definitions.md) från olika regioner som du kan använda direkt.</span><span class="sxs-lookup"><span data-stu-id="91df8-140">Microsoft 365 includes [definitions for many common sensitive information types](sensitive-information-type-entity-definitions.md) from across many different regions that are ready for you to use.</span></span> <span data-ttu-id="91df8-141">Det kan exempelvis vara kreditkortsnummer, bankkontonummer, nationella ID-nummer och Windows Live ID-tjänstnummer.</span><span class="sxs-lookup"><span data-stu-id="91df8-141">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

> [!NOTE]
> <span data-ttu-id="91df8-142">Innehållsutforskaren söker för närvarande inte efter typer av känslig information i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="91df8-142">Content explorer doesn't currently scan for sensitive information types in Exchange Online.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="91df8-143">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="91df8-143">Sensitivity labels</span></span>

<span data-ttu-id="91df8-144">En [känslighetsetikett](sensitivity-labels.md) är helt enkelt en tagg som anger värdet för objektet i din organisation.</span><span class="sxs-lookup"><span data-stu-id="91df8-144">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="91df8-145">Den kan tillämpas manuellt eller automatiskt.</span><span class="sxs-lookup"><span data-stu-id="91df8-145">It can be applied manually, or automatically.</span></span> <span data-ttu-id="91df8-146">När den används bäddas den in i dokumentet och medföljer det överallt.</span><span class="sxs-lookup"><span data-stu-id="91df8-146">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="91df8-147">En känslighetsetikett möjliggör olika säkerhetsmetoder, till exempel obligatorisk vattenstämpel eller kryptering.</span><span class="sxs-lookup"><span data-stu-id="91df8-147">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span>

<span data-ttu-id="91df8-148">Känslighetsetiketter måste vara aktiverade för filer som finns i SharePoint och OneDrive för att motsvarande data ska visas på dataklassificeringssidan.</span><span class="sxs-lookup"><span data-stu-id="91df8-148">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="91df8-149">Mer information finns i [Aktivera känslighetsetiketter för Office-filer i SharePoint och OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span><span class="sxs-lookup"><span data-stu-id="91df8-149">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="91df8-150">Kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="91df8-150">Retention labels</span></span>

<span data-ttu-id="91df8-151">Med en [kvarhållningsetikett](retention.md) kan du ange hur länge ett etiketterat objekt ska behållas och vilka steg som ska vidtas innan det tas bort.</span><span class="sxs-lookup"><span data-stu-id="91df8-151">A [retention label](retention.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="91df8-152">De kan tillämpas manuellt eller automatiskt via principer.</span><span class="sxs-lookup"><span data-stu-id="91df8-152">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="91df8-153">De kan användas för att hjälpa din organisation att följa juridiska krav och regelkrav.</span><span class="sxs-lookup"><span data-stu-id="91df8-153">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="91df8-154">Använda innehållsutforskaren</span><span class="sxs-lookup"><span data-stu-id="91df8-154">How to use content explorer</span></span>

1. <span data-ttu-id="91df8-155">Öppna **Microsoft 365 Efterlevnadscenter**  > **Dataklassificering** > **Innehållsutforskaren**.</span><span class="sxs-lookup"><span data-stu-id="91df8-155">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="91df8-156">Om du känner till namnet på etiketten eller typen av känslig information kan du skriva det i filterrutan.</span><span class="sxs-lookup"><span data-stu-id="91df8-156">If you know the name of the label, or the sensitive information type, you can type that into the filter box.</span></span>
3. <span data-ttu-id="91df8-157">Du kan också bläddra efter objektet genom att expandera etikettypen och välja etiketten i listan.</span><span class="sxs-lookup"><span data-stu-id="91df8-157">Alternately, you can browse for the item by expanding the label type and selecting the label from the list.</span></span>
4. <span data-ttu-id="91df8-158">Välj en plats under **Alla platser** och öka detaljnivån i objektets mappstruktur.</span><span class="sxs-lookup"><span data-stu-id="91df8-158">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="91df8-159">Dubbelklicka för att öppna objektet i innehållsutforskaren.</span><span class="sxs-lookup"><span data-stu-id="91df8-159">Double-click to open the item natively in content explorer.</span></span>

### <a name="export"></a><span data-ttu-id="91df8-160">Exportera</span><span class="sxs-lookup"><span data-stu-id="91df8-160">Export</span></span>
<span data-ttu-id="91df8-161">**Exporten** skapar en .csv-fil med en lista över det som visas i fönstret **Alla platser**.</span><span class="sxs-lookup"><span data-stu-id="91df8-161">The **export** control will create a .csv file that contains a listing of whatever is showing in the **All locations** pane.</span></span>

![exportkontroll för dataklassificering](../media/data_classification_export_control.png)


### <a name="search"></a><span data-ttu-id="91df8-163">Söka</span><span class="sxs-lookup"><span data-stu-id="91df8-163">Search</span></span>

<span data-ttu-id="91df8-164">När du ökar detaljnivån för en plats, till exempel en Exchange-mapp eller en SharePoint- eller OneDrive-webbplats, visas **sök**-verktyget.</span><span class="sxs-lookup"><span data-stu-id="91df8-164">When you drill down into a location, such as an Exchange folder, or a SharePoint or OneDrive site, the **search** tool appears.</span></span>

![sökverktyg för innehållsutforskaren](../media/data_classification_search_tool.png)


<span data-ttu-id="91df8-166">Verktygets sökomfång visas i rutan **Alla platser**. Vad du kan söka efter varierar beroende på den valda platsen.</span><span class="sxs-lookup"><span data-stu-id="91df8-166">The scope of the search tool is what is displaying in the **All locations** pane and what you can search on varies depending on the selected location.</span></span> 

<span data-ttu-id="91df8-167">När **Exchange** är den valda platsen kan du söka efter den fullständiga e-postadressen för postlådan, till exempel `user@domainname.com`.</span><span class="sxs-lookup"><span data-stu-id="91df8-167">When **Exchange** is the selected location, you can search on the full email address of the mailbox, for example `user@domainname.com`.</span></span>

<span data-ttu-id="91df8-168">När antingen **SharePoint** eller **OneDrive** har valts som plats, visas sökverktyget när du ökar detaljnivån för webbplatsnamn, mappar och filer.</span><span class="sxs-lookup"><span data-stu-id="91df8-168">When either **SharePoint** or **OneDrive** are selected location, the search tool will appear when you drill down to site names, folders and files.</span></span> 

> [!NOTE]
> <span data-ttu-id="91df8-169">**OneDrive** Vi har lyssnat på den värdefulla feedbacken om OneDrive-integreringen från förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="91df8-169">**OneDrive** We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="91df8-170">Baserat på feedbacken finns OneDrive-funktionerna kvar i förhandsversionen tills alla korrigeringar har gjorts.</span><span class="sxs-lookup"><span data-stu-id="91df8-170">Based on that feedback, the OneDrive functionality will remain in preview till all fixes are in place.</span></span> <span data-ttu-id="91df8-171">Beroende på din klientorganisation kanske vissa kunder inte ser OneDrive som en plats.</span><span class="sxs-lookup"><span data-stu-id="91df8-171">Depending on your tenant, some customers may not see OneDrive as a location.</span></span> <span data-ttu-id="91df8-172">Vi uppskattar ditt fortsatta stöd för detta.</span><span class="sxs-lookup"><span data-stu-id="91df8-172">We appreciate your continued support on this.</span></span>

<span data-ttu-id="91df8-173">Du kan söka på:</span><span class="sxs-lookup"><span data-stu-id="91df8-173">You can search on:</span></span>


|<span data-ttu-id="91df8-174">värde</span><span class="sxs-lookup"><span data-stu-id="91df8-174">value</span></span>|<span data-ttu-id="91df8-175">exempel</span><span class="sxs-lookup"><span data-stu-id="91df8-175">example</span></span>  |
|---------|---------|
|<span data-ttu-id="91df8-176">fullständigt webbplatsnamn</span><span class="sxs-lookup"><span data-stu-id="91df8-176">full site name</span></span>    |`https://contoso.onmicrosoft.com/sites/sitename`    |
|<span data-ttu-id="91df8-177">rotmappens namn – hämtar alla undermappar</span><span class="sxs-lookup"><span data-stu-id="91df8-177">root folder name - gets all subfolders</span></span>    | `/sites`        |
|<span data-ttu-id="91df8-178">filnamn</span><span class="sxs-lookup"><span data-stu-id="91df8-178">file name</span></span>    |    `RES_Resume_1234.txt`     |
|<span data-ttu-id="91df8-179">text i början av filnamnet</span><span class="sxs-lookup"><span data-stu-id="91df8-179">text at the beginning of file name</span></span>| `RES`|
|<span data-ttu-id="91df8-180">text efter ett understreck (_) i filnamnet</span><span class="sxs-lookup"><span data-stu-id="91df8-180">text after an underscore character ( _ ) in file name</span></span>|<span data-ttu-id="91df8-181">`Resume` eller `1234`</span><span class="sxs-lookup"><span data-stu-id="91df8-181">`Resume` or `1234`</span></span>| 
|<span data-ttu-id="91df8-182">filtillägg</span><span class="sxs-lookup"><span data-stu-id="91df8-182">file extension</span></span>|`txt`|


## <a name="see-also"></a><span data-ttu-id="91df8-183">Se även</span><span class="sxs-lookup"><span data-stu-id="91df8-183">See also</span></span>

- [<span data-ttu-id="91df8-184">Mer information om känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="91df8-184">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="91df8-185">Mer information om kvarhållningsprinciper och kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="91df8-185">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="91df8-186">Entitetsdefinitioner för typer av känslig information</span><span class="sxs-lookup"><span data-stu-id="91df8-186">Sensitive information type entity definitions.md</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="91df8-187">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="91df8-187">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)