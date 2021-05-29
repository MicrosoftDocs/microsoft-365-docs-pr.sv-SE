---
title: Översikt över Grundläggande rörlighet och säkerhet för Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Använd Basic Mobility and Security för att ange säkerhetsprinciper och åtkomstregler för enheter.
ms.openlocfilehash: 37be420a4b9499da3d1290b8b6a898b9fcb09c5b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706316"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Översikt över Grundläggande rörlighet och säkerhet för Microsoft 365

Du kan hantera och skydda mobila enheter när de är anslutna till din Microsoft 365 organisation med hjälp av Basic Mobility and Security. Mobila enheter som smartphones och surfplattor som används för att komma åt arbets-e-post, kalender, kontakter och dokument spelar en stor roll för att säkerställa att anställda får jobbet gjort när som helst, var som helst. Därför är det viktigt att du hjälper till att skydda organisationens information när personer använder enheter. Du kan använda Grundläggande rörlighet och säkerhet för att ställa in säkerhetsprinciper och åtkomstregler för enheter, och för att rensa mobila enheter om de försvinner eller blir stulna.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Grundläggande rörlighets- och säkerhetskonfiguration":::

## <a name="what-types-of-devices-can-you-manage"></a>Vilka typer av enheter kan du hantera?

Du kan använda Basic Mobility and Security för att hantera många typer av mobila enheter som Windows Phone, Android, iPhone och iPad. För att hantera mobila enheter som används av personer i din organisation måste varje person ha en tillämplig Microsoft 365-licens och sin enhet måste vara registrerad i Basic Mobility and Security.

Information om vilka stöd för Basic Mobility och Security som stöds för varje typ av enhet [finns i Funktioner för grundläggande rörlighet och säkerhet.](capabilities.md)

## <a name="setup-steps-for-basic-mobility-and-security"></a>Konfigurationssteg för Basic Mobility and Security

En Microsoft 365 global administratör måste utföra följande steg för att aktivera och konfigurera grundläggande rörlighet och säkerhet. Detaljerade instruktioner finns i Konfigurera grundläggande [rörlighet och säkerhet.](set-up.md) 

Här följer en sammanfattning av stegen:

**Steg 1:** Aktivera grundläggande rörlighet och säkerhet genom att följa stegen i  [Konfigurera grundläggande rörlighet och säkerhet.](set-up.md)

**Steg 2:** Konfigurera Basic Mobility and Security genom att till exempel skapa ett APNs-certifikat för att hantera iOS-enheter och lägga till en DNS-post (Domain Name System) för din domän för att stödja Windows telefoner.

**Steg 3:** Skapa enhetsprinciper och använd dem på grupper av användare. När du gör det får användarna ett meddelande om registrering på sin enhet, och när registreringen är klar begränsas deras enheter av de principer du har angett för dem. Mer information finns i [Registrera din mobila enhet med grundläggande rörlighet och säkerhet.](enroll-your-mobile-device.md) 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Principinställningar för grundläggande säkerhet och rörlighet":::

## <a name="device-management-tasks"></a>Uppgifter för enhetshantering

När du har konfigurerat Basic Mobility and Security och dina användare har registrerat sina enheter kan du hantera enheterna, blockera åtkomst eller rensa en enhet om det behövs. Mer information om några vanliga uppgifter för enhetshantering, bland annat var du utför uppgifter, finns i Hantera enheter som är registrerade i Hantering av mobila enheter [för Microsoft 365](manage-enrolled-devices.md).

## <a name="other-ways-to-manage-devices-and-apps"></a>Andra sätt att hantera enheter och appar

Om du bara behöver hantering av mobilappar (MAM), kanske för personer som uppdaterar arbetsprojekt på sina egna enheter, tillhandahåller Intune ett annat alternativ än att registrera och hantera enheter. Med en Intune-prenumeration kan du konfigurera MAM-principer med hjälp av Azure-portalen, även om personers enheter inte är registrerade i Intune. Mer information finns i Översikt [över principer för programskydd](/mem/intune/apps/app-protection-policy).

## <a name="related-content"></a>Relaterat innehåll

[Konfigurera grundläggande rörlighet och säkerhet](set-up.md) (artikel)\
[Registrera din mobila enhet med hjälp av Basic Mobility and Security](enroll-your-mobile-device.md) (artikel)\
[Hantera enheter som registrerats i Hantering av mobila enheter för Microsoft 365](manage-enrolled-devices.md) (artikel)\
[Få information om enheter som hanteras av Basic Mobility and Security](get-details-about-managed-devices.md) (artikel)