---
title: Ökad Microsoft 365-säkerhet för din Testmiljö för Microsoft 365 för företag
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
description: Använd den här testlabbguiden för att aktivera ytterligare Microsoft 365-säkerhetsinställningar i testmiljön Microsoft 365 för företag.
ms.openlocfilehash: d1bff8b736e5074f621a173d206f7c5f77841b25
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198357"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Ökad Microsoft 365-säkerhet för din Testmiljö för Microsoft 365 för företag

*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*

Med hjälp av instruktionerna i den här artikeln konfigurerar du ytterligare Microsoft 365-inställningar för att öka säkerheten i testmiljön Microsoft 365 för företag.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicka [här](../downloads/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: Bygg ut microsoft 365 för företagstestmiljö

Om du bara vill konfigurera ökad Microsoft 365-säkerhet på ett lätt sätt med minimikraven följer du anvisningarna i [Lätt baskonfiguration.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Om du vill konfigurera ökad Microsoft 365-säkerhet i ett simulerat företag följer du anvisningarna i [Direktautentisering.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Om du testar ökad Microsoft 365-säkerhet krävs inte den simulerade företagstestmiljön, som omfattar en simulerad intranätansluten till Internet och katalogsynkronisering för en AD DS-skog (Active Directory Domain Services). Här finns ett alternativ så att du kan testa automatiska licenser och gruppmedlemskap och experimentera med det i en miljö som representerar en vanlig organisation. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fas 2: Konfigurera ökad Microsoft 365-säkerhet

I den här fasen aktiverar du ökad Microsoft 365-säkerhet för din Testmiljö för Microsoft 365 för företag. Mer information och inställningar finns i Konfigurera [klientorganisationen för ökad säkerhet.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Konfigurera SharePoint Online för att blockera appar som inte stöder modern autentisering

Appar som inte stöder modern autentisering kan inte ha [identitets-](../security/office-365-security/microsoft-365-policies-configurations.md) och enhetsåtkomstkonfigurationer tillämpade på dem, vilket är en viktig del av att skydda din Microsoft 365-prenumeration och dess digitala tillgångar. 

1. Gå till administrationscentret för Microsoft 365 ( ) och logga in på din [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365-provlabbprenumeration med ditt globala administratörskonto.
    
  - Om du använder den lätta Microsoft 365-testmiljön loggar du in från din lokala dator.
    
  - Om du använder den simulerade Microsoft 365-testmiljön för företag använder du [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella KLIENT1-datorn och loggar sedan in från KLIENT1.
 
2. På den nya **fliken Administrationscenter för Microsoft 365,** under **Administrationscenter i** det vänstra navigeringsfönstret, klickar du på **SharePoint.**
3. På den nya **fliken Administrationscenter för SharePoint** klickar du på **Principer > Åtkomstkontroll**.
4. Klicka **på Appar som inte stöder modern autentisering .** Välj Blockera **åtkomst** och klicka sedan på **Spara**.


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Aktivera Defender för Office 365 för SharePoint, OneDrive för företag och Microsoft Teams

Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams skyddar organisationen från att oavsiktligt dela skadliga filer.

1. Gå till [Säkerhets- & Säkerhets- och](https://protection.office.com) efterlevnadscenter och logga in med ditt globala administratörskonto.

2. I det vänstra navigeringsfönstret, under **Hothantering,** klickar du **på Princip** och sedan på Säkra **bifogade filer.** 

3. Under **Skydda filer i SharePoint, OneDrive och Microsoft Teams**. välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams.**

4. Klicka på **Spara**.


### <a name="enable-anti-malware"></a>Aktivera skadlig programvara

Skadlig programvara består av virus och spionprogram. Virus smittar andra program och data, och de sprids i din dator genom att söka efter program som de kan smitta. Spionprogram används om skadlig programvara som samlar in personlig information, till exempel inloggningsuppgifter och personuppgifter, som sedan skickas tillbaka till den som skapar skadlig programvara. 

Microsoft 365 har inbyggd skadlig programvara och filtrering av skräppost som hjälper till att skydda inkommande och utgående meddelanden från skadlig programvara och skydda dig mot skräppost. Mer information finns i Skydd [mot skräppost & skydd mot skadlig programvara.](../security/office-365-security/anti-spam-and-anti-malware-protection.md)

Så här säkerställer du att bearbetning med skadlig programvara utförs på filer med vanliga filtyper för bifogade filer:

1. Gå tillbaka till sidan Princip genom att klicka på **tillbakaknappen i** webbläsaren.
2. Klicka **på Skydd mot skadlig programvara.**
3. Dubbelklicka på principen Standard **.**
4. Klicka på **Inställningar i fönstret princip mot** skadlig **programvara.**
4. Under **Vanliga typer av bifogade filer** väljer du **På** och klickar sedan på **Spara.**


## <a name="phase-3-examine-the-security-dashboard"></a>Fas 3: Undersöka säkerhetspanelen

Hothantering i Microsoft 365 kan hjälpa dig att styra och hantera mobil enhetsåtkomst till din organisations data, skydda organisationen från dataförlust och skydda inkommande och utgående meddelanden från skadlig programvara och skräppost. Du använder även hothantering för att skydda domänens rykte och för att avgöra om avsändare är skadliga förfalskningskonton från din domän. 

Så här visar du säkerhetspanelen:

1. Om det behövs går du till [säkerhets- & säkerhets- och](https://protection.office.com) efterlevnadscentret och loggar in med ditt globala administratörskonto.

2. I det vänstra navigeringsfönstret, under **Hothantering, klickar** du på **Instrumentpanel**.

Ta en närmare titt på alla kort på instrumentpanelen för att bekanta dig med den information som finns.

Mer information finns i [Säkerhetsinstrumentpanel](../security/office-365-security/security-dashboard.md).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fas 4: Undersöka Microsoft Secure Score

Microsoft Secure Score visar att din säkerhet ligger på ett nummer, vilket anger din aktuella nivå i förhållande till de funktioner som är tillgängliga i din prenumeration. Du får också en lista över förbättringsåtgärder du kan vidta för att förbättra ditt resultat.

1. Skapa en ny flik i webbläsaren, gå till [Säkerhetscenter för Microsoft 365](https://security.microsoft.com/)och klicka sedan på **Säker poäng.**
2. På fliken **Översikt**  kan du notera ditt aktuella Secure Score och hur det står sig jämfört med det globala medelvärdet och prenumerationer med liknande antal licenser.
3. På fliken **Förbättringsåtgärder** läser du igenom listan med åtgärder du kan vidta för att höja poäng.

Mer information finns i [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).

## <a name="next-steps"></a>Nästa steg

Utforska ytterligare [informationsskyddsfunktioner](m365-enterprise-test-lab-guides.md#information-protection) i testmiljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)