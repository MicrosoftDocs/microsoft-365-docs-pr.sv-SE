---
title: Översikt över Microsoft 365 Defender-API:er
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 14553f3891fd81a672b62fa0575f6c253fbb0224
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068977"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Översikt över Microsoft 365 Defender-API:er

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Microsoft 365 Defender är byggt på en plattform som är integrationsklar.

Använd Microsoft 365 Defender-API:er för att automatisera arbetsflöden baserat på delade tabeller för incidenter och avancerad sökning.

- **[Kö för kombinerade incidenter](api-incident.md)** – Fokusera på vad som är viktigt genom att gruppera hela attackomfånget och alla påverkade tillgångar under incident-API:t.

- **[Skydd](api-advanced-hunting.md)** mot hot för flera produkter – Använd säkerhetsteamets organisationskunskaper till att leta efter komprometterade tecken på kompromisser genom att skapa egna anpassade frågor för att gå igenom rådata som samlas in över flera skyddsprodukter.

Tillsammans med dessa Microsoft 365 Defender-specifika API:er visar var och en av våra andra säkerhetsprodukter ytterligare [API:er](api-articles.md) så att du kan använda deras unika funktioner.

## <a name="learn-more"></a>Mer information

| **Förstå hur du får åtkomst till API:er** |
|-|
| [Läs mer om API-kvoter och licensiering](api-terms.md) |
| [Åtkomst till Microsoft 365 Defender-API:er](api-access.md) |
| **Skapa appar** |
| [Skapa en Hello world-app](api-hello-world.md) |
| [Skapa en app för åtkomst till Microsoft 365 Defender-API:er för en användares räkning](api-create-app-user-context.md) |
| [Skapa en app för att komma åt Microsoft 365 Defender utan en användare](api-create-app-web.md) |
| [Skapa en app med partner med flera klientorganisationens åtkomst till Microsoft 365 Defender-API:er](api-partner-access.md) |
| **Felsöka och underhålla dina appar** |
| [Förstå API-felkoder](api-error-codes.md) |
| [Hantera hemligheter i dina appar med Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementera OAuth 2.0-auktorisering för användar logga in](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |