---
title: Importera en termuppsättning med ett SKOS-baserat format
description: Läs mer om att importera en termuppsättning med ett SKOS-baserat format
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 734edbb462193291b6bd2fb4a8e6afc3a0b709cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928254"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importera en termuppsättning med ett SKOS-baserat format

Du kan importera en termuppsättning med ett SKOS-baserat format. Mer information om formatet finns i [SKOS-formatreferens för SharePoint-taxonomi](skos-format-reference.md). Den här funktionen kräver en [SharePoint Syntex](index.md) licens.

Vi rekommenderar att du endast importerar filer med färre än 20 000 termer. Större filer kan göra att verifiering och import tar längre tid.

1. Öppna **Innehållstjänster** i administrationscenter för SharePoint och klicka sedan på **Termlagring**.

2. Välj den termgrupp där du vill importera termuppsättningen.

3. Klicka på **Importera termuppsättning** i kommandofältet.
 
4.  Om du vill ladda ned en exempelfil och använda den som en mall klickar du på **sample-metadata.ttl** för att hämta en exempelfil som använder det SKOS-baserade formatet.
 
5.  Skapa importfilen innehållandes de termuppsättningar och termer du vill importera.

6.  Under **Filformat** väljer du **SKOS (*.ttl)**.

7.  Klicka på **Bläddra**, leta upp och lägg till din importfil.

8.  Klicka på **Importera**. Stäng inte panelen förrän importen har slutförts.

Vid import av filen visas ett meddelande om att importen lyckades och termlagringsplatsen uppdateras. Du kan nu gå till de nyskapade termuppsättningarna.

## <a name="see-also"></a>Se även

[Introduktion till hanterade metadata](/sharepoint/managed-metadata)

[Översikt för dokumenttolkning](document-understanding-overview.md)

[Importera termuppsättningar (webbplatsnivå)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)