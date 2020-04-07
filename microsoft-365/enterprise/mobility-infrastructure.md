---
title: Fas 5 - Hantering av mobila enheter
description: Microsoft 365 Enterprise inkluderar hantering av mobila enheter med Microsoft Intune. Granska kraven och förutsättningarna, konfigurera Intune med din Azure Active Directory-resurs, registrera iOS-, macOS-, Android- och Windows-enheter, distribuera appar, skapa en konfigurera profil, använda en efterlevnadsprincip och aktivera villkorad åtkomst för hantering av mobila enheter med Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-dokumentation, hantering av mobila enheter, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: a957ef037aed1f9aba923af428c2a440790dbfba
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153898"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>Fas 5: Hantering av mobila enheter för Microsoft 365 Enterprise

![Fas 5: Hantering av mobilenheter](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*Den här funktionen gäller E3- och E5-versionerna av Microsoft 365 Enterprise*

Microsoft 365 Enterprise innehåller funktioner som hjälper till att hantera enheter och deras appar inom organisationen. Med Microsoft Intune kan du hantera iOS-, Android-, macOS- och Windows-enheter för att skydda åtkomsten till organisationens resurser, inklusive dina data. 

I den här fasen registrerar du dina enheter i Intune och skapar och tillämpar principer för att skydda dina data. Hela biblioteket med Intune-dokumentation [finns tillgängligt online](https://docs.microsoft.com/intune). Det är också bra att granska [Intune-distributionsplanerings-, design- och implementeringsguiden](https://docs.microsoft.com/intune/planning-guide) innan du börjar.

## <a name="step-1-plan-for-your-scenario"></a>Steg 1: Planera för ditt scenario

En av de främsta anledningarna till att hantera mobila enheter är att skydda organisationens resurser. [Vanliga sätt att använda Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) visar några verkliga exempel, bland annat att skydda Office 365-e-post och data.

Intune ger dig alternativ för att hantera åtkomst till din organisation med hjälp av MDM (Mobile Device Management) eller Mobile Application Management (MAM). MDM är när användare "registrera" sina enheter i Intune. När de har registrerats är de hanterade enheter och kan ta emot alla principer, regler och inställningar som används av din organisation. Du kan till exempel installera specifika appar, skapa en lösenordsprincip, installera en VPN-anslutning med mera.

Användare med sina egna personliga enheter kanske inte vill registrera sina enheter eller hanteras av Intune och dina policyer. Men du måste fortfarande skydda organisationens resurser och data. I det här fallet kan du skydda dina appar med MAM. Du kan till exempel använda en MAM-princip som kräver att en användare anger en PIN-kod när du öppnar SharePoint på enheten.

Du kommer också att bestämma hur du ska hantera personliga eller organisationsägda enheter. Du kanske vill behandla enheter på olika sätt, beroende på deras användning. Du kanske till exempel vill ha olika planer för användare i Personal (HR) eller användare i Försäljning. [Identifiera användningsfall för hantering av mobila enheter](https://docs.microsoft.com/intune/planning-guide-scenarios) kan komma igång och innehåller några riktlinjer för dessa olika scenarier.

## <a name="step-2-get-your-prerequisites"></a>Steg 2: Få dina förutsättningar

Hämta sedan dina förutsättningar baserat på dina krav och dina scenarier som skapats i föregående steg. [Implementera dina planlistor](https://docs.microsoft.com/intune/planning-guide-onboarding) för alla krav. Här är de viktiga objekt du behöver för Intune med Microsoft 365:

- **Intune-prenumeration:** Ingår i Microsoft 365 och ger dig åtkomst till Microsoft Intune i [Azure-portalen](https://portal.azure.com)
- **Office 365-prenumeration:** Ingår i Microsoft 365 och används för Office-appar, inklusive e-post
- **Azure Active Directory (Azure AD) premium**: Ingår i Microsoft 365 och används för att skapa användar- eller säkerhetsgrupper. Dessa grupper får Intune-principer som du skapar, till exempel att tvinga en lösenordslängd för att låsa upp en enhet. De grupper som du skapar i [fas 2: Identitet](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) kan användas.

Det kan finnas vissa ytterligare krav, beroende på organisationens behov. Om du till exempel ska hantera iOS-enheter behöver du ett Apple MDM Push-certifikat. Om du använder lokalt Exchange behöver du den lokala Exchange-kopplingen. Dessa ytterligare krav beskrivs när du kommer till dessa steg.

## <a name="step-3-set-up-intune"></a>Steg 3: Konfigurera Intune

Intune använder många funktioner i Azure AD, inklusive din domän, dina användare och dina grupper. Du kan också skapa nya användare och nya grupper som passar företagets behov. Du kan till exempel skapa en grupp som kallas **iOS-enheter**eller **Alla HR-användare**.  Dra nytta av [dynamiska grupper](https://docs.microsoft.com/intune/groups-add) som gör att du kan skapa antingen användar- eller enhetsgrupper baserat på enkla eller avancerade regler.

Det här steget fokuserar på att konfigurera Intune och göra det klart för dig att hantera dina enheter.

1. **[Bekräfta att dina enheter stöds](https://docs.microsoft.com/intune/supported-devices-browsers)**. Bekräfta att dina iOS-, macOS-, Android-, Galaxy- och Windows-enheter stöds av Intune. Om din organisation innehåller enheter som inte stöds tillämpas inte principerna på dessa enheter.

2. **[Anpassa ditt domännamn](https://docs.microsoft.com/intune/custom-domain-name-configure)**. Som standard skapas en domän med namnet **något i stil med your-domain.onmicrosoft.com** automatiskt i Azure AD. **onmicrosoft.com** kan anpassas för din organisation. När du anpassar den ger det också användarna en välbekant domän när de ansluter till Intune och använder resurser.

3. **[Logga in på Intune](https://docs.microsoft.com/intune/account-sign-up)**. När du loggar in kan du bli ombedd att ange information om din organisation. Intune ingår i Microsoft 365 och kan öppnas direkt från [Microsoft 365 admin center](https://admin.microsoft.com). Du kan också öppna Intune direkt från [Azure-portalen](https://portal.azure.com).

4. **[Välj konfiguration för hantering av mobila enheter](https://docs.microsoft.com/intune/mdm-authority-set)**. Första gången du använder Intune måste du aktivera enhetshantering. Intune kan användas som en molntjänst, en hybrid med Intune och Microsoft Endpoint Configuration Manager eller med hjälp av Hantering av mobila enheter för Office 365. Du kan välja vilken konfiguration som fungerar bäst för din organisation.

5. **[Lägg till användare](https://docs.microsoft.com/intune/users-add)** och **[lägg till grupper](https://docs.microsoft.com/intune/groups-add)**. 

   Du kan manuellt lägga till användare eller använda hybrididentitet och Azure AD Connect för att synkronisera dina lokala användarkonton med Intune. Du kan också ge administratörsroller till specifika användare. Användare krävs om inte dina enheter är "användarlösa" enheter, till exempel kioskenheter.

   Azure AD-grupper används för att förenkla hur du hanterar enheter och användare i Intune. Med hjälp av grupper kan du utföra många olika uppgifter. Din organisation vill till exempel kräva en viss app på Android-enheter. Du kan skapa en Android-enhetsgrupp och distribuera en princip med den här appen till gruppen.

    I Intune kan du lägga till användare eller grupper som du skapar i [fas 2: Identitet](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)

6. **[Tilldela licenser](https://docs.microsoft.com/intune/licenses-assign)**. För att användare eller enheter ska kunna registrera sig i Intune kräver de en Microsoft 365-licens med Intune-tjänsten aktiverad för att komma åt Intune-tjänsten. Du tilldelar Microsoft 365-licenser, som har Microsoft Intune-tjänsten aktiverad som standard, i Microsoft 365-administrationscentret eller med PowerShell.

## <a name="step-4-enroll-devices"></a>Steg 4: Registrera enheter

För att hantera enheter måste enheterna vara registrerade i Intune. Som administratör ska du ställa in registreringsbegränsningar och principer för användare och enheter. Varje enhetsplattform (iOS, Android, macOS och Windows) har en mängd olika alternativ. Du kan låta användarna registrera sig. Du kan också automatisera registreringen så att användarna helt enkelt loggar in på enheten.

Registrering är ett viktigt steg när du använder Intune. [Registrera enheter](https://docs.microsoft.com/intune/device-enrollment) visar stegen för de olika enheterna.

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: registrering av iOS- och Android-enheter](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>Steg 5: Lägga till och distribuera appar

Appar på mobila enheter är ofta det snabbaste sättet för användarna att få tillgång till dina företagsresurser. 

Det finns utmaningar när du använder appar, eftersom det finns olika enheter, inklusive personliga enheter och företagsenheter. Och du vill skydda organisationens resurser och dess data samtidigt som du ser till att användarna är produktiva.

Intune kan hantera appar, inklusive lägga till appar, tilldela dem till olika användare eller grupper och granska andra viktiga detaljer. Du kan till exempel se vilka appar som inte kan installeras, kontrollera versionen av en app med mera.

När användarna får en mobil enhet är en av de första uppgifterna att komma åt organisations-e-post och dokument. Med Intune kan du [skapa och distribuera e-postinställningar](https://docs.microsoft.com/intune/email-settings-configure) med hjälp av e-postappar som är förinstallerade på enheterna. 

I artikeln [Lägg till appar](https://docs.microsoft.com/intune/apps/apps-add) visas stegen för att lägga till, distribuera, övervaka, konfigurera och skydda appar på enheter i organisationen.

|||
|:-------|:-----|
|![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabbguide: Policyer för enhetsefterlevnad](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>Steg 6: Aktivera efterlevnad och villkorlig åtkomst

I föregående steg konfigurerar du din miljö och aktiverade Intune. Nu är du redo att skapa vissa principer med efterlevnad och villkorlig åtkomst.

Efterlevnad och villkorlig åtkomst är viktiga för att hantera enheter. [Efterlevnadsprinciper](https://docs.microsoft.com/intune/device-compliance-get-started) skapas för att skydda organisationens resurser. När du skapar en efterlevnadsprincip definierar du standarden eller "baslinjen" för vad en enhet måste ha. Du kan till exempel välja en acceptabel (eller oacceptabel) hotnivå, blockera jailbroken enheter, kräva en lösenordslängd med mera. Om dessa enheter inte uppfyller dina regler, vilket innebär att de inte är kompatibla, kan du blockera åtkomst till dina resurser.

Den här "blockeringen" introducerar [villkorlig åtkomst](https://docs.microsoft.com/intune/conditional-access). Om en enhet anses inte vara kompatibel kan du blockera åtkomst till e-post, SharePoint med mera.

Intune i [Azure-portalen](https://portal.azure.com) kan du skapa dessa principer och tillämpa dem på dina användare och enheter. Som bästa praxis, börja i liten skala och använda en stegvis metod. Skapa till exempel en iOS-princip som blockerar jailbroken-enheter. Tillämpa (kallas "tilldela" i Intune) principen till en pilot eller testgrupp. Efter inledande testning lägger du till fler användare i pilotgruppen. Med hjälp av en stegvis metod kan du få feedback från ett brett spektrum av användartyper.

Se [Komma igång med principer för enhetsefterlevnad](https://docs.microsoft.com/intune/device-compliance-get-started) och Lär dig mer om villkorlig åtkomst och [Intune?](https://docs.microsoft.com/intune/conditional-access)

## <a name="step-7-apply-features-and-settings"></a>Steg 7: Använda funktioner och inställningar

Dessa funktioner och inställningar anses ofta vara den "coola" delen av Intune, och är mycket kraftfulla. När du har tillämpat vissa efterlevnadsprinciper med villkorlig åtkomst är du redo att skapa **enhetsprofiler**.

Intune i [Azure-portalen](https://portal.azure.com) kan du skapa olika profiler baserat på din enhetsplattform - iOS, macOS, Android och Windows. Du kan till exempel:

- Använd slutpunktsskydd på Windows 10-enheter för att aktivera olika BitLocker-alternativ, inklusive kryptering.
- Använd funktionen Begränsade appar på iOS-enheter för att skapa en lista över godkända appar som kan installeras. Eller skapa en lista över förbjudna appar.
- Använd kioskinställningarna för att välja vilka appar som kan användas på Android-enheter som körs i kioskläge.
- Använd en Wi-Fi-anslutning och dess inställningar, inklusive säkerhetstypen, på enheter som kör macOS.

[Att använda funktioner och inställningar på dina enheter med hjälp av enhetsprofiler](https://docs.microsoft.com/intune/device-profiles) är ett bra ställe att läsa om profiler, se hur du skapar en profil med mera.

Kom ihåg, börja i liten skala och använd en stegvis metod. Tilldela profilen till en pilot eller testgrupp. Tilldela sedan profilen till fler pilotgrupper.

## <a name="step-8-get-to-know-the-other-features"></a>Steg 8: Lär känna de andra funktionerna

Intune är en kraftfull tjänst och innehåller många funktioner. Här är några andra uppgifter som du kan göra med Intune:

- Hantera programvara och uppdateringar på[Windows-enheters](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune) [devices](https://docs.microsoft.com/intune/windows-update-for-business-configure) & datorer och [iOS-enheter](https://docs.microsoft.com/intune/software-updates-ios)
- Aktivera [Microsoft Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) på dina Windows 10-enheter och använd efterlevnad och villkorlig åtkomst för att skydda åtkomsten till företagsresurser, till exempel SharePoint eller Exchange Online
- Använd [Lookout,](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector) [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)och andra mobila försvarshotpartner
- Lägga till en [partnercertifikatutfärdare för](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) att utfärda och förnya certifikat
- [Ge vägledning till dina slutanvändare](https://docs.microsoft.com/intune/end-user-educate) i företagsportalappen, hämta appar med mera
- Övervaka [appar](https://docs.microsoft.com/intune/apps-monitor) och [enhetsefterlevnad och konfigurationsprofiler](https://docs.microsoft.com/intune/compliance-policy-monitor)och mer telemetri med hjälp av granskningsloggarna. Du kan också ansluta till [Intune Data Warehouse](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) och använda Power BI för ännu fler rapporteringsbehov.


## <a name="identity-and-device-access-recommendations"></a>Rekommendationer för identitets- och enhetsåtkomst

Microsoft tillhandahåller en uppsättning rekommendationer för [identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md) för att säkerställa en säker och produktiv arbetsstyrka. För enhetsåtkomst använder du rekommendationerna och inställningarna i följande artiklar tillsammans med stegen i den här fasen:

- [Krav](identity-access-prerequisites.md)
- [Vanliga principer för identitets- och enhetsåtkomst](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Så här används Microsoft 365 Enterprise på Microsoft

Lär dig hur IT-experter på Microsoft [hanterar enheter med EMS](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Så här använder Contoso Microsoft 365 Enterprise

Se hur Contoso Corporation, ett fiktivt men representativt multinationellt företag, [distribuerade sin infrastruktur för hantering](contoso-mdm.md) av mobila enheter med Microsoft 365-molntjänster.

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nästa steg

[Exitkriterier för hantering av mobila enheter](mobility-infrastructure-exit-criteria.md)

