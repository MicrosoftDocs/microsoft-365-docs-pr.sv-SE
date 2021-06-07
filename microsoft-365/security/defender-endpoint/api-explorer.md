---
title: API Explorer i Microsoft Defender för Slutpunkt
ms.reviewer: ''
description: Använda API Explorer för att skapa och göra API-frågor, testa och skicka förfrågningar för alla tillgängliga API
keywords: api, explorer, send, request, get, post,
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
ms.custom: api
ms.openlocfilehash: 6a5684d71d34b3efdfe915ae674b4fcb90342154
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769803"
---
# <a name="api-explorer"></a>API Explorer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)


Microsoft Defender för slutpunkts-API Explorer är ett verktyg som hjälper dig att utforska olika Defender för slutpunkts-API:er interaktivt. 

MED API Explorer är det enkelt att skapa och göra API-frågor, testa och skicka förfrågningar för tillgängliga Defender för Endpoint API-slutpunkt. Använd API Explorer för att vidta åtgärder eller hitta data som kanske ännu inte är tillgängliga i användargränssnittet.

Verktyget är användbart under programutveckling. Du kan utföra API-frågor som respekterar dina inställningar för användaråtkomst, vilket minskar behovet av att skapa åtkomsttoken.

Du kan också använda verktyget för att utforska galleriet med exempelfrågor, kopiera exempel på resultatkoder och generera felsökningsinformation.

Med API Explorer kan du:

- Kör begäranden för alla metoder och se svar i realtid
- Bläddra snabbt igenom API-exemplen och lär dig vilka parametrar de stöder
- Gör API-anrop enkelt. du behöver inte autentisera utöver hanteringsportalens inloggning

## <a name="access-api-explorer"></a>Access API Explorer

I den vänstra navigeringsmenyn väljer du **Partners & API Explorer**  >  .

## <a name="supported-apis"></a>API:er som stöds

API Explorer har stöd för alla API:er som erbjuds av Defender för Endpoint.
  
Listan över API:er som stöds finns i [API:er-dokumentationen.](apis-intro.md) 

## <a name="get-started-with-the-api-explorer"></a>Komma igång med API Explorer

1. I den vänstra rutan finns en lista med exempelbegäranden som du kan använda. 
2. Följ länkarna och klicka på **Kör fråga.** 

Vissa exempel kan kräva att du anger en parameter i URL:en, till exempel {machine- ID}.

## <a name="faq"></a>Vanliga frågor och svar

**Måste jag ha en API-token för att använda API Explorer?** <br>
Autentiseringsuppgifter för att komma åt ett API behövs inte. API Explorer använder Defender för slutpunktshanteringsportal-token när en begäran begärs.

De inloggade autentiseringsuppgifterna för användare används för att verifiera att API Explorer har behörighet att komma åt data för din räkning.

Vissa API-begäranden är begränsade baserat på dina RBAC-behörigheter. En begäran om att skicka-indikatorn är till exempel begränsad till rollen som säkerhetsadministratör. 
