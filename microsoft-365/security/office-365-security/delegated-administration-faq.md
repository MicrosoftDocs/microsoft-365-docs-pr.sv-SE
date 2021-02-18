---
title: Vanliga frågor och svar om delegerad administration
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan visa vanliga frågor och svar om uppgifter med delegerad administration i Microsoft 365 för Microsoft-partner och återförsäljare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 971572f8bff80da6dd63bed8958112332292feb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288365"
---
# <a name="delegated-administration-faq"></a>Vanliga frågor och svar om delegerad administration

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Den här artikeln innehåller vanliga frågor och svar om uppgifter med delegerad administration i Microsoft 365 för Microsoft-partner och återförsäljare. Delegerad administration omfattar möjligheten att hantera Exchange Online Protection-inställningar (EOP) för andra klientorganisationar (företag).

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Jag är återförsäljare och behöver hantera mina kundklienter. Hur fungerar det?

Om du är Microsoft-partner eller återförsäljare och har registrerat dig som Microsoft-rådgivare kan du begära delegerad _administration_ i kundens Microsoft 365-organisation.

Med delegerad administration kan du hantera Microsoft 365 (inklusive EOP-inställningar) som om du var administratör i den organisationen. Stegen för att konfigurera delegerad administration beskrivs i följande lista:

1. Registrera dig för att bli [Microsoft Office 365-rådgivare.](https://aka.ms/cloudbenefits)

2. Registrera dig för delegerad administration. Innan du kan börja administrera en kunds klientorganisation måste de godkänna dig som delegerad administratör. Om du vill få deras godkännande skickar du [först ett erbjudande om delegerad administration till dem.](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e) Du kan också erbjuda kunden delegerad administration vid ett senare tillfälle.

3. Skapa ett delegerat administratörskonto med hjälp av stegen i [Lägga till, ändra eller ta bort en partner till prenumerationsrådgivaren.](../../admin/misc/add-partner.md)

Besök [partners: Bygg upp din verksamhet och administrera partnerprenumerationen](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) för mer information om hur du tecknar delegerad administration.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Jag är kund, inte återförsäljare. Hur kan jag konfigurera delegerade administratörer för mina undergrupp?

Delegerad administration är endast tillgänglig för återförsäljare och partner. Det finns dock ett PowerShell-exempelskript som hjälper dig att tillämpa principer på underetr (företag). Mer information finns i [Exempelskript för tillämpning av EOP-inställningar på flera klientorganisationar.](sample-script-for-applying-eop-settings-to-multiple-tenants.md)

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>Kan jag hindra en underadministratör från att ändra min princip?

Nej. Microsoft 365 har för närvarande inte den här funktionen.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>Kan jag få konsoliderad rapportering för alla mina subtenanter?

Konsoliderad rapportering i de företag du hanterar är inte tillgänglig i rapporter i administrationscentret för Microsoft 365. Däremot kan du få rapporter genom att använda [Microsoft Graph.](https://docs.microsoft.com/graph/overview)
