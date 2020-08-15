---
title: Azure AD Identity Protection för test miljön av Microsoft 365 för företag
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
description: Konfigurera Azure AD Identity Protection och analysera aktuella konton i test miljön för Microsoft 365 för företag.
ms.openlocfilehash: bd1e7560e978b13d24e9e93a99a2567adca95c75
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694996"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a>Azure AD Identity Protection för test miljön av Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Med identitets skydd i Azure Active Directory (Azure AD) kan du upptäcka potentiella säkerhets problem som påverkar organisationens identitet, konfigurera automatiserade svar och undersöka incidenter. I den här artikeln beskrivs hur du använder Azure AD Identity Protection för att visa analyser av test miljö kontona.

Det finns två faser för konfiguration av Azure AD Identity-skydd i test miljön för Microsoft 365 för företag:

1. Skapa test miljön för Microsoft 365 för företag.
2. Använd Azure AD Identity Protection.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill testa Azure AD Identity-skyddet på ett billigt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill testa Azure AD Identity Protection i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av Azure AD Identity Protection kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en AD DS-skog (Active Directory Domain Services). Det finns ett alternativ som gör att du kan testa Azure AD Identity-skyddet och experimentera med den i en miljö som representerar en typisk organisation. 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a>Fas 2: använda Azure AD Identity-skydd

1. Öppna en privat instans av webbläsaren och logga in på Azure-portalen [https://portal.azure.com](https://portal.azure.com) med det globala administratörs kontot i test miljön för Microsoft 365 för företag.
2. I Azure-portalen skriver du **identitets skydd** i sökrutan och klickar sedan på **Azure AD Identity Protection**.
3. I bladet **identitets skydd-översikt** klickar du på var och en av rapporterna för att se vad de rapporterar.
4. Under **meddela**klickar **du på användare med risk varningar**.
5. Välj **medium**i fönstret **användare vid risk identifiering** .
6. För **e-postmeddelanden skickas till följande användare**: Klicka på **inkluderat** och kontrol lera att ditt globala administratörs konto finns med i listan med valda medlemmar.
7. Klicka på **Spara**.

Klicka igenom de olika principerna under **skydda** för att se hur du konfigurerar dem. Om du skapar och aktiverar en princip bör du kontrol lera att den inte blockerar åtkomsten för ett alltför långt giltighets område, eller så kanske du inte kan logga in, även som den globala administratören.

Mer information om testning och experimentering finns i [simulera risk händelser](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).

## <a name="next-step"></a>Nästa steg

Utforska ytterligare [identitetsfunktioner](m365-enterprise-test-lab-guides.md#identity) i testmiljön.

## <a name="see-also"></a>Se även

[Identitets översikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
