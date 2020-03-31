---
title: Testlabbguider för Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Skapa miljöer för demonstrationer, funktionstest och utveckling/testning för Microsoft 365 för företag med hjälp av testlabbguider.
ms.openlocfilehash: 4190eb4619f4732310786b5a7dde6bb590a969c1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805849"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Testlabbguider för Microsoft 365 för företag

*Detta gäller för både Microsoft 365 för företag och Office 365 Enterprise.*

Med testlabbguider kan du snabbt lära dig mer om Microsofts produkter. De innehåller instruktioner för hur du konfigurerar enkla men representativa testmiljöer. Du kan använda dessa miljöer för demonstrationer, anpassningar eller skapa komplexa funktionstester under giltighetstiden för en utvärderingsversion eller med en betald prenumeration. 

Testlabbguiderna är modulära. De bygger på varandra, vilket innebär att du kan skapa flera konfigurationer som matchar dina utbildnings- eller testkonfigurationsbehov. ”Jag skapade det själv och det fungerar” är känslan man får med sig efter de praktiska övningarna. Guiderna hjälper dig att förstå distributionskraven för en ny produkt eller ett nytt scenario, så att du kan planera bättre för distributionen i produktion.

Du kan också skapa representativa miljöer för utveckling och testning av program med hjälp av testlabbguiderna.
  
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.

[![Samlingen med testlabbguider för Microsoft 365 för företag](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>Grundläggande konfiguration

Först skapar du en testmiljö för [Microsoft 365 för företag](https://docs.microsoft.com/microsoft-365-enterprise/) som innehåller Office 365 E5, Enterprise Mobility + Security (EMS) E5 och Windows 10 Enterprise. Du kan skapa två olika typer av grundläggande konfigurationer:

- Använd den [enkla grundläggande konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md) när du vill konfigurera och demonstrera funktioner för Microsoft 365 för företag i en molnmiljö, som inte omfattar några lokala komponenter.

- Använd [grundläggande konfiguration för simulerat företag](simulated-ent-base-configuration-microsoft-365-enterprise.md) när du vill konfigurera och demonstrera funktioner för Microsoft 365 för företag i en hybridmolnmiljö, som omfattar lokala komponenter som en AD DS-domän (Active Directory Domain Services).

Du kan också skapa testmiljöer för Office 365 E5 genom att inte lägga till Microsoft 365 E5-licensen i utvärderings- eller produktionstestmiljön.
    
## <a name="identity"></a>Identitet

För en demonstration av identitetsrelaterade funktioner, se:

- [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md)
  
   Aktivera och testa lösenordshash-baserad katalogsynkronisering från en AD DS-domänkontrollant.

- [Direktautentisering](pass-through-auth-m365-ent-test-environment.md)
  
   Aktivera och testa direktautentisering till en AD DS-domänkontrollant.

- [Federerad autentisering](federated-identity-for-your-office-365-dev-test-environment.md)
  
   Aktivera och testa federerad autentisering till en AD DS-domänkontrollant.

- [Enkel inloggning med Azure AD](single-sign-on-m365-ent-test-environment.md)
  
   Aktivera och testa enkel inloggning med Azure AD med en AD DS-domänkontrollant.

- [Multifaktorautentisering](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Aktivera och testa multifaktorautentisering via telefon för ett specifikt användarkonto.

- [Skydda globala administratörskonton](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   Lås dina globala administratörskonton med principer för villkorsstyrd åtkomst.

- [Tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md)

   Använd tillbakaskrivning av lösenord när du ändrar lösenordet för ditt AD DS-användarkonto från Azure AD.

- [Återställning av lösenord](password-reset-m365-ent-test-environment.md)

   Använd självbetjäning av lösenordsåterställning (SSPR) för att återställa ditt lösenord.

- [Automatisk licensiering och gruppmedlemskap](automate-licenses-group-membership-microsoft-365-test-environment.md)

   Administrera nya konton enklare än någonsin med automatisk licensiering och medlemskap i dynamiska grupper.

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   Sök igenom dina aktuella användarkonton efter säkerhetsrisker.

- [Identitet och enhetsåtkomst](identity-device-access-m365-test-environment.md)

   Skapa en miljö för att testa rekommenderade konfigurationer för identitet och enhetsåtkomst och principer för villkorsstyrd åtkomst.


## <a name="mobile-device-management"></a>Hantering av mobila enheter

För en demonstration av funktioner för hantering av mobila enheter, se:

- [Principer för enhetsefterlevnad](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Skapa en användargrupp och en princip för enhetsefterlevnad för Windows 10-enheter.
    
- [Registrera iOS- och Android-enheter](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   Registrera iOS-och Android-enheter och hantera dem på distans.


## <a name="information-protection"></a>Informationsskydd

För en demonstration av informationsskyddsrelaterade funktioner, se:

- [Ökad säkerhet för Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Konfigurera inställningar för ökad säkerhet i Office 365 och utforska inbyggda säkerhetsverktyg.
  
- [Dataklassificering](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Konfigurera och använd Office 365-etiketter i ett dokument på en SharePoint Online-gruppwebbplats.
    
- [Privilegierad åtkomsthantering](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Konfigurera privilegierad åtkomsthantering för just-in-time-åtkomst till upphöjda och privilegierade uppgifter i din Office 365-organisation.


