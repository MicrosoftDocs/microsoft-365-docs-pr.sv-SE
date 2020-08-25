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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan visa vanliga frågor och svar om delegerade administrations uppgifter i Microsoft 365 för Microsoft-partners och åter försäljare.
ms.openlocfilehash: 3efadc8793778bfabe10922e8e29044747d60ad0
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/24/2020
ms.locfileid: "46866701"
---
# <a name="delegated-administration-faq"></a>Vanliga frågor och svar om delegerad administration

Den här artikeln innehåller vanliga frågor och svar om delegerade administrations uppgifter i Microsoft 365 för Microsoft-partners och åter försäljare. Delegerad administration inkluderar möjligheten att hantera inställningar för Exchange Online Protection (EOP) för andra klient organisationer.

## <a name="im-a-reseller-and-i-need-to-manage-my-customer-tenants-how-does-this-work"></a>Jag är åter försäljare och måste hantera mina kund innehavare. Hur fungerar detta?

Om du är Microsoft-partner eller åter försäljare och har registrerat dig för att vara Microsoft Advisor kan du begära _delegerade administrativa_ funktioner i kundens Microsoft 365-organisation.

Delegerad administration gör att du kan hantera Microsoft 365 (inklusive EOP-inställningar) som om du vore administratör inom organisationen. Stegen för att konfigurera delegerad administration beskrivs i följande lista:

1. Registrera dig som [Microsoft Office 365-rådgivare](https://aka.ms/cloudbenefits).

2. Registrera dig för delegerad administration. Innan du kan börja administrera en kunds klient organisation måste de ge dig som administratör. För att få sitt godkännande, [Skicka först dem ett anbud för delegerad administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). Du kan även ge din kund en delegerad administration senare.

3. Skapa det delegerade administratörs kontot enligt anvisningarna i [lägga till, ändra eller ta bort en abonnemangs rådgivare](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).

Besök [partners: skapa en prenumeration på ditt företag och administrera partner](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) för mer information om hur du konfigurerar delegerad administration.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-subtenants"></a>Jag är kund och inte en åter försäljare. Hur kan du konfigurera den delegerade administratören för mina under klienter?

Delegerad administration är endast tillgänglig för åter försäljare och partners. Men det finns ett exempel på PowerShell-skript som hjälper dig att tillämpa principer på dina under klienter (företag). Mer information finns i [exempel skript för att tillämpa EOP-inställningar på flera klient organisationer](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-subtenant-admin-from-modifying-my-policy"></a>Kan jag förhindra att mina administratörer ändrar min princip?

Nej. Microsoft 365 har för närvarande inte den här funktionen.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-subtenants"></a>Kan jag få konsol IDE rad rapportering i alla mina under klienter?

Konsol IDE rad rapportering över de företag som du hanterar är inte tillgängliga i Microsoft 365 Admin Center-rapporter. Men du kan få rapporter med [Microsoft Graph](https://docs.microsoft.com/graph/overview).
