---
title: Efterlevnadsprinciper för enheter för din Microsoft 365 för företagstestmiljö
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
description: Använd den här testlabbguiden för att lägga till Intune-efterlevnadsprinciper för enheter i Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367101"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Efterlevnadsprinciper för enheter för din Microsoft 365 för företagstestmiljö

*Den här testlabbguiden kan endast användas Microsoft 365 för företagstestmiljöer.*

I den här artikeln beskrivs hur du lägger till en intune enhetsefterlevnadsprincip för Windows 10 enheter och Microsoft 365-appar för företag i din Microsoft 365 för företagstestmiljö.

När du lägger till en Intune-enhetsefterlevnadsprincip ingår två faser:
- [Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Skapa en policy för enhetsefterlevnad för Windows 10 enheter](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö

Om du bara vill konfigurera MAM-principer på ett lätt sätt med minimikraven följer du anvisningarna i Enkel [baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Om du vill konfigurera MAM-principer i ett simulerat företag följer du anvisningarna i [Direktautentisering.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Om du testar automatiserad licensiering och gruppmedlemskap krävs inte den simulerade företagstestmiljön, som omfattar en simulerad intranätansluten till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Här finns ett alternativ så att du kan testa automatisk licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en vanlig organisation.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fas 2: Skapa en policy för enhetsefterlevnad för Windows 10 enheter

I den här fasen skapar du en policy för enhetsefterlevnad för Windows 10 enheter. Den här fasen använder Microsoft Intune och [Microsoft Endpoint Manager för att](https://go.microsoft.com/fwlink/?linkid=2109431) lägga till en grupp och skapa en efterlevnadsprincip.

1. Gå till [Microsoft 365 och logga](https://admin.microsoft.com)in på din prenumeration Microsoft 365 testlabb med ditt globala administratörskonto. Välj **Endpoint Manager** administrationscenter. Administrationscentret [Endpoint Manager öppnas.](https://go.microsoft.com/fwlink/?linkid=2109431)

    Om du ser ett meddelande **som liknar Du har inte** aktiverat enhetshantering än väljer du Intune som MDM-instans. Specifika steg finns i Ange [utfärdare för hantering av mobila enheter.](/mem/intune/fundamentals/mdm-authority-set)

    Fokus Endpoint Manager på enhetshantering och apphantering. En genomgång av det här administrationscentret finns i [Självstudiekurs: Genomgång av Intune i Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. I **Grupper lägger** du till en **Microsoft 365** **säkerhetsgrupp** eller säkerhetsgrupp med namnet Managed Windows 10 **device users**, med en **tilldelad** medlemskapstyp. I nästa steg ska du tilldela den här gruppen din efterlevnadsprincip. 

    För specifika steg, och för information om hur du **Microsoft 365** **säkerhetsgrupper,** se Lägga [till grupper för att ordna användare och enheter.](/mem/intune/fundamentals/groups-add)

3. Skapa **en** princip för Windows 10 i Enheter. Tilldela den här principen till gruppen **hanterade Windows 10 enhet som du** har skapat.

    I principen kan du blockera enkla lösenord, kräva en brandvägg, kräva att Microsoft Defender-tjänsten mot skadlig programvara körs och mycket mer. En efterlevnadsprincip omfattar vanligtvis basinställningarna eller en miniminivå som varje enhet ska ha.

    Mer information om tillgängliga efterlevnadsinställningar som du kan konfigurera finns i Använda efterlevnadsprinciper för att ange regler för [enheter som du hanterar.](/mem/intune/protect/device-compliance-get-started)

När du är klar har du en princip för enhetsefterlevnad för att testa medlemmar i **gruppen Hanterade Windows 10 och enhetsanvändare.**
  
## <a name="next-step"></a>Nästa steg

Utforska ytterligare [funktioner för hantering av](m365-enterprise-test-lab-guides.md#mobile-device-management) mobila enheter och funktioner i testmiljön.

## <a name="see-also"></a>Se även

[Microsoft 365 för testlabbguider för företag.](m365-enterprise-test-lab-guides.md)
  
[Registrera iOS- och Android-enheter i din Microsoft 365 för företagstestmiljö](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
