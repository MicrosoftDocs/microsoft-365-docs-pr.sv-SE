---
title: Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Använd den här test laboratorie guiden för att registrera enheter i test miljön för Microsoft 365 och fjärrhantera dem.
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487702"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

I den här artikeln beskrivs hur du registrerar och testar grundläggande funktioner för mobila enheter för iOS och Android-enheter i test miljön för Microsoft 365 för företag.

Att registrera iOS-och Android-enheter i test miljön omfattar tre faser:
- [Fas 1: bygga ut test miljön för Microsoft 365 för företag](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: registrera dina iOS-och Android-enheter](#phase-2-enroll-your-ios-and-android-devices)
- [Fas 3: hantera dina iOS-och Android-enheter från andra datorer](#phase-3-manage-your-ios-and-android-devices-remotely)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du vill registrera iOS-och Android-enheter på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill registrera iOS-och Android-enheter i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserade licensierings-och grupp medlemskap och du kan experimentera med det i en miljö som representerar en typisk organisation.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fas 2: registrera dina iOS-och Android-enheter

Börja med att använda anvisningarna i [Installera och logga in på appen företags Portal](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) för att anpassa Microsoft Intune-företagsportalsappen för din test miljö.

Följ sedan anvisningarna i [Konfigurera åtkomst till dina företags resurser](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) för att registrera en iOS-enhet.

Använd sedan instruktionerna i [Registrera din Android-enhet i Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) för att registrera en Android-enhet.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fas 3: hantera dina iOS-och Android-enheter från andra datorer

Microsoft Intune innehåller funktioner för återställning av både fjärrlåsning och lösen ord. Om någon förlorar sin enhet kan du fjärrans luta enheten. Om någon glömmer sitt lösen ord kan du återställa det.
  
Så här låser du upp en iOS-eller Android-enhet:

1. Logga in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med autentiseringsuppgifterna för ditt globala administratörs konto.
2. I Azure-portalen anger du **Intune** i sökrutan och väljer **Intune**.
3. Klicka på **enheter > alla enheter**.
4. I listan över enheter väljer du en iOS-eller Android-enhet och väljer sedan **fjärrlåsning** .
    
Så här återställer du lösen ordet från en annan dator:

1. Om det behövs loggar du in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med autentiseringsuppgifterna för ditt globala administratörs konto.
2. I Azure-portalen anger du **Intune** i sökrutan och väljer **Intune**.
3. Välj **enheter**till  >  **alla enheter**.
4. I listan över enheter som du hanterar väljer du en iOS-eller Android-enhet väljer du **... Mer**och välj sedan fjärråtgärd för att **ta bort en lösen ords** enhet.

Mer information finns i [tillgängliga enheter](https://docs.microsoft.com/intune/device-management#available-device-actions).
    
## <a name="next-step"></a>Nästa steg

Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)
  
[Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)
