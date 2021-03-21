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
ms.openlocfilehash: 7c3b4f82d94888cfa6c63b25f20130a38f8b4c9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919206"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Postlådemigrering mellan klientorganisationen (förhandsversion)

Tidigare när en Exchange Online-klientorganisation behövde flytta postlådor till en annan klientorganisation i samma Exchange Online-tjänst behövde de helt ta bort dem lokalt och sedan registrera dem i en ny klientorganisation. Med den nya funktionen för postlådemigrering mellan klientorganisationen kan innehavaradministratörer i både käll- och målklientorganisationen flytta postlådor mellan klientorganisationen med minimala infrastrukturberoenden i sina lokala system. Det här tar bort behovet av postlådor för off-board och onboard.

Ofta vid sammanslagningar eller företag behöver du möjligheten att flytta användare och innehåll till en ny klientorganisation. När målklientorganisationens administratör kör flytten kallas det en pull-flytt, ungefär som migreringar av onboarding i molnet lokalt.

Exchange-postlådeflyttningar mellan klientorganisationen är helt självservice av innehavaradministratörer och använder välkända gränssnitt som kan skriptas i de större arbetsflödena som behövs för att flytta användare till den nya organisationen. Administratörer kan använda `New-MigrationBatch` cmdleten, som är tillgänglig via rollen Flytta postlådor, för att köra flyttningar mellan klientorganisationen. Flyttningsprocessen omfattar autentiseringskontroller av klientorganisationen under synkronisering och slutförande av postlådan. 
 
Användare som migrerar måste finnas i målklientorganisationens Exchange Online-system som MailUsers, markerat med specifika attribut för att aktivera flyttningar mellan klientorganisationen. Systemet kommer att misslyckas för användare som inte är korrekt konfigurerade i målklientorganisationen.  

När flytten är slutförd konverteras källsystempostlådan till MailUser och targetAddress (visas som ExternalEmailAddress i Exchange) stämplas med routningsadressen till målklientorganisationen. Den här processen lämnar den äldre MailUser i källklientorganisationen och möjliggör en viss period av samexisten och e-postdirigering. När affärsprocesser tillåter kan källklientorganisationen ta bort källan MailUser eller konvertera dem till en e-postkontakt. 

Exchange-postlådemigrering mellan klientorganisationen stöds endast för klientorganisationen i hybrid- eller molnet, eller en kombination av dessa.

I den här artikeln beskrivs processen för flytt av postlådor mellan klientorganisationen och innehåller anvisningar om hur du förbereder käll- och målklientorganisationen för innehållsflyttningen.  

## <a name="preparing-source-and-target-tenants"></a>Förbereda käll- och målklientorganisationen

Funktionen för exchange-postlådemigrering med flera innehavare kräver auktorisering och utomfång för migreringar mellan klientorganisationen. Med hjälp av Azure Enterprise-programmet och lagringslösningar för nyckelvalv har nu innehavaradministratörer möjlighet att hantera både auktorisering och utomfång för Exchange Online-postlådemigrering från en klientorganisation till en annan. Postlådeflyttningar mellan klientorganisationen har stöd för en modell för inbjudan och medgivande för att upprätta ett Azure Active Directory-program (Azure AD) som används för autentisering mellan ett klientpar. Ytterligare komponenter, till exempel en organisationsrelation och en migreringsslutpunkt, krävs också.

