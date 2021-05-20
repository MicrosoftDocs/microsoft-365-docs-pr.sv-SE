---
title: Få åtkomst till Microsoft Defender för Endpoint API
ms.reviewer: ''
description: Lär dig hur du kan använda API:er för att automatisera arbetsflöden och innovera baserat på Microsoft Defender för slutpunktsfunktioner
keywords: apis, api, wdatp, open api, microsoft defender för endpoint api, microsoft defender atp, public api, stöds apis, varningar, enhet, användare, domän, ip, fil, avancerad jakt, fråga
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
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571835"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Få åtkomst till Microsoft Defender för Endpoint API 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Gäller för:** 
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vill du uppleva Microsoft Defender för Endpoint? [Registrera dig för en gratis provperiod.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



Defender for Endpoint exponerar mycket av sina data och åtgärder via en uppsättning programmatiska API:er. Dessa API:er gör att du kan automatisera arbetsflöden och förnya baserat på Defender för Endpoint-funktioner. API-åtkomsten kräver OAuth2.0-autentisering. Mer information finns i [OAuth 2.0 Auktoriseringskod Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Titta på den här videon för en snabb översikt över Defender for Endpoints API:er. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

I allmänhet måste du vidta följande steg för att använda API: erna:
- Skapa ett [AAD-program](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Hämta en åtkomsttoken med det här programmet
- Använda token för att komma åt Defender for Endpoint API


Du kan komma åt Defender för slutpunkts-API:et **med programkontext** eller **användarkontext**.

- **Programkontext: (rekommenderas)** <br>
    Används av appar som körs utan att en inloggad användare är närvarande. till exempel appar som körs som bakgrundstjänster eller demoner.

    Steg som måste vidtas för att komma åt Defender for Endpoint API med programkontext:

  1. Skapa ett AAD-webbprogram.
  2. Tilldela önskad behörighet till programmet, till exempel "Läs aviseringar", "Isolera datorer". 
  3. Skapa en nyckel för det här programmet.
  4. Hämta token med hjälp av programmet med nyckeln.
  5. Använda token för att komma åt MICROSOFT Defender för Endpoint API

     Mer information finns i [Få åtkomst med programkontext .](exposed-apis-create-app-webapp.md)


- **Användarkontext:** <br>
    Används för att utföra åtgärder i API:et för en användares räkning.

    Steg att vidta för att komma åt Defender for Endpoint API med programkontext:

  1. Skapa AAD Native-Application.
  2. Tilldela önskad behörighet till programmet, t.ex. "Läs varningar", "Isolera maskiner" etc. 
  3. Hämta token med hjälp av programmet med användarautentiseringsuppgifter.
  4. Använda token för att komma åt MICROSOFT Defender för Endpoint API

     Mer information finns i [Få åtkomst med användarkontext .](exposed-apis-create-app-nativeapp.md)


## <a name="related-topics"></a>Relaterade ämnen
- [Microsoft Defender för API:er för slutpunkter](exposed-apis-list.md)
- [Komma åt Microsoft Defender för slutpunkt med programkontext](exposed-apis-create-app-webapp.md)
- [Komma åt Microsoft Defender för slutpunkt med användarkontext](exposed-apis-create-app-nativeapp.md)
