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
ms.openlocfilehash: 1e2624fea7a93013e4b4de2dd4ede4144000f075
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073089"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Migrera mellan innehavare (för hands version)

Tidigare, när en Exchange Online-klient måste flytta post lådor till en annan klient organisation i samma Exchange Online-tjänst, måste de helt ta bort dem på lokal och sedan vara inloggade på en ny klient organisation. Med den nya Överflyttnings funktionen för post lådor för flera innehavare kan klient organisationer i både käll-och mål klient organisationer flytta post lådor mellan klient organisationerna och deras lokala system. Detta tar bort behovet av ta bort och inbyggda post lådor.

Vanligt vis kan du med att flytta användare och innehåll till en ny klient organisation under fusioner och divestitures. När mål gruppens administratör utför flytten kallas det för pull-Move, som liknar lokal distribution med lokala Cloud-migreringar.

Exchange-postlådor för utbyte av flera innehavare är helt självbetjänings fria från klient organisationer, med välkända gränssnitt som kan följa skript i de större arbets flöden som behövs för att överföra användare till deras nya organisation. Administratörer kan använda `New-MigrationBatch` cmdleten som är tillgänglig via hanterings rollen flytta post lådor för att utföra flytt av klient organisationer. Flyttnings processen inkluderar kontroll av klient organisationens verifiering under synkronisering och avslut. 
 
Användare som migreras måste finnas i mål klient organisationens Exchange Online-system som användare med specifika attribut för att aktivera kors klient organisationer. Systemet kommer inte att flyttas för användare som inte har kon figurer ATS korrekt i mål klient organisationen. 

När flyttningarna är slutförda konverteras post lådan till Mail-användare och targetAddress (visas som ExternalEmailAddress i Exchange) med Dirigerings adressen till destinations innehavaren. Den här processen lämnar den gamla e-postkontot i källans klient organisation och möjliggör en period med samtidig existens och e-postdirigering. När affärs processer tillåts kan käll klient organisationen ta bort käll-mail-användaren eller konvertera dem till en e-postkontakt. 

Migrering för Exchange-postlåda med flera innehavare stöds endast för klient organisationer i hybrid-eller moln syfte, eller någon kombination av båda.

I den här artikeln beskrivs processen för flytt av post lådor mellan innehavare och vägledning för hur du förbereder käll-och mål klienter för innehållet. 

## <a name="preparing-source-and-target-tenants"></a>Förbereda käll-och mål klient organisationer

Migreringsguiden för Exchange-postlådan för flera innehavare kräver auktorisering och omfattning för migrering mellan innehavare. Genom att använda Azure Enterprise-programmet och viktiga valv lagrings lösningarna kan klient administratörer hantera både auktorisering och omfångst av Exchange Online Mailbox-migreringar från en klient organisation till en annan. Post låda för flera innehavare flyttar stöd för en inbjudan och en tillstånds modell för att upprätta ett Azure Active Directory-program som används för att verifiera ett klient par. Ytterligare komponenter som organisations relationer och slut punkt för migrering krävs också.

