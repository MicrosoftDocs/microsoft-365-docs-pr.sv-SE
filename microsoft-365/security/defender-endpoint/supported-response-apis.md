---
title: Svars-API:er som stöds av Microsoft Defender Advanced Threat Protection
description: Läs mer om specifika svarsrelaterade Microsoft Defender API-anrop för avancerat skydd.
keywords: response apis, graph api, stöds apis, aktör, aviseringar, enhet, användare, domän, ip, fil
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: a290c431f6d81b23896ddf77e7c7a47de378de22
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185557"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>Microsoft Defender för slutpunktsfråge-API:er som stöds 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

Läs mer om vilka svarsrelaterade API-anrop som stöds som du kan köra och information om till exempel rubriker för begäran och förväntat svar från samtalen.

## <a name="in-this-section"></a>I det här avsnittet
Ämne | Beskrivning
:---|:---
Paket för insamling av undersökning | Kör detta API för att samla in ett undersökningspaket från en enhet.
Identifiera enhet | Kör detta API för att isolera en enhet från nätverket.
Ta bortisolera enhet | Ta bort en enhet från isolation. 
Begränsa kodkörning | Kör detta API för att innehålla en attack genom att stoppa skadliga processer. Du kan också låsa en enhet och förhindra att efterföljande försök till potentiellt skadliga program körs.
Obegränsad kodkörning | Kör detta för att återställa begränsningen för programprincipen när du har kontrollerat att den komprometterade enheten har åtgärdats.
Kör antivirussökning | Starta en antivirussökning på distans för att identifiera och åtgärda skadlig programvara som kan finnas på en komprometterad enhet.
Stoppa och sätt filen i karantän |  Kör det här anropet för att sluta köra processer, sätta filer i karantän och ta bort beständiga funktioner, till exempel registernycklar.
Exempel på förfrågan | Kör det här anropet för att begära ett exempel på en fil från en viss enhet. Filen samlas in från enheten och laddas upp till ett säkert lagringsutrymme.
Blockera fil | Kör det här API:t för att förhindra ytterligare spridning av en attack i organisationen genom att förbjuda potentiellt skadliga filer eller misstänkt skadlig programvara. 
Ta bort blockering av fil | Tillåt att en fil körs i organisationen med Microsoft Defender Antivirus.
Hämta SAS URI för paket | Kör detta API för att få en URI som gör att du kan ladda ned ett undersökningspaket.
Skaffa MachineAction-objekt | Kör detta API för att få MachineAction-objekt.
Skaffa MachineActions-samlingen | Kör detta för att få MachineAction-samlingen.
Skaffa FileActions-samlingen | Kör detta API för att få FileActions-samlingen.
Skaffa FileMachineAction-objekt | Kör detta API för att få FileMachineAction-objekt.
Hämta FileMachineActions-samlingen | Kör detta API för att få FileMachineAction-samlingen.
