---
title: Ökad Microsoft 365-säkerhet för microsoft 365 Enterprise-testmiljön
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
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Använd den här testlabbet-guiden om du vill aktivera ytterligare microsoft 365-säkerhetsinställningar i Microsoft 365 Enterprise-testmiljön.
ms.openlocfilehash: 53205f0626ce55c5a9627339f3631964e3374a19
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631675"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Ökad Microsoft 365-säkerhet för microsoft 365 Enterprise-testmiljön

*Den här testlabbguiden kan bara användas i Microsoft 365 Enterprise-testmiljöer.*

Med instruktionerna i den här artikeln konfigurerar du ytterligare Microsoft 365-inställningar för att öka säkerheten i microsoft 365 Enterprise-testmiljön.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med Microsoft 365 Enterprise-testlabbguider.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygga ut testmiljön i Microsoft 365 Enterprise

Om du bara vill konfigurera ökad Microsoft 365-säkerhet på ett lätt väg med minimikraven följer du instruktionerna i [Lightweight base-konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera ökad Microsoft 365-säkerhet i ett simulerat företag följer du instruktionerna i [Direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av ökad Microsoft 365-säkerhet kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fas 2: Konfigurera ökad Microsoft 365-säkerhet

I den här fasen aktiverar du ökad Microsoft 365-säkerhet för microsoft 365 Enterprise-testmiljön. Mer information och inställningar finns i [Konfigurera klienten för ökad säkerhet](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Konfigurera SharePoint Online för att blockera appar som inte stöder modern autentisering

Appar som inte stöder modern autentisering kan inte ha [konfigurationer för identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) som tillämpas på dem, vilket är en viktig del för att skydda din Microsoft 365-prenumeration och dess digitala tillgångar. 

1. Gå till Microsoft 365[https://portal.microsoft.com](https://portal.microsoft.com)admincenter ( ) och logga in på din Microsoft 365 testlabbprenumeration med ditt globala administratörskonto.
    
  - Om du använder den lätta testmiljön för Microsoft 365 loggar du in från den lokala datorn.
    
  - Om du använder testmiljön för simulerade företag microsoft 365 använder du [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella klientdatorn och loggar sedan in från CLIENT1.
 
2. Klicka på **SharePoint**under **Administrationscenter** i det vänstra navigeringsfönstret på fliken **Microsoft 365 i administrationscentret.**
3. Klicka på **Principer > Åtkomstkontroll**på fliken Nytt **administrationscenter i SharePoint.**
4. Klicka på **Appar som inte stöder modern autentisering,** välj Blockera **åtkomst**och klicka sedan på **Spara**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Aktivera avancerat skydd mot hot för SharePoint, OneDrive för företag och Microsoft Teams

Office 365 Advanced Threat Protection (ATP) för SharePoint, OneDrive och Microsoft Teams skyddar din organisation från att oavsiktligt dela skadliga filer.

1. Gå till [Security & Compliance Center](https://protection.office.com) och logga in med ditt globala administratörskonto.

2. Klicka på **Princip**under **Hothantering**i det vänstra navigeringsfönstret och klicka sedan på **BETRODDa bifogade filer.** 

3. Under **Skydda filer i SharePoint, OneDrive och Microsoft Teams**. välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.

4. Klicka på **Spara**.


### <a name="enable-anti-malware"></a>Aktivera anti-malware

Skadlig kod består av virus och spionprogram. Virus infekterar andra program och data, och de sprids i hela datorn letar efter program att infektera. Spionprogram refererar till skadlig kod som samlar in din personliga information, till exempel inloggningsinformation och personuppgifter, och skickar tillbaka den till den skadliga koden. 

Microsoft 365 har inbyggda funktioner för filtrering av skadlig kod och skräppost som skyddar inkommande och utgående meddelanden från skadlig programvara och skyddar dig från skräppost. Mer information finns i [Skydd mot skräppost & skydd mot skadlig kod i Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

Så här säkerställer du att bearbetning av skadlig kod utförs på filer med vanliga filtyper för bifogade filer:

1. Klicka på bakåtknappen i webbläsaren för att komma tillbaka till **sidan Policy.**
2. Klicka på **Anti-malware**.
3. Dubbelklicka på principen **Standard**.
4. Klicka på **Inställningar**i **policyfönstret mot skadlig kod** .
4. Under **filtret Vanliga typer av bifogade filer**väljer du **På**och klickar sedan på **Spara**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fas 3: Undersök säkerhetsinstrumentpanelen

Office 365-hothantering kan hjälpa dig att kontrollera och hantera åtkomst till mobila enheter till organisationens data, skydda din organisation från dataförlust och skydda inkommande och utgående meddelanden från skadlig programvara och skräppost. Du använder också hothantering för att skydda domänens rykte och för att avgöra om avsändare förfalskar konton från domänen eller inte. 

Så här ser du säkerhetsinstrumentpanelen:

1. Om det behövs går du till [Security & Compliance Center](https://protection.office.com) och loggar in med ditt globala administratörskonto.

2. Klicka på **Instrumentpanel**under **Hothantering**i det vänstra navigeringsfönstret.

Ta en närmare titt på alla kort på instrumentpanelen för att bekanta dig med den information som tillhandahålls.

Mer information finns i [Säkerhetspanelen](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fas 4: Undersök Microsoft Secure Score

Microsoft Secure Score visar din säkerhetsposition som ett nummer, vilket anger din nuvarande nivå i förhållande till de funktioner som är tillgängliga i din prenumeration. Det ger dig också en lista över förbättringsåtgärder du kan vidta för att förbättra din poäng.

1. Skapa en ny flik i webbläsaren och gå till [Säkerhetscentret för Microsoft 365](https://security.microsoft.com/)och klicka sedan på **Säker poäng**.
2. På fliken **Översikt** noterar du ditt nuvarande säkra resultat och hur det kan jämföras med det globala genomsnittet och prenumerationerna med ett liknande antal licenser.
3. På fliken **Förbättringsåtgärder** läser du igenom listan över åtgärder som du kan vidta för att öka din poäng.

Mer information finns i [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="next-steps"></a>Nästa steg

Se steget [Konfigurera ökad säkerhet för Microsoft 365](infoprotect-configure-increased-security-office-365.md) i **informationsskyddsfasen** för information och länkar för att konfigurera dessa inställningar i produktionen.

Utforska ytterligare funktioner och funktioner för [informationsskydd](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.

## <a name="see-also"></a>Snabbreferens

[Testlabbguider för Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