I det här avsnittet ingår inte de steg som krävs för att förbereda användar objekt i gruppen användare i mål katalogen, eller så inkluderar det inte kommandot exempel för att skicka in en migreringstabell. Se [förbereda mål användar objekt för migrering](#prepare-target-user-objects-for-migration) för den här informationen.

## <a name="prerequisites"></a>Förutsättningar

För funktionen för flytt av post lådor krävs ett [Azure-valv](https://docs.microsoft.com/azure/key-vault/basic-concepts) för att upprätta ett klient organisations par-specifika Azure-program för säker lagring och åtkomst till certifikatet/hemligheten som används för att autentisera och auktorisera post lådans migrering från en klient organisation till den andra, vilket tar bort alla krav för att dela certifikat/hemligheter mellan klient organisationer. 

Innan du börjar bör du kontrol lera att du har nödvändig behörighet för att köra distributions skripten för att kunna konfigurera Azure Key Vault, flytta program varan för EXO, slut punkt för migrering och EXO organisations relation. Vanligt vis har global administratör behörighet att utföra alla konfigurations steg.

Dessutom krävs e-postaktiverade säkerhets grupper i käll klient organisationen innan installationen körs. Dessa grupper används för att scope listan med post lådor som kan flyttas från källan (eller ibland kallas resurs) för klient organisationen till mål innehavaren. Detta gör att du kan använda administratörs administratören för att begränsa eller ange omfattningen av de post lådor som måste flyttas för att förhindra att oavsiktliga användare migreras. Kapslade grupper stöds inte.

Du måste också kommunicera med ditt betrodda partner företag (du kommer att flytta brev lådor) för att få sitt Microsoft 365-klient-ID. Detta klient-ID används i fältet organisations relation `DomainName` .

Om du vill skaffa klient organisationens ID för ett abonnemang loggar du in i administrations centret för Microsoft 365 och går till [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Klicka på ikonen Kopiera för egenskapen innehavaradministration för att kopiera den till Urklipp.

Så här fungerar processen.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Förberedelse av klient organisation för migrering av post låda.":::

[Visa en större version av bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Förbereda klient organisationer

På en hög nivå utförs följande konfigurations åtgärder när du kör installations skripten.

Förbereda mål klient organisationen:

1. Om det inte finns någon befintlig Azure-gruppgrupp skapas en ny (skript).
2. Om det inte finns något befintligt huvud valv skapas ett nytt (skript).
3. En ny åtkomst policy skapas för Office 365 Exchange Online Mailbox migration-programmet (skript).
4. Ett nytt certifikat skapas (eller används för det) för att hålla hemligheten till migreringsarkivet (skript).
5. Ett nytt Azure AD-program skapas (skript).
6. Certifikatet/hemligheten laddas upp till migreringsarkivet (skript).
7. Överflyttnings behörigheter för post lådor är tilldelade till programmet (skript).
8. Distributions skriptet pausas tills mål administratören samtycker till deras egna program (skript).
9. Mål organisationens administratör samtycker till de behörigheter som givits till programmet (MANUAL).
10. En organisations relation skapas till mål klient organisationen (skript).
11. En slut punkt för migrering skapas för att hämta post lådor till mål klient organisationen (skript).

Förbereda käll klient organisationen:

1. Klient organisationens administratör accepterar godkännande från mål klient organisationen (MANUAL) för migrering av postinbjudan.
2. Klient organisationens administratör skapar en e-postaktive rad säkerhets grupp i sin klient organisation som innehåller listan över post lådor som ska kunna flyttas av migreringsarkivet (manuellt).
3. En organisations relation skapas till mål innehavaren som anger att programmet för postmigrering ska användas för OAuth-verifiering för att acceptera flytt förfrågan (skript).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Steg-för-steg-instruktioner för mål gruppens administratör

1. Ladda ned SetupCrossTenantRelationshipForTargetTenant.ps1-skript för mål klient organisationens konfiguration från [GitHub-databasen](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 
2. Spara skriptet (SetupCrossTenantRelationshipForTargetTenant.ps1) till den dator som du ska köra skriptet från.
3. Skapa en fjärran sluten PowerShell-anslutning till Exchange Online-måldomänkontrollanten. Kontrol lera igen att du har nödvändig behörighet för att köra distributions skripten för att kunna konfigurera lagring och certifikat för Azure Key Vault, flytta program varan för migrering, EXO och EXO organisations relation.
4. Ändra katalogen för filmapp till skript platsen eller kontrol lera att skriptet är sparat på platsen som för närvarande är en fjärr-PowerShell-session.
5. Kör skriptet med följande parametrar och värden.

    | Indataparametern | Värde | Obligatoriskt eller valfritt
    |---------------------------------------------|-----------------|--------------|
    | -ResourceTenantDomain                       | Käll klient organisation, till exempel Fabrikam \. onmicrosoft.com. | Obligatoriskt |
    | -ResourceTenantAdminEmail                   | Källa för klient organisationens e-postadress. Det här är käll klientens administratör som kommer att skickas vidare till den som skickas från mål administratören. Det här är administratören som kommer att få e-postinbjudan för programmet. | Obligatoriskt |
    | -TargetTenantDomain                         | Mål grupps domän, till exempel contoso \. onmicrosoft.com. | Obligatoriskt |
    | -ResourceTenantId                           | Organisations-ID för käll innehavare (GUID). | Obligatoriskt |
    | -SubscriptionId                             | Azure-abonnemanget som används för att skapa resurser. | Obligatoriskt |
    | -ResourceGroup                              | Namnet på Azure Resource-gruppen som innehåller eller kommer att innehålla huvud-valvet. | Obligatoriskt |
    | -KeyVaultName                               | Azure Key Vault-instans som lagrar certifikatet/hemligheten för post lådan. | Obligatoriskt |
    | -CertificateName                            | Certifikat namn när du skapar eller söker efter certifikat i Key Vault. | Obligatoriskt |
    | -CertificateSubject                         | Namn på certifikat för Azure Key valv, till exempel CN = contoso_fabrikam. | Obligatoriskt |
    | -ExistingApplicationId                      | E-postmigrering som ska användas om en redan har skapats. | Valfritt |
    | -AzureAppPermissions                        | De behörigheter som krävs för att få åtkomst till migreringsarkivet-programmet, till exempel Exchange eller MSGraph (Exchange för att flytta post lådor, MSGraph för att använda detta program för att skicka en inbjudan till resurs innehavaren av programmet. | Obligatoriskt |
    | -UseAppAndCertGeneratedForSendingInvitation | Parameter för användning av det program som har skapats för migrering för att skicka inbjudan om godkännande länk till source innehavaradministratörer-administratör. Om det inte visas uppmanas du att ange inloggnings uppgifter för att ansluta till Azure Inbjudnings hanteraren och skicka inbjudan som mål administratör. | Valfritt |
    | -KeyVaultAuditStorageAccountName            | Lagrings kontot där viktiga Valvs gransknings loggar lagras. | Valfritt |
    | -KeyVaultAuditStorageResourceGroup          | Resurs gruppen som innehåller lagrings kontot för att spara gransknings loggar för Key valv. | Valfritt |
    ||||

6. Skriptet pausas och du uppmanas att acceptera eller godkänna det migreringsåtgärder för Exchange-postprogrammet som skapades under processen. Här är ett exempel.

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. En URL-adress kommer att visas i fjärrsessionen. Kopiera länken som tillhandahålls för innehavarens medgivande och klistra in den i en webbläsare.

8. Logga in med dina autentiseringsuppgifter för din globala administratör. När följande skärm visas väljer du **acceptera**.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialog rutan Godkänn behörigheter":::
    
9. Gå tillbaka till fjärrsessionen för PowerShell och Fortsätt genom att trycka på RETUR.

10. Skriptet konfigurerar de återstående installations objekt. Här är ett exempel.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

Konfigurationen för mål administratören är nu klar!

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Stegvisa anvisningar för käll klient organisationens administratör

1.  Logga in på din post låda som den-ResourceTenantAdminEmail som anges av mål administratören under installationen. Sök efter e-postinbjudan från mål innehavaren och välj sedan knappen **Kom igång** .

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialog rutan har blivit inbjuden":::

2. Välj **acceptera** för att acceptera inbjudan.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialog ruta för att godkänna behörigheter":::

   > [!NOTE]
   > Om du inte får det här e-postmeddelandet eller inte kan hitta det, har mål organisationens administratör en direkt URL som kan tilldelas dig för att acceptera inbjudan. URL: en ska i avskriften för klient organisationens fjärradministratörs fjärrsession.

3. I administrations centret för Microsoft 365 eller en fjärr-PowerShell-session skapar du en eller flera e-postaktiverade säkerhets grupper för att kontrol lera listan med post lådor som tillåts av mål klient organisationen för att ta bort (flytta) från käll klient organisationen till mål klient organisationen. Du behöver inte fylla i den här gruppen i förväg, men minst en grupp måste tillhandahållas för att köra konfigurations stegen (skript). Kapslade grupper stöds inte. 

4. Ladda ned SetupCrossTenantRelationshipForTargetResource.ps1-skript för käll klient organisations konfiguration från GitHub-databasen [här](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 

5. Skapa en fjärran sluten PowerShell-anslutning till käll klient organisationen med administratörs behörigheter för Exchange. Den globala administratörs behörighet krävs inte för att konfigurera käll klient organisationen, bara mål innehavaren på grund av processen att skapa Azure-program.

6. Byt katalog till skript platsen eller kontrol lera att skriptet för närvarande är sparat på platsen som för närvarande är en fjärr-PowerShell-session.

7. Kör skriptet med följande obligatoriska parametrar och värden.

    | Indataparametern | Värde |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | E-postaktive rad säkerhets grupp skapad av käll klient organisationen för de identiteter/post lådor som är i omfång för migrering. |
    | -ResourceTenantDomain | Käll klient namn för källan, till exempel Fabrikam \. onmicrosoft.com. |
    | -TargetTenantDomain | Mål gruppens domän namn, till exempel contoso \. onmicrosoft.com. |
    | -ApplicationId | ID för Azure-programmet (GUID) för programmet som används för migrering. Program-ID tillgängligt via din Azure-Portal (Azure AD, Enterprise-program, program namn, program-ID) eller inkluderat i e-postinbjudan.  |
    | -TargetTenantId | Innehavarens ID för mål innehavaren. Till exempel Azure AD-klient organisations-ID: t contoso \. onmicrosoft.com-klienten. |
    |||
    
    Här är ett exempel.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

Konfiguration av käll administratör är nu klar!

### <a name="verify-setup"></a>Verifiera inställningar

Kontrol lera att organisations relationerna i både käll-och mål klient organisationer och slut punkt för migrering i målet har skapats.

#### <a name="target-tenant"></a>Mål klient organisation

**Organisations relation**

Kontrol lera att du har skapat och konfigurerat organisations Relations objekt med det här kommandot.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Här är ett exempel:

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Slut punkt för migrering**

Kontrol lera att migrerings slut punkten skapades och konfigurerades med det här kommandot.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Här är ett exempel.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Käll klient organisation

**Organisations relation**

Kontrol lera att du har skapat och konfigurerat organisations Relations objekt med det här kommandot.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
Här är ett exempel.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Flytta tillbaka post lådorna till den ursprungliga källan

Om en post låda flyttas tillbaka till den ursprungliga käll klient organisationen krävs samma uppsättning steg och skript i både ny källa och nya mål klienter. Befintligt organisations Relations objekt uppdateras eller läggs till, inte återskapas.

## <a name="prepare-target-user-objects-for-migration"></a>Förbereda mål användar objekt för migrering

Användare som migreras måste finnas i mål klient organisationen och Exchange Online-systemet (som återanvändare) markeras med specifika attribut för att aktivera kors klient organisationer. Systemet kommer inte att flyttas för användare som inte har kon figurer ATS korrekt i mål klient organisationen. I följande avsnitt beskrivs användar objekts kraven för mål klient organisationen.

### <a name="prerequisites"></a>Förutsättningar
  
Du måste kontrol lera att följande objekt och attribut är inställda i mål organisationen.  

1. För alla post lådor som flyttas från en käll organisation måste du tillhandahålla ett e-postobjekt i mål organisationen: 
   - Mål-e-postkontot måste ha följande attribut från käll post lådan eller tilldelat det nya användarobjektet:
      - ExchangeGUID (direkt flöde från källa till mål) – post lådans GUID måste stämma. Flyttningen går inte att genomföra om det inte finns någon på målobjektet. 
      - ArchiveGUID (direkt flöde från källa till mål) – Arkiv-GUID måste stämma. Flyttningen går inte att genomföra om det inte finns något på målobjektet. (Detta krävs endast om käll brev lådan är aktive rad. 
      - LegacyExchangeDN (flöde som proxyAddress, "x500: <LegacyExchangeDN> ") – LegacyExchangeDN måste finnas på mål gruppen. Det går inte att gå vidare om det inte finns något på målobjektet. 
      - UserPrincipalName – UPN kommer att justera till användarens nya identitet eller mål bolag (till exempel user@northwindtraders.onmicrosoft.com). 
      - Primär SMTPAddress – primär SMTP-adress kommer att justeras efter användarens nya företag (till exempel user@northwind.com). 
      - TargetAddress/ExternalEmailAddress – Mail-användare hänvisar till användarens aktuella post låda i käll klient organisationen (till exempel user@contoso.onmicrosoft.com). När du tilldelar det här värdet bör du kontrol lera att du har/tilldelar PrimarySMTPAddress eller det här värdet ställer in PrimarySMTPAddress som orsakar ett flytt problem. 
      - Du kan inte lägga till gamla SMTP-proxyadresser från käll brev lådan till mål-och e-postanvändare. Du kan till exempel inte underhålla contoso.com på POSTAKTIVERADE användaren i fabrikam.onmicrosoft.com klient organisations objekt). Domäner är kopplade till bara en Azure AD-eller Exchange Online-klient organisation.
 
    Exempel på **mål** användar objekt:
 
    | Attribut             | Värde                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | Standardaliasuppsättning                 | LaraN                                                                                                                    |
    | RecipientType         | Användare                                                                                                                 |
    | En  | Användare                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders \. onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Lara \. Newton@northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP: LaraN@contoso \. onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o = första organisation/ou = Exchange administrativ grupp                                                                   |
    |                       | (FYDIBOHF23SPDLT)/CN = mottagare/CN = 74e5385fce4b46d19006876949855035Lara                                                  |
    | Postadresser '        | x500:/o = First organisation/ou = Exchange Administrative Group (FYDIBOHF23SPDLT)/CN = mottagare/CN = d11ec1a2cacd4f81858c8190  |
    |                       | 7273f1f9-Lara                                                                                                            |
    |                       | SMTP: LaraN@northwindtraders \. onmicrosoft.com                                                                              |
    |                       | SMTP: Lara \. Newton@northwind.com                                                                                           |
    |||

   Exempel på **käll** post låda:

   | Attribut             | Värde                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | Standardaliasuppsättning                 | LaraN                                                                    |
   | RecipientType         | UserMailbox                                                              |
   | En  | UserMailbox                                                              |
   | UserPrincipalName     | LaraN@contoso \. onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Lara \. Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o = första organisation/ou = Exchange administrativ grupp                   |
   |                       | (FYDIBOHF23SPDLT)/CN = mottagare/CN = d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | Postadresser '        | SMTP: LaraN@contoso \. onmicrosoft.com 
   |                       | SMTP: Lara \. Newton@contoso.com          |
   |||

   - Ytterligare attribut kan ingå i Exchange hybrid Skriv tillbaka. Om inte, ska de inkluderas. 
   - msExchBlockedSendersHash – skriver tillbaka säkra och blockerade avsändare från klienter till lokala Active Directory.
   - msExchSafeRecipientsHash – skriver tillbaka säkra och blockerade avsändare från klienter till lokala Active Directory.
   - msExchSafeSendersHash – skriver tillbaka säkra och blockerade avsändare från klienter till lokala Active Directory.

2. Om käll brev lådan är på LitigationHold och storleken på post lådan för återställnings bara objekt är större än vår databas (30 GB), går det inte att flytta eftersom mål kvoten är mindre än käll post lådan. Du kan uppdatera mål-e-postobjektet för att överföra ELC från käll miljön till målet, vilket utlöser mål systemet för att expandera kvoten för e-postkontot till 100 GB och därmed tillåta flytten till målet. De här instruktionerna fungerar bara för Hybrid identitet med Azure AD Connect, eftersom de kommandon som används för att stämpla ELC flaggor inte är utsatta för klient organisationer.

    >[!Note]
    > EXEMPEL – SOM DET ÄR, INGEN GARANTI<br/>Det här manuset utgår från en anslutning till båda käll brev lådan (för att få käll värden) och mål platsen lokalt Active Directory (för att stämpla ADUser-objektet). Om källan har en tvist eller återställning av enskilt objekt aktiverat anger du detta på mål kontot.  Detta ökar Dumpster storlek för mål kontot till 100 GB.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. Icke-hybrid mål innehavare kan ändra kvoten för mappen för återställnings bara objekt för användare före migreringen genom att köra följande kommando för att aktivera tvist i gruppen User och öka kvoten till 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Observera att detta inte fungerar för klient organisationer i hybrid.

4. Användare i mål organisationen måste vara licensierade med lämpliga Exchange Online-prenumerationer för organisationen. Du kan lägga till en licens i förväg i en post lådas flytt, men bara när mål-e-postkontot har kon figurer ATS korrekt med ExchangeGUID och proxyadresser. Om du använder en licens innan ExchangeGUID tillämpas kommer en ny post låda att läggas till i mål organisation. 

    > [!Note]
    > När du tillämpar en licens på en post låda eller ett e-postobjekt, tas alla SMTP-proxyAddresses bort så att endast verifierade domäner tas med i matrisen Exchange postadresser '. 

5. Du måste se till att mål-ExchangeGuid inte har några tidigare som inte stämmer överens med ExchangeGuid. Det här kan inträffa om mål-POSTAKTIVERADE användaren tidigare var licensierad för Exchange Online och etablerade en post låda. Om mål-eller postanvändaren har licensierat för eller haft en ExchangeGuid som inte matchar käll ExchangeGuid måste du utföra en rensning av moln POSTAKTIVERADE användaren. Du kan köra kommandot för dessa moln postaktiverade användare `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` . 

    > [!Caution]
    > Den här processen kan inte ångras. Om objektet har en softDeleted-postlåda kan den inte återställas efter den här punkten. När du har avmarkerat den kan du synkronisera rätt ExchangeGuid till målobjektet och MRS ansluter käll post lådan till den nya mål post lådan. (Referens, EHLO-blogg på den nya parametern.) 
 
    Hitta objekt som tidigare post lådor med det här kommandot.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    Här är ett exempel. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    Rensa den borttagna post lådan med det här kommandot.

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    Här är ett exempel.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a>Utföra migrering av post lådor

Migreringar av Exchange-postgrupper som skickas från mål klient organisationen. Detta liknar det sätt som de on-Board-kommandona fungerar när du migrerar från Exchange lokalt till Microsoft 365. 

### <a name="create-migration-batches"></a>Skapa migreringsåtgärder

Här är ett exempel på en cmdlet för migrering för att stoppa flytten.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> E-postadressen i CSV-filen måste vara den som anges i mål klient organisationen, inte till käll klient organisationen.

Batchbearbetning stöds också från det nya administrations centret för Exchange när du väljer alternativet kors klient organisation.
 
#### <a name="update-on-premises-mailusers"></a>Uppdatera lokala användare

När post lådan flyttas från källa till mål bör du kontrol lera att lokala e-postkonton, både källa och mål, uppdateras med den nya targetAddress. I exemplen är targetDeliveryDomain som används i flytten **contoso \. onmicrosoft.com**. Uppdatera e-postanvändare med denna targetAddress.
 
## <a name="frequently-asked-questions"></a>Vanliga frågor och svar
 
**Måste vi uppdatera RemoteMailboxes i lokal plats efter flytten?**
 
Ja, du bör uppdatera targetAddress (RemoteRoutingAddress/ExternalEmailAddress) för lokala käll användare när käll gruppens post låda flyttas till mål klient organisationen.  När e-postroutning kan följa hänvisningar till flera e-postkonton med olika targetAddresses måste du ha en särskild/upptagen-sökning för att e-postanvändare ska ha plats för platsen för post lådan. Ledig/upptagen-sökningar kommer inte att spåra flera omdirigeringar. 
 
**Migrerar mappen Teams-mappinnehåll kors klient organisationen?** 

Nej, mappinnehåll för Teams-chatt migrerar inte kors klient organisationer. 
 
**Hur kan jag se bara flytt mellan klient organisationer, inte mina inbyggda och offboardinger?**

Använd `-flags` parametern. Här är ett exempel.

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
**Kan du ange exempel skript för kopiering av attribut som används vid testning?**

> [!Note]
> EXEMPEL – SOM DET ÄR, INGEN GARANTI<br/>Det här manuset utgår från en anslutning till båda käll brev lådan (för att få käll värden) och målets lokala Active Directory Domain Services (för att stämpla ADUser-objektet). Om källan har en tvist eller återställning av enskilt objekt aktiverat anger du detta på mål kontot.  Detta ökar Dumpster storlek för mål kontot till 100 GB.

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
**Hur kommer vi åt Outlook på dag 1 efter att Använd post låda har flyttats?**

Eftersom bara en klient organisation kan äga en domän kopplas inte den tidigare primära SMTPAddress till användaren i mål klient organisationen när flytt brev lådan är klar. endast de domäner som är kopplade till den nya innehavaren. Outlook använder de nya UPN-användarna för att autentisera till tjänsten och Outlook-profilen förväntar sig att hitta den äldre primära SMTPAddress för att matcha post lådan i mål systemet. Eftersom den äldre adressen inte finns i mål systemet går det inte att ansluta till den nyligen flyttade post lådan. 

För den här första distributionen måste användarna återskapa sin profil med deras nya UPN, primära SMTP-adress och Synkronisera OST-innehåll på nytt. 

> [!Note]
> Planera detta när du gruppanvändar dina användare. Du måste ha till gång till nätverks användning och-kapacitet när Outlook-klient profiler skapas och följande OST-och OAB-filer laddas ned till klienter. 
 
**Vilka Exchange RBAC-roller måste jag vara medlem i för att kunna konfigurera eller slutföra en förflyttning mellan klienter?**
 
En matris med roller baseras på antagande av delegerade uppgifter när en post låda flyttas. För närvarande krävs två roller:  

- Den första rollen är en konfiguration med en enda tids period som anger tillstånd för att flytta innehåll till eller från din klient organisations gräns. Eftersom flytt av data från din organisations kontroll är ett kritiskt problem för alla företag har vi valt den mest tilldelade rollen som organisations administratör (OrgAdmin). Den här rollen måste ändra eller ställa in en ny OrganizationRelationship som definierar MailboxMoveCapability med fjärrorganisationen. Det är bara funktionen OrgAdmin som kan ändra inställningen för MailboxMoveCapability medan andra attribut i OrganizationRelationhip kan hanteras av administratören för extern delning. 
 
- Rollen för att köra kommandot faktiskt flytt kan delegeras till en lågnivå funktion. Rollen som flyttar post lådor är kopplad till eller från organisationen genom att använda `-RemoteTenant` parametern.  

**Hur kan vi nå SMTP-adressen för targetAddress (TargetDeliveryDomain) på den konverterade post lådan (to user Conversion)?**
 
Exchange-postlådan flyttar med MRS-båtar targetAddress på den ursprungliga käll brev lådan när du konverterar till en e-postanvändare genom att matcha en adress (proxyAddress) för målobjektet. Processen tar TargetDeliveryDomain-värdet som skickas till kommandot Move och letar sedan efter en matchande proxyserver för domänen på mål sidan. När vi hittar en matchning används den matchande proxyAddress för att ange ExternalEmailAddress (targetAddress) i det konverterade post lådan (nu).
 
**Hur över gången åtkomst till post lådor?**

Behörigheter för Mailbox inkluderar Send för användarens och post lådans åtkomst: 

- Skicka åt (AD: publicDelegates) lagrar DN för mottagarna med åtkomst till en användares post låda som ombud. Det här värdet lagras i Active Directory och flyttas inte som en del av över gången till post lådan. Om käll brev lådan innehåller publicDelegates måste du omstämpla publicDelegates i mål brev lådan när POSTAKTIVERADE användaren-konverteringen till post låda har slutförts i mål miljön med `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` kommandot. 
 
- Behörigheter för Mailbox som lagras i post lådan flyttas med post lådan när både huvud kontot och ombudet flyttas till mål systemet. Användaren TestUser_7 ges till exempel behörigheten Full Access till post lådan TestUser_8 i klient organisationens SourceCompany.onmicrosoft.com. När flyttningen av post lådan är färdig med TargetCompany.onmicrosoft.com har samma behörigheter ställts in i mål katalogen. Exempel på *Get-MailboxPermission* för TestUser_7 i både käll-och mål klient organisationer visas nedan. Exchange-cmdlets föregås av källa och mål därefter. 
 
Här är ett exempel på utdata från Mailbox-behörigheten före flytt. 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Här är ett exempel på utdata från Mailbox-behörighet efter flytten. 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Det går inte att hantera behörigheter mellan innehavare och kalender. Du måste ordna objekt och ombud i konsoliderade flyttningar så att dessa kopplade post lådor kopplas samtidigt från käll klient organisationen. 
 
## <a name="known-issues"></a>Kända problem 

-  **Problem: det går inte att migrera automatiskt utökade arkiv.** Överflyttnings funktionen mellan innehavare stöder migrering av den primära post lådan och Arkiv post lådan för en viss användare. Om användaren i källan har ett automatiskt expanderat Arkiv – d.v.s. mer än en Arkiv post låda kan funktionen inte migrera ytterligare arkiv.

- **Problem: Cloud-användare med icke ägda SMTP-proxyAddress blockera MRS flyttar bakgrunden.** När du skapar användare av mål grupp för användar namn måste du se till att alla SMTP-proxyadresser tillhör organisationen för mål innehavaren. Om en SMTP-proxyAddress finns på mål-e-postkontot som inte tillhör den lokala klient organisationen förhindras konverteringen av e-postmeddelandet till post låda. Detta är på grund av vår garanti att Mailbox-objekt endast kan skicka e-post från domäner för vilka klient organisationen är auktoritär (domäner som klienten använder): 
- 
   - När du synkroniserar användare via lokal användning av Azure AD Connect etablerar du lokala e-postobjekt med ExternalEmailAddress som pekar på käll klient organisationen där post lådan finns (laran@contoso \. onmicrosoft.com) och sedan stämplar PrimarySMTPAddress som en domän som finns i mål klient organisationen (Lara.Newton@northwind \. com). Dessa värden synkroniseras till klient organisationen och en lämplig e-postanvändare tillhandahålls och är klar för migrering. Ett exempel objekt visas här.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > Com-adressen *contoso \. . onmicrosoft* finns *inte* i postadresser '/proxyAddresses-matrisen.

- **Problem: användar objekt med "externa" primära SMTP-adresser ändras/återställs till "det interna" Företaget begärde domäner**

   Postobjekt är pekare till icke-lokala post lådor. I fråga om migrering av post lådor mellan innehavare använder vi användar objekt för att representera antingen käll post lådan (från mål organisationens perspektiv) eller mål post lådan (från käll organisationens perspektiv). E-postanvändare kommer att ha en ExternalEmailAddress (targetAddress) som pekar på SMTP-adressen till den faktiska post lådan (ProxyTest \@ fabrikam \. onmicrosoft.com) och primarySMTP-adressen som representerar den SMTP-adress som står för användare i katalogen. Vissa organisationer väljer att visa den primära SMTP-adressen som en extern SMTP-adress, inte som en adress som ägs/verifieras av den lokala klient organisationen (till exempel fabrikam.com istället för som contoso.com).  När ett Exchange Service plan-objekt tillämpas på en användare via licensierings åtgärder ändras emellertid den primära SMTP-adressen så att den visas som en domän verifierad av den lokala organisationen (contoso.com). Det finns två möjliga orsaker:
   
   - När en Exchange Service-plan tillämpas på en e-användare börjar Azure AD-processen att tvinga fram återskrubbning för att säkerställa att den lokala organisationen inte kan skicka e-post, förfalskningar eller e-post från en annan klient organisation. Alla SMTP-adresser på ett mottagar objekt med dessa Service planer tas bort om adressen inte verifieras av den lokala organisationen. Precis som i exemplet \. är Fabikam com-domänen inte verifierad av contoso \. onmicrosoft.com-klienten, så rensning tar bort den Fabrikam \. com-domänen. Om du vill behålla de här externa domänerna på en användare, antingen före migreringen eller efter migreringen, måste du ändra migrerings processerna till stripe-licenser efter flytten eller före flytten för att säkerställa att användarna har den förväntade externa märkningen. Du måste kontrol lera att objektet Mailbox är korrekt licensierat för att inte påverka e-posttjänsten.<br/><br/>Ett exempel skript som används för att ta bort tjänste abonnemangen på en användare i Contoso \. onmicrosoft.com-innehavaren visas här.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Resultat i den uppsättning ServicePlans som har tilldelats visas här.

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
 
       Användarens PrimarySMTPAddress tas inte längre bort. Fabrikam.com-domänen ägs inte av contoso.onmicrosoft.com-klienten och kommer att bevaras som den primära SMTP-adressen som visas i katalogen.

       Här är ett exempel.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - När msExchRemoteRecipientType är inställt på 8 (DeprovisionMailbox) för lokala-användare som migreras till mål klient organisationen tas de icke ägda domänerna bort och återställas till en ägd domän. Genom att rensa msExchRemoteRecipientType i den lokala postkontot gäller inte den här logiken för skrubbning. <br/><br>Nedan hittar du alla möjliga service abonnemang som innehåller Exchange Online.

   | Namn                                              |
   |---------------------------------------------------|
   | Avancerade eDiscovery-lagringar (500 GB)               |
   | Customer Lockbox                                  |
   | Dataförlustskydd                              |
   | Exchange Enterprise CAL-tjänster (EOP, DLP)       |
   | Grunderna i Exchange                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (abonnemang 1)                          |
   | Exchange Online (abonnemang 2)                          |
   | Exchange Online-arkivering för Exchange Online     |
   | Exchange Online-arkivering för Exchange Server     |
   | Inaktive rad Exchange Online-tillägg              |
   | Exchange Online-kiosk                             |
   | Exchange Online multi-geo                         |
   | Exchange Online-abonnemang 1                            |
   | POP för Exchange Online                               |
   | Exchange Online Protection                        |
   | Informations hinder                              |
   | Informations skydd för Office 365 – Premium   |
   | Informations skydd för Office 365 – standard  |
   | Insikter för analys                           |
   | Microsoft 365 avancerad granskning                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft $ (fullständig)                      |
   | Avancerad eDiscovery för Office 365                    |
   | Microsoft Defender för Office 365 (abonnemang 1)    |
   | Microsoft Defender för Office 365 (abonnemang 2)    |
   | Office 365 hantering av privilegie rad åtkomst           |
   | Premium-kryptering i Office 365                  |
    
