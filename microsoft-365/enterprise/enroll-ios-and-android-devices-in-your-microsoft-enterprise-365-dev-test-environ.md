---
title: Registrera iOS-/iPadOS- och Android-enheter i din Microsoft 365 för företagstestmiljö
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
description: Använd den här testlabbguiden för att registrera enheter i Microsoft 365 testmiljö och hantera dem på distans.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367089"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrera iOS- och Android-enheter i din Microsoft 365 för företagstestmiljö

*Den här testlabbguiden kan endast användas Microsoft 365 för företagstestmiljöer.*

I den här artikeln beskrivs hur du registrerar och testar grundläggande funktioner för hantering av mobila enheter för iOS-/iPadOS- och Android-enheter i testmiljön för Microsoft 365 företag.

Registrering av iOS-/iPadOS- och Android-enheter i testmiljön omfattar tre faser:
- [Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Registrera dina iOS-/iPadOS- och Android-enheter](#phase-2-enroll-your-ios-and-android-devices)
- [Fas 3: Hantera dina iOS-/iPadOS- och Android-enheter via fjärrstyrning](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö

Om du vill registrera iOS-/iPadOS- och Android-enheter på ett lätt sätt med minimikraven följer du anvisningarna i [Lätt baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Om du vill registrera iOS/iPadOS och Android-enheter i ett simulerat företag följer du anvisningarna i [Direktautentisering.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Om du testar automatiserad licensiering och gruppmedlemskap krävs inte den simulerade företagstestmiljön, som omfattar en simulerad intranätansluten till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Här finns ett alternativ så att du kan testa automatisk licensiering och gruppmedlemskap, och du kan experimentera med det i en miljö som representerar en vanlig organisation.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fas 2: Registrera dina iOS- och Android-enheter

Om du överväger en MDM-lösning (Mobile Device Management) för att hantera dina enheter kan du använda Microsoft Intune. När du arbetar med en MDM-leverantör, inklusive Intune, registreras enheter. När de har registrerats får de de funktioner och inställningar som du konfigurerar. 

I Intune finns det några olika sätt att registrera dina iOS-/iPadOS- och Android-enheter. Du kan välja det registreringsalternativ som passar din organisation bäst. Mer information och vägledning finns i följande artiklar:

- [Distributionsguide: Registrera iOS- och iPadOS-enheter i Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Distributionsguide: Registrera Android-enheter i Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Om du är redo att använda Intune för enhetshantering och vill ha lite vägledning kan följande information vara till hjälp:

- [Översikt över enhetshantering](/mem/intune/fundamentals/what-is-device-management)
- [Självstudiekurs: Genomgång av Intune i Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Distributionsguide: Installera eller flytta till Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fas 3: Hantera iOS- och Android-enheter via fjärrstyrning

Microsoft Intune även fjärrlås och återställning av lösenord. Om någon förlorar sin enhet kan du fjärrlåsa enheten. Om någon glömmer sitt lösenord kan du fjärråterställninga det.

- Information om hur du fjärrlåser en iOS/iPadOS- eller Android-enhet finns i [Fjärrlåsa enheter med Intune.](/mem/intune/remote-actions/device-remote-lock)
- Om du vill fjärråterställning av lösenordet kan du [gå till Återställa eller ta bort en enhetskod i Intune.](/mem/intune/remote-actions/device-passcode-reset)

Information om ytterligare uppgifter som du kan köra på distans finns [i tillgängliga enhetsåtgärder.](/mem/intune/remote-actions/device-management#available-device-actions)
    
## <a name="next-step"></a>Nästa steg

Utforska ytterligare [funktioner för hantering av](m365-enterprise-test-lab-guides.md#mobile-device-management) mobila enheter och funktioner i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)
  
[Efterlevnadsprinciper för enheter för din Microsoft 365 för företagstestmiljö](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)
