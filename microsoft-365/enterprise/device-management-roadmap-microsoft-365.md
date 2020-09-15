---
title: Enhets hanterings översikt för Microsoft 365
keywords: Microsoft 365, Microsoft 365 för Enterprise, Microsoft 365-dokumentation, hantering av mobila enheter, Intune
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
description: Översikten för konfiguration av enhets hantering för Microsoft 365.
ms.openlocfilehash: bb19c38d5cf92cfc04ac83bc29573ea24c93ef30
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775177"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Enhets hanterings översikt för Microsoft 365

Microsoft 365 för Enterprise innehåller funktioner för att hantera enheter och deras appar i din organisation. Genom att hantera mobila enheter kan du skydda din organisations resurser.

Det finns två alternativ för enhets hantering:

- [Microsoft Intune](#microsoft-intune)
- [Grundläggande mobilitet och säkerhet](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Du kan använda Microsoft Intune för att hantera åtkomst till din organisation med hantering av mobila enheter och hantering av mobil program. Hantering av mobila enheter är när användarna "registrerar" sina enheter i Intune. När en enhet har registrerats är det en hanterad enhet; Därför kan det ta emot organisationens principer, regler och inställningar. Du kan till exempel installera specifika appar, skapa en lösen ords princip, installera en VPN-anslutning m.m.

Användare med egna personliga enheter kanske inte vill registrera sina enheter eller hanteras av Intune och organisationens principer. Men du måste ändå skydda organisationens resurser och data. I det här scenariot kan du skydda dina appar med hantering av mobil program. Du kan till exempel använda en hanterings princip för mobila program som kräver att en användare anger en PIN-kod när jag försöker använda Microsoft SharePoint på enheten.

Du bestämmer också hur du ska hantera personliga enheter och företagsägda enheter. Du kanske vill behandla enheter på olika sätt, beroende på hur de används.

Börja [här](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)om du vill hantera enheter med Intune.

## <a name="basic-mobility-and-security"></a>Grundläggande mobilitet och säkerhet

Den är inbyggd i Microsoft 365 och hjälper dig att skydda och hantera användares mobila enheter som iPhone, iPad, Android och Windows-telefoner. Du kan skapa och hantera säkerhets principer för enheter, rensa en enhet och se detaljerade enhets rapporter.

Börja [här](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)för att hantera enheter med grundläggande mobilitet och säkerhet.
 
## <a name="identity-and-device-access-recommendations"></a>Rekommendationer för identitets- och enhetsåtkomst

Microsoft tillhandahåller en uppsättning rekommendationer för [identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) för att säkerställa en säker och produktiv arbetsstyrka. Använd rekommendationer och inställningar i följande artiklar för att få åtkomst till enheter:

- [Krav](identity-access-prerequisites.md)
- [Vanliga principer för identitets- och enhetsåtkomst](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Hur contoso hanterade enhets hantering för Microsoft 365

Mer information om hur du kan hitta en fiktiv men representativ organisation för hantering av mobila enheter med Microsoft 365-molntjänster finns i [Hantera mobila enheter för Contoso](contoso-mdm.md).
