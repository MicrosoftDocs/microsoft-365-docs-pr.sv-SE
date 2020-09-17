---
title: Under och efter dataflytt
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: Data transporter är bakgrunds åtgärder som inträffar när Microsoft flyttar tjänster och tillhör ande data för din klient organisation till ett nytt Data Center geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: acd2601d32617c56019ca8b4bf8688ce40f5d76a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950278"
---
# <a name="during-and-after-your-data-move"></a>Under och efter dataflytt

Data flyttas är en backend-åtgärd som påverkar slutanvändaren minimalt. Ingen åtgärd krävs när Microsoft flyttar över alla tjänster och tillhör ande data för din klient organisation till ett nytt Data Center geo. Data överföring och verifiering sker i bakgrunden i förväg med minimal påverkan på användarna.
  
> [!NOTE]
> Flyttningarna sker vid olika tillfällen för varje tjänst. Det innebär att du ser de reducerade funktionerna för varje tjänst samtidigt. 
  
Titta på meddelande Center för Microsoft 365 för att bekräfta när det rör sig om för varje Exchange Online, SharePoint Online, teams och Skype för företag. Som du ser i tabellen nedan kan det ta upp till 24 månader efter det att registrerings perioden är slut för att slutföra alla begärda data för alla kunder i en viss geo. Om du får problem med klient organisationen efter flytten kontaktar du [support](https://go.microsoft.com/fwlink/p/?LinkID=522459) för att få hjälp. 
  

|**Kunder med anmälan land i**|**Alla flyttningar slutförda av**|
|:-----|:-----|
|Australien, Nya Zeeland, Fidji  <br/> |Den 1 juli 2022  <br/> |
|Japan   <br/> |Den 1 juli 2022  <br/> |
|Indien  <br/> |Den 1 juli 2022  <br/> |
|Kanada  <br/> |Den 1 juli 2022  <br/> |
|Sydkorea  <br/> |Den 1 juli 2022  <br/> |
|Storbritannien  <br/> |Den 1 juli 2022  <br/> |
|Frankrike  <br/> |Den 1 juli 2022  <br/> |
|Förenade Arabemiraten  <br/> |Den 1 juli 2022  <br/> |
|Sydafrika  <br/> |Den 1 juli 2022  <br/> |
|Schweiz, Liechtenstein  <br/> |Den 1 juli 2022  <br/> |
|Norge  <br/> |Den 1 november 2022  <br/> |
|Tyskland  <br/> |Disponera  <br/> |

## <a name="exchange-online"></a>Exchange Online

Eftersom det tar tid att flytta varje användare till det nya datacentret geo för en enda klient organisation kommer vissa användare ändå att befinner sig i det gamla data centret geo under flytten, medan andra är i det nya data centret geo. Det innebär att vissa funktioner som kräver åtkomst till flera post lådor kanske inte helt fungerar under en tids period som flyttas, vilka kan gå under de senaste veckorna. Dessa funktioner beskrivs i följande avsnitt.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Öppna "delad mapp" i Outlook Web Access

Vissa användare öppnar en delad e-postmapp från en annan post låda (som användaren har Läs-eller Skriv behörighet till) i Outlook Web Access med funktionen "delad mapp". I följande tabell beskrivs hur åtkomst till delade mappar fungerar under en post låda. Observera att användare med fullständig behörighet till en delad post låda kan öppna post lådan genom att använda Outlook Web Access under flytten. 
  
|**Konfiguration**|**Beskrivning**|
|:-----|:-----|
|Användaren har behörigheten post låda till en annan post låda  <br/> |Möjligt.  <br/> Om användare A och post låda B inte är med i samma geo när klient organisationen flyttas, kan användare A inte öppna post lådans mapp i Outlook Web Access om användaren har en enda behörighet för en viss mapp i post låda B.  <br/> Om du vill lägga till en delad mapp högerklickar du på användar namnet i navigerings panelen och väljer **Lägg till delad mapp**.  <br/> |
|Användare med fullständig Mailbox-behörighet till en annan post låda  <br/> |Stöds helt.  <br/> Om användare A har full till gång till post låda B kan användare A Klicka på den delade mappen i den vänstra navigerings panelen i Outlook Web Access för att öppna ett fönster som visar post låda B.  En användare kan öppna en delad post låda med Outlook Web Access under flytten utan att det påverkar något negativt. Begränsningen gäller bara delning på filnivå i en post låda.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

När SharePoint Online flyttas flyttas även data för följande tjänster:
  
- En enhet för företag
    
- Project Online
    
- Project för Microsoft 365
    
- Microsoft 365 Video-tjänster
    
- Office i s webbläsare
    
-  Microsoft 365 Apps för företag
    
- Visio Pro för Microsoft 365
    
När vi har flyttat dina SharePoint Online-data kan du se några av följande effekter.
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 Video-tjänster

- Data flytten för videon tar längre tid än flyttas för resten av innehållet i SharePoint Online.
    
- När SharePoint Online-innehållet flyttas visas en tidsram när videoklippen inte kan spelas upp.
    
- Vi tar bort de förkodade kopiorna från föregående Data Center och förkodar dem igen i det nya data centret.
    
### <a name="search"></a>Sökmotor

Vi migrerar Sök index och Sök inställningar till en ny plats när du flyttar dina SharePoint Online-data. **Nu när vi har flyttat** dina SharePoint Online-data fortsätter vi att betjäna användarna från indexet på den ursprungliga platsen. På den nya platsen börjar Sök automatiskt crawla innehållet när vi har flyttat dina SharePoint Online-data. Från och med nu tjänar vi användarna från det migrerade indexet. Ändringar av innehållet som uppstod efter migreringen ingår inte i det migrerade indexet förrän crawlningen väljer upp dem. De flesta kunder märker inte att resultaten blir mindre färska direkt efter att vi har flyttat sina SharePoint Online-data, men vissa kunder kan uppleva minskad aktualitet under de första 24-48 timmarna 
  
Följande Sök funktioner påverkas:
  
- Sök Resultat och Sök webb delar: resultaten innehåller inte ändringar som uppstod efter migreringen förrän crawlningen har gjort det. 
    
- Delve: Delve inkluderar inte ändringar som uppstod efter migreringen förrän crawlningen har gjort det.
    
- Popularitet och Sök rapporter för webbplatsen: antal för Excel-rapporter på den nya platsen endast innehåller migrerade räknare och antal från användnings rapporter som körs när vi har flyttat dina SharePoint Online-data. Alla räkningar från den mellanliggande perioden förloras och kan inte återställas. Detta är vanligt vis ett par dagar. Vissa kunder kan uppleva kortare eller längre förluster.
    
- Video Portal: Visa räknare och statistik för video portalen beror på statistik för Excel-rapporter, så att det går att Visa räknare och statistik för video portalen under samma tids period som för Excel-rapporterna.
    
- eDiscovery: objekt som ändrats under migreringen visas inte förrän crawlningen hämtar ändringarna.
    
- Data förlust skydd (DLP): principer tillämpas inte på objekt som ändras tills crawlningen hämtar ändringarna.

## <a name="microsoft-teams"></a>Microsoft Teams

Utöver Exchange Online, SharePoint Online och OneDrive för företag migreras team data till det lokala data centret.

- Teams chattar meddelanden, inklusive privata meddelanden och kanal meddelanden.
- Team-bilder som används i chattar.

Teams-filer lagras i SharePoint Online-och Teams-chatt-filer lagras i OneDrive för företag. Röst brev låda, kalender, chatt och kontakter lagras i Exchange Online. I många fall används Exchange Online, SharePoint Online och OneDrive för företag redan av kunden i det lokala datacentret Geo och är också en del av Microsoft 365 migrations program för godkända kund länder.

## <a name="skype-for-business"></a>Skype för företag

Skype för Business-flytt är tillgängligt för Australien, Japan, Indien, Kanada, Storbritannien och Sydkorea.

Alla användare loggas ut från Skype för företag-klientens program vara under klipp-över. Automatisk inloggning kommer att återansluta användare inom två minuter.
  
|**Funktioner som fungerar under hela flytten**|**Funktioner som kan begränsas under en del av flytten**|
|:-----|:-----|
| Snabb meddelanden och röst samtal  <br/>  Användare kan lägga till kontakter, lägga till kontakt grupper, lägga till möten, ange plats och ändra "Vad händer idag".  <br/>  Inställningar för en ljud konferens leverantör (AVS) kopieras till mål Data Center geo. Om AVS-leverantören finns i mål data centret kommer den att fungera. Annars kommer den inte att visas.  <br/> | Klient organisationens administratörs TRPS (klient organisationens fjärrpowershell) är inte tillgängligt för administratörer att skapa sessioner.  <br/>  Klient organisationens administratörs LAC är inte tillgängliga för administratörer att logga in och ändra användar inställningar.  <br/> |
   
|**Efter flytten**|
|:-----|
| Mötes data (uppladdade presentationer etc.) flyttas inte och måste laddas upp på nytt.  <br/>  Äldre Lync-klienter, till exempel Lync 2010-klienten och Lync för Mac 2011-klienten, är kända för cachelagring av DNS-information till tjänsten som orsakar inloggnings problem. Det kan krävas en rensning av DNS-cachen om användaren inte är på den senaste Skype för företag-Windows-klienten. Se [fel sökning för DNS-konfiguration för Skype för företag – Online i Office 365](https://docs.microsoft.com/skypeforbusiness/troubleshoot/online-configuration/dns-configuration-issue). Användare av Lync för Mac-klienter bör följa [dessa instruktioner](https://support.microsoft.com/kb/2629861).  <br/> |
   
### <a name="skype-for-business-moves-that-involve-a-third-party-audio-conferencing-provider"></a>Skype för företag-flytt med en tredjeparts ljud konferens leverantör
Tredjepartsleverantör av ljud konferens leverantörer för Skype för företag är inte tillgängliga för användare som är hemifrån i nya geo-specifika data Center.  Befintliga kunder som använder en tredjepartsleverantör för ljud konferenser bör inte begära en flytt till ett nytt geo-specifikt Data Center.  Nya kunder som distribueras till nya geo-specifika data centra måste begära en flytt till ett regionalt Data Center för att använda en tredjepartsleverantör för ljud konferenser.
  
## <a name="related-topics"></a>Relaterade ämnen 
 
[Hur du begär din dataflytt](request-your-data-move.md)
    
[Vanliga frågor och svar om dataflytt](data-move-faq.md)
  
[Ny datacenter-geos för Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure-tjänster efter region](https://azure.microsoft.com/regions/)
