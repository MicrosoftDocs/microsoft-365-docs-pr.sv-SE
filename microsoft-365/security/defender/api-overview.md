---
title: Översikt över Microsoft 365 Defender API:er
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
ms.openlocfilehash: 2ca601c3c68df9f9f1cc4fb90bcfbe907850ce91
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029735"
---
# <a name="overview-of-microsoft-365-defender-apis"></a>Översikt över Microsoft 365 Defender API:er

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> En del information gäller förinstallerad produkt som kan ha ändrats mycket innan den släpps kommersiellt. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på den information som anges här.

Microsoft 365 Defender är uppbyggt på en plattform som är integrationsklar.

Använd API:Microsoft 365 Defender för att automatisera arbetsflöden baserat på delade incidenter och avancerade tabeller för sökning.

- **[Kö för kombinerade incidenter](api-incident.md)** – Fokusera på vad som är viktigt genom att gruppera hela attackomfånget och alla påverkade tillgångar under incident-API:t.

- **[Skydd](api-advanced-hunting.md)** mot hot för flera produkter – Använd säkerhetsteamets organisationskunskaper till att leta efter komprometterade tecken på kompromisser genom att skapa egna anpassade frågor för att gå igenom rådata som samlas in över flera skyddsprodukter.

Använd [Streaming API för](../defender-endpoint/raw-data-export.md) att skicka händelser och aviseringar i realtid från instanser när de inträffar i en enda dataström.

Tillsammans med dessa Microsoft 365 Defender-specifika API:er visar var och en av våra andra säkerhetsprodukter ytterligare [API:er](api-articles.md) så att du kan använda deras unika funktioner.

> [!NOTE]
> Övergången till den enhetliga portalen bör inte påverka PowerBi-instrumentpanelerna baserade på Microsoft Defender för slutpunkts-API:er. Du kan fortsätta att arbeta med befintliga API:er oavsett den interaktiva portalövergången.

## <a name="learn-more"></a>Mer information

| **Förstå hur du får åtkomst till API:er** |
|-|
| [Läs mer om API-kvoter och licensiering](api-terms.md) |
| [Få åtkomst Microsoft 365 Defender API:er](api-access.md) |
| **Skapa appar** |
| [Skapa en Hello world-app](api-hello-world.md) |
| [Skapa ett program för att komma Microsoft 365 Defender API:er för en användares räkning](api-create-app-user-context.md) |
| [Skapa ett program för åtkomst Microsoft 365 Defender utan en användare](api-create-app-web.md) |
| [Skapa ett program med partner med flera klientorganisationens åtkomst Microsoft 365 Defender API:er](api-partner-access.md) |
| **Felsöka och underhålla dina appar** |
| [Förstå API-felkoder](api-error-codes.md) |
| [Hantera hemligheter i dina appar med Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementera OAuth 2.0-auktorisering för användar logga in](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |