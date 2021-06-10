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
description: Lär dig hur du använder PowerShell för att flytta innehåll från ett käll-e-postsystem över tid med hjälp av en stegad migrering till Microsoft 365.
ms.openlocfilehash: 0c93de181c54fb1c4021d23d787b63577317aad4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924798"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Använda PowerShell för att utföra en stegvis migrering till Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan migrera innehållet i användarpostlådor från ett källsystem för e-Microsoft 365 över tid med hjälp av en sådan migrering.
  
I den här artikeln får du hjälp med de olika uppgifterna som ingår i en sådan e-postmigrering Exchange Online PowerShell. I avsnittet Vad [du behöver veta om en sådan e-postmigrering](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration)får du en översikt över migreringsprocessen. När du har bekantat dig med innehållet i den artikeln kan du använda den här för att börja migrera postlådor från ett e-postsystem till ett annat.
  
> [!NOTE]
> Du kan också använda Exchange för att utföra en stegad migrering. Mer [information finns i Utföra en stegad migrering av e-post till Microsoft 365](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Beräknad tid för att slutföra den här uppgiften: 2–5 minuter för att skapa en migreringsbatch. När migreringsbatchen har startats varierar varaktigheten för migreringen beroende på antalet postlådor i batchen, storleken på varje postlåda och din tillgängliga nätverkskapacitet. Information om andra faktorer som påverkar hur lång tid det tar att migrera postlådor till Microsoft 365 finns i [Migreringsprestanda.](/Exchange/mailbox-migration/office-365-migration-best-practices)
  
Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna. Du kan se vilka behörigheter du behöver i migreringsposten i [avsnittet Behörigheter för](/exchange/recipients-permissions-exchange-2013-help) mottagare.
  
Om du vill Exchange Online för PowerShell-cmdlets måste du logga in och importera cmdletarna i dina lokala Windows PowerShell session. Instruktioner [Anslut finns Exchange Online använda fjärr-PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)
  
En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)
  
## <a name="migration-steps"></a>Migreringssteg

### <a name="step-1-prepare-for-a-staged-migration"></a>Steg 1: Förbereda en stegvis migrering

Innan du migrerar postlådor Microsoft 365 migrering genom en stegad migrering finns det några ändringar du måste göra i Exchange miljö.
  
 **Konfigurera Outlook överallt på din lokala Exchange Server** E-postmigreringstjänsten använder Outlook överallt (som även kallas RPC över HTTP) för att ansluta till din lokala Exchange Server. Mer information om hur du 2007 Outlook finns i Exchange Server 2007 och Exchange 2003 finns i:
  
- [Exchange 2007: Aktivera Outlook överallt](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))
    
- [Konfigurera Outlook överallt med Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))
    
> [!IMPORTANT]
> Du måste använda ett certifikat som utfärdats av en pålitlig certifikatutfärdare (CA) med din Outlook överallt-konfiguration. Outlook överallt kan inte konfigureras med ett självsignerat certifikat. Mer information finns i [Konfigurera SSL för Outlook överallt](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)). 
  
 **Valfritt: Kontrollera att du kan ansluta till din Exchange-organisation med Outlook överallt** Prova någon av följande metoder för att testa dina anslutningsinställningar.
  
- Använd Outlook utanför företagets nätverk för att ansluta till den lokala Exchange postlådan.
    
