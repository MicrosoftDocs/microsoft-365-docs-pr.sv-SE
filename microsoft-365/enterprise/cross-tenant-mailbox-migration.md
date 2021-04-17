---
title: Migrering av postlådor mellan klientorganisationer
description: Så här flyttar du postlådor mellan Microsoft 365- eller Office 365-klientorganisationen.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: d52a0ca4a2dc9b799a32f70962416ffe190e16db
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876193"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="75cea-103">Postlådemigrering mellan klientorganisationen (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="75cea-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="75cea-104">Tidigare när en Exchange Online-klientorganisation behövde flytta postlådor till en annan klientorganisation i samma Exchange Online-tjänst behövde de helt ta bort dem lokalt och sedan registrera dem i en ny klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="75cea-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="75cea-105">Med den nya funktionen för postlådemigrering mellan klientorganisationen kan innehavaradministratörer i både käll- och målklientorganisationen flytta postlådor mellan klientorganisationen med minimala infrastrukturberoenden i sina lokala system.</span><span class="sxs-lookup"><span data-stu-id="75cea-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="75cea-106">Det här tar bort behovet av postlådor för off-board och onboard.</span><span class="sxs-lookup"><span data-stu-id="75cea-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="75cea-107">Ofta vid sammanslagningar eller företag behöver du möjligheten att flytta användare och innehåll till en ny klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="75cea-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="75cea-108">När målklientorganisationens administratör kör flytten kallas det en pull-flytt, ungefär som migreringar av onboarding i molnet lokalt.</span><span class="sxs-lookup"><span data-stu-id="75cea-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="75cea-109">Exchange-postlådeflyttningar mellan klientorganisationen är helt självservice av innehavaradministratörer och använder välkända gränssnitt som kan skriptas i de större arbetsflödena som behövs för att flytta användare till den nya organisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="75cea-110">Administratörer kan använda `New-MigrationBatch` cmdleten, som är tillgänglig via rollen Flytta postlådor, för att köra flyttningar mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="75cea-111">Flyttningsprocessen omfattar autentiseringskontroller av klientorganisationen under synkronisering och slutförande av postlådan.</span><span class="sxs-lookup"><span data-stu-id="75cea-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="75cea-112">Användare som migrerar måste finnas i målklientorganisationens Exchange Online-system som MailUsers, markerat med specifika attribut för att aktivera flyttningar mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="75cea-113">Systemet kommer att misslyckas för användare som inte är korrekt konfigurerade i målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="75cea-114">När flytten är slutförd konverteras källsystempostlådan till MailUser och targetAddress (visas som ExternalEmailAddress i Exchange) stämplas med routningsadressen till målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="75cea-115">Den här processen lämnar den äldre MailUser i källklientorganisationen och möjliggör en viss period av samexisten och e-postdirigering.</span><span class="sxs-lookup"><span data-stu-id="75cea-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="75cea-116">När affärsprocesser tillåter kan källklientorganisationen ta bort källan MailUser eller konvertera dem till en e-postkontakt.</span><span class="sxs-lookup"><span data-stu-id="75cea-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="75cea-117">Exchange-postlådemigrering mellan klientorganisationen stöds endast för klientorganisationen i hybrid- eller molnet, eller en kombination av dessa.</span><span class="sxs-lookup"><span data-stu-id="75cea-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="75cea-118">I den här artikeln beskrivs processen för flytt av postlådor mellan klientorganisationen och innehåller anvisningar om hur du förbereder käll- och målklientorganisationen för innehållsflyttningen.</span><span class="sxs-lookup"><span data-stu-id="75cea-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="75cea-119">Förbereda käll- och målklientorganisationen</span><span class="sxs-lookup"><span data-stu-id="75cea-119">Preparing source and target tenants</span></span>

<span data-ttu-id="75cea-120">Funktionen för exchange-postlådemigrering med flera innehavare kräver auktorisering och utomfång för migreringar mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="75cea-121">Med hjälp av Azure Enterprise-programmet och lagringslösningar för nyckelvalv har nu innehavaradministratörer möjlighet att hantera både auktorisering och utomfång för Exchange Online-postlådemigrering från en klientorganisation till en annan.</span><span class="sxs-lookup"><span data-stu-id="75cea-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="75cea-122">Postlådeflyttningar mellan klientorganisationen har stöd för en modell för inbjudan och medgivande för att upprätta ett Azure Active Directory-program (Azure AD) som används för autentisering mellan ett klientpar.</span><span class="sxs-lookup"><span data-stu-id="75cea-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="75cea-123">Ytterligare komponenter, till exempel en organisationsrelation och en migreringsslutpunkt, krävs också.</span><span class="sxs-lookup"><span data-stu-id="75cea-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="75cea-124">Det här avsnittet innehåller inte de specifika steg som krävs för att förbereda användarobjekten för MailUser i målkatalogen, och inte heller exempelkommandot för att skicka en migreringsbatch.</span><span class="sxs-lookup"><span data-stu-id="75cea-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="75cea-125">Mer information [finns i Förbereda målanvändares objekt för](#prepare-target-user-objects-for-migration) migrering.</span><span class="sxs-lookup"><span data-stu-id="75cea-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75cea-126">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="75cea-126">Prerequisites</span></span>

<span data-ttu-id="75cea-127">Flyttfunktionen för postlådor mellan klientorganisationen kräver [att Azure](/azure/key-vault/basic-concepts) Key Vault skapar ett klientparspecifikt Azure-program för att på ett säkert sätt lagra och få åtkomst till det certifikat/den hemligt som används för att autentisera och auktorisera postlådemigrering från en klientorganisation till en annan, ta bort krav för att dela certifikat/hemligheter mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="75cea-128">Innan du startar kontrollerar du att du har de behörigheter som krävs för att köra distributionsskripten för att konfigurera Azure-nyckelvalv, programmet Flytta postlåda, EXO-migreringsslutpunkt och EXO-organisationsrelationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="75cea-129">Global administratör har vanligtvis behörighet att utföra alla konfigurationssteg.</span><span class="sxs-lookup"><span data-stu-id="75cea-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="75cea-130">Dessutom krävs e-postaktiverade säkerhetsgrupper i källklientorganisationen innan du kör konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="75cea-131">De här grupperna används för att begränsa listan över postlådor som kan flyttas från källklientorganisationen (eller som ibland kallas för resurs) till målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="75cea-132">På så sätt kan källklientorganisationens administratör begränsa eller begränsa den specifika uppsättning postlådor som måste flyttas, vilket hindrar oavsiktliga användare från att migreras.</span><span class="sxs-lookup"><span data-stu-id="75cea-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="75cea-133">Kapslade grupper stöds inte.</span><span class="sxs-lookup"><span data-stu-id="75cea-133">Nested groups are not supported.</span></span>

<span data-ttu-id="75cea-134">Du måste också kommunicera med ditt betrodda partnerföretag (som du kommer att flytta postlådor med) för att få deras Klientorganisations-ID för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75cea-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="75cea-135">Detta klient-ID används i fältet `DomainName` Organisationsrelation.</span><span class="sxs-lookup"><span data-stu-id="75cea-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="75cea-136">Om du vill ha klient-ID för en prenumeration loggar du in på administrationscentret för Microsoft 365 och går till [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="75cea-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="75cea-137">Klicka på kopieringsikonen för egenskapen Klientorganisations-ID för att kopiera den till Urklipp.</span><span class="sxs-lookup"><span data-stu-id="75cea-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="75cea-138">Så här fungerar processen.</span><span class="sxs-lookup"><span data-stu-id="75cea-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Klientförberedelse för postlådemigrering.":::

<span data-ttu-id="75cea-140">[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span><span class="sxs-lookup"><span data-stu-id="75cea-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="75cea-141">Förbereda klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="75cea-141">Prepare tenants</span></span>

<span data-ttu-id="75cea-142">På en hög nivå sker följande konfigurationsåtgärder när du kör installationsskripten.</span><span class="sxs-lookup"><span data-stu-id="75cea-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="75cea-143">Förbereda målklientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="75cea-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="75cea-144">Om ingen befintlig Azure-resursgrupp tillhandahålls skapas en ny (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="75cea-145">Om ett befintligt nyckelvalv inte tillhandahålls skapas ett nytt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="75cea-146">En ny åtkomstprincip skapas för postlådemigreringsprogrammet för Office 365 Exchange Online (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="75cea-147">Ett nytt certifikat skapas (eller befintligt, om det anges) som håller hemligheten med migreringsprogrammet (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="75cea-148">Ett nytt Azure AD-program skapas (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="75cea-149">Certifikatet/hemligheten laddas upp till migreringsprogrammet (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="75cea-150">Behörigheter för postlådemigrering tilldelas till programmet (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="75cea-151">Distributionsskriptet pausas tills måladministratören har gett sitt eget program (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="75cea-152">Målklientorganisationens administratör godkänner de behörigheter som ges till programmet (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="75cea-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="75cea-153">En organisationsrelation skapas till målklientorganisationen (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="75cea-154">En migreringsslutpunkt skapas för att hämta postlådor till målklientorganisationen (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="75cea-155">Förbereda källklientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="75cea-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="75cea-156">Källklientorganisationens administratör accepterar inbjudan om migrering av postlåda från målklientorganisationen (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="75cea-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="75cea-157">Källklientorganisationens administratör skapar en e-postaktiverad säkerhetsgrupp i klientorganisationen för att innehålla listan över postlådor som tillåts flyttas av migreringsprogrammet (MANUELL).</span><span class="sxs-lookup"><span data-stu-id="75cea-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="75cea-158">En organisationsrelation skapas för den målklientorganisation som anger postlådemigreringsprogrammet ska användas för OAuth-verifiering för att acceptera flyttningsbegäran (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="75cea-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="75cea-159">Stegvisa instruktioner för målklientorganisationens administratör</span><span class="sxs-lookup"><span data-stu-id="75cea-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="75cea-160">Hämta SetupCrossTenantRelationshipForTargetTenant.ps1 för konfigurationen av målklientorganisationen från [GitHub-databasen](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span><span class="sxs-lookup"><span data-stu-id="75cea-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="75cea-161">Spara skriptet (SetupCrossTenantRelationshipForTargetTenant.ps1) på den dator där du ska köra skriptet.</span><span class="sxs-lookup"><span data-stu-id="75cea-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="75cea-162">Skapa en Fjärranslutning till PowerShell-målklientorganisationen för Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="75cea-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="75cea-163">Kontrollera att du har de behörigheter som krävs för att köra distributionsskripten för att konfigurera Azure-nyckelvalvens lagring och certifikat, programmet Move Mailbox, EXO-migreringsslutpunkten och EXO-organisationsrelationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="75cea-164">Ändra mappens katalog till skriptplatsen eller kontrollera att skriptet för närvarande sparas på den plats som för närvarande finns i Remote PowerShell-sessionen.</span><span class="sxs-lookup"><span data-stu-id="75cea-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="75cea-165">Kör skriptet med följande parametrar och värden.</span><span class="sxs-lookup"><span data-stu-id="75cea-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="75cea-166">Parameter</span><span class="sxs-lookup"><span data-stu-id="75cea-166">Parameter</span></span> | <span data-ttu-id="75cea-167">Värde</span><span class="sxs-lookup"><span data-stu-id="75cea-167">Value</span></span> | <span data-ttu-id="75cea-168">Obligatorisk eller valfri</span><span class="sxs-lookup"><span data-stu-id="75cea-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="75cea-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="75cea-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="75cea-170">Målklientorganisationens domän, till exempel fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="75cea-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="75cea-171">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="75cea-171">Required</span></span> |
    | <span data-ttu-id="75cea-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="75cea-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="75cea-173">Källklientorganisationens domän, till exempel contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="75cea-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="75cea-174">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="75cea-174">Required</span></span> |
    | <span data-ttu-id="75cea-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="75cea-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="75cea-176">Källklientorganisationens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="75cea-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="75cea-177">Det här är källklientorganisationens administratör som godkänner användningen av postlådemigreringsprogrammet som skickas från måladministratören. Det här är administratören som får inbjudan via e-post för programmet.</span><span class="sxs-lookup"><span data-stu-id="75cea-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="75cea-178">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="75cea-178">Required</span></span> |
    | <span data-ttu-id="75cea-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="75cea-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="75cea-180">Organisationens källorganisations-ID (GUID).</span><span class="sxs-lookup"><span data-stu-id="75cea-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="75cea-181">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="75cea-181">Required</span></span> |
    | <span data-ttu-id="75cea-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="75cea-182">-SubscriptionId</span></span>                             | <span data-ttu-id="75cea-183">Den Azure-prenumeration som ska användas för att skapa resurser.</span><span class="sxs-lookup"><span data-stu-id="75cea-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="75cea-184">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="75cea-184">Required</span></span> |
    | <span data-ttu-id="75cea-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="75cea-185">-ResourceGroup</span></span>                              | <span data-ttu-id="75cea-186">Azure-resursgruppnamn som innehåller eller kommer att innehålla nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="75cea-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="75cea-187">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="75cea-187">Required</span></span> |
    | <span data-ttu-id="75cea-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="75cea-188">-KeyVaultName</span></span>                               | <span data-ttu-id="75cea-189">Azure-nyckelvalvsinstans där migreringscertifikatet/hemligheten för postlådeprogrammet lagras.</span><span class="sxs-lookup"><span data-stu-id="75cea-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="75cea-190">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="75cea-190">Required</span></span> |
    | <span data-ttu-id="75cea-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="75cea-191">-CertificateName</span></span>                            | <span data-ttu-id="75cea-192">Certifikatnamn när de skapar eller söker efter certifikat i nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="75cea-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="75cea-193">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="75cea-193">Required</span></span> |
    | <span data-ttu-id="75cea-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="75cea-194">-CertificateSubject</span></span>                         | <span data-ttu-id="75cea-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="75cea-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="75cea-196">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="75cea-196">Required</span></span> |
    | <span data-ttu-id="75cea-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="75cea-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="75cea-198">Migreringsprogram för e-post som ska användas om ett redan har skapats.</span><span class="sxs-lookup"><span data-stu-id="75cea-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="75cea-199">Valfritt</span><span class="sxs-lookup"><span data-stu-id="75cea-199">Optional</span></span> |
    | <span data-ttu-id="75cea-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="75cea-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="75cea-201">De behörigheter som krävs för postlådemigreringsprogrammet, till exempel Exchange eller MSGraph (Exchange för att flytta postlådor, MSGraph för att använda det här programmet för att skicka en inbjudan med en medgivandelänk till resursklientorganisationen).</span><span class="sxs-lookup"><span data-stu-id="75cea-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="75cea-202">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="75cea-202">Required</span></span> |
    | <span data-ttu-id="75cea-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="75cea-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="75cea-204">Parameter för att använda programmet som skapats för migrering för att användas för att skicka inbjudan om en medgivandelänk till källklientorganisationens administratör. Om inte det här visas en uppmaning om att ange måladministratörens autentiseringsuppgifter för att ansluta till Azure Invitation Manager och skicka inbjudan som måladministratör.</span><span class="sxs-lookup"><span data-stu-id="75cea-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="75cea-205">Valfritt</span><span class="sxs-lookup"><span data-stu-id="75cea-205">Optional</span></span> |
    | <span data-ttu-id="75cea-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="75cea-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="75cea-207">Lagringskontot där nyckelvalvens granskningsloggar lagras.</span><span class="sxs-lookup"><span data-stu-id="75cea-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="75cea-208">Valfritt</span><span class="sxs-lookup"><span data-stu-id="75cea-208">Optional</span></span> |
    | <span data-ttu-id="75cea-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="75cea-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="75cea-210">Resursgruppen som innehåller lagringskontot för lagring av granskningsloggar för nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="75cea-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="75cea-211">Valfritt</span><span class="sxs-lookup"><span data-stu-id="75cea-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="75cea-212">Se till att du har installerat Azure AD PowerShell-modulen innan du kör skripten.</span><span class="sxs-lookup"><span data-stu-id="75cea-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="75cea-213">Mer information om ![ ](/powershell/azure/install-az-ps?view=azps-5.1.0) installationsannstruktionerna finns här</span><span class="sxs-lookup"><span data-stu-id="75cea-213">Please refer to ![here](/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="75cea-214">Skriptet pausar och ber dig godkänna eller godkänna Exchange-postlådemigreringsprogrammet som skapades under den här processen.</span><span class="sxs-lookup"><span data-stu-id="75cea-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="75cea-215">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="75cea-215">Here is an example.</span></span>

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. <span data-ttu-id="75cea-216">En URL visas i Remote PowerShell-sessionen.</span><span class="sxs-lookup"><span data-stu-id="75cea-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="75cea-217">Kopiera den länk som du fått för klientorganisationens medgivande och klistra in den i en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="75cea-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="75cea-218">Logga in med dina autentiseringsuppgifter som global administratör.</span><span class="sxs-lookup"><span data-stu-id="75cea-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="75cea-219">När följande skärm visas väljer du **Acceptera**.</span><span class="sxs-lookup"><span data-stu-id="75cea-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialogrutan Acceptera behörigheter":::

9. <span data-ttu-id="75cea-221">Växla tillbaka till Remote PowerShell-sessionen och tryck på Retur för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="75cea-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="75cea-222">Skriptet konfigurerar de återstående installationsobjekten.</span><span class="sxs-lookup"><span data-stu-id="75cea-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="75cea-223">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="75cea-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="75cea-224">Konfigurationen av måladministratören är nu klar!</span><span class="sxs-lookup"><span data-stu-id="75cea-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="75cea-225">Stegvisa instruktioner för källklientorganisationens administratör</span><span class="sxs-lookup"><span data-stu-id="75cea-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="75cea-226">Logga in på din postlåda som det -ResourceTenantAdminEmail som anges av måladministratören under konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="75cea-227">Leta reda på e-postinbjudan från målklientorganisationen och välj **sedan knappen Komma** igång.</span><span class="sxs-lookup"><span data-stu-id="75cea-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialogrutan Du har bjudits in":::

2. <span data-ttu-id="75cea-229">Välj **Acceptera** för att acceptera inbjudan.</span><span class="sxs-lookup"><span data-stu-id="75cea-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialogruta för att godkänna behörigheter":::

   > [!NOTE]
   > <span data-ttu-id="75cea-231">Om du inte får det här e-postmeddelandet eller inte hittar det har målklientorganisationens administratör fått en direkt-URL som du kan få för att acceptera inbjudan.</span><span class="sxs-lookup"><span data-stu-id="75cea-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="75cea-232">URL-adressen ska i transkriptionen av målklientorganisationens administratörs Fjärr-PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="75cea-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="75cea-233">I administrationscentret för Microsoft 365 eller i en fjärrsession i PowerShell skapar du en eller flera e-postaktiverade säkerhetsgrupper för att styra listan över postlådor som tillåts av målklientorganisationen att hämta (flytta) från källklientorganisationen till målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="75cea-234">Du behöver inte fylla i den här gruppen i förväg, men du måste ha minst en grupp för att kunna köra konfigurationsstegen (skript).</span><span class="sxs-lookup"><span data-stu-id="75cea-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="75cea-235">Kapslade grupper stöds inte.</span><span class="sxs-lookup"><span data-stu-id="75cea-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="75cea-236">Ladda SetupCrossTenantRelationshipForResourceTenant.ps1 för källklientorganisationens konfiguration från GitHub-databasen här: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="75cea-236">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="75cea-237">Skapa en Fjärranslutning till PowerShell-källklientorganisationen med dina Exchange-administratörsbehörigheter.</span><span class="sxs-lookup"><span data-stu-id="75cea-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="75cea-238">Globala administratörsbehörigheter krävs inte för att konfigurera källklientorganisationen, utan endast målklientorganisationen på grund av azure-programskapandeprocessen.</span><span class="sxs-lookup"><span data-stu-id="75cea-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="75cea-239">Ändra katalog till skriptplatsen eller kontrollera att skriptet för närvarande är sparat på den plats som för närvarande finns i Remote PowerShell-sessionen.</span><span class="sxs-lookup"><span data-stu-id="75cea-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="75cea-240">Kör skriptet med följande obligatoriska parametrar och värden.</span><span class="sxs-lookup"><span data-stu-id="75cea-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="75cea-241">Parameter</span><span class="sxs-lookup"><span data-stu-id="75cea-241">Parameter</span></span> | <span data-ttu-id="75cea-242">Värde</span><span class="sxs-lookup"><span data-stu-id="75cea-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="75cea-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="75cea-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="75cea-244">E-postaktiverad säkerhetsgrupp som skapats av källklientorganisationen för identiteter/postlådor som omfattas för migreringen.</span><span class="sxs-lookup"><span data-stu-id="75cea-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="75cea-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="75cea-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="75cea-246">Källklientorganisationens domännamn, till exempel contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="75cea-246">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="75cea-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="75cea-247">-ApplicationId</span></span> | <span data-ttu-id="75cea-248">Azure-program-ID (GUID) för programmet som användes för migreringen.</span><span class="sxs-lookup"><span data-stu-id="75cea-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="75cea-249">Program-ID som är tillgängligt via din Azure-portal (Azure AD, Enterprise Applications, appnamn, program-ID) eller som finns i din e-postinbjudan.</span><span class="sxs-lookup"><span data-stu-id="75cea-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="75cea-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="75cea-250">-TargetTenantDomain</span></span> | <span data-ttu-id="75cea-251">Målklientorganisationens domännamn, till exempel fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="75cea-251">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="75cea-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="75cea-252">-TargetTenantId</span></span> | <span data-ttu-id="75cea-253">Klientorganisations-ID för målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="75cea-254">Till exempel så är Azure AD-klientorganisationens ID för contoso \. onmicrosoft.com klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="75cea-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="75cea-255">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="75cea-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="75cea-256">Källadministratörskonfigurationen är nu klar!</span><span class="sxs-lookup"><span data-stu-id="75cea-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="75cea-257">Verifiera installationen</span><span class="sxs-lookup"><span data-stu-id="75cea-257">Verify setup</span></span>

<span data-ttu-id="75cea-258">Kontrollera att organisationsrelationerna i både käll- och målklientorganisationen och migreringsslutpunkten i målet har skapats.</span><span class="sxs-lookup"><span data-stu-id="75cea-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="75cea-259">Målklientorganisation</span><span class="sxs-lookup"><span data-stu-id="75cea-259">Target tenant</span></span>

<span data-ttu-id="75cea-260">**Organisationsrelation**</span><span class="sxs-lookup"><span data-stu-id="75cea-260">**Organization relationship**</span></span>

<span data-ttu-id="75cea-261">Kontrollera att organisationsrelationsobjektet har skapats och konfigurerats med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="75cea-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="75cea-262">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="75cea-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="75cea-263">**Migreringsslutpunkt**</span><span class="sxs-lookup"><span data-stu-id="75cea-263">**Migration endpoint**</span></span>

<span data-ttu-id="75cea-264">Kontrollera att migreringsslutpunktsobjektet har skapats och konfigurerats med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="75cea-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="75cea-265">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="75cea-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="75cea-266">Källklientorganisation</span><span class="sxs-lookup"><span data-stu-id="75cea-266">Source tenant</span></span>

<span data-ttu-id="75cea-267">**Organisationsrelation**</span><span class="sxs-lookup"><span data-stu-id="75cea-267">**Organization relationship**</span></span>

<span data-ttu-id="75cea-268">Kontrollera att organisationsrelationsobjektet har skapats och konfigurerats med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="75cea-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="75cea-269">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="75cea-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="75cea-270">Verifiera installationsskriptet</span><span class="sxs-lookup"><span data-stu-id="75cea-270">Verify Setup Script</span></span>

<span data-ttu-id="75cea-271">Om du får felmeddelanden under konfigurationen av käll- eller målklientorganisationen kan du köra VerifySetup.ps1-skriptet som finns på [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) och granska resultatet.</span><span class="sxs-lookup"><span data-stu-id="75cea-271">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="75cea-272">Här är ett exempel på hur du kör VerifySetup.ps1 på målklientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="75cea-272">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="75cea-273">Här är ett exempel på VerifySetup.ps1 i källklientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="75cea-273">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="75cea-274">Flytta tillbaka postlådor till den ursprungliga källan</span><span class="sxs-lookup"><span data-stu-id="75cea-274">Move mailboxes back to the original source</span></span>

<span data-ttu-id="75cea-275">Om en postlåda flyttas tillbaka till den ursprungliga källklientorganisationen måste samma uppsättning steg och skript köras i både den nya källklientorganisationen och den nya målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-275">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="75cea-276">Det befintliga organisationsrelationsobjektet uppdateras eller läggs till, inte återskapas.</span><span class="sxs-lookup"><span data-stu-id="75cea-276">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="75cea-277">Förbereda målanvändarobjekt för migrering</span><span class="sxs-lookup"><span data-stu-id="75cea-277">Prepare target user objects for migration</span></span>

<span data-ttu-id="75cea-278">Användare som migrerar måste finnas i målklientorganisationen och Exchange Online-systemet (som MailUsers) markerade med specifika attribut för att aktivera flyttningar mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-278">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="75cea-279">Systemet kommer att misslyckas för användare som inte är korrekt konfigurerade i målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-279">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="75cea-280">I följande avsnitt finns information om MailUser-objektkraven för målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-280">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="75cea-281">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="75cea-281">Prerequisites</span></span>
  
<span data-ttu-id="75cea-282">Du måste se till att följande objekt och attribut anges i målorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-282">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="75cea-283">För alla postlådor som flyttas från en källorganisation måste du etablera ett MailUser-objekt i målorganisationen:</span><span class="sxs-lookup"><span data-stu-id="75cea-283">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="75cea-284">Target MailUser måste ha följande attribut från källpostlådan eller ha tilldelats det nya användarobjektet:</span><span class="sxs-lookup"><span data-stu-id="75cea-284">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="75cea-285">ExchangeGUID (direktflöde från källa till mål) – postlådans GUID måste matcha.</span><span class="sxs-lookup"><span data-stu-id="75cea-285">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="75cea-286">Flyttningsprocessen fortsätter inte om detta inte finns i målobjektet.</span><span class="sxs-lookup"><span data-stu-id="75cea-286">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="75cea-287">ArchiveGUID (direkt flöde från källa till mål) – arkiv-GUID måste matcha.</span><span class="sxs-lookup"><span data-stu-id="75cea-287">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="75cea-288">Flyttningsprocessen fortsätter inte om det inte finns i målobjektet.</span><span class="sxs-lookup"><span data-stu-id="75cea-288">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="75cea-289">(Detta krävs endast om källpostlådan är aktiverad).</span><span class="sxs-lookup"><span data-stu-id="75cea-289">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="75cea-290">LegacyExchangeDN (flöde som proxyAddress, "x500: ") – LegacyExchangeDN måste finnas på <LegacyExchangeDN> mål-MailUser som x500: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="75cea-290">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="75cea-291">Flyttningsprocesserna fortsätter inte om det inte finns i målobjektet.</span><span class="sxs-lookup"><span data-stu-id="75cea-291">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="75cea-292">UserPrincipalName – UPN justerar användarens NYA identitet eller målföretag (till exempel user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="75cea-292">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="75cea-293">Primary SMTPAddress – Primary SMTP address will align to the user's NEW company (for example, user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="75cea-293">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="75cea-294">TargetAddress/ExternalEmailAddress – MailUser refererar till användarens aktuella postlåda hos källklientorganisationen (till exempel user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="75cea-294">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="75cea-295">När du tilldelar det här värdet ska du kontrollera att du har/även tilldelar PrimarySMTPAddress, annars anges PrimarySMTPAddress som orsakar flyttningsfel.</span><span class="sxs-lookup"><span data-stu-id="75cea-295">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="75cea-296">Du kan inte lägga till äldre smtp-proxyadresser från källpostlådan till MailUser som mål.</span><span class="sxs-lookup"><span data-stu-id="75cea-296">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="75cea-297">Du kan till exempel inte underhålla contoso.com på den e-postadress som finns fabrikam.onmicrosoft.com-klientorganisationens objekt).</span><span class="sxs-lookup"><span data-stu-id="75cea-297">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="75cea-298">Domäner är kopplade till endast en Azure AD- eller Exchange Online-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="75cea-298">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="75cea-299">Exempel **på target** MailUser-objekt:</span><span class="sxs-lookup"><span data-stu-id="75cea-299">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="75cea-300">Attribut</span><span class="sxs-lookup"><span data-stu-id="75cea-300">Attribute</span></span>             | <span data-ttu-id="75cea-301">Värde</span><span class="sxs-lookup"><span data-stu-id="75cea-301">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="75cea-302">Alias</span><span class="sxs-lookup"><span data-stu-id="75cea-302">Alias</span></span>                 | <span data-ttu-id="75cea-303">LaraN</span><span class="sxs-lookup"><span data-stu-id="75cea-303">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="75cea-304">RecipientType</span><span class="sxs-lookup"><span data-stu-id="75cea-304">RecipientType</span></span>         | <span data-ttu-id="75cea-305">MailUser</span><span class="sxs-lookup"><span data-stu-id="75cea-305">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="75cea-306">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="75cea-306">RecipientTypeDetails</span></span>  | <span data-ttu-id="75cea-307">MailUser</span><span class="sxs-lookup"><span data-stu-id="75cea-307">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="75cea-308">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="75cea-308">UserPrincipalName</span></span>     | <span data-ttu-id="75cea-309">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="75cea-309">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="75cea-310">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="75cea-310">PrimarySmtpAddress</span></span>    | <span data-ttu-id="75cea-311">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="75cea-311">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="75cea-312">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="75cea-312">ExternalEmailAddress</span></span>  | <span data-ttu-id="75cea-313">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="75cea-313">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="75cea-314">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="75cea-314">ExchangeGuid</span></span>          | <span data-ttu-id="75cea-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="75cea-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="75cea-316">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="75cea-316">LegacyExchangeDN</span></span>      | <span data-ttu-id="75cea-317">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="75cea-317">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="75cea-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="75cea-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="75cea-319">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="75cea-319">EmailAddresses</span></span>        | <span data-ttu-id="75cea-320">x500:/o=First Organization/ou=Exchange Administrative Group (RÅDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="75cea-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="75cea-321">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="75cea-321">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="75cea-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="75cea-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="75cea-323">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="75cea-323">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="75cea-324">Exempel **på källpostlådeobjekt:**</span><span class="sxs-lookup"><span data-stu-id="75cea-324">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="75cea-325">Attribut</span><span class="sxs-lookup"><span data-stu-id="75cea-325">Attribute</span></span>             | <span data-ttu-id="75cea-326">Värde</span><span class="sxs-lookup"><span data-stu-id="75cea-326">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="75cea-327">Alias</span><span class="sxs-lookup"><span data-stu-id="75cea-327">Alias</span></span>                 | <span data-ttu-id="75cea-328">LaraN</span><span class="sxs-lookup"><span data-stu-id="75cea-328">LaraN</span></span>                                                                    |
     | <span data-ttu-id="75cea-329">RecipientType</span><span class="sxs-lookup"><span data-stu-id="75cea-329">RecipientType</span></span>         | <span data-ttu-id="75cea-330">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="75cea-330">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="75cea-331">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="75cea-331">RecipientTypeDetails</span></span>  | <span data-ttu-id="75cea-332">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="75cea-332">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="75cea-333">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="75cea-333">UserPrincipalName</span></span>     | <span data-ttu-id="75cea-334">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="75cea-334">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="75cea-335">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="75cea-335">PrimarySmtpAddress</span></span>    | <span data-ttu-id="75cea-336">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="75cea-336">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="75cea-337">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="75cea-337">ExchangeGuid</span></span>          | <span data-ttu-id="75cea-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="75cea-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="75cea-339">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="75cea-339">LegacyExchangeDN</span></span>      | <span data-ttu-id="75cea-340">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="75cea-340">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="75cea-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="75cea-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="75cea-342">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="75cea-342">EmailAddresses</span></span>        | <span data-ttu-id="75cea-343">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="75cea-343">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="75cea-344">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="75cea-344">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="75cea-345">Det kan redan finnas fler attribut i Exchange-hybridskrivning.</span><span class="sxs-lookup"><span data-stu-id="75cea-345">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="75cea-346">Om inte bör de inkluderas.</span><span class="sxs-lookup"><span data-stu-id="75cea-346">If not, they should be included.</span></span> 
   - <span data-ttu-id="75cea-347">msExchBlockedSendersHash – Skriver tillbaka data om betrodda och spärrade avsändare online från klienter till lokal Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75cea-347">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="75cea-348">msExchSafeRecipientsHash – Skriver tillbaka data om betrodda och spärrade avsändare online från klienter till lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75cea-348">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="75cea-349">msExchSafeSendersHash – Skriver tillbaka data om betrodda och spärrade avsändare online från klienter till lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75cea-349">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="75cea-350">Om källpostlådan finns i LitigationHold och storleken på återställningsbara objekt i källpostlådan är större än databasens standardstorlek (30 GB), går flyttningar inte vidare eftersom målkvoten är mindre än källpostlådans storlek.</span><span class="sxs-lookup"><span data-stu-id="75cea-350">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="75cea-351">Du kan uppdatera mailuser-målobjektet för att flytta över ELC-postlådeflaggor från källmiljön till målet, vilket utlöser målsystemet att utöka kvoten för MailUser till 100 GB, vilket gör att flytten till målet tillåts.</span><span class="sxs-lookup"><span data-stu-id="75cea-351">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="75cea-352">De här instruktionerna fungerar bara för hybrididentitet som kör Azure AD Connect, eftersom kommandon för att stämpla ELC-flaggor inte exponeras för innehavaradministratörer.</span><span class="sxs-lookup"><span data-stu-id="75cea-352">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="75cea-353">EXEMPEL – I SIN RÄTT TILL EXEMPEL INGEN GARANTI</span><span class="sxs-lookup"><span data-stu-id="75cea-353">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="75cea-354">Det här skriptet förutsätter en anslutning till både källpostlådan (för att få källvärden) och målet lokalt Active Directory (för att stämpla ADUser-objektet).</span><span class="sxs-lookup"><span data-stu-id="75cea-354">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="75cea-355">Om källan har aktiverat återställning av juridiska skäl eller enstaka objekt ska du ange detta i målkontot.</span><span class="sxs-lookup"><span data-stu-id="75cea-355">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="75cea-356">Detta ökar storleken på destinationskontot till 100 GB.</span><span class="sxs-lookup"><span data-stu-id="75cea-356">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="75cea-357">Icke-hybridmålklienter kan ändra kvoten för mappen Återställningsbara objekt för MailUsers innan migreringen genom att köra följande kommando för att aktivera Bevarande av juridiska skäl i MailUser-objektet och öka kvoten till 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="75cea-357">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="75cea-358">Observera att detta inte fungerar för klientorganisationen i hybriden.</span><span class="sxs-lookup"><span data-stu-id="75cea-358">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="75cea-359">Användare i målorganisationen måste vara licensierade med lämpliga Exchange Online-prenumerationer som gäller för organisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-359">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="75cea-360">Du kan använda en licens i förväg för en postlådeflyttning men BARA när målets MailUser är korrekt konfigurerad med ExchangeGUID- och proxyadresser.</span><span class="sxs-lookup"><span data-stu-id="75cea-360">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="75cea-361">Om du tillämpar en licens innan ExchangeGUID tillämpas kommer en ny postlåda etableras i målorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-361">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="75cea-362">När du använder en licens för ett Mailbox- eller MailUser-objekt rensas alla SMTP-typer proxyAddresses för att säkerställa att endast verifierade domäner ingår i matrisen Exchange EmailAddresses.</span><span class="sxs-lookup"><span data-stu-id="75cea-362">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="75cea-363">Du måste säkerställa att målets MailUser inte har någon tidigare ExchangeGuid som inte matchar Source ExchangeGuid.</span><span class="sxs-lookup"><span data-stu-id="75cea-363">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="75cea-364">Det här kan inträffa om mål-e-postinnehavaren tidigare har licensierats för Exchange Online och etablerat en postlåda.</span><span class="sxs-lookup"><span data-stu-id="75cea-364">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="75cea-365">Om målet MailUser tidigare har licensieras för eller hade en ExchangeGuid som inte matchar Source ExchangeGuid måste du rensa den molnbaserade e-postanvändaren.</span><span class="sxs-lookup"><span data-stu-id="75cea-365">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="75cea-366">Du kan köra för de här molnbaserade e-moln-e-molnanvändarna. `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`</span><span class="sxs-lookup"><span data-stu-id="75cea-366">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="75cea-367">Den här processen är bestående.</span><span class="sxs-lookup"><span data-stu-id="75cea-367">This process is irreversible.</span></span> <span data-ttu-id="75cea-368">Om objektet har en softDeleted-postlåda går det inte att återställa det efter den här punkten.</span><span class="sxs-lookup"><span data-stu-id="75cea-368">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="75cea-369">När du rensat kan du synkronisera rätt ExchangeGuid till målobjektet, och MRS ansluter källpostlådan till den nya målpostlådan.</span><span class="sxs-lookup"><span data-stu-id="75cea-369">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="75cea-370">(Referens EHLO-bloggen om den nya parametern.)</span><span class="sxs-lookup"><span data-stu-id="75cea-370">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="75cea-371">Hitta objekt som tidigare var postlådor med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="75cea-371">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="75cea-372">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="75cea-372">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="75cea-373">Rensa den mjukt borttagna postlådan med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="75cea-373">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="75cea-374">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="75cea-374">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="75cea-375">Utföra postlådemigrering</span><span class="sxs-lookup"><span data-stu-id="75cea-375">Perform mailbox migrations</span></span>

<span data-ttu-id="75cea-376">Exchange-postlådemigrering mellan klientorganisationen skickas som migreringsbatchar initierade från målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-376">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="75cea-377">Det här liknar det sätt som migreringsbatcharna på plats fungerar när du migrerar från Exchange lokalt till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75cea-377">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="75cea-378">Skapa migreringsbatchar</span><span class="sxs-lookup"><span data-stu-id="75cea-378">Create Migration batches</span></span>

<span data-ttu-id="75cea-379">Här är ett exempel på cmdlet för migreringsbatch för att starta flyttningar.</span><span class="sxs-lookup"><span data-stu-id="75cea-379">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="75cea-380">E-postadressen i CSV-filen måste vara den som anges i målklientorganisationen, inte källklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-380">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="75cea-381">Inskickning av migreringsbatch stöds också från det nya administrationscentret för Exchange när du väljer alternativet för flera innehavare.</span><span class="sxs-lookup"><span data-stu-id="75cea-381">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="75cea-382">Uppdatera lokala MailUsers</span><span class="sxs-lookup"><span data-stu-id="75cea-382">Update on-premises MailUsers</span></span>

<span data-ttu-id="75cea-383">När postlådan flyttas från källa till mål bör du se till att de lokala e-postanvändarna, både käll- och målanvändare, uppdateras med den nya targetAddress.</span><span class="sxs-lookup"><span data-stu-id="75cea-383">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="75cea-384">I exemplen är targetDeliveryDomain som används i flyttningen **contoso.onmicrosoft.com.**</span><span class="sxs-lookup"><span data-stu-id="75cea-384">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="75cea-385">Uppdatera e-postanvändarna med denna targetAddress.</span><span class="sxs-lookup"><span data-stu-id="75cea-385">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="75cea-386">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="75cea-386">Frequently asked questions</span></span>

<span data-ttu-id="75cea-387">**Behöver vi uppdatera RemoteMailboxes lokalt i källan efter flytten?**</span><span class="sxs-lookup"><span data-stu-id="75cea-387">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="75cea-388">Ja, du bör uppdatera targetAddress (RemoteRoutingAddress/ExternalEmailAddress) för den lokala källans användare när källklientorganisationens postlåda flyttas till målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-388">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="75cea-389">Även om e-postdirigering kan följa referenserna för flera e-postanvändare med olika targetAddresses måste uppslag för ledig/upptagen för e-postanvändare vara rätt mål för postlådans användare.</span><span class="sxs-lookup"><span data-stu-id="75cea-389">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="75cea-390">Uppslag av ledig/upptagen-information duar inte efter flera omdirigeringar.</span><span class="sxs-lookup"><span data-stu-id="75cea-390">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="75cea-391">**Migrerar Teams-möten mellan klientorganisationen?**</span><span class="sxs-lookup"><span data-stu-id="75cea-391">**Do Teams meetings migrate cross-tenant?**</span></span>  

<span data-ttu-id="75cea-392">Mötena flyttas men Teams mötes-URL uppdateras inte när objekt migreras mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-392">The meetings will move however the Teams meeting URL does not update when items migrate cross-tenant.</span></span> <span data-ttu-id="75cea-393">Eftersom URL:en blir ogiltig i målklientorganisationen måste du ta bort och återskapa Teams-mötena.</span><span class="sxs-lookup"><span data-stu-id="75cea-393">Since the URL will be invalid in the target tenant you will need to remove and recreate the Teams meetings.</span></span>

<span data-ttu-id="75cea-394">**Migrerar innehållet i chattmappen i Teams mellan klientorganisationen?**</span><span class="sxs-lookup"><span data-stu-id="75cea-394">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="75cea-395">Nej, innehållet i chattmappen i Teams migreras inte mellan klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-395">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="75cea-396">**Hur kan jag se flyttningar mellan klientorganisationen, inte flyttningar av registrering och off-boarding?**</span><span class="sxs-lookup"><span data-stu-id="75cea-396">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="75cea-397">Använd `-flags` parametern.</span><span class="sxs-lookup"><span data-stu-id="75cea-397">Use the `-flags` parameter.</span></span> <span data-ttu-id="75cea-398">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="75cea-398">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="75cea-399">**Kan du ange exempelskript för kopiering av attribut som används vid testning?**</span><span class="sxs-lookup"><span data-stu-id="75cea-399">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="75cea-400">EXEMPEL – I SIN RÄTT TILL EXEMPEL INGEN GARANTI</span><span class="sxs-lookup"><span data-stu-id="75cea-400">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="75cea-401">Det här skriptet förutsätter en anslutning till både källpostlådan (för att få källvärden) och målet lokalt Active Directory Domain Services (för att stämpla ADUser-objektet).</span><span class="sxs-lookup"><span data-stu-id="75cea-401">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="75cea-402">Om källan har aktiverat återställning av juridiska skäl eller enstaka objekt ska du ange detta i målkontot.</span><span class="sxs-lookup"><span data-stu-id="75cea-402">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="75cea-403">Detta ökar storleken på destinationskontot till 100 GB.</span><span class="sxs-lookup"><span data-stu-id="75cea-403">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on Get-Mailbox is for an attribute set on CustomAttribute1 = "ProjectKermit" 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFileUsers = "$home\desktop\userstomigrate.txt"
$outFileUsersXML = "$home\desktop\userstomigrate.xml"
#output the test objects 
Get-Mailbox -Filter "CustomAttribute1 -like 'ProjectKermit'" -ResultSize Unlimited | Select-Object -ExpandProperty Alias | Out-File $outFileUsers
$mailboxes = Get-Content $outFileUsers
$mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML

################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$mailboxes = Import-Clixml $home\desktop\userstomigrate.xml

foreach ($m in $mailboxes) {
    $organization = "@contoso.onmicrosoft.com"
    $mosi = $m.Alias+$organization
    $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
    $x500 = "x500:" +$m.LegacyExchangeDn
    $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
    $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "ProjectKermit"
    $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
    $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
    }

################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
<span data-ttu-id="75cea-404">**Hur kommer vi åt Outlook på dag 1 när postlådan har flyttats?**</span><span class="sxs-lookup"><span data-stu-id="75cea-404">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="75cea-405">Eftersom endast en klientorganisation kan äga en domän kommer den tidigare primära SMTPAddressen inte att kopplas till användaren i målklientorganisationen när postlådeflyttningen har slutförts. endast de domäner som är kopplade till den nya klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-405">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="75cea-406">Outlook använder användarnas nya UPN för att autentisera i tjänsten, och Outlook-profilen förväntar sig att hitta den äldre primära SMTPAddress för att matcha postlådan i målsystemet.</span><span class="sxs-lookup"><span data-stu-id="75cea-406">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="75cea-407">Eftersom den äldre adressen inte finns i målets system kan inte Outlook-profilen ansluta för att hitta den flyttade postlådan.</span><span class="sxs-lookup"><span data-stu-id="75cea-407">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="75cea-408">För den här första distributionen måste användarna återskapa sin profil med sin nya UPN,primära SMTP-adress och synkronisera OST-innehåll igen.</span><span class="sxs-lookup"><span data-stu-id="75cea-408">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="75cea-409">Planera enligt detta när du grupperar användarna så att de kan slutföras.</span><span class="sxs-lookup"><span data-stu-id="75cea-409">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="75cea-410">Du måste ta hänsyn till nätverksanvändningen och kapaciteten när Outlook-klientprofiler skapas och efterföljande OST- och OAB-filer laddas ned till klienter.</span><span class="sxs-lookup"><span data-stu-id="75cea-410">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="75cea-411">**Vilka Exchange RBAC-roller behöver jag vara medlem i för att konfigurera eller slutföra en flytt mellan klientorganisationen?**</span><span class="sxs-lookup"><span data-stu-id="75cea-411">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="75cea-412">Det finns en matris med roller utifrån antagandet om delegerade uppgifter vid körning av postlådeflyttning.</span><span class="sxs-lookup"><span data-stu-id="75cea-412">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="75cea-413">För närvarande krävs två roller:</span><span class="sxs-lookup"><span data-stu-id="75cea-413">Currently, two roles are required:</span></span>  

- <span data-ttu-id="75cea-414">Den första rollen är för en 1:a konfigurationsaktivitet som upprättar auktoriseringen för att flytta innehåll till eller från organisationens klientorganisations-/organisationsgräns.</span><span class="sxs-lookup"><span data-stu-id="75cea-414">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="75cea-415">Eftersom flytten av data från organisationens kontroll är ett viktigt problem för alla företag har vi valt den högsta tilldelade rollen som organisationsadministratör (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="75cea-415">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="75cea-416">Den här rollen måste ändra eller konfigurera en ny OrganizationRelationship som definierar -MailboxMoveCapability med den fjärranslutna organisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-416">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="75cea-417">Endast OrgAdmin kan ändra inställningen MailboxMoveCapability, medan andra attribut i OrganizationRelationhip kan hanteras av administratören för federerad delning.</span><span class="sxs-lookup"><span data-stu-id="75cea-417">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="75cea-418">Rollen för att köra de faktiska flyttningskommandona kan delegeras till en lägre nivå-funktion.</span><span class="sxs-lookup"><span data-stu-id="75cea-418">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="75cea-419">Rollen för Flytta postlådor tilldelas möjligheten att flytta postlådor till eller från organisationen med hjälp av `-RemoteTenant` parametern.</span><span class="sxs-lookup"><span data-stu-id="75cea-419">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="75cea-420">**Hur riktar vi den SMTP-adress som valts för targetAddress (TargetDeliveryDomain) på den konverterade postlådan (till MailUser-konvertering)?**</span><span class="sxs-lookup"><span data-stu-id="75cea-420">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="75cea-421">Exchange-postlådeflyttningar med MRS-skick av måladressen på den ursprungliga källpostlådan när du konverterar till en MailUser genom att matcha en e-postadress (proxyAddress) på målobjektet.</span><span class="sxs-lookup"><span data-stu-id="75cea-421">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="75cea-422">Processen tar värdet -TargetDeliveryDomain som skickas till flyttningskommandot och söker sedan efter en matchande proxy för den domänen på målsidan.</span><span class="sxs-lookup"><span data-stu-id="75cea-422">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="75cea-423">När vi hittar en matchning används den matchande proxyAdressen till att ange ExternalEmailAddress (targetAddress) på den konverterade postlådan (nu MailUser) objektet.</span><span class="sxs-lookup"><span data-stu-id="75cea-423">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="75cea-424">**Hur går postlådebehörigheter över?**</span><span class="sxs-lookup"><span data-stu-id="75cea-424">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="75cea-425">Postlådebehörigheter omfattar Skicka för och Postlådeåtkomst:</span><span class="sxs-lookup"><span data-stu-id="75cea-425">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="75cea-426">I Skicka för (AD:publicDelegates) lagras DN för mottagare med åtkomst till en användares postlåda som ombud.</span><span class="sxs-lookup"><span data-stu-id="75cea-426">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="75cea-427">Det här värdet lagras i Active Directory och flyttas för närvarande inte som en del av postlådeövergången.</span><span class="sxs-lookup"><span data-stu-id="75cea-427">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="75cea-428">Om källpostlådan har angetts med offentligDelegerat måste du skapa en ombyggnad av den offentligaDelegeringen på målpostlådan när konverteringen av e-postlådor har slutförts i målmiljön genom att köra `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` .</span><span class="sxs-lookup"><span data-stu-id="75cea-428">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="75cea-429">Postlådebehörigheter som lagras i postlådan flyttas med postlådan när både huvudmannen och ombudet flyttas till målsystemet.</span><span class="sxs-lookup"><span data-stu-id="75cea-429">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="75cea-430">Till exempel tilldelas användaren TestUser_7 FullAccess till postlådan i TestUser_8 i SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="75cea-430">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="75cea-431">När postlådeflyttningen har TargetCompany.onmicrosoft.com postlådeflyttningen konfigureras samma behörigheter i målkatalogen.</span><span class="sxs-lookup"><span data-stu-id="75cea-431">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="75cea-432">Exempel med *Get-MailboxPermission* för TestUser_7 i både käll- och målklientorganisationen visas nedan.</span><span class="sxs-lookup"><span data-stu-id="75cea-432">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="75cea-433">Exchange-cmdlets föregås av käll- och måldata i enlighet med detta.</span><span class="sxs-lookup"><span data-stu-id="75cea-433">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="75cea-434">Här är ett exempel på utdata för postlådebehörigheten före flytten.</span><span class="sxs-lookup"><span data-stu-id="75cea-434">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="75cea-435">Här är ett exempel på utdata för postlådebehörigheten efter flytten.</span><span class="sxs-lookup"><span data-stu-id="75cea-435">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="75cea-436">Behörigheter för postlådor och kalendrar mellan klientorganisationen stöds INTE.</span><span class="sxs-lookup"><span data-stu-id="75cea-436">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="75cea-437">Du måste organisera huvudnamn och ombud i konsoliderade flyttbatchar så att dessa anslutna postlådor flyttas samtidigt från källklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-437">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="75cea-438">**Vilken X500-proxy ska läggas till i mål-MailUser-proxyadresserna för att aktivera migrering?**</span><span class="sxs-lookup"><span data-stu-id="75cea-438">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="75cea-439">Postlådemigrering mellan klientorganisationen kräver att LegacyExchangeDN-värdet för källpostlådeobjektet stämplas som en x500-e-postadress på målets MailUser-objekt.</span><span class="sxs-lookup"><span data-stu-id="75cea-439">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="75cea-440">Exempel:</span><span class="sxs-lookup"><span data-stu-id="75cea-440">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="75cea-441">Utöver den här X500-proxyn måste du kopiera alla X500-proxyservrar från postlådan i källan till postlådan i målet.</span><span class="sxs-lookup"><span data-stu-id="75cea-441">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="75cea-442">**Var ska jag börja felsöka om flyttningar inte fungerar?**</span><span class="sxs-lookup"><span data-stu-id="75cea-442">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="75cea-443">Börja med att VerifySetup.ps1 skriptet som [finns på GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) och granska resultatet.</span><span class="sxs-lookup"><span data-stu-id="75cea-443">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="75cea-444">Här är ett exempel på hur du kör VerifySetup.ps1 på målklientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="75cea-444">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="75cea-445">Här är ett exempel på ett VerifySetup.ps1 på källklientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="75cea-445">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="75cea-446">**Kan käll- och målklientorganisationen använda samma domännamn?**</span><span class="sxs-lookup"><span data-stu-id="75cea-446">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="75cea-447">Nej.</span><span class="sxs-lookup"><span data-stu-id="75cea-447">No.</span></span> <span data-ttu-id="75cea-448">Domännamnen för käll- och målklientorganisationen måste vara unika.</span><span class="sxs-lookup"><span data-stu-id="75cea-448">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="75cea-449">En källdomän av contoso.com och måldomänen för fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="75cea-449">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="75cea-450">**Kommer delade postlådor att flyttas och fungerar fortfarande?**</span><span class="sxs-lookup"><span data-stu-id="75cea-450">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="75cea-451">Ja, men vi behåller bara lagringsbehörigheterna enligt beskrivningen i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="75cea-451">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="75cea-452">Microsoft Docs | Hantera behörigheter för mottagare i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="75cea-452">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="75cea-453">Microsoft Support | Så här beviljar du behörigheter för Exchange- och Outlook-postlådor i dedikerade Office 365</span><span class="sxs-lookup"><span data-stu-id="75cea-453">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="75cea-454">**Krävs Azure-nyckelvalv och när görs transaktioner?**</span><span class="sxs-lookup"><span data-stu-id="75cea-454">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="75cea-455">Ja, en Azure-prenumeration krävs för att använda nyckelvalv för att lagra certifikatet för att auktorisera migreringen.</span><span class="sxs-lookup"><span data-stu-id="75cea-455">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="75cea-456">Till skillnad från onboarding-migreringar där användarnamn och lösenord & används för autentisering för källan används OAuth och det här certifikatet som hemliga/autentiseringsuppgifter för flera klientorganisationens postlådemigreringar.</span><span class="sxs-lookup"><span data-stu-id="75cea-456">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="75cea-457">Åtkomst till nyckelvalvet måste bibehållas under alla postlådemigreringar eftersom det används en gång i början och en gång i slutet av migreringen, samt en gång var 24:e timme under stegvis synkronisering.</span><span class="sxs-lookup"><span data-stu-id="75cea-457">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="75cea-458">Du kan granska kostnadsinformation för AKV [här]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="75cea-458">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="75cea-459">**Har du några rekommendationer för batchar?**</span><span class="sxs-lookup"><span data-stu-id="75cea-459">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="75cea-460">Överstig inte 2 000 postlådor per batch.</span><span class="sxs-lookup"><span data-stu-id="75cea-460">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="75cea-461">Vi rekommenderar att du skickar in batchar två veckor före brytdatumet eftersom det inte påverkar slutanvändarna under synkroniseringen. Om du behöver vägledning för postlådemängder över 50 000 kan du kontakta distributionslistan för teknisk feedback crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="75cea-461">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="75cea-462">**Vad händer om jag använder tjänstkryptering med kundnyckel?**</span><span class="sxs-lookup"><span data-stu-id="75cea-462">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="75cea-463">Postlådan dekrypteras innan du flyttar den.</span><span class="sxs-lookup"><span data-stu-id="75cea-463">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="75cea-464">Se till att kundnyckeln är konfigurerad i målklientorganisationen om den fortfarande krävs.</span><span class="sxs-lookup"><span data-stu-id="75cea-464">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="75cea-465">Mer [](../compliance/customer-key-overview.md) information finns här.</span><span class="sxs-lookup"><span data-stu-id="75cea-465">See [here](../compliance/customer-key-overview.md) for more information.</span></span>  

<span data-ttu-id="75cea-466">**Vilken migreringstid beräknas?**</span><span class="sxs-lookup"><span data-stu-id="75cea-466">**What is the estimated migration time?**</span></span>

<span data-ttu-id="75cea-467">I tabellen som finns här [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) visas riktlinjer för när du kan förvänta dig att masspostlådemigrering eller enskilda migreringar ska slutföras för att hjälpa dig planera migreringen.</span><span class="sxs-lookup"><span data-stu-id="75cea-467">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="75cea-468">De här uppskattningarna baseras på en dataanalys av tidigare kundmigreringar.</span><span class="sxs-lookup"><span data-stu-id="75cea-468">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="75cea-469">Eftersom varje miljö är unik kan den exakta migreringshastigheten variera.</span><span class="sxs-lookup"><span data-stu-id="75cea-469">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="75cea-470">Kom ihåg att den här funktionen är i förhandsversion och SLA och alla tillämpliga tjänstnivåer gäller inte för några prestanda- eller tillgänglighetsproblem under förhandsgranskningsstatusen för den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="75cea-470">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="75cea-471">Kända problem</span><span class="sxs-lookup"><span data-stu-id="75cea-471">Known issues</span></span>  

-  <span data-ttu-id="75cea-472">**Problem: Automatiskt utökade arkiv kan inte migreras.**</span><span class="sxs-lookup"><span data-stu-id="75cea-472">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="75cea-473">Funktionen för migrering mellan klientorganisationen har stöd för migreringar av den primära postlådan och arkivpostlådan för en viss användare.</span><span class="sxs-lookup"><span data-stu-id="75cea-473">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="75cea-474">Om användaren i källan däremot har ett automatiskt expanderat arkiv, vilket innebär fler än en arkivpostlåda, kan funktionen inte migrera de extra arkiven och bör misslyckas.</span><span class="sxs-lookup"><span data-stu-id="75cea-474">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="75cea-475">**Problem: Cloud MailUsers med icke-ägd smtp-proxyAddress-block MRS flyttar bakgrunden.**</span><span class="sxs-lookup"><span data-stu-id="75cea-475">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="75cea-476">När du skapar MailUser-objekt för målklientorganisationen måste du se till att alla SMTP-proxyadresser tillhör målklientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-476">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="75cea-477">Om det finns en SMTP-proxyAddress på målanvändaren för e-post som inte tillhör den lokala klientorganisationen förhindras konverteringen av MailUser till Mailbox.</span><span class="sxs-lookup"><span data-stu-id="75cea-477">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="75cea-478">Detta beror på vår garanti för att postlådeobjekt bara kan skicka e-post från domäner där klientorganisationen är auktoritativ (domäner som anspråksklienten gör anspråk på):</span><span class="sxs-lookup"><span data-stu-id="75cea-478">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="75cea-479">När du synkroniserar användare från den lokala platsen med Azure AD Connect etablerar du lokala MailUser-objekt med ExternalEmailAddress som pekar på källklientorganisationen där postlådan finns (laran@contoso.onmicrosoft.com) och du stämplar PrimarySMTPAddress som en domän som finns i målklientorganisationen (Lara.Newton@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="75cea-479">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="75cea-480">De här värdena synkroniseras ned till klientorganisationen och en lämplig e-postanvändare har etablerats och är redo för migrering.</span><span class="sxs-lookup"><span data-stu-id="75cea-480">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="75cea-481">Här visas ett exempelobjekt.</span><span class="sxs-lookup"><span data-stu-id="75cea-481">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="75cea-482">Fältet *contoso.onmicrosoft.com* finns *inte i* matrisen E-postadresser/proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="75cea-482">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="75cea-483">**Problem: MailUser-objekt med "externa" primära SMTP-adresser ändras /återställs till "interna" företagsdrekuterade domäner**</span><span class="sxs-lookup"><span data-stu-id="75cea-483">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="75cea-484">MailUser-objekt är pekare till icke-lokala postlådor.</span><span class="sxs-lookup"><span data-stu-id="75cea-484">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="75cea-485">För postlådemigrering mellan klientorganisationen använder vi MailUser-objekt för att representera antingen källpostlådan (från målorganisationens perspektiv) eller målpostlådan (från källorganisationens perspektiv).</span><span class="sxs-lookup"><span data-stu-id="75cea-485">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="75cea-486">MailUsers har en ExternalEmailAddress (targetAddress) som pekar på smtp-adressen för den faktiska postlådan (ProxyTest@fabrikam.onmicrosoft.com) och primarySMTP-adressen som representerar den SMTP-adress som visas för postlådeanvändaren i katalogen.</span><span class="sxs-lookup"><span data-stu-id="75cea-486">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="75cea-487">Vissa organisationer väljer att visa den primära SMTP-adressen som en extern SMTP-adress, inte som en adress som ägs/verifieras av den lokala klientorganisationen (till exempel fabrikam.com i stället för som contoso.com).</span><span class="sxs-lookup"><span data-stu-id="75cea-487">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="75cea-488">När ett Objekt i en Exchange-tjänstplan tillämpas på MailUser via licensåtgärder ändras dock den primära SMTP-adressen så att den visas som en domän som verifierats av den lokala organisationen (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="75cea-488">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="75cea-489">Det finns två möjliga orsaker:</span><span class="sxs-lookup"><span data-stu-id="75cea-489">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="75cea-490">När ett Exchange-tjänstabonnemang tillämpas på en MailUser börjar Azure AD-processen att framtvinga proxyskrubbning för att säkerställa att den lokala organisationen inte kan skicka e-post, förfalskning eller e-post från en annan klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="75cea-490">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="75cea-491">Alla SMTP-adresser på ett mottagarobjekt med dessa tjänstplaner tas bort om adressen inte verifieras av den lokala organisationen.</span><span class="sxs-lookup"><span data-stu-id="75cea-491">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="75cea-492">Som i exemplet har Fabikam.com INTE verifierats av contoso.onmicrosoft.com-klientorganisationen, så skrubbningen tar bort det fabrikam.com domänen.</span><span class="sxs-lookup"><span data-stu-id="75cea-492">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="75cea-493">Om du vill bevara dessa externa domäner på MailUser, antingen före migreringen eller efter migreringen, måste du ändra dina migreringsprocesser för att ta bort licenser efter flytten eller innan flytten för att säkerställa att användarna har den förväntade externa varumärkeskopplingen.</span><span class="sxs-lookup"><span data-stu-id="75cea-493">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="75cea-494">Du måste se till att postlådeobjektet är korrekt licensierat för att inte påverka e-posttjänsten.</span><span class="sxs-lookup"><span data-stu-id="75cea-494">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="75cea-495">Ett exempelskript för att ta bort tjänstplaner på en MailUser i Contoso.onmicrosoft.com klientorganisationen visas här.</span><span class="sxs-lookup"><span data-stu-id="75cea-495">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="75cea-496">Resultatet för uppsättningen serviceplaner som har tilldelats visas här.</span><span class="sxs-lookup"><span data-stu-id="75cea-496">Results in the set of ServicePlans assigned are shown here.</span></span>

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       <span data-ttu-id="75cea-497">Användarens PrimarySMTPAddress är inte längre rensad.</span><span class="sxs-lookup"><span data-stu-id="75cea-497">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="75cea-498">Domänen fabrikam.com inte ägs av contoso.onmicrosoft.com klientorganisationen och finns kvar som den primära SMTP-adressen som visas i katalogen.</span><span class="sxs-lookup"><span data-stu-id="75cea-498">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="75cea-499">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="75cea-499">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="75cea-500">När msExchRemoteRecipientType är inställt på 8 (DeprovisionMailbox), kommer den lokala MailUsers som migreras till målklientorganisationen att ta bort icke-tillhörda domäner och återställa primarySMTP till en ägd domän.</span><span class="sxs-lookup"><span data-stu-id="75cea-500">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="75cea-501">Genom att rensa msExchRemoteRecipientType i den lokala MailUser tillämpas inte längre proxy-scrub-logiken.</span><span class="sxs-lookup"><span data-stu-id="75cea-501">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="75cea-502">Nedan visas alla möjliga tjänstplaner med Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="75cea-502">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="75cea-503">Namn</span><span class="sxs-lookup"><span data-stu-id="75cea-503">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="75cea-504">Advanced eDiscovery Storage (500 GB)</span><span class="sxs-lookup"><span data-stu-id="75cea-504">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="75cea-505">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="75cea-505">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="75cea-506">Dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="75cea-506">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="75cea-507">Exchange Enterprise CAL Services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="75cea-507">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="75cea-508">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="75cea-508">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="75cea-509">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="75cea-509">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="75cea-510">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="75cea-510">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="75cea-511">Exchange Online (abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="75cea-511">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="75cea-512">Exchange Online (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="75cea-512">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="75cea-513">Exchange Online – arkivering för Exchange Online</span><span class="sxs-lookup"><span data-stu-id="75cea-513">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="75cea-514">Exchange Online - arkivering för Exchange Server</span><span class="sxs-lookup"><span data-stu-id="75cea-514">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="75cea-515">Inaktivt användar tillägg för Exchange Online</span><span class="sxs-lookup"><span data-stu-id="75cea-515">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="75cea-516">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="75cea-516">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="75cea-517">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="75cea-517">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="75cea-518">Exchange Online-abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="75cea-518">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="75cea-519">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="75cea-519">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="75cea-520">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="75cea-520">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="75cea-521">Informationsbarriärer</span><span class="sxs-lookup"><span data-stu-id="75cea-521">Information Barriers</span></span>                              |
   | <span data-ttu-id="75cea-522">Informationsskydd för Office 365 – Premium</span><span class="sxs-lookup"><span data-stu-id="75cea-522">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="75cea-523">Informationsskydd för Office 365 – Standard</span><span class="sxs-lookup"><span data-stu-id="75cea-523">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="75cea-524">Insights från MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="75cea-524">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="75cea-525">Avancerad granskning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75cea-525">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="75cea-526">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="75cea-526">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="75cea-527">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="75cea-527">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="75cea-528">Microsoft MyAnalytics (fullständiga)</span><span class="sxs-lookup"><span data-stu-id="75cea-528">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="75cea-529">Avancerad eDiscovery för Office 365</span><span class="sxs-lookup"><span data-stu-id="75cea-529">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="75cea-530">Microsoft Defender för Office 365 (abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="75cea-530">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="75cea-531">Microsoft Defender för Office 365 (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="75cea-531">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="75cea-532">Hantering av behörighet i Office 365</span><span class="sxs-lookup"><span data-stu-id="75cea-532">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="75cea-533">Premiumkryptering i Office 365</span><span class="sxs-lookup"><span data-stu-id="75cea-533">Premium Encryption in Office 365</span></span>                  |
