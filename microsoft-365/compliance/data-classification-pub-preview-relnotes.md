---
title: Viktig information för dataklassificering
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: normal
recommendations: false
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Information om dataklassificering.
ms.openlocfilehash: bbce01555367c6151a7b16b551d5580ebcaf9d43
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52162914"
---
# <a name="data-classification-release-notes"></a>Viktig information för dataklassificering


## <a name="exchange-mailbox-count"></a>Exchange postlådans antal

Du ser att en liten verktygstips visas när du går in på detaljgranskning Exchange postlådor. Detta för att visa att det samlade antalet som visas för typ av känslig information, känslighetsetikett och bevarandeetikett kanske inte exakt matchar antalet objekt som du hittar i postlådan. Det beror på att den granska nedåt i mappen hämtar live-vy av innehåll, som klassificeras, medan det samlade antalet beräknas.


## <a name="rendering-of-encrypted-documents"></a>Återgivning av krypterade dokument

SharePoint, Exchange och OneDrive som är krypterade återges inte i innehållsutforskaren. Det här är ett känsligt problem som kräver en balans mellan behovet av att se filinnehåll i Innehållsutforskaren och behovet av att hålla innehållet krypterat. Med de behörigheter som beviljas av  Visningsprogram för innehållsutforskaren och med rollgrupperna Innehållsvisningsprogram för innehållsutforskaren visas en listvy över filerna, filernas metadata och en länk som du kan använda för att komma åt innehållet via webbklienten.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Tecken som stöds i namn på bevarandeetiketter SharePoint sökning

SharePoint inte har stöd för bevarandeetikettnamn med `-` eller `_` i dem. Till `Label-MIP` exempel, `Label_MIP` och stöds inte. SharePoint sökningen stöder dessa tecken i känslighetsetikettnamn och namn på typer av känslig information.

## <a name="onedrive-remains-in-preview"></a>OneDrive förblir i förhandsgranskning

Tack för din värdefulla feedback om OneDrive integration under vårt förhandsversionsprogram. När vi går igenom de specifika uppgifterna kan du få inkonsekventa data/flöden. Vi fortsätter att visa upp OneDrive i förhandsgranskningen tills alla korrigeringar är på plats. Vi uppskattar din fortsatta support.


## <a name="see-also"></a>Se även

- [Komma igång med dataklassificering (förhandsversion)](data-classification-overview.md)
- [Visa aktivitet med etiketter (förhandsvisning)](data-classification-activity-explorer.md)
- [Visa märkt innehåll (förhandsvisning)](data-classification-content-explorer.md)
- [Mer information om känslighetsetiketter](sensitivity-labels.md)
- [Mer information om kvarhållningsprinciper och kvarhållningsetiketter](retention.md)
- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)