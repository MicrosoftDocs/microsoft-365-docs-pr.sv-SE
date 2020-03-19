---
title: Vanliga frågor om delegerad administration
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
description: Det här avsnittet innehåller vanliga frågor och svar för Microsoft-partner och återförsäljare som vill utföra delegerade Office 365-administrationsuppgifter, inklusive möjligheten att hantera Exchange Online Protection (EOP) för andra klienter (företag).
ms.openlocfilehash: 2a237da685ae3c3d81c5a0912e15b5e7370e2118
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807129"
---
# <a name="delegated-administration-faq"></a>Vanliga frågor om delegerad administration

Det här avsnittet innehåller vanliga frågor och svar för Microsoft-partner och återförsäljare som vill utföra delegerade Office 365-administrationsuppgifter, inklusive möjligheten att hantera Exchange Online Protection (EOP) för andra klienter (företag).

**F. Jag är återförsäljare och jag måste hantera min kunds hyresgäster; Hur fungerar detta?**

A. Om du är Microsoft-partner eller återförsäljare och har registrerat dig för att bli Microsoft-rådgivare kan du begära tillstånd att administrera sin klient organisation i administrationscentret. Detta kallas delegerad administration och det gör att du kan hantera deras Office 365-klient (inklusive EOP-inställningar) som om du var administratör inom organisationen. Stegen för att utföra delegerad administration är följande:

1. Registrera dig för att bli Microsoft [Office 365 Advisor](https://aka.ms/cloudbenefits).

2. Registrera dig för Office 365-delegerad administration. Innan du kan börja administrera en kunds konto måste de auktorisera dig som delegerad administratör. För att få deras godkännande skickar du [först ett erbjudande till delegerad administration](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e)för dem. (Du kan också erbjuda delegerad administration till kunden vid ett senare tillfälle.)

3. Skapa det delegerade administratörskontot med hjälp av stegen i [Lägg till, ändra eller ta bort en prenumerationsrådgivarepartner](https://docs.microsoft.com/office365/admin/misc/add-partner).

Besök [partner: Bygg ditt företag och administrera din Office 365-partnerprenumeration](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) för mer information om hur du konfigurerar Office 365-delegerad administration.

**F. Jag är kund, inte återförsäljare, hur kan ställa in delegerad administratör för mina underklienter?**

A. Delegerad administration är endast tillgänglig för återförsäljare och partners just nu. Vi har dock angett ett exempel på Windows PowerShell-skript som hjälper dig att tillämpa principer på dina underklienter (företag). Mer information finns i [Exempelskript för att tillämpa EOP-inställningar på flera klienter](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

**F. Kan jag hindra min underklientadministratör från att ändra min princip?**

A. Office 365 har för närvarande inte den här funktionen.

**F. Kan jag få konsoliderad rapportering över alla mina underklienter?**

A. Konsoliderad rapportering i alla företag som du hanterar är inte tillgänglig för Microsoft 365-administratörscenterrapporterna just nu. Du kan dock göra detta med hjälp av [Microsoft Graph](https://docs.microsoft.com/graph/overview).
