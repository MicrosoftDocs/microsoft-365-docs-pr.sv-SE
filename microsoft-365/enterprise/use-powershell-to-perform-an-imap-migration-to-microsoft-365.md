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
ms.openlocfilehash: 6eb422455d0bdf31fa1859bd0231b68e5568748c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694738"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>Använda PowerShell för att utföra en IMAP-migrering till Microsoft 365

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Som en del av processen med att distribuera Microsoft 365 kan du välja att migrera innehållet i användar post lådor från en e-posttjänst via IMAP (Internet Mail Access Protocol) till Microsoft 365. I den här artikeln får du stegvisa instruktioner för ett e-postmeddelande med IMAP-migrering genom att använda Exchange Online PowerShell. 
  
> [!NOTE]
> Du kan också använda administrations centret för Exchange för att utföra en IMAP-migrering. Se [migrera dina IMAP-postlådor](https://go.microsoft.com/fwlink/p/?LinkId=536685). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

Uppskattad tid för att slutföra den här uppgiften: 2-5 minuter för att skapa en migreringstabell. När migreringen har startat varierar varaktigheten för migreringen baserat på antalet post lådor i gruppen, storleken på varje post låda och din tillgängliga nätverks kapacitet. Information om andra faktorer som påverkar hur lång tid det tar att migrera post lådor till Microsoft 365 finns i [migreringens prestanda](https://go.microsoft.com/fwlink/p/?LinkId=275079).
  
Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna. Om du vill se vilka behörigheter du behöver läser du "migration"-posten i en tabell i avsnittet [mottagare](https://go.microsoft.com/fwlink/p/?LinkId=534105) .
  
För att använda PowerShell-cmdletar för Exchange Online måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session. Se [ansluta till Exchange Online med Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) för instruktioner.
  
En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
Följande begränsningar gäller för IMAP-migreringar:
  
- Endast objekt i en användares inkorg eller andra e-postmappar kan migreras. Du kan inte migrera kontakter, Kalender objekt eller uppgifter.
    
- Högst 500 000 objekt kan migreras från en användares post låda.
    
- Maximal meddelande storlek som kan migreras är 35 MB.
    
## <a name="migration-steps"></a>Migreringsåtgärder

### <a name="step-1-prepare-for-an-imap-migration"></a>Steg 1: förbereda en IMAP-migrering
<a name="BK_Step1"> </a>

- **Om du har en domän för IMAP-organisation lägger du till den som en godkänd domän i din Microsoft 365-organisation.** Om du vill använda samma domän som du redan äger för dina Microsoft 365-postlådor måste du först lägga till den som godkänd domän i Microsoft 365. När du har lagt till den kan du skapa användare i Microsoft 365. Mer information finns i[Verifiera din domän](https://go.microsoft.com/fwlink/p/?LinkId=534110).
    
- **Lägg till varje användare i Microsoft 365 så att de har en post låda.** Anvisningar finns i[lägga till användare i Microsoft 365 för företag](https://go.microsoft.com/fwlink/p/?LinkId=535065).
    
- **Skaffa IMAP-serverns FQDN**. Du måste ange det fullständigt kvalificerade domän namnet (FQDN) (kallas även det fullständiga dator namnet) för IMAP-servern som du migrerar post lådor från när du skapar en slut punkt för IMAP-migrering. Använd en IMAP-klient eller kommandot PING och kontrollera att du kan använda det fullständiga domännamnet för att kommunicera med IMAP-servern över Internet.
    
- **Konfigurera brand väggen för att tillåta IMAP-anslutningar**. Du kanske måste öppna portar i brand väggen för organisationen som är värd för IMAP-servern så att nätverks trafik från Microsoft-datacentret under migreringen tillåts ange den organisation som är värd för IMAP-servern. En lista med IP-adresser som används av Microsoft Data Center finns i [URL: er och IP-adressintervall för Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=535066).
    
- **Tilldela administratörs konto behörigheter till post lådor i IMAP-organisationen**. Om du använder administratörsautentiseringsuppgifter i CSV-filen måste det konto som du använder ha nödvändig åtkomstbehörighet till de lokala postlådorna. De behörigheter som krävs för att komma åt användar post lådorna bestäms av den specifika IMAP-servern. 
    
- **För att använda PowerShell-cmdletar för Exchange Online**måste du logga in och importera cmdletarna till din lokala Windows PowerShell-session. Se [ansluta till Exchange Online med Remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) för instruktioner.
    
    En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).
    
- **Kontrol lera att du kan ansluta till IMAP-servern**. Kör följande kommando i Exchange Online PowerShell för att testa anslutnings inställningarna till IMAP-servern.
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    För värdet på parametern **port** är det normalt att använda 143 för okrypterade eller TLS-anslutningar (Transport Layer Security) och för att använda 993 för SSL-anslutningar.
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>Steg 2: skapa en CSV-fil för en IMAP-migrering
<a name="BK_Step2"> </a>

Identifiera gruppen med användare vars post lådor du vill migrera i ett batchjobb för IMAP-migrering. Varje rad i CSV-filen innehåller information som behövs för att ansluta till en post låda i IMAP Messaging system.
  
Här är de obligatoriska attributen för varje användare: 
  
- **EmailAddress** anger användar-ID: t för användarens Microsoft 365-postlåda.
    
- **Username** anger namnet på det konto som ska användas för att komma åt post lådan på IMAP-servern.
    
- **Lösen ord** anger lösen ordet för kontot i kolumnen **username** .
    
Här följer ett exempel på CSV-filens format. I det här exemplet migreras tre post lådor:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

För attributet **username** kan du förutom användar namnet använda autentiseringsuppgifterna för ett konto som har tilldelats nödvändiga behörigheter för att komma åt post lådor på IMAP-servern, men följande är några av de specifika format som används för vissa IMAP-servrar:
  
 **Microsoft Exchange:**
  
Om du migrerar e-post från IMAP-implementeringen för Microsoft Exchange använder du formatet **Domain/Admin_UserName/User_UserName** för attributet **UserName** i CSV-filen. Säg att du migrerar e-post från Exchange för Terry Adams, Ann Beebe och Paul Cannon. Du har ett e-postadministratörs konto med användar namnet **administratör** och lösen ordet är **P@ssw0rd**. Så här skulle CSV-filen se ut:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot:**
  
För IMAP-servrar som stöder enkel inloggningsautentisering och säkerhets skikt (SASL), till exempel en Dovecot IMAP-server, använder du formatet **User_UserName * Admin_UserName**, där asterisken (*) är ett konfigurerbart avgränsnings tecken. Låt oss säga att du migrerar samma användares e-post från en Dovecot IMAP-server med **Administratörs** behörighet för administratörer och **P@ssw0rd**. Så här skulle CSV-filen se ut:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint**
  
Om du migrerar e-post från Mirapoint Message Server använder du formatet **#user@domain#Admin_UserName#** för administratörsautentiseringsuppgifterna. Om du vill migrera e-post från Mirapoint **med administratörs-och** **P@ssw0rd**för administratörer kan CSV-filen se ut så här:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP:**
  
Vissa käll-e-postsystem, till exempel Courier IMAP, stöder inte användning av administratörsautentiseringsuppgifter för att migrera post lådor till Microsoft 365. I stället kan du konfigurera käll-e-postsystemet till att använda virtuella delade mappar. Genom att använda virtuella delade mappar kan du använda administratörsautentiseringsuppgifter för att komma åt användar post lådor i e-postsystemet. Mer information om hur du konfigurerar virtuella delade mappar för Courier IMAP finns i [Delade mappar](https://go.microsoft.com/fwlink/p/?LinkId=398870).
  
Om du vill migrera postlådor när du har konfigurerat virtuella delade mappar på ditt käll-e-postsystem måste du ta med det valfria attributet **UserRoot** i migreringsfilen. Attributet anger platsen för varje användares postlåda i strukturen med virtuella delade mappar på käll-e-postsystemet. Till exempel är sökvägen till Terrys post låda/Users/Terry.Adams.
  
Här är ett exempel på en CSV-fil som innehåller attributet **UserRoot**:
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>Steg 3: skapa en slut punkt för en IMAP-migrering
<a name="BK_Step3"> </a>

För att migrera e-post måste Microsoft 365 ansluta till och kommunicera med käll-e-postsystemet. För att göra det, använder Microsoft 365 en slut punkt för migrering. Slut punkten för migreringen definierar också antalet post lådor som ska migreras samtidigt och antalet post lådor som synkroniseras samtidigt under stegvis synkronisering, vilket inträffar en gång var 24: e timme. [Anslut först till Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121)för att skapa en slut punkt för migrering för IMAP-migrering. 
  
En fullständig lista över migreringsåtgärder finns i avsnittet [flytta och migrera cmdletar](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
Om du vill skapa IMAP-migreringens slut punkt med namnet "IMAPEndpoint" i Exchange Online PowerShell kör du följande kommando:
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

Du kan också lägga till parametrar för att ange samtidiga migreringar, stegvisa inkrementella migreringar och vilken port som ska användas. Med följande Exchange Online PowerShell-kommando skapas en Endpoint-slutpunkt med namnet "IMAPEndpoint" som har stöd för 50-samtidiga migreringar och upp till 25 samtidiga inkrementella synkroniseringar. Den konfigurerar också slut punkten så att port 143 används för TLS-kryptering.
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

Mer information om **New-MigrationEndpoint** -cmdleten finns i[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).
  
#### <a name="verify-it-worked"></a>Verifiera att den fungerade

Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPEndpoint":
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>Steg 4: skapa och starta en batch för IMAP-migrering
<a name="BK_Step4"> </a>

Du kan använda cmdleten [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) för att skapa en migreringstabell för en IMAP-migrering. Du kan skapa en migreringstabell och starta den automatiskt genom att inkludera _Autostart_ -parametern. Alternativt kan du skapa migreringstabellen och sedan starta den efteråt med hjälp av cmdleten[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) .
  
Med följande Exchange Online PowerShell-kommando startas migreringsverktyget automatiskt för "IMAPBatch1" med IMAP-slutpunkten "IMAPEndpoint":
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>Verifiera att den fungerade

Kör cmdleten [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) för att visa information om "IMAPBatch1":
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

Du kan också kontrol lera att batchjobbet har startat genom att köra följande kommando:
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Steg 5: dirigera din e-post till Microsoft 365
<a name="BK_Step5"> </a>

Email systems use a DNS record called an MX record to figure out where to deliver emails. Under e-postmigreringen pekar din MX-post på ditt käll-e-postsystem. Nu när e-postmigreringen till Microsoft 365 är klar är det dags att skicka MX-posten på Microsoft 365. Då ser du till att e-post skickas till dina Microsoft 365-postlådor. Genom att flytta MX-posten kan du även inaktivera det gamla e-postsystemet när du är klar. 
  
För många DNS-leverantörer finns det särskilda anvisningar för hur du ändrar MX-posten. Om din DNS-leverantör inte är inkluderad, eller om du vill ha en uppfattning om de allmänna anvisningarna, kan du också få [allmänna MX Record-instruktioner ](https://go.microsoft.com/fwlink/?LinkId=397449) .
  
Det kan ta upp till 72 timmar innan dina kunder och partners e-postsystem känner igen den ändrade MX-posten. Vänta minst 72 timmar innan du går vidare till nästa uppgift: steg 6: ta bort ett batchjobb för IMAP-migrering. 
  
### <a name="step-6-delete-imap-migration-batch"></a>Steg 6: ta bort en batch för IMAP-migrering
<a name="BK_Step6"> </a>

När du har ändrat MX-posten och kontrollerat att all e-post dirigeras till Microsoft 365-postlådor och meddelar användarna att deras e-post ska skickas till Microsoft 365. Därefter kan du ta bort batchen för IMAP-migrering. Kontrollera följande innan du tar bort migreringsbatchen.
  
- Alla användare använder Microsoft 365-postlådor. När du har tagit bort gruppen kopieras inte e-post till post lådor på den lokala Exchange-servern till motsvarande Microsoft 365-postlådor.
    
- Microsoft 365-postlådor synkroniserades minst en gång efter att e-post började skickas direkt till dem. Det gör du genom att se till att värdet i rutan för den senast synkroniserade tiden för migreringstabellen är senare än när e-post som har börjat dirigeras direkt till Microsoft 365-postlådor.
    
Om du vill ta bort IMAPBatch1 i Exchange Online PowerShell kör du följande kommando:
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

Mer information om cmdleten **Remove-MigrationBatch** finns i[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).
  
#### <a name="verify-it-worked"></a>Verifiera att den fungerade

Kör följande kommando i Exchange Online PowerShell för att visa information om "IMAPBatch1":
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

Kommandot returnerar antingen migreringsarkivet med **statusen borttagen**eller returnerar ett fel meddelande som säger att det inte gick att hitta den Överflyttnings journal som verifierar att gruppen har tagits bort.
  
Mer information om cmdleten **Get-MigrationBatch** finns i[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).
  
## <a name="see-also"></a>Se även

[Fel sökning för IMAP-migrering](https://go.microsoft.com/fwlink/p/?LinkId=536482)

