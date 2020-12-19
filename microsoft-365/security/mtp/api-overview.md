---
title: 'Översikt över Microsoft 365 Defender API: er'
description: 'Läs mer om tillgängliga API: er i Microsoft 365 Defender'
keywords: 'API, API: er, översikt, tillbud, tillbud, hot om, Microsoft 365 Defender'
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719196"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Översikt över Microsoft 365 Defender API: er

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

Microsoft 365 Defender är baserat på en integrations klar plattform.

Använd Microsoft 365 Defender API: er till att automatisera arbets flöden baserat på tabellerna delade incidenter och avancerade jakt.

- Sammanslagen **[händelse i kö](api-incident.md)** -fokusera på vad som är kritiskt genom att gruppera hela attack omfattningen och alla aktiva till gångar tillsammans under API: t.

- Stöldskydd **[mellan produkter](api-advanced-hunting.md)** – Använd din säkerhets grupps organisatoriska vetskap för att hitta inloggnings problem, genom att skapa egna anpassade frågor för att ändra rå data som samlats in över flera olika skydds produkter.

Tillsammans med dessa Microsoft 365 Defender-specifika API: er kan de andra säkerhets produkterna Visa [ytterligare API: er](api-articles.md) som hjälper dig att utnyttja deras unika funktioner.

## <a name="learn-more"></a>Mer information

| **Förstå hur du kommer åt API: erna** |
|-|
| [Läs mer om API-kvoter och licensiering](api-terms.md) |
| [Gå till API för Microsoft 365 Defender](api-access.md) |
| **Skapa appar** |
| [Skapa en ' Hej världen '-App](api-hello-world.md) |
| [Skapa en app för att få åtkomst till Microsoft 365 Defender API: er för en användares räkning](api-create-app-user-context.md) |
| [Skapa en app för åtkomst till Microsoft 365 Defender utan en användare](api-create-app-web.md) |
| [Skapa en app med åtkomst för flera innehavare partner till Microsoft 365 Defender API: er](api-partner-access.md) |
| **Felsöka och underhålla dina appar** |
| [Förstå API-felkoder](api-error-codes.md) |
| [Hantera hemligheter i dina appar med Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [Implementera OAuth 2,0-auktorisering för användarens inloggning](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
