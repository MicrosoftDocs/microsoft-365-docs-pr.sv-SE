---
title: Migrering av postlådor mellan klientorganisationer
description: Så här flyttar du post lådor mellan Microsoft 365 eller Office 365-klient organisationer.
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
ms.openlocfilehash: 4296879b36e26f11f945105ccebea351ad88314d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029532"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="559a9-103">Migrera mellan innehavare (för hands version)</span><span class="sxs-lookup"><span data-stu-id="559a9-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="559a9-104">Tidigare, när en Exchange Online-klient måste flytta post lådor till en annan klient organisation i samma Exchange Online-tjänst, måste de helt ta bort dem på lokal och sedan vara inloggade på en ny klient organisation.</span><span class="sxs-lookup"><span data-stu-id="559a9-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="559a9-105">Med den nya Överflyttnings funktionen för post lådor för flera innehavare kan klient organisationer i både käll-och mål klient organisationer flytta post lådor mellan klient organisationerna och deras lokala system.</span><span class="sxs-lookup"><span data-stu-id="559a9-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="559a9-106">Detta tar bort behovet av andra och andra-postlådor.</span><span class="sxs-lookup"><span data-stu-id="559a9-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="559a9-107">Vanligt vis kan du med att flytta användare och innehåll till en ny klient organisation under fusioner och divestitures.</span><span class="sxs-lookup"><span data-stu-id="559a9-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="559a9-108">När mål gruppens administratör utför flytten kallas det för pull-Move, som liknar lokal distribution med lokala Cloud-migreringar.</span><span class="sxs-lookup"><span data-stu-id="559a9-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="559a9-109">Exchange-postlådor för utbyte av flera innehavare är helt självbetjänings fria från klient organisationer, med välkända gränssnitt som kan följa skript i de större arbets flöden som behövs för att överföra användare till deras nya organisation.</span><span class="sxs-lookup"><span data-stu-id="559a9-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="559a9-110">Administratörer kan använda `New-MigrationBatch` cmdleten som är tillgänglig via hanterings rollen flytta post lådor för att utföra flytt av klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="559a9-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="559a9-111">Flyttnings processen inkluderar kontroll av klient organisationens verifiering under synkronisering och avslut.</span><span class="sxs-lookup"><span data-stu-id="559a9-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="559a9-112">Användare som migreras måste finnas i mål klient organisationens Exchange Online-system som användare med specifika attribut för att aktivera kors klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="559a9-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="559a9-113">Systemet kommer inte att flyttas för användare som inte har kon figurer ATS korrekt i mål klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="559a9-114">När flyttningarna är slutförda konverteras post lådan till Mail-användare och targetAddress (visas som ExternalEmailAddress i Exchange) med Dirigerings adressen till destinations innehavaren.</span><span class="sxs-lookup"><span data-stu-id="559a9-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="559a9-115">Den här processen lämnar den gamla e-postkontot i källans klient organisation och möjliggör en period med samtidig existens och e-postdirigering.</span><span class="sxs-lookup"><span data-stu-id="559a9-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="559a9-116">När affärs processer tillåts kan käll klient organisationen ta bort käll-mail-användaren eller konvertera dem till en e-postkontakt.</span><span class="sxs-lookup"><span data-stu-id="559a9-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="559a9-117">Migrering för Exchange-postlåda med flera innehavare stöds endast för klient organisationer i hybrid-eller moln syfte, eller någon kombination av båda.</span><span class="sxs-lookup"><span data-stu-id="559a9-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="559a9-118">I den här artikeln beskrivs processen för flytt av post lådor mellan innehavare och vägledning för hur du förbereder käll-och mål klienter för innehållet.</span><span class="sxs-lookup"><span data-stu-id="559a9-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="559a9-119">Förbereda käll-och mål klient organisationer</span><span class="sxs-lookup"><span data-stu-id="559a9-119">Preparing source and target tenants</span></span>

<span data-ttu-id="559a9-120">Migreringsguiden för Exchange-postlådan för flera innehavare kräver auktorisering och omfattning för migrering mellan innehavare.</span><span class="sxs-lookup"><span data-stu-id="559a9-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="559a9-121">Genom att använda Azure Enterprise-programmet och viktiga valv lagrings lösningarna kan klient administratörer hantera både auktorisering och omfångst av Exchange Online Mailbox-migreringar från en klient organisation till en annan.</span><span class="sxs-lookup"><span data-stu-id="559a9-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="559a9-122">Post låda för flera innehavare flyttar stöd för en inbjudan och en tillstånds modell för att upprätta ett Azure Active Directory-program som används för att verifiera ett klient par.</span><span class="sxs-lookup"><span data-stu-id="559a9-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="559a9-123">Ytterligare komponenter som organisations relationer och slut punkt för migrering krävs också.</span><span class="sxs-lookup"><span data-stu-id="559a9-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="559a9-124">I det här avsnittet ingår inte de steg som krävs för att förbereda användar objekt i gruppen användare i mål katalogen, eller så inkluderar det inte kommandot exempel för att skicka in en migreringstabell.</span><span class="sxs-lookup"><span data-stu-id="559a9-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="559a9-125">Se [förbereda mål användar objekt för migrering](#prepare-target-user-objects-for-migration) för den här informationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="559a9-126">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="559a9-126">Prerequisites</span></span>

