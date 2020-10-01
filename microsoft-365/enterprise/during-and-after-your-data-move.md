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
ms.openlocfilehash: d2e63dd046f62f07e367b3632f96bf7261b99c9c
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333706"
---
# <a name="during-and-after-your-data-move"></a>Under och efter dataflytt

Data flyttas är en backend-åtgärd som påverkar slutanvändaren minimalt. Ingen åtgärd krävs när Microsoft flyttar över alla tjänster och tillhör ande data för din klient organisation till ett nytt Data Center geo. Data överföring och verifiering sker i bakgrunden i förväg med minimal påverkan på användarna.
  
> [!NOTE]
> Flyttningarna sker vid olika tillfällen för varje tjänst. Det innebär att du ser de reducerade funktionerna för varje tjänst samtidigt. 
  
Se meddelande Center för Microsoft 365 för att bekräfta när det rör sig om för varje Exchange Online-, SharePoint Online-och Teams-chatt. Som du ser i tabellen nedan kan det ta upp till 24 månader efter det att registrerings perioden är slut för att komplettera alla grundläggande kunddata på rest till det nya data Center geo.   

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
|Tyskland  <br/> |Den 1 april 2023  <br/> |

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
    
- Microsoft 365 Video-tjänster
    
- Office i en webbläsare
    
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

Utöver Exchange Online, SharePoint Online och OneDrive för företag migreras automatiskt data från Teams chat till det lokala data centret.

- Teams chattar meddelanden, inklusive privata meddelanden och kanal meddelanden.
- Team-bilder som används i chattar.

Teams-filer lagras i SharePoint Online-och Teams-chatt-filer lagras i OneDrive för företag. Röst brev låda, kalender, chatt och kontakter lagras i Exchange Online. I många fall används Exchange Online, SharePoint Online och OneDrive för företag redan av kunden i det lokala datacentret Geo och är också en del av Microsoft 365 migrations program för godkända kund länder.

## <a name="skype-for-business"></a>Skype för företag

Flytt av Skype för företag är inte längre tillgängligt.  [Skype för företag – Online kommer att avvecklas](https://docs.microsoft.com/lifecycle/announcements/skype-for-business-online-retirement) den 31 juli 2021. Efter den tiden är tjänsten inte längre tillgänglig. 
  
## <a name="related-topics"></a>Relaterade ämnen 
 
[Hur du begär din dataflytt](request-your-data-move.md)
    
[Vanliga frågor och svar om dataflytt](data-move-faq.md)
  
[Ny datacenter-geos för Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure-tjänster efter region](https://azure.microsoft.com/regions/)
