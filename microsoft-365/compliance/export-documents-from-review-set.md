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
ms.openlocfilehash: 76865ae92d3b3090ae2bba01c9b3e9e0f1f86366
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244367"
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

Använd följande alternativ för att konfigurera exporten. Vissa utdataalternativ är inte tillåtna, de viktigaste är att exportera textfiler och PDF-filer som har omformaterats, inte tillåts vid export till PST-format.

- **Exportera namn:** Namnet på exportjobbet. Används för att namnge ZIP-filerna som ska laddas ned.

- **Beskrivning**: Fritt textfält där du kan lägga till en beskrivning.

- **Exportera de här dokumenten**

  - Endast markerade dokument: Med det här alternativet exporteras endast de dokument som är markerade för närvarande. Det här alternativet är bara tillgängligt när objekt markeras i en granskningsuppsättning.
  - Alla filtrerade dokument: Med det här alternativet exporteras dokumenten i ett aktivt filter. Det här alternativet är bara tillgängligt när ett filter tillämpas på granskningsuppsättningen.
  - Alla dokument i granskningsuppsättningen: Med det här alternativet exporteras alla dokument i granskningsuppsättningen.

- **Utdataalternativ:** Exporterat innehåll är antingen tillgängligt för nedladdning direkt via en webbläsare eller kan skickas till ett Azure Storage konto. De två första alternativen ger möjlighet till direkt nedladdning.
  
  - Endast rapporter: Endast sammanfattnings- och inläsningsfilen skapas.
  - Lösa filer och PSTs (e-post läggs till i PSTs om möjligt): Filer exporteras i ett format som liknar den ursprungliga katalogstrukturen som användare ser i sina ursprungliga program.  Mer information finns i avsnittet [Lösa filer och PST-exportstruktur.](#loose-files-and-pst-export-structure)
  - Komprimerad katalogstruktur: Filerna exporteras och inkluderas i nedladdningen.
  - Komprimerad katalogstruktur som exporterats till Azure Storage-konto: Filer exporteras till organisationens Azure Storage konto. För det här alternativet måste du ange URL-adressen för behållaren i ditt Azure Storage att exportera filerna till. Du måste också ange SAS-token (delad åtkomstsignatur) för ditt Azure Storage konto. Mer information finns i Exportera [dokument i en granskning som är inställd på ett Azure Storage konto](download-export-jobs.md).

- **Inkludera**
  - Taggar: När det här alternativet valts inkluderas taggningsinformationen i inläsningsfilen.
  - Textfiler: Det här alternativet innehåller extraherade textversioner av ursprungliga filer i exporten.
  - Ersätt inbyggda filer med konverterade PDF-filer: Om pdf-filer som har omaktiverats genereras under granskning är dessa filer tillgängliga för export. Du kan välja att exportera endast de ursprungliga filer som redigerades (genom att inte välja det här alternativet) eller så kan du välja det här alternativet om du vill exportera PDF-filer som innehåller de faktiska redigeringarna.

## <a name="the-following-sections-describe-the-folder-structure-for-loose-files-and-condensed-directory-structure-options"></a>I följande avsnitt beskrivs mappstrukturen för lösa filer och alternativ för komprimerad katalogstruktur

Exporter partitioneras till ZIP-filer med en maximal storlek på okomprimerat innehåll på 75 GB. Om exporten är mindre än 75 GB består exporten av en sammanfattningsfil och en enda ZIP-fil. För exporter som överskrider 75 GB okomprimerade data skapas flera ZIP-filer. När ZIP-filerna har laddats ned kan de komprimeras till en enda plats för att återskapa den fullständiga exporten.

### <a name="loose-files-and-pst-export-structure"></a>Lösa filer och PST-exportstruktur

Om du väljer det här exportalternativet ordnas det exporterade innehållet i följande struktur:

- Summary.csv: Innehåller en sammanfattning av innehållet som exporterats från granskningsuppsättningen
- Rotmapp: Den här mappen med namnet [Exportnamn] x z.zip och upprepas för varje ZIP-filpartition.
  - Export_load_file_x av z.csv: metadatafilen.
  - Varningar och fel x z.csv: Den här filen innehåller information om fel som påträffades när du försökte exportera från granskningsuppsättningen.
  - Exchange: Den här mappen innehåller allt innehåll från Exchange som lagras i PST-filer. Omaktiverade PDF-filer kan inte inkluderas med det här alternativet. Om en bifogad fil markeras i granskningsuppsättningen exporteras det överordnade e-postmeddelandet med den bifogade filen.
  - SharePoint: Den här mappen innehåller allt inbyggt innehåll SharePoint i ett ursprungligt filformat. Omaktiverade PDF-filer kan inte inkluderas med det här alternativet.

### <a name="condensed-directory-structure"></a>Komprimerad katalogstruktur

- Summary.csv: Innehåller en sammanfattning av innehållet som exporterats från granskningsuppsättningen
- Rotmapp: Den här mappen med namnet [Exportnamn] x z.zip och upprepas för varje ZIP-filpartition.
  - Export_load_file_x av z.csv: Metadatafilen och innehåller även platsen för varje fil som lagras i ZIP-filen.
  - Varningar och fel x z.csv: Den här filen innehåller information om fel som påträffades när du försökte exportera från granskningsuppsättningen.
  - NativeFiles: Den här mappen innehåller alla ursprungliga filer som exporterades. Ursprungliga filer ersätts med omaktiverade PDF-filer om du väljer alternativet Ersätt *omaktiverade inbyggda filer med konverterade PDF-filer.*
  - Error_files: Den här mappen innehåller filer som hade antingen extrahering eller annat bearbetningsfel. Filerna placeras i olika mappar, antingen ExtraheringFel eller ProcessingError. Dessa filer visas i inläsningsfilen.
  - Extracted_text_files: Den här mappen innehåller alla extraherade textfiler som skapades vid bearbetningen.

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a>Komprimerad katalogstruktur exporterad till ditt Azure Storage konto

Det här alternativet har samma allmänna struktur som *komprimerad* katalogstruktur, men innehållet zippas inte och data sparas i ditt Azure Storage konto. Det här alternativet används i allmänhet när du arbetar med en eDiscovery-leverantör från tredje part. Mer information om hur du använder det här alternativet finns i [Exportera dokument i en granskning inställd på ett Azure Storage konto](download-export-jobs.md).