- Använd [Microsoft Analysverktyg för fjärranslutning för](https://https://testconnectivity.microsoft.com/) att testa dina anslutningsinställningar. Använd Outlook överallt (RPC över HTTP) eller Outlook Automatisk upptäckt av tester.
    
- Kör följande kommandon i Exchange Online PowerShell:
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **Ange behörigheter** Det lokala användarkonto som du använder för att ansluta till din lokala Exchange-organisation (kallas även migreringsadministratör) måste ha nödvändiga behörigheter för att få åtkomst till de lokala postlådor som du vill migrera till Microsoft 365. Det här användarkontot används när du ansluter till ditt e-postsystem genom att skapa en migreringsslutpunkt senare i den här proceduren ( Steg[3: Skapa en migreringsslutpunkt](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ).
  
För att kunna migrera postlådor måste administratören ha någon av följande behörigheter:
  
- Bli medlem i **gruppen Domänadministratörer** i Active Directory i den lokala organisationen.
    
    eller
    
- Tilldelas **FullAccess-behörighet** för varje lokal postlåda och **WriteProperty-behörighet** att ändra **egenskapen TargetAddress** på de lokala användarkontona.
    
    eller
    
- Tilldelas **Receive As-behörighet** på den lokala postlådedatabas där användarpostlådorna lagras och **writeProperty-behörigheten** att ändra **egenskapen TargetAddress** på de lokala användarkontona.
    
Anvisningar om hur du anger behörigheterna finns i Tilldela [behörigheter för att migrera postlådor till Microsoft 365.](/Exchange/mailbox-migration/assign-permissions-for-migration)
  
 **Inaktivera Unified Messaging (UM)** Om UM är aktiverat för de lokala postlådorna som du migrerar, stänger du av UM före migreringen. Aktivera UM för postlådorna när migreringen är klar. Instruktioner finns i Inaktivera[Unified Messaging.](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80))
  
 **Använd katalogsynkronisering för att skapa nya användare i Microsoft 365.** Du använder katalogsynkronisering för att skapa alla lokala användare i Microsoft 365 organisation.
  
Du måste licensiera användarna när de har skapats. Du har 30 dagar på dig att lägga till licenser efter att användarna skapats. Information om hur du lägger till licenser finns [i Steg 8: Slutför uppgifter efter migreringen.](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration)
  
 Du kan använda synkroniseringsverktyget för Microsoft Azure Active Directory (Azure AD) eller Microsoft Azure AD-synkroniseringstjänster för att synkronisera och skapa dina lokala användare i Microsoft 365. När postlådor migreras till Microsoft 365 hanterar du användarkonton i den lokala organisationen och de synkroniseras med din Microsoft 365 organisation. Mer information finns i[Katalogintegrering](/previous-versions/azure/azure-services/jj573653(v=azure.100)) .
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>Steg 2: Skapa en CSV-fil för en stegvis migreringsbatch

När du har identifierat de användare vars lokala postlådor du vill migrera till Microsoft 365, använder du en CSV-fil (kommaavgränsade värden) för att skapa en migreringsbatch. Varje rad i CSV-filen – som används Microsoft 365 för att köra migreringen – innehåller information om en lokal postlåda. 
  
> [!NOTE]
> Det finns ingen gräns för antalet postlådor som du kan migrera till Microsoft 365 med en stegmigrering. CSV-filen för en migreringsbatch rymmer högst 2 000 rader. Om du vill migrera fler än 2 000 postlådor måste du skapa ytterligare CSV-filer och använda varje fil för att skapa en ny batch. 
  
 **Attribut som stöds**
  
CSV-filen för en stegvis migrering har stöd för följande tre attribut. Varje rad i CSV-filen motsvarar en postlåda och måste innehålla ett värde för vart och ett av de här attributen.
  
|**Attribut**|**Beskrivning**|**Obligatorisk**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |Anger den primära SMTP-e-postadressen, till exempel pilarp@contoso.com, för lokala postlådor.  <br/> Använd den primära SMTP-adressen för lokala postlådor och inte användar-IDt från Microsoft 365. Om den lokala domänen heter contoso.com men Microsoft 365-e-postdomänen heter service.contoso.com använder du contoso.com-domännamnet för e-postadresser i CSV-filen.  <br/> |Obligatoriskt  <br/> |
|Lösenord  <br/> |Det lösenord som anges för den nya e Microsoft 365 postlådan. Alla lösenordsbegränsningar som tillämpas på Microsoft 365 organisationen gäller även lösenorden som ingår i CSV-filen.  <br/> |Valfri  <br/> |
|ForceChangePassword  <br/> |Anger om användaren måste ändra lösenord första gången han eller hon loggar in till sin nya e Microsoft 365 postlåda. Använd **True** eller **False** för den här parameterns värde. <br/> > [!NOTE]> Om du har implementerat en lösning för enkel inloggning (SSO) genom att distribuera AD FS (Active Directory Federation Services) eller större i den lokala organisationen måste du använda **False** för värdet på **ForceChangePassword-attributet.**          |Valfri  <br/> |
   
 **CSV-filformat**
  
Här följer ett exempel på CSV-filens format. I det här exemplet migreras tre lokala postlådor till Microsoft 365.
  
CSV-filens första rad, eller rubrikraden, visar namnen på de attribut, eller fält, som anges i de följande raderna. Varje attributnamn avgränsas av ett kommatecken.
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

Varje rad under rubrikraden representerar en användare och ger den information som ska användas för att migrera användarens postlåda. Attributvärdena på varje rad måste vara placerade i samma ordning som attributnamnen på rubrikraden. 
  
Använd en textredigerare eller ett program som Excel för att skapa CSV-filen. Spara filen som CSV eller TXT.
  
> [!NOTE]
> Om CSV-filen innehåller specialtecken eller andra tecken än ASCII-tecken sparar du CSV-filen med UTF-8-kodning eller annan Unicode-kodning. Beroende på vilket program du använder kan det vara enklare att spara CSV-filen med UTF-8-kodning eller annan Unicode-kodning när systemspråket på datorn matchar språket som används i CSV-filen. 
  
### <a name="step-3-create-a-migration-endpoint"></a>Steg 3: Skapa en migreringsslutpunkt
<a name="BK_Endpoint"> </a>

För att e-post ska Microsoft 365 kunna ansluta till och kommunicera med käll-e-postsystemet. För att göra det Microsoft 365 en migreringsslutpunkt. Om du vill skapa Outlook migreringsslutpunkt för var som helst med hjälp av PowerShell för steg-migrering [ska du först ansluta till Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell) 
  
En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)
  
