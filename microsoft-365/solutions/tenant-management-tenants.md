---
title: Steg 1. Dina klientorganisationar i Microsoft 365 för företag
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Distribuera och hantera en eller flera Microsoft 365-klientorganisationar, med alternativ för multigeobaserade och rörliga platser.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406390"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="f860e-104">Steg 1.</span><span class="sxs-lookup"><span data-stu-id="f860e-104">Step 1.</span></span> <span data-ttu-id="f860e-105">Dina klientorganisationar i Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="f860e-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="f860e-106">Ett av dina första klientbeslut är hur många som ska ha.</span><span class="sxs-lookup"><span data-stu-id="f860e-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="f860e-107">Varje Microsoft 365-innehavare är distinkt, unik och separat från alla andra Microsoft 365-klientorganisationar.</span><span class="sxs-lookup"><span data-stu-id="f860e-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="f860e-108">Det är motsvarande Azure AD-klientorganisation som också är distinkt, unik och separat från alla andra Microsoft 365-klientorganisationar.</span><span class="sxs-lookup"><span data-stu-id="f860e-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="f860e-109">Enskild klient</span><span class="sxs-lookup"><span data-stu-id="f860e-109">Single tenant</span></span>
<span data-ttu-id="f860e-110">Om du har en enda klientorganisation förenklas många aspekter av organisationens användning av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f860e-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="f860e-111">En enda klient innebär en enda Azure AD-klientorganisation med en enda uppsättning konton, grupper och principer.</span><span class="sxs-lookup"><span data-stu-id="f860e-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="f860e-112">Behörigheter och delning av resurser i organisationen kan göras via den centrala identitetsleverantören.</span><span class="sxs-lookup"><span data-stu-id="f860e-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="f860e-113">En enda klientorganisation erbjuder mest funktionsrika och förenklade samarbets- och produktivitetsupplevelser för användarna.</span><span class="sxs-lookup"><span data-stu-id="f860e-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="f860e-114">Här är ett exempel som visar standardplatsen och Azure AD-klientorganisationen för en Microsoft 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="f860e-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![En enskild Microsoft 365-klientorganisation med Azure AD-klientorganisationen](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="f860e-116">Flera klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="f860e-116">Multiple tenants</span></span>

<span data-ttu-id="f860e-117">Det finns många anledningar till varför organisationen kan ha flera klientorganisationar:</span><span class="sxs-lookup"><span data-stu-id="f860e-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="f860e-118">Administrativ avgränsning</span><span class="sxs-lookup"><span data-stu-id="f860e-118">Administrative isolation</span></span>
- <span data-ttu-id="f860e-119">Decentraliserad IT</span><span class="sxs-lookup"><span data-stu-id="f860e-119">Decentralized IT</span></span>
- <span data-ttu-id="f860e-120">Historiska beslut</span><span class="sxs-lookup"><span data-stu-id="f860e-120">Historical decisions</span></span>
- <span data-ttu-id="f860e-121">Sammanslagningar, förvärv eller divestitures</span><span class="sxs-lookup"><span data-stu-id="f860e-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="f860e-122">Tydlig avgränsning av varumärken för organisationer med grattis till ett företag</span><span class="sxs-lookup"><span data-stu-id="f860e-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="f860e-123">Klientorganisation för förhands produktions-, test- eller sandbox-miljö</span><span class="sxs-lookup"><span data-stu-id="f860e-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="f860e-124">Här är ett exempel på en organisation som har två klientorganisationar (klientorganisation A och klientorganisation B) i samma standarddatacenter.</span><span class="sxs-lookup"><span data-stu-id="f860e-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="f860e-125">Varje klientorganisation som en separat Azure AD-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="f860e-125">Each tenant as a separate Azure AD tenant.</span></span>

![Flera Microsoft 365-klientorganisationar med sina egna Azure AD-klientorganisationar](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="f860e-127">När du har flera klientorganisationar finns det begränsningar och ytterligare överväganden när du hanterar dem och tillhandahåller tjänster till användarna.</span><span class="sxs-lookup"><span data-stu-id="f860e-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="f860e-128">Samarbete mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="f860e-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="f860e-129">Om du vill att användarna ska samarbeta mer effektivt i olika Microsoft 365-klientprogram på ett säkert sätt kan du använda samarbetsalternativen mellan klientorganisationen genom att använda en central plats för filer och konversationer, dela kalendrar, använda snabbmeddelanden, ljud-/videosamtal för kommunikation och säkerställa åtkomst till resurser och program.</span><span class="sxs-lookup"><span data-stu-id="f860e-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="f860e-130">Mer information finns i Samarbete mellan klientorganisationen i [Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)</span><span class="sxs-lookup"><span data-stu-id="f860e-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="f860e-131">Migrering av postlådor mellan klientorganisationen (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="f860e-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="f860e-132">Innan du migrerar flera klientlådor (i förhandsversionen) måste du när du flyttar Exchange Online-postlådor mellan klientorganisationen helt ta bort en användarpostlåda från den aktuella klientorganisationen (källklientorganisationen) till den lokala och sedan registrera dem för en ny klientorganisation (målklientorganisationen).</span><span class="sxs-lookup"><span data-stu-id="f860e-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="f860e-133">Med den nya funktionen för postlådemigrering mellan klientorganisationen kan innehavaradministratörer i både käll- och målklientorganisationen flytta postlådor mellan klientorganisationen med minimalt beroende av infrastrukturen i sina lokala system.</span><span class="sxs-lookup"><span data-stu-id="f860e-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="f860e-134">Det här tar bort behovet av postlådor för off-board och onboard.</span><span class="sxs-lookup"><span data-stu-id="f860e-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="f860e-135">Här är två exempel på klientorganisationsklienter och deras postlådor före postlådemigrering mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="f860e-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Flera Microsoft 365-klientorganisationar och deras postlådor](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="f860e-137">I den här bilden har två separata klientorganisationsdomäner och en uppsättning Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="f860e-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="f860e-138">Här är målklientorganisationen (klientorganisation A) efter postlådemigrering mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="f860e-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![Målklientorganisationen efter postlådemigrering mellan klientorganisationen](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="f860e-140">I den här bilden har en enda klientorganisation både domäner och båda uppsättningar av Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="f860e-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="f860e-141">Mer information finns i migrering av [postlådor mellan klientorganisationen.](../enterprise/cross-tenant-mailbox-migration.md)</span><span class="sxs-lookup"><span data-stu-id="f860e-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="f860e-142">Migrering mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="f860e-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="f860e-143">Det finns flera arkitekturer för sammanslagningar, förvärv, divestitures och andra scenarier som kan leda till att du migrerar en befintlig Microsoft 365-klientorganisation till en ny klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="f860e-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="f860e-144">Detaljerad information finns i [Microsoft 365-migreringar från klientorganisation till klientorganisation.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)</span><span class="sxs-lookup"><span data-stu-id="f860e-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="f860e-145">Multi-Geo för en klientorganisation</span><span class="sxs-lookup"><span data-stu-id="f860e-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="f860e-146">Med Microsoft 365 Multi-Geo kan du tillhandahålla och lagra data i vila på andra datacenters geoplatser som du har valt att uppfylla datalagringskraven och samtidigt låsa upp din globala distribution av moderna produktivitetsupplevelser till dina medarbetare.</span><span class="sxs-lookup"><span data-stu-id="f860e-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="f860e-147">I en Multi-Geo-miljö består Microsoft 365-innehavaren av en standard- eller central plats där Microsoft 365-prenumerationen ursprungligen skapades och en eller flera satellitplatser.</span><span class="sxs-lookup"><span data-stu-id="f860e-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="f860e-148">I en flera geoklientorganisation hanteras information om geoplatser, grupper och användarinformation i en global Azure AD-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="f860e-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="f860e-149">Eftersom information om klientorganisationen är centraliserad och synkroniserad till varje geoplats delas samarbetsupplevelser för alla från ditt företag mellan platserna.</span><span class="sxs-lookup"><span data-stu-id="f860e-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="f860e-150">Här är ett exempel på en organisation som har sin standardplats i Europa och en satellitplats i Nordamerika.</span><span class="sxs-lookup"><span data-stu-id="f860e-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="f860e-151">Båda platserna har samma globala Azure AD-klientorganisation för den enda Microsoft 365-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="f860e-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Exempel på en Microsoft 365-klientorganisation med flera geoklienter](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="f860e-153">Mer information finns i [Microsoft 365 Multi-Geo.](../enterprise/microsoft-365-multi-geo.md)</span><span class="sxs-lookup"><span data-stu-id="f860e-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="f860e-154">Flytta basdata till ett nytt datacenter geo</span><span class="sxs-lookup"><span data-stu-id="f860e-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="f860e-155">Microsoft fortsätter att öppna nya datacenter geos för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="f860e-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="f860e-156">Dessa nya datacenter geos lägger till kapacitet och beräknar resurser för att stödja vår pågående kundbehov och användnings tillväxt.</span><span class="sxs-lookup"><span data-stu-id="f860e-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="f860e-157">Det nya datacentrets geodata erbjuder dessutom geodata som lagras för basdata från kunder.</span><span class="sxs-lookup"><span data-stu-id="f860e-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="f860e-158">Även om geoinvigning av ett nytt datacenter inte påverkar dig och dina basdata som lagras i ett befintligt datacenter geo gör Microsoft att du kan begära en tidig migrering av organisationens baskunddata i vila till ett nytt datacenter geo.</span><span class="sxs-lookup"><span data-stu-id="f860e-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="f860e-159">Här är ett exempel där en Microsoft 365-klientorganisation har flyttats från eu:s datacenter (EU) geo till det som finns i Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="f860e-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Exempel på flytt av Microsoft 365-klientorganisation mellan geodatadata](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="f860e-161">Mer information finns i Flytta [basdata till nya geodata i Microsoft 365-datacentret.](../enterprise/moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="f860e-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="f860e-162">Produkter och licenser för en klientorganisation</span><span class="sxs-lookup"><span data-stu-id="f860e-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="f860e-163">Din Microsoft 365-klientorganisation skapas när du köper din första produkt, till exempel Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="f860e-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="f860e-164">Tillsammans med produkten ingår licenser som debiteras en månatlig avgift eller årsavgift.</span><span class="sxs-lookup"><span data-stu-id="f860e-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="f860e-165">En administratör tilldelar sedan en tillgänglig licens från en av dina produkter till ett användarkonto, antingen direkt eller via gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="f860e-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="f860e-166">Beroende på organisationens affärsbehov kanske du har en uppsättning produkter, som var och en har en egen licenspool.</span><span class="sxs-lookup"><span data-stu-id="f860e-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="f860e-167">För att fastställa produktuppsättningen och antalet licenser för var och en krävs en del planering för att:</span><span class="sxs-lookup"><span data-stu-id="f860e-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="f860e-168">Se till att du har tillräckligt med licenser för användarkonton som behöver avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="f860e-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="f860e-169">Förhindra att licenser tar slut eller att du har för många licenser som inte tilldelats, baserat på ändringar av personalen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="f860e-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="f860e-170">Resultat i steg 1</span><span class="sxs-lookup"><span data-stu-id="f860e-170">Results of Step 1</span></span>

<span data-ttu-id="f860e-171">För dina Klientorganisationar i Microsoft 365 för företag har du fastställt:</span><span class="sxs-lookup"><span data-stu-id="f860e-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="f860e-172">Hur många klientorganisationar du har eller behöver.</span><span class="sxs-lookup"><span data-stu-id="f860e-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="f860e-173">Vilka produkter och licenser som måste köpas för varje klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="f860e-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="f860e-174">Om en klientorganisation måste vara multi-geo för att uppfylla kraven för datalagring.</span><span class="sxs-lookup"><span data-stu-id="f860e-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="f860e-175">Om du behöver konfigurera samarbete mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="f860e-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="f860e-176">Om du behöver migrera en klientorganisation till en annan.</span><span class="sxs-lookup"><span data-stu-id="f860e-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="f860e-177">Oavsett om du behöver flytta basdata från ett datacenter geo till ett nytt.</span><span class="sxs-lookup"><span data-stu-id="f860e-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="f860e-178">Här är ett exempel på en ny klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="f860e-178">Here is an example of a new tenant.</span></span>

![Exempel på en ny klientorganisation](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="f860e-180">I den här bilden har klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="f860e-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="f860e-181">En standardplats som motsvarar ett geodatacenter i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f860e-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="f860e-182">En uppsättning produkter och licenser.</span><span class="sxs-lookup"><span data-stu-id="f860e-182">A set of products and licenses.</span></span>
- <span data-ttu-id="f860e-183">Uppsättningen appar för molntjänster, varav en del är specifika för produkter.</span><span class="sxs-lookup"><span data-stu-id="f860e-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="f860e-184">En Azure AD-klient som innehåller globala administratörskonton och ett initialt DNS-domännamn.</span><span class="sxs-lookup"><span data-stu-id="f860e-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="f860e-185">När vi går igenom de ytterligare stegen i den här lösningen kommer vi att bygga ut den här siffran.</span><span class="sxs-lookup"><span data-stu-id="f860e-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="f860e-186">Löpande underhåll för klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="f860e-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="f860e-187">Du kan kontinuerligt behöva:</span><span class="sxs-lookup"><span data-stu-id="f860e-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="f860e-188">Lägg till en ny klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="f860e-188">Add a new tenant.</span></span>
- <span data-ttu-id="f860e-189">Lägg till nya produkter i en klientorganisation med ett första antal licenser.</span><span class="sxs-lookup"><span data-stu-id="f860e-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="f860e-190">Ändra licensuppsättningen för en produkt i en klientorganisation för att justera för att ändra personalkrav.</span><span class="sxs-lookup"><span data-stu-id="f860e-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="f860e-191">Flytta dina kärndata från en klientorganisation till en ny geoplats i datacentret.</span><span class="sxs-lookup"><span data-stu-id="f860e-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="f860e-192">Lägg till Krav för Multi-Geo för datalagring.</span><span class="sxs-lookup"><span data-stu-id="f860e-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="f860e-193">Konfigurera samarbete mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="f860e-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="f860e-194">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f860e-194">Next step</span></span>

<span data-ttu-id="f860e-195">[![Steg 2. Optimera klientorganisationen för nätverk för åtkomst](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="f860e-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="f860e-196">Fortsätt med [nätverk](tenant-management-networking.md) för att tillhandahålla optimala nätverk från dina medarbetare till Microsoft 365-molntjänster.</span><span class="sxs-lookup"><span data-stu-id="f860e-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
