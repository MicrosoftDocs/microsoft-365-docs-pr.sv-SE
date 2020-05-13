---
title: Vanliga frågor och svar om delegerad administration
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Det här avsnittet innehåller vanliga frågor och svar för Microsoft-partner och återförsäljare som vill utföra delegerade Microsoft 365-administrationsuppgifter.
ms.openlocfilehash: d1522973292b290fd9f66f534ca23aeaa55ee756
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209529"
---
# <a name="delegated-administration-faq"></a>Vanliga frågor och svar om delegerad administration

Det här avsnittet innehåller vanliga frågor och svar för Microsoft-partner och återförsäljare som vill utföra delegerade administrationsuppgifter, inklusive möjligheten att hantera Exchange Online Protection (EOP) för andra klienter (företag).

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>Jag är återförsäljare och jag måste hantera mina kunders hyresgäster; Hur fungerar detta?

Om du är en Microsoft-partner eller återförsäljare och har registrerat dig för att vara Microsoft-rådgivare kan du begära tillstånd att administrera deras klientorganisation i administrationscentret. Detta kallas delegerad administration och gör att du kan hantera deras Microsoft 365-klientorganisation (inklusive EOP-inställningar) som om du var administratör inom organisationen. Stegen för att utföra delegerad administration är följande:

1. Registrera dig för att bli microsoft [office 365 Advisor](https://aka.ms/cloudbenefits).

2. Registrera dig för delegerad administration. Innan du kan börja administrera en kunds konto måste de auktorisera dig som delegerad administratör. För att få deras godkännande skickar du dem först [ett erbjudande om delegerad administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). (Du kan också erbjuda delegerad administration till kunden vid ett senare tillfälle.)

3. Skapa det delegerade administratörskontot med hjälp av stegen i [Lägg till, ändra eller ta bort en partner för prenumerationsrådgivare](https://docs.microsoft.com/office365/admin/misc/add-partner).

Besök [Partners: Skapa din företagsprenumeration och administrera partnerprenumerationen](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) för mer information om hur du konfigurerar delegerad administration.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>Jag är kund, inte återförsäljare, hur kan konfigurera delegerad administratör för mina underhyresgäster?

Delegerad administration är för närvarande endast tillgänglig för återförsäljare och partner. Vi har dock tillhandahållit ett exempel på Windows PowerShell-skript som hjälper dig att tillämpa principer på dina underhyresgäster (företag). Mer information finns i [Exempelskript för att tillämpa EOP-inställningar på flera klienter](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>Kan jag hindra min administratör för underinnehavare från att ändra min princip?

Microsoft 365 har för närvarande inte den här funktionen.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>Kan jag få konsoliderad rapportering över alla mina underhyresgäster?

Konsoliderad rapportering för de företag du hanterar är inte tillgänglig för Microsoft 365 admincenterrapporter för tillfället. Du kan dock göra detta med hjälp av [Microsoft Graph](https://docs.microsoft.com/graph/overview).
