---
title: Översikt över import av PST-filer i din organisation
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du massimporterar e-postdata (PST-filer) till användarnas postlådor med hjälp av importtjänsten i Säkerhets- och efterlevnadscenter.
ms.openlocfilehash: c645228598eb9cf0e6edca7104b8977e7eaf72f7
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/29/2021
ms.locfileid: "52162553"
---
# <a name="overview-of-importing-your-organizations-pst-files"></a>Översikt över import av PST-filer i din organisation

> [!NOTE]
> Den här artikeln är avsedd för administratörer. Försöker du importera PST-filer till din egen postlåda? Se [Importera e-post, kontakter och kalender från en Outlook .pst-fil](https://go.microsoft.com/fwlink/p/?LinkID=785075).

Med importtjänsten i Säkerhets- och efterlevnadscenter kan du snabbt massimportera PST-filer till Exchange Online-postlådor i din organisation. Du kan importera PST-filer till Office 365 på två sätt:

- **Nätverksuppladdning** ![Molnuppladdning i](../media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) – Ladda upp PST-filerna via nätverket till en tillfällig Azure-lagringsplats i Microsofts moln. Använd sedan Office 365-importtjänsten för att importera PST-data till postlådor i din organisation. 

- **Enhetsleverans** ![Hårddisk](../media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) – Kopiera PST-filerna till en BitLocker-krypterad hårddisk och skicka den sedan fysiskt till Microsoft. När Microsoft får hårddisken laddar personalen på datacentret upp data till en tillfällig Azure-lagringsplats i Microsoft-molnet. Använd sedan Office 365-importtjänsten för att importera data till postlådor i din organisation.

## <a name="step-by-step-instructions"></a>Stegvisa instruktioner
  
Läs något av följande avsnitt för detaljerade stegvisa instruktioner för hur du massimporterar PST-filer till Office 365 i din organisation. 

- [Importera PST-filer till Office 365 via nätverksuppladdning](use-network-upload-to-import-pst-files.md)

- [Importera PST-filer via enhetsleverans](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Så här fungerar import av PST-filer

Här är en bild och beskrivning av den fullständiga PST-importprocessen. Bilden visar det primära arbetsflödet och framhäver skillnaderna mellan att använda nätverksuppladdning och enhetsleverans.
  
![Arbetsflöde för PST-importprocess](../media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **Ladda ned PST-importverktygen och nyckeln till en privat Azure-lagringsplats** – Det första steget är att ladda ned verktyget och åtkomstnyckeln som används för att ladda upp PST-filer eller kopiera dem till en hårddisk. Du hittar dem på **importsidan** i Säkerhets- och efterlevnadscenter. Nyckeln ger dig (eller personalen på Microsofts datacenter vid enhetsleverans) nödvändiga behörigheter för att ladda upp PST-filer till en privat och säker Azure-lagringsplats. Den här åtkomstnyckeln är unik för din organisation och hjälper till att förhindra obehörig åtkomst till dina PST-filer när de har laddats upp till Microsofts moln. Organisationen behöver inte ha en separat Azure-prenumeration för att importera PST-filer till Microsoft 365. 
    
2. **Ladda upp eller kopiera PST-filer** – Nästa steg beror på om du ska importera PST-filerna via nätverksuppladdning eller enhetsleverans. I båda fallen använder du verktyget och nyckeln för säker lagring som du erhöll i föregående steg.
    
    - **Nätverksuppladdning:** Verktyget AzCopy.exe (som laddades ned i steg 1) används för att ladda upp och spara dina PST-filer på en Azure-lagringsplats i Microsofts moln. Den Azure-lagringsplats som du laddar upp PST-filer till finns i samma regionala Microsoft-datacenter som din organisation.
    
      För att kunna ladda upp de PST-filer som du vill importera måste de finnas i en filresurs eller filserver i din organisation.
    
    - **Enhetsleverans:** Verktyget WAImportExport.exe (som laddades ned i steg 1) används för att kopiera PST-filerna till hårddisken. Det här verktyget krypterar hårddisken med BitLocker och kopierar sedan PST-filerna till hårddisken. Liksom vid en nätverksuppladdning måste de PST-filer som du vill importera finnas i en filresurs eller filserver i din organisation.
    
3. **Skapa en mappningsfil för PST-import** – Efter att PST-filerna har laddats upp till Azure-lagringsplatsen eller kopierats till en hårddisk är nästa steg att skapa en kommaavgränsad fil (CSV) som anger vilka användarpostlådor som PST-filerna ska importeras till (en PST-fil kan importeras till en användares primära postlåda eller arkivpostlåda). Importtjänsten i Office 365 använder informationen för att importera PST-filerna. 
    
4. **Skapa ett PST-importjobb** – Nästa steg är att skapa ett PST-importjobb på sidan **Importera PST-filer** i Säkerhets- och efterlevnadscenter och skicka mappningsfilen för PST-import som skapades i föregående steg. Vid en nätverksuppladdning analyserar Microsoft 365 data i PST-filerna (eftersom PST-filerna har laddats upp till Azure) och ger dig sedan möjlighet att ange filter som styr vilka data som faktiskt importeras till de postlådor som anges i mappningsfilen för PST-import. 
    
    Vid en enhetsleverans händer några andra saker vid den här punkten i processen.
    
    - Du skickar hårddisken fysiskt till ett Microsoft-datacenter (leveransadressen för Microsofts datacenter visas när importjobbet skapas).
    
    - När Microsoft tar emot hårddisken laddar personalen på datacentret upp PST-filerna på hårddisken till Azure-lagringsplatsen för din organisation. PST-filerna laddas som sagt upp till en Azure-lagringsplats som finns i samma regionala Microsoft-datacenter som din organisation.
    
      > [!NOTE]
      > PST-filerna på hårddisken laddas upp till Azure inom 7 till 10 arbetsdagar efter att Microsoft har tagit emot hårddisken.

      Precis som vid en nätverksuppladdning analyserar Microsoft 365 sedan data i PST-filerna och ger dig sedan möjlighet att ange filter för att styra vilka data som faktiskt ska importeras till de postlådor som anges i mappningsfilen för PST-import.
    
    - Microsoft skickar tillbaka hårddisken till dig.
    
5. **Filtrera PST-data som ska importeras till postlådor** – När importjobbet har skapats (och efter att PST-filerna från ett enhetsleveransjobb har laddats upp till Azure-lagringsplatsen) analyserar Microsoft 365 data i PST-filerna (på ett säkert sätt) genom att identifiera objektens ålder och vilka olika meddelandetyper som ingår i PST-filerna. När analysen är klar och data är redo att importeras kan du importera alla data som finns i PST-filerna, eller så kan du trimma data som importeras genom att ställa in ett filter som bestämmer vilka data som ska importeras. 
    
6. **Starta PST-importjobbet** – När importjobbet har startats använder Microsoft 365 informationen i mappningsfilen för PST-import för att importera PST-filerna från Azure-lagringsplatsen till användarnas postlådor. Statusinformation om importjobbet (inklusive information om varje PST-fil som importeras) visas på sidan **Importera PST-filer** i Säkerhets- och efterlevnadscenter. När importjobbet är klart blir jobbets status **Slutfört**.
  
## <a name="why-import-email-data-to-microsoft-365"></a>Varför ska jag importera e-postdata till Microsoft 365?

- Det är ett bra sätt att importera organisationens meddelandedata för arkivering till Microsoft 365.
    
- Med funktionen [Intelligent import](filter-data-when-importing-pst-files.md) kan du filtrera de objekt i PST-filerna som faktiskt ska importeras till målpostlådorna. På så sätt kan du trimma de data som importeras genom att ställa in filter som bestämmer vilka data som ska importeras. 
    
- Genom att importera e-postdata till Microsoft 365 kan du tillgodose efterlevnadsbehoven i din organisation eftersom du kan:
    
  - Aktivera [arkivpostlådor](enable-archive-mailboxes.md) och [obegränsad arkivering](unlimited-archiving.md) för att ge användarna ytterligare lagringsutrymme för postlådor. 
    
  - Placera postlådor i [Bevarande av juridiska skäl](./create-a-litigation-hold.md) för att bevara innehåll. 
    
  - Söka efter innehåll i postlådor med [verktyget Innehållssökning](content-search.md). 
    
  - Hantera organisationens juridiska undersökningar med [eDiscovery-ärenden](./get-started-core-ediscovery.md) 
    
  - Med [kvarhållningsprinciper](retention.md) i Säkerhets- och efterlevnadscenter kan du ange hur länge postlådeinnehåll ska bevaras innan det sedan tas bort när kvarhållningsperioden gått ut. 

  - Med [principer för kommunikationsefterlevnad](communication-compliance.md) kan du undersöka meddelanden för att försäkra dig om att de är kompatibla med meddelandestandarder och lägga till en klassificeringstyp.
    
- Att importera data till Microsoft 365 skyddar mot dataförlust. E-postdata som importeras till Microsoft 365 ärver funktionerna för hög tillgänglighet i Exchange Online.
    
- Användarna kan komma åt e-postdata från alla enheter eftersom dessa data lagras i molnet.
    
## <a name="importing-sharepoint-data-to-microsoft-365"></a>Importera SharePoint-data till Microsoft 365

Du kan också importera filer och dokument till SharePoint-webbplatser och OneDrive-konton i din organisation. Mer information finns i följande artiklar:

- [Migrera till SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)

- [Introduktion till migreringsverktyget för SharePoint](/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [Migrera till SharePoint Online med PowerShell](/sharepointmigration/overview-spmt-ps-cmdlets)

- [Migrera ditt filresursinnehåll till SharePoint Online med Azure Data Box](/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)

## <a name="frequently-asked-questions-about-importing-pst-files"></a>Vanliga frågor och svar om import av PST-filer
  
Här är några vanliga frågor och svar om hur du använder importtjänsten i Office 365 för att massimportera PST-filer till Microsoft 365-postlådor. 
  
- [Importera PST-filer via nätverksuppladdning](#using-network-upload-to-import-pst-files)
  
- [Importera PST-filer med hjälp av enhetsleverans](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>Importera PST-filer via nätverksuppladdning

 **Vilka behörigheter krävs för att skapa importjobb i Office365-importtjänsten?**
  
Du måste vara tilldelad rollen Import/export av postlåda i Exchange Online för att kunna importera PST-filer till Microsoft 365-postlådor. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Import/export av postlåda i rollgruppen Organisationshantering. Eller så kan du skapa en ny rollgrupp, tilldela rollen Import/export av postlåda och sedan lägga till dig själv eller andra användare som medlemmar. Mer information finns i avsnitten ”Lägg till en roll i rollgrupp” och ”Skapa en rollgrupp” i [Hantera rollgrupper i Exchange Online](/Exchange/permissions-exo/role-groups).
  
Om du ska skapa importjobb i Säkerhets- och efterlevnadscenter måste dessutom något av följande stämma:
  
- Du har tilldelats rollen E-postmottagare i Exchange Online. Som standard är den här rollen tilldelad rollgrupperna Organisationshantering och Mottagarhantering.

    Eller
    
- Du måste vara global administratör i din organisation.

> [!TIP]
> Du kan skapa en ny rollgrupp i Exchange Online som är specifikt avsedd att importera PST-filer till Office 365. För den lägsta nivån av behörighet som krävs för att importera PST-filer tilldelar du rollerna Import/export av postlåda och E-postmottagare till den nya rollgruppen och lägger sedan till medlemmar. 
  
 **Var är nätverksuppladdning tillgängligt?**
  
Nätverksuppladdning är för närvarande tillgängligt i USA, Kanada, Brasilien, Storbritannien, Frankrike, Tyskland, Schweiz, Norge, Europa, Indien, Östasien, Sydostasien, Japan, Sydkorea, Australien och Förenade Arabemiraten. Nätverksuppladdning kommer snart att finnas i fler områden.
  
 **Vad kostar det att importera PST-filer med hjälp av nätverksuppladdning?**
  
Det är kostnadsfritt att använda nätverksuppladdning för att importera PST-filer.
  
Det innebär också att när PST-filer tas bort från Azure-lagringsutrymmet visas de inte längre i listan över filer för slutförda importjobb i Administrationscenter för Microsoft 365. Även om ett importjobb kanske fortfarande finns med på sidan **Importera data till Office 365** kan listan över PST-filer vara tom när du visar information om äldre importjobb.
  
 **Vilken version av PST-filformat stöds för import till Office 365?**
  
Det finns två versioner av PST-filformatet: ANSI och Unicode. Vi rekommenderar att du importerar filer som använder Unicode PST-filformatet. Men filer som använder ANSI PST-filformatet, till exempel för språk som använder en teckenuppsättning med dubbla byte (DBCS), kan också importeras till Office 365. Mer information om hur du importerar ANSI PST-filer finns i steg 4 i [Använda nätverksuppladdning för att importera PST-filer till Office 365](./use-network-upload-to-import-pst-files.md).
  
Dessutom kan PST-filer från Outlook 2007 och senare versioner importeras till Office 365.
  
 **När jag har laddat upp mina PST-filer till Azure-lagringsutrymmet, hur lång tid bevaras de då i Azure innan de tas bort?**
  
När du importerar PST-filer med nätverksuppladdningsmetoden laddar du upp dem till en Azure-blobcontainer med namnet `ingestiondata`. Om inga importjobb pågår på sidan **Importera PST-filer** i Säkerhets- och efterlevnadscenter tas alla filer i `ingestiondata`-containern bort 30 dagar efter det att det senaste importjobbet skapades i Säkerhets- och efterlevnadscenter. Det innebär också att du måste skapa ett nytt importjobb i Säkerhets- och efterlevnadscenter (beskrivs i steg 5 i instruktionerna för nätverksuppladdning) inom 30 dagar efter att PST-filer laddats upp till Azure.
  
Det innebär också att när PST-filer tas bort från Azure-lagringsutrymmet visas de inte längre i listan över filer för slutförda importjobb i Säkerhets- och efterlevnadscenter. Även om ett importjobb kanske fortfarande finns med på sidan **Importera PST-filer** i Säkerhets- och efterlevnadscenter kan listan över PST-filer vara tom när du visar information om äldre importjobb.
  
 **Hur lång tid tar det att importera en PST-fil till en postlåda?**
  
Det beror på kapaciteten i nätverket, men det tar normalt flera timmar att ladda upp varje terabyte (TB) data till organisationens Azure-lagringsutrymme. När PST-filerna har kopierats till Azure-lagringsutrymmet importeras en PST-fil till en Microsoft 365-postlåda med en hastighet på minst 24 GB per dag. Om hastigheten inte uppfyller dina behov bör du fundera på andra metoder för att överföra e-postdata till Office 365. Mer information finns i [Olika sätt att migrera flera e-postkonton till Office 365](/Exchange/mailbox-migration/mailbox-migration).
  
Om olika PST-filer importeras till olika målpostlådor sker importen parallellt, med andra ord importeras varje PST-/postlådepar samtidigt. Om flera PST-filer importeras till samma postlåda kommer de att importeras samtidigt.
  
 **Hur hanteras dubbletter av e-postobjekt vid PST-importen?**

Vid PST-importen kontrolleras om det finns dubbletter av objekt. Objekt kopieras inte från en PST-fil till postlådan eller arkivet om det redan finns ett matchande objekt i målmappen i målpostlådan eller målarkivet. Om du importerar samma PST-fil igen och anger en annan målmapp (med egenskapen TargetRootFolder i mappningsfilen för PST-import) än den du angav i ett tidigare importjobb kommer alla objekt i PST-filen att importeras på nytt.
 
 **Finns det någon storleksgräns för meddelanden vid importering av PST-filer?**
  
Ja. Om en PST-fil innehåller ett objekt som är större än 150 MB hoppas det objektet över och importeras inte under importen. Objekt som är större än 150 MB importeras inte eftersom 150 MB är storleksgränsen för meddelanden i Exchange Online. Mer information finns i [Meddelandegränser i Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits).
  
 **Bevaras meddelandeegenskaper, till exempel när meddelandet skickades eller togs emot, listan över mottagare och andra egenskaper, när PST-filer importeras till en Microsoft 365-postlåda?**
  
Ja. Ursprungliga metadata för ett meddelande ändras inte under importen.
  
 **Finns det en nivågräns i en mapphierarki för en PST-fil som jag vill importera till en postlåda?**
  
Ja. Du kan inte importera en PST-fil som innehåller 300 eller flera nivåer med kapslade mappar.
  
 **Kan jag använda nätverksuppladdning för att importera PST-filer till en inaktiv postlåda i Office 365?**
  
Ja, denna funktion är nu tillgänglig.
  
 **Kan jag använda nätverksuppladdning för att importera PST-filer till en onlinearkivpostlåda i en Exchange-hybriddistribution?**
  
Ja, denna funktion är nu tillgänglig. 
  
 **Kan jag använda nätverksuppladdning för att importera PST-filer till gemensamma mappar i Exchange Online?**
  
Nej, du kan inte importera PST-filer till gemensamma mappar.
  
### <a name="using-drive-shipping-to-import-pst-files"></a>Importera PST-filer med hjälp av enhetsleverans

 **Vilka behörigheter krävs för att skapa importjobb i Office365-importtjänsten?**
  
Du måste vara tilldelad rollen Import/export av postlåda för att kunna importera PST-filer till Microsoft 365-postlådor. Som standard är den här rollen inte tilldelad en rollgrupp i Exchange Online. Du kan lägga till rollen Import/export av postlåda i rollgruppen Organisationshantering. Eller så kan du skapa en ny rollgrupp, tilldela rollen Import/export av postlåda och sedan lägga till dig själv eller andra användare som medlemmar. Mer information finns i avsnitten ”Lägg till en roll i rollgrupp” och ”Skapa en rollgrupp” i [Hantera rollgrupper i Exchange Online](/Exchange/permissions-exo/role-groups).
  
Om du ska skapa importjobb i Säkerhets- och efterlevnadscenter måste dessutom något av följande stämma:
  
- Du har tilldelats rollen E-postmottagare i Exchange Online. Som standard är den här rollen tilldelad rollgrupperna Organisationshantering och Mottagarhantering.
    
    Eller
    
- Du måste vara global administratör i din organisation.
    
> [!TIP]
> Du kan skapa en ny rollgrupp i Exchange Online som är specifikt avsedd att importera PST-filer till Office 365. För den lägsta nivån av behörighet som krävs för att importera PST-filer tilldelar du rollerna Import/export av postlåda och E-postmottagare till den nya rollgruppen och lägger sedan till medlemmar. 
  
 **Var finns möjligheten att skicka in en hårddisk tillgänglig?**
  
Möjligheten att skicka in en hårddisk är för närvarande tillgänglig i USA, Kanada, Brasilien, Storbritannien, Europa, Indien, Östasien, Sydostasien, Japan, Republiken Korea och Australien. Möjligheten att skicka in en hårddisk kommer snart att vara tillgänglig i fler områden.

> [!NOTE]
> För närvarande är import av PST-filer via enhetsleverans inte tillgängligt i Tyskland och Schweiz. Dessa vanliga frågor och svar kommer att uppdateras när enhetsleverans är tillgängligt i dessa länder.
  
 **Vilka kommersiella licensavtal har stöd för möjligheten att skicka in en hårddisk?**
  
Möjligheten att importera PST-filer till Microsoft 365 genom att skicka in en hårddisk är tillgänglig via ett Microsoft Enterprise-avtal (EA). Möjligheten att skicka in en hårddisk är inte tillgänglig via ett MPSA-avtal (Microsoft Products and Services Agreement).
  
 **Vad kostar det att använda möjligheten att skicka in en hårddisk för att importera PST-filer till Microsoft 365?**
  
Kostnaden för att skicka in en hårddisk för att importera PST-filer till Microsoft 365-postlådor är 2 USD per GB data. Om du till exempel skickar in en hårddisk som innehåller 1 000 GB (1 TB) PST-filer är kostnaden 2 000 USD. Du kan samarbeta med en partner för att betala importavgiften. Information om hur du hittar en partner finns i [Hitta en Microsoft-partner eller återförsäljare](../admin/manage/find-your-partner-or-reseller.md).
  
 **Vilken typ av hårddiskar är möjliga att skicka in?**
  
Endast 2,5-tums SSD (Solid-state Drives) eller 2,5- eller 3,5-tums SATA II/III interna hårddiskar stöds för användning med importtjänsten i Office 365. Du kan använda hårddiskar på upp till 10 TB. För importjobb är det endast den första datavolymen på hårddisken som bearbetas. Datavolymen måste vara formaterad med NTFS. När du kopierar data till en hårddisk kan du ansluta den direkt med hjälp av en 2,5-tums SSD- eller 2,5- eller 3,5-tums SATA II/III-koppling, eller så kan du ansluta den externt med hjälp av en extern 2,5-tums SSD- eller 2,5- eller 3,5-tums SATA II/III USB-adapter.
  
> [!IMPORTANT]
> Externa hårddiskar som har en inbyggd USB-adapter stöds inte av Office 365-importtjänsten. Det går inte heller att använda disken inuti en extern hårddisks hölje. Skicka inte in externa hårddiskar. 
  
 **Hur många hårddiskar kan jag skicka in för ett importjobb?**
  
Du kan skicka maximalt 10 hårddiskar för ett importjobb.
  
 **När jag har skickat in min hårddisk, hur lång tid tar det då för den att komma fram till Microsofts datacenter?**
  
Det beror på några olika saker, till exempel hur nära du befinner dig Microsofts datacenter och vilken typ av leveransalternativ du använde för att skicka hårddisken (till exempel leverans nästa dag, två dagars leveranstid eller standardleverans). Hos de flesta speditörer kan du använda spårningsnumret för att spåra status för din leverans.
  
 **Hur lång tid tar det att ladda upp PST-filer till Azure efter att min hårddisk har anlänt till Microsofts datacenter?**
  
När hårddisken har tagits emot på Microsofts datacenter tar det mellan 7 och 10 arbetsdagar att ladda upp PST-filer till Azure-lagringsplatsen för din organisation. PST-filerna laddas upp till en Azure-blobcontainer med namnet `ingestiondata`. 
  
 **Hur lång tid tar det att importera en PST-fil till en postlåda?**
  
När PST-filerna har laddats upp till Azure-lagringsutrymmet analyserar Microsoft 365 data i PST-filerna (på ett säkert sätt) för att identifiera åldern på objekten och de olika meddelandetyper som finns i PST-filerna. När den här analysen är klar har du möjlighet att importera alla data i PST-filerna eller ställa in filter för att bestämma vilka data som ska importeras. När du startar importjobbet importeras en PST-fil till en Microsoft 365-postlåda med en hastighet på minst 24 GB per dag. Om hastigheten inte uppfyller dina behov bör du fundera på andra metoder för att överföra e-postdata till Microsoft 365. Mer information finns i [Olika sätt att migrera flera e-postkonton till Microsoft 365](/Exchange/mailbox-migration/mailbox-migration).
  
Om olika PST-filer importeras till olika målpostlådor sker importen parallellt, med andra ord importeras varje PST-/postlådepar samtidigt. Om flera PST-filer importeras till samma postlåda kommer de att importeras samtidigt.
  
 **När Microsoft har laddat upp mina PST-filer till Azure, hur länge finns de kvar i Azure innan de tas bort?**
  
Alla PST-filer på Azure-lagringsplatsen för din organisation (i en blobcontainer med namnet `ingestiondata`) tas bort 30 dagar efter att det senaste importjobbet skapades på sidan **Importera PST-filer** i Säkerhets- och efterlevnadscenter. 
  
Det innebär också att när PST-filer tas bort från Azure-lagringsutrymmet visas de inte längre i listan över filer för slutförda importjobb i Säkerhets- och efterlevnadscenter. Även om ett importjobb kanske fortfarande finns med på sidan **Importera PST-filer** i Säkerhets- och efterlevnadscenter kan listan över PST-filer vara tom när du visar information om äldre importjobb. 
  
 **Vilken version av PST-filformat stöds för import till Microsoft 365?**
  
Det finns två versioner av PST-filformatet: ANSI och Unicode. Vi rekommenderar att du importerar filer som använder Unicode PST-filformatet. Men filer som använder ANSI PST-filformatet, till exempel för språk som använder en teckenuppsättning med dubbla byte (DBCS), kan också importeras till Microsoft 365. Mer information om hur du importerar ANSI PST-filer finns i steg 3 i [Använda möjligheten att skicka in en hårddisk för att importera organisationens PST-filer i Microsoft 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Dessutom kan PST-filer från Outlook 2007 och senare versioner importeras till Microsoft 365.
  
 **Finns det någon storleksgräns för meddelanden vid importering av PST-filer?**
  
Ja. Om en PST-fil innehåller ett objekt som är större än 150 MB hoppas det objektet över och importeras inte under importen. Objekt som är större än 150 MB importeras inte eftersom 150 MB är storleksgränsen för meddelanden i Exchange Online. Mer information finns i [Meddelandegränser i Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits).
  
  **Hur hanteras dubbletter av e-postobjekt vid PST-importen?**

Vid PST-importen kontrolleras om det finns dubbletter av objekt. Objekt kopieras inte från en PST-fil till postlådan eller arkivet om det redan finns ett matchande objekt i målmappen i målpostlådan eller målarkivet. Om du importerar samma PST-fil igen och anger en annan målmapp (med egenskapen TargetRootFolder i mappningsfilen för PST-import) än den du angav i ett tidigare importjobb kommer alla objekt i PST-filen att importeras på nytt.
 
 **Bevaras meddelandeegenskaper, till exempel när meddelandet skickades eller togs emot, listan över mottagare och andra egenskaper, när PST-filer importeras till en Microsoft 365-postlåda?**
  
Ja. Ursprungliga metadata för ett meddelande ändras inte under importen
  
 **Finns det en nivågräns i en mapphierarki för en PST-fil som jag vill importera till en postlåda?**
  
Ja. Du kan inte importera en PST-fil som innehåller 300 eller flera nivåer med kapslade mappar.
  
 **Kan jag använda möjligheten att skicka in en hårddisk för att importera PST-filer till en inaktiv postlåda i Microsoft 365?**
  
Ja, denna funktion är nu tillgänglig. 
  
 **Kan jag använda möjligheten att skicka in en hårddisk för att importera PST-filer till en onlinearkivpostlåda i en Exchange-hybriddistribution?**
  
Ja, denna funktion är nu tillgänglig. 
  
 **Kan jag använda möjligheten att skicka in en hårddisk för att importera PST-filer till gemensamma mappar i Exchange Online?**
  
Nej, du kan inte importera PST-filer till gemensamma mappar.
  
 **Kan Microsoft radera min hårddisk innan de skickar tillbaka den till mig?**
  
Nej, Microsoft kan inte radera hårddiskar innan de skickas tillbaka till kunderna. Hårddiskar returneras till dig i samma skick som de var när de togs emot av Microsoft.
  
 **Kan Microsoft förstöra min hårddisk i stället för att skicka tillbaka den till mig?**
  
Nej, Microsoft kan inte förstöra hårddisken. Hårddiskar returneras till dig i samma skick som de var när de togs emot av Microsoft.
  
 **Vilka posttjänster stöds för returleveransen?**
  
Om du är kund i USA eller Europa använder Microsoft FedEx för att returnera hårddisken. För alla andra regioner använder Microsoft DHL.
  
 **Vad kostar returleveransen?**
  
Kostnaden för returleveransen varierar beroende på hur nära du befinner dig det Microsoft-datacenter som du skickat hårddisken till. Microsoft kommer att debitera ditt FedEx- eller DHL-konto för returleveransen av hårddisken. Kostnaden för returleveransen ansvarar du för.
  
 **Kan jag använda en anpassad postleveranstjänst, till exempel FedEx:s anpassade leverans, för att skicka in min hårddisk till Microsoft?**
  
Ja.
  
 **Om jag måste skicka min hårddisk till ett annat land, finns det något särskilt jag behöver tänkta på?**
  
Hårddisken som du skickar till Microsoft kan behöva korsa internationella gränslinjer. I så fall är du ansvarig för att säkerställa att hårddisken och de data den innehåller importeras och/eller exporteras i enlighet med gällande lagstiftning. Fråga dina rådgivare för att försäkra dig om att din hårddisk och dina data lagligt kan skickas till det angivna Microsoft-datacentret innan du skickar hårddisken. Det här gör det lättare att se till att det når Microsoft i tid.