---
title: Använda PowerShell för att utföra en snabb migrering till Microsoft 365
ms.author: sirkkuw
author: sirkkuw
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
description: Lär dig hur du använder PowerShell för att flytta innehållet från ett käll-e-postsystem samtidigt genom att utföra en snabbmigrering migrering till Microsoft 365.
ms.openlocfilehash: 74e7791c4292598e4717e56af25e39b3c8208108
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948202"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>Använda PowerShell för att utföra en snabb migrering till Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan migrera innehållet i användar post lådor från ett käll-e-postsystem till Microsoft 365 alla samtidigt genom att använda en snabbmigrering-migrering. I den här artikeln får du stegvisa instruktioner för en e-snabbmigrering migrering genom att använda Exchange Online PowerShell.

Genom att granska avsnittet, [vad du behöver veta om en snabbmigrering-migrering till Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536688), kan du få en översikt över migreringen. När du har bekantat dig med innehållet i den artikeln kan du använda den här för att börja migrera postlådor från ett e-postsystem till ett annat.

> [!NOTE]
> Du kan också använda administrations centret för Exchange för att utföra en snabbmigrering migrering. Se [utföra en snabbmigrering migrering av e-post till Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Uppskattad tid för att slutföra den här uppgiften: 2-5 minuter för att skapa en migreringstabell. När migreringen har startat varierar varaktigheten för migreringen baserat på antalet post lådor i gruppen, storleken på varje post låda och din tillgängliga nätverks kapacitet. Information om andra faktorer som påverkar hur lång tid det tar att migrera post lådor till Microsoft 365 finns i [migreringens prestanda](https://go.microsoft.com/fwlink/p/?LinkId=275079).

Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna. Om du vill se vilka behörigheter du behöver läser du "migration"-posten i en tabell i avsnittet [mottagare](https://go.microsoft.com/fwlink/p/?LinkId=534105) .

För att använda PowerShell-cmdletar för Exchange Online måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session. Se [ansluta till Exchange Online med Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) för instruktioner.

En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).

## <a name="migration-steps"></a>Migreringsåtgärder

### <a name="step-1-prepare-for-a-cutover-migration"></a>Steg 1: förbereda en snabbmigrering migrering
<a name="BK_Step1"> </a>

- **Lägg till din lokala Exchange-organisation som en godkänd domän i din Microsoft 365-organisation.** Migreringstjänster använder SMTP-adressen för dina lokala post lådor för att skapa användar-ID för Microsoft Online Services och e-postadress för de nya Microsoft 365-postlådor. Migreringen Miss lyckas om din Exchange-domän inte är en godkänd domän eller din Microsoft 365-organisations primära domän. Mer information finns i [Verifiera din domän](https://go.microsoft.com/fwlink/p/?LinkId=534110).

- **Konfigurera Outlook överallt på din lokala Exchange-Server.** Tjänsten för e-postmigrering använder RPC via HTTP eller Outlook överallt för att ansluta till din lokala Exchange-Server. Mer information om hur du konfigurerar Outlook överallt för Exchange 2010, Exchange 2007 och Exchange 2003 finns här:

  - [Exchange 2010: Aktivera Outlook överallt](https://go.microsoft.com/fwlink/?LinkID=187249)

  - [Exchange 2007: Aktivera Outlook överallt](https://go.microsoft.com/fwlink/?LinkID=167210)

  - [Exchange 2003: distributions scenarier för RPC via HTTP](https://go.microsoft.com/fwlink/?LinkID=73657)

  - [Konfigurera Outlook överallt med Exchange 2003](https://go.microsoft.com/fwlink/?LinkID=167209)

    > [!IMPORTANT]
    > Din Outlook Anywhere-konfiguration måste konfigureras med ett certifikat utfärdat av en betrodd certifikat utfärdare (CA). Den kan inte konfigureras med ett självsignerat certifikat. Mer information finns i [så här konfigurerar du SSL för Outlook överallt](https://go.microsoft.com/fwlink/?LinkID=80875).

- **Kontrol lera att du kan ansluta till Exchange-organisationen med hjälp av Outlook överallt.** Prova med någon av följande metoder för att testa dina anslutnings inställningar:

  - Använd Microsoft Outlook utanför företagets nätverk för att ansluta till den lokala Exchange-postlådan.

  - Använd Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) för att testa dina anslutnings inställningar. Använd Outlook överallt (RPC över HTTP) eller Outlook Automatisk upptäckt av tester.

  - Kör följande kommandon i Exchange Online PowerShell.

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Tilldela ett lokalt användar konto de behörigheter som krävs för att komma åt post lådor i din Exchange-organisation.** Det lokala användar kontot som du använder för att ansluta till den lokala Exchange-organisationen (kallas även för administratör för migrering) måste ha nödvändig behörighet för att få åtkomst till de lokala post lådorna som du vill migrera till Microsoft 365. Detta användar konto används för att skapa en slut punkt för migrering till din lokala organisation.

    Följande lista visar de administratörs behörigheter som krävs för att migrera post lådor med en snabbmigrering-migrering. Det finns tre möjliga alternativ.

  - Uppgraderingen måste vara medlem i gruppen **Domain admins** i Active Directory i den lokala organisationen.

    Eller

  - Migreringsadministratören måste ha **FullAccess** -behörighet för var och en av de lokala postlådorna.

    Eller

  - Överflyttnings administratören måste ha behörigheten **Receive As** för den lokala post lådan som lagrar användar post lådorna.

- **Inaktivera Unified Messaging.** Om de lokala post lådorna som du migrerar är aktiverade för Unified Messaging (UM) måste du inaktivera UM på post lådorna innan du migrerar dem. Du kan sedan aktivera UM på post lådorna efter migreringen.

- **Säkerhets grupper och ombud** Tjänsten för e-postmigrering kan inte identifiera om lokala Active Directory-grupper är säkerhets grupper eller inte, så den kan inte etablera migrerade grupper som säkerhets grupper i Microsoft 365. Om du vill ha säkerhets grupper i din Microsoft 365-klient organisation måste du först etablera en tom e-postaktiverad säkerhets grupp i din Microsoft 365-klient organisation innan du kan starta snabbmigrering-migreringen. Dessutom flyttas den här metoden endast för post lådor, e-postsamt e-postkontakter och e-postaktiverade grupper. Om ett annat Active Directory-objekt, till exempel användare som inte migreras till Microsoft 365, tilldelas som chef eller ombud för ett objekt som migreras, måste de tas bort från objektet innan du migrerar.

### <a name="step-2-create-a-migration-endpoint"></a>Steg 2: skapa en slut punkt för migrering
<a name="BK_Step2"> </a>

För att migrera e-post måste Microsoft 365 ansluta och kommunicera med käll-e-postsystemet. För att göra det, använder Microsoft 365 en slut punkt för migrering. Om du vill skapa en migrerings slut punkt för Outlook för snabbmigrering migration [ansluter du först till Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).

En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).

Kör följande kommandon i Exchange Online PowerShell:

```powershell
$Credentials = Get-Credential
```

I exemplet används cmdleten [test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) för att hämta och testa anslutnings inställningarna till den lokala Exchange-servern, och sedan används dessa anslutnings inställningar för att skapa migrerings slut punkten med namnet "CutoverEndpoint".

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> Cmdleten **New-MigrationEndpoint** kan användas för att ange en databas som ska användas med alternativet **-TargetDatabase** . I annat fall tilldelas en databas slumpmässigt från AD FS-2,0 (Active Directory Federation Services) där hanterings post lådan finns.

#### <a name="verify-it-worked"></a>Verifiera att den fungerade

I Exchange Online PowerShell kör du följande kommando för att visa information om "CutoverEndpoint"-slut punkt för migrering:

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>Steg 3: Skapa snabbmigreringsbatch
<a name="BK_Step3"> </a>

Du kan använda cmdleten **New-MigrationBatch** i Exchange Online PowerShell för att skapa en migreringstabell för en snabbmigrering-migrering. Du kan skapa en migreringstabell och starta den automatiskt genom att inkludera _Autostart_ -parametern. Alternativt kan du skapa migreringstabellen och sedan starta den manuellt med hjälp av cmdleten **Start-MigrationBatch** . I det här exemplet skapas ett migreringsarkiv med namnet "CutoverBatch" och används den slut punkt som skapades i föregående steg.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

I det här exemplet skapas en migreringstabell med namnet "CutoverBatch" och används den migrerings slut punkt som skapades i föregående steg. Eftersom den  _Autostart_ -parametern inte är inkluderad måste migreringsverktyget startas manuellt på kontroll panelen för migreringen eller genom att använda cmdleten **Start-MigrationBatch** . Som tidigare angiven kan bara en snabbmigrering för migrering finnas åt gången.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>Verifiera att den fungerade

Om du vill kontrol lera att du har skapat en migreringstabell för en snabbmigrering migrering kör du följande kommando i Exchange Online PowerShell och visar information om den nya migreringstabellen:

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>Steg 4: Starta snabbmigreringsbatchen
<a name="BK_Step4"> </a>

Om du vill starta migreringsverktyget i Exchange Online PowerShell kör du följande kommando. Detta skapar ett migreringsarkiv med namnet "CutoverBatch".

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>Verifiera att den fungerade

Om en migreringstabell har startat anges dess status på kontroll panelen för migrering som synkronisering. Om du vill kontrol lera att du har startat en migreringstabell med Exchange Online PowerShell kör du följande kommando:

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Steg 5: dirigera din e-post till Microsoft 365
<a name="BK_Step5"> </a>

Email systems use a DNS record called an MX record to figure out where to deliver emails. Under e-postmigreringen pekar din MX-post på ditt käll-e-postsystem. Nu när e-postmigreringen till Microsoft 365 är klar är det dags att skicka MX-posten på Microsoft 365. Då ser du till att e-post skickas till dina Microsoft 365-postlådor. Genom att flytta MX-posten kan du även inaktivera det gamla e-postsystemet när du är klar.

För många DNS-leverantörer finns det särskilda anvisningar för hur du ändrar MX-posten. Om din DNS-värd inte finns med eller om du bara allmänt vill se hur anvisningarna ser ut, finns det även [allmänna anvisningar för MX-posten](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx).

Det kan ta upp till 72 timmar för kunders och partners e-postsystem att se den ändrade MX-posten. Vänta minst 72 timmar innan du går vidare till nästa uppgift: [steg 6: ta bort snabbmigrering](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).

### <a name="step-6-delete-the-cutover-migration-batch"></a>Steg 6: Ta bort snabbmigreringsbatchen
<a name="Bk_step6"> </a>

När du har ändrat MX-posten och kontrollerat att all e-post dirigeras till Microsoft 365-postlådor och meddelar användarna att deras e-post ska skickas till Microsoft 365. Därefter kan du ta bort snabbmigrering. Kontrollera följande innan du tar bort migreringsbatchen.

- Alla användare använder Microsoft 365-postlådor. När du har tagit bort gruppen kopieras inte e-post till post lådor på den lokala Exchange-servern till motsvarande Microsoft 365-postlådor.

- Microsoft 365-postlådor synkroniserades minst en gång efter att e-post började skickas direkt till dem. Det gör du genom att se till att värdet i rutan för den senast synkroniserade tiden för migreringstabellen är senare än när e-post som har börjat dirigeras direkt till Microsoft 365-postlådor.

Om du vill ta bort "CutoverBatch"-migreringsverktyget i Exchange Online PowerShell kör du följande kommando:

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>Avsnitt 7: Tilldela användar licenser
<a name="BK_Step7"> </a>

 **Aktivera Microsoft 365-användarkonton för de migrerade kontona genom att tilldela licenser.** Om du inte tilldelar en licens inaktiveras postlådan när tidsfristen löper ut (30 dagar). Information om hur du tilldelar en licens i administrations centret för Microsoft 365 finns i [tilldela eller ta bort licenser](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

### <a name="step-8-complete-post-migration-tasks"></a>Steg 8: slutföra uppgifter efter migreringen
<a name="BK_Step8"> </a>

- **Skapa en DNS-post för automatisk upptäckt så att användarna enkelt kan komma till sina postlådor.** När alla lokala post lådor har migrerats till Microsoft 365 kan du konfigurera en DNS-post för automatisk upptäckt för din Microsoft 365-organisation så att användarna enkelt kan ansluta till deras nya Microsoft 365-postlådor med Outlook-och mobila klienter. Den nya DNS-posten Autodiscover måste använda samma namn område som du använder för din Microsoft 365-organisation. Om ditt molnbaserade namnområde till exempel är cloud.contoso.com, behöver du skapa DNS-posten autodiscover.cloud.contoso.com.

    Om du behåller Exchange-servern bör du också se till att automatisk upptäckt av DNS CNAME-posten måste peka på Microsoft 365 i både intern och extern DNS efter migreringen så att Outlook-klienten ansluter till rätt post låda.

    > [!NOTE]
    >  I Exchange 2007, Exchange 2010 och Exchange 2013 ska du också ställa in `Set-ClientAccessServer AutodiscoverInternalConnectionURI` på `Null` .

    I Microsoft 365 används en CNAME-post för att implementera tjänsten för automatisk upptäckt för Outlook och mobila klienter. CNAME-posten för automatisk upptäckt måste innehålla följande information:

  - **Alias:** autodiscover

  - **Target:** autodiscover.outlook.com

    Mer information finns i [lägga till DNS-poster för att ansluta din domän](https://go.microsoft.com/fwlink/p/?LinkId=535028).

- **Inaktivera lokala Exchange-servrar.** När du har verifierat att all e-post dirigeras direkt till Microsoft 365-postlådor och du inte längre behöver underhålla den lokala e-postorganisationen eller inte planerar att implementera en lösning för enkel inloggning (SSO), kan du avinstallera Exchange från dina servrar och ta bort din lokala Exchange-organisation.

    Mer information finns i följande avsnitt:

  - [Ändra eller ta bort Exchange 2010](https://go.microsoft.com/fwlink/?LinkId=217936)

  - [Ta bort en Exchange 2007-organisation](https://go.microsoft.com/fwlink/?LinkID=100485)

  - [Avinstallera Exchange Server 2003](https://go.microsoft.com/fwlink/?LinkID=56561)


