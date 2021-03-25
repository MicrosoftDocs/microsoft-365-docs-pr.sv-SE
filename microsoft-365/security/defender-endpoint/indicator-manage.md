---
title: Hantera indikatorer
ms.reviewer: ''
description: Hantera indikatorer för en filhash, IP-adress, URL:er eller domäner som definierar identifiering, skydd och undantag för enheter.
keywords: importera, indikator, lista, ioc, csv, hantera, tillåten, blockerad, blockera, rensa, skadlig, filshashar, ip-adress, url:er, domän
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185951"
---
# <a name="manage-indicators"></a>Hantera indikatorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. Välj Inställningar Indikatorer i  >  **navigeringsfönstret.**

2. Välj fliken för den entitetstyp som du vill hantera.  

3. Uppdatera information om indikatorn och klicka  **på Spara** eller klicka på knappen Ta bort om du vill ta bort entiteten från listan.

## <a name="import-a-list-of-iocs"></a>Importera en lista med IoCs

Du kan också välja att ladda upp en CSV-fil som definierar attribut för indikatorer, den åtgärd som ska vidtas och annan information.

Ladda ned CSV-exemplet för att ta fram de kolumnattribut som stöds.

1. Välj Inställningar Indikatorer i  >  **navigeringsfönstret.**

2. Välj fliken för den enhetstyp som du vill importera indikatorer för.

3. Välj **Importera**  >  **välj fil**. 

4. Välj **Importera.** Gör så här för alla filer du vill importera. 

5. Välj **Klar**.

I följande tabell visas de parametrar som stöds.

Parameter | Skriv    |   Beskrivning
:---|:---|:---
indicatorType | Uppräkning | Typ av indikator. Möjliga värden är: "FileSha1", "FileSha256", "IpAddress", "DomainName" och "Url". **Obligatoriskt**
indicatorValue | Sträng | Identiteten för [indikatorenheten.](ti-indicator.md) **Obligatoriskt**
åtgärd | Uppräkning | Den åtgärd som kommer att vidtas om indikatorn upptäcks i organisationen. Möjliga värden är: "Avisering", "AviseringOchBlock" och "Tillåtet". **Obligatoriskt**
rubrik | Sträng | Indikatoraviseringens rubrik. **Obligatoriskt**
beskrivning | Sträng |  Beskrivning av indikatorn. **Obligatoriskt**
expirationTime | DateTimeOffset | Förfallodatum för indikatorn i följande format YYYY-MM-DDTHH:MM:SS.0Z. **Valfritt**
allvarlighetsgrad | Uppräkning | Indikatorns allvarlighetsgrad. Möjliga värden är: "Informationsblad", "Låg", "Medel" och "Hög". **Valfritt**
recommendedActions | Sträng | Rekommenderade åtgärder för TI-indikatoraviseringar. **Valfritt**
rbacGroupNames | Sträng | Kommaavgränsade listor med namn på RBAC-grupper indikatorn skulle tillämpas på. **Valfritt**
kategori | Sträng | Kategorin för aviseringen. Några exempel: Åtkomst för körning och autentiseringsuppgifter. **Valfritt**
mitretechniques| Sträng | MITRE-tekniker, kod/id (kommaavgränsade). Mer information finns i [Enterprise taktiker](https://attack.mitre.org/tactics/enterprise/). **Valfritt** Vi rekommenderar att du lägger till ett värde i kategori när du använder en MITRE-teknik.

Mer information finns i [Microsoft Defender för slutpunktsvarningskategorier](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)är nu i linje med MITRE ATT&CK! .


## <a name="see-also"></a>Se även
- [Skapa indikatorer](manage-indicators.md)
- [Skapa indikatorer för filer](indicator-file.md)
- [Skapa indikatorer för IP-adresser och URL:er/domäner](indicator-ip-domain.md)
- [Skapa indikatorer baserade på certifikat](indicator-certificates.md)
