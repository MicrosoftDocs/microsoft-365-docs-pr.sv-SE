---
title: Microsoft Defender ATP partner affärsmöjligheter och scenarier
ms.reviewer: ''
description: Lär dig hur du kan utöka befintliga säkerhetserbjudanden ovanpå det öppna ramverket och en omfattande uppsättning API:er för att skapa tillägg och integreringar med Microsoft Defender ATP
keywords: API, partner, utöka, öppna ramverket, api:er, tillägg, integreringar, identifiering, hantering, svar, svagheter, information
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1db82afa06fd0b6b3d7228aaf3020c5496ed69e7
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186899"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a>Microsoft Defender för slutpunkt partner affärsmöjligheter och scenarier

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Partner kan enkelt utöka sina befintliga säkerhetserbjudanden ovanpå det öppna ramverket och en omfattande och fullständig uppsättning API:er för att skapa tillägg och integreringar med Defender för Slutpunkt. 

API:erna omfattar funktionella områden, inklusive identifiering, hantering, svar, säkerhetsproblem och användningsfall som omfattar information. Baserat på användningsfall och behov kan partner antingen strömma eller fråga data från Defender för Slutpunkt. 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a>Scenario 1: Extern aviseringskorrelation och automatiserad undersökning och åtgärd
Defender för Endpoint erbjuder unika automatiska undersöknings- och åtgärdsfunktioner för att köra incidentåtgärder med en skala. 

Genom att integrera automatisk undersökning och svarsfunktioner med andra lösningar, till exempel produkter för nätverkssäkerhet eller andra slutpunktssäkerhetsprodukter, blir det bättre att hantera aviseringar. Integreringen minimerar också komplexiteten kring nätverks- och enhets signalkorrelation, vilket effektiviserar undersöknings- och hotåtgärder på enheter.

Defender för Endpoint lägger till stöd för det här scenariot i följande formulär:

- Externa aviseringar kan skickas till Defender för Slutpunkt och presenteras sida vid sida med ytterligare enhetsbaserade aviseringar från Defender för Slutpunkt. Den här vyn ger en fullständig kontext av varningen – med den faktiska processen och hela attackprocessen.

- När en avisering skapas delas signalen mellan alla Defender för slutpunktsskyddade slutpunkter i företaget. Defender för Endpoint tar omedelbart automatiserat eller operatörs assisterat svar för att åtgärda aviseringen.

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a>Scenario 2: Säkerhetshantering och automationssvarsintegrering (SOAR)
Om du tar bort olika lösningar kan du skapa spelböcker och integrera den omfattande datamodellen och åtgärderna som Defender för slutpunkts-API:er exponerar för att få svar, till exempel fråga om enhetsdata, utlösa enhetsisolering, blockera/tillåta, åtgärda aviseringar och andra.

## <a name="scenario-3-indicators-matching"></a>Scenario 3: Indikatormatchning 
Indikator på kompromettering (IoCs) är en viktig funktion i varje lösning för slutpunktsskydd. Den här funktionen är tillgänglig i Defender för Endpoint och ger möjlighet att ange en lista över indikatorer för skydd, identifiering och exkludering av enheter. En kan definiera vilken åtgärd som ska vidtas samt varaktigheten för när åtgärden ska tillämpas.

Ovanstående scenarier fungerar som exempel på plattformens utökningsbarhet. Du är inte begränsad till exemplen och vi uppmuntrar dig verkligen att använda det öppna ramverket för att upptäcka och utforska andra scenarier.

Följ stegen i Bli [en Microsoft Defender för Slutpunkt-partner för](get-started-partner-integration.md) att integrera din lösning i Defender för Slutpunkt.

## <a name="related-topic"></a>Relaterat ämne
- [Översikt över hantering och API:er](management-apis.md)
