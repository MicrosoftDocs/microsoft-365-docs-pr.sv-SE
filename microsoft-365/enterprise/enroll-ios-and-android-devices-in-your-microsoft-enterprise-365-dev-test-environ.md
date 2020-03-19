---
title: Registrera iOS- och Android-enheter i testmiljön för Microsoft 365 Enterprise
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
description: Använd den här testlabbet-guiden för att registrera enheter i microsoft 365-testmiljön och fjärrhantera dem.
ms.openlocfilehash: ae6ff9e704fc239638b5951a95ae23c45e85b7be
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807000"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Registrera iOS- och Android-enheter i testmiljön för Microsoft 365 Enterprise

*Den här testlabbet-guiden kan endast användas för Microsoft 365 Enterprise-testmiljöer.*

Genom att följa instruktionerna i den här artikeln kan du registrera och testa grundläggande funktioner för hantering av mobila enheter för iOS- och Android-enheter i microsoft 365 Enterprise-testmiljön.

![Testlabbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill ha en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide-stacken.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygg ut testmiljön för Microsoft 365 Enterprise

Om du bara vill registrera iOS- och Android-enheter på ett lätt sätt med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill registrera iOS- och [Android-enheter](pass-through-auth-m365-ent-test-environment.md)i ett simulerat företag följer du instruktionerna i Direktautentisering .
  
> [!NOTE]
> Testning av automatiserad licensiering och gruppmedlemskap kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fas 2: Registrera dina iOS- och Android-enheter

Använd först instruktionerna i [Installera och logga in på företagsportalappen](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) för att anpassa Microsoft Intune Company Portal-appen för din testmiljö.

Använd sedan instruktionerna i [Konfigurera åtkomst till företagets resurser](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) för att registrera en iOS-enhet.

Använd sedan instruktionerna i [Registrera din Android-enhet i Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) för att registrera en Android-enhet.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fas 3: Fjärrhantera dina iOS- och Android-enheter

Microsoft Intune tillhandahåller både fjärrlås och återställning av lösenkod. Om någon förlorar sin enhet kan du fjärrlåsa enheten. Om någon glömmer sin lösenkod kan du återställa den på distans.
  
Så här låser du en iOS- eller Android-enhet på distans:

1. Logga in på Azure-portalen med [https://portal.azure.com](https://portal.azure.com) autentiseringsuppgifterna för ditt globala administratörskonto.
2. Skriv **Intune** i sökrutan på fliken Azure portal i webbläsaren och klicka sedan på **Intune**.
3. Klicka på **Enheter > Alla enheter**.
4. Klicka på en iOS- eller Android-enhet i listan över enheter och klicka sedan på åtgärden **Fjärrlås.**

    
Så här återställer du lösenkoden på distans:

1. Om det behövs loggar du [https://portal.azure.com](https://portal.azure.com) in på Azure-portalen med autentiseringsuppgifterna för ditt globala administratörskonto.
2. Skriv **Intune** i sökrutan på fliken Azure portal i webbläsaren och klicka sedan på **Intune**.
3. Klicka på **Enheter > Alla enheter**.
4. Från listan över enheter du hanterar, klicka på en iOS eller Android-enhet, och välj **... Mer**. Välj sedan fjärråtgärden **Ta bort lösenkodsenhet.**

Ytterligare experiment finns i [Tillgängliga enhetsåtgärder](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Nästa steg

Utforska ytterligare funktioner och funktioner för hantering av [mobila](m365-enterprise-test-lab-guides.md#mobile-device-management) enheter i testmiljön.

## <a name="see-also"></a>Se även

[Testlaboratorikguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[Principer för enhetsefterlevnad för microsoft 365 Enterprise-testmiljön](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

