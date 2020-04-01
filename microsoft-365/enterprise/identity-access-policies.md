---
title: Vanliga principer för identitets- och enhetsåtkomst – Microsoft 365 Enterprise | Microsoft-dokument
description: I artikeln beskrivs principerna för Microsofts rekommendationer om hur du tillämpar principer och konfigurationer för identitets- och enhetsåtkomst.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
ms.openlocfilehash: 8b5cb7d8d8b16fea1c1bef44e477dfd43a79a3d8
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081332"
---
# <a name="common-identity-and-device-access-policies"></a>Vanliga principer för identitets- och enhetsåtkomst
I den här artikeln beskrivs de vanliga rekommenderade principerna för att skydda åtkomsten till molntjänster, inklusive lokala program som publiceras med Azure AD Application Proxy. 

I den här vägledningen beskrivs hur du distribuerar de rekommenderade principerna i en nyligen etablerad miljö. Genom att ställa in dessa principer i en separat labbmiljö kan du förstå och utvärdera de rekommenderade principerna innan du mellanlagrar distributionen till dina förproduktions- och produktionsmiljöer. Din nyligen etablerade miljö kan vara endast molnet eller hybrid.  

## <a name="policy-set"></a>Principuppsättning 

Följande diagram illustrerar den rekommenderade uppsättningen principer. Den visar vilken skyddsnivå varje princip gäller för och om principerna gäller för datorer eller telefoner och surfplattor, eller båda kategorierna av enheter. Den anger också var dessa principer är konfigurerade.