Om du vill Outlook en migreringsslutpunkt för överallt som kallas "StagedEndpoint" i Exchange Online PowerShell kör du följande kommandon:
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

Mer information om **cmdleten New-MigrationEndpoint** finns i [New-MigrationEndpoint.](/powershell/module/exchange/new-migrationendpoint)
  
> [!NOTE]
> Cmdleten **New-MigrationEndpoint** kan användas för att ange en databas för tjänsten som ska användas med **alternativet -TargetDatabase.** Annars tilldelas en databas slumpmässigt från AD FS 2.0-webbplatsen (Active Directory Federation Services) där hanteringspostlådan finns.
  
#### <a name="verify-it-worked"></a>Kontrollera att det fungerade

I Exchange Online PowerShell kör du följande kommando för att visa information om migreringsslutpunkten "StagedEndpoint":
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>Steg 4: Skapa och starta en batch för stegvis migrering
<a name="BK_Endpoint"> </a>

Du kan använda **cmdleten New-MigrationBatch** i Exchange Online PowerShell för att skapa en migreringsbatch för en cutover-migrering. Du kan skapa en migreringsbatch och starta den automatiskt genom att ta med _parametern AutoStart._ Alternativt kan du skapa migreringsbatchen och sedan starta den manuellt efteråt med hjälp av cmdleten **Start-MigrationBatch.** Det här exemplet skapar en migreringsbatch med namnet "StagedBatch1" och använder migreringsslutpunkten som skapades i föregående steg.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

Det här exemplet skapar också en migreringsbatch med namnet "StagedBatch1" och använder migreringsslutpunkten som skapades i föregående steg. Eftersom _parametern AutoStart_ inte ingår måste migreringsbatchen startas manuellt på instrumentpanelen för migrering eller med hjälp av **cmdleten Start-MigrationBatch.** Som tidigare nämnts kan bara en batch för migreringsmigrering finnas i taget.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>Kontrollera att det fungerade

Kör följande kommando i Exchange Online PowerShell för att visa information om "StagedBatch1":
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

Du kan också kontrollera att batchen har startats genom att köra följande kommando:
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

Mer information om cmdleten **Get-MigrationBatch** finns i [Get-MigrationBatch.](/powershell/module/exchange/get-migrationbatch)
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>Steg 5: Konvertera lokala postlådor till e-postanvändare
<a name="BK_Endpoint"> </a>

När du har migrerat en grupp postlådor måste användarna kunna komma åt sin e-post. En användare vars postlåda har migrerats har nu både en postlåda lokalt och en i Microsoft 365. Användare som har en postlåda Microsoft 365 får inte nya e-postmeddelanden till sina lokala postlådor. 
  
Eftersom du inte är klar med dina migreringar än, kan du inte hänvisa alla användare till de Microsoft 365 för sin e-post. Vad gör man då med de personer som har båda postlådorna? En sak som du kan göra är att ändra de lokala postlådorna som du redan har migrerat till e-postanvändare. När du ändrar från postlåda till e-postanvändare kan du dirigera användaren till Microsoft 365 för sin e-post i stället för att gå till den lokala postlådan. 
  
