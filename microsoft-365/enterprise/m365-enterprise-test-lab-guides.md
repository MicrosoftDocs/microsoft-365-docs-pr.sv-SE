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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Skapa miljöer för demonstrationer, funktionstest och utveckling/testning för Microsoft 365 för företag med hjälp av testlabbguider.
ms.openlocfilehash: a006f549d0ac68562faee9c935df7f15161b2f12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909604"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Testlabbguider för Microsoft 365 för företag

*Detta gäller för både Microsoft 365 för företag och Office 365 Enterprise.*

Med testlabbguider kan du snabbt lära dig mer om Microsofts produkter. De innehåller instruktioner för hur du konfigurerar enkla men representativa testmiljöer. Du kan använda dessa miljöer för demonstrationer, anpassningar eller skapa komplexa funktionstester under giltighetstiden för en utvärderingsversion eller med en betald prenumeration.

Testlabbguiderna är modulära. De bygger på varandra, vilket innebär att du kan skapa flera konfigurationer som matchar dina utbildnings- eller testkonfigurationsbehov. Med hjälp av funktionen "Jag har byggt ut det själv och det fungerar" får du hjälp att förstå distributionskraven för en ny produkt eller ett nytt scenario, så att du bättre kan planera för värdskap i produktionen.

Du kan också använda TGG för att skapa representativa miljöer för att utveckla och testa program, även kallat utvecklings-/testmiljöer.
  
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Om du vill visa en visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide, expanderar du följande bild eller går till Microsoft 365 för testlabbguidesstack för [företag.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

[![Samlingen med testlabbguider för Microsoft 365 för företag](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>Grundläggande konfiguration

Skapa först en testmiljö för [Microsoft 365 för företag.](/microsoft-365-enterprise/) Du kan skapa två olika typer av grundläggande konfigurationer:

- [Enkel grundkonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md) – Använd den här om du vill konfigurera och demonstrera Microsoft 365 för företagsfunktioner och -funktioner i en miljö som bara är molnbaserad, som inte innehåller några lokala komponenter.

- [Simulerad företagsbaskonfiguration](simulated-ent-base-configuration-microsoft-365-enterprise.md) – Använd det här alternativet när du vill konfigurera och visa Microsoft 365 för företagsfunktioner i en hybridmolnmiljö som använder lokala komponenter som ad ds-domäner (Active Directory Domain Services).

Du kan också skapa testmiljöer för Office 365 E5 genom att inte lägga till Microsoft 365 E5-licensen i utvärderings- eller produktionstestmiljön.
    
## <a name="identity"></a>Identitet

För en demonstration av identitetsrelaterade funktioner, se:

- [Synkronisering av lösenordshash](password-hash-sync-m365-ent-test-environment.md)
  
   Aktivera och testa lösenordshash-baserad katalogsynkronisering från en AD DS-domänkontrollant.

- [Direktautentisering](pass-through-auth-m365-ent-test-environment.md)
  
   Aktivera och testa direktautentisering till en AD DS-domänkontrollant.

- [Federerad autentisering](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   Aktivera och testa federerad autentisering till en AD DS-domänkontrollant.

- [Enkel inloggning med Azure AD](single-sign-on-m365-ent-test-environment.md)
  
   Aktivera och testa sömlös enkel inloggning (sömlös SSO) i Azure AD med en AD DS-domänkontrollant.

- [Multifaktorautentisering](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Aktivera och testa multifaktorautentisering via telefon för ett specifikt användarkonto.

- [Skydda globala administratörskonton](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   Lås dina globala administratörskonton med principer för villkorsstyrd åtkomst.

- [Tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md)

   Använd tillbakaskrivning av lösenord när du ändrar lösenordet för ditt AD DS-användarkonto från Azure AD.

- [Återställning av lösenord](password-reset-m365-ent-test-environment.md)

   Använd självbetjäning för återställning av lösenord för att återställa lösenordet.

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

- [Ökad säkerhet i Microsoft 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Konfigurera inställningar för ökad säkerhet i Microsoft 365 och utforska inbyggda säkerhetsverktyg.
  
- [Dataklassificering](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Konfigurera och använd etiketter i ett dokument på en SharePoint Online-gruppwebbplats.
    
- [Privilegierad åtkomsthantering](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Konfigurera privilegierad åtkomsthantering för just-in-time-åtkomst till upphöjda och privilegierade uppgifter i din organisation.