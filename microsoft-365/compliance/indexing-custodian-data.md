---
title: Avancerad indexering av dokumentägardata
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
description: När en vårdnadshavare läggs till i ett Advanced eDiscovery ärende bearbetas allt innehåll som anses vara delvis indexerat på nytt så att det blir sökbart.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161991"
---
# <a name="advanced-indexing-of-custodian-data"></a>Avancerad indexering av dokumentägardata

När en vårdnadshavare läggs till i ett Advanced eDiscovery ärende bearbetas allt innehåll som anses vara delvis indexerat på nytt så att det blir sökbart.  Den här processen kallas *Avancerad indexering.* Innehåll kan indexeras delvis av flera olika anledningar, till exempel att det finns bilder, filtyper som inte stöds eller när begränsning av filstorlek för indexering påträffas.

Mer information om att bearbeta stöd och delvis indexerade objekt finns i:

- [Filtyper som stöds i Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Delvis indexerade objekt i innehållssökning i Office 365](partially-indexed-items-in-content-search.md)

- [Filformat som indexeras av Exchange Search](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Förvalda filnamnstillägg och filtyper som crawlas och analyseras i SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Visa avancerade indexeringsresultat

När indexeringsprocessen Avancerat är klar får du en förståelse för hur effektiv ombearbetningen är.  I vyn Avancerat indexeringsresultat på fliken **Bearbetning** för ett ärende visar diagrammet antalet objekt som lagts till i *hybridindexet.*  I hybridindexet lagras Advanced eDiscovery bearbetat innehåll.

Den här vyn innehåller också antalet objekt som kräver åtgärd och ett annat diagram med fel efter filtyp. Mer information finns i:

- [Åtgärda fel vid bearbetning av data](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Felåtgärder för enskilt objekt](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Uppdatera Avancerat index för bibliotek

När en vårdnadshavare läggs till i Advanced eDiscovery fall bearbetas alla delvis indexerade objekt. Men allt eftersom det går kan mer delvis indexerade objekt läggas till i en användares postlåda eller OneDrive konto.  Om det behövs kan du uppdatera indexet för specifik vårdnadshavare. Mer information finns i Hantera [vårdnadshavare i ett Advanced eDiscovery fall.](manage-new-custodians.md#re-index-custodian-data) Du kan även uppdatera indexet för alla informaterade i ett fall genom att klicka **på Uppdateringsindex** på **fliken** Bearbetning.

> [!NOTE]
> Uppdatering av katalogindex är en process som redan pågår. Vi rekommenderar att du inte uppdaterar index mer än en gång om dagen.