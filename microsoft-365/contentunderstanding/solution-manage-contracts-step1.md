---
title: Steg 1. Använda SharePoint Syntex för att identifiera kontraktsfiler och extrahera data
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig hur du använder SharePoint Syntex för att identifiera kontraktsfiler och extrahera data med hjälp av en Microsoft 365 lösning.
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281339"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>Steg 1. Använda SharePoint Syntex för att identifiera kontraktsfiler och extrahera data

Din organisation behöver ett sätt att identifiera och klassificera alla kontraktsdokument från de många filer du får. Du vill också snabbt kunna visa flera nyckelelement i var och en av de identifierade kontraktsfilerna (till exempel *kund,* entreprenör *och* *avgiftsbelopp).* Det kan du göra genom att [SharePoint Syntex för](index.md) att skapa en dokumentförståelsemodell och använda den på ett dokumentbibliotek.

[Dokument förstå](document-understanding-overview.md) använder artificiell intelligens (AI) modeller för att automatisera klassificering av filer och extrahering av information. Dokument förstå modeller är också optimala för att extrahera information från ostrukturerade och semi-strukturerade dokument där den information du behöver inte finns i tabeller eller formulär, till exempel kontrakt.

1. Först måste du hitta minst fem exempelfiler som du kan använda för att "utbilda" modellen för att söka efter egenskaper som är specifika för den innehållstyp som du försöker identifiera (ett kontrakt). 

2. Med SharePoint Syntex kan du skapa en ny modell för dokumentförståelse. När du använder exempelfilerna måste [du skapa en klassificerare](create-a-classifier.md). Genom att utbilda klassificeraren med dina exempelfiler lär du dig att söka efter egenskaper som är specifika för det du skulle se i företagets kontrakt. Skapa till [exempel en "förklaring"](create-a-classifier.md#create-an-explanation) som söker efter specifika strängar som finns i ditt avtal, till exempel *Tjänstavtal,* *Avtalsvillkor* och *Kompensation.* Du kan till och med utbilda din förklaring så att du kan leta efter de här strängarna i specifika avsnitt i dokumentet eller ligga bredvid andra strängar. När du tror att du har utbildat din klassificerare med den information som behövs kan du testa modellen på en exempeluppsättning exempelfiler för att se hur effektivt den är. Efter att ha testat kan du, om det behövs, välja att ändra dina förklaringar för att göra dem mer effektiva. 

3. I modellen kan du skapa [en extraherare för att](create-an-extractor.md) hämta specifika data från varje kontrakt. För varje kontrakt är den information som du är mest orolig för till exempel vem klienten är, namnet på entreprenören och totalkostnaden.

4. När du har skapat din modell kan [du använda den på SharePoint ett dokumentbibliotek](apply-a-model.md). När du laddar upp dokument till dokumentbiblioteket körs dokument förstå modellen för dokument och kommer att identifiera och klassificera alla filer som matchar den typ av innehåll som du har definierat i modellen. Alla filer som klassificeras som kontrakt visas i en anpassad biblioteksvy. Filerna visar också värdena från varje kontrakt som du definierade i extraheraren.

   ![Kontrakt i dokumentbibliotek](../media/content-understanding/doc-lib-solution.png)

5. Om du dessutom har kvarhållningskrav för kontrakten kan [](apply-a-retention-label-to-a-model.md) du också använda modellen för att använda en bevarandeetikett som gör att kontrakten inte raderas under en viss tidsperiod.

## <a name="next-step"></a>Nästa steg

[Steg 2. Använd Microsoft Teams för att skapa din kanal för kontraktshantering](solution-manage-contracts-step2.md)