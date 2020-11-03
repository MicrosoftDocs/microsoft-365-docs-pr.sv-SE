---
title: Ökad Microsoft 365-säkerhet för test miljön av Microsoft 365 för företag
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
description: Använd den här test laboratorie guiden för att aktivera ytterligare Microsoft 365-säkerhets inställningar din Microsoft 365 för företags test miljö.
ms.openlocfilehash: d385688a6e59ee500442bcf1b815dfd165102242
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847006"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Ökad Microsoft 365-säkerhet för test miljön av Microsoft 365 för företag

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

Med instruktionerna i den här artikeln konfigurerar du ytterligare Microsoft 365-inställningar för att öka säkerheten i test miljön av Microsoft 365 för företag.

![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Klicka [här](../downloads/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fas 1: bygga ut test miljön för Microsoft 365 för företag

Om du bara vill konfigurera ökad Microsoft 365-säkerhet på ett enkelt sätt med minimi kraven följer du anvisningarna i [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Om du vill konfigurera utökad Microsoft 365-säkerhet i ett simulerat företag följer du anvisningarna i [vidarekoppling](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testning av utökad Microsoft 365-säkerhet kräver inte den simulerade företags test miljön, som innehåller ett simulerat intranät som är kopplat till Internet-och katalogs-synkronisering för en AD DS-skog (Active Directory Domain Services). Det tillhandahålls här som ett alternativ så att du kan testa automatiserad licensiering och grupp medlemskap och experimentera med den i en miljö som representerar en typisk organisation. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>Fas 2: Konfigurera utökad Microsoft 365-säkerhet

I den här fasen aktiverar du ökad Microsoft 365-säkerhet för din test miljö för Microsoft 365. Mer information och inställningar finns i [Konfigurera din klient organisation för ökad säkerhet](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Konfigurera SharePoint Online för att blockera appar som inte stöder modern

Appar som inte stöder modern lösenordsautentisering kan inte ha [identitets-och enhets åtkomst inställningar](../security/office-365-security/microsoft-365-policies-configurations.md) kopplade till dem, vilket är ett viktigt element för att skydda ditt Microsoft 365-abonnemang och dess digitala till gångar. 

1. Gå till administrations centret för Microsoft 365 [https://portal.microsoft.com](https://portal.microsoft.com) och logga in på ditt microsoft 365 test laboratorie abonnemang med ditt globala administratörs konto.
    
  - Om du använder test miljön för det lättviktiga Microsoft 365 loggar du in från din lokala dator.
    
  - Om du använder den simulerade företags test miljön för Microsoft 365 kan du använda [Azure-portalen](https://portal.azure.com) för att ansluta till den virtuella KLIENT1 och sedan logga in från KLIENT1.
 
2. På fliken ny **administrations Center för Microsoft 365** går du till **administrations** Center i det vänstra navigerings fönstret och klickar på **SharePoint**.
3. Klicka på **principer > åtkomst kontroll** på fliken nytt **administrations Center för SharePoint** .
4. Klicka på **appar som inte stöder modern auktorisering** , Välj **blockera åtkomst** och klicka sedan på **Spara**.


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>Aktivera Defender för Office 365 för SharePoint, OneDrive för företag och Microsoft Teams

Defender för Office 365 för SharePoint, OneDrive och Microsoft Teams skyddar din organisation från oavsiktlig delning av skadliga filer.

1. Gå till [säkerhets & Compliance Center](https://protection.office.com) och logga in med ditt globala administratörs konto.

2. I det vänstra navigerings fönstret under **Threat Management** klickar du på **princip** och sedan på **säkra bifogade filer**. 

3. Under **skydda filer i SharePoint, OneDrive och Microsoft Teams**. Välj **Aktivera ATP för SharePoint, OneDrive och Microsoft Teams**.

4. Klicka på **Spara**.


### <a name="enable-anti-malware"></a>Aktivera skadlig program vara

Skadlig program vara består av virus och spionprogram. Virus angriper andra program och data och de fördelas på hela datorn och letar efter program att infektera. Spionprogram refererar till skadlig program vara som samlar in dina person uppgifter, till exempel inloggnings information och person uppgifter, och skickar tillbaka den till författaren med skadlig program vara. 

Microsoft 365 har inbyggda funktioner för skräp post och spam som hjälper dig att skydda inkommande och utgående meddelanden från skadlig program vara och hjälpa till att skydda dig från skräp post. Mer information finns i [anti-spam & skydd mot skadlig program vara](../security/office-365-security/anti-spam-and-anti-malware-protection.md).

Så här kontrollerar du att behandling mot skadlig program vara utförs på filer med vanliga typer av bifogade filer:

1. Klicka på knappen bakåt i webbläsaren för att gå tillbaka till **princip** sidan.
2. Klicka på **skadlig program vara**.
3. Dubbelklicka på den princip som heter **default**.
4. Klicka på **Inställningar** i **princip fönstret mot skadlig program vara** .
4. Välj **på** under **vanliga typer av bifogade filer** och klicka sedan på **Spara**.


## <a name="phase-3-examine-the-security-dashboard"></a>Fas 3: granska säkerhets instrument panelen

Threat Management i Microsoft 365 hjälper dig att kontrol lera och hantera mobila enheters åtkomst till organisationens data, skydda din organisation från data förlust och hjälpa till att skydda inkommande och utgående meddelanden från skadlig program vara och skräp post. Du använder också Threat Management för att skydda din domäns rykte och för att avgöra om avsändaren är skadligt falsk från din domän. 

Så här visar du säkerhets instrument panelen:

1. Om det behövs går du till sidan [säkerhets & efterlevnad](https://protection.office.com) och loggar in med ditt globala administratörs konto.

2. Klicka på **instrument panel** under **Threat Management** i det vänstra navigerings fönstret.

Ta en titt på alla kort på instrument panelen för att bekanta dig med informationen.

Mer information finns i [säkerhets instrument panelen](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).


## <a name="phase-4-examine-microsoft-secure-score"></a>Fas 4: Undersök Microsofts säkra Poäng

Microsofts säkra poäng visar din Posture som ett nummer som visar din aktuella nivå i förhållande till de funktioner som är tillgängliga i ditt abonnemang. Du får också en lista över förbättrings åtgärder som du kan vidta för att förbättra din poäng.

1. Skapa en ny flik i webbläsaren och gå till [Microsoft 365 säkerhets Center](https://security.microsoft.com/)och klicka sedan på **säker Poäng**.
2. På fliken **Översikt**  ser du din nuvarande säkra poäng och hur den jämförs med det globala medelvärdet och abonnemanget med ett liknande antal licenser.
3. På fliken **förbättrings åtgärder** läser du igenom listan med åtgärder du kan vidta för att öka poängen.

Mer information finns i [Microsofts säkra Poäng](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).

## <a name="next-steps"></a>Nästa steg

Utforska ytterligare funktioner för [informations skydd](m365-enterprise-test-lab-guides.md#information-protection) i test miljön.

## <a name="see-also"></a>Se även

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
