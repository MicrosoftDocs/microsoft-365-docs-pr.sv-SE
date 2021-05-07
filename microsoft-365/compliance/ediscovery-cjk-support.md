---
title: Stöd för CJK/Double Byte för Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig Advanced eDiscovery tecken Microsoft 365 kinesiska, japanska och koreanska (CJK) som använder teckenuppsättning med dubbla byte.
ms.openlocfilehash: ee47c5cd7f1a378ccfff05b8f7712e91092907cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162234"
---
# <a name="cjk-language-support-for-advanced-ediscovery"></a>CJK-språkstöd för Advanced eDiscovery

Advanced eDiscovery har stöd för språk med teckenuppsättning med dubbla byte (till exempel förenklad kinesiska, traditionell kinesiska, japanska och koreanska som gemensamt kallas *CJK-språk)* för följande avancerade scenarier i en granskningsuppsättning:

- När du [ställer frågor mot data i en granskningsuppsättning](review-set-search.md).

- När du [taggar dokument i en granskningsuppsättning](tagging-documents.md).

- När du [analyserar ärendedata i en granskningsuppsättning med](analyzing-data-in-review-set.md) nästan dubblettidentifiering, e-posttrådning och teman.

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

**Hur skapar jag en sökning för att samla objekt som innehåller CJK-tecken?**

Du kan använda CJK-tecken [för](building-search-queries.md#keyword-searches) [nyckelordssökningar, nyckelordsfrågor](keyword-queries-and-search-conditions.md) och sökvillkor när du söker efter innehåll i Advanced eDiscovery. Det går även att söka efter CJK-tecken när du söker efter innehåll i Core eDiscovery och Content Search.

Vi har stöd för CJK [för](keyword-queries-and-search-conditions.md#search-operators) alla sökoperatorer och sökvillkor, [](keyword-queries-and-search-conditions.md#search-conditions)inklusive booleska operatorer **OCH,** **ELLER,** **NOT** och **NEAR.**

Om du är säker på att innehållsplatser eller objekt innehåller CJK-tecken men sökningar inte returnerar några resultat klickar du på ikonen för frågans språk/land/region ![Ikonen för språk/region för fråga i innehållssökning](../media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) och välj motsvarande språk-land-kulturkodvärde för sökningen. Standardspråket/regionen är neutral.

**Kan jag söka efter flera språk samtidigt?**

Det beror på sökscenariot.

- När du [avfrågar data i en granskningsuppsättning](review-set-search.md) Advanced eDiscovery kan du söka efter flera språk.

- När du [skapar en sökning för att samla in data](create-search-to-collect-data.md)skapar du en separat sökning för varje språk du riktar. Om du till exempel söker efter ett dokument som innehåller både kinesiska och koreanska väljer du Kinesiska för din första fråga och sedan Koreanska för din andra fråga.

**Jag ser inte ikonen för att välja språk/region för frågan för att välja ett språk för frågor i en granskningsuppsättning. Hur anger jag ett frågespråk i en granskningsuppsättningssökning?**

För frågor i en granskningsuppsättning behöver du inte ange ett dokumentspråk. Advanced eDiscovery automatiskt identifierar dokumentspråk när du lägger till innehåll i en granskningsuppsättning. Det hjälper dig att optimera frågeresultatet i en granskningsuppsättning.

**Kan jag se identifierade språk i [filmetadata?](view-documents-in-review-set.md#file-metadata)**

Nej, du kan inte se identifierade språk i filmetadata.

**Kan jag filtrera efter dokumentspråk i en granskningsuppsättning?**

Nej, du kan inte filtrera, sortera eller söka efter dokumentspråk i en granskningsuppsättning.

**Påverkar den här CJK-versionen för granskningsscenarier några av mina befintliga sökningar och granskningsuppsättningar?**

Nej, inga av dina befintliga sökningar eller granskningsuppsättningar kommer att ändras. Du behöver inte indexera om befintliga data, och sökresultaten för text på engelska är desamma.

**Hur ändrar jag visningsspråket till kinesiska, japanska eller koreanska?**

Mer information om hur du ändrar visningsspråk och tidszon finns i Så här anger du språk- och [regionsinställningar för Office 365.](/office365/troubleshoot/access-management/set-language-and-region)

## <a name="known-issues"></a>Kända problem

- OCR stöder inte CJK-tecken från bildfiler

- E-postfiler (till exempel *.eml och [](view-documents-in-review-set.md#annotate-view) *.msg) i vyn Anteckningar stöds inte för CJK-språk.

- Sökningsmarkering i [textvyn](view-documents-in-review-set.md#text-view) stöds inte för CJK-språk.

- Den [relevansmodul](using-relevance.md) som används för att analysera data stöder inte CJK-språk.

- [Frågebaserade spärrade](managing-holds.md#manage-non-custodial-holds) frågor stöds inte för CJK-språk.