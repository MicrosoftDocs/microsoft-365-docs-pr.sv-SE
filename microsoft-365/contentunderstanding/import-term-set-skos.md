---
title: Importera en term uppsättning med ett SKOSt format
description: Lär dig hur du importerar en term uppsättning med ett SKOSt format
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296234"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importera en term uppsättning med ett SKOSt format

Du kan importera en term uppsättning med ett SKOSt format. Mer information om formatet finns i [SharePoint-taxonomi för SKOS format](skos-format-reference.md).

Vi rekommenderar att du sparar dina import filer på färre än 20 000 villkor. Större filer kan öka tiden för validering och import.

1. Expandera **innehålls tjänster**i administrations centret för SharePoint och klicka sedan på **term lagrings plats**.

2. Välj den term grupp där du vill importera term uppsättningen.

3. Klicka på **Importera term uppsättning**i kommando fältet.
 
4.  Om du vill ladda ned en exempel fil som du vill använda som mall klickar du på **Sample-metadata. TTL** för att hämta en exempel fil som använder det SKOSbaserade formatet.
 
5.  Skapa import filen som innehåller term uppsättningarna & villkor som du vill importera.

6.  Under **fil format**väljer du **SKOS (*. TTL)**.

7.  Klicka på **Bläddra** och navigera till och Lägg till en import fil.

8.  Klicka på **Importera**. Stäng inte panelen förrän importen är klar.

När filen importeras visas ett meddelande om att det är klart och term lagrings platsen uppdateras och du kan navigera till de nya term uppsättningarna.

## <a name="see-also"></a>Se även

[Introduktion till hanterade metadata](https://docs.microsoft.com/sharepoint/managed-metadata)

[Översikt över dokument förståelse](document-understanding-overview.md)

[Importera term uppsättningar (webbplats nivå)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)