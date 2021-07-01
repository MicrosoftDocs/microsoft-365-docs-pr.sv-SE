---
title: Använda PowerShell för att utföra en IMAP-migrering till Microsoft 365
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
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Lär dig hur du använder PowerShell för att utföra en IMAP-migrering (Internet Mail Access Protocol) till Microsoft 365.
ms.openlocfilehash: 679cf222d7474349907d1c21f38a30b5fd86f798
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229641"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>Använda PowerShell för att utföra en IMAP-migrering till Microsoft 365

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Som en del av distributionen av Microsoft 365 kan du välja att migrera innehållet i användarpostlådor från en E-posttjänst med IMAP (Internet Mail Access Protocol) till Microsoft 365. I den här artikeln får du hjälp med uppgifterna för en IMAP-migrering av e-post med hjälp Exchange Online PowerShell.

> [!NOTE]
> Du kan också använda Exchange för att utföra en IMAP-migrering. Se [Migrera dina IMAP-postlådor.](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Beräknad tid för att slutföra den här uppgiften: 2–5 minuter för att skapa en migreringsbatch. När migreringsbatchen har startats varierar varaktigheten för migreringen beroende på antalet postlådor i batchen, storleken på varje postlåda och din tillgängliga nätverkskapacitet. Information om andra faktorer som påverkar hur lång tid det tar att migrera postlådor till Microsoft 365 finns i [Migreringsprestanda.](/Exchange/mailbox-migration/office-365-migration-best-practices)

Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna. Du kan se vilka behörigheter du behöver i migreringsposten i en tabell i [avsnittet Behörigheter för](/exchange/recipients-permissions-exchange-2013-help) mottagare.

Om du vill Exchange Online för PowerShell-cmdlets måste du logga in och importera cmdletarna i dina lokala Windows PowerShell session. Instruktioner [Anslut finns Exchange Online använda fjärr-PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)

Följande begränsningar gäller för IMAP-migreringar:

- Endast objekt i en användares inkorg eller andra e-postmappar kan migreras. Du kan inte migrera kontakter, kalenderobjekt eller uppgifter.

- Maximalt 500 000 objekt kan migreras från en användares postlåda.

- Maximal meddelandestorlek som kan migreras är 35 MB.

## <a name="migration-steps"></a>Migreringssteg

### <a name="step-1-prepare-for-an-imap-migration"></a>Steg 1: Förbereda en IMAP-migrering
<a name="BK_Step1"> </a>

- **Om du har en domän för din IMAP-organisation lägger du till den som en godkänd domän i Microsoft 365 organisation.** Om du vill använda samma domän som du redan äger för dina Microsoft 365-postlådor måste du först lägga till den som en godkänd domän för att Microsoft 365. När du har lagt till den kan du skapa dina användare i Microsoft 365. Mer information finns i[Verifiera din domän.](../admin/setup/add-domain.md)

- **Lägg till alla användare Microsoft 365 så att de har en postlåda.** Anvisningar finns i Lägga[till användare i Microsoft 365 för företag.](../admin/add-users/add-users.md)

- **Hämta FQDN för IMAP-servern**. Du måste ange det fullständiga kvalificerade domännamnet (FQDN) (det fullständiga datornamnet) för IMAP-servern som du ska migrera e-postdata från när du skapar en IMAP-migreringsslutpunkt. Använd en IMAP-klient eller kommandot PING och kontrollera att du kan använda det fullständiga domännamnet för att kommunicera med IMAP-servern över Internet.

- **Konfigurera brandväggen så att IMAP-anslutningar tillåts.** Du kanske måste öppna portar i brandväggen för den organisation som är värd för IMAP-servern så att nätverkstrafik som kommer från Microsoft-datacentret under migreringen tillåts att ange organisationen som är värd för IMAP-servern. En lista över IP-adresser som används av Microsofts datacenter finns i Exchange Online [URL:er och IP-adressintervall.](./urls-and-ip-address-ranges.md)

- **Tilldela administratörskontobehörigheter för åtkomst till postlådor i din IMAP-organisation.** Om du använder administratörsautentiseringsuppgifter i CSV-filen måste det konto som du använder ha nödvändig åtkomstbehörighet till de lokala postlådorna. Vilka behörigheter som krävs för att få åtkomst till användarnas postlådor bestäms av den specifika IMAP-servern.

- **Om du vill använda Exchange Online PowerShell-cmdlets** måste du logga in och importera cmdletarna till den lokala Windows PowerShell-sessionen. Instruktioner [Anslut finns Exchange Online använda fjärr-PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

    En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)

- **Kontrollera att du kan ansluta till din IMAP-server.** Kör följande kommando i Exchange Online PowerShell för att testa anslutningsinställningarna till din IMAP-server.

  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    För parameterns  värde är det vanligt att använda 143 för okrypterade anslutningar eller TLS-anslutningar (Transport Layer Security) och att använda 993 för SSL-anslutningar.

### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>Steg 2: Skapa en CSV-fil för en IMAP-migreringsbatch
<a name="BK_Step2"> </a>

Identifiera den grupp användare vars postlådor du vill migrera i en IMAP-migreringsbatch. Varje rad i CSV-filen innehåller information som behövs för att ansluta till en postlåda i IMAP-meddelandesystemet.

Här är de obligatoriska attributen för varje användare:

- **EmailAddress** anger användar-ID:t för användarens e Microsoft 365 postlåda.

- **UserName** anger inloggningsnamnet för kontot som ska användas för att få åtkomst till postlådan på IMAP-servern.

- **Lösenord** anger lösenordet för kontot i **kolumnen Användarnamn.**

Här följer ett exempel på CSV-filens format. I det här exemplet migreras tre postlådor:

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

För **attributet UserName** kan du, förutom användarnamnet, använda autentiseringsuppgifterna för ett konto som har tilldelats nödvändiga behörigheter för att komma åt postlådor på IMAP-servern. Nedan följer några av de specifika format som används för vissa IMAP-servrar:

 **Microsoft Exchange:**

Om du migrerar e-post från IMAP-implementeringen för Microsoft Exchange använder du formatet **Domain/Admin_UserName/User_UserName** för attributet **UserName** i CSV-filen. Säg att du migrerar e-post från Exchange för Terry Adams, Ann Beebe och Paul Cannon. Du har ett e-postadministratörskonto, där användarnamnet är **mailadmin** och lösenordet **är P \@ ssw0rd**. Så här skulle CSV-filen se ut:

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot:**

För IMAP-servrar som stöder SASL (Simple Authentication and Security Layer), till exempel en Dovecot-IMAP-server, använder du formatet **User_UserName*Admin_UserName**, där asterisken ( * ) är ett konfigurerbart avgränsningstecken. Säg att du migrerar samma användares e-post från en Dovecot IMAP-server med administratörsautentiseringsuppgifterna **mailadmin** och **P \@ ssw0rd**. Så här skulle CSV-filen se ut:

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint:**

Om du migrerar e-post från Mirapoint Message Server använder du formatet **#user \@ domän#Admin_UserName#** som administratörsautentiseringsuppgifter. Om du vill migrera e-post från Mirapoint med administratörsautentiseringsuppgifterna **mailadmin** och **P \@ ssw0rd** skulle CSV-filen se ut så här:

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP:**

Vissa käll-e-postsystem, till exempel Courier IMAP, stöder inte användning av autentiseringsuppgifter som administratör för postlådan för att migrera postlådor till Microsoft 365. I stället kan du konfigurera käll-e-postsystemet till att använda virtuella delade mappar. Genom att använda virtuella delade mappar kan du använda postlådans administratörsuppgifter för att få åtkomst till användarnas postlådor i käll-e-postsystemet. Mer information om hur du konfigurerar virtuella delade mappar för Courier IMAP finns i [Delade mappar](https://go.microsoft.com/fwlink/p/?LinkId=398870).

Om du vill migrera postlådor när du har konfigurerat virtuella delade mappar på ditt käll-e-postsystem måste du ta med det valfria attributet **UserRoot** i migreringsfilen. Attributet anger platsen för varje användares postlåda i strukturen med virtuella delade mappar på käll-e-postsystemet. Sökvägen till Terrys postlåda är till exempel /users/terry.adams.

Här är ett exempel på en CSV-fil som innehåller attributet **UserRoot**:

```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>Steg 3: Skapa en IMAP-migreringsslutpunkt
<a name="BK_Step3"> </a>

Om du vill migrera e-Microsoft 365 måste du ansluta till och kommunicera med käll-e-postsystemet. För att göra det Microsoft 365 en migreringsslutpunkt. Migreringsslutpunkten definierar också antalet postlådor som ska migreras samtidigt och antalet postlådor som ska synkroniseras samtidigt under stegvis synkronisering, som sker en gång per dygn. Om du vill skapa en migreringsslutpunkt för IMAP-migrering [måste du först ansluta till Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

En fullständig lista över migreringskommandon finns i [Flytta och migrera cmdlets.](/powershell/exchange/)

Om du vill skapa slutpunkten för IMAP-migrering med namnet "IMAPEndpoint" i Exchange Online PowerShell kör du följande kommando:

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

Du kan också lägga till parametrar för att ange samtidig migrering, samtidig stegvis migrering och den port som ska användas. Följande PowerShell Exchange Online kommando skapar en IMAP-migreringsslutpunkt som kallas "IMAPEndpoint" som stöder 50 samtidiga migreringar och upp till 25 samtidiga stegvisa synkroniseringar. Slutpunkten konfigureras också att använda port 143 för TLS-kryptering.

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

Mer information om **cmdleten New-MigrationEndpoint** finns i [New-MigrationEndpoint.](/powershell/module/exchange/new-migrationendpoint)

#### <a name="verify-it-worked"></a>Kontrollera att det fungerade

Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPEndpoint":

```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>Steg 4: Skapa och starta en IMAP-migreringsbatch
<a name="BK_Step4"> </a>

Du kan använda cmdleten [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) för att skapa en migreringsbatch för en IMAP-migrering. Du kan skapa en migreringsbatch och starta den automatiskt genom att ta med _parametern AutoStart._ Alternativt kan du skapa migreringsbatchen och sedan starta den efteråt med hjälp av cmdleten[Start-MigrationBatch.](/powershell/module/exchange/start-migrationbatch)

Följande Exchange Online PowerShell-kommando startar automatiskt migreringsbatchen "IMAPBatch1" med hjälp av IMAP-slutpunkten som kallas "IMAPEndpoint":

```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>Kontrollera att det fungerade

Kör [cmdleten Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) för att visa information om "IMAPBatch1":

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

Du kan också kontrollera att batchen har startats genom att köra följande kommando:

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Steg 5: Dirigera din e-post till Microsoft 365
<a name="BK_Step5"> </a>

Email systems use a DNS record called an MX record to figure out where to deliver emails. Under e-postmigreringsprocessen pekade MX-posten på ditt käll-e-postsystem. Nu när e-postmigrering till Microsoft 365 är slutförd är det dags att peka MX-posten på Microsoft 365. Då ser du till att e-posten levereras till Microsoft 365 postlådor. Genom att flytta MX-posten kan du också stänga av ditt gamla e-postsystem när du är redo.

För många DNS-leverantörer finns det särskilda anvisningar för hur du ändrar MX-posten. Om din DNS-värd inte finns med eller om du bara allmänt vill se hur anvisningarna ser ut, finns det även [allmänna anvisningar för MX-posten](https://go.microsoft.com/fwlink/?LinkId=397449).

Det kan ta upp till 72 timmar för kunders och partners e-postsystem att se den ändrade MX-posten. Vänta i minst 72 timmar innan du går vidare till nästa uppgift: Steg 6: Ta bort IMAP-migreringsbatch.

### <a name="step-6-delete-imap-migration-batch"></a>Steg 6: Ta bort IMAP-migreringsbatchen
<a name="BK_Step6"> </a>

När du har ändrat MX-posten och verifierat att all e-post dirigeras till Microsoft 365 postlådorna meddelar du användarna att deras e-post kommer att Microsoft 365. Därefter kan du ta bort IMAP-migreringsbatchen. Kontrollera följande innan du tar bort migreringsbatchen.

- Alla användare använder en Microsoft 365 postlådor. När batchen tagits bort kopieras inte e-post som skickas till postlådorna Exchange Server lokala postlådorna till motsvarande Microsoft 365 postlådor.

- Microsoft 365 postlådorna synkroniserades minst en gång efter att e-posten började skickas direkt till dem. Det gör du genom att kontrollera att värdet i rutan Senast synkroniserad tid för migreringsbatchen är senare än när e-posten började dirigeras direkt till Microsoft 365 postlådor.

Om du vill ta bort migreringsbatchen "IMAPBatch1" från Exchange Online PowerShell kör du följande kommando:

```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

Mer information om cmdleten **Remove-MigrationBatch** finns i [Remove-MigrationBatch.](/powershell/module/exchange/remove-migrationbatch)

#### <a name="verify-it-worked"></a>Kontrollera att det fungerade

Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPBatch1":

```powershell
Get-MigrationBatch IMAPBatch1"
```

Kommandot returnerar antingen migreringsbatchen med statusen Ta **bort,** eller så returneras ett felmeddelande om att migreringsbatchen inte kunde hittas och verifierar att batchen har tagits bort.

Mer information om cmdleten **Get-MigrationBatch** finns i [Get-MigrationBatch.](/powershell/module/exchange/get-migrationbatch)

## <a name="see-also"></a>Se även

[Felsökare för IMAP-migrering](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)