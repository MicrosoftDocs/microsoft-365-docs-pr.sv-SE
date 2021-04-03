---
title: Använda PowerShell för att utföra en snabb migrering till Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Lär dig hur du använder PowerShell för att flytta innehållet från ett käll-e-postsystem på en gång genom att utföra en migrering till Microsoft 365.
ms.openlocfilehash: 6e59ac4d590208e0faed22e94cabe05601b17f18
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581064"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>Använda PowerShell för att utföra en snabb migrering till Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan migrera innehållet i användarpostlådor från ett källsystem för e-post till Microsoft 365 på en gång med hjälp av en cutover-migrering. I den här artikeln får du hjälp med uppgifterna för en e-postmigrering med Exchange Online PowerShell.

Genom att gå igenom avsnittet Vad du behöver veta om en snabb e-postmigrering till [Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)får du en översikt över migreringsprocessen. När du har bekantat dig med innehållet i den artikeln kan du använda den här för att börja migrera postlådor från ett e-postsystem till ett annat.

> [!NOTE]
> Du kan också använda Exchange admin center för att utföra en cutover-migrering. Se [Utföra en cutover-migrering av e-post till Microsoft 365.](/Exchange/mailbox-migration/cutover-migration-to-office-365)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Beräknad tid för att slutföra den här uppgiften: 2–5 minuter för att skapa en migreringsbatch. När migreringsbatchen har startats varierar varaktigheten för migreringen beroende på antalet postlådor i batchen, storleken på varje postlåda och din tillgängliga nätverkskapacitet. Information om andra faktorer som påverkar hur lång tid det tar att migrera postlådor till Microsoft 365 finns i [Migreringsprestanda.](/Exchange/mailbox-migration/office-365-migration-best-practices)

Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna. Du kan se vilka behörigheter du behöver i migreringsposten i en tabell i [avsnittet Behörigheter för](/exchange/recipients-permissions-exchange-2013-help) mottagare.

Om du vill använda Exchange Online PowerShell-cmdlets måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session. Instruktioner [finns i Ansluta till Exchange Online med fjärr-PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)

## <a name="migration-steps"></a>Migreringssteg

### <a name="step-1-prepare-for-a-cutover-migration"></a>Steg 1: Förbereda för en cutover-migrering
<a name="BK_Step1"> </a>

- **Lägg till din lokala Exchange-organisation som en godkänd domän i din Microsoft 365-organisation.** Migreringstjänsten använder SMTP-adressen för dina lokala postlådor för att skapa Microsoft Online Services användar-ID och e-postadress för de nya Microsoft 365-postlådorna. Migreringen misslyckas om din Exchange-domän inte är en godkänd domän eller primär domän i din Microsoft 365-organisation. Mer information finns i [Verifiera din domän.](../admin/setup/add-domain.md)

- **Konfigurera Outlook överallt på den lokala Exchange-servern.** E-postmigreringstjänsten använder RPC över HTTP, eller Outlook Anywhere, för att ansluta till din lokala Exchange-server. Mer information om hur du konfigurerar Outlook överallt för Exchange 2010, Exchange 2007 och Exchange 2003 finns här:

  - [Exchange 2010: Aktivera Outlook överallt](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))

  - [Exchange 2007: Aktivera Outlook överallt](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))

  - [Exchange 2003: Distributionsscenarier för RPC över HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))

  - [Så här konfigurerar du Outlook var som helst med Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))

    > [!IMPORTANT]
    > Konfigurationen för Outlook Anywhere måste konfigureras med ett certifikat utfärdat av en betrodd certifikatutfärdare (CA). Det kan inte konfigureras med ett själv signerat certifikat. Mer information finns i Konfigurera [SSL för Outlook överallt.](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))

