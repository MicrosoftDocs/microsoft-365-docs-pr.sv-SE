---
title: Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Använd den här test laboratorie guiden för att lägga till principer för efterlevnadsprinciper i din Microsoft 365 för företags test miljö.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487418"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

I den här artikeln beskrivs hur du lägger till en policy för principer för en Intune-enhet för Windows 10-enheter och Microsoft 365-appar för företag till din test miljö för Microsoft 365 för företag.

Du lägger till en policy för en Intune-enhet i två faser:
- [Fas 1: bygga ut test miljön för Microsoft 365 för företag](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: skapa en policy för enhetskompatibilitet för Windows 10-enheter](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet går du till [Microsoft 365 för Enterprise Test Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du vill konfigurera MAM-principer på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera MAM-principer i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fas 2: skapa en policy för enhetskompatibilitet för Windows 10-enheter

I den här fasen skapar du en princip för enhetskompatibilitet för Windows 10-enheter.
  
1. Gå till [administrations centret för microsoft 365](https://admin.microsoft.com) och logga in på ditt Microsoft 365 test laboratorie abonnemang med ditt globala administratörs konto.
1. Öppna Azure-portalen på på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .
1. I sökrutan för Azure-portalen anger du **Intune**och sedan **Intune**.
1. Om du ser ett meddelande om **att du inte har aktiverat enhets hantering ännu** i fönstret **Microsoft Intune** väljer du det. I fönstret **hantering av mobila enheter** väljer du **Intune MDM**och väljer sedan **Välj**.
1. Uppdatera din webbläsare.
1. I det vänstra navigerings fönstret väljer du **grupper**.
1. I fönstret **grupper – alla grupper** väljer du **+ ny grupp**.
1. I fönstret **grupp** väljer du **Microsoft 365** eller **säkerhet** för **grupptyp?**, anger **hanterade Windows 10-användare** i **namn**, Välj **tilldelat** i **medlemskaps typ**och välj sedan **skapa**.
1. Välj **Microsoft Intune**.
1. I listan **snabb uppgifter** i fönstret **Microsoft Intune** väljer du **skapa en policy för efterlevnad**.
1. I fönstret **policy profiler för efterlevnad** väljer du **Skapa princip**.
1. Ange **Windows 10**i **namn**i fönstret **Skapa princip** . I **Platform**väljer du **Windows 10 och senare**, väljer **OK** i fönstret **policyn för Windows 10-efterlevnad** och väljer sedan **skapa**.
1. Välj **profiler för efterlevnadsprinciper**och välj sedan **Windows 10** -princip namnet.
1. I fönstret **Windows 10** väljer du **uppgifter**och väljer sedan **Välj grupper som ska ingå**.
1. I fönstret **Välj grupper som ska inkluderas** väljer du gruppen **hanterade Windows 10-enheter** och väljer sedan **Välj**.
1. Välj **Spara**, Välj **Microsoft Intune-översikt**och välj sedan **klient program** i det vänstra navigerings fältet.
1. Välj **appar**i fönstret **klient program** och välj sedan **Lägg till**.
1. Välj **program typ**i fönstret **Lägg till app** och välj sedan **Windows 10** under **Microsoft 365 Suite**.
1. I fönstret **Lägg till app** väljer du **information för programpaket**.
1. I fönstret **Programsvits information** anger du **Microsoft 365-appar för företag** i både **Suite-namn** och **programbeskrivning**och väljer sedan **OK**.
1. I fönstret **Lägg till app** väljer du **Konfigurera programsvit**och sedan **OK**.
1. I fönstret **Lägg till app** väljer du **Inställningar för programpaket**.
1. För **Uppdatera kanal**, Välj **halvårs företag**och välj sedan **OK**.
1. I fönstret **Lägg till app** väljer du **Lägg till**.

Du har nu en policy för enhetskompatibilitet för att testa de valda programmen i policyn för **Windows 10** -enheter och för medlemmar i gruppen **användare av hanterade Windows 10-enheter** . Observera att om du väljer **Microsoft 365** skapas ytterligare resurser med grupp typen.
  
## <a name="next-step"></a>Nästa steg

Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.

## <a name="see-also"></a>Se även

[Microsoft 365 för företags test labb guider](m365-enterprise-test-lab-guides.md).
  
[Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
