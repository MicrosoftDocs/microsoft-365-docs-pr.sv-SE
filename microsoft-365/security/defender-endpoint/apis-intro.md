---
title: Få åtkomst till Microsoft Defender för Endpoint API
ms.reviewer: ''
description: Lär dig hur du kan använda API:er för att automatisera arbetsflöden och ny information baserat på Microsoft Defender för slutpunktsfunktioner
keywords: apis, api, wdatp, open api, microsoft defender för endpoint api, microsoft defender atp, public api, apis som stöds, aviseringar, enhet, användare, domän, ip, fil, avancerad sökning, fråga
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9d3f4431825193d189f7ea1d73b6a99163cac428
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843704"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Få åtkomst till Microsoft Defender för Endpoint API 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Gäller för:** 
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender för Slutpunkt visar mycket av dess data och åtgärder via en uppsättning programmässiga API:er. De HÄR API:erna gör det möjligt att automatisera arbetsflöden och nya funktioner baserat på Defender för slutpunktsfunktioner. API-åtkomst kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 auktoriseringskod för Flow.](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)

Titta på den här videon för en snabb överblick över Defender för Endpoints API:er. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

I allmänhet måste du vidta följande steg för att använda API:er:
- Skapa ett [AAD-program](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Hämta en åtkomsttoken med det här programmet
- Använda token för att komma åt Defender för Endpoint API


Du kan komma åt Defender för Endpoint API med **programkontext** eller **användarkontext.**

- **Programkontext: (Rekommenderas)** <br>
    Används av appar som körs utan att en inloggad användare finns. Exempel: appar som körs som bakgrundstjänster eller som bakgrundstjänster.

    Steg som måste vidtas för att komma åt Defender för Endpoint API med programkontext:

  1. Skapa ett AAD-webbprogram.
  2. Tilldela önskat tillstånd till programmet, till exempel "Läsaviseringar", "Isolera maskiner". 
  3. Skapa en nyckel för det här programmet.
  4. Hämta token genom att använda programmet med dess nyckel.
  5. Använda token för att få åtkomst till Microsoft Defender för Endpoint API

     Mer information finns i Få [åtkomst med programmets kontext.](exposed-apis-create-app-webapp.md)


- **Användarkontext:** <br>
    Används för att utföra åtgärder i API:t för en användares räkning.

    Åtgärder att vidta för att komma åt Defender för Endpoint API med programkontext:

  1. Skapa det ursprungliga AAD-programmet.
  2. Tilldela önskat tillstånd till programmet, t.ex. "Läsaviseringar", "Isolera maskiner" osv. 
  3. Hämta token genom att använda programmet med användaruppgifter.
  4. Använda token för att få åtkomst till Microsoft Defender för Endpoint API

     Mer information finns i Få [åtkomst med användarkontext.](exposed-apis-create-app-nativeapp.md)


## <a name="related-topics"></a>Relaterade ämnen
- [Microsoft Defender för slutpunkts-API:er](exposed-apis-list.md)
- [Access Microsoft Defender för slutpunkt med programkontext](exposed-apis-create-app-webapp.md)
- [Använda Microsoft Defender för slutpunkt med användarkontext](exposed-apis-create-app-nativeapp.md)
