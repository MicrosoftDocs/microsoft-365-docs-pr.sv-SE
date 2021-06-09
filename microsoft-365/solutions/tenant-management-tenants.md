---
title: Steg 1. Din Microsoft 365 för företagsklienter
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
description: Distribuera och hantera en eller Microsoft 365 klientorganisation, med alternativ för multi-geo- och flyttningsplatser.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406390"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="4689b-104">Steg 1.</span><span class="sxs-lookup"><span data-stu-id="4689b-104">Step 1.</span></span> <span data-ttu-id="4689b-105">Din Microsoft 365 för företagsklienter</span><span class="sxs-lookup"><span data-stu-id="4689b-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="4689b-106">Ett av dina första klientbeslut är hur många du har.</span><span class="sxs-lookup"><span data-stu-id="4689b-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="4689b-107">Varje Microsoft 365 är distinkt, unik och skiljer sig från alla Microsoft 365 klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="4689b-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="4689b-108">Den motsvarande Azure AD-klientorganisationen är också distinkt, unik och separat från alla Microsoft 365 klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4689b-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="4689b-109">Enskild klient</span><span class="sxs-lookup"><span data-stu-id="4689b-109">Single tenant</span></span>
<span data-ttu-id="4689b-110">Om du har en enda klientorganisation förenklas många aspekter av organisationens användning av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4689b-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="4689b-111">En enskild klient innebär en enda Azure AD-klientorganisation med en enda uppsättning konton, grupper och principer.</span><span class="sxs-lookup"><span data-stu-id="4689b-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="4689b-112">Behörigheter och delning av resurser i organisationen kan göras via den här centrala identitetsleverantören.</span><span class="sxs-lookup"><span data-stu-id="4689b-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="4689b-113">En enskild klientorganisation erbjuder de mest funktionsrika och förenklade samarbets- och produktivitetsupplevelsen för användarna.</span><span class="sxs-lookup"><span data-stu-id="4689b-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="4689b-114">Här är ett exempel som visar standardplatsen och Azure AD-klientorganisationen för Microsoft 365 klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4689b-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![En enskild Microsoft 365 med sin Azure AD-klientorganisation](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="4689b-116">Flera klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="4689b-116">Multiple tenants</span></span>

<span data-ttu-id="4689b-117">Det finns många anledningar till att organisationen kan ha flera klientorganisationar:</span><span class="sxs-lookup"><span data-stu-id="4689b-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="4689b-118">Administrativ avgränsning</span><span class="sxs-lookup"><span data-stu-id="4689b-118">Administrative isolation</span></span>
- <span data-ttu-id="4689b-119">Decentraliserad IT</span><span class="sxs-lookup"><span data-stu-id="4689b-119">Decentralized IT</span></span>
- <span data-ttu-id="4689b-120">Historiska beslut</span><span class="sxs-lookup"><span data-stu-id="4689b-120">Historical decisions</span></span>
- <span data-ttu-id="4689b-121">Sammanslagningar, förvärv eller företag</span><span class="sxs-lookup"><span data-stu-id="4689b-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="4689b-122">En tydlig åtskillnad mellan företags profilering för storkongruens</span><span class="sxs-lookup"><span data-stu-id="4689b-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="4689b-123">Klientorganisationen före produktion, test eller sandbox-miljö</span><span class="sxs-lookup"><span data-stu-id="4689b-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="4689b-124">Här är ett exempel på en organisation som har två klientorganisationar (klientorganisation A och klientorganisation B) i samma standarddatacenter geo.</span><span class="sxs-lookup"><span data-stu-id="4689b-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="4689b-125">Varje klientorganisation som en separat Azure AD-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4689b-125">Each tenant as a separate Azure AD tenant.</span></span>

