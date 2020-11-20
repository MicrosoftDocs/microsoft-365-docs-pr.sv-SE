---
title: Registrera iOS/iPad och Android-enheter i test miljön för Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Använd den här test laboratorie guiden för att registrera enheter i test miljön för Microsoft 365 och fjärrhantera dem.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367089"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

I den här artikeln beskrivs hur du registrerar och testar grundläggande funktioner för hantering av mobila enheter för iOS/iPad och Android-enheter i test miljön för Microsoft 365 för företag.

Att registrera iOS/iPad och Android-enheter i test miljön omfattar tre faser:
- [Fas 1: bygga ut test miljön för Microsoft 365 för företag](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: registrera dina iOS/iPad-och Android-enheter](#phase-2-enroll-your-ios-and-android-devices)
- [Fas 3: hantera dina iOS/iPad-och Android-enheter från andra datorer](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du vill registrera iOS/iPad-och Android-enheter på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill registrera iOS/iPad och Android-enheter i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserade licensierings-och grupp medlemskap och du kan experimentera med det i en miljö som representerar en typisk organisation.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fas 2: registrera dina iOS-och Android-enheter

Om du funderar på att hantera dina enheter med hjälp av en lösning för en mobil enhet kan du använda Microsoft Intune. När du arbetar med en MDM-leverantör, inklusive Intune, är enheterna "registrerade". När de har registrerats får de de funktioner och inställningar som du konfigurerar. 

I Intune finns det ett par sätt att registrera iOS/iPad-och Android-enheter. Du kan välja vilket alternativ som passar bäst för din organisation. Mer information och vägledning finns i följande artiklar:

- [Distributions guide: registrera enheter för iOS och iPad i Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Distributions guide: registrera Android-enheter i Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Om du är redo att använda Intune för enhets hantering och vill ha lite vägledning kan följande information vara till hjälp:

- [Översikt över enhets hantering](/mem/intune/fundamentals/what-is-device-management)
- [Själv studie kurs: genom gång av Intune i Microsoft slut punkts hanteraren](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Distributions guide: Konfigurera eller gå till Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fas 3: hantera dina iOS-och Android-enheter från andra datorer

Microsoft Intune tillhandahåller funktionen för återställning av fjär lås och lösen ord. Om någon förlorar sin enhet kan du fjärrans luta enheten. Om någon glömmer sitt lösen ord kan du återställa det.

- Om du vill låsa upp en iOS/iPad-eller Android-enhet går du till [fjär lås enheter med Intune](/mem/intune/remote-actions/device-remote-lock).
- Information om hur du återställer lösen ordet från en dator finns i [återställa eller ta bort en enhets kod i Intune](/mem/intune/remote-actions/device-passcode-reset).

Mer information om hur du kör fjärr anslutningar finns i [tillgängliga enheter](/mem/intune/remote-actions/device-management#available-device-actions).
    
## <a name="next-step"></a>Nästa steg

Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)
  
[Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)
