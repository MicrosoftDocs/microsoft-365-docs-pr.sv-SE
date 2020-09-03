---
title: Vanliga principer för identitets-och enhets åtkomst – Microsoft 365 för företag | Microsoft-dok
description: Här beskrivs rekommenderade vanliga principer och konfigurationer för identitets-och enhets åtkomst.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
ms.openlocfilehash: 9819c161cc421117730cb4c58d1db06859125476
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332127"
---
# <a name="common-identity-and-device-access-policies"></a>Vanliga principer för identitets- och enhetsåtkomst
I den här artikeln beskrivs vanliga rekommenderade principer för att skydda åtkomst till moln tjänster, inklusive lokala program som publicerats med Azure AD Application Proxy. 

Den här vägledningen handlar om hur du distribuerar rekommenderade principer i en nyligen etablerad miljö. Genom att konfigurera dessa principer i en särskild laboratorie miljö kan du förstå och utvärdera rekommenderade principer innan du förbereder introduktionen till din produkt miljö. Den nyligen etablerade miljön kan endast vara moln-eller hybrid.  

## <a name="policy-set"></a>Princip uppsättning 

Följande diagram illustrerar den rekommenderade uppsättningen principer. Det visar vilken skydds nivå varje princip gäller för och om policyn gäller för datorer eller telefoner och surfplattor, eller båda enhets kategorierna. Det visar också var dessa principer är konfigurerade.

