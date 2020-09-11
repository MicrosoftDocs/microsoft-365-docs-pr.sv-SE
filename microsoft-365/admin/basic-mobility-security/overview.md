---
title: Översikt över grundläggande mobilitet och säkerhet för Microsoft 365
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
description: Använd grundläggande mobilitet och säkerhet för att ange säkerhets principer och åtkomst regler för enheter.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430321"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Översikt över grundläggande mobilitet och säkerhet för Microsoft 365

Du kan hantera och skydda mobila enheter när de är anslutna till din Microsoft 365-organisation med grundläggande mobilitet och säkerhet. Mobila enheter som smartphones och surfplattor som används för att komma åt e-post, kalender, kontakter och dokument spelar en stor del för att se till att anställda får jobbet gjort när som helst. Så det är viktigt att du skyddar organisationens information när personer använder enheter. Du kan använda grundläggande mobilitet och säkerhet för att ange säkerhets principer och åtkomst regler för enheter och för att rensa mobila enheter om de är förlorade eller stulna.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Grundläggande mobilitet och säkerhets inställningar":::

## <a name="what-types-of-devices-can-you-manage"></a>Vilka typer av enheter kan du hantera?

Du kan använda grundläggande mobilitet och säkerhet för att hantera många typer av mobila enheter som Windows Phone, Android, iPhone och iPad. För att hantera mobila enheter som används av personer i organisationen måste varje person ha en giltig Microsoft 365-licens och deras enheter måste vara registrerade i grundläggande mobilitet och säkerhet.

Om du vill se vilken grundläggande mobilitet och säkerhet som stöds för varje typ av enhet kan du läsa mer i [grundläggande mobilitet och säkerhet](capabilities.md).

## <a name="setup-steps-for-basic-mobility-and-security"></a>Konfigurations steg för grundläggande mobilitet och säkerhet

En global administratör för Microsoft 365 måste utföra följande steg för att aktivera och konfigurera grundläggande mobilitet och säkerhet. Detaljerade anvisningar finns i [Konfigurera grundläggande mobilitet och säkerhet](set-up.md). 

Här är en sammanfattning av stegen:

**Steg 1:** Aktivera grundläggande mobilitet och säkerhets inställningar genom att följa stegen i [installera grundläggande mobilitet och säkerhet](set-up.md).

**Steg 2:** Konfigurera grundläggande mobilitet och säkerhet genom att till exempel skapa ett APN-certifikat för att hantera iOS-enheter och lägga till en DNS-post (Domain Name System) för din domän för att stödja Windows-telefoner.

**Steg 3:** Skapa enhets principer och Använd dem för grupper av användare. När du gör det får dina användare ett registrerings meddelande på sina enheter och när de har genomgått registrering begränsas deras enheter av de principer som du har angett för dem. Mer information finns i [Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device.md). 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundläggande principer för säkerhet och mobilitet":::

## <a name="device-management-tasks"></a>Enhets hanterings uppgifter

Efter att du har grundläggande mobilitet och säkerhets inställningar och användarna har registrerat sina enheter kan du hantera enheter, blockera åtkomst eller rensa en enhet om det behövs. Om du vill veta mer om några vanliga enhets hanterings uppgifter, till exempel var du ska utföra åtgärderna, läser du [Hantera enheter som är registrerade i hantering för mobila enheter för Microsoft 365](manage-enrolled-devices.md).

## <a name="other-ways-to-manage-devices-and-apps"></a>Andra sätt att hantera enheter och appar

Om du bara behöver hantering av mobil program (MAM), till exempel för personer som uppdaterar arbets projekt på sina egna enheter, ger Intune ett annat alternativ förutom att registrera och hantera enheter. Med en Intune-prenumeration kan du konfigurera MAM policys med Azure-portalen, även om personers enheter inte är registrerade i Intune. Mer information finns i [Översikt över program skydds principer](https://go.microsoft.com/fwlink/?LinkId=2132517).

## <a name="related-topics"></a>Relaterade ämnen

[Konfigurera grundläggande mobilitet och säkerhet](set-up.md)

[Registrera din mobila enhet med grundläggande mobilitet och säkerhet](enroll-your-mobile-device.md)

[Hantera enheter som är registrerade i hantering av mobila enheter för Microsoft 365](manage-enrolled-devices.md)

[Få information om enheter som hanteras av grundläggande mobilitet och säkerhet](get-details-about-managed-devices.md)