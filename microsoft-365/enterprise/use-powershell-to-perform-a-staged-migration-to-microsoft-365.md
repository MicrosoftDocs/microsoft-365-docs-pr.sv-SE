---
title: Använda PowerShell för att utföra en stegvis migrering till Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: Lär dig hur du använder PowerShell för att flytta innehåll från ett käll-e-postsystem över tid med hjälp av en stegvis migrering till Microsoft 365.
ms.openlocfilehash: ebf2067fe7ae9fc2d2b58d0aa804c7843295b38a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694469"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Använda PowerShell för att utföra en stegvis migrering till Microsoft 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan migrera innehållet i användar post lådor från ett käll-e-postsystem till Microsoft 365 över tiden med en stegvis migrering.
  
I den här artikeln får du stegvisa instruktioner för hur du använder en stegvis e-postmigrering med Exchange Online PowerShell. I det här avsnittet får du en översikt över hur du migrerar [e-postmigreringen](https://go.microsoft.com/fwlink/p/?LinkId=536487). När du har bekantat dig med innehållet i den artikeln kan du använda den här för att börja migrera postlådor från ett e-postsystem till ett annat.
  
> [!NOTE]
> Du kan också använda administrations centret för Exchange för att utföra stegvis migrering. Se [utföra en stegvis migrering av e-post till Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536687). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Uppskattad tid för att slutföra den här uppgiften: 2-5 minuter för att skapa en migreringstabell. När migreringen har startat varierar varaktigheten för migreringen baserat på antalet post lådor i gruppen, storleken på varje post låda och din tillgängliga nätverks kapacitet. Information om andra faktorer som påverkar hur lång tid det tar att migrera post lådor till Microsoft 365 finns i [migreringens prestanda](https://go.microsoft.com/fwlink/p/?LinkId=275079).
  
Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna. Om du vill se vilka behörigheter du behöver läser du "migration"-posten i avsnittet [mottagare](https://go.microsoft.com/fwlink/p/?LinkId=534105) .
  
För att använda PowerShell-cmdletar för Exchange Online måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session. Se [ansluta till Exchange Online med Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) för instruktioner.
  
En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
## <a name="migration-steps"></a>Migreringsåtgärder

### <a name="step-1-prepare-for-a-staged-migration"></a>Steg 1: förbereda en stegvis migrering

Innan du migrerar post lådor till Microsoft 365 med en stegvis migrering finns det några ändringar du måste göra i din Exchange-miljö.
  
 **Konfigurera Outlook överallt på din lokala Exchange Server** E-postmigreringstjänsten använder Outlook överallt (som även kallas RPC över HTTP) för att ansluta till din lokala Exchange Server. Information om hur du konfigurerar Outlook för Exchange Server 2007 och Exchange 2003 finns i följande avsnitt:
  
- [Exchange 2007: Aktivera Outlook överallt](https://go.microsoft.com/fwlink/?LinkID=167210)
    
- [Konfigurera Outlook överallt med Exchange 2003](https://go.microsoft.com/fwlink/?LinkID=167209)
    
> [!IMPORTANT]
> Du måste använda ett certifikat som utfärdats av en pålitlig certifikatutfärdare (CA) med din Outlook överallt-konfiguration. Outlook överallt kan inte konfigureras med ett självsignerat certifikat. Mer information finns i [Konfigurera SSL för Outlook överallt](https://go.microsoft.com/fwlink/?LinkID=80875). 
  
 **Valfritt: Kontrollera att du kan ansluta till din Exchange-organisation med Outlook överallt** Prova någon av följande metoder för att testa dina anslutningsinställningar.
  
- Använd Outlook utanför företagets nätverk för att ansluta till den lokala Exchange postlådan.
    
- Använd [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) för att testa dina anslutnings inställningar. Använd Outlook överallt (RPC över HTTP) eller Outlook Automatisk upptäckt av tester.
    
- Kör följande kommandon i Exchange Online PowerShell:
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **Ange behörigheter** Det lokala användar kontot som du använder för att ansluta till den lokala Exchange-organisationen (kallas även för administratör för migrering) måste ha nödvändig behörighet för att få åtkomst till de lokala post lådorna som du vill migrera till Microsoft 365. Det här användar kontot används när du ansluter till ditt e-postsystem genom att skapa en slut punkt för migrering senare i den här proceduren ([steg 3: skapa en migrerings slut punkt](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ).
  
För att kunna migrera postlådor måste administratören ha någon av följande behörigheter:
  
- Bli medlem i gruppen **Domain admins** i Active Directory i den lokala organisationen.
    
    eller
    
- Tilldelas **behörigheten Full Access** -behörighet för varje lokal post låda och **WriteProperty** -behörigheten för att ändra egenskapen **targetAddress** för lokala användar konton.
    
    eller
    
- Tilldelas behörigheten **Receive As** för den lokala post lådan som lagrar användar post lådor och **WriteProperty** -behörigheten för att ändra egenskapen **targetAddress** för lokala användar konton.
    
Anvisningar om hur du anger de här behörigheterna finns i [tilldela behörigheter för att migrera post lådor till Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=521656).
  
 **Inaktivera Unified Messaging (UM)** Om UM är aktiverat för de lokala postlådorna som du migrerar, stänger du av UM före migreringen. Aktivera UM för postlådorna när migreringen är klar. Instruktioner finns i[inaktivera Unified Messaging](https://go.microsoft.com/fwlink/?LinkId=521891).
  
 **Använd katalog-synkronisering för att skapa nya användare i Microsoft 365.** Du använder katalog synkronisering för att skapa alla lokala användare i din Microsoft 365-organisation.
  
Du måste licensiera användarna efter att de har skapats. Du har 30 dagar på dig att lägga till licenser efter att användarna skapats. Anvisningar för hur du lägger till licenser finns i [steg 8: slutföra uppgifter efter migreringen](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).
  
 Du kan använda Microsoft Azure Active Directory-synkroniseringsfunktionen (Azure AD) eller Microsoft Azure AD Sync Services för att synkronisera och skapa lokala användare i Microsoft 365. När post lådor har migrerats till Microsoft 365 kan du hantera användar konton i din lokala organisation och de synkroniseras med din Microsoft 365-organisation. Mer information finns i[katalog integrering](https://go.microsoft.com/fwlink/?LinkId=521788) .
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>Steg 2: skapa en CSV-fil för ett batchjobb med stegvis migrering

När du har identifierat de användare vars lokala post lådor du vill migrera till Microsoft 365 använder du en CSV-fil (kommaseparerade värden) för att skapa en migreringstabell. Varje rad i CSV-filen – som används av Microsoft 365 för att köra migreringen – innehåller information om en lokal post låda. 
  
> [!NOTE]
> Det finns inte någon begränsning för hur många post lådor du kan migrera till Microsoft 365 med en stegvis migrering. CSV-filen för en migreringsbatch rymmer högst 2 000 rader. Om du vill migrera fler än 2 000 postlådor måste du skapa ytterligare CSV-filer och använda varje fil för att skapa en ny batch. 
  
 **Attribut som stöds**
  
CSV-filen för en stegvis migrering har stöd för följande tre attribut. Varje rad i CSV-filen motsvarar en postlåda och måste innehålla ett värde för vart och ett av de här attributen.
  
|**Attribut**|**Beskrivning**|**Obligatorisk**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |Anger den primära SMTP-e-postadressen, till exempel pilarp@contoso.com, för lokala postlådor.  <br/> Använd den primära SMTP-adressen för lokala post lådor och inte användar-ID: n från Microsoft 365. Om den lokala domänen till exempel heter contoso.com men Microsoft 365-e-postdomänen heter service.contoso.com, använder du contoso.com domän namn för e-postadresser i CSV-filen.  <br/> |Obligatoriskt  <br/> |
|Lösenord  <br/> |Lösen ordet som ska anges för den nya Microsoft 365-postlådan. Eventuella lösen ords begränsningar som gäller för Microsoft 365-organisationen gäller också för lösen ord som ingår i CSV-filen.  <br/> |Valfri  <br/> |
|ForceChangePassword  <br/> |Anger om en användare måste ändra lösen ordet första gången de loggar in i sin nya Microsoft 365-postlåda. Använd **True** eller **False** för den här parameterns värde. <br/> > [!NOTE]> om du har implementerat en lösning för enkel inloggning (SSO) genom att distribuera Active Directory Federation Services (AD FS) eller större i din lokala organisation, måste du använda **falskt** för värdet för attributet **ForceChangePassword** .          |Valfri  <br/> |
   
 **CSV-filformat**
  
Här följer ett exempel på CSV-filens format. I det här exemplet migreras tre lokala post lådor till Microsoft 365.
  
CSV-filens första rad, eller rubrikraden, visar namnen på de attribut, eller fält, som anges i de följande raderna. Varje attributnamn avgränsas av ett kommatecken.
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

Varje rad under rubrikraden representerar en användare och ger den information som ska användas för att migrera användarens postlåda. Attributvärdena på varje rad måste vara placerade i samma ordning som attributnamnen på rubrikraden. 
  
Använd valfri text redigerare eller ett program som Excel för att skapa CSV-filen. Spara filen som CSV eller TXT.
  
> [!NOTE]
> Om CSV-filen innehåller specialtecken eller andra tecken än ASCII-tecken sparar du CSV-filen med UTF-8-kodning eller annan Unicode-kodning. Beroende på programmet kan det vara enklare att spara CSV-filen med UTF-8 eller annan Unicode-kodning när datorns system språk matchar det språk som används i CSV-filen. 
  
### <a name="step-3-create-a-migration-endpoint"></a>Steg 3: skapa en slut punkt för migrering
<a name="BK_Endpoint"> </a>

För att migrera e-post måste Microsoft 365 ansluta och kommunicera med käll-e-postsystemet. För att göra det, använder Microsoft 365 en slut punkt för migrering. Om du vill skapa en uppgraderings slut punkt för Outlook överallt med PowerShell, för stegvis migrering, [ansluter du först till Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121). 
  
En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
Om du vill skapa en migrerings slut punkt för Outlook överallt med namnet "StagedEndpoint" i Exchange Online PowerShell kör du följande kommandon:
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

Mer information om **New-MigrationEndpoint** -cmdleten finns i[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).
  
> [!NOTE]
> Cmdleten **New-MigrationEndpoint** kan användas för att ange en databas som ska användas med alternativet **-TargetDatabase** . I annat fall tilldelas en databas slumpmässigt från AD FS-2,0 (Active Directory Federation Services) där hanterings post lådan finns.
  
#### <a name="verify-it-worked"></a>Verifiera att den fungerade

I Exchange Online PowerShell kör du följande kommando för att visa information om "StagedEndpoint"-slut punkt för migrering:
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>Steg 4: skapa och starta ett batchjobb för en fas
<a name="BK_Endpoint"> </a>

Du kan använda cmdleten **New-MigrationBatch** i Exchange Online PowerShell för att skapa en migreringstabell för en snabbmigrering-migrering. Du kan skapa en migreringstabell och starta den automatiskt genom att inkludera _Autostart_ -parametern. Alternativt kan du skapa migreringstabellen och sedan starta den manuellt med hjälp av cmdleten **Start-MigrationBatch** . I det här exemplet skapas ett migreringsarkiv med namnet "StagedBatch1" och används den slut punkt som skapades i föregående steg.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

I det här exemplet skapas en migreringstabell med namnet "StagedBatch1" och används den migrerings slut punkt som skapades i föregående steg. Eftersom den  _Autostart_ -parametern inte är inkluderad måste migreringsverktyget startas manuellt på kontroll panelen för migreringen eller genom att använda cmdleten **Start-MigrationBatch** . Som tidigare angiven kan bara en snabbmigrering för migrering finnas åt gången.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>Verifiera att den fungerade

Kör följande kommando i Exchange Online PowerShell för att visa information om "StagedBatch1":
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

Du kan också kontrol lera att batchjobbet har startat genom att köra följande kommando:
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

Mer information om cmdleten **Get-MigrationBatch** finns i[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>Steg 5: konvertera lokala post lådor till e-postaktiverade användare
<a name="BK_Endpoint"> </a>

När du har migrerat en grupp postlådor måste användarna kunna komma åt sin e-post. En användare vars post låda har migrerats har nu både en post låda och en i Microsoft 365. Användare som har en post låda i Microsoft 365 slutar att få ny e-post i sin lokala post låda. 
  
Eftersom du inte är uppkopplad med dina migreringar är du inte redo att direkt dirigera alla användare till Microsoft 365 för deras e-post. Vad gör man då med de personer som har båda postlådorna? En sak som du kan göra är att ändra de lokala postlådorna som du redan har migrerat till e-postanvändare. När du ändrar från en post låda till en e-postaktiverad användare kan du dirigera användaren till Microsoft 365 för e-post i stället för att gå till den lokala post lådan. 
  
En annan viktig anledning att konvertera lokala post lådor till e-postaktiverade användare är att behålla proxyadresser från Microsoft 365-postlådor genom att kopiera proxyadresser till e-postaktiverade användare. Med den här funktionen kan du hantera molnbaserade användare från din lokala organisation genom att använda Active Directory. Om du bestämmer dig för att inaktivera din lokala Exchange Server-organisation efter att alla post lådor har migrerats till Microsoft 365, kommer de proxyservrar som du har kopierat till e-postaktiverade användare att bevaras i din lokala Active Directory.
    
### <a name="step-6-delete-a-staged-migration-batch"></a>Steg 6: ta bort batchen för stegvis migrering
<a name="BK_Endpoint"> </a>

 När alla post lådor i en migreringstabell har migrerats och du har konverterat de lokala post lådorna i gruppen till e-postaktiverade användare är det dags att ta bort ett batchjobb för stegvis migrering. Kontrol lera att e-post vidarekopplas till Microsoft 365-postlådor i fältet migration. När du tar bort ett batchjobb för stegvis migrering rensar migreringsguiden alla poster relaterade till migreringsverktyget och tar bort migreringsverktyget.
  
Om du vill ta bort batchjobbet "StagedBatch1" i Exchange Online PowerShell kör du följande kommando.
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

Mer information om cmdleten **Remove-MigrationBatch** finns i[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).
  
#### <a name="verify-it-worked"></a>Verifiera att den fungerade

Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPBatch1":
  
```powershell
Get-MigrationBatch StagedBatch1
```

Kommandot returnerar antingen migreringsarkivet med **statusen borttagen**eller returnerar ett fel meddelande som säger att det inte gick att hitta den Överflyttnings journal som verifierar att gruppen har tagits bort.
  
Mer information om cmdleten **Get-MigrationBatch** finns i[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a>Step7: tilldela licenser till Microsoft 365-användare
<a name="BK_Endpoint"> </a>

Aktivera Microsoft 365-användarkonton för de migrerade kontona genom att tilldela licenser. Om du inte tilldelar en licens inaktiveras postlådan när tidsfristen löper ut (30 dagar). Information om hur du tilldelar en licens i administrations centret för Microsoft 365 finns i [tilldela eller ta bort licenser](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).
  
### <a name="step-8-complete-post-migration-tasks"></a>Steg 8: slutföra uppgifter efter migreringen
<a name="BK_Postmigration"> </a>

- **Skapa en DNS-post för automatisk upptäckt så att användarna enkelt kan komma till sina postlådor.** När alla lokala post lådor har migrerats till Microsoft 365 kan du konfigurera en DNS-post för automatisk upptäckt för din Microsoft 365-organisation så att användarna enkelt kan ansluta till deras nya Microsoft 365-postlådor med Outlook-och mobila klienter. Den nya DNS-posten Autodiscover måste använda samma namn område som du använder för din Microsoft 365-organisation. Om ditt molnbaserade namnområde till exempel är cloud.contoso.com, behöver du skapa DNS-posten autodiscover.cloud.contoso.com.
    
    I Microsoft 365 används en CNAME-post för att implementera tjänsten för automatisk upptäckt för Outlook och mobila klienter. CNAME-posten för automatisk upptäckt måste innehålla följande information:
    
  - **Alias:** autodiscover
    
  - **Target:** autodiscover.outlook.com
    
    Mer information finns i [lägga till DNS-poster för att ansluta din domän](https://go.microsoft.com/fwlink/p/?LinkId=535028).
    
- **Inaktivera lokala Exchange-servrar.** När du har verifierat att all e-post dirigeras direkt till Microsoft 365-postlådor och du inte längre behöver underhålla din lokala e-postorganisation eller inte tänker implementera en SSO-lösning kan du avinstallera Exchange från dina servrar och ta bort din lokala Exchange-organisation.
    
    Mer information finns i följande avsnitt:
    
  - [Ändra eller ta bort Exchange 2010](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [Ta bort en Exchange 2007-organisation](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [Avinstallera Exchange Server 2003](https://go.microsoft.com/fwlink/?LinkID=56561)
    

