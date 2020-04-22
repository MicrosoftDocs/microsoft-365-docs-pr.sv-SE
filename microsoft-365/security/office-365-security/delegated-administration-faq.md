---
title: Vanliga frågor och svar om delegerad administration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: Det här avsnittet innehåller vanliga frågor och svar för Microsoft-partner och återförsäljare som vill utföra delegerade administrationsuppgifter, inklusive möjligheten att hantera Exchange Online Protection (EOP) för andra klienter (företag).
ms.openlocfilehash: b79c0aba026a8d59aac338ceac0f1c4a60d71c4d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637658"
---
# <a name="delegated-administration-faq"></a>Vanliga frågor och svar om delegerad administration

Det här avsnittet innehåller vanliga frågor och svar för Microsoft-partner och återförsäljare som vill utföra delegerade administrationsuppgifter, inklusive möjligheten att hantera Exchange Online Protection (EOP) för andra klienter (företag).

**F. Jag är återförsäljare och jag måste hantera mina kunders hyresgäster; Hur fungerar detta?**

A. Om du är en Microsoft-partner eller återförsäljare och har registrerat dig för att vara Microsoft-rådgivare kan du begära tillstånd att administrera deras klientorganisation i administrationscentret. Detta kallas delegerad administration och gör att du kan hantera deras Microsoft 365-klientorganisation (inklusive EOP-inställningar) som om du var administratör inom organisationen. Stegen för att utföra delegerad administration är följande:

1. Registrera dig för att bli microsoft [office 365 Advisor](https://aka.ms/cloudbenefits).

2. Registrera dig för delegerad administration. Innan du kan börja administrera en kunds konto måste de auktorisera dig som delegerad administratör. För att få deras godkännande skickar du dem först [ett erbjudande om delegerad administration](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e). (Du kan också erbjuda delegerad administration till kunden vid ett senare tillfälle.)

3. Skapa det delegerade administratörskontot med hjälp av stegen i [Lägg till, ändra eller ta bort en partner för prenumerationsrådgivare](https://docs.microsoft.com/office365/admin/misc/add-partner).

Besök [Partners: Skapa din företagsprenumeration och administrera partnerprenumerationen](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) för mer information om hur du konfigurerar delegerad administration.

**F. Jag är kund, inte återförsäljare, hur kan ställa in delegerad administratör för mina underhyresgäster?**

A. Delegerad administration är för närvarande endast tillgänglig för återförsäljare och partner. Vi har dock tillhandahållit ett exempel på Windows PowerShell-skript som hjälper dig att tillämpa principer på dina underhyresgäster (företag). Mer information finns i [Exempelskript för att tillämpa EOP-inställningar på flera klienter](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

**F. Kan jag hindra min administratör för underinnehavare från att ändra min princip?**

A. Microsoft 365 har för närvarande inte den här funktionen.

**F. Kan jag få konsoliderad rapportering över alla mina underhyresgäster?**

A. Konsoliderad rapportering för de företag du hanterar är inte tillgänglig för Microsoft 365 admincenterrapporter för tillfället. Du kan dock göra detta med hjälp av [Microsoft Graph](https://docs.microsoft.com/graph/overview).
