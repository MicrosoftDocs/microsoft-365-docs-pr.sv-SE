---
title: Översikt över MICROSOFT 365 Defender API:er
description: Läs mer om tillgängliga API:er i Microsoft 365 Defender
keywords: api, apis, översikt, incident, incidenter, hotsökning, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931008"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Översikt över API:er för Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Viss information gäller förhandsversioner av produkter som kan komma att ändras väsentligt innan de släpps till kommersiellt bruk. Microsoft ger inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Microsoft 365 Defender är uppbyggt på en plattform som är integrationsklar.

Använd Microsoft 365 Defender API:er för att automatisera arbetsflöden baserat på delade tabeller för incidenter och avancerad sökning.

- **[Kombinerad incidentkö](api-incident.md)** – Fokusera på vad som är viktigt genom att gruppera hela attackomfånget och alla påverkade tillgångar under incident-API:t.

- **[Produkter](api-advanced-hunting.md)** med flera hot på vift – använd säkerhetsteamets organisationskunskaper för att leta efter komprometterade tecken genom att skapa egna anpassade frågor för att gå igenom rådata som samlas in över flera skyddsprodukter.

Tillsammans med dessa Microsoft 365 Defender-specifika API:er visar var och en av våra andra säkerhetsprodukter ytterligare [API:er](api-articles.md) för att hjälpa dig att dra nytta av deras unika funktioner.

## <a name="learn-more"></a>Mer information

| **Förstå hur du kommer åt API:er** |
|-|
| [Läs mer om API-kvoter och -licensiering](api-terms.md) |
| [Få åtkomst till API:er för Microsoft 365 Defender](api-access.md) |
| **Skapa appar** |
| [Skapa appen Hej världen](api-hello-world.md) |
| [Skapa en app för att få åtkomst till Microsoft 365 Defender-API:er för en användares räkning](api-create-app-user-context.md) |
| [Skapa en app för att komma åt Microsoft 365 Defender utan en användare](api-create-app-web.md) |
| [Skapa en app med partneråtkomst för flera klientorganisationsklienter till API:er för Microsoft 365 Defender](api-partner-access.md) |
| **Felsöka och underhålla appar** |
| [Förstå API-felkoder](api-error-codes.md) |
| [Hantera hemligheter i dina appar med Azure-nyckelvalv](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementera OAuth 2.0-auktorisering för användar logga in](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
