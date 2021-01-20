---
title: 'Steg 5: Hantering av enheter och program för Microsoft 365 för företags klienter'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Distribuera rätt alternativ för enhets-och program hantering för Microsoft 365-klient organisationer.
ms.openlocfilehash: a581af3ec2ec192112656f1919e27f5b05a41cb1
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908713"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Steg 5: Hantering av enheter och program för Microsoft 365 för företags klienter

Microsoft 365 för Enterprise innehåller funktioner för att hantera enheter och användning av appar på dessa enheter inom din organisation med hantering av mobila enheter (MDM) och mobil program hantering (MAM). Du kan hantera iOS-, Android-, macOS-och Windows-enheter för att skydda åtkomsten till organisationens resurser, inklusive dina data. Du kan till exempel förhindra att e-postmeddelanden skickas till personer utanför organisationen eller att du isolerar organisations data från person uppgifter på din personliga persons enheter.

Här är ett exempel på validering och hantering av användare, deras enheter och användning av lokala och moln produktivitets program som Microsoft Teams.

![Validering och hantering av användare, enheter och appar](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

För att hjälpa dig att skydda och skydda organisationens resurser inkluderar Microsoft 365 för företag funktioner för att hantera enheter och deras åtkomst till program. Det finns två alternativ för enhets hantering:

- Microsoft Intune, som är en omfattande lösning för enhet och program hantering för företag.
- Grundläggande mobilitet och säkerhet, som är en delmängd Intune-tjänster som ingår i alla Microsoft 365-produkter för att hantera enheter i din organisation. Mer information finns i [grundläggande mobilitet och säkerhet](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).

Om du har Microsoft 365 E3 eller E5 bör du använda Intune.

## <a name="microsoft-intune"></a>Microsoft Intune

Du använder [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) för att hantera åtkomst till din organisation med MDM eller Mam. MDM är när användare "registrerar" sina enheter i Intune. När en enhet har registrerats är den en hanterad enhet och kan ta emot organisationens principer, regler och inställningar. Du kan till exempel installera specifika appar, skapa en lösen ords princip, installera en VPN-anslutning m.m.

Användare med egna personliga enheter kanske inte vill registrera sina enheter eller hanteras av Intune och organisationens principer. Men du måste ändå skydda organisationens resurser och data. I det här scenariot kan du skydda dina appar med MAM. Du kan till exempel använda en MAM policy som kräver att en användare anger en PIN-kod när jag öppnar SharePoint på enheten.

Du bestämmer också hur du ska hantera personliga enheter och företagsägda enheter. Du kanske vill behandla enheter på olika sätt, beroende på hur de används.

## <a name="identity-and-device-access-configurations"></a>Konfigurationer av identiteter och enhetsåtkomst

Microsoft tillhandahåller en uppsättning konfigurationer för [identitets-och enhets åtkomst](../security/office-365-security/microsoft-365-policies-configurations.md) för att säkerställa en säker och produktiv personal. Dessa konfigurationer inkluderar användning av:

- Principer för villkorsstyrd åtkomst i Azure AD
- Microsoft Intune-enhetsupptäckning och skydds principer för appar
- Användar risk principer för Azure AD Identity Protection
- Ytterligare principer för molnappar

Här är ett exempel på hur dessa inställningar och principer används för att verifiera och begränsa användare, deras enheter och deras användning av lokala och moln produktivitets program som Microsoft Teams.

![Konfigurationer för identitets-och enhets åtkomst för krav och begränsningar för användare, deras enheter och deras användning av appar](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

Använd konfigurationerna i följande artiklar för enhets åtkomst och program hantering:

- [Krav](../security/office-365-security/identity-access-prerequisites.md)
- [Vanliga principer för identitets- och enhetsåtkomst](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Resultat av steg 5

För hantering av enheter och program för din Microsoft 365-klient organisation har du fastställt Intune-inställningar och policyer för att verifiera och begränsa användare, deras enheter och deras användning av lokala och Cloud Productivity-appar.

Här är ett exempel på en klient organisation med Intune-enhet och program hantering med de nya objekten markerade.

![Exempel på en klient organisation med Intune-enhet och program hantering](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

I den här bilden har klient organisationen:

- Företagsägda enheter registrerade i Intune.
- Intune-enhet och program principer för registrerade och personliga enheter.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Pågående underhåll av enhets-och program hantering

Kontinuerligt måste du kanske: 

- Hantera enhets registrering.
- Omarbeta inställningar och policyer för ytterligare appar, enheter och säkerhets krav.