Det här avsnittet innehåller inte de specifika steg som krävs för att förbereda användarobjekten för MailUser i målkatalogen, och inte heller exempelkommandot för att skicka en migreringsbatch. Mer information [finns i Förbereda målanvändares objekt för](#prepare-target-user-objects-for-migration) migrering.

## <a name="prerequisites"></a>Förutsättningar

Flyttfunktionen för postlådor mellan klientorganisationen kräver [att Azure](/azure/key-vault/basic-concepts) Key Vault skapar ett klientparspecifikt Azure-program för att på ett säkert sätt lagra och få åtkomst till det certifikat/den hemligt som används för att autentisera och auktorisera postlådemigrering från en klientorganisation till en annan, ta bort krav för att dela certifikat/hemligheter mellan klientorganisationen. 

Innan du startar kontrollerar du att du har de behörigheter som krävs för att köra distributionsskripten för att konfigurera Azure-nyckelvalv, programmet Flytta postlåda, EXO-migreringsslutpunkt och EXO-organisationsrelationen. Global administratör har vanligtvis behörighet att utföra alla konfigurationssteg.

Dessutom krävs e-postaktiverade säkerhetsgrupper i källklientorganisationen innan du kör konfigurationen. De här grupperna används för att begränsa listan över postlådor som kan flyttas från källklientorganisationen (eller som ibland kallas för resurs) till målklientorganisationen. På så sätt kan källklientorganisationens administratör begränsa eller begränsa den specifika uppsättning postlådor som måste flyttas, vilket hindrar oavsiktliga användare från att migreras. Kapslade grupper stöds inte.

Du måste också kommunicera med ditt betrodda partnerföretag (som du kommer att flytta postlådor med) för att få deras Klientorganisations-ID för Microsoft 365. Detta klient-ID används i fältet `DomainName` Organisationsrelation.

Om du vill ha klient-ID för en prenumeration loggar du in på administrationscentret för Microsoft 365 och går till [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Klicka på kopieringsikonen för egenskapen Klientorganisations-ID för att kopiera den till Urklipp.

Så här fungerar processen.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Klientförberedelse för postlådemigrering.":::

[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Förbereda klientorganisationen

På en hög nivå sker följande konfigurationsåtgärder när du kör installationsskripten.

Förbereda målklientorganisationen:

1. Om ingen befintlig Azure-resursgrupp tillhandahålls skapas en ny (SCRIPT).
2. Om ett befintligt nyckelvalv inte tillhandahålls skapas ett nytt (SCRIPT).
3. En ny åtkomstprincip skapas för postlådemigreringsprogrammet för Office 365 Exchange Online (SCRIPT).
4. Ett nytt certifikat skapas (eller befintligt, om det anges) som håller hemligheten med migreringsprogrammet (SCRIPT).
5. Ett nytt Azure AD-program skapas (SCRIPT).
6. Certifikatet/hemligheten laddas upp till migreringsprogrammet (SCRIPT).
7. Behörigheter för postlådemigrering tilldelas till programmet (SCRIPT).
8. Distributionsskriptet pausas tills måladministratören har gett sitt eget program (SCRIPT).
9. Målklientorganisationens administratör godkänner de behörigheter som ges till programmet (MANUAL).
10. En organisationsrelation skapas till målklientorganisationen (SCRIPT).
11. En migreringsslutpunkt skapas för att hämta postlådor till målklientorganisationen (SCRIPT).

Förbereda källklientorganisationen:

1. Källklientorganisationens administratör accepterar inbjudan om migrering av postlåda från målklientorganisationen (MANUAL).
2. Källklientorganisationens administratör skapar en e-postaktiverad säkerhetsgrupp i klientorganisationen för att innehålla listan över postlådor som tillåts flyttas av migreringsprogrammet (MANUELL).
3. En organisationsrelation skapas för den målklientorganisation som anger postlådemigreringsprogrammet ska användas för OAuth-verifiering för att acceptera flyttningsbegäran (SCRIPT).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Stegvisa instruktioner för målklientorganisationens administratör

1. Hämta SetupCrossTenantRelationshipForTargetTenant.ps1 för konfigurationen av målklientorganisationen från [GitHub-databasen](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 
2. Spara skriptet (SetupCrossTenantRelationshipForTargetTenant.ps1) på den dator där du ska köra skriptet.
3. Skapa en Fjärranslutning till PowerShell-målklientorganisationen för Exchange Online. Kontrollera att du har de behörigheter som krävs för att köra distributionsskripten för att konfigurera Azure-nyckelvalvens lagring och certifikat, programmet Move Mailbox, EXO-migreringsslutpunkten och EXO-organisationsrelationen.
4. Ändra mappens katalog till skriptplatsen eller kontrollera att skriptet för närvarande sparas på den plats som för närvarande finns i Remote PowerShell-sessionen.
5. Kör skriptet med följande parametrar och värden.

    | Parameter | Value | Obligatorisk eller valfri
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Målklientorganisationens domän, till exempel fabrikam \. onmicrosoft.com. | Obligatoriskt |
    | -ResourceTenantDomain                       | Källklientorganisationens domän, till exempel contoso \. onmicrosoft.com. | Obligatoriskt |
    | -ResourceTenantAdminEmail                   | Källklientorganisationens e-postadress. Det här är källklientorganisationens administratör som godkänner användningen av postlådemigreringsprogrammet som skickas från måladministratören. Det här är administratören som får inbjudan via e-post för programmet. | Obligatoriskt |
    | -ResourceTenantId                           | Organisationens källorganisations-ID (GUID). | Obligatoriskt |
    | -SubscriptionId                             | Den Azure-prenumeration som ska användas för att skapa resurser. | Obligatoriskt |
    | -ResourceGroup                              | Azure-resursgruppnamn som innehåller eller kommer att innehålla nyckelvalvet. | Obligatoriskt |
    | -KeyVaultName                               | Azure-nyckelvalvsinstans där migreringscertifikatet/hemligheten för postlådeprogrammet lagras. | Obligatoriskt |
    | -CertificateName                            | Certifikatnamn när de skapar eller söker efter certifikat i nyckelvalv. | Obligatoriskt |
    | -CertificateSubject                         | Azure Key Vault certificate subject name, such as CN=contoso_fabrikam. | Obligatoriskt |
    | -ExistingApplicationId                      | Migreringsprogram för e-post som ska användas om ett redan har skapats. | Valfritt |
    | -AzureAppPermissions                        | De behörigheter som krävs för postlådemigreringsprogrammet, till exempel Exchange eller MSGraph (Exchange för att flytta postlådor, MSGraph för att använda det här programmet för att skicka en inbjudan med en medgivandelänk till resursklientorganisationen). | Obligatoriskt |
    | -UseAppAndCertGeneratedForSendingInvitation | Parameter för att använda programmet som skapats för migrering för att användas för att skicka inbjudan om en medgivandelänk till källklientorganisationens administratör. Om inte det här visas en uppmaning om att ange måladministratörens autentiseringsuppgifter för att ansluta till Azure Invitation Manager och skicka inbjudan som måladministratör. | Valfritt |
    | -KeyVaultAuditStorageAccountName            | Lagringskontot där nyckelvalvens granskningsloggar lagras. | Valfritt |
    | -KeyVaultAuditStorageResourceGroup          | Resursgruppen som innehåller lagringskontot för lagring av granskningsloggar för nyckelvalv. | Valfritt |
    ||||

    >[!Note]
    > Se till att du har installerat Azure AD PowerShell-modulen innan du kör skripten. Mer information om ![ ](/powershell/azure/install-az-ps?view=azps-5.1.0) installationsannstruktionerna finns här

6. Skriptet pausar och ber dig godkänna eller godkänna Exchange-postlådemigreringsprogrammet som skapades under den här processen. Här är ett exempel.

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

7. En URL visas i Remote PowerShell-sessionen. Kopiera den länk som du fått för klientorganisationens medgivande och klistra in den i en webbläsare.

8. Logga in med dina autentiseringsuppgifter som global administratör. När följande skärm visas väljer du **Acceptera**.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialogrutan Acceptera behörigheter":::

9. Växla tillbaka till Remote PowerShell-sessionen och tryck på Retur för att fortsätta.

10. Skriptet konfigurerar de återstående installationsobjekten. Här är ett exempel.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

Konfigurationen av måladministratören är nu klar!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Stegvisa instruktioner för källklientorganisationens administratör

1.  Logga in på din postlåda som det -ResourceTenantAdminEmail som anges av måladministratören under konfigurationen. Leta reda på e-postinbjudan från målklientorganisationen och välj **sedan knappen Komma** igång.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialogrutan Du har bjudits in":::

2. Välj **Acceptera** för att acceptera inbjudan.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialogruta för att godkänna behörigheter":::

   > [!NOTE]
   > Om du inte får det här e-postmeddelandet eller inte hittar det har målklientorganisationens administratör fått en direkt-URL som du kan få för att acceptera inbjudan. URL-adressen ska i transkriptionen av målklientorganisationens administratörs Fjärr-PowerShell-session.

3. I administrationscentret för Microsoft 365 eller i en fjärrsession i PowerShell skapar du en eller flera e-postaktiverade säkerhetsgrupper för att styra listan över postlådor som tillåts av målklientorganisationen att hämta (flytta) från källklientorganisationen till målklientorganisationen. Du behöver inte fylla i den här gruppen i förväg, men du måste ha minst en grupp för att kunna köra konfigurationsstegen (skript). Kapslade grupper stöds inte. 

4. Ladda SetupCrossTenantRelationshipForResourceTenant.ps1 för källklientorganisationens konfiguration från GitHub-databasen här: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) . 

5. Skapa en Fjärranslutning till PowerShell-källklientorganisationen med dina Exchange-administratörsbehörigheter. Globala administratörsbehörigheter krävs inte för att konfigurera källklientorganisationen, utan endast målklientorganisationen på grund av azure-programskapandeprocessen.

6. Ändra katalog till skriptplatsen eller kontrollera att skriptet för närvarande är sparat på den plats som för närvarande finns i Remote PowerShell-sessionen.

7. Kör skriptet med följande obligatoriska parametrar och värden.

    | Parameter | Value |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | E-postaktiverad säkerhetsgrupp som skapats av källklientorganisationen för identiteter/postlådor som omfattas för migreringen. |
    | -ResourceTenantDomain | Källklientorganisationens domännamn, till exempel contoso \. onmicrosoft.com. |
    | -ApplicationId | Azure-program-ID (GUID) för programmet som användes för migreringen. Program-ID som är tillgängligt via din Azure-portal (Azure AD, Enterprise Applications, appnamn, program-ID) eller som finns i din e-postinbjudan.  |
    | -TargetTenantDomain | Målklientorganisationens domännamn, till exempel fabrikam \. onmicrosoft.com. |
    | -TargetTenantId | Klientorganisations-ID för målklientorganisationen. Till exempel så är Azure AD-klientorganisationens ID för contoso \. onmicrosoft.com klientorganisation. |
    |||

    Här är ett exempel.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

Källadministratörskonfigurationen är nu klar!

### <a name="verify-setup"></a>Verifiera installationen

Kontrollera att organisationsrelationerna i både käll- och målklientorganisationen och migreringsslutpunkten i målet har skapats.

#### <a name="target-tenant"></a>Målklientorganisation

**Organisationsrelation**

Kontrollera att organisationsrelationsobjektet har skapats och konfigurerats med det här kommandot.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Här är ett exempel:

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Migreringsslutpunkt**

Kontrollera att migreringsslutpunktsobjektet har skapats och konfigurerats med det här kommandot.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Här är ett exempel.

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Källklientorganisation

**Organisationsrelation**

Kontrollera att organisationsrelationsobjektet har skapats och konfigurerats med det här kommandot.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

Här är ett exempel.

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a>Verifiera installationsskriptet

Om du får felmeddelanden under konfigurationen av käll- eller målklientorganisationen kan du köra VerifySetup.ps1-skriptet som finns på [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) och granska resultatet.

Här är ett exempel på hur du kör VerifySetup.ps1 på målklientorganisationen:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Här är ett exempel på VerifySetup.ps1 i källklientorganisationen:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Flytta tillbaka postlådor till den ursprungliga källan

Om en postlåda flyttas tillbaka till den ursprungliga källklientorganisationen måste samma uppsättning steg och skript köras i både den nya källklientorganisationen och den nya målklientorganisationen. Det befintliga organisationsrelationsobjektet uppdateras eller läggs till, inte återskapas.

## <a name="prepare-target-user-objects-for-migration"></a>Förbereda målanvändarobjekt för migrering

Användare som migrerar måste finnas i målklientorganisationen och Exchange Online-systemet (som MailUsers) markerade med specifika attribut för att aktivera flyttningar mellan klientorganisationen. Systemet kommer att misslyckas för användare som inte är korrekt konfigurerade i målklientorganisationen. I följande avsnitt finns information om MailUser-objektkraven för målklientorganisationen.

### <a name="prerequisites"></a>Förutsättningar
  
Du måste se till att följande objekt och attribut anges i målorganisationen.  

1. För alla postlådor som flyttas från en källorganisation måste du etablera ett MailUser-objekt i målorganisationen: 

   - Target MailUser måste ha följande attribut från källpostlådan eller ha tilldelats det nya användarobjektet:
      - ExchangeGUID (direktflöde från källa till mål) – postlådans GUID måste matcha. Flyttningsprocessen fortsätter inte om detta inte finns i målobjektet. 
      - ArchiveGUID (direkt flöde från källa till mål) – arkiv-GUID måste matcha. Flyttningsprocessen fortsätter inte om det inte finns i målobjektet. (Detta krävs endast om källpostlådan är aktiverad). 
      - LegacyExchangeDN (flöde som proxyAddress, "x500: ") – LegacyExchangeDN måste finnas på <LegacyExchangeDN> mål-MailUser som x500: proxyAddress. Flyttningsprocesserna fortsätter inte om det inte finns i målobjektet. 
      - UserPrincipalName – UPN justerar användarens NYA identitet eller målföretag (till exempel user@northwindtraders.onmicrosoft.com). 
      - Primary SMTPAddress – Primary SMTP address will align to the user's NEW company (for example, user@northwind.com). 
      - TargetAddress/ExternalEmailAddress – MailUser refererar till användarens aktuella postlåda hos källklientorganisationen (till exempel user@contoso.onmicrosoft.com). När du tilldelar det här värdet ska du kontrollera att du har/även tilldelar PrimarySMTPAddress, annars anges PrimarySMTPAddress som orsakar flyttningsfel. 
      - Du kan inte lägga till äldre smtp-proxyadresser från källpostlådan till MailUser som mål. Du kan till exempel inte underhålla contoso.com på den e-postadress som finns fabrikam.onmicrosoft.com-klientorganisationens objekt). Domäner är kopplade till endast en Azure AD- eller Exchange Online-klientorganisation.
 
     Exempel **på target** MailUser-objekt:
 
     | Attribut             | Value                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                                                                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500:/o=First Organization/ou=Exchange Administrative Group (RÅDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     Exempel **på källpostlådeobjekt:**

     | Attribut             | Value                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - Det kan redan finnas fler attribut i Exchange-hybridskrivning. Om inte bör de inkluderas. 
   - msExchBlockedSendersHash – Skriver tillbaka data om betrodda och spärrade avsändare online från klienter till lokal Active Directory.
   - msExchSafeRecipientsHash – Skriver tillbaka data om betrodda och spärrade avsändare online från klienter till lokala Active Directory.
   - msExchSafeSendersHash – Skriver tillbaka data om betrodda och spärrade avsändare online från klienter till lokala Active Directory.

2. Om källpostlådan finns i LitigationHold och storleken på återställningsbara objekt i källpostlådan är större än databasens standardstorlek (30 GB), går flyttningar inte vidare eftersom målkvoten är mindre än källpostlådans storlek. Du kan uppdatera mailuser-målobjektet för att flytta över ELC-postlådeflaggor från källmiljön till målet, vilket utlöser målsystemet att utöka kvoten för MailUser till 100 GB, vilket gör att flytten till målet tillåts. De här instruktionerna fungerar bara för hybrididentitet som kör Azure AD Connect, eftersom kommandon för att stämpla ELC-flaggor inte exponeras för innehavaradministratörer.

    >[!Note]
    > EXEMPEL – I SIN RÄTT TILL EXEMPEL INGEN GARANTI<br/>Det här skriptet förutsätter en anslutning till både källpostlådan (för att få källvärden) och målet lokalt Active Directory (för att stämpla ADUser-objektet). Om källan har aktiverat återställning av juridiska skäl eller enstaka objekt ska du ange detta i målkontot.  Detta ökar storleken på destinationskontot till 100 GB.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. Icke-hybridmålklienter kan ändra kvoten för mappen Återställningsbara objekt för MailUsers innan migreringen genom att köra följande kommando för att aktivera Bevarande av juridiska skäl i MailUser-objektet och öka kvoten till 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Observera att detta inte fungerar för klientorganisationen i hybriden.

4. Användare i målorganisationen måste vara licensierade med lämpliga Exchange Online-prenumerationer som gäller för organisationen. Du kan använda en licens i förväg för en postlådeflyttning men BARA när målets MailUser är korrekt konfigurerad med ExchangeGUID- och proxyadresser. Om du tillämpar en licens innan ExchangeGUID tillämpas kommer en ny postlåda etableras i målorganisationen. 

    > [!Note]
    > När du använder en licens för ett Mailbox- eller MailUser-objekt rensas alla SMTP-typer proxyAddresses för att säkerställa att endast verifierade domäner ingår i matrisen Exchange EmailAddresses. 

5. Du måste säkerställa att målets MailUser inte har någon tidigare ExchangeGuid som inte matchar Source ExchangeGuid. Det här kan inträffa om mål-e-postinnehavaren tidigare har licensierats för Exchange Online och etablerat en postlåda. Om målet MailUser tidigare har licensieras för eller hade en ExchangeGuid som inte matchar Source ExchangeGuid måste du rensa den molnbaserade e-postanvändaren. Du kan köra för de här molnbaserade e-moln-e-molnanvändarna. `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`  

    > [!Caution]
    > Den här processen är bestående. Om objektet har en softDeleted-postlåda går det inte att återställa det efter den här punkten. När du rensat kan du synkronisera rätt ExchangeGuid till målobjektet, och MRS ansluter källpostlådan till den nya målpostlådan. (Referens EHLO-bloggen om den nya parametern.)  

    Hitta objekt som tidigare var postlådor med det här kommandot.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    Här är ett exempel. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    Rensa den mjukt borttagna postlådan med det här kommandot.

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    Här är ett exempel.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a>Utföra postlådemigrering

Exchange-postlådemigrering mellan klientorganisationen skickas som migreringsbatchar initierade från målklientorganisationen. Det här liknar det sätt som migreringsbatcharna på plats fungerar när du migrerar från Exchange lokalt till Microsoft 365. 

### <a name="create-migration-batches"></a>Skapa migreringsbatchar

Här är ett exempel på cmdlet för migreringsbatch för att starta flyttningar.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> E-postadressen i CSV-filen måste vara den som anges i målklientorganisationen, inte källklientorganisationen.

Inskickning av migreringsbatch stöds också från det nya administrationscentret för Exchange när du väljer alternativet för flera innehavare.

#### <a name="update-on-premises-mailusers"></a>Uppdatera lokala MailUsers

När postlådan flyttas från källa till mål bör du se till att de lokala e-postanvändarna, både käll- och målanvändare, uppdateras med den nya targetAddress. I exemplen är targetDeliveryDomain som används i flyttningen **contoso.onmicrosoft.com.** Uppdatera e-postanvändarna med denna targetAddress.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

**Behöver vi uppdatera RemoteMailboxes lokalt i källan efter flytten?**

Ja, du bör uppdatera targetAddress (RemoteRoutingAddress/ExternalEmailAddress) för den lokala källans användare när källklientorganisationens postlåda flyttas till målklientorganisationen.  Även om e-postdirigering kan följa referenserna för flera e-postanvändare med olika targetAddresses måste uppslag för ledig/upptagen för e-postanvändare vara rätt mål för postlådans användare. Uppslag av ledig/upptagen-information duar inte efter flera omdirigeringar. 

**Migrerar innehållet i chattmappen i Teams mellan klientorganisationen?**  

Nej, innehållet i chattmappen i Teams migreras inte mellan klientorganisationen.  

**Hur kan jag se flyttningar mellan klientorganisationen, inte flyttningar av registrering och off-boarding?**

Använd `-flags` parametern. Här är ett exempel.

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**Kan du ange exempelskript för kopiering av attribut som används vid testning?**

> [!Note]
> EXEMPEL – I SIN RÄTT TILL EXEMPEL INGEN GARANTI<br/>Det här skriptet förutsätter en anslutning till både källpostlådan (för att få källvärden) och målet lokalt Active Directory Domain Services (för att stämpla ADUser-objektet). Om källan har aktiverat återställning av juridiska skäl eller enstaka objekt ska du ange detta i målkontot.  Detta ökar storleken på destinationskontot till 100 GB.

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
**Hur kommer vi åt Outlook på dag 1 när postlådan har flyttats?**

Eftersom endast en klientorganisation kan äga en domän kommer den tidigare primära SMTPAddressen inte att kopplas till användaren i målklientorganisationen när postlådeflyttningen har slutförts. endast de domäner som är kopplade till den nya klientorganisationen. Outlook använder användarnas nya UPN för att autentisera i tjänsten, och Outlook-profilen förväntar sig att hitta den äldre primära SMTPAddress för att matcha postlådan i målsystemet. Eftersom den äldre adressen inte finns i målets system kan inte Outlook-profilen ansluta för att hitta den flyttade postlådan. 

För den här första distributionen måste användarna återskapa sin profil med sin nya UPN,primära SMTP-adress och synkronisera OST-innehåll igen. 

> [!Note]
> Planera enligt detta när du grupperar användarna så att de kan slutföras. Du måste ta hänsyn till nätverksanvändningen och kapaciteten när Outlook-klientprofiler skapas och efterföljande OST- och OAB-filer laddas ned till klienter. 
 
**Vilka Exchange RBAC-roller behöver jag vara medlem i för att konfigurera eller slutföra en flytt mellan klientorganisationen?**
 
Det finns en matris med roller utifrån antagandet om delegerade uppgifter vid körning av postlådeflyttning. För närvarande krävs två roller:  

- Den första rollen är för en 1:a konfigurationsaktivitet som upprättar auktoriseringen för att flytta innehåll till eller från organisationens klientorganisations-/organisationsgräns. Eftersom flytten av data från organisationens kontroll är ett viktigt problem för alla företag har vi valt den högsta tilldelade rollen som organisationsadministratör (OrgAdmin). Den här rollen måste ändra eller konfigurera en ny OrganizationRelationship som definierar -MailboxMoveCapability med den fjärranslutna organisationen. Endast OrgAdmin kan ändra inställningen MailboxMoveCapability, medan andra attribut i OrganizationRelationhip kan hanteras av administratören för federerad delning. 
 
- Rollen för att köra de faktiska flyttningskommandona kan delegeras till en lägre nivå-funktion. Rollen för Flytta postlådor tilldelas möjligheten att flytta postlådor till eller från organisationen med hjälp av `-RemoteTenant` parametern.  

**Hur riktar vi den SMTP-adress som valts för targetAddress (TargetDeliveryDomain) på den konverterade postlådan (till MailUser-konvertering)?**
 
Exchange-postlådeflyttningar med MRS-skick av måladressen på den ursprungliga källpostlådan när du konverterar till en MailUser genom att matcha en e-postadress (proxyAddress) på målobjektet. Processen tar värdet -TargetDeliveryDomain som skickas till flyttningskommandot och söker sedan efter en matchande proxy för den domänen på målsidan. När vi hittar en matchning används den matchande proxyAdressen till att ange ExternalEmailAddress (targetAddress) på den konverterade postlådan (nu MailUser) objektet.
 
**Hur går postlådebehörigheter över?**

Postlådebehörigheter omfattar Skicka för och Postlådeåtkomst: 

- I Skicka för (AD:publicDelegates) lagras DN för mottagare med åtkomst till en användares postlåda som ombud. Det här värdet lagras i Active Directory och flyttas för närvarande inte som en del av postlådeövergången. Om källpostlådan har angetts med offentligDelegerat måste du skapa en ombyggnad av den offentligaDelegeringen på målpostlådan när konverteringen av e-postlådor har slutförts i målmiljön genom att köra `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` . 
 
- Postlådebehörigheter som lagras i postlådan flyttas med postlådan när både huvudmannen och ombudet flyttas till målsystemet. Till exempel tilldelas användaren TestUser_7 FullAccess till postlådan i TestUser_8 i SourceCompany.onmicrosoft.com. När postlådeflyttningen har TargetCompany.onmicrosoft.com postlådeflyttningen konfigureras samma behörigheter i målkatalogen. Exempel med *Get-MailboxPermission* för TestUser_7 i både käll- och målklientorganisationen visas nedan. Exchange-cmdlets föregås av käll- och måldata i enlighet med detta. 
 
Här är ett exempel på utdata för postlådebehörigheten före flytten. 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Här är ett exempel på utdata för postlådebehörigheten efter flytten. 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Behörigheter för postlådor och kalendrar mellan klientorganisationen stöds INTE. Du måste organisera huvudnamn och ombud i konsoliderade flyttbatchar så att dessa anslutna postlådor flyttas samtidigt från källklientorganisationen. 

**Vilken X500-proxy ska läggas till i mål-MailUser-proxyadresserna för att aktivera migrering?**  

Postlådemigrering mellan klientorganisationen kräver att LegacyExchangeDN-värdet för källpostlådeobjektet stämplas som en x500-e-postadress på målets MailUser-objekt.  

Exempel:  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> Utöver den här X500-proxyn måste du kopiera alla X500-proxyservrar från postlådan i källan till postlådan i målet.  

**Var ska jag börja felsöka om flyttningar inte fungerar?**  

Börja med att VerifySetup.ps1 skriptet som [finns på GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) och granska resultatet.

Här är ett exempel på hur du kör VerifySetup.ps1 på målklientorganisationen:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Här är ett exempel på ett VerifySetup.ps1 på källklientorganisationen:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**Kan käll- och målklientorganisationen använda samma domännamn?**  

Nej. Domännamnen för käll- och målklientorganisationen måste vara unika. En källdomän av contoso.com och måldomänen för fourthcoffee.com.

**Kommer delade postlådor att flyttas och fungerar fortfarande?**

Ja, men vi behåller bara lagringsbehörigheterna enligt beskrivningen i följande artiklar:

- [Microsoft Docs | Hantera behörigheter för mottagare i Exchange Online](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Microsoft Support | Så här beviljar du behörigheter för Exchange- och Outlook-postlådor i dedikerade Office 365](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**Krävs Azure-nyckelvalv och när görs transaktioner?**  

Ja, en Azure-prenumeration krävs för att använda nyckelvalv för att lagra certifikatet för att auktorisera migreringen. Till skillnad från onboarding-migreringar där användarnamn och lösenord & används för autentisering för källan används OAuth och det här certifikatet som hemliga/autentiseringsuppgifter för flera klientorganisationens postlådemigreringar. Åtkomst till nyckelvalvet måste bibehållas under alla postlådemigreringar eftersom det används en gång i början och en gång i slutet av migreringen, samt en gång var 24:e timme under stegvis synkronisering. Du kan granska kostnadsinformation för AKV [här]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).  

**Har du några rekommendationer för batchar?**  

Överstig inte 2 000 postlådor per batch. Vi rekommenderar att du skickar in batchar två veckor före brytdatumet eftersom det inte påverkar slutanvändarna under synkroniseringen. Om du behöver vägledning för postlådemängder över 50 000 kan du kontakta distributionslistan för teknisk feedback crosstenantmigrationpreview@service.microsoft.com.

**Vad händer om jag använder tjänstkryptering med kundnyckel?**

Postlådan dekrypteras innan du flyttar den. Se till att kundnyckeln är konfigurerad i målklientorganisationen om den fortfarande krävs. Mer [](../compliance/customer-key-overview.md) information finns här.  

**Vilken migreringstid beräknas?**

I tabellen som finns här [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) visas riktlinjer för när du kan förvänta dig att masspostlådemigrering eller enskilda migreringar ska slutföras för att hjälpa dig planera migreringen. De här uppskattningarna baseras på en dataanalys av tidigare kundmigreringar. Eftersom varje miljö är unik kan den exakta migreringshastigheten variera.  

Kom ihåg att den här funktionen är i förhandsversion och SLA och alla tillämpliga tjänstnivåer gäller inte för några prestanda- eller tillgänglighetsproblem under förhandsgranskningsstatusen för den här funktionen.

## <a name="known-issues"></a>Kända problem  

-  **Problem: Automatiskt utökade arkiv kan inte migreras.** Funktionen för migrering mellan klientorganisationen har stöd för migreringar av den primära postlådan och arkivpostlådan för en viss användare. Om användaren i källan däremot har ett automatiskt expanderat arkiv, vilket innebär fler än en arkivpostlåda, kan funktionen inte migrera de extra arkiven och bör misslyckas.

- **Problem: Cloud MailUsers med icke-ägd smtp-proxyAddress-block MRS flyttar bakgrunden.** När du skapar MailUser-objekt för målklientorganisationen måste du se till att alla SMTP-proxyadresser tillhör målklientorganisationen. Om det finns en SMTP-proxyAddress på målanvändaren för e-post som inte tillhör den lokala klientorganisationen förhindras konverteringen av MailUser till Mailbox. Detta beror på vår garanti för att postlådeobjekt bara kan skicka e-post från domäner där klientorganisationen är auktoritativ (domäner som anspråksklienten gör anspråk på): 

   - När du synkroniserar användare från den lokala platsen med Azure AD Connect etablerar du lokala MailUser-objekt med ExternalEmailAddress som pekar på källklientorganisationen där postlådan finns (laran@contoso.onmicrosoft.com) och du stämplar PrimarySMTPAddress som en domän som finns i målklientorganisationen (Lara.Newton@northwind.com). De här värdena synkroniseras ned till klientorganisationen och en lämplig e-postanvändare har etablerats och är redo för migrering. Här visas ett exempelobjekt.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > Fältet *contoso.onmicrosoft.com* finns *inte i* matrisen E-postadresser/proxyAddresses.

- **Problem: MailUser-objekt med "externa" primära SMTP-adresser ändras /återställs till "interna" företagsdrekuterade domäner**

   MailUser-objekt är pekare till icke-lokala postlådor. För postlådemigrering mellan klientorganisationen använder vi MailUser-objekt för att representera antingen källpostlådan (från målorganisationens perspektiv) eller målpostlådan (från källorganisationens perspektiv). MailUsers har en ExternalEmailAddress (targetAddress) som pekar på smtp-adressen för den faktiska postlådan (ProxyTest@fabrikam.onmicrosoft.com) och primarySMTP-adressen som representerar den SMTP-adress som visas för postlådeanvändaren i katalogen. Vissa organisationer väljer att visa den primära SMTP-adressen som en extern SMTP-adress, inte som en adress som ägs/verifieras av den lokala klientorganisationen (till exempel fabrikam.com i stället för som contoso.com).  När ett Objekt i en Exchange-tjänstplan tillämpas på MailUser via licensåtgärder ändras dock den primära SMTP-adressen så att den visas som en domän som verifierats av den lokala organisationen (contoso.com). Det finns två möjliga orsaker:
   
   - När ett Exchange-tjänstabonnemang tillämpas på en MailUser börjar Azure AD-processen att framtvinga proxyskrubbning för att säkerställa att den lokala organisationen inte kan skicka e-post, förfalskning eller e-post från en annan klientorganisation. Alla SMTP-adresser på ett mottagarobjekt med dessa tjänstplaner tas bort om adressen inte verifieras av den lokala organisationen. Som i exemplet har Fabikam.com INTE verifierats av contoso.onmicrosoft.com-klientorganisationen, så skrubbningen tar bort det fabrikam.com domänen. Om du vill bevara dessa externa domäner på MailUser, antingen före migreringen eller efter migreringen, måste du ändra dina migreringsprocesser för att ta bort licenser efter flytten eller innan flytten för att säkerställa att användarna har den förväntade externa varumärkeskopplingen. Du måste se till att postlådeobjektet är korrekt licensierat för att inte påverka e-posttjänsten.<br/><br/>Ett exempelskript för att ta bort tjänstplaner på en MailUser i Contoso.onmicrosoft.com klientorganisationen visas här.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Resultatet för uppsättningen serviceplaner som har tilldelats visas här.

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
 
       Användarens PrimarySMTPAddress är inte längre rensad. Domänen fabrikam.com inte ägs av contoso.onmicrosoft.com klientorganisationen och finns kvar som den primära SMTP-adressen som visas i katalogen.

       Här är ett exempel.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - När msExchRemoteRecipientType är inställt på 8 (DeprovisionMailbox), kommer den lokala MailUsers som migreras till målklientorganisationen att ta bort icke-tillhörda domäner och återställa primarySMTP till en ägd domän. Genom att rensa msExchRemoteRecipientType i den lokala MailUser tillämpas inte längre proxy-scrub-logiken. <br/><br>Nedan visas alla möjliga tjänstplaner med Exchange Online.

   | Namn                                              |
   |---------------------------------------------------|
   | Advanced eDiscovery Storage (500 GB)               |
   | Customer Lockbox                                  |
   | Dataförlustskydd                              |
   | Exchange Enterprise CAL Services (EOP, DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (abonnemang 1)                          |
   | Exchange Online (abonnemang 2)                          |
   | Exchange Online – arkivering för Exchange Online     |
   | Exchange Online - arkivering för Exchange Server     |
   | Inaktivt användar tillägg för Exchange Online              |
   | Exchange Online Kiosk                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online-abonnemang 1                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | Informationsbarriärer                              |
   | Informationsskydd för Office 365 – Premium   |
   | Informationsskydd för Office 365 – Standard  |
   | Insights från MyAnalytics                           |
   | Avancerad granskning i Microsoft 365                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (fullständiga)                      |
   | Avancerad eDiscovery för Office 365                    |
   | Microsoft Defender för Office 365 (abonnemang 1)    |
   | Microsoft Defender för Office 365 (abonnemang 2)    |
   | Hantering av behörighet i Office 365           |
   | Premiumkryptering i Office 365                  |
