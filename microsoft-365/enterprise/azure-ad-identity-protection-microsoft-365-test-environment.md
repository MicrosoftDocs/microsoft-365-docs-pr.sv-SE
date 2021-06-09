---
title: Azure AD-identitetsskydd för din Microsoft 365 för företagstestmiljö
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
description: Konfigurera Azure AD Identity Protection och analysera de aktuella kontona i din Microsoft 365 för företagstestmiljö.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905350"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD-identitetsskydd för din Microsoft 365 för företagstestmiljö

*Den här testlabbguiden kan endast användas Microsoft 365 för företagstestmiljöer.*

Du kan använda Azure Active Directory (Azure AD) Identity Protection för att upptäcka potentiella säkerhetsproblem som påverkar organisationens identiteter, konfigurera automatiska svar och undersöka incidenter. I den här artikeln beskrivs hur du använder Azure AD Identity Protection för att visa analysen av testmiljökontona.

Att konfigurera Azure AD-identitetsskydd i din Microsoft 365 för företagstestmiljö omfattar två faser:

- [Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fas 2: Använda Azure AD Identity Protection](#phase-2-use-azure-ad-identity-protection)

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> En visuell karta till alla artiklar i Microsoft 365 för företags testlabbguide stack finns i [Microsoft 365 för företags testlabbguide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: Bygg ut din Microsoft 365 för företagstestmiljö

Om du bara vill testa Azure AD Identity Protection på ett lätt sätt med minimikraven följer du anvisningarna i [Lightweight Base-konfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Om du vill testa Azure AD Identity Protection i ett simulerat företag följer du anvisningarna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Om du testar Azure AD Identity Protection krävs inte den simulerade företagstestmiljön, som omfattar en simulerad intranätansluten till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Den finns här som ett alternativ så att du kan testa Azure AD Identity Protection och experimentera med det i en miljö som representerar en vanlig organisation.
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fas 2: Använda Azure AD Identity Protection

1. Öppna en privat instans av webbläsaren och logga in på Azure-portalen med det globala administratörskontot för [https://portal.azure.com](https://portal.azure.com) din Microsoft 365 för företagstestmiljö.
2. I Azure-portalen skriver du **identitetsskydd** i sökrutan och väljer sedan **Azure AD Identity Protection.**
3. I **bladet Identitetsskydd –** Översikt markerar du varje rapport för att se vad det är för rapportering.
4. Under **Meddela** väljer du **Användare med risk upptäckte aviseringar.**
5. I fönstret **Användare med risk upptäckte aviseringar** väljer du **Medel**.
6. För **E-postmeddelanden skickas till följande användare** väljer du Ingår **och** kontrollerar att ditt globala administratörskonto finns med i listan med valda medlemmar.
7. Välj **Spara**.

Under **Skydda** väljer du olika metoder för att se hur du konfigurerar dem. Om du skapar och aktiverar en princip ska du kontrollera att den inte blockerar åtkomsten för alla användare, eller att du kanske inte kan logga in. Du kan förhindra detta genom att utesluta specifika användarkonton, till exempel globala administratörer.

Mer information om hur du provar och experimenterar [finns i Flytta upp riskhändelser.](/azure/active-directory/active-directory-identityprotection-playbook)

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitetsöversikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)