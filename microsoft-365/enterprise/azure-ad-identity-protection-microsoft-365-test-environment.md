---
title: Azure AD Identity Protection för din Testmiljö för Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurera Azure AD Identity Protection och analysera de aktuella kontona i din Microsoft 365 Enterprise-testmiljö.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42810371"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a>Azure AD Identity Protection för din Testmiljö för Microsoft 365 Enterprise

*Den här testlabbguiden kan endast användas för Testmiljöer för Microsoft 365 Enterprise.*

Med Azure Active Directory (Azure AD) Identity Protection kan du identifiera potentiella säkerhetsproblem som påverkar organisationens identiteter, konfigurera automatiska svar och undersöka incidenter. I den här artikeln beskrivs hur du använder Azure AD Identity Protection för att visa analysen av dina testmiljökonton.

Det finns två faser för att konfigurera Azure AD Identity Protection i din Testmiljö för Microsoft 365 Enterprise:

1. Skapa testmiljön för Microsoft 365 Enterprise.
2. Använd Azure AD Identity Protection.

![Testa labbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) för en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide stacken.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygg upp din Testmiljö för Microsoft 365 Enterprise

Om du bara vill testa Azure AD Identity Protection på ett lätt sätt med minimikraven följer du instruktionerna i [Lightweight baskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa Azure AD Identity Protection i ett simulerat företag följer du instruktionerna i [direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av Azure AD Identity Protection kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet- och katalogsynkroniseringen för en AD DS-skog (Active Directory Domain Services). Den finns här som ett alternativ så att du kan testa Azure AD Identity Protection och experimentera med det i en miljö som representerar en typisk organisation. 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fas 2: Använd Azure AD Identity Protection

1. Öppna en privat instans av din webbläsare och [https://portal.azure.com](https://portal.azure.com) logga in på Azure-portalen med det globala administratörskontot för din Testmiljö för Microsoft 365 Enterprise.
2. Skriv **identitetsskydd** i sökrutan i Azure-portalen och klicka sedan på **Azure AD Identity Protection**.
3. I bladet **Identitetsskydd - Översikt** klickar du på var och en av rapporterna för att se vad de rapporterar.
4. Klicka på **Användare i riskzonen som upptäckts aviseringar under** **Meddelande**.
5. Välj **Medel**i fönstret **Användare med riskidentifierade aviseringar.**
6. För **e-postmeddelanden skickas till följande användare**, klicka på **Ingår** och kontrollera att ditt globala administratörskonto finns i listan över valda medlemmar.
7. Klicka på **Spara**.

Klicka igenom de olika principerna under **Skydda** för att se hur du konfigurerar dem. Om du skapar och aktiverar en princip kontrollerar du att den inte blockerar åtkomsten för ett alltför brett utrymme för villkor, eller så kanske du inte kan logga in, inte ens som global administratör.

För ytterligare testning och experiment, se [Simulera riskhändelser](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

Se steget [Skydda mot autentiseringskomprometterande åtgärder i identitetsfasen](identity-secure-user-sign-ins.md#identity-ident-prot) för information och länkar för att distribuera Azure AD Identity Protection i produktionen.

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) och funktioner i testmiljön.

## <a name="see-also"></a>Se även

[Fas 2: Identitet](identity-infrastructure.md)

[Labbguider för Microsoft 365 Enterprise Test](m365-enterprise-test-lab-guides.md)

[Distribution av Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation för Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