[![Vanliga principer för att konfigurera identitets- och enhetsåtkomst](../media/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)
[Se en större version av den här avbildningen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/Identity_device_access_policies_byplan.png)

I resten av den här artikeln beskrivs hur du konfigurerar dessa principer. 

Användning av multifaktorautentisering rekommenderas innan du registrerar enheter i Intune för att garantera att enheten är i den avsedda användarens ägo. Du måste också registrera enheter till Intune innan du tillämpar principer för enhetsefterlevnad.

För att ge dig tid att utföra dessa uppgifter rekommenderar vi att du implementerar originalprinciperna i den ordning som anges i den här tabellen. MFA:s politik för känsligt och starkt reglerat skydd kan dock genomföras när som helst.


|Skyddsnivå|Politik|Mer information|
|:---------------|:-------|:----------------|
|**Grundläggande**|[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](#require-mfa-based-on-sign-in-risk)| |
|        |[Blockera klienter som inte har stöd för modern autentisering](#block-clients-that-dont-support-modern-authentication)|Klienter som inte använder modern autentisering kan kringgå regler för villkorlig åtkomst, så det är viktigt att blockera dessa|
|        |[Högriskanvändare måste ändra lösenord](#high-risk-users-must-change-password)|Tvingar användare att ändra sitt lösenord när de loggar in om högriskaktivitet upptäcks för deras konto|
|        |[Tillämpa APP-dataskyddsprinciper](#apply-app-data-protection-policies)|En princip per plattform (iOS, Android, Windows). Intune App Protection Policies (APP) är fördefinierade uppsättningar av skydd, från nivå 1 till nivå 3.|
|        |[Kräv godkända appar och APP-skydd](#require-approved-apps-and-app-protection)|Tillämpar skydd av mobilappar för telefoner och surfplattor|
|        |[Definiera principer för enhetsefterlevnad](#define-device-compliance-policies)|En policy för varje plattform|
|        |[Kräv kompatibla PC-datorer](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Tillämpar Intune-hantering av datorer|
|**Känslig**|[Kräv MFA när inloggningsrisken är *låg,* *medelhög* eller *hög*](#require-mfa-based-on-sign-in-risk)| |
|         |[Kräv kompatibla datorer *och* mobila enheter](#require-compliant-pcs-and-mobile-devices)|Tillämpar Intune-hantering för datorer och telefon/surfplattor|
|**Strikt reglerad**|[*Kräver alltid* MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Tilldela principer till användare
Innan du konfigurerar principer identifierar du de Azure AD-grupper som du använder för varje skyddsnivå. Vanligtvis gäller baslinjeskyddet för alla i organisationen. En användare som ingår för både baslinje och känsligt skydd kommer att ha alla grundläggande principer tillämpas plus känsliga principer. Skyddet är kumulativt och den mest restriktiva principen tillämpas. 

En rekommenderad metod är att skapa en Azure AD-grupp för uteslutning av villkorlig åtkomst. Lägg till den här gruppen i alla dina regler för villkorlig åtkomst under "Uteslut". Detta ger dig en metod för att ge åtkomst till en användare medan du felsöker åtkomstproblem. Detta rekommenderas endast som en tillfällig lösning. Övervaka den här gruppen för ändringar och se till att uteslutningsgruppen endast används som avsett. 

Följande diagram är ett exempel på användartilldelning och undantag.

![Exempel på användartilldelning och undantag för MFA-regler](../media/identity-access-policies-assignment.png)

I bilden tilldelas "Topphemligt projekt X-team" en princip för villkorlig åtkomst som kräver MFA *alltid*. Var omdömesgill när du tillämpar högre skyddsnivåer för användare. Medlemmar i den här projektgruppen måste tillhandahålla två former av autentisering varje gång de loggar in, även om de inte visar starkt reglerat innehåll.  

Alla Azure AD-grupper som skapas som en del av dessa rekommendationer måste skapas som Office 365-grupper. Detta är särskilt viktigt för distributionen av Azure Information Protection (AIP) när du skyddar dokument i SharePoint Online.

![Skärminsamling för att skapa Office 365-grupper](../media/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>Kräv MFA baserat på inloggningsrisk
Innan du kräver MFA använder du först en registreringsprincip för MFA-registrering för identitetsskydd för att registrera användare för MFA. När användare har registrerats kan du framtvinga MFA för inloggning. I [det nödvändiga arbetet](identity-access-prerequisites.md) ingår att registrera alla användare med MFA.

Så här skapar du en ny princip för villkorlig åtkomst: 

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorlig åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

![Princip för certifikatutfärdarbaslinje](../media/secure-email/CA-EXO-policy-1.png)

 I följande tabeller beskrivs de principinställningar för villkorlig åtkomst som ska implementeras för den här principen.

**Uppdrag**

|Type (Typ)|Egenskaper|Värden|Anteckningar|
|:---|:---------|:-----|:----|
|Användare och grupper|Inkluderar|Välj användare och grupper – Välj specifik säkerhetsgrupp som innehåller riktade användare|Börja med säkerhetsgrupp inklusive pilotanvändare|
||Utesluta|Säkerhetsgrupp för undantag. tjänstkonton (appidentiteter)|Medlemskapet ändras vid behov tillfälligt|
|Molnappar|Inkluderar|Markera de appar som du vill att den här regeln ska gälla för. Välj till exempel Office 365 Exchange Online||
|Villkor|Konfigurerad|Ja|Konfigurera specifik för din miljö och dina behov|
|Inanmälningsrisk|Risknivå||Se vägledningen i följande tabell|

**Inanmälningsrisk**

Använd inställningarna baserat på den skyddsnivå du riktar dig till.

|Egenskap|Skyddsnivå|Värden|Anteckningar|
|:---|:---------|:-----|:----|
|Risknivå|Grundläggande|Hög, medelhög|Kontrollera båda|
| |Känslig|Hög, medelhög, låg|Kontrollera alla tre|
| |Strikt reglerad| |Lämna alla alternativ avmarkerade för att alltid framtvinga MFA|

**Åtkomstkontroller**

|Type (Typ)|Egenskaper|Värden|Anteckningar|
|:---|:---------|:-----|:----|
|Bevilja|Bevilja åtkomst|Sant|Markerade|
||Kräv MFA|Sant|Check|
||Kräv att enheten ska markeras som kompatibel|Falska||
||Kräv hybrid Azure AD-ansluten enhet|Falska||
||Kräv godkänd klientapp|Falska||
||Kräv alla markerade kontroller|Sant|Markerade|

> [!NOTE]
> Var noga med att aktivera den här principen genom att välja **På**. Överväg också att använda verktyget [Vad händer om](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) för att testa principen.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Blockera klienter som inte har stöd för modern autentisering
1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorlig åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

I följande tabeller beskrivs de principinställningar för villkorlig åtkomst som ska implementeras för den här principen.

**Uppdrag**

|Type (Typ)|Egenskaper|Värden|Anteckningar|
|:---|:---------|:-----|:----|
|Användare och grupper|Inkluderar|Välj användare och grupper – Välj specifik säkerhetsgrupp som innehåller riktade användare|Börja med säkerhetsgrupp inklusive pilotanvändare|
||Utesluta|Säkerhetsgrupp för undantag. tjänstkonton (appidentiteter)|Medlemskap ändrat vid behov tillfälligt|
|Molnappar|Inkluderar|Markera de appar som du vill att den här regeln ska gälla för. Välj till exempel Office 365 Exchange Online||
|Villkor|Konfigurerad|Ja|Konfigurera klientappar|
|Klientappar|Konfigurerad|Ja|Mobilappar och skrivbordsklienter, Andra klienter (välj båda)|

**Åtkomstkontroller**

|Type (Typ)|Egenskaper|Värden|Anteckningar|
|:---|:---------|:-----|:----|
|Bevilja|Blockera åtkomst|Sant|Markerade|
||Kräv MFA|Falska||
||Kräv att enheten ska markeras som kompatibel|Falska||
||Kräv hybrid Azure AD-ansluten enhet|Falska||
||Kräv godkänd klientapp|Falska||
||Kräv alla markerade kontroller|Sant|Markerade|

> [!NOTE]
> Var noga med att aktivera den här principen genom att välja **På**. Överväg också att använda verktyget [Vad händer om](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) för att testa principen.



## <a name="high-risk-users-must-change-password"></a>Högriskanvändare måste ändra lösenord
Om du vill vara säkra på att alla högriskanvändares komprometterade konton tvingas utföra en lösenordsändring när du loggar in måste du tillämpa följande princip.

Logga in på [Microsofthttps://portal.azure.com) Azure-portalen (](https://portal.azure.com/) med administratörsbehörighet och navigera sedan till **Azure AD Identity Protection > Användarriskprincip**.

**Uppdrag**

|Type (Typ)|Egenskaper|Värden|Anteckningar|
|:---|:---------|:-----|:----|
|Användare|Inkluderar|Alla användare|Markerade|
||Utesluta|Ingen||
|Villkor|Användarrisk|Högsta|Markerade|

**Kontroller**

| Type (Typ) | Egenskaper | Värden                  | Anteckningar |
|:-----|:-----------|:------------------------|:------|
|      | Åtkomst     | Tillåt åtkomst            | Sant  |
|      | Åtkomst     | Kräv lösenordsändring | Sant  |

**Recension:** ej tillämpligt

> [!NOTE]
> Var noga med att aktivera den här principen genom att välja **På**. Överväg också att använda verktyget [Vad händer om](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) för att testa principen

## <a name="apply-app-data-protection-policies"></a>Tillämpa APP-dataskyddsprinciper
App Protection Policies (APP) definierar vilka appar som är tillåtna och vilka åtgärder de kan vidta med organisationens data. De val som finns i APP gör det möjligt för organisationer att skräddarsy skyddet efter sina specifika behov. För vissa kanske det inte är uppenbart vilka principinställningar som krävs för att implementera ett fullständigt scenario. För att hjälpa organisationer att prioritera härdning av mobila klientslutpunkter har Microsoft infört taxonomi för sitt APP-dataskyddsramverk för iOS- och Android-hantering av mobilappar. 

APP-ramverket för dataskydd är indelat i tre olika konfigurationsnivåer, där varje nivå bygger ut den tidigare nivån: 

- **Enterprise basic data protection** (Nivå 1) säkerställer att appar skyddas med en PIN-kod och krypteras och utför selektiva rensningsåtgärder. För Android-enheter validerar den här nivån Android-enhetsintyg. Det här är en konfiguration på ingångsnivå som ger liknande dataskyddskontroll i Exchange Online-postlådeprinciper och introducerar IT och användarpopulationen till APP. 
- **Enterprise enhanced data protection** (Level 2) introducerar APP-mekanismer för förebyggande av dataläckage och minimikrav på operativsystem. Det här är den konfiguration som gäller för de flesta mobila användare som använder arbets- eller skoldata. 
- **Enterprise high data protection** (Level 3) introducerar avancerade dataskyddsmekanismer, förbättrad PIN-konfiguration och APP Mobile Threat Defense. Den här konfigurationen är önskvärd för användare som har åtkomst till högriskdata. 

Om du vill se de specifika rekommendationerna för varje konfigurationsnivå och de minsta appar som måste skyddas läser du [Ramverket för dataskydd med hjälp av appskyddsprinciper](https://docs.microsoft.com/mem/intune/apps/app-protection-framework). 

Med hjälp av principerna i konfigurationer för [identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md)mappas nivåerna För baslinje och känsligt skydd noggrant med de förbättrade dataskyddsinställningarna på nivå 2. Den starkt reglerade skyddsnivån mappar nära till nivå 3-inställningarna för högt dataskydd på nivå 3.

|Skyddsnivå |Princip för appskydd  |Mer information  |
|---------|---------|---------|
|Grundläggande     | [Förbättrad dataskydd på nivå 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | De principinställningar som tillämpas på nivå 2 innehåller alla principinställningar som rekommenderas för nivå 1 och lägger bara till eller uppdaterar de principinställningar som finns under för att implementera fler kontroller och en mer sofistikerad konfiguration än nivå 1.         |
|Känslig     | [Förbättrad dataskydd på nivå 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | De principinställningar som tillämpas på nivå 2 innehåller alla principinställningar som rekommenderas för nivå 1 och lägger bara till eller uppdaterar de principinställningar som finns under för att implementera fler kontroller och en mer sofistikerad konfiguration än nivå 1.        |
|Mycket reglerad     | [Företagsnivå 3 högt dataskydd](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | De principinställningar som tillämpas på nivå 3 innehåller alla principinställningar som rekommenderas för nivå 1 och 2 och lägger bara till eller uppdaterar de principinställningar som finns under för att implementera fler kontroller och en mer sofistikerad konfiguration än nivå 2.        |

Om du vill skapa en ny appskyddsprincip för varje plattform (iOS och Android) i Microsoft Endpoint Manager med hjälp av raminställningarna för dataskydd kan administratörer:
1. Skapa principer manuellt genom att följa stegen i [Hur du skapar och distribuerar appskyddsprinciper med Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies). 
2. Importera exempelramverket [För konfiguration av appskyddsprincip JSON](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) med [Intunes PowerShell-skript](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-approved-apps-and-app-protection"></a>Kräv godkända appar och APP-skydd
Om du vill tillämpa appskyddsprinciperna som du har tillämpat i Intune måste du skapa en regel för villkorlig åtkomst för att kräva godkända klientappar och villkoren i APP-skyddsprinciperna. 

Tillämpa APP-skyddsprinciper kräver en uppsättning principer som beskrivs i i [Kräv appskyddsprincip för molnappåtkomst med villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access). Dessa principer ingår alla i den här rekommenderade uppsättningen konfigurationsprinciper för identitet och åtkomst.

Om du vill skapa regeln för villkorlig åtkomst som kräver godkända appar och APP-skydd följer du "Steg 1: Konfigurera en Azure AD-princip för villkorlig åtkomst för Office 365" i [Scenario 1: Office 365-appar kräver godkända appar med appskyddsprinciper](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), vilket tillåter Outlook för iOS och Android, men blockerar OAuth-kompatibla Exchange ActiveSync-klienter från att ansluta till Exchange Online.

   > [!NOTE]
   > Den här principen säkerställer att mobila användare kan komma åt alla Office-slutpunkter med hjälp av tillämpliga appar.

Om du aktiverar mobil åtkomst till Exchange Online implementerar du [Block ActiveSync-klienter](secure-email-recommended-policies.md#block-activesync-clients), vilket förhindrar att Exchange ActiveSync-klienter utnyttjar grundläggande autentisering från att ansluta till Exchange Online. Den här principen visas inte i bilden högst upp i den här artikeln. Det beskrivs och avbildas i [Policy rekommendationer för att säkra e-post](secure-email-recommended-policies.md).

 Dessa principer utnyttjar bidragskontrollerna [Kräv godkänd klientapp](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) och [Kräv appskyddsprincip](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

Slutligen säkerställer blockering av äldre autentisering för andra klientappar på iOS- och Android-enheter att dessa klienter inte kan kringgå regler för villkorlig åtkomst. Om du följer vägledningen i den här artikeln har du redan konfigurerat [Blockera klienter som inte stöder modern autentisering](#block-clients-that-dont-support-modern-authentication).

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several conditional access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Office 365" in [Scenario 1: Office 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>Definiera principer för enhetsefterlevnad

Principer för enhetsefterlevnad definierar de krav som enheter måste följa för att markeras som kompatibla. Skapa Intune-principer för enhetsefterlevnad från administrationscentret för Microsoft Slutpunktshanteraren.

Skapa en princip för varje plattform:
- Administratör för Android-enheter
- Android Företag
- iOS/iPadOS
- Macos
- Windows Phone 8.1
- Windows 8.1 och senare
- Windows 10 och senare

Om du vill skapa principer för enhetsefterlevnad loggar du in på [Administrationscentret för Microsoft Slutpunktshanteraren](https://go.microsoft.com/fwlink/?linkid=2109431) med dina administratörsautentiseringsuppgifter och navigerar sedan till principer för**Policies** > **enhetsefterlevnad** > . **Devices** Välj **Skapa princip**.

För att enhetsefterlevnadsprinciper ska kunna distribueras måste de tilldelas användargrupper. Du tilldelar en princip när du har skapat och sparat den. Välj principen i administrationscentret och välj sedan **Tilldelningar**. När du har valt de grupper som du vill ta emot principen väljer du **Spara** för att spara grupptilldelningen och distribuera principen.

Stegvis vägledning om hur du skapar efterlevnadsprinciper i Intune finns [i Skapa en efterlevnadsprincip i Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) i Intune-dokumentationen.

Följande inställningar rekommenderas för Windows 10.

**Enhetens hälsa: Utvärderingsregler för Windows Health Attestation Service**

|Egenskaper|Värden|Anteckningar|
|:---------|:-----|:----|
|Kräv BitLocker|Kräver||
|Kräv säker start aktiveras på enheten|Kräver||
|Kräv kodintegritet|Kräver||


**Enhetsegenskaper**

|Type (Typ)|Egenskaper|Värden|Anteckningar|
|:---|:---------|:-----|:----|
|Version av operativsystemet|Alla|Inte konfigurerad||

**Systemsäkerhet**

|Type (Typ)|Egenskaper|Värden|Anteckningar|
|:---|:---------|:-----|:----|
|Lösenord|Kräv ett lösenord för att låsa upp mobila enheter|Kräver||
||Enkla lösenord|Blockera||
||Typ av lösenord|Standard för enhet||
||Minsta lösenordslängd|6||
||Maximalt antal minuter inaktivitet innan lösenord krävs|15|Den här inställningen stöds för Android-versioner 4.0 och högre eller KNOX 4.0 och högre. För iOS-enheter stöds det för iOS 8.0 och högre|
||Lösenordsförfall (dagar)|41||
||Antal tidigare lösenord för att förhindra återanvändning|5||
||Kräv lösenord när enheten återgår från inaktivt tillstånd (mobil och holografisk)|Kräver|Tillgängligt för Windows 10 och senare|
|Kryptering|Kryptering av datalagring på enheten|Kräver||
|Enhetssäkerhet|Brandvägg|Kräver||
||Antivirus|Kräver||
||Antispyware|Kräver|Den här inställningen kräver en antispionlösning som är registrerad hos Windows Security Center|
|Försvarare|Microsoft Defender Antimalware|Kräver||
||Microsoft Defender Antimalware minsta version||Stöds endast för Windows 10-skrivbordet. Microsoft rekommenderar versioner högst fem bakom från den senaste versionen|
||Microsoft Defender Antimalware signatur uppdaterad|Kräver||
||Realtidsskydd|Kräver|Stöds endast för Windows 10-skrivbordet|

**Microsoft Defender ATP**

|Type (Typ)|Egenskaper|Värden|Anteckningar|
|:---|:---------|:-----|:----|
|Regler för avancerat hotskydd i Microsoft Defender|Kräv att enheten är på eller under maskinriskpoängen|Medium||


## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Kräv kompatibla datorer (men inte kompatibla telefoner och surfplattor)
Innan du lägger till en princip för att kräva kompatibla datorer måste du registrera enheter för hantering i Intune. Användning av multifaktorautentisering rekommenderas innan du registrerar enheter i Intune för att garantera att enheten är i den avsedda användarens ägo. 

Så här kräver du kompatibla datorer:

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorlig åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

5. Ange ett principnamn och välj sedan de **användare och grupper** som du vill tillämpa principen för.

6. Välj **Molnappar**.

7. Välj **Välj appar**, välj önskade appar i listan **Molnappar.** Välj till exempel Office 365 Exchange Online. Välj **Välj** och **gjort**.

8. Om du vill kräva kompatibla datorer, men inte kompatibla telefoner och surfplattor, väljer du **Villkor** och **Enhetsplattformar**. Välj **Välj enhetsplattformar** och välj **Windows** och **macOS**.

9. Välj **Bevilja** i avsnittet **Access-kontroller.**

10. Välj **Bevilja åtkomst**, välj **Kräv enhet som ska markeras som kompatibel**. För flera kontroller väljer du **Kräv alla markerade kontroller**och väljer sedan **Markera**. 

11. Välj **Skapa**.

Om ditt mål är att kräva kompatibla datorer *och* mobila enheter ska du inte välja plattformar. Detta upprätthåller efterlevnad för alla enheter. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Kräv kompatibla datorer *och* mobila enheter

Så här kräver du efterlevnad för alla enheter:

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorlig åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

5. Ange ett principnamn och välj sedan de **användare och grupper** som du vill tillämpa principen för.

6. Välj **Molnappar**.

7. Välj **Välj appar**, välj önskade appar i listan **Molnappar.** Välj till exempel Office 365 Exchange Online. Välj **Välj** och **gjort**.

8. Välj **Bevilja** i avsnittet **Access-kontroller.**

9. Välj **Bevilja åtkomst**, välj **Kräv enhet som ska markeras som kompatibel**. För flera kontroller väljer du **Kräv alla markerade kontroller**och väljer sedan **Markera**. 

10. Välj **Skapa**.

När du skapar den här principen ska du inte välja plattformar. Detta upprätthåller kompatibla enheter.


## <a name="next-steps"></a>Nästa steg

[Läs mer om principrekommendationer för att skydda e-post](secure-email-recommended-policies.md)