![Flera Microsoft 365 med sina egna Azure AD-klientorganisationen](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="4689b-127">När du har flera klientorganisationen finns det restriktioner och ytterligare överväganden när du hanterar dem och tillhandahåller tjänster till användarna.</span><span class="sxs-lookup"><span data-stu-id="4689b-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="4689b-128">Samarbete mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="4689b-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="4689b-129">Om du vill att användarna ska samarbeta mer effektivt i olika Microsoft 365-klientorganisationar på ett säkert sätt, kan du använda en central plats för filer och konversationer, dela kalendrar, använda snabbmeddelanden, ljud-/videosamtal för kommunikation och skydda åtkomst till resurser och program.</span><span class="sxs-lookup"><span data-stu-id="4689b-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="4689b-130">Mer information finns i Microsoft 365 [samarbete mellan klientorganisationen.](../enterprise/microsoft-365-inter-tenant-collaboration.md)</span><span class="sxs-lookup"><span data-stu-id="4689b-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="4689b-131">Postlådemigrering mellan klientorganisationen (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="4689b-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="4689b-132">Innan postlådemigrering mellan klientorganisationen (i förhandsversion) måste du ta bort en användarpostlåda helt från den aktuella klientorganisationen (källklientorganisationen) till den lokala och sedan registrera dem i en ny klientorganisation (målklientorganisationen) när du flyttar Exchange Online postlådor mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="4689b-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="4689b-133">Med den nya funktionen för postlådemigrering mellan klientorganisationen kan innehavaradministratörer i både käll- och målklientorganisationen flytta postlådor mellan klientorganisationen med minimala infrastrukturberoenden i sina lokala system.</span><span class="sxs-lookup"><span data-stu-id="4689b-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="4689b-134">Det här tar bort behovet av postlådor för off-board och onboard.</span><span class="sxs-lookup"><span data-stu-id="4689b-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="4689b-135">Här är två exempel på klientorganisationar och deras postlådor före postlådemigrering mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="4689b-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Flera Microsoft 365 och deras postlådor](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="4689b-137">I den här bilden har två separata klienter sina egna domäner och en uppsättning Exchange postlådor.</span><span class="sxs-lookup"><span data-stu-id="4689b-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="4689b-138">Här är målklientorganisationen (klientorganisation A) efter postlådemigrering mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="4689b-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![Målklientorganisationen efter postlådemigrering mellan klientorganisationen](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="4689b-140">I den här illustrationen har en enda innehavare både domäner och båda uppsättningarna Exchange postlådor.</span><span class="sxs-lookup"><span data-stu-id="4689b-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="4689b-141">Mer information finns i Migrering av [postlådor i flera klientorganisationen.](../enterprise/cross-tenant-mailbox-migration.md)</span><span class="sxs-lookup"><span data-stu-id="4689b-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="4689b-142">Migrering mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="4689b-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="4689b-143">Det finns flera arkitekturscenarier för samgåenden, förvärv, företag och andra scenarier som kan leda till att du migrerar en befintlig Microsoft 365-klientorganisation till en ny klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4689b-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="4689b-144">Detaljerade instruktioner finns i [Microsoft 365 migreringar från klientorganisation till klientorganisation.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)</span><span class="sxs-lookup"><span data-stu-id="4689b-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="4689b-145">Multi-Geo för en klientorganisation</span><span class="sxs-lookup"><span data-stu-id="4689b-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="4689b-146">Med Microsoft 365 Multi-Geo kan du tillhandahålla och lagra data i vila på andra datacenters geoplatser som du har valt att uppfylla datalagringskraven och samtidigt låsa upp din globala distribution av moderna produktivitetsupplevelser till dina medarbetare.</span><span class="sxs-lookup"><span data-stu-id="4689b-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="4689b-147">I en Multi-Geo-miljö består Microsoft 365-klientorganisationen av en standardplats eller central plats där Microsoft 365-prenumerationen ursprungligen skapades och en eller flera satellitplatser.</span><span class="sxs-lookup"><span data-stu-id="4689b-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="4689b-148">I en flera geoklientorganisation hanteras information om geografiska platser, grupper och användarinformation i en global Azure AD-klient.</span><span class="sxs-lookup"><span data-stu-id="4689b-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="4689b-149">Eftersom din klientorganisationsinformation är centraliserad och synkroniserad till varje geoplats delas samarbetsupplevelser för alla från ditt företag över platserna.</span><span class="sxs-lookup"><span data-stu-id="4689b-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="4689b-150">Här är ett exempel på en organisation som har sin standardplats i Europa och en satellitplats i Nordamerika.</span><span class="sxs-lookup"><span data-stu-id="4689b-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="4689b-151">Båda platserna har samma globala Azure AD-klientorganisation för den Microsoft 365 klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="4689b-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Exempel på en multi-geo Microsoft 365 klientorganisation](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="4689b-153">Mer information finns i [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="4689b-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="4689b-154">Flytta basdata till ett nytt datacenter geo</span><span class="sxs-lookup"><span data-stu-id="4689b-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="4689b-155">Microsoft fortsätter att öppna nya datacenter geos för Microsoft 365 tjänster.</span><span class="sxs-lookup"><span data-stu-id="4689b-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="4689b-156">Dessa nya datacenter geos lägger till kapacitet och beräknar resurser för att stödja vår pågående kundbehov och användningstillväxt.</span><span class="sxs-lookup"><span data-stu-id="4689b-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="4689b-157">Det nya datacentret geos erbjuder dessutom geodata som används för basdata.</span><span class="sxs-lookup"><span data-stu-id="4689b-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="4689b-158">Även om en geoinvigering av ett nytt datacenter inte påverkar dig och dina basdata som lagras i ett befintligt datacenter geo kan du med Microsoft begära en tidig migrering av organisationens basdata för kunder i vila till ett nytt datacenter geo.</span><span class="sxs-lookup"><span data-stu-id="4689b-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="4689b-159">Här är ett exempel där en Microsoft 365-klientorganisation har flyttats från EU-datacentret geo till det som finns i Storbritannien.</span><span class="sxs-lookup"><span data-stu-id="4689b-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Exempel på flytt av Microsoft 365 klientorganisation mellan geodatadata](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="4689b-161">Mer information finns i Flytta [basdata till det nya Microsoft 365 datacentrets geos.](../enterprise/moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="4689b-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="4689b-162">Produkter och licenser för en klientorganisation</span><span class="sxs-lookup"><span data-stu-id="4689b-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="4689b-163">Din Microsoft 365 skapas när du köper din första produkt, till exempel Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="4689b-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="4689b-164">Tillsammans med produkten ingår licenser som debiteras en månatlig eller årlig avgift.</span><span class="sxs-lookup"><span data-stu-id="4689b-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="4689b-165">En administratör tilldelar sedan en tillgänglig licens från en av dina produkter till ett användarkonto, antingen direkt eller via gruppmedlemskap.</span><span class="sxs-lookup"><span data-stu-id="4689b-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="4689b-166">Beroende på organisationens affärsbehov kan du ha en uppsättning produkter, som var och en har sin egen licenspool.</span><span class="sxs-lookup"><span data-stu-id="4689b-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="4689b-167">För att fastställa produktuppsättningen och antalet licenser för var och en krävs en del planering för att:</span><span class="sxs-lookup"><span data-stu-id="4689b-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="4689b-168">Se till att du har tillräckligt med licenser för användarkonton som behöver avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="4689b-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="4689b-169">Förhindra att licenser tar slut eller att du har för många licenser som inte tilldelats, baserat på ändringar av personalen i din organisation.</span><span class="sxs-lookup"><span data-stu-id="4689b-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="4689b-170">Resultat i steg 1</span><span class="sxs-lookup"><span data-stu-id="4689b-170">Results of Step 1</span></span>

<span data-ttu-id="4689b-171">För din Microsoft 365 för företagsklienter har du beslutat följande:</span><span class="sxs-lookup"><span data-stu-id="4689b-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="4689b-172">Hur många klientorganisationar du har eller behöver.</span><span class="sxs-lookup"><span data-stu-id="4689b-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="4689b-173">Vilka produkter och licenser som måste köpas för varje klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4689b-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="4689b-174">Om en klientorganisation måste vara en multi-geoklient för att uppfylla datalagringskraven.</span><span class="sxs-lookup"><span data-stu-id="4689b-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="4689b-175">Om du behöver konfigurera samarbete mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="4689b-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="4689b-176">Om du behöver migrera en klientorganisation till en annan.</span><span class="sxs-lookup"><span data-stu-id="4689b-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="4689b-177">Om du behöver flytta basdata från ett geodatadatacenter till ett nytt.</span><span class="sxs-lookup"><span data-stu-id="4689b-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="4689b-178">Här är ett exempel på en ny klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4689b-178">Here is an example of a new tenant.</span></span>

![Exempel på en ny klientorganisation](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="4689b-180">I den här illustrationen har klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="4689b-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="4689b-181">En standardplats som motsvarar en geoplats Microsoft 365 datacentret.</span><span class="sxs-lookup"><span data-stu-id="4689b-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="4689b-182">En uppsättning produkter och licenser.</span><span class="sxs-lookup"><span data-stu-id="4689b-182">A set of products and licenses.</span></span>
- <span data-ttu-id="4689b-183">Uppsättningen molnproduktivitetsprogram, av vilka vissa är specifika för produkter.</span><span class="sxs-lookup"><span data-stu-id="4689b-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="4689b-184">En Azure AD-klient som innehåller globala administratörskonton och ett initialt DNS-domännamn.</span><span class="sxs-lookup"><span data-stu-id="4689b-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="4689b-185">När vi går igenom de ytterligare stegen i den här lösningen kommer vi att bygga ut den här siffran.</span><span class="sxs-lookup"><span data-stu-id="4689b-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="4689b-186">Löpande underhåll för klientorganisation</span><span class="sxs-lookup"><span data-stu-id="4689b-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="4689b-187">Du kan behöva:</span><span class="sxs-lookup"><span data-stu-id="4689b-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="4689b-188">Lägg till en ny klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="4689b-188">Add a new tenant.</span></span>
- <span data-ttu-id="4689b-189">Lägg till nya produkter i en klientorganisation med ett första antal licenser.</span><span class="sxs-lookup"><span data-stu-id="4689b-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="4689b-190">Ändra licensuppsättningen för en produkt i en klientorganisation för att justera för att ändra personalkrav.</span><span class="sxs-lookup"><span data-stu-id="4689b-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="4689b-191">Flytta dina kärndata från en klientorganisation till en ny geoplats i datacentret.</span><span class="sxs-lookup"><span data-stu-id="4689b-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="4689b-192">Lägg till Krav för Multi-Geo för datalagring.</span><span class="sxs-lookup"><span data-stu-id="4689b-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="4689b-193">Konfigurera samarbete mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="4689b-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="4689b-194">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="4689b-194">Next step</span></span>

<span data-ttu-id="4689b-195">[![Steg 2. Optimera klientorganisationen för nätverk för åtkomst](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="4689b-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="4689b-196">Fortsätt med [nätverk för](tenant-management-networking.md) att tillhandahålla optimala nätverk från dina medarbetare till Microsoft 365 molntjänster.</span><span class="sxs-lookup"><span data-stu-id="4689b-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