- **Kontrollera att du kan ansluta till Exchange-organisationen med Outlook överallt.** Prova någon av de här metoderna för att testa dina anslutningsinställningar:

  - Använd Microsoft Outlook utanför företagsnätverket för att ansluta till din lokala Exchange-postlåda.

  - Använd Microsoft [Analysverktyg för fjärranslutning för](https://www.testexchangeconnectivity.com/) Att testa dina anslutningsinställningar. Använd Outlook överallt (RPC över HTTP) eller Outlook Automatisk upptäckt av tester.

  - Kör följande kommandon i Exchange Online PowerShell.

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Tilldela ett lokalt användarkonto nödvändiga behörigheter för åtkomst till postlådor i din Exchange-organisation.** Det lokala användarkonto som du använder för att ansluta till den lokala Exchange-organisationen (kallas även migreringsadministratör) måste ha nödvändiga behörigheter för att få åtkomst till de lokala postlådor som du vill migrera till Microsoft 365. Det här användarkontot används för att skapa en migreringsslutpunkt för den lokala organisationen.

    I följande lista visas de administratörsrättigheter som krävs för att migrera postlådor med hjälp av en cutover-migrering. Det finns tre möjliga alternativ.

  - Migreringsadministratören måste vara medlem i **gruppen Domänadministratörer** i Active Directory i den lokala organisationen.

    Eller

  - Migreringsadministratören måste ha **FullAccess** -behörighet för var och en av de lokala postlådorna.

    Eller

  - Migreringsadministratören måste ha **Receive As-behörighet** till den lokala postlådedatabas där användarnas postlådor lagras.

- **Inaktivera Unified Messaging.** Om de lokala postlådor du migrerar har aktiverats för Unified Messaging (UM) måste du inaktivera UM för postlådorna innan du migrerar dem. Du kan sedan aktivera UM för postlådorna när migreringen är klar.

- **Säkerhetsgrupper och ombud** E-postmigreringstjänsten kan inte identifiera om lokala Active Directory-grupper är säkerhetsgrupper eller inte. Därför kan den inte tillhandahålla några migrerade grupper som säkerhetsgrupper i Microsoft 365. Om du vill ha säkerhetsgrupper i Microsoft 365-klienten måste du först tillhandahålla en tom e-postaktiverad säkerhetsgrupp i Microsoft 365-klientorganisationen innan du påbörjar migreringen. Med den här migreringsmetoden flyttas dessutom bara postlådor, e-postanvändare, e-postkontakter och e-postgrupper. Om något annat Active Directory-objekt, till exempel en användare som inte har migrerats till Microsoft 365, tilldelas som chef eller ombud till ett objekt som migreras måste de tas bort från objektet innan du migrerar.

### <a name="step-2-create-a-migration-endpoint"></a>Steg 2: Skapa en migreringsslutpunkt
<a name="BK_Step2"> </a>

För att e-post ska migreras måste Microsoft 365 ansluta till och kommunicera med käll-e-postsystemet. För att göra det använder Microsoft 365 en migreringsslutpunkt. Om du vill skapa en migreringsslutpunkt för Outlook Överallt för en migrering i Outlook ska [du först ansluta till Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)

En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)

Kör följande kommandon i Exchange Online PowerShell:

```powershell
$Credentials = Get-Credential
```

I exemplet används cmdleten [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) för att hämta och testa anslutningsinställningarna till den lokala Exchange-servern, och sedan används dessa anslutningsinställningar för att skapa migreringsslutpunkten med namnet "CutoverEndpoint".

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> Cmdleten **New-MigrationEndpoint** kan användas för att ange en databas för tjänsten som ska användas med **alternativet -TargetDatabase.** Annars tilldelas en databas slumpmässigt från AD FS 2.0-webbplatsen (Active Directory Federation Services) där hanteringspostlådan finns.

#### <a name="verify-it-worked"></a>Kontrollera att det fungerade

Kör följande kommando i Exchange Online PowerShell för att visa information om migreringsslutpunkten "CutoverEndpoint":

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>Steg 3: Skapa snabbmigreringsbatch
<a name="BK_Step3"> </a>

Du kan använda cmdleten **New-MigrationBatch** i Exchange Online PowerShell för att skapa en migreringsbatch för en migreringsbatch. Du kan skapa en migreringsbatch och starta den automatiskt genom att ta med _parametern AutoStart._ Alternativt kan du skapa migreringsbatchen och sedan starta den manuellt efteråt med hjälp av cmdleten **Start-MigrationBatch.** Det här exemplet skapar en migreringsbatch med namnet "CutoverBatch" och använder migreringsslutpunkten som skapades i föregående steg.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

Det här exemplet skapar också en migreringsbatch med namnet "CutoverBatch" och använder migreringsslutpunkten som skapades i föregående steg. Eftersom _parametern AutoStart_ inte ingår måste migreringsbatchen startas manuellt på instrumentpanelen för migrering eller med hjälp av **cmdleten Start-MigrationBatch.** Som tidigare nämnts kan bara en batch för migreringsmigrering finnas i taget.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>Kontrollera att det fungerade

Kontrollera att du har skapat en migreringsbatch för en migreringsbatch genom att köra följande kommando i Exchange Online PowerShell för att visa information om den nya migreringsbatchen:

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>Steg 4: Starta snabbmigreringsbatchen
<a name="BK_Step4"> </a>

Starta migreringsbatchen i Exchange Online PowerShell genom att köra följande kommando. Det här skapar en migreringsbatch med namnet "CutoverBatch".

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>Kontrollera att det fungerade

Om en migreringsbatch har startats anges dess status på instrumentpanelen för migrering som Synkroniserar. Kör följande kommando för att verifiera att du har startat en migreringsbatch med Exchange Online PowerShell:

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Steg 5: Dirigera din e-post till Microsoft 365
<a name="BK_Step5"> </a>

