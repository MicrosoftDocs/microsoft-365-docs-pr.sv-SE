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
description: Det här avsnittet innehåller vanliga frågor och svar om Microsoft-partners och åter försäljare som vill utföra delegerade Microsoft 365-administrations uppgifter.
ms.openlocfilehash: 01781437bbc7e8fe5c035ea23e4392e734e0231f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827093"
---
# <a name="delegated-administration-faq"></a>Vanliga frågor och svar om delegerad administration

Det här avsnittet innehåller vanliga frågor och svar om Microsoft-partners och åter försäljare som vill utföra delegerade administrativa uppgifter, inklusive möjligheten att hantera Exchange Online Protection (EOP) för andra klient organisationer.

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>Jag är åter försäljare och måste hantera min kunds innehavare; Hur fungerar detta?

Om du är Microsoft-partner eller åter försäljare och har registrerat dig för att vara Microsoft Advisor kan du begära tillstånd att administrera klient organisationen i administrations centret. Detta kallas delegerad administration och gör att du kan hantera sin Microsoft 365-klient organisation (inklusive EOP-inställningar) som om du vore administratör inom organisationen. Så här gör du för att utföra delegerad administration:

1. Registrera dig som [Microsoft Office 365-rådgivare](https://aka.ms/cloudbenefits).

2. Registrera dig för delegerad administration. Innan du kan börja administrera en kunds konto måste de ge dig administratörs behörighet. För att få sitt godkännande, [Skicka först dem ett anbud för delegerad administration](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). (Du kan även ge din kund delegerad administration vid ett senare tillfälle.)

3. Skapa det delegerade administratörs kontot enligt anvisningarna i [lägga till, ändra eller ta bort en abonnemangs rådgivare](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).

Besök [partners: skapa en prenumeration på ditt företag och administrera partner](https://support.microsoft.com/office/30dd1681-47e0-4cbc-abfe-a222cd111319) för mer information om hur du konfigurerar delegerad administration.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>Jag är kund och inte en åter försäljare, hur kan konfigurera den delegerade administratören för mina under klienter?

Delegerad administration är bara tillgänglig för åter försäljare och partner för närvarande. Vi har ett exempel på ett Windows PowerShell-skript som hjälper dig att tillämpa principer på dina under klienter (företag). Mer information finns i [exempel skript för att tillämpa EOP-inställningar på flera klient organisationer](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>Kan jag förhindra att min princip ändras med administratör för under administratören?

Microsoft 365 har för närvarande inte den här funktionen.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>Kan jag få konsol IDE rad rapportering i alla mina under klienter?

Konsol IDE rad rapportering över de företag som du hanterar är inte tillgängligt för Microsoft 365 Admin Center-rapporter just nu. Det kan du göra genom att använda [Microsoft Graph](https://docs.microsoft.com/graph/overview).