En annan viktig anledning till att konvertera lokala postlådor till e-postanvändare är att man kan behålla proxyadresser från Microsoft 365-postlådorna genom att kopiera proxyadresser till e-postaktiverade användare. Med den här funktionen kan du hantera molnbaserade användare från din lokala organisation genom att använda Active Directory. Om du bestämmer dig för att inaktivera din lokala Exchange Server-organisation när alla postlådor har migrerats till Microsoft 365, finns proxyadresserna som du har kopierat till de e-postaktiverade användarna även kvar i din lokala Active Directory.
    
### <a name="step-6-delete-a-staged-migration-batch"></a>Steg 6: Ta bort en stegvis migreringsbatch
<a name="BK_Endpoint"> </a>

 När alla postlådor i en migreringsbatch har migrerats korrekt, och du har konverterat de lokala postlådorna i batchen till e-postaktiverade användare, är du redo att ta bort en stegad migreringsbatch. Kontrollera att e-post vidarebefordras till postlådorna Microsoft 365 postlådorna i migreringsbatchen. När du tar bort en stegad migreringsbatch rensar migreringstjänsten bort alla poster som är relaterade till migreringsbatchen och tar bort migreringsbatchen.
  
Om du vill ta bort migreringsbatchen "StagedBatch1" i Exchange Online PowerShell kör du följande kommando.
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

Mer information om cmdleten **Remove-MigrationBatch** finns i [Remove-MigrationBatch.](/powershell/module/exchange/remove-migrationbatch)
  
#### <a name="verify-it-worked"></a>Kontrollera att det fungerade

Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPBatch1":
  
```powershell
Get-MigrationBatch StagedBatch1
```

Kommandot returnerar antingen migreringsbatchen med statusen Ta **bort,** eller så returneras ett felmeddelande om att migreringsbatchen inte kunde hittas och verifierar att batchen har tagits bort.
  
Mer information om cmdleten **Get-MigrationBatch** finns i [Get-MigrationBatch.](/powershell/module/exchange/get-migrationbatch)
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a>Steg7: Tilldela licenser till Microsoft 365 användare
<a name="BK_Endpoint"> </a>

Aktivera Microsoft 365-postkonton för de migrerade kontona genom att tilldela licenser. Om du inte tilldelar en licens inaktiveras postlådan när tidsfristen löper ut (30 dagar). Information om hur du tilldelar en licens Microsoft 365 administrationscentret finns i [Tilldela eller ta bort licenser.](../admin/manage/assign-licenses-to-users.md)
  
### <a name="step-8-complete-post-migration-tasks"></a>Steg 8: Slutför uppgifter efter migreringen
<a name="BK_Postmigration"> </a>

- **Skapa en DNS-post för automatisk upptäckt så att användarna enkelt kan komma till sina postlådor.** När alla lokala postlådor har migrerats till Microsoft 365 kan du konfigurera en DNS-post för automatisk upptäckt för Microsoft 365-organisationen så att användarna enkelt kan ansluta till sina nya Microsoft 365-postlådor med Outlook och mobila klienter. Den nya DNS-posten för automatisk upptäckt måste använda samma namnområde som du använder för din Microsoft 365 organisation. Om ditt molnbaserade namnområde till exempel är cloud.contoso.com, behöver du skapa DNS-posten autodiscover.cloud.contoso.com.
    
    Microsoft 365 använder en CNAME-post för att implementera tjänsten för automatisk upptäckt för Outlook och mobila klienter. CNAME-posten för automatisk upptäckt måste innehålla följande information:
    
  - **Alias:** autodiscover
    
  - **Target:** autodiscover.outlook.com
    
    Mer information finns i Lägga [till DNS-poster för att ansluta din domän.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
- **Inaktivera lokala Exchange-servrar.** När du har verifierat att all e-post dirigeras direkt till Microsoft 365-postlådorna och du inte längre behöver underhålla din lokala e-postorganisation eller inte planerar att implementera en SSO-lösning, kan du avinstallera Exchange från servrarna och ta bort din lokala Exchange organisation.
    
    Mer information finns i följande avsnitt:
    
  - [Ändra eller ta bort Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))
    
  - [Ta bort en Exchange 2007-organisation](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))
    
  - [Avinstallera Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))