<span data-ttu-id="559a9-127">För funktionen för flytt av post lådor krävs ett [Azure-valv](https://docs.microsoft.com/azure/key-vault/basic-concepts) för att upprätta ett klient organisations par-specifika Azure-program för säker lagring och åtkomst till certifikatet/hemligheten som används för att autentisera och auktorisera post lådans migrering från en klient organisation till den andra, vilket tar bort alla krav för att dela certifikat/hemligheter mellan klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="559a9-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="559a9-128">Innan du börjar bör du kontrol lera att du har nödvändig behörighet för att köra distributions skripten för att kunna konfigurera Azure Key Vault, flytta program varan för EXO, slut punkt för migrering och EXO organisations relation.</span><span class="sxs-lookup"><span data-stu-id="559a9-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="559a9-129">Vanligt vis har global administratör behörighet att utföra alla konfigurations steg.</span><span class="sxs-lookup"><span data-stu-id="559a9-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="559a9-130">Dessutom krävs e-postaktiverade säkerhets grupper i käll klient organisationen innan installationen körs.</span><span class="sxs-lookup"><span data-stu-id="559a9-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="559a9-131">Dessa grupper används för att scope listan med post lådor som kan flyttas från källan (eller ibland kallas resurs) för klient organisationen till mål innehavaren.</span><span class="sxs-lookup"><span data-stu-id="559a9-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="559a9-132">Detta gör att du kan använda administratörs administratören för att begränsa eller ange omfattningen av de post lådor som måste flyttas för att förhindra att oavsiktliga användare migreras.</span><span class="sxs-lookup"><span data-stu-id="559a9-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="559a9-133">Kapslade grupper stöds inte.</span><span class="sxs-lookup"><span data-stu-id="559a9-133">Nested groups are not supported.</span></span>

<span data-ttu-id="559a9-134">Du måste också kommunicera med ditt betrodda partner företag (du kommer att flytta brev lådor) för att få sitt Microsoft 365-klient-ID.</span><span class="sxs-lookup"><span data-stu-id="559a9-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="559a9-135">Detta klient-ID används i fältet organisations relation `DomainName` .</span><span class="sxs-lookup"><span data-stu-id="559a9-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="559a9-136">Om du vill skaffa klient organisationens ID för ett abonnemang loggar du in i administrations centret för Microsoft 365 och går till [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="559a9-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="559a9-137">Klicka på ikonen Kopiera för egenskapen innehavaradministration för att kopiera den till Urklipp.</span><span class="sxs-lookup"><span data-stu-id="559a9-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="559a9-138">Så här fungerar processen.</span><span class="sxs-lookup"><span data-stu-id="559a9-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Förberedelse av klient organisation för migrering av post låda.":::

<span data-ttu-id="559a9-140">[Visa en större version av bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span><span class="sxs-lookup"><span data-stu-id="559a9-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="559a9-141">Förbereda klient organisationer</span><span class="sxs-lookup"><span data-stu-id="559a9-141">Prepare tenants</span></span>

<span data-ttu-id="559a9-142">På en hög nivå utförs följande konfigurations åtgärder när du kör installations skripten.</span><span class="sxs-lookup"><span data-stu-id="559a9-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="559a9-143">Förbereda mål klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="559a9-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="559a9-144">Om det inte finns någon befintlig Azure-gruppgrupp skapas en ny (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="559a9-145">Om det inte finns något befintligt huvud valv skapas ett nytt (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="559a9-146">En ny åtkomst policy skapas för Office 365 Exchange Online Mailbox migration-programmet (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="559a9-147">Ett nytt certifikat skapas (eller används för det) för att hålla hemligheten till migreringsarkivet (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="559a9-148">Ett nytt Azure AD-program skapas (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="559a9-149">Certifikatet/hemligheten laddas upp till migreringsarkivet (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="559a9-150">Överflyttnings behörigheter för post lådor är tilldelade till programmet (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="559a9-151">Distributions skriptet pausas tills mål administratören samtycker till deras egna program (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="559a9-152">Mål organisationens administratör samtycker till de behörigheter som givits till programmet (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="559a9-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="559a9-153">En organisations relation skapas till mål klient organisationen (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="559a9-154">En slut punkt för migrering skapas för att hämta post lådor till mål klient organisationen (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="559a9-155">Förbereda käll klient organisationen:</span><span class="sxs-lookup"><span data-stu-id="559a9-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="559a9-156">Klient organisationens administratör accepterar godkännande från mål klient organisationen (MANUAL) för migrering av postinbjudan.</span><span class="sxs-lookup"><span data-stu-id="559a9-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="559a9-157">Klient organisationens administratör skapar en e-postaktive rad säkerhets grupp i sin klient organisation som innehåller listan över post lådor som ska kunna flyttas av migreringsarkivet (manuellt).</span><span class="sxs-lookup"><span data-stu-id="559a9-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="559a9-158">En organisations relation skapas till mål innehavaren som anger att programmet för postmigrering ska användas för OAuth-verifiering för att acceptera flytt förfrågan (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="559a9-159">Steg-för-steg-instruktioner för mål gruppens administratör</span><span class="sxs-lookup"><span data-stu-id="559a9-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="559a9-160">Ladda ned SetupCrossTenantRelationshipForTargetTenant.ps1-skript för mål klient organisationens konfiguration från [GitHub-databasen](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span><span class="sxs-lookup"><span data-stu-id="559a9-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="559a9-161">Spara skriptet (SetupCrossTenantRelationshipForTargetTenant.ps1) till den dator som du ska köra skriptet från.</span><span class="sxs-lookup"><span data-stu-id="559a9-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="559a9-162">Skapa en fjärran sluten PowerShell-anslutning till Exchange Online-måldomänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="559a9-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="559a9-163">Kontrol lera igen att du har nödvändig behörighet för att köra distributions skripten för att kunna konfigurera lagring och certifikat för Azure Key Vault, flytta program varan för migrering, EXO och EXO organisations relation.</span><span class="sxs-lookup"><span data-stu-id="559a9-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="559a9-164">Ändra katalogen för filmapp till skript platsen eller kontrol lera att skriptet är sparat på platsen som för närvarande är en fjärr-PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="559a9-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="559a9-165">Kör skriptet med följande parametrar och värden.</span><span class="sxs-lookup"><span data-stu-id="559a9-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="559a9-166">Indataparametern</span><span class="sxs-lookup"><span data-stu-id="559a9-166">Parameter</span></span> | <span data-ttu-id="559a9-167">Value</span><span class="sxs-lookup"><span data-stu-id="559a9-167">Value</span></span> | <span data-ttu-id="559a9-168">Obligatoriskt eller valfritt</span><span class="sxs-lookup"><span data-stu-id="559a9-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="559a9-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="559a9-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="559a9-170">Mål grupps domän, till exempel contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="559a9-170">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="559a9-171">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="559a9-171">Required</span></span> |
    | <span data-ttu-id="559a9-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="559a9-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="559a9-173">Käll klient organisation, till exempel Fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="559a9-173">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="559a9-174">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="559a9-174">Required</span></span> |
    | <span data-ttu-id="559a9-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="559a9-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="559a9-176">Källa för klient organisationens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="559a9-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="559a9-177">Det här är käll klientens administratör som kommer att skickas vidare till den som skickas från mål administratören. Det här är administratören som kommer att få e-postinbjudan för programmet.</span><span class="sxs-lookup"><span data-stu-id="559a9-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="559a9-178">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="559a9-178">Required</span></span> |
    | <span data-ttu-id="559a9-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="559a9-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="559a9-180">Organisations-ID för käll innehavare (GUID).</span><span class="sxs-lookup"><span data-stu-id="559a9-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="559a9-181">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="559a9-181">Required</span></span> |
    | <span data-ttu-id="559a9-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="559a9-182">-SubscriptionId</span></span>                             | <span data-ttu-id="559a9-183">Azure-abonnemanget som används för att skapa resurser.</span><span class="sxs-lookup"><span data-stu-id="559a9-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="559a9-184">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="559a9-184">Required</span></span> |
    | <span data-ttu-id="559a9-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="559a9-185">-ResourceGroup</span></span>                              | <span data-ttu-id="559a9-186">Namnet på Azure Resource-gruppen som innehåller eller kommer att innehålla huvud-valvet.</span><span class="sxs-lookup"><span data-stu-id="559a9-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="559a9-187">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="559a9-187">Required</span></span> |
    | <span data-ttu-id="559a9-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="559a9-188">-KeyVaultName</span></span>                               | <span data-ttu-id="559a9-189">Azure Key Vault-instans som lagrar certifikatet/hemligheten för post lådan.</span><span class="sxs-lookup"><span data-stu-id="559a9-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="559a9-190">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="559a9-190">Required</span></span> |
    | <span data-ttu-id="559a9-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="559a9-191">-CertificateName</span></span>                            | <span data-ttu-id="559a9-192">Certifikat namn när du skapar eller söker efter certifikat i Key Vault.</span><span class="sxs-lookup"><span data-stu-id="559a9-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="559a9-193">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="559a9-193">Required</span></span> |
    | <span data-ttu-id="559a9-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="559a9-194">-CertificateSubject</span></span>                         | <span data-ttu-id="559a9-195">Namn på certifikat för Azure Key valv, till exempel CN = contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="559a9-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="559a9-196">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="559a9-196">Required</span></span> |
    | <span data-ttu-id="559a9-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="559a9-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="559a9-198">E-postmigrering som ska användas om en redan har skapats.</span><span class="sxs-lookup"><span data-stu-id="559a9-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="559a9-199">Valfritt</span><span class="sxs-lookup"><span data-stu-id="559a9-199">Optional</span></span> |
    | <span data-ttu-id="559a9-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="559a9-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="559a9-201">De behörigheter som krävs för att få åtkomst till migreringsarkivet-programmet, till exempel Exchange eller MSGraph (Exchange för att flytta post lådor, MSGraph för att använda detta program för att skicka en inbjudan till resurs innehavaren av programmet.</span><span class="sxs-lookup"><span data-stu-id="559a9-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="559a9-202">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="559a9-202">Required</span></span> |
    | <span data-ttu-id="559a9-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="559a9-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="559a9-204">Parameter för användning av det program som har skapats för migrering för att skicka inbjudan om godkännande länk till source innehavaradministratörer-administratör. Om det inte visas uppmanas du att ange inloggnings uppgifter för att ansluta till Azure Inbjudnings hanteraren och skicka inbjudan som mål administratör.</span><span class="sxs-lookup"><span data-stu-id="559a9-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="559a9-205">Valfritt</span><span class="sxs-lookup"><span data-stu-id="559a9-205">Optional</span></span> |
    | <span data-ttu-id="559a9-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="559a9-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="559a9-207">Lagrings kontot där viktiga Valvs gransknings loggar lagras.</span><span class="sxs-lookup"><span data-stu-id="559a9-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="559a9-208">Valfritt</span><span class="sxs-lookup"><span data-stu-id="559a9-208">Optional</span></span> |
    | <span data-ttu-id="559a9-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="559a9-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="559a9-210">Resurs gruppen som innehåller lagrings kontot för att spara gransknings loggar för Key valv.</span><span class="sxs-lookup"><span data-stu-id="559a9-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="559a9-211">Valfritt</span><span class="sxs-lookup"><span data-stu-id="559a9-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="559a9-212">Kontrol lera att du har installerat Azure AD PowerShell-modulen innan du kör skripten.</span><span class="sxs-lookup"><span data-stu-id="559a9-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="559a9-213">Se ![ här ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) för installations anvisningar</span><span class="sxs-lookup"><span data-stu-id="559a9-213">Please refer to ![here](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="559a9-214">Skriptet pausas och du uppmanas att acceptera eller godkänna det migreringsåtgärder för Exchange-postprogrammet som skapades under processen.</span><span class="sxs-lookup"><span data-stu-id="559a9-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="559a9-215">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="559a9-215">Here is an example.</span></span>

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

7. <span data-ttu-id="559a9-216">En URL-adress kommer att visas i fjärrsessionen.</span><span class="sxs-lookup"><span data-stu-id="559a9-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="559a9-217">Kopiera länken som tillhandahålls för innehavarens medgivande och klistra in den i en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="559a9-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="559a9-218">Logga in med dina autentiseringsuppgifter för din globala administratör.</span><span class="sxs-lookup"><span data-stu-id="559a9-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="559a9-219">När följande skärm visas väljer du **acceptera**.</span><span class="sxs-lookup"><span data-stu-id="559a9-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialog rutan Godkänn behörigheter":::

9. <span data-ttu-id="559a9-221">Gå tillbaka till fjärrsessionen för PowerShell och Fortsätt genom att trycka på RETUR.</span><span class="sxs-lookup"><span data-stu-id="559a9-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="559a9-222">Skriptet konfigurerar de återstående installations objekt.</span><span class="sxs-lookup"><span data-stu-id="559a9-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="559a9-223">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="559a9-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="559a9-224">Konfigurationen för mål administratören är nu klar!</span><span class="sxs-lookup"><span data-stu-id="559a9-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="559a9-225">Stegvisa anvisningar för käll klient organisationens administratör</span><span class="sxs-lookup"><span data-stu-id="559a9-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="559a9-226">Logga in på din post låda som den-ResourceTenantAdminEmail som anges av mål administratören under installationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="559a9-227">Sök efter e-postinbjudan från mål innehavaren och välj sedan knappen **Kom igång** .</span><span class="sxs-lookup"><span data-stu-id="559a9-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialog rutan har blivit inbjuden":::

2. <span data-ttu-id="559a9-229">Välj **acceptera** för att acceptera inbjudan.</span><span class="sxs-lookup"><span data-stu-id="559a9-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialog ruta för att godkänna behörigheter":::

   > [!NOTE]
   > <span data-ttu-id="559a9-231">Om du inte får det här e-postmeddelandet eller inte kan hitta det, har mål organisationens administratör en direkt URL som kan tilldelas dig för att acceptera inbjudan.</span><span class="sxs-lookup"><span data-stu-id="559a9-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="559a9-232">URL: en ska i avskriften för klient organisationens fjärradministratörs fjärrsession.</span><span class="sxs-lookup"><span data-stu-id="559a9-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="559a9-233">I administrations centret för Microsoft 365 eller en fjärr-PowerShell-session skapar du en eller flera e-postaktiverade säkerhets grupper för att kontrol lera listan med post lådor som tillåts av mål klient organisationen för att ta bort (flytta) från käll klient organisationen till mål klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="559a9-234">Du behöver inte fylla i den här gruppen i förväg, men minst en grupp måste tillhandahållas för att köra konfigurations stegen (skript).</span><span class="sxs-lookup"><span data-stu-id="559a9-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="559a9-235">Kapslade grupper stöds inte.</span><span class="sxs-lookup"><span data-stu-id="559a9-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="559a9-236">Ladda ned SetupCrossTenantRelationshipForResourceTenant.ps1-skript för käll klient organisations konfiguration från GitHub-databasen här: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="559a9-236">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="559a9-237">Skapa en fjärran sluten PowerShell-anslutning till käll klient organisationen med administratörs behörigheter för Exchange.</span><span class="sxs-lookup"><span data-stu-id="559a9-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="559a9-238">Den globala administratörs behörighet krävs inte för att konfigurera käll klient organisationen, bara mål innehavaren på grund av processen att skapa Azure-program.</span><span class="sxs-lookup"><span data-stu-id="559a9-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="559a9-239">Byt katalog till skript platsen eller kontrol lera att skriptet för närvarande är sparat på platsen som för närvarande är en fjärr-PowerShell-session.</span><span class="sxs-lookup"><span data-stu-id="559a9-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="559a9-240">Kör skriptet med följande obligatoriska parametrar och värden.</span><span class="sxs-lookup"><span data-stu-id="559a9-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="559a9-241">Indataparametern</span><span class="sxs-lookup"><span data-stu-id="559a9-241">Parameter</span></span> | <span data-ttu-id="559a9-242">Value</span><span class="sxs-lookup"><span data-stu-id="559a9-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="559a9-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="559a9-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="559a9-244">E-postaktive rad säkerhets grupp skapad av käll klient organisationen för de identiteter/post lådor som är i omfång för migrering.</span><span class="sxs-lookup"><span data-stu-id="559a9-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="559a9-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="559a9-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="559a9-246">Käll klient namn för källan, till exempel Fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="559a9-246">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="559a9-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="559a9-247">-ApplicationId</span></span> | <span data-ttu-id="559a9-248">ID för Azure-programmet (GUID) för programmet som används för migrering.</span><span class="sxs-lookup"><span data-stu-id="559a9-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="559a9-249">Program-ID tillgängligt via din Azure-Portal (Azure AD, Enterprise-program, program namn, program-ID) eller inkluderat i e-postinbjudan.</span><span class="sxs-lookup"><span data-stu-id="559a9-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="559a9-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="559a9-250">-TargetTenantDomain</span></span> | <span data-ttu-id="559a9-251">Mål gruppens domän namn, till exempel contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="559a9-251">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="559a9-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="559a9-252">-TargetTenantId</span></span> | <span data-ttu-id="559a9-253">Innehavarens ID för mål innehavaren.</span><span class="sxs-lookup"><span data-stu-id="559a9-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="559a9-254">Till exempel Azure AD-klient organisations-ID: t contoso \. onmicrosoft.com-klienten.</span><span class="sxs-lookup"><span data-stu-id="559a9-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="559a9-255">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="559a9-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="559a9-256">Konfiguration av käll administratör är nu klar!</span><span class="sxs-lookup"><span data-stu-id="559a9-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="559a9-257">Verifiera inställningar</span><span class="sxs-lookup"><span data-stu-id="559a9-257">Verify setup</span></span>

<span data-ttu-id="559a9-258">Kontrol lera att organisations relationerna i både käll-och mål klient organisationer och slut punkt för migrering i målet har skapats.</span><span class="sxs-lookup"><span data-stu-id="559a9-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="559a9-259">Mål klient organisation</span><span class="sxs-lookup"><span data-stu-id="559a9-259">Target tenant</span></span>

<span data-ttu-id="559a9-260">**Organisations relation**</span><span class="sxs-lookup"><span data-stu-id="559a9-260">**Organization relationship**</span></span>

<span data-ttu-id="559a9-261">Kontrol lera att du har skapat och konfigurerat organisations Relations objekt med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="559a9-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="559a9-262">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="559a9-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="559a9-263">**Slut punkt för migrering**</span><span class="sxs-lookup"><span data-stu-id="559a9-263">**Migration endpoint**</span></span>

<span data-ttu-id="559a9-264">Kontrol lera att migrerings slut punkten skapades och konfigurerades med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="559a9-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="559a9-265">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="559a9-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="559a9-266">Käll klient organisation</span><span class="sxs-lookup"><span data-stu-id="559a9-266">Source tenant</span></span>

<span data-ttu-id="559a9-267">**Organisations relation**</span><span class="sxs-lookup"><span data-stu-id="559a9-267">**Organization relationship**</span></span>

<span data-ttu-id="559a9-268">Kontrol lera att du har skapat och konfigurerat organisations Relations objekt med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="559a9-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="559a9-269">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="559a9-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="559a9-270">Flytta tillbaka post lådorna till den ursprungliga källan</span><span class="sxs-lookup"><span data-stu-id="559a9-270">Move mailboxes back to the original source</span></span>

<span data-ttu-id="559a9-271">Om en post låda flyttas tillbaka till den ursprungliga käll klient organisationen krävs samma uppsättning steg och skript i både ny källa och nya mål klienter.</span><span class="sxs-lookup"><span data-stu-id="559a9-271">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="559a9-272">Befintligt organisations Relations objekt uppdateras eller läggs till, inte återskapas.</span><span class="sxs-lookup"><span data-stu-id="559a9-272">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="559a9-273">Förbereda mål användar objekt för migrering</span><span class="sxs-lookup"><span data-stu-id="559a9-273">Prepare target user objects for migration</span></span>

<span data-ttu-id="559a9-274">Användare som migreras måste finnas i mål klient organisationen och Exchange Online-systemet (som återanvändare) markeras med specifika attribut för att aktivera kors klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="559a9-274">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="559a9-275">Systemet kommer inte att flyttas för användare som inte har kon figurer ATS korrekt i mål klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-275">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="559a9-276">I följande avsnitt beskrivs användar objekts kraven för mål klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-276">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="559a9-277">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="559a9-277">Prerequisites</span></span>
  
<span data-ttu-id="559a9-278">Du måste kontrol lera att följande objekt och attribut är inställda i mål organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-278">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="559a9-279">För alla post lådor som flyttas från en käll organisation måste du tillhandahålla ett e-postobjekt i mål organisationen:</span><span class="sxs-lookup"><span data-stu-id="559a9-279">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="559a9-280">Mål-e-postkontot måste ha följande attribut från käll post lådan eller tilldelat det nya användarobjektet:</span><span class="sxs-lookup"><span data-stu-id="559a9-280">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="559a9-281">ExchangeGUID (direkt flöde från källa till mål) – post lådans GUID måste stämma.</span><span class="sxs-lookup"><span data-stu-id="559a9-281">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="559a9-282">Flyttningen går inte att genomföra om det inte finns någon på målobjektet.</span><span class="sxs-lookup"><span data-stu-id="559a9-282">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="559a9-283">ArchiveGUID (direkt flöde från källa till mål) – Arkiv-GUID måste stämma.</span><span class="sxs-lookup"><span data-stu-id="559a9-283">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="559a9-284">Flyttningen går inte att genomföra om det inte finns något på målobjektet.</span><span class="sxs-lookup"><span data-stu-id="559a9-284">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="559a9-285">(Detta krävs endast om käll brev lådan är aktive rad.</span><span class="sxs-lookup"><span data-stu-id="559a9-285">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="559a9-286">LegacyExchangeDN (flöde som proxyAddress, "x500: <LegacyExchangeDN> ") – LegacyExchangeDN måste finnas på mål gruppen.</span><span class="sxs-lookup"><span data-stu-id="559a9-286">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="559a9-287">Det går inte att gå vidare om det inte finns något på målobjektet.</span><span class="sxs-lookup"><span data-stu-id="559a9-287">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="559a9-288">UserPrincipalName – UPN kommer att justera till användarens nya identitet eller mål bolag (till exempel user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="559a9-288">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="559a9-289">Primär SMTPAddress – primär SMTP-adress kommer att justeras efter användarens nya företag (till exempel user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="559a9-289">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="559a9-290">TargetAddress/ExternalEmailAddress – Mail-användare hänvisar till användarens aktuella post låda i käll klient organisationen (till exempel user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="559a9-290">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="559a9-291">När du tilldelar det här värdet bör du kontrol lera att du har/tilldelar PrimarySMTPAddress eller det här värdet ställer in PrimarySMTPAddress som orsakar ett flytt problem.</span><span class="sxs-lookup"><span data-stu-id="559a9-291">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="559a9-292">Du kan inte lägga till gamla SMTP-proxyadresser från käll brev lådan till mål-och e-postanvändare.</span><span class="sxs-lookup"><span data-stu-id="559a9-292">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="559a9-293">Du kan till exempel inte underhålla contoso.com på POSTAKTIVERADE användaren i fabrikam.onmicrosoft.com klient organisations objekt).</span><span class="sxs-lookup"><span data-stu-id="559a9-293">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="559a9-294">Domäner är kopplade till bara en Azure AD-eller Exchange Online-klient organisation.</span><span class="sxs-lookup"><span data-stu-id="559a9-294">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="559a9-295">Exempel på **mål** användar objekt:</span><span class="sxs-lookup"><span data-stu-id="559a9-295">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="559a9-296">Attribut</span><span class="sxs-lookup"><span data-stu-id="559a9-296">Attribute</span></span>             | <span data-ttu-id="559a9-297">Value</span><span class="sxs-lookup"><span data-stu-id="559a9-297">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="559a9-298">Standardaliasuppsättning</span><span class="sxs-lookup"><span data-stu-id="559a9-298">Alias</span></span>                 | <span data-ttu-id="559a9-299">LaraN</span><span class="sxs-lookup"><span data-stu-id="559a9-299">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="559a9-300">RecipientType</span><span class="sxs-lookup"><span data-stu-id="559a9-300">RecipientType</span></span>         | <span data-ttu-id="559a9-301">Användare</span><span class="sxs-lookup"><span data-stu-id="559a9-301">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="559a9-302">En</span><span class="sxs-lookup"><span data-stu-id="559a9-302">RecipientTypeDetails</span></span>  | <span data-ttu-id="559a9-303">Användare</span><span class="sxs-lookup"><span data-stu-id="559a9-303">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="559a9-304">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="559a9-304">UserPrincipalName</span></span>     | <span data-ttu-id="559a9-305">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="559a9-305">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="559a9-306">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="559a9-306">PrimarySmtpAddress</span></span>    | <span data-ttu-id="559a9-307">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="559a9-307">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="559a9-308">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="559a9-308">ExternalEmailAddress</span></span>  | <span data-ttu-id="559a9-309">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="559a9-309">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="559a9-310">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="559a9-310">ExchangeGuid</span></span>          | <span data-ttu-id="559a9-311">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="559a9-311">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="559a9-312">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="559a9-312">LegacyExchangeDN</span></span>      | <span data-ttu-id="559a9-313">/o = första organisation/ou = Exchange administrativ grupp</span><span class="sxs-lookup"><span data-stu-id="559a9-313">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="559a9-314">(FYDIBOHF23SPDLT)/CN = mottagare/CN = 74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="559a9-314">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="559a9-315">Postadresser '</span><span class="sxs-lookup"><span data-stu-id="559a9-315">EmailAddresses</span></span>        | <span data-ttu-id="559a9-316">x500:/o = First organisation/ou = Exchange Administrative Group (FYDIBOHF23SPDLT)/CN = mottagare/CN = d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="559a9-316">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="559a9-317">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="559a9-317">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="559a9-318">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="559a9-318">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="559a9-319">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="559a9-319">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="559a9-320">Exempel på **käll** post låda:</span><span class="sxs-lookup"><span data-stu-id="559a9-320">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="559a9-321">Attribut</span><span class="sxs-lookup"><span data-stu-id="559a9-321">Attribute</span></span>             | <span data-ttu-id="559a9-322">Value</span><span class="sxs-lookup"><span data-stu-id="559a9-322">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="559a9-323">Standardaliasuppsättning</span><span class="sxs-lookup"><span data-stu-id="559a9-323">Alias</span></span>                 | <span data-ttu-id="559a9-324">LaraN</span><span class="sxs-lookup"><span data-stu-id="559a9-324">LaraN</span></span>                                                                    |
     | <span data-ttu-id="559a9-325">RecipientType</span><span class="sxs-lookup"><span data-stu-id="559a9-325">RecipientType</span></span>         | <span data-ttu-id="559a9-326">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="559a9-326">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="559a9-327">En</span><span class="sxs-lookup"><span data-stu-id="559a9-327">RecipientTypeDetails</span></span>  | <span data-ttu-id="559a9-328">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="559a9-328">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="559a9-329">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="559a9-329">UserPrincipalName</span></span>     | <span data-ttu-id="559a9-330">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="559a9-330">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="559a9-331">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="559a9-331">PrimarySmtpAddress</span></span>    | <span data-ttu-id="559a9-332">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="559a9-332">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="559a9-333">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="559a9-333">ExchangeGuid</span></span>          | <span data-ttu-id="559a9-334">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="559a9-334">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="559a9-335">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="559a9-335">LegacyExchangeDN</span></span>      | <span data-ttu-id="559a9-336">/o = första organisation/ou = Exchange administrativ grupp</span><span class="sxs-lookup"><span data-stu-id="559a9-336">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="559a9-337">(FYDIBOHF23SPDLT)/CN = mottagare/CN = d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="559a9-337">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="559a9-338">Postadresser '</span><span class="sxs-lookup"><span data-stu-id="559a9-338">EmailAddresses</span></span>        | <span data-ttu-id="559a9-339">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="559a9-339">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="559a9-340">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="559a9-340">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="559a9-341">Ytterligare attribut kan ingå i Exchange hybrid Skriv tillbaka.</span><span class="sxs-lookup"><span data-stu-id="559a9-341">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="559a9-342">Om inte, ska de inkluderas.</span><span class="sxs-lookup"><span data-stu-id="559a9-342">If not, they should be included.</span></span> 
   - <span data-ttu-id="559a9-343">msExchBlockedSendersHash – skriver tillbaka säkra och blockerade avsändare från klienter till lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="559a9-343">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="559a9-344">msExchSafeRecipientsHash – skriver tillbaka säkra och blockerade avsändare från klienter till lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="559a9-344">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="559a9-345">msExchSafeSendersHash – skriver tillbaka säkra och blockerade avsändare från klienter till lokala Active Directory.</span><span class="sxs-lookup"><span data-stu-id="559a9-345">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="559a9-346">Om käll brev lådan är på LitigationHold och storleken på post lådan för återställnings bara objekt är större än vår databas (30 GB), går det inte att flytta eftersom mål kvoten är mindre än käll post lådan.</span><span class="sxs-lookup"><span data-stu-id="559a9-346">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="559a9-347">Du kan uppdatera mål-e-postobjektet för att överföra ELC från käll miljön till målet, vilket utlöser mål systemet för att expandera kvoten för e-postkontot till 100 GB och därmed tillåta flytten till målet.</span><span class="sxs-lookup"><span data-stu-id="559a9-347">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="559a9-348">De här instruktionerna fungerar bara för Hybrid identitet med Azure AD Connect, eftersom de kommandon som används för att stämpla ELC flaggor inte är utsatta för klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="559a9-348">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="559a9-349">EXEMPEL – SOM DET ÄR, INGEN GARANTI</span><span class="sxs-lookup"><span data-stu-id="559a9-349">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="559a9-350">Det här manuset utgår från en anslutning till båda käll brev lådan (för att få käll värden) och mål platsen lokalt Active Directory (för att stämpla ADUser-objektet).</span><span class="sxs-lookup"><span data-stu-id="559a9-350">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="559a9-351">Om källan har en tvist eller återställning av enskilt objekt aktiverat anger du detta på mål kontot.</span><span class="sxs-lookup"><span data-stu-id="559a9-351">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="559a9-352">Detta ökar Dumpster storlek för mål kontot till 100 GB.</span><span class="sxs-lookup"><span data-stu-id="559a9-352">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="559a9-353">Icke-hybrid mål innehavare kan ändra kvoten för mappen för återställnings bara objekt för användare före migreringen genom att köra följande kommando för att aktivera tvist i gruppen User och öka kvoten till 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="559a9-353">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="559a9-354">Observera att detta inte fungerar för klient organisationer i hybrid.</span><span class="sxs-lookup"><span data-stu-id="559a9-354">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="559a9-355">Användare i mål organisationen måste vara licensierade med lämpliga Exchange Online-prenumerationer för organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-355">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="559a9-356">Du kan lägga till en licens i förväg i en post lådas flytt, men bara när mål-e-postkontot har kon figurer ATS korrekt med ExchangeGUID och proxyadresser.</span><span class="sxs-lookup"><span data-stu-id="559a9-356">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="559a9-357">Om du använder en licens innan ExchangeGUID tillämpas kommer en ny post låda att läggas till i mål organisation.</span><span class="sxs-lookup"><span data-stu-id="559a9-357">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="559a9-358">När du tillämpar en licens på en post låda eller ett e-postobjekt, tas alla SMTP-proxyAddresses bort så att endast verifierade domäner tas med i matrisen Exchange postadresser '.</span><span class="sxs-lookup"><span data-stu-id="559a9-358">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="559a9-359">Du måste se till att mål-ExchangeGuid inte har några tidigare som inte stämmer överens med ExchangeGuid.</span><span class="sxs-lookup"><span data-stu-id="559a9-359">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="559a9-360">Det här kan inträffa om mål-POSTAKTIVERADE användaren tidigare var licensierad för Exchange Online och etablerade en post låda.</span><span class="sxs-lookup"><span data-stu-id="559a9-360">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="559a9-361">Om mål-eller postanvändaren har licensierat för eller haft en ExchangeGuid som inte matchar käll ExchangeGuid måste du utföra en rensning av moln POSTAKTIVERADE användaren.</span><span class="sxs-lookup"><span data-stu-id="559a9-361">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="559a9-362">För dessa moln postaktiverade användare kan du köra `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .</span><span class="sxs-lookup"><span data-stu-id="559a9-362">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="559a9-363">Den här processen kan inte ångras.</span><span class="sxs-lookup"><span data-stu-id="559a9-363">This process is irreversible.</span></span> <span data-ttu-id="559a9-364">Om objektet har en softDeleted-postlåda kan den inte återställas efter den här punkten.</span><span class="sxs-lookup"><span data-stu-id="559a9-364">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="559a9-365">När du har avmarkerat den kan du synkronisera rätt ExchangeGuid till målobjektet och MRS ansluter käll post lådan till den nya mål post lådan.</span><span class="sxs-lookup"><span data-stu-id="559a9-365">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="559a9-366">(Referens, EHLO-blogg på den nya parametern.)</span><span class="sxs-lookup"><span data-stu-id="559a9-366">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="559a9-367">Hitta objekt som tidigare post lådor med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="559a9-367">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="559a9-368">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="559a9-368">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="559a9-369">Rensa den borttagna post lådan med det här kommandot.</span><span class="sxs-lookup"><span data-stu-id="559a9-369">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="559a9-370">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="559a9-370">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="559a9-371">Utföra migrering av post lådor</span><span class="sxs-lookup"><span data-stu-id="559a9-371">Perform mailbox migrations</span></span>

<span data-ttu-id="559a9-372">Migreringar av Exchange-postgrupper som skickas från mål klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-372">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="559a9-373">Detta liknar det sätt som de on-Board-kommandona fungerar när du migrerar från Exchange lokalt till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="559a9-373">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="559a9-374">Skapa migreringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="559a9-374">Create Migration batches</span></span>

<span data-ttu-id="559a9-375">Här är ett exempel på en cmdlet för migrering för att stoppa flytten.</span><span class="sxs-lookup"><span data-stu-id="559a9-375">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="559a9-376">E-postadressen i CSV-filen måste vara den som anges i mål klient organisationen, inte till käll klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-376">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="559a9-377">Batchbearbetning stöds också från det nya administrations centret för Exchange när du väljer alternativet kors klient organisation.</span><span class="sxs-lookup"><span data-stu-id="559a9-377">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="559a9-378">Uppdatera lokala användare</span><span class="sxs-lookup"><span data-stu-id="559a9-378">Update on-premises MailUsers</span></span>

<span data-ttu-id="559a9-379">När post lådan flyttas från källa till mål bör du kontrol lera att lokala e-postkonton, både källa och mål, uppdateras med den nya targetAddress.</span><span class="sxs-lookup"><span data-stu-id="559a9-379">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="559a9-380">I exemplen är targetDeliveryDomain som används i flytten **contoso.onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="559a9-380">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="559a9-381">Uppdatera e-postanvändare med denna targetAddress.</span><span class="sxs-lookup"><span data-stu-id="559a9-381">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="559a9-382">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="559a9-382">Frequently asked questions</span></span>

<span data-ttu-id="559a9-383">**Måste vi uppdatera RemoteMailboxes i lokal plats efter flytten?**</span><span class="sxs-lookup"><span data-stu-id="559a9-383">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="559a9-384">Ja, du bör uppdatera targetAddress (RemoteRoutingAddress/ExternalEmailAddress) för lokala käll användare när käll gruppens post låda flyttas till mål klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-384">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="559a9-385">När e-postroutning kan följa hänvisningar till flera e-postkonton med olika targetAddresses måste du ha en särskild/upptagen-sökning för att e-postanvändare ska ha plats för platsen för post lådan.</span><span class="sxs-lookup"><span data-stu-id="559a9-385">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="559a9-386">Ledig/upptagen-sökningar kommer inte att spåra flera omdirigeringar.</span><span class="sxs-lookup"><span data-stu-id="559a9-386">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="559a9-387">**Migrerar mappen Teams-mappinnehåll kors klient organisationen?**</span><span class="sxs-lookup"><span data-stu-id="559a9-387">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="559a9-388">Nej, mappinnehåll för Teams-chatt migrerar inte kors klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="559a9-388">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="559a9-389">**Hur kan jag se bara flytt mellan klient organisationer, inte mina inregistreringar och släckning?**</span><span class="sxs-lookup"><span data-stu-id="559a9-389">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="559a9-390">Använd `-flags` parametern.</span><span class="sxs-lookup"><span data-stu-id="559a9-390">Use the `-flags` parameter.</span></span> <span data-ttu-id="559a9-391">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="559a9-391">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="559a9-392">**Kan du ange exempel skript för kopiering av attribut som används vid testning?**</span><span class="sxs-lookup"><span data-stu-id="559a9-392">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="559a9-393">EXEMPEL – SOM DET ÄR, INGEN GARANTI</span><span class="sxs-lookup"><span data-stu-id="559a9-393">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="559a9-394">Det här manuset utgår från en anslutning till båda käll brev lådan (för att få käll värden) och målets lokala Active Directory Domain Services (för att stämpla ADUser-objektet).</span><span class="sxs-lookup"><span data-stu-id="559a9-394">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="559a9-395">Om källan har en tvist eller återställning av enskilt objekt aktiverat anger du detta på mål kontot.</span><span class="sxs-lookup"><span data-stu-id="559a9-395">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="559a9-396">Detta ökar Dumpster storlek för mål kontot till 100 GB.</span><span class="sxs-lookup"><span data-stu-id="559a9-396">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
<span data-ttu-id="559a9-397">**Hur kommer vi åt Outlook på dag 1 efter att Använd post låda har flyttats?**</span><span class="sxs-lookup"><span data-stu-id="559a9-397">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="559a9-398">Eftersom bara en klient organisation kan äga en domän kopplas inte den tidigare primära SMTPAddress till användaren i mål klient organisationen när flytt brev lådan är klar. endast de domäner som är kopplade till den nya innehavaren.</span><span class="sxs-lookup"><span data-stu-id="559a9-398">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="559a9-399">Outlook använder de nya UPN-användarna för att autentisera till tjänsten och Outlook-profilen förväntar sig att hitta den äldre primära SMTPAddress för att matcha post lådan i mål systemet.</span><span class="sxs-lookup"><span data-stu-id="559a9-399">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="559a9-400">Eftersom den äldre adressen inte finns i mål systemet går det inte att ansluta till den nyligen flyttade post lådan.</span><span class="sxs-lookup"><span data-stu-id="559a9-400">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="559a9-401">För den här första distributionen måste användarna återskapa sin profil med deras nya UPN, primära SMTP-adress och Synkronisera OST-innehåll på nytt.</span><span class="sxs-lookup"><span data-stu-id="559a9-401">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="559a9-402">Planera detta när du gruppanvändar dina användare.</span><span class="sxs-lookup"><span data-stu-id="559a9-402">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="559a9-403">Du måste ha till gång till nätverks användning och-kapacitet när Outlook-klient profiler skapas och följande OST-och OAB-filer laddas ned till klienter.</span><span class="sxs-lookup"><span data-stu-id="559a9-403">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="559a9-404">**Vilka Exchange RBAC-roller måste jag vara medlem i för att kunna konfigurera eller slutföra en förflyttning mellan klienter?**</span><span class="sxs-lookup"><span data-stu-id="559a9-404">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="559a9-405">En matris med roller baseras på antagande av delegerade uppgifter när en post låda flyttas.</span><span class="sxs-lookup"><span data-stu-id="559a9-405">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="559a9-406">För närvarande krävs två roller:</span><span class="sxs-lookup"><span data-stu-id="559a9-406">Currently, two roles are required:</span></span>  

- <span data-ttu-id="559a9-407">Den första rollen är en konfiguration med en enda tids period som anger tillstånd för att flytta innehåll till eller från din klient organisations gräns.</span><span class="sxs-lookup"><span data-stu-id="559a9-407">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="559a9-408">Eftersom flytt av data från din organisations kontroll är ett kritiskt problem för alla företag har vi valt den mest tilldelade rollen som organisations administratör (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="559a9-408">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="559a9-409">Den här rollen måste ändra eller ställa in en ny OrganizationRelationship som definierar MailboxMoveCapability med fjärrorganisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-409">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="559a9-410">Det är bara funktionen OrgAdmin som kan ändra inställningen för MailboxMoveCapability medan andra attribut i OrganizationRelationhip kan hanteras av administratören för extern delning.</span><span class="sxs-lookup"><span data-stu-id="559a9-410">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="559a9-411">Rollen för att köra kommandot faktiskt flytt kan delegeras till en lågnivå funktion.</span><span class="sxs-lookup"><span data-stu-id="559a9-411">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="559a9-412">Rollen som flyttar post lådor är kopplad till eller från organisationen genom att använda `-RemoteTenant` parametern.</span><span class="sxs-lookup"><span data-stu-id="559a9-412">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="559a9-413">**Hur kan vi nå SMTP-adressen för targetAddress (TargetDeliveryDomain) på den konverterade post lådan (to user Conversion)?**</span><span class="sxs-lookup"><span data-stu-id="559a9-413">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="559a9-414">Exchange-postlådan flyttar med MRS-båtar targetAddress på den ursprungliga käll brev lådan när du konverterar till en e-postanvändare genom att matcha en adress (proxyAddress) för målobjektet.</span><span class="sxs-lookup"><span data-stu-id="559a9-414">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="559a9-415">Processen tar TargetDeliveryDomain-värdet som skickas till kommandot Move och letar sedan efter en matchande proxyserver för domänen på mål sidan.</span><span class="sxs-lookup"><span data-stu-id="559a9-415">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="559a9-416">När vi hittar en matchning används den matchande proxyAddress för att ange ExternalEmailAddress (targetAddress) i det konverterade post lådan (nu).</span><span class="sxs-lookup"><span data-stu-id="559a9-416">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="559a9-417">**Hur över gången åtkomst till post lådor?**</span><span class="sxs-lookup"><span data-stu-id="559a9-417">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="559a9-418">Behörigheter för Mailbox inkluderar Send för användarens och post lådans åtkomst:</span><span class="sxs-lookup"><span data-stu-id="559a9-418">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="559a9-419">Skicka åt (AD: publicDelegates) lagrar DN för mottagarna med åtkomst till en användares post låda som ombud.</span><span class="sxs-lookup"><span data-stu-id="559a9-419">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="559a9-420">Det här värdet lagras i Active Directory och flyttas inte som en del av över gången till post lådan.</span><span class="sxs-lookup"><span data-stu-id="559a9-420">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="559a9-421">Om käll brev lådan innehåller publicDelegates måste du omstämpla publicDelegates i mål brev lådan när POSTAKTIVERADE användaren-konverteringen till post låda har slutförts i mål miljön `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` .</span><span class="sxs-lookup"><span data-stu-id="559a9-421">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="559a9-422">Behörigheter för Mailbox som lagras i post lådan flyttas med post lådan när både huvud kontot och ombudet flyttas till mål systemet.</span><span class="sxs-lookup"><span data-stu-id="559a9-422">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="559a9-423">Användaren TestUser_7 ges till exempel behörigheten Full Access till post lådan TestUser_8 i klient organisationens SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="559a9-423">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="559a9-424">När flyttningen av post lådan är färdig med TargetCompany.onmicrosoft.com har samma behörigheter ställts in i mål katalogen.</span><span class="sxs-lookup"><span data-stu-id="559a9-424">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="559a9-425">Exempel på *Get-MailboxPermission* för TestUser_7 i både käll-och mål klient organisationer visas nedan.</span><span class="sxs-lookup"><span data-stu-id="559a9-425">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="559a9-426">Exchange-cmdlets föregås av källa och mål därefter.</span><span class="sxs-lookup"><span data-stu-id="559a9-426">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="559a9-427">Här är ett exempel på utdata från Mailbox-behörigheten före flytt.</span><span class="sxs-lookup"><span data-stu-id="559a9-427">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="559a9-428">Här är ett exempel på utdata från Mailbox-behörighet efter flytten.</span><span class="sxs-lookup"><span data-stu-id="559a9-428">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="559a9-429">Det går inte att hantera behörigheter mellan innehavare och kalender.</span><span class="sxs-lookup"><span data-stu-id="559a9-429">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="559a9-430">Du måste ordna objekt och ombud i konsoliderade flyttningar så att dessa kopplade post lådor kopplas samtidigt från käll klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-430">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="559a9-431">**Vilken X500-proxy bör läggas till i mål adresserna för användar adresser för att aktivera migrering?**</span><span class="sxs-lookup"><span data-stu-id="559a9-431">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="559a9-432">Migreringen av post lådan mellan innehavare kräver att LegacyExchangeDN-värdet för käll post lådans objekt ska märkas som en x500 e-postadress i mål gruppen.</span><span class="sxs-lookup"><span data-stu-id="559a9-432">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="559a9-433">Exempel:</span><span class="sxs-lookup"><span data-stu-id="559a9-433">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="559a9-434">Förutom den här X500-proxyservern måste du kopiera alla X500-proxyservrar från post lådan i källan till post lådan i målet.</span><span class="sxs-lookup"><span data-stu-id="559a9-434">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="559a9-435">**Behövs ett Azure Key-valv och när transaktioner görs?**</span><span class="sxs-lookup"><span data-stu-id="559a9-435">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="559a9-436">Ja, ett Azure-abonnemang krävs för att använda Key Vault för att lagra certifikatet för att auktorisera migrering.</span><span class="sxs-lookup"><span data-stu-id="559a9-436">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="559a9-437">Till skillnad från migrering som använder användar namn & lösen ord för att autentisera till käll gruppen migrerade post lådor används OAuth och detta certifikat som hemlighet/autentiseringsuppgift.</span><span class="sxs-lookup"><span data-stu-id="559a9-437">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="559a9-438">Åtkomst till Key Vault måste finnas i hela alla migreringar av postlådan när den används en gång vid början och när migreringen har slutförts, samt en gång var 24: e timme.</span><span class="sxs-lookup"><span data-stu-id="559a9-438">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="559a9-439">Du kan granska AKV kostnads information [här]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="559a9-439">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="559a9-440">**Har du några rekommendationer för batchar?**</span><span class="sxs-lookup"><span data-stu-id="559a9-440">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="559a9-441">Inte överskrida 2000 post lådor per batch.</span><span class="sxs-lookup"><span data-stu-id="559a9-441">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="559a9-442">Vi rekommenderar starkt att du skickar satser två veckor före datumet för stycknings tillfället eftersom det inte påverkar slutanvändarna under synkroniseringen. Om du behöver vägledning för post lådor över 50 000 kan du nå distributions listan för teknisk feedback på crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="559a9-442">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="559a9-443">**Vad händer om jag använder tjänst kryptering med kund nycklar?**</span><span class="sxs-lookup"><span data-stu-id="559a9-443">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="559a9-444">Post lådan kommer att avkrypteras innan den flyttas.</span><span class="sxs-lookup"><span data-stu-id="559a9-444">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="559a9-445">Se till att kund nycklar är konfigurerat i mål klient organisationen om det fortfarande krävs.</span><span class="sxs-lookup"><span data-stu-id="559a9-445">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="559a9-446">Se [här](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) för mer information.</span><span class="sxs-lookup"><span data-stu-id="559a9-446">See [here](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) for more information.</span></span>  

<span data-ttu-id="559a9-447">**Vad är den uppskattade migrations tiden?**</span><span class="sxs-lookup"><span data-stu-id="559a9-447">**What is the estimated migration time?**</span></span>

<span data-ttu-id="559a9-448">För att hjälpa dig att planera migreringen visar tabellen [här](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) instruktioner om när Mass post lådor eller enskilda migreringar ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="559a9-448">To help you plan your migration, the table present [here](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="559a9-449">Dessa uppskattningar baseras på en data analys av tidigare kundmigreringar.</span><span class="sxs-lookup"><span data-stu-id="559a9-449">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="559a9-450">Eftersom alla miljöer är unika kan din exakta migrations hastighet variera.</span><span class="sxs-lookup"><span data-stu-id="559a9-450">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="559a9-451">Kom ihåg att den här funktionen är för närvarande i för hands version och att SLA och eventuella tillämpliga tjänste nivåer inte gäller för prestanda eller tillgänglighet i den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="559a9-451">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="559a9-452">Kända problem</span><span class="sxs-lookup"><span data-stu-id="559a9-452">Known issues</span></span>  

-  <span data-ttu-id="559a9-453">**Problem: det går inte att migrera automatiskt utökade arkiv.**</span><span class="sxs-lookup"><span data-stu-id="559a9-453">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="559a9-454">Överflyttnings funktionen mellan innehavare stöder migrering av den primära post lådan och Arkiv post lådan för en viss användare.</span><span class="sxs-lookup"><span data-stu-id="559a9-454">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="559a9-455">Om användaren i källan har ett automatiskt expanderat Arkiv – d.v.s. mer än en Arkiv post låda kan funktionen inte migrera ytterligare arkiv.</span><span class="sxs-lookup"><span data-stu-id="559a9-455">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="559a9-456">**Problem: Cloud-användare med icke ägda SMTP-proxyAddress blockera MRS flyttar bakgrunden.**</span><span class="sxs-lookup"><span data-stu-id="559a9-456">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="559a9-457">När du skapar användare av mål grupp för användar namn måste du se till att alla SMTP-proxyadresser tillhör organisationen för mål innehavaren.</span><span class="sxs-lookup"><span data-stu-id="559a9-457">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="559a9-458">Om en SMTP-proxyAddress finns på mål-e-postkontot som inte tillhör den lokala klient organisationen förhindras konverteringen av e-postmeddelandet till post låda.</span><span class="sxs-lookup"><span data-stu-id="559a9-458">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="559a9-459">Detta är på grund av vår garanti att Mailbox-objekt endast kan skicka e-post från domäner för vilka klient organisationen är auktoritär (domäner som klienten använder):</span><span class="sxs-lookup"><span data-stu-id="559a9-459">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="559a9-460">När du synkroniserar användare via lokal användning av Azure AD Connect tillhandahåller du lokala mail-objekt med ExternalEmailAddress som pekar på käll klient organisationen där post lådan finns (laran@contoso.onmicrosoft.com) och sedan stämplar PrimarySMTPAddress som en domän som finns i mål klient organisationen (Lara.Newton@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="559a9-460">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="559a9-461">Dessa värden synkroniseras till klient organisationen och en lämplig e-postanvändare tillhandahålls och är klar för migrering.</span><span class="sxs-lookup"><span data-stu-id="559a9-461">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="559a9-462">Ett exempel objekt visas här.</span><span class="sxs-lookup"><span data-stu-id="559a9-462">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="559a9-463">*Contoso.onmicrosoft.com* -adressen finns *inte* i postadresser '/proxyAddresses-matrisen.</span><span class="sxs-lookup"><span data-stu-id="559a9-463">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="559a9-464">**Problem: användar objekt med "externa" primära SMTP-adresser ändras/återställs till "det interna" Företaget begärde domäner**</span><span class="sxs-lookup"><span data-stu-id="559a9-464">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="559a9-465">Postobjekt är pekare till icke-lokala post lådor.</span><span class="sxs-lookup"><span data-stu-id="559a9-465">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="559a9-466">I fråga om migrering av post lådor mellan innehavare använder vi användar objekt för att representera antingen käll post lådan (från mål organisationens perspektiv) eller mål post lådan (från käll organisationens perspektiv).</span><span class="sxs-lookup"><span data-stu-id="559a9-466">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="559a9-467">Mail-användarna får en ExternalEmailAddress (targetAddress) som pekar på SMTP-adressen till den faktiska post lådan (ProxyTest@fabrikam.onmicrosoft.com) och primarySMTP-adressen som representerar den SMTP-adress som står till i e-postlådan i katalogen.</span><span class="sxs-lookup"><span data-stu-id="559a9-467">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="559a9-468">Vissa organisationer väljer att visa den primära SMTP-adressen som en extern SMTP-adress, inte som en adress som ägs/verifieras av den lokala klient organisationen (till exempel fabrikam.com istället för som contoso.com).</span><span class="sxs-lookup"><span data-stu-id="559a9-468">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="559a9-469">När ett Exchange Service plan-objekt tillämpas på en användare via licensierings åtgärder ändras emellertid den primära SMTP-adressen så att den visas som en domän verifierad av den lokala organisationen (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="559a9-469">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="559a9-470">Det finns två möjliga orsaker:</span><span class="sxs-lookup"><span data-stu-id="559a9-470">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="559a9-471">När en Exchange Service-plan tillämpas på en e-användare börjar Azure AD-processen att tvinga fram återskrubbning för att säkerställa att den lokala organisationen inte kan skicka e-post, förfalskningar eller e-post från en annan klient organisation.</span><span class="sxs-lookup"><span data-stu-id="559a9-471">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="559a9-472">Alla SMTP-adresser på ett mottagar objekt med dessa Service planer tas bort om adressen inte verifieras av den lokala organisationen.</span><span class="sxs-lookup"><span data-stu-id="559a9-472">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="559a9-473">Precis som i exemplet är Fabikam.com-domänen inte verifierad av contoso.onmicrosoft.com-klienten, så avrensningen tar bort den fabrikam.com-domänen.</span><span class="sxs-lookup"><span data-stu-id="559a9-473">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="559a9-474">Om du vill behålla de här externa domänerna på en användare, antingen före migreringen eller efter migreringen, måste du ändra migrerings processerna till stripe-licenser efter flytten eller före flytten för att säkerställa att användarna har den förväntade externa märkningen.</span><span class="sxs-lookup"><span data-stu-id="559a9-474">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="559a9-475">Du måste kontrol lera att objektet Mailbox är korrekt licensierat för att inte påverka e-posttjänsten.</span><span class="sxs-lookup"><span data-stu-id="559a9-475">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="559a9-476">Ett exempel skript som används för att ta bort tjänste abonnemangen på en användare i Contoso.onmicrosoft.com-klient organisationen visas här.</span><span class="sxs-lookup"><span data-stu-id="559a9-476">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="559a9-477">Resultat i den uppsättning ServicePlans som har tilldelats visas här.</span><span class="sxs-lookup"><span data-stu-id="559a9-477">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="559a9-478">Användarens PrimarySMTPAddress tas inte längre bort.</span><span class="sxs-lookup"><span data-stu-id="559a9-478">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="559a9-479">Fabrikam.com-domänen ägs inte av contoso.onmicrosoft.com-klienten och kommer att bevaras som den primära SMTP-adressen som visas i katalogen.</span><span class="sxs-lookup"><span data-stu-id="559a9-479">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="559a9-480">Här är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="559a9-480">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="559a9-481">När msExchRemoteRecipientType är inställt på 8 (DeprovisionMailbox) för lokala-användare som migreras till mål klient organisationen tas de icke ägda domänerna bort och återställas till en ägd domän.</span><span class="sxs-lookup"><span data-stu-id="559a9-481">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="559a9-482">Genom att rensa msExchRemoteRecipientType i den lokala postkontot gäller inte den här logiken för skrubbning.</span><span class="sxs-lookup"><span data-stu-id="559a9-482">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="559a9-483">Nedan hittar du alla möjliga service abonnemang som innehåller Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="559a9-483">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="559a9-484">Namn</span><span class="sxs-lookup"><span data-stu-id="559a9-484">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="559a9-485">Avancerade eDiscovery-lagringar (500 GB)</span><span class="sxs-lookup"><span data-stu-id="559a9-485">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="559a9-486">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="559a9-486">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="559a9-487">Dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="559a9-487">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="559a9-488">Exchange Enterprise CAL-tjänster (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="559a9-488">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="559a9-489">Grunderna i Exchange</span><span class="sxs-lookup"><span data-stu-id="559a9-489">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="559a9-490">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="559a9-490">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="559a9-491">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="559a9-491">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="559a9-492">Exchange Online (abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="559a9-492">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="559a9-493">Exchange Online (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="559a9-493">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="559a9-494">Exchange Online-arkivering för Exchange Online</span><span class="sxs-lookup"><span data-stu-id="559a9-494">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="559a9-495">Exchange Online-arkivering för Exchange Server</span><span class="sxs-lookup"><span data-stu-id="559a9-495">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="559a9-496">Inaktive rad Exchange Online-tillägg</span><span class="sxs-lookup"><span data-stu-id="559a9-496">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="559a9-497">Exchange Online-kiosk</span><span class="sxs-lookup"><span data-stu-id="559a9-497">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="559a9-498">Exchange Online multi-geo</span><span class="sxs-lookup"><span data-stu-id="559a9-498">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="559a9-499">Exchange Online-abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="559a9-499">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="559a9-500">POP för Exchange Online</span><span class="sxs-lookup"><span data-stu-id="559a9-500">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="559a9-501">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="559a9-501">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="559a9-502">Informations hinder</span><span class="sxs-lookup"><span data-stu-id="559a9-502">Information Barriers</span></span>                              |
   | <span data-ttu-id="559a9-503">Informations skydd för Office 365 – Premium</span><span class="sxs-lookup"><span data-stu-id="559a9-503">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="559a9-504">Informations skydd för Office 365 – standard</span><span class="sxs-lookup"><span data-stu-id="559a9-504">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="559a9-505">Insikter för analys</span><span class="sxs-lookup"><span data-stu-id="559a9-505">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="559a9-506">Microsoft 365 avancerad granskning</span><span class="sxs-lookup"><span data-stu-id="559a9-506">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="559a9-507">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="559a9-507">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="559a9-508">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="559a9-508">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="559a9-509">Microsoft $ (fullständig)</span><span class="sxs-lookup"><span data-stu-id="559a9-509">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="559a9-510">Avancerad eDiscovery för Office 365</span><span class="sxs-lookup"><span data-stu-id="559a9-510">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="559a9-511">Microsoft Defender för Office 365 (abonnemang 1)</span><span class="sxs-lookup"><span data-stu-id="559a9-511">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="559a9-512">Microsoft Defender för Office 365 (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="559a9-512">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="559a9-513">Office 365 hantering av privilegie rad åtkomst</span><span class="sxs-lookup"><span data-stu-id="559a9-513">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="559a9-514">Premium-kryptering i Office 365</span><span class="sxs-lookup"><span data-stu-id="559a9-514">Premium Encryption in Office 365</span></span>                  |
    
