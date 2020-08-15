---
title: Diagnosticera prestanda problem med SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: Den här artikeln visar hur du kan diagnostisera vanliga problem med SharePoint Online-webbplatsen med utvecklingsverktyg för Internet Explorer.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694548"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>Diagnosticera prestanda problem med SharePoint Online

Den här artikeln visar hur du kan diagnostisera vanliga problem med SharePoint Online-webbplatsen med utvecklingsverktyg för Internet Explorer.
  
Det finns tre olika sätt att identifiera att en sida på en SharePoint Online-webbplats har ett prestanda problem med anpassningarna.
  
- Nätverks övervakaren i F12-verktygsfältet

- Jämförelse med en icke-anpassad original plan

- Mått för svars rubriker i SharePoint Online

I det här avsnittet beskrivs hur du använder dessa metoder för att diagnosticera prestanda problem. När du har tagit reda på orsaken till problemet kan du jobba mot en lösning med hjälp av artiklarna om att förbättra SharePoint-prestandan som du kan hitta på https://aka.ms/tune .
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>Använda F12-verktygsfältet för att diagnosticera prestanda i SharePoint Online
<a name="F12ToolInfo"> </a>

I den här artikeln används Internet Explorer 11. Versioner av F12-utvecklingsverktygen i andra webbläsare har liknande funktioner, men de kan se lite annorlunda ut. Information om F12-utvecklingsverktygen finns i:
  
- [Nyheter i F12-verktyg](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [Använda verktygen för att F12-utvecklare](https://go.microsoft.com/fwlink/p/?LinkId=522546)

Öppna utvecklingsverktygen genom att trycka på **F12** och sedan klicka på WiFi-ikonen:
  
![Skärm bild av ikonen för att F12-utvecklingsverktygen](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
På fliken **nätverk** trycker du på den gröna uppspelnings knappen för att läsa in en sida. Verktyget returnerar alla filer som webbläsaren begär för att få den sida du bad om. På följande bild visas en sådan lista.
  
![Skärm bild av listan med filer som returnerats med en sidbegäran.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
Du kan också se nedladdnings tiderna för filerna till höger som visas i den här skärm bilden.
  
![Diagram som visar hur lång tid det tar att läsa in begärda sidor från SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
Då får du en bild av hur lång tid det tagit att läsa in filen. Den gröna linjen representerar när sidan är klar att renderas av webbläsaren. Det här kan ge dig en snabb översikt över de olika filerna som kan orsaka långsam sid läsning på din webbplats.
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>Konfigurera en icke-anpassad original plan för SharePoint Online
<a name="F12ToolInfo"> </a>

Det bästa sättet att kontrol lera webbplatsens prestanda svaga punkter är att konfigurera en helt annan webbplats samling i SharePoint Online. På det sättet kan du jämföra alla olika aspekter av din webbplats med vad du skulle få utan att anpassa på sidan. Start sidan för OneDrive för företag är ett bra exempel på en separat webbplats samling som sannolikt inte har några anpassningar.
  
## <a name="viewing-sharepoint-response-header-information"></a>Visa information om SharePoint-svarshuvuden
<a name="F12ToolInfo"> </a>

I SharePoint Online kan du komma åt den information som skickas tillbaka till webbläsaren i svars huvudet för varje fil. Det mest användbara värdet för diagnostisering av prestanda problem är **SPRequestDuration**, som visar hur lång tid det tog för servern att behandlas. Det här kan hjälpa till att avgöra om begäran är mycket tungt och krävande för resurserna. Det här är det bästa med hur mycket arbete som servern utför för att betjäna sidan.

### <a name="to-view-sharepoint-response-header-information"></a>Visa information om SharePoint-svarshuvuden
  
1. Kontrol lera att du har F12-verktygen installerat. Mer information om hur du laddar ned och installerar de här verktygen finns i [Nyheter i F12-verktyg](https://go.microsoft.com/fwlink/p/?LinkId=522545).

2. I F12-verktyg trycker du på den gröna uppspelnings knappen på fliken **nätverk** för att läsa in en sida.

3. Klicka på en av. aspx-filerna som returneras av verktyget och klicka sedan på **information**.

    ![Visar information om svars huvudet](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. Klicka på **svarshuvuden**.

    ![Diagram som visar URL-adressen för svars huvudet](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>Vad orsakar prestanda problem i SharePoint Online?
<a name="F12ToolInfo"> </a>

I artikel [navigerings alternativen för SharePoint Online](navigation-options-for-sharepoint-online.md) visas ett exempel på hur du kan använda SPRequestDuration-värdet för att fastställa att den komplexa strukturell navigeringen gjorde att sidan är lång tid att bearbeta på servern. Genom att ta ett värde för en original webbplats (utan anpassning) kan du avgöra om en viss fil tar lång tid att läsa in. Exemplet som används i [navigerings alternativ för SharePoint Online](navigation-options-for-sharepoint-online.md) är main. aspx-filen. Filen innehåller de flesta ASP.NET-koder som körs för sid inläsningen. Beroende på vilken webbplatsmall du använder kan du starta. aspx, Home. aspx, default. aspx eller ett annat namn om du anpassar start sidan. Om det här numret är betydligt högre än din original plats är det lämpligt att ange att det finns något komplicerat på sidan som orsakar prestanda problem.
  
När du har identifierat att det finns ett problem som är specifikt för din webbplats, rekommenderar vi att du tar reda på vad som orsakar dålig prestanda genom att eliminera alla möjliga orsaker, till exempel sid anpassningar, och sedan lägga till dem på en och samma plats. När du har tagit bort tillräckligt många anpassningar som sidan fungerar kan du lägga till ytterligare anpassningar en och en.
  
Om du till exempel har en mycket komplicerad navigering kan du ändra navigeringen till att inte Visa under webbplatser och sedan kontrol lera utvecklingsverktygen för att se om det gör något. Om du har en stor mängd innehåll kan du försöka med att ta bort dem från sidan och se om det här förbättrar saker. Om du tar bort alla möjliga orsaker och lägger till dem på en gång, kan du enkelt se vilka funktioner som är det största problemet och sedan arbeta med en lösning.
