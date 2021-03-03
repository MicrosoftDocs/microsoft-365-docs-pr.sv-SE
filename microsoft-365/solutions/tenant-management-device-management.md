---
title: 'Steg 5: Enhet- och apphantering för Microsoft 365 för företagsklienter'
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Distribuera rätt alternativ för enhet och programhantering för Microsoft 365-klientorganisationen.
ms.openlocfilehash: 96412cb52540e87341fa67e20382951db7becfbe
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406378"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a>Steg 5: Enhet- och apphantering för Microsoft 365 för företagsklienter

Microsoft 365 för företag innehåller funktioner för att hantera enheter och användning av appar på de enheterna i din organisation med hantering av mobila enheter (MDM) och hantering av mobila program (MAM). Du kan hantera iOS-, Android-, macOS- och Windows-enheter för att skydda åtkomsten till organisationens resurser, inklusive dina data. Du kan till exempel förhindra att e-postmeddelanden skickas till personer utanför organisationen eller isolera organisationsdata från personuppgifter på dina anställdas personliga enheter.

Här är ett exempel på validering och hantering av användare, deras enheter och användning av lokala appar och produktivitetsappar i molnet som Microsoft Teams.

![Validering och hantering av användare, enheter och appar](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

För att hjälpa dig att skydda organisationens resurser innehåller Microsoft 365 för företag funktioner som hjälper dig att hantera enheter och deras åtkomst till appar. Det finns två alternativ för enhetshantering:

- Microsoft Intune, som är en omfattande lösning för enhet- och apphantering för företag.
- Basic Mobility and Security, som är en delmängd av Intune-tjänsterna som ingår i alla Microsoft 365-produkter för att hantera enheter i organisationen. Mer information finns i [Funktionerna för grundläggande rörlighet och säkerhet.](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)

Om du har Microsoft 365 E3 eller E5 bör du använda Intune.

## <a name="microsoft-intune"></a>Microsoft Intune

Du använder [Microsoft Intune för](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) att hantera åtkomsten till din organisation med MDM eller MAM. MDM är när användare "registrerar" sina enheter i Intune. När en enhet har registrerats är det en hanterad enhet och kan ta emot organisationens principer, regler och inställningar. Du kan till exempel installera specifika appar, skapa en lösenordsprincip, installera en VPN-anslutning och mycket mer.

Användare med egna personliga enheter kanske inte vill registrera sina enheter eller hanteras av Intune och organisationens principer. Men du måste fortfarande skydda organisationens resurser och data. I det här scenariot kan du skydda dina program med mam. Du kan till exempel använda en MAM-princip som kräver att användaren anger en PIN-kod när han eller hon använder SharePoint på enheten.

Du får också bestämma hur du ska hantera personliga enheter och enheter som ägs av organisationen. Du kanske vill behandla enheter olika beroende på hur de används.

## <a name="identity-and-device-access-configurations"></a>Konfigurationer av identiteter och enhetsåtkomst

Microsoft tillhandahåller en uppsättning konfigurationer för identitet [och enhetsåtkomst för](../security/office-365-security/microsoft-365-policies-configurations.md) att säkerställa en säker och produktiv arbetsstyrka. De här konfigurationerna omfattar användning av:

- Principer för villkorsstyrd åtkomst i Azure AD
- Microsoft Intune-policyer för enhetsefterlevnad och appskydd
- Användarriskprinciper för Azure AD Identity Protection
- Ytterligare principer för molnappar

Här är ett exempel på hur de här inställningarna och principerna används för att verifiera och begränsa användare, deras enheter och användning av lokala appar och produktivitetsappar i molnet, till exempel Microsoft Teams.

![Konfigurationer av identitets- och enhetsåtkomst för krav och begränsningar för användare, deras enheter och deras användning av appar](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

För enhetsåtkomst och apphantering använder du konfigurationerna i följande artiklar:

- [Krav](../security/office-365-security/identity-access-prerequisites.md)
- [Vanliga principer för identitets- och enhetsåtkomst](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a>Resultat av steg 5

För enhet- och apphantering för Microsoft 365-klienten har du fastställt Intune-inställningarna och principerna för att verifiera och begränsa användare, deras enheter och deras användning av lokala appar och appar för moln produktivitet.

Här är ett exempel på en klientorganisation med Intune-enhet och apphantering med de nya elementen markerade.

![Exempel på en klientorganisation med Intune-enhet och apphantering](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

I den här bilden har klientorganisationen:

- Organisationsägda enheter som registrerats i Intune.
- Intune-enhet och appprinciper för registrerade och personliga enheter.

## <a name="ongoing-maintenance-for-device-and-app-management"></a>Löpande underhåll för enhet och apphantering

Du kan kontinuerligt behöva: 

- Hantera enhetsregistrering.
- Ändra inställningarna och principerna för ytterligare appar, enheter och säkerhetskrav.