[ ![ Vanliga principer för att konfigurera åtkomst till identiteter och enheter](../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png) 
 [se en större version av bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

I resten av den här artikeln beskrivs hur du konfigurerar dessa principer. 

Om du använder multifaktorautentisering rekommenderas innan du registrerar enheter i Intune för att garantera att enheten är avsedd för den avsedda användaren. Du måste också registrera enheter i Intune innan du påtvingar dig principer för enhetskompatibilitet.

För att ge dig tid att utföra dessa uppgifter rekommenderar vi att du implementerar rikt linjerna i den ordning som anges i tabellen. MFA-principerna för känsligt och högreglerat skydd kan implementeras när som helst.


|Skydds nivå|Principerna|Mer information|
|:---------------|:-------|:----------------|
|**Grundläggande**|[Kräv MFA när en inloggnings risk är *mellan* eller *hög*](#require-mfa-based-on-sign-in-risk)| |
|        |[Blockera klienter som inte har stöd för modern autentisering](#block-clients-that-dont-support-modern-authentication)|Klienter som inte använder modern lösenordsautentisering kan kringgå regler för villkorsstyrd åtkomst, så det är viktigt att blockera dessa|
|        |[Användare med hög risk måste byta lösenord](#high-risk-users-must-change-password)|Tvingar användare att ändra sitt lösen ord när de loggar in om en högrisk aktivitet identifieras för sitt konto|
|        |[Tillämpa program data skydds policy](#apply-app-data-protection-policies)|En princip per plattform (iOS, Android, Windows). Intune App Protection policies (APP) är fördefinierade skydds uppsättningar, från nivå 1 till nivå 3.|
|        |[Kräv godkända appar och program skydd](#require-approved-apps-and-app-protection)|Aktiverar dataexekveringsskydd för telefoner och surfplattor|
|        |[Definiera principer för efterlevnadsprinciper](#define-device-compliance-policies)|En princip för varje plattform|
|        |[Kräv kompatibla PC-datorer](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Tillämpar Intune-hantering av datorer|
|**Känslig**|[Kräv MFA när en inloggnings risk är *låg*, *medium* eller *hög*](#require-mfa-based-on-sign-in-risk)| |
|         |[Kräv kompatibla datorer *och* mobila enheter](#require-compliant-pcs-and-mobile-devices)|Aktiverar Intune-hantering för datorer och telefoner/surfplattor|
|**Strikt reglerad**|[Kräv *alltid* MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Tilldela användare principer
Innan du konfigurerar principer ska du identifiera de Azure AD-grupper du använder för varje skydds nivå. Bas linje skydd gäller normalt för alla i organisationen. En användare som ingår i både bas linje och känsligt skydd får alla rikt linjer som tillämpas samt känsliga principer. Skyddet är kumulativt och den mest restriktiva principen tillämpas. 

Ett rekommenderat tillvägagångs sätt är att skapa en Azure AD-grupp för undantag för villkorlig åtkomst. Lägg till den här gruppen i alla regler för villkorsstyrd åtkomst under "exkludera". Det gör att du kan ge åtkomst till en användare när du felsöker åtkomst problem. Detta rekommenderas endast som en tillfällig lösning. Övervaka den här gruppen för ändringar och kontrol lera att exkluderings gruppen bara används som avsett. 

I följande diagram finns ett exempel på användar tilldelning och undantag.

![Exempel på användar tilldelning och undantag för MFA-regler](../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

I bilden är "Top Secret Project X team" tilldelad en princip för villkorsstyrd åtkomst som kräver MFA *alltid*. Bli judicious när du tillämpar högre skydds nivåer för användarna. Medlemmar i den här projekt gruppen måste kunna ge två typer av verifikation varje gång de loggar in, även om de inte visar mycket reglerad information.  

Alla Azure AD-grupper som skapas som en del av dessa rekommendationer måste skapas som Microsoft 365-grupper. Det är viktigt att du använder känslighets etiketter när du skyddar dokument i SharePoint Online.

![Skärmdump för att skapa Microsoft 365-grupper](../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>Kräv MFA baserat på inloggnings risker
Innan MFA krävs måste du först använda en identitets skydds registrerings princip för att registrera användare för MFA. När användare är registrerade kan du använda MFA för inloggning. För [kravet på arbete](identity-access-prerequisites.md) ingår att registrera alla användare med MFA.

Så här skapar du en ny princip för villkorsstyrd åtkomst: 

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina inloggnings uppgifter. När du har loggat in ser du Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **villkorsstyrd åtkomst**under avsnittet **säkerhet** .

4. Välj **ny princip**.

![Principer för rikt linjer](../media/secure-email/CA-EXO-policy-1.png)

 I följande tabell beskrivs princip inställningarna för villkorsstyrd åtkomst för den här principen.

**Tilldelningarnas**

|Type (Typ)|Fjärråtkomstsegenskaper|Värden|Kommentarer|
|:---|:---------|:-----|:----|
|Användare och grupper|Inkludera|Välj användare och grupper – Välj specifik säkerhets grupp som innehåller riktade användare|Starta med säkerhets grupp, inklusive pilot användare|
||Ta|Säkerhets grupp för undantag; tjänst konton (program identiteter)|Medlemskap ändrat vid tillfällig grund|
|Molnappar|Inkludera|Välj de program du vill att regeln ska gälla för. Välj till exempel Exchange Online||
|Situationer|Konfigurerade|Ja|Konfigurera specifika för din miljö och dina behov|
|Inloggnings risker|Risk nivå||Se anvisningarna i följande tabell|

**Inloggnings risker**

Tillämpa inställningarna utifrån den skydds nivå som du använder.

|Egenskap|Skydds nivå|Värden|Kommentarer|
|:---|:---------|:-----|:----|
|Risk nivå|Grundläggande|Hög, medium|Markera båda|
| |Känslig|Hög, medium, lågt|Markera alla tre|
| |Strikt reglerad| |Låt alla alternativ vara avmarkerade om du alltid vill använda MFA|

**Åtkomst kontroller**

|Type (Typ)|Fjärråtkomstsegenskaper|Värden|Kommentarer|
|:---|:---------|:-----|:----|
|Tilldelas|Bevilja åtkomst|Sant|Markerade|
||Kräv MFA|Sant|Check|
||Kräv att enheten markeras som kompatibel|Null||
||Kräv hybrid Azure AD-ansluten enhet|Null||
||Kräv godkänt klient program|Null||
||Kräv alla markerade kontroller|Sant|Markerade|

> [!NOTE]
> Aktivera den här principen genom att välja **på**. Överväg [också att använda verktyget för](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) att testa policyn.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Blockera klienter som inte har stöd för modern autentisering
1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina inloggnings uppgifter. När du har loggat in ser du Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **villkorsstyrd åtkomst**under avsnittet **säkerhet** .

4. Välj **ny princip**.

I följande tabell beskrivs princip inställningarna för villkorsstyrd åtkomst för den här principen.

**Tilldelningarnas**

|Type (Typ)|Fjärråtkomstsegenskaper|Värden|Kommentarer|
|:---|:---------|:-----|:----|
|Användare och grupper|Inkludera|Välj användare och grupper – Välj specifik säkerhets grupp som innehåller riktade användare|Starta med säkerhets grupp, inklusive pilot användare|
||Ta|Säkerhets grupp för undantag; tjänst konton (program identiteter)|Medlemskap ändrat på grund av tillfälliga behov|
|Molnappar|Inkludera|Välj de program du vill att regeln ska gälla för. Välj till exempel Exchange Online||
|Situationer|Konfigurerade|Ja|Konfigurera klient program|
|Klient program|Konfigurerade|Ja|Mobila appar och skriv bords klienter, andra klienter (Välj båda)|

**Åtkomst kontroller**

|Type (Typ)|Fjärråtkomstsegenskaper|Värden|Kommentarer|
|:---|:---------|:-----|:----|
|Tilldelas|Blockera åtkomst|Sant|Markerade|
||Kräv MFA|Null||
||Kräv att enheten markeras som kompatibel|Null||
||Kräv hybrid Azure AD-ansluten enhet|Null||
||Kräv godkänt klient program|Null||
||Kräv alla markerade kontroller|Sant|Markerade|

> [!NOTE]
> Aktivera den här principen genom att välja **på**. Överväg [också att använda verktyget för](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) att testa policyn.



## <a name="high-risk-users-must-change-password"></a>Användare med hög risk måste byta lösenord
För att säkerställa att alla högrisk användares komprometterade konton tvingas göra en ändring av lösen ord när de loggar in måste du tillämpa följande policy.

Logga in på [Microsoft Azure-portalen ( https://portal.azure.com) ](https://portal.azure.com/) med administratörs uppgifterna och navigera sedan till **Azure AD Identity Protection > User risk policy**.

**Tilldelningarnas**

|Type (Typ)|Fjärråtkomstsegenskaper|Värden|Kommentarer|
|:---|:---------|:-----|:----|
|Användare|Inkludera|Alla användare|Markerade|
||Ta|Inga||
|Situationer|Risk för användare|Högsta|Markerade|

**Kontroller**

| Type (Typ) | Fjärråtkomstsegenskaper | Värden                  | Kommentarer |
|:-----|:-----------|:------------------------|:------|
|      | Åtkomst     | Tillåt åtkomst            | Sant  |
|      | Åtkomst     | Kräv lösen ords ändring | Sant  |

**Granska:** ej tillämpligt

> [!NOTE]
> Aktivera den här principen genom att välja **på**. Överväg också att använda verktyget [What om](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) för att testa policyn

## <a name="apply-app-data-protection-policies"></a>Tillämpa program data skydds policy
App Protection policies (APP) definierar vilka appar som tillåts och vilka åtgärder de kan utföra med din organisations data. De val som är tillgängliga i appen gör det möjligt för organisationer att skräddarsy skyddet mot deras specifika behov. I vissa fall är det kanske inte uppenbart vilka princip inställningar som krävs för att implementera ett fullständigt scenario. För att hjälpa organisationer att prioritera en mobil klient Bryt punkts härdning har Microsoft infört taxonomi för programmets data skydds ramverk för iOS-och Android-mobilappar. 

PROGRAM data skydds ramverket är uppdelat i tre olika konfigurations nivåer, med varje nivå som bygger på föregående nivå: 

- **Företags grundläggande data skydd** (nivå 1) säkerställer att appar skyddas med en PIN-kod och krypterad och utför selektiv rensning. För Android-enheter verifierar den här nivån Android-enhetens attestering. Det här är en inmatnings nivå konfiguration som ger en liknande data skydds kontroll i Exchange Online Mailbox-principer och introducerar den och användar populationen till program. 
- **Förbättrat data skydd för företag** (nivå 2) introducerar mekanismer för att förhindra program data läckage och minimi krav på operativ system. Det här är den konfiguration som kan användas för de flesta mobila användare som vill komma åt arbets-eller skol data. 
- **Data skydd i företags kvalitet** (nivå 3) introducerar avancerade data skydds mekanismer, förbättrad PIN-konfiguration och försvar för mobil hot från appen. Denna konfiguration är önskvärt för användare som har till gång till högrisk data. 

Om du vill se de särskilda rekommendationerna för varje konfigurations nivå och de program som måste skyddas kan du granska [data skydds ramverket med hjälp av skydds principer för appar](https://docs.microsoft.com/mem/intune/apps/app-protection-framework). 

Genom att använda de principer som beskrivs i [identitets-och enhets åtkomst](microsoft-365-policies-configurations.md)kan du följa de grundläggande inställningarna för data skydd i nivå 2. De data skydds nivåer som är starkt prioriterade är nära nivå 3-inställningar för data skydd i Enterprise.

|Skydds nivå |Program skydds princip  |Mer information  |
|---------|---------|---------|
|Grundläggande     | [Nivå 2-förbättrat data skydd](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | De princip inställningar som tillämpas i nivå 2 inkluderar alla princip inställningar som rekommenderas för nivå 1 och lägger till eller uppdaterar princip inställningarna nedan för att implementera fler kontroller och en mer avancerad konfiguration än nivå 1.         |
|Känslig     | [Nivå 2-förbättrat data skydd](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | De princip inställningar som tillämpas i nivå 2 inkluderar alla princip inställningar som rekommenderas för nivå 1 och lägger till eller uppdaterar princip inställningarna nedan för att implementera fler kontroller och en mer avancerad konfiguration än nivå 1.        |
|Säkerhets regler     | [Nivå 3-skydda företags data](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | De princip inställningar som tillämpas i nivå 3 inkluderar alla princip inställningar som rekommenderas för nivå 1 och 2 och lägger till eller uppdaterar de här princip inställningarna för att implementera fler kontroller och en mer avancerad konfiguration än nivå 2.        |

Administratörer kan göra följande för att skapa en ny skydds princip för varje plattform (iOS och Android) i Microsoft slut punkts hanteraren med hjälp av inställningarna för data skydds ramverk:
1. Skapa principer manuellt genom att följa de steg som beskrivs [för att skapa och distribuera skydds principer för appar med Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies). 
2. Importera exempel på [princip konfigurations ramverket för Intune-appens skydd](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) med INTUNE-JSON- [skript](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Kräv godkända appar och program skydd
För att tvinga program skydds principerna som du använde i Intune måste du skapa en regel för villkorsstyrd åtkomst för att kräva godkända klient program och de villkor som ställts in i APPENs skydds principer. 

För att tvinga skydds principer för appar krävs en uppsättning principer som beskrivs i [Kräv program skydds princip för Cloud App Access med villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access). Dessa principer ingår i de rekommenderade uppsättningarna med identitets-och åtkomst principer.

Om du vill skapa en regel för villkorlig åtkomst som kräver godkända appar och APP Protection följer du anvisningarna i "steg 1: Konfigurera en princip för villkorsstyrd åtkomst i Azure AD för Microsoft 365" i [Scenario 1: Microsoft 365-program kräver godkända appar med skydds principer för appar](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), som tillåter Outlook för iOS och Android, men blockerar OAuth-kompatibla Exchange ActiveSync-klienter från att ansluta till Exchange Online.

   > [!NOTE]
   > Den här principen gör att mobila användare kan komma åt alla Office-slutpunkter med hjälp av tillämpliga appar.

Om du aktiverar mobil åtkomst till Exchange Online implementerar du [spärrar ActiveSync-klienter](secure-email-recommended-policies.md#block-activesync-clients)som hindrar Exchange ActiveSync-klienter att använda grundläggande åtkomst från anslutning till Exchange Online. Den här principen visas inte i bilden högst upp i den här artikeln. Det beskrivs och visas i [Policy rekommendationer för att skydda e-post](secure-email-recommended-policies.md).

 Dessa principer använder kontrollen för [godkända klienter](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) och kräver [program skydds princip](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Om du blockerar äldre klientautentisering för andra klient program på iOS-och Android-enheter ser du till att dessa klienter inte kan kringgå regler för villkorlig åtkomst. Om du följer anvisningarna i den här artikeln har du redan konfigurerat [blockera klienter som inte stöder modern](#block-clients-that-dont-support-modern-authentication).

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several conditional access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definiera principer för enhetskompatibilitet

Enhet – efterlevnadsprinciper definierar de krav som enheter måste uppfylla för att markeras som kompatibla. Skapa efterlevnadsprinciper för Intune-enheter från administrations centret för Microsoft Endpoint Manager.

Skapa en princip för varje plattform:
- Android-enhetens administratör
- Android Enterprise
- iOS/iPad
- macOS
- Windows Phone 8.1
- Windows 8,1 och senare
- Windows 10 och senare

Om du vill skapa principer för efterlevnadsprinciper loggar du in i [administrations centret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) med dina administratörs uppgifter och navigerar **sedan till principer för efterlevnadsprinciper**  >  **Compliance policies**  >  **Policies**. Välj **Skapa princip**.

Om principer för enhetskompatibilitet ska distribueras måste de kopplas till användar grupper. Du tilldelar en policy när du har skapat och sparat den. I Admin Center väljer du policy och sedan **uppgifter**. När du har valt de grupper som du vill ta emot principen för väljer du **Spara** för att spara grupp tilldelningen och distribuera policyn.

Stegvisa instruktioner om hur du skapar efterlevnadsprinciper i Intune finns i [skapa en policy för efterlevnad i Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) i Intune-dokumentationen.

Följande inställningar rekommenderas för Windows 10.

**Enhets hälsa: utvärderings regler för tjänsten Windows hälsoattestering**

|Fjärråtkomstsegenskaper|Värden|Kommentarer|
|:---------|:-----|:----|
|Kräv BitLocker|Nödvändig||
|Kräv säker start för att vara aktive rad på enheten|Nödvändig||
|Kräv kod integritet|Nödvändig||


**Enhets egenskaper**

|Type (Typ)|Fjärråtkomstsegenskaper|Värden|Kommentarer|
|:---|:---------|:-----|:----|
|Operativ system version|Alla|Inte konfigurerat||

**Systemsäkerhet**

|Type (Typ)|Fjärråtkomstsegenskaper|Värden|Kommentarer|
|:---|:---------|:-----|:----|
|Lösenord|Kräv lösen ord för att låsa upp mobila enheter|Nödvändig||
||Enkla lösen ord|Blockera||
||Lösen ords typ|Enhetens standard||
||Minsta längd på lösen ord|18.6||
||Maximalt antal minuter av inaktivitet innan lösen ord krävs|0,15|Den här inställningen stöds för Android-versionerna 4,0 och senare eller KNOX 4,0 och senare. För iOS-enheter stöds det för iOS 8,0 och senare|
||Lösen ordet upphör (dagar)|41||
||Antal tidigare lösen ord för att förhindra åter användning|T5||
||Kräv lösen ord när enheten återgår från Idle-tillstånd (mobil och Holographic)|Nödvändig|Tillgängligt för Windows 10 och senare|
|Kryptering|Kryptering av data lagring på enhet|Nödvändig||
|Enhets säkerhet|Vägg|Nödvändig||
||Viktigt|Nödvändig||
||Antispionprogram|Nödvändig|Den här inställningen kräver en lösning för antispionprogram som är registrerad i Windows säkerhets Center|
|Defender|Microsoft Defender antimalware|Nödvändig||
||Microsoft Defender antimalware-version||Stöds endast för Windows 10-skrivbordet. Microsoft rekommenderar att versions nummer inte överstiger fem gånger från den senaste versionen|
||Microsoft Defender antimalware-signatur uppdaterad|Nödvändig||
||Real tids skydd|Nödvändig|Stöds endast för Windows 10-skrivbordet|

**Microsoft Defender Avancerat skydd**

|Type (Typ)|Fjärråtkomstsegenskaper|Värden|Kommentarer|
|:---|:---------|:-----|:----|
|Microsoft Defender-regler för avancerat skydd|Kräv att enheten bevaras på eller under maskin risk poängen|Risk||


## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Kräv kompatibla datorer (men inte kompatibla telefoner och surfplattor)
Innan du lägger till en princip för att kräva kompatibla datorer måste du registrera enheter för hantering i Intune. Om du använder multifaktorautentisering rekommenderas innan du registrerar enheter i Intune för att garantera att enheten är avsedd för den avsedda användaren. 

Så här kräver du kompatibla datorer:

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina inloggnings uppgifter. När du har loggat in ser du Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **villkorsstyrd åtkomst**under avsnittet **säkerhet** .

4. Välj **ny princip**.

5. Ange ett princip namn och välj sedan de **användare och grupper** som du vill tillämpa principen för.

6. Välj **molnappar**.

7. Välj **Välj appar**och välj apparna i listan med **moln program** . Välj till exempel Exchange Online. Välj **Välj** och **klar**.

8. För att kräva kompatibla datorer, men inte kompatibla telefoner och surfplattor, Välj **villkor** och **enheternas plattformar**. Välj **Välj datorplattformar** och välj **Windows** och **MacOS**.

9. Välj **bevilja** i avsnittet **Access Controls** .

10. Välj **Tillåt åtkomst**, Välj **Kräv att enheten ska markeras som kompatibel**. För flera kontroller väljer du **Kräv alla markerade kontroller**och sedan **Välj**. 

11. Välj **Skapa**.

Om ditt syfte är att kräva kompatibla datorer *och* mobila enheter ska du inte välja plattformar. Detta framtvingar efterlevnad för alla enheter. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Kräv kompatibla datorer *och* mobila enheter

Så här kräver du efterlevnad för alla enheter:

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina inloggnings uppgifter. När du har loggat in ser du Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **villkorsstyrd åtkomst**under avsnittet **säkerhet** .

4. Välj **ny princip**.

5. Ange ett princip namn och välj sedan de **användare och grupper** som du vill tillämpa principen för.

6. Välj **molnappar**.

7. Välj **Välj appar**och välj apparna i listan med **moln program** . Välj till exempel Exchange Online. Välj **Välj** och **klar**.

8. Välj **bevilja** i avsnittet **Access Controls** .

9. Välj **Tillåt åtkomst**, Välj **Kräv att enheten ska markeras som kompatibel**. För flera kontroller väljer du **Kräv alla markerade kontroller**och sedan **Välj**. 

10. Välj **Skapa**.

Välj inte plattformar när du skapar den här principen. Detta tillämpar kompatibla enheter.


## <a name="next-steps"></a>Nästa steg

[Lär dig mer om policy rekommendationer för att skydda e-post](secure-email-recommended-policies.md)