Email systems use a DNS record called an MX record to figure out where to deliver emails. Under e-postmigreringsprocessen pekade MX-posten på ditt käll-e-postsystem. Nu när e-postmigrering till Microsoft 365 är klar är det dags att peka MX-posten på Microsoft 365. Då ser du till att e-posten levereras till dina Microsoft 365-postlådor. Genom att flytta MX-posten kan du också stänga av ditt gamla e-postsystem när du är redo.

För många DNS-leverantörer finns det särskilda anvisningar för hur du ändrar MX-posten. Om din DNS-värd inte finns med eller om du bara allmänt vill se hur anvisningarna ser ut, finns det även [allmänna anvisningar för MX-posten](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx).

Det kan ta upp till 72 timmar för kunders och partners e-postsystem att se den ändrade MX-posten. Vänta i minst 72 timmar innan du går vidare till nästa uppgift: [Steg 6: Ta bort batchen för cutover-migrering.](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6)

### <a name="step-6-delete-the-cutover-migration-batch"></a>Steg 6: Ta bort snabbmigreringsbatchen
<a name="Bk_step6"> </a>

När du har ändrat MX-posten och verifierat att all e-post dirigeras till postlådor i Microsoft 365 informerar du användarna om att deras e-post kommer till Microsoft 365. Därefter kan du ta bort batchen för cutover-migrering. Kontrollera följande innan du tar bort migreringsbatchen.

- Alla användare använder Microsoft 365-postlådor. När batchen har tagits bort kopieras inte e-post som skickas till postlådorna på den lokala Exchange Server till motsvarande Microsoft 365-postlådor.

- Microsoft 365-postlådor synkroniserades minst en gång efter att e-posten började skickas direkt till dem. Det gör du genom att kontrollera att värdet i rutan Senaste synkronisering är senare än när e-posten började dirigeras direkt till Microsoft 365-postlådorna.

Om du vill ta bort migreringsbatchen "CutoverBatch" i Exchange Online PowerShell kör du följande kommando:

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>Avsnitt 7: Tilldela användarlicenser
<a name="BK_Step7"> </a>

 **Aktivera Microsoft 365-användarkonton för de migrerade kontona genom att tilldela licenser.** Om du inte tilldelar en licens inaktiveras postlådan när tidsfristen löper ut (30 dagar). Information om hur du tilldelar en licens i administrationscentret för Microsoft 365 finns i [Tilldela eller ta bort licenser.](../admin/manage/assign-licenses-to-users.md)

### <a name="step-8-complete-post-migration-tasks"></a>Steg 8: Slutför uppgifter efter migreringen
<a name="BK_Step8"> </a>

- **Skapa en DNS-post för automatisk upptäckt så att användarna enkelt kan komma till sina postlådor.** När alla lokala postlådor har migrerats till Microsoft 365 kan du konfigurera en DNS-post för automatisk upptäckt för Microsoft 365-organisationen så att användare enkelt kan ansluta till sina nya Microsoft 365-postlådor med Outlook och mobila klienter. Den nya DNS-posten för automatisk upptäckt måste använda samma namnområde som du använder för Microsoft 365-organisationen. Om ditt molnbaserade namnområde till exempel är cloud.contoso.com, behöver du skapa DNS-posten autodiscover.cloud.contoso.com.

    Om du behåller Exchange Server bör du också se till att automatisk upptäckt av DNS CNAME-posten pekar på Microsoft 365 i både intern och extern DNS efter migreringen så att Outlook-klienten kan ansluta till rätt postlåda.

    > [!NOTE]
    >  I Exchange 2007, Exchange 2010 och Exchange 2013 bör du också ange `Set-ClientAccessServer AutodiscoverInternalConnectionURI` `Null` .

    Microsoft 365 använder en CNAME-post för att implementera tjänsten för automatisk upptäckt för Outlook och mobila klienter. CNAME-posten för automatisk upptäckt måste innehålla följande information:

  - **Alias:** autodiscover

  - **Target:** autodiscover.outlook.com

    Mer information finns i Lägga [till DNS-poster för att ansluta din domän.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

- **Inaktivera lokala Exchange-servrar.** När du har kontrollerat att all e-post dirigeras direkt till Microsoft 365-postlådorna och du inte längre behöver underhålla din lokala e-postorganisation eller inte planerar att implementera enkel inloggning (SSO), kan du avinstallera Exchange från dina servrar och ta bort din lokala Exchange-organisation.

    Mer information finns i följande avsnitt:

  - [Ändra eller ta bort Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))

  - [Ta bort en Exchange 2007-organisation](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))

  - [Avinstallera Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))