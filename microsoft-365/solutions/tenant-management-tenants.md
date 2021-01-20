---
title: Steg 1. Din Microsoft 365 för företags innehavare
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
ms.custom:
- Ent_Solutions
description: Distribuera och hantera en eller flera Microsoft 365-klient organisationer med alternativ för multi-Geo och flytt av platser.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908721"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="39724-104">Steg 1.</span><span class="sxs-lookup"><span data-stu-id="39724-104">Step 1.</span></span> <span data-ttu-id="39724-105">Din Microsoft 365 för företags innehavare</span><span class="sxs-lookup"><span data-stu-id="39724-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="39724-106">Ett av dina första besluts fattare är hur många som ska vara med.</span><span class="sxs-lookup"><span data-stu-id="39724-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="39724-107">Varje Microsoft 365-klient organisation är distinkt, unikt och åtskilt från alla andra Microsoft 365-klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="39724-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="39724-108">Det motsvarande Azure AD-klient organisationen är också distinkt, unikt och åtskilt från alla andra Microsoft 365-klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="39724-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="39724-109">En enda klient organisation</span><span class="sxs-lookup"><span data-stu-id="39724-109">Single tenant</span></span>
<span data-ttu-id="39724-110">Om du har en enda klient organisation blir det enklare för många olika sätt att använda Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39724-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="39724-111">En enskild klient organisation betyder en enda Azure AD-klient organisation med en enda uppsättning konton, grupper och principer.</span><span class="sxs-lookup"><span data-stu-id="39724-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="39724-112">Behörigheter och delning av resurser i organisationen kan göras via den här centrala identitets leverantören.</span><span class="sxs-lookup"><span data-stu-id="39724-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="39724-113">En enda klient organisation tillhandahåller den mest omfattande och förenklade samarbets-och produktivitets upplevelsen för dina användare.</span><span class="sxs-lookup"><span data-stu-id="39724-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="39724-114">Här är ett exempel som visar standard platsen och Azure AD-klient organisationen för en Microsoft 365-klient organisation.</span><span class="sxs-lookup"><span data-stu-id="39724-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![En enda Microsoft 365-klient organisation med sin Azure AD-klient organisation](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="39724-116">Flera klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="39724-116">Multiple tenants</span></span>

<span data-ttu-id="39724-117">Det finns många anledningar till att organisationen kan ha flera klient organisationer:</span><span class="sxs-lookup"><span data-stu-id="39724-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="39724-118">Administratörs isolering</span><span class="sxs-lookup"><span data-stu-id="39724-118">Administrative isolation</span></span>
- <span data-ttu-id="39724-119">Decentralisera det</span><span class="sxs-lookup"><span data-stu-id="39724-119">Decentralized IT</span></span>
- <span data-ttu-id="39724-120">Historiska beslut</span><span class="sxs-lookup"><span data-stu-id="39724-120">Historical decisions</span></span>
- <span data-ttu-id="39724-121">Fusioner, förvärv eller divestitures</span><span class="sxs-lookup"><span data-stu-id="39724-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="39724-122">Tydligt separering av varumärkes märkning för konglomerat organisationer</span><span class="sxs-lookup"><span data-stu-id="39724-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="39724-123">För produktions-, test-eller sand lådor</span><span class="sxs-lookup"><span data-stu-id="39724-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="39724-124">Här är ett exempel på en organisation med två klient organisationer (klient organisation A och Tenant B) i samma standard Data Center.</span><span class="sxs-lookup"><span data-stu-id="39724-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="39724-125">Varje klient organisation som en separat Azure AD-klient.</span><span class="sxs-lookup"><span data-stu-id="39724-125">Each tenant as a separate Azure AD tenant.</span></span>

![Flera Microsoft 365-klient organisationer med deras egna Azure AD-klient organisationer](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="39724-127">När du har flera klient organisationer finns det restriktioner och andra överväganden när du hanterar dem och tillhandahåller tjänster till användarna.</span><span class="sxs-lookup"><span data-stu-id="39724-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="39724-128">Samarbete mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="39724-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="39724-129">Om du vill att användarna ska samar beta mer effektivt över olika Microsoft 365-klient organisationer på ett säkert sätt kan du använda en central plats för filer och konversationer, dela kalendrar med snabb meddelanden, ljud/video samtal och skydda åtkomsten till resurser och program.</span><span class="sxs-lookup"><span data-stu-id="39724-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="39724-130">Mer information finns i [Microsoft 365 samarbete mellan innehavare](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="39724-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="39724-131">Migrera mellan innehavare (för hands version)</span><span class="sxs-lookup"><span data-stu-id="39724-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="39724-132">Innan migrering av post låda från flera innehavare (i för hands version), när Exchange Online-postlådor flyttas mellan klient organisationer måste du helt ta bort en användar post låda från den aktuella klient organisationen (käll klient organisationen) till lokalt och sedan till en ny klient organisation (mål klient organisationen).</span><span class="sxs-lookup"><span data-stu-id="39724-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="39724-133">Med den nya Överflyttnings funktionen för post lådor för flera innehavare kan klient organisationer i både käll-och mål klient organisationer flytta post lådor mellan klient organisationerna och deras lokala system.</span><span class="sxs-lookup"><span data-stu-id="39724-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="39724-134">Detta tar bort behovet av andra och andra-postlådor.</span><span class="sxs-lookup"><span data-stu-id="39724-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="39724-135">Här är två exempel klient organisationer och deras post lådor innan migrering mellan innehavare av post lådor.</span><span class="sxs-lookup"><span data-stu-id="39724-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Flera Microsoft 365-klient organisationer och deras post lådor](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="39724-137">I den här bilden har två separata klient organisationer sina egna domäner och en uppsättning Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="39724-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="39724-138">Här är mål klient organisationen (klient organisation A) efter migrering av post låda mellan innehavare.</span><span class="sxs-lookup"><span data-stu-id="39724-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![Mål klient organisationen efter migrering av post låda mellan innehavare](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="39724-140">I den här bilden har en enskild klient organisation både domäner och båda uppsättningarna med Exchange-postlådor.</span><span class="sxs-lookup"><span data-stu-id="39724-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="39724-141">Mer information finns i [migrering av post lådor mellan innehavare](../enterprise/cross-tenant-mailbox-migration.md).</span><span class="sxs-lookup"><span data-stu-id="39724-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="39724-142">Migrering mellan klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="39724-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="39724-143">Det finns flera arkitektur metoder för fusioner, förvärv, divestitures och andra scenarier som kan leda till att du migrerar en befintlig Microsoft 365-klient organisation till en ny klient organisation.</span><span class="sxs-lookup"><span data-stu-id="39724-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="39724-144">Detaljerad information finns i [Microsoft 365-migreringar för klient organisationer](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span><span class="sxs-lookup"><span data-stu-id="39724-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="39724-145">Multi-geo för en innehavare</span><span class="sxs-lookup"><span data-stu-id="39724-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="39724-146">Med Microsoft 365 multi-geo kan du tillhandahålla och lagra data på andra platser i Data Center som du har valt att uppfylla data de kraven och samtidigt låsa upp din globala installation av moderna produktivitets upplevelser till dina anställda.</span><span class="sxs-lookup"><span data-stu-id="39724-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="39724-147">I en multi-geo-miljö består din Microsoft 365-klient av en standard-eller central plats där ditt Microsoft 365-abonnemang ursprungligen skapades och en eller flera satellit platser.</span><span class="sxs-lookup"><span data-stu-id="39724-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="39724-148">I en multi-geo-klient organisation ska informationen om geo-platser, grupper och användar information hanteras i en global Azure AD-klient.</span><span class="sxs-lookup"><span data-stu-id="39724-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="39724-149">Eftersom klient informationen hanteras centralt och synkroniseras på varje Geo-plats delas samarbets upplevelser med alla från ditt företag på alla platser.</span><span class="sxs-lookup"><span data-stu-id="39724-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="39724-150">Här är ett exempel på en organisation med standard platsen i Europa och en satellit plats i Nord Amerika.</span><span class="sxs-lookup"><span data-stu-id="39724-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="39724-151">Båda platserna delar samma globala Azure AD-klient organisation för den enda Microsoft 365-klienten.</span><span class="sxs-lookup"><span data-stu-id="39724-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Exempel på en multigeo Microsoft 365-klient organisation](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="39724-153">Mer information finns i [Microsoft 365 multi-geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="39724-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="39724-154">Flytta grundläggande data till ett nytt Data Center geo</span><span class="sxs-lookup"><span data-stu-id="39724-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="39724-155">Microsoft fortsätter att öppna nya data Center-geos för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="39724-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="39724-156">De här nya datacenter-geos lägga till kapacitet och beräkna resurser för att stödja vår pågående kund efter frågan och förbruknings tillväxt.</span><span class="sxs-lookup"><span data-stu-id="39724-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="39724-157">Dessutom ger det nya data Center geos in-Geo data de för grundläggande kunddata.</span><span class="sxs-lookup"><span data-stu-id="39724-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="39724-158">Trots att en ny datacenter-geo inte påverkar dig och dina grundläggande data som lagras i ett befintligt Data Center, kan du använda Microsoft för att begära en tidig migrering av organisationens grundläggande kund data på en ny data Center-geo.</span><span class="sxs-lookup"><span data-stu-id="39724-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="39724-159">Här är ett exempel där en Microsoft 365-klient har flyttats från Europeiska unionen (EU) Data Center till den som befinner sig i Storbritannien (UK).</span><span class="sxs-lookup"><span data-stu-id="39724-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Exempel på att flytta en Microsoft 365-klient organisation mellan data Center geos](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="39724-161">Mer information finns i [Flytta grundläggande data till nya Microsoft 365 Data Center-geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="39724-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="39724-162">Produkter och licenser för en klient organisation</span><span class="sxs-lookup"><span data-stu-id="39724-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="39724-163">Din Microsoft 365-klient organisation skapas när du köper din första produkt, till exempel Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="39724-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="39724-164">Tillsammans med produkten är licenser, som debiteras per månad eller årlig avgift.</span><span class="sxs-lookup"><span data-stu-id="39724-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="39724-165">En administratör tilldelar sedan en tillgänglig licens från en av dina produkter till ett användar konto, antingen direkt eller via grupp medlemskap.</span><span class="sxs-lookup"><span data-stu-id="39724-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="39724-166">Beroende på organisationens affärs behov kan du ha en uppsättning produkter, var och en med sina egna licenser.</span><span class="sxs-lookup"><span data-stu-id="39724-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="39724-167">Det krävs lite planering för att fastställa produkterna och antalet licenser för var och en av dem:</span><span class="sxs-lookup"><span data-stu-id="39724-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="39724-168">Se till att du har tillräckligt med licenser för de användar konton som behöver avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="39724-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="39724-169">Förhindra att licenser tar slut eller att du inte har till gång till för många otilldelade licenser, baserat på ändringar i Personalen på din organisation.</span><span class="sxs-lookup"><span data-stu-id="39724-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="39724-170">Resultat i steg 1</span><span class="sxs-lookup"><span data-stu-id="39724-170">Results of Step 1</span></span>

<span data-ttu-id="39724-171">För din Microsoft 365 för företags klient organisationer har du fastställt:</span><span class="sxs-lookup"><span data-stu-id="39724-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="39724-172">Hur många klient organisationer du har eller behöver.</span><span class="sxs-lookup"><span data-stu-id="39724-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="39724-173">Vilka produkter och licenser som måste köpas för varje klient organisation.</span><span class="sxs-lookup"><span data-stu-id="39724-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="39724-174">Om en innehavare måste vara Multi-geo för att uppfylla data de kraven.</span><span class="sxs-lookup"><span data-stu-id="39724-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="39724-175">Om du behöver konfigurera samarbete mellan klienter.</span><span class="sxs-lookup"><span data-stu-id="39724-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="39724-176">Om du behöver migrera en klient organisation till en annan.</span><span class="sxs-lookup"><span data-stu-id="39724-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="39724-177">Om du behöver flytta grundläggande data från ett Data Center geo till New.</span><span class="sxs-lookup"><span data-stu-id="39724-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="39724-178">Här är ett exempel på en ny klient organisation.</span><span class="sxs-lookup"><span data-stu-id="39724-178">Here is an example of a new tenant.</span></span>

![Exempel på en ny klient organisation](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="39724-180">I den här bilden har klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="39724-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="39724-181">En standard plats för ett Microsoft 365-datacenter geo.</span><span class="sxs-lookup"><span data-stu-id="39724-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="39724-182">En uppsättning produkter och licenser.</span><span class="sxs-lookup"><span data-stu-id="39724-182">A set of products and licenses.</span></span>
- <span data-ttu-id="39724-183">Uppsättningen Cloud Productivity-appar, varav vissa är specifika för produkterna.</span><span class="sxs-lookup"><span data-stu-id="39724-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="39724-184">En Azure AD-klient som innehåller globala administratörs konton och ett ursprungligt DNS-domännamn.</span><span class="sxs-lookup"><span data-stu-id="39724-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="39724-185">När vi går igenom de ytterligare stegen i den här lösningen kommer vi att bygga upp den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="39724-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="39724-186">Pågående underhåll för klient organisationer</span><span class="sxs-lookup"><span data-stu-id="39724-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="39724-187">Kontinuerligt måste du kanske:</span><span class="sxs-lookup"><span data-stu-id="39724-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="39724-188">Lägg till en ny klient organisation.</span><span class="sxs-lookup"><span data-stu-id="39724-188">Add a new tenant.</span></span>
- <span data-ttu-id="39724-189">Lägg till nya produkter till en klient organisation med ett inledande antal licenser.</span><span class="sxs-lookup"><span data-stu-id="39724-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="39724-190">Ändra uppsättningen med licenser för en produkt i en klient organisation för att justera personal kraven.</span><span class="sxs-lookup"><span data-stu-id="39724-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="39724-191">Flytta dina grundläggande data från en klient organisation till en ny data Center Geo-plats.</span><span class="sxs-lookup"><span data-stu-id="39724-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="39724-192">Lägg till villkor för multi-geo för data de.</span><span class="sxs-lookup"><span data-stu-id="39724-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="39724-193">Konfigurera samarbete mellan innehavare.</span><span class="sxs-lookup"><span data-stu-id="39724-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="39724-194">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="39724-194">Next step</span></span>

<span data-ttu-id="39724-195">[![Steg 2. Optimera klient organisationen för nätverk för åtkomst](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="39724-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="39724-196">Fortsätt med [nätverk](tenant-management-networking.md) för att erbjuda optimala nätverksfunktioner från dina arbetare till Microsoft 365-moln tjänster.</span><span class="sxs-lookup"><span data-stu-id="39724-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
