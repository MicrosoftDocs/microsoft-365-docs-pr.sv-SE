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
ms.openlocfilehash: 3c77a7ea8ddc5120a2ce53fa0834dab213502657
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686760"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Principer för enhetskompatibilitet för test miljön av Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Med instruktionerna i den här artikeln kan du lägga till en policy för principer för en Intune-enhet för Windows 10-enheter och Microsoft 365-appar för företag till din test miljö för Microsoft 365 för företag.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill konfigurera MAM-principer på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera MAM-principer i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> För testning av automatiserade licensierings-och grupp medlemskap krävs inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet och Directory-synkronisering för en AD DS-skog (Active Directory Domain Services). Det tillhandahålls här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fas 2: skapa en policy för enhetskompatibilitet för Windows 10-enheter

I den här fasen skapar du en princip för enhetskompatibilitet för Windows 10-enheter.
  
1. Gå till [administrations centret för microsoft 365](https://admin.microsoft.com) och logga in på ditt Microsoft 365 test laboratorie abonnemang med ditt globala administratörs konto.
    
2. Öppna Azure-portalen på på en ny flik i webbläsaren [https://portal.azure.com](https://portal.azure.com) .

3. På fliken Azure Portal i webbläsaren skriver du **Intune** i sökrutan och klickar sedan på **Intune**.
    
4. Om du ser ett meddelande om **att du inte har aktiverat enhets hantering** i **Microsoft Intune** -fönstret klickar du på det. Klicka på **INTUNE MDM-auktoritet**i fönstret **hantering av mobila enheter** och klicka sedan på **Välj**. Uppdatera din webbläsare.
    
5. Klicka på **grupper**i det vänstra navigerings fönstret.
    
6. I fönstret **grupper – alla grupper** klickar du på **+ ny grupp**.
    
7. I fönstret **grupp** väljer du **Microsoft 365** eller **säkerhet** för **grupptyp?**, Skriv **hanterade Windows 10-enheter-användare** i **namn**, Välj **tilldelat** i **medlemskaps typ**och klicka sedan på **skapa**. 
    
8. Klicka på **Microsoft Intune**. Klicka på **skapa en policy för efterlevnad**i listan **snabb uppgifter** i fönstret **Microsoft Intune** .
    
9. Klicka på **Skapa princip**i fönstret **policy profiler för efterlevnad** .
    
10. I fönstret **Skapa princip** skriver du **Windows 10**i **namn**. I **Platform**väljer du **Windows 10 och senare**klickar du på **OK** i fönstret **efterlevnad för Windows 10** och klickar sedan på **skapa**. 
    
11. Klicka på **profiler för efterlevnadsprinciper**och klicka sedan på princip namnet för **Windows 10** .
    
12. I fönstret **Windows 10** klickar du på **uppgifter**och sedan på **Välj grupper som ska ingå**.
    
13. Klicka på gruppen **hanterade användare av Windows 10-enhet** i fönstret **Välj grupper som ska inkluderas** och klicka sedan på **Välj**.
    
14. Klicka på **Spara**, klicka på **Microsoft Intune-översikt**och klicka sedan på **klient program** i det vänstra navigerings fältet.
    
15. I fönstret **klient program** klickar du på **appar**och sedan på **Lägg till**. 

16. Välj **program typ**i fönstret **Lägg till app** och välj sedan **Windows 10** under **Microsoft 365 Suite**.

17. I fönstret **Lägg till app** väljer du **information för programpaket**.
 
18. I fönstret **information om programsviten** skriver du **Microsoft 365-appar för företag** i både **serie namn** och **programbeskrivning**.
Klicka på OK.

19. I fönstret **Lägg till app** väljer du **Konfigurera programsvit**och klickar sedan på **OK**.

20. I fönstret **Lägg till app** väljer du **Inställningar för programpaket**.

21. För **Uppdatera kanal**väljer du **halvår för företag**och klickar sedan på **OK**.

22. Klicka på **Lägg till**i fönstret **Lägg till app** .

Du har nu en policy för enhetskompatibilitet för att testa de valda programmen i policyn för **Windows 10** -enheter och för medlemmar i gruppen **användare av hanterade Windows 10-enheter** . Observera att om du väljer Microsoft 365 som grupptyp skapas ytterligare resurser. 
  
## <a name="next-step"></a>Nästa steg

Utforska fler funktioner och funktioner för [hantering av mobila enheter](m365-enterprise-test-lab-guides.md#mobile-device-management) i test miljön.

## <a name="see-also"></a>Se även

[Microsoft 365 för företags test labb guider](m365-enterprise-test-lab-guides.md).
  
[Registrera iOS-och Android-enheter i test miljön för Microsoft 365 för företag](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
