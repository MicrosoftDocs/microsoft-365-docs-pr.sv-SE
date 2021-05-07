---
title: Exportera dokument från en granskningsuppsättning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Lär dig hur du markerar och exporterar innehåll från en Advanced eDiscovery granskningsuppsättning för presentationer eller externa granskningar.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162640"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportera dokument från en granskningsuppsättning i Advanced eDiscovery

Med export kan användarna anpassa innehållet som ingår i nedladdningspaketet när du exporterar dokument från en granskningsuppsättning i Advanced eDiscovery.

Så här exporterar du dokument från en granskningsuppsättning:

1. I Microsoft 365 kompatibilitetscenter öppnar du Advanced eDiscovery, väljer fliken Granska **uppsättningar** och väljer sedan den granskningsuppsättning som du vill exportera.

2. Klicka på Åtgärdsexport i   >  **granskningsuppsättningen.**

   Med exportverktyget visas den utfällällade sidan med inställningar för att konfigurera exporten. Vissa alternativ är markerade som standard, men du kan ändra dessa. I följande avsnitt finns beskrivningar av de exportalternativ som du kan konfigurera.

   ![Konfigurationsalternativ för att exportera objekt från en granskningsuppsättning](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. När du har konfigurerat exporten klickar du **på Exportera** för att starta exporten. Beroende på det alternativ  du valde i avsnittet Utdataalternativ kan du komma åt exportfilerna genom direkt nedladdning eller i organisationens Azure Storage konto.

> [!NOTE]
> Exportjobben behålls under hela ärendets livscykel. Men du måste hämta innehållet från ett exportjobb inom 30 dagar efter att exportjobbet är klart.

## <a name="export-options"></a>Exportalternativ

Använd följande alternativ för att konfigurera exporten.

- **Exportera namn:** Namnet på exportjobbet.

- **Beskrivning**: Fritt textfält där du kan lägga till en beskrivning.

- **Exportera de här dokumenten**

  - **Endast markerade dokument:** Med det här alternativet exporteras bara de dokument som är markerade för närvarande.
  
  - **Alla dokument i granskningsuppsättningen**: Med det här alternativet exporteras alla dokument i granskningsuppsättningen.

- **Metadata**
  
  - **Läs in fil:** Den här filen innehåller metadata för varje fil. Den här filen kan vanligtvis matas in med eDiscovery-verktyg från tredje part. Mer information om vilka fält som ingår finns i [Dokumentera metadatafält i Advanced eDiscovery.](document-metadata-fields-in-Advanced-eDiscovery.md)
  
  - **Taggar:** När det här alternativet valts inkluderas taggningsinformation i inläsningsfilen.

- **Content**
  
  - **Ursprungliga filer:** Markera den här kryssrutan om du vill ta med de ursprungliga filerna i dokumenten i granskningsuppsättningen. Om du väljer att exportera ursprungliga filer har du följande alternativ för hur du exporterar chattkonversationer.
  
  - **Konversationsalternativ**

    - **Konversationsfiler:** Det här alternativet exporterar rekonstruerade chattkonversationer. I det här formatet visas konversationer i ett formulär som liknar det som visas i det ursprungliga programmet.

    - **Enskilda chattmeddelanden:** Med det här alternativet exporteras de ursprungliga konversationsfilerna när de lagras i Microsoft 365.

- **Alternativ**

  - **Textfiler**: – Det här alternativet innehåller extraherade textversioner av ursprungliga filer i exporten.
  
  - **Ersätt ursprungliga original med konverterade** PDF-filer: Om pdf-filer som har omaktiverats genereras under granskning är dessa filer tillgängliga för export. Du kan välja att exportera endast de ursprungliga filer som redigerades (genom att inte välja det här alternativet) eller så kan du välja det här alternativet om du vill exportera PDF-filer som innehåller de faktiska redigeringarna.

- **Utdataalternativ:** Exporterat innehåll är antingen tillgängligt för nedladdning direkt via en webbläsare eller kan skickas till ett Azure Storage konto. De två första alternativen ger möjlighet till direkt nedladdning.
  
  - Lösa filer och **PSTs (e-post** läggs till i PSTs om möjligt) : Filer exporteras i ett format som liknar den ursprungliga katalogstrukturen som användare i sina ursprungliga program ser.  Mer information finns i avsnittet [Lösa filer och PST-exportstruktur.](#loose-files-and-pst-export-structure)
  
  - **Komprimerad katalogstruktur:** Filerna exporteras och inkluderas i nedladdningen.
  
  - **Komprimerad katalogstruktur som exporterats till** Azure Storage-konto: Filer exporteras till organisationens Azure Storage konto. För det här alternativet måste du ange URL-adressen för behållaren i ditt Azure Storage att exportera filerna till. Du måste också ange SAS-token (delad åtkomstsignatur) för ditt Azure Storage konto. Mer information finns i Exportera [dokument i en granskning som är inställd på ett Azure Storage konto](download-export-jobs.md).

I följande avsnitt beskrivs mappstrukturen för lösa filer och komprimerade strukturalternativ.

### <a name="loose-files-and-pst-export-structure"></a>Lösa filer och PST-exportstruktur

Om du väljer det här exportalternativet ordnas det exporterade innehållet i följande struktur:

- Rotmapp: Den här mappen i namnet ExportName.zip
  
  - Export_load_file.csv: metadatafilen.
  
  - Summary.csv: En sammanfattningsfil som även innehåller exportstatistik.
  
  - Exchange: Den här mappen innehåller allt innehåll Exchange i ursprungligt filformat. Ursprungliga filer ersätts med omaktiverade PDF-filer om du väljer alternativet Ersätt **omaktiverade inbyggda filer med konverterade PDF-filer.**
  
  - SharePoint: Den här mappen innehåller allt inbyggt innehåll SharePoint i ett ursprungligt filformat. Ursprungliga filer ersätts med omaktiverade PDF-filer om du väljer alternativet Ersätt **omaktiverade inbyggda filer med konverterade PDF-filer.**

### <a name="condensed-directory-structure"></a>Komprimerad katalogstruktur

- Rotmapp: Den här mappen heter ExportName.zip
  
  - Export_load_file.csv: metadatafilen.
  
  - Summary.txt: En sammanfattningsfil som även innehåller exportstatistik.
  
  - NativeFiles: Den här mappen innehåller alla ursprungliga filer som exporterades. Om du exporterar omaktiverade PDF-filer lagras de inte i PST-filer. I stället läggs de till i en avgränsad mapp.
  
  - Error_files: Den här mappen innehåller följande felfiler, om de tas med i exporten:

    - ExtraheringFel: En CSV-fil som innehåller alla tillgängliga metadata för filer som inte extraherats korrekt från överordnade filer.

    - ProcessingError: Den här filen innehåller en lista över dokument med bearbetningsfel. Innehållet är objektnivå, vilket innebär att om en bifogad fil resulterade i ett bearbetningsfel inkluderas e-postmeddelandet som innehåller den bifogade filen i den här mappen.
  
  - Extracted_text_files: Den här mappen innehåller alla extraherade textfiler som skapades vid bearbetningen.
