---
title: Ökad Microsoft 365-säkerhet för din Testmiljö för Microsoft 365 Enterprise
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
description: Använd den här testlabbguiden för att aktivera ytterligare Microsoft 365-säkerhetsinställningar för din Testmiljö för Microsoft 365 Enterprise.
ms.openlocfilehash: 465e9df40e8dfe9883a81d352eabff17151df8f3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807002"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Ökad Microsoft 365-säkerhet för din Testmiljö för Microsoft 365 Enterprise

*Den här testlabbguiden kan endast användas för Testmiljöer för Microsoft 365 Enterprise.*

Med instruktionerna i den här artikeln konfigurerar du ytterligare Microsoft 365-inställningar för att öka säkerheten i din Testmiljö för Microsoft 365 Enterprise.

![Testa labbguider för Microsoft-molnet](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) för en visuell karta till alla artiklar i Microsoft 365 Enterprise Test Lab Guide stacken.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fas 1: Bygg upp din Testmiljö för Microsoft 365 Enterprise

Om du bara vill konfigurera ökad Microsoft 365-säkerhet på ett lätt sätt med minimikraven följer du instruktionerna i [Lightweight-baskonfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera ökad Microsoft 365-säkerhet i ett simulerat företag följer du instruktionerna i [direktautentisering](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av ökad Microsoft 365-säkerhet kräver inte den simulerade företagstestmiljön, som innehåller ett simulerat intranät som är anslutet till Internet- och katalogsynkroniseringen för en AD DS-skog (Active Directory Domain Services). Det finns här som ett alternativ så att du kan testa automatiserad licensiering och gruppmedlemskap och experimentera med det i en miljö som representerar en typisk organisation. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fas 2: Konfigurera ökad Microsoft 365-säkerhet

I den här fasen aktiverar du ökad Microsoft 365-säkerhet för din Microsoft 365 Enterprise-testmiljö. Mer information och inställningar finns i [Konfigurera din Office 365-klient för ökad säkerhet](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Konfigurera SharePoint Online för att blockera appar som inte stöder modern autentisering

Appar som inte stöder modern autentisering kan inte ha [identitets- och enhetsåtkomstkonfigurationer](microsoft-365-policies-configurations.md) som tillämpas på dem, vilket är en viktig del av att skydda din Microsoft 365-prenumeration och dess digitala tillgångar. 

1. Gå till administrationscentret för[https://portal.microsoft.com](https://portal.microsoft.com)Microsoft 365 ( ) och logga in på din Microsoft 365-testlabbprenumeration med ditt globala administratörskonto.
    
  - Om du använder den lätta testmiljön i Microsoft 365 loggar du in från den lokala datorn.
    
  - Om du använder den simulerade testmiljön för företaget Microsoft 365 använder du [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella KLIENTEN FÖR KLIENT1 och loggar sedan in från CLIENT1.
 
2. Klicka på **SharePoint**under **Administrationscenter** i det vänstra navigeringsfönstret på fliken nytt **administrationscenter i Microsoft 365.**
3. Klicka på **Access-kontroll**på fliken Nytt **administrationscenter i SharePoint.**
4. Klicka på **Appar som inte stöder modern autentisering,** välj Blockera **åtkomst**och klicka sedan på **Spara**.


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Aktivera avancerat hotskydd för SharePoint- och OneDrive för företag och Microsoft-team

Office 365 Advanced Threat Protection (ATP) för SharePoint, OneDrive och Microsoft Teams skyddar din organisation från att oavsiktligt dela skadliga filer.

1. Gå till [Office 365 Security & Compliance Center](https://protection.office.com) och logga in med ditt globala administratörskonto.

2. Klicka på **Princip**under **Hothantering**i det vänstra navigeringsfönstret och klicka sedan på **AP-säkra bilagor**. 

3. Under **Skydda filer i SharePoint, OneDrive och Microsoft Teams**. välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.

4. Klicka på **Spara**.


### <a name="enable-anti-malware"></a>Aktivera skadlig kod

Skadlig kod består av virus och spionprogram. Virus infekterar andra program och data, och de sprids över hela datorn letar efter program att infektera. Spionprogram refererar till skadlig kod som samlar in din personliga information, till exempel inloggningsinformation och personuppgifter, och skickar tillbaka den till den skadliga koden. 

Microsoft 365 har inbyggda funktioner för skadlig programvara och skräppostfiltrering som hjälper till att skydda inkommande och utgående meddelanden från skadlig programvara och skyddar dig från skräppost. Mer information finns i [Skydd mot skräppost & skydd mot skadlig kod i Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

Så här kontrollerar du att bearbetning mot skadlig kod utförs på filer med vanliga filtyper för bifogade filer:

1. Klicka på bakåtknappen i webbläsaren för att komma tillbaka till **sidan Policy.**
2. Klicka på **Anti-malware**.
3. Dubbelklicka på principen **Standard**.
4. Klicka på **Inställningar**i **principfönstret Mot skadlig kod** .
4. Under **Filtret Vanliga bifogade filer**väljer du **På**och klickar sedan på **Spara**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fas 3: Undersök säkerhetsinstrumentpanelen

Hothantering i Office 365 kan hjälpa dig att kontrollera och hantera åtkomst till mobila enheter till organisationens data, skydda din organisation från dataförlust och skydda inkommande och utgående meddelanden från skadlig programvara och skräppost. Du använder också hothantering för att skydda domänens rykte och för att avgöra om avsändare är skadligt förfalska konton från din domän. 

Så här visar du säkerhetsinstrumentpanelen:

1. Om det behövs går du till [Office 365 Security & Compliance Center](https://protection.office.com) och loggar in med ditt globala administratörskonto.

2. Klicka på **Instrumentpanel**under **Hothantering**i det vänstra navigeringsfönstret .

Ta en närmare titt på alla kort på instrumentpanelen för att bekanta dig med den information som tillhandahålls.

Mer information finns i [Säkerhetsinstrumentpanelen](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fas 4: Undersök Microsoftsecure-poäng

Microsoft Secure Score visar din säkerhetsposition som ett tal, vilket anger din aktuella nivå i förhållande till de funktioner som är tillgängliga i prenumerationen. Det ger dig också en lista över förbättringsåtgärder du kan vidta för att förbättra din poäng.

1. Skapa en ny flik i webbläsaren och gå till [Säkerhetscentret för Microsoft 365](https://security.microsoft.com/)och klicka sedan på **Säker poäng**.
2. På fliken **Översikt** bör du notera din aktuella säkra poäng och hur det kan jämföras med det globala genomsnittet och prenumerationer med ett liknande antal licenser.
3. På fliken **Förbättringsåtgärder** läser du igenom listan över åtgärder som du kan vidta för att öka poängen.

Mer information finns i [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="next-steps"></a>Nästa steg

Se [steget Konfigurera ökad säkerhet för Microsoft 365](infoprotect-configure-increased-security-office-365.md) i **informationsskyddsfasen** för information och länkar för att konfigurera dessa inställningar i produktionen.

Utforska ytterligare [funktioner för informationsskydd](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.

## <a name="see-also"></a>Se även

[Labbguider för Microsoft 365 Enterprise Test](m365-enterprise-test-lab-guides.md)

[Distribuera Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation för Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
