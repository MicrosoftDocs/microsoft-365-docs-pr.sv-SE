---
title: Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Använd den här test laboratorie guiden för att lägga till principer för efterlevnadsprinciper i din Microsoft 365 för företags test miljö.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367101"
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

I den här fasen skapar du en princip för enhetskompatibilitet för Windows 10-enheter. I den här fasen används Microsoft Intune och [administrations centret för Microsoft slut punkts hanteraren](https://go.microsoft.com/fwlink/?linkid=2109431) för att lägga till en grupp och skapa en policy för efterlevnad.

1. Gå till [administrations centret för microsoft 365](https://admin.microsoft.com)och logga in på ditt Microsoft 365 test laboratorie abonnemang med ditt globala administratörs konto. Välj administrations centret för **slut punkts hanteraren** . [Administrations centret för slut punkts hanteraren](https://go.microsoft.com/fwlink/?linkid=2109431) öppnas.

    Om ett meddelande som liknar **dig inte har aktiverat enhets hantering ännu** visas väljer du INTUNE som MDM-auktoritet. Anvisningar för hur du gör finns i [Ange hanterings myndigheten för mobila enheter](/mem/intune/fundamentals/mdm-authority-set).

    Administrations centret för slut punkts hanteraren fokuserar på enhets hantering och program hantering. En guidad visning av detta administrations Center finns i [själv studie kursen: genom gången Intune i Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. I **grupper** lägger du till en ny **Microsoft 365** -eller **säkerhets** grupp med namnet **hanterade Windows 10-enheter** med en **tilldelad** medlems typ. I nästa steg ska du tilldela din policy för efterlevnad till den här gruppen. 

    Anvisningar för de olika stegen och information om **Microsoft 365** eller **säkerhets** grupper finns i [lägga till grupper för att ordna användare och enheter](/mem/intune/fundamentals/groups-add).

3. I **enheter** skapar du en policy för Windows 10-efterlevnad. Koppla den här principen till gruppen **hanterade användare av Windows 10-enhet** som du har skapat.

    I din policy kan du blockera enkla lösen ord, kräva en brand vägg, kräva att Microsoft Defender Antimalware-tjänsten körs och mycket mer. En policy för efterlevnad innehåller vanligt vis grund inställningarna eller minimum att varje enhet ska ha.

    Anvisningar för hur du konfigurerar olika inställningar för kompatibilitet finns i [använda efterlevnadsprinciper för att ange regler för enheter som du hanterar](/mem/intune/protect/device-compliance-get-started).

När du är klar har du en policy för enhetskompatibilitet för att testa medlemmar i gruppen **användare med hanterade Windows 10-enheter** .
  
## <a name="next-step"></a>Nästa steg

Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.

## <a name="see-also"></a>Se även

[Microsoft 365 för företags test labb guider](m365-enterprise-test-lab-guides.md).
  
[Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
