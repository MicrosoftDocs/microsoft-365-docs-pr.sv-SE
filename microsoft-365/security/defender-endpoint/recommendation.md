---
title: Rekommendationsmetoder och egenskaper
description: Hämtar de senaste aviseringarna.
keywords: apis, graph api, API som stöds, skaffa, aviseringar, senaste
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6ab4d4e1acab0e4b837195f64c369057d7ceb417
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198239"
---
# <a name="recommendation-resource-type"></a>Rekommendation för resurstyp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Metoder
Metod |Returtyp |Beskrivning
:---|:---|:---
[Lista alla rekommendationer](get-all-recommendations.md) | Samling med rekommendation | Hämtar en lista över alla säkerhetsrekommendationer som påverkar organisationen
[Få rekommendation från Id](get-recommendation-by-id.md) | Rekommendation | Hämtar en säkerhetsrekommendationer genom sitt ID
[Skaffa programvara som du rekommenderas](get-recommendation-software.md)| [Programvara](software.md) | Hämtar en säkerhetsrekommendationer för en viss programvara
[Få rekommendationsenheter](get-recommendation-machines.md)|MachineRef-samling | Hämtar en lista över enheter som är kopplade till säkerhetsrekommendationer
[Få rekommendationer om säkerhetsproblem](get-recommendation-vulnerabilities.md) | [Sårbarhetssamling](vulnerability.md) | Hämtar en lista över säkerhetsproblem som är knutna till säkerhetsrekommendationer


## <a name="properties"></a>Egenskaper
Egenskap |   Skriv   |   Beskrivning
:---|:---|:---
id | Sträng | Rekommendations-ID
productName | Sträng | Namn på relaterad programvara  
recommendationName | Sträng | Rekommendationens namn
Svagheter | Long | Antal identifierade säkerhetsproblem
Leverantör | Sträng | Relaterade leverantörsnamn
recommendedVersion | Sträng | Rekommenderad version
rekommendationKategori | Sträng | Kategorin Rekommendation. Möjliga värden är: "Konton", "Program", "Nätverk", "OS", "SecurityStack"
underKategori | Sträng | Underkategorin Rekommendation
allvarlighetsstreck | Double | Konfigurationens potentiella påverkan på organisationens Microsoft Secure Score för enheter (1–10)
publicExploit | Boolesk | Offentlig sårbarhet är tillgänglig 
activeAlert | Boolesk | Aktiv avisering är kopplad till denna rekommendation
associatedThreats | Strängsamling | Rapporten hotanalys är associerad med den här rekommendationen
remediationType | Sträng | Åtgärdstyp. Möjliga värden är: "ConfigurationChange","Update","Upgrade","Uninstall"
Status | Uppräkning | Status för rekommendations undantag. Möjliga värden är: "Aktiv" och "Undantag"
configScoreImpact | Double | Microsoft Secure Score för enheter påverkas
exponeringImpacte | Double | Påverkan på exponeringsresultat
totalMachineCount | Long | Antal installerade enheter
exposedMachinesCount | Long | Antal installerade enheter som exponeras för säkerhetsproblem
nonProductivityImpactedAssets | Long | Antal enheter som inte påverkas  
relatedComponent | Sträng |  Relaterad programvarukomponent
