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
ms.openlocfilehash: b4a95b2c7e58239c0a8d0d3b5045e7337f43de6b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686016"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Genom att följa anvisningarna i den här artikeln kan du registrera dig för och testa grundläggande funktioner för mobila enheter för iOS och Android-enheter i test miljön för Microsoft 365 för företag.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill registrera iOS-och Android-enheter på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill registrera iOS-och Android-enheter i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services). Det tillhandahålls här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fas 2: registrera dina iOS-och Android-enheter

Börja med att använda anvisningarna i [Installera och logga in på appen företags Portal](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) för att anpassa Microsoft Intune-företagsportalsappen för din test miljö.

Följ sedan anvisningarna i [Konfigurera åtkomst till dina företags resurser](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) för att registrera en iOS-enhet.

Använd sedan instruktionerna i [Registrera din Android-enhet i Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) för att registrera en Android-enhet.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fas 3: hantera dina iOS-och Android-enheter från andra datorer

Microsoft Intune innehåller funktioner för återställning av både fjärrlåsning och lösen ord. Om någon förlorar sin enhet kan du låsa den från en annan enhet. Om någon glömmer sitt lösen ord kan du återställa det från en annan dator.
  
Så här låser du en iOS-eller Android-enhet från fjärrdator:

1. Logga in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med autentiseringsuppgifterna för ditt globala administratörs konto.
2. På fliken Azure Portal i webbläsaren skriver du **Intune** i sökrutan och klickar sedan på **Intune**.
3. Klicka på **enheter > alla enheter**.
4. Klicka på en iOS-eller Android-enhet i listan med enheter och klicka sedan på **Remote lock** -åtgärden.

    
Så här återställer du lösen ordet från fjärrdator:

1. Om det behövs loggar du in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med autentiseringsuppgifterna för ditt globala administratörs konto.
2. På fliken Azure Portal i webbläsaren skriver du **Intune** i sökrutan och klickar sedan på **Intune**.
3. Klicka på **enheter > alla enheter**.
4. I listan med enheter som du hanterar klickar du på en iOS-eller Android-enhet och väljer **... Mer**. Välj sedan fjärråtgärd för att **ta bort en lösen ords** enhet.

Mer information finns i [tillgängliga enheter](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Nästa steg

Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)
  
[Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

