---
title: Principer för enhetsefterlevnad för microsoft 365 Enterprise-testmiljön
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
description: Använd den här testlabbet-guiden om du vill lägga till Intune-principer för enhetsefterlevnad i microsoft 365 Enterprise-testmiljön.
ms.openlocfilehash: 5ef39310ff74e5d5a38e8a5dd8c7ca24a126af58
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679032"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Principer för enhetsefterlevnad för microsoft 365 Enterprise-testmiljön

*Den här testlabbguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*

Med instruktionerna i den här artikeln lägger du till en Intune-enhetsefterlevnadsprincip för Windows 10-enheter och Microsoft 365 Apps för företag i microsoft 365 Enterprise-testmiljön.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise

Om du bara vill konfigurera MAM-principer på ett lätt väg med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera [MAM-principer](pass-through-auth-m365-ent-test-environment.md)i ett simulerat företag följer du instruktionerna i Direktautentisering .
  
> [!NOTE]
> Testning av automatiserad licensiering och gruppmedlemskap kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fas 2: Skapa en princip för enhetsefterlevnad för Windows 10-enheter

I den här fasen skapar du en enhetsefterlevnadsprincip för Windows 10-enheter.
  
1. Gå till Office 365-portalen på ( [https://portal.office.com](https://portal.office.com) ) och logga in på din Office 365 testlabbprenumeration med ditt globala administratörskonto.
    
2. Öppna Azure-portalen på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .

3. Skriv **Intune** i sökrutan på fliken Azure portal i webbläsaren och klicka sedan på **Intune**.
    
4. Om meddelandet **Du inte har aktiverat enhetshantering ännu i** Microsoft **Intune-fönstret** klickar du på den. Klicka på **Intune MDM Authority**i **fönstret Hantering av mobila enheter** och klicka sedan på **Välj**. Uppdatera webbläsarfliken.
    
5. Klicka på **Grupper**i det vänstra navigeringsfönstret .
    
6. Klicka på **+ Ny grupp**i fönstret **Grupper-allagrupper** .
    
7. I **gruppfönstret** väljer du Typ av **Office 365** eller **Säkerhet** för **grupp?**, skriver **du Hanterade Windows 10-enhetsanvändare** i **Namn**, väljer Tilldelad i **medlemstyp** och klickar sedan på **Skapa**. **Membership type** 
    
8. Klicka på **Microsoft Intune**. Klicka på **Skapa en efterlevnadsprincip**i **snabbdatalistan** i fönstret **Microsoft Intune.**
    
9. Klicka på Skapa princip i fönstret **Profil för efterlevnadsprincip.** **Create Policy**
    
10. Skriv **Windows 10**i **Namn**i fönstret **Skapa princip** . Välj Windows **10 och senare** **i** **fönstret Windows** **10 och** klicka sedan på **Skapa**. 
    
11. Klicka på **Efterlevnadsprincipprofiler**och sedan på principnamnet för **Windows 10.**
    
12. Klicka på **Tilldelningar**i fönstret **Windows 10** och klicka sedan på **Välj grupper som du vill inkludera**.
    
13. Klicka på gruppen Hanterade Windows **10-enhetsanvändare** i fönstret **Välj grupper som ska inkluderas** och klicka sedan på **Välj**.
    
14. Klicka på **Spara,** klicka på **Microsoft Intune-Översikt**och sedan på **Klientappar** i den vänstra navigeringen.
    
15. Klicka på **Appar**i fönstret **Klientappar** och klicka sedan på **Lägg till**. 

16. I fönstret **Lägg till app** väljer du **Apptyp**och väljer sedan **Windows 10** under **Office 365 Suite**.

17. Välj Information om **App Suite**i fönstret Lägg till **app** .
 
18. Skriv **Microsoft 365 Apps för företag** i både Suite **Name** och **Suite Description**i informationsfönstret i **App Suite.**
Klicka på OK.

19. I fönstret **Lägg till app** väljer du Konfigurera App **Suite**och klickar sedan på **OK**.

20. Välj **Inställningar för App Suite**i fönstret Lägg till **app.**

21. För **Uppdatera kanal**väljer du **Halvårsvis företag**och klickar sedan på **OK**.

22. Klicka på **Lägg till**i fönstret Lägg **till app** .

Du har nu en princip för enhetsefterlevnad för att testa de valda apparna i windows **10-enhetens** efterlevnadsprincip och för medlemmar i gruppen **Hanterade Windows 10-enhetsanvändare.** Observera att om du väljer Office 365 som grupptyp skapas ytterligare resurser. 
  
## <a name="next-step"></a>Nästa steg

Utforska ytterligare funktioner och funktioner för hantering av [mobila](m365-enterprise-test-lab-guides.md#mobile-device-management) enheter i testmiljön.

## <a name="see-also"></a>Se även

[Microsoft 365 Företagstestlabbguider](m365-enterprise-test-lab-guides.md).
  
[Registrera iOS- och Android-enheter i testmiljön för Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Företagsmobilitet + säkerhet (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
