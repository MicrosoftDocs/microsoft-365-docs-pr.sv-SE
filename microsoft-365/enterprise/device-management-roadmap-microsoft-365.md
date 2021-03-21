---
title: Översikt över enhetshantering för Microsoft 365
keywords: Microsoft 365, Microsoft 365 för företag, Microsoft 365-dokumentation, hantering av mobila enheter, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: Översikt över att konfigurera enhetshantering för Microsoft 365.
ms.openlocfilehash: 4c37033898865372fea19ddbb53ec9c8586f27b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918972"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Översikt över enhetshantering för Microsoft 365

Microsoft 365 för företag innehåller funktioner som hjälper dig att hantera enheter och deras appar inom organisationen. Hantering av mobila enheter hjälper dig att skydda organisationens resurser.

Det finns två alternativ för enhetshantering:

- [Microsoft Intune](#microsoft-intune)
- [Grundläggande Mobility and Security](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Du kan använda Microsoft Intune för att hantera åtkomsten till din organisation med hantering av mobila enheter eller hantering av mobilprogram. Hantering av mobila enheter är när användarna "registrerar" sina enheter i Intune. När en enhet har registrerats är det en hanterad enhet. Det innebär att organisationens principer, regler och inställningar kan visas. Du kan till exempel installera specifika appar, skapa en lösenordsprincip, installera en VPN-anslutning med mera.

Användare med sina egna personliga enheter kanske inte vill registrera sina enheter eller hanteras av Intune och organisationens principer. Men du måste fortfarande skydda organisationens resurser och data. I det här scenariot kan du skydda dina appar med hantering av mobilprogram. Du kan till exempel använda en princip för hantering av mobilprogram som kräver att användaren anger en PIN-kod när han eller hon öppnar SharePoint Online på enheten.

Du får också bestämma hur du ska hantera personliga enheter och organisationsägda enheter. Du kanske vill behandla enheter olika beroende på hur de används.

## <a name="basic-mobility-and-security"></a>Grundläggande Mobility and Security

Det här är inbyggt i Microsoft 365 och hjälper dig att skydda och hantera dina användares mobila enheter, till exempel iPhone, iPad, Android och Windows-telefoner. Du kan skapa och hantera säkerhetsprinciper för enheter, fjärradea enheter och visa detaljerade enhetsrapporter.

## <a name="choose-between-the-two-options"></a>Välja mellan de två alternativen

Mer information om vilka alternativ för enhetshantering som passar bäst för dig finns i [Välja mellan Basic Mobility Security och Intune.](/office365/securitycompliance/choose-between-mdm-and-intune)

Baserat på din utvärdering kan du komma igång med att hantera dina enheter med:

- [Intune](/mem/intune/fundamentals/planning-guide)
- [Grundläggande Mobility and Security](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>Rekommendationer för identitets- och enhetsåtkomst

Microsoft tillhandahåller en uppsättning rekommendationer för [identitets- och enhetsåtkomst](../security/office-365-security/microsoft-365-policies-configurations.md) för att säkerställa en säker och produktiv arbetsstyrka. För enhetsåtkomst använder du rekommendationer och inställningar i följande artiklar:

- [Krav](../security/office-365-security/identity-access-prerequisites.md)
- [Vanliga principer för identitets- och enhetsåtkomst](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Hur Contoso hanterade enheter för Microsoft 365

Mer information om hur en fiktiv men representativt multinationellt företag distribuerade sin infrastruktur för hantering av mobila enheter med Microsoft 365-molntjänster finns i [Mobile device management för Contoso.](contoso-mdm.md)