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
ms.openlocfilehash: 772c4c5785115995593a4946bfbac49312ad15f3
ms.sourcegitcommit: 8e8230ceab480a5f1506e31de828f04f5590a350
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2020
ms.locfileid: "42959234"
---
# <a name="common-identity-and-device-access-policies"></a>Vanliga principer för identitets- och enhetsåtkomst
I den här artikeln beskrivs de vanliga rekommenderade principerna för att skydda åtkomsten till molntjänster, inklusive lokala program som publiceras med Azure AD Application Proxy. 

I den här vägledningen beskrivs hur du distribuerar de rekommenderade principerna i en nyligen etablerad miljö. Genom att ställa in dessa principer i en separat labbmiljö kan du förstå och utvärdera de rekommenderade principerna innan du mellanlagrar distributionen till dina förproduktions- och produktionsmiljöer. Din nyligen etablerade miljö kan vara endast molnet eller hybrid.  

## <a name="policy-set"></a>Principuppsättning 

Följande diagram illustrerar den rekommenderade uppsättningen principer. Den visar vilken skyddsnivå varje princip gäller för och om principerna gäller för datorer eller telefoner och surfplattor, eller båda kategorierna av enheter. Den anger också var dessa principer är konfigurerade.

![Vanliga principer för att konfigurera identitets- och enhetsåtkomst](../media/Identity_device_access_policies_byplan.png)


I resten av den här artikeln beskrivs hur du konfigurerar dessa principer. 

Användning av multifaktorautentisering rekommenderas innan du registrerar enheter i Intune för att garantera att enheten är i den avsedda användarens ägo. Du måste också registrera enheter till Intune innan du tillämpar principer för enhetsefterlevnad.

För att ge dig tid att utföra dessa uppgifter rekommenderar vi att du implementerar originalprinciperna i den ordning som anges i den här tabellen. MFA:s politik för känsligt och starkt reglerat skydd kan dock genomföras när som helst.


|Skyddsnivå|Politik|Mer information|
|:---------------|:-------|:----------------|
|**Baslinje**|[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](#require-mfa-based-on-sign-in-risk)| |
|        |[Blockera klienter som inte stöder modern autentisering](#block-clients-that-dont-support-modern-authentication)|Klienter som inte använder modern autentisering kan kringgå regler för villkorlig åtkomst, så det är viktigt att blockera dessa|
|        |[Högriskanvändare måste ändra lösenord](#high-risk-users-must-change-password)|Tvingar användare att ändra sitt lösenord när de loggar in om högriskaktivitet upptäcks för deras konto|
|        |[Definiera principer för appskydd](#define-app-protection-policies)|En princip per plattform (iOS, Android, Windows).|
|        |[Kräv appar som stöder Intune-appskyddsprinciper](#require-apps-that-support-intune-app-protection-policies)|Tillämpar skydd av mobilappar för telefoner och surfplattor|
|        |[Definiera principer för enhetsefterlevnad](#define-device-compliance-policies)|En policy för varje plattform|
|        |[Kräv kompatibla datorer](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Tillämpar Intune-hantering av datorer|
|**Känslig**|[Kräv MFA när inloggningsrisken är *låg,* *medelhög* eller *hög*](#require-mfa-based-on-sign-in-risk)| |
|         |[Kräv kompatibla datorer *och* mobila enheter](#require-compliant-pcs-and-mobile-devices)|Tillämpar Intune-hantering för datorer och telefon/surfplattor|
|**Mycket reglerad**|[*Kräver alltid* MFA](#require-mfa-based-on-sign-in-risk)|
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

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Användare och grupper|Inkluderar|Välj användare och grupper – Välj specifik säkerhetsgrupp som innehåller riktade användare|Börja med säkerhetsgrupp inklusive pilotanvändare|
||Utesluta|Säkerhetsgrupp för undantag. tjänstkonton (appidentiteter)|Medlemskapet ändras vid behov tillfälligt|
|Molnappar|Inkluderar|Markera de appar som du vill att den här regeln ska gälla för. Välj till exempel Office 365 Exchange Online||
|Villkor|Konfigurerad|Ja|Konfigurera specifik för din miljö och dina behov|
|Inanmälningsrisk|Risknivå||Se vägledningen i följande tabell|

**Inanmälningsrisk**

Använd inställningarna baserat på den skyddsnivå du riktar dig till.

|Egenskap|Skyddsnivå|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Risknivå|Baslinje|Hög, medelhög|Kontrollera båda|
| |Känslig|Hög, medelhög, låg|Kontrollera alla tre|
| |Mycket reglerad| |Lämna alla alternativ avmarkerade för att alltid framtvinga MFA|

**Åtkomstkontroller**

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Bevilja|Bevilja åtkomst|Sant|Markerade|
||Kräv MFA|Sant|Check|
||Kräv att enheten ska markeras som kompatibel|Falska||
||Kräv hybrid Azure AD-ansluten enhet|Falska||
||Kräv godkänd klientapp|Falska||
||Kräv alla markerade kontroller|Sant|Markerade|

> [!NOTE]
> Var noga med att aktivera den här principen genom att välja **På**. Överväg också att använda verktyget [Vad händer om](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) för att testa principen.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Blockera klienter som inte stöder modern autentisering
1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorlig åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

I följande tabeller beskrivs de principinställningar för villkorlig åtkomst som ska implementeras för den här principen.

**Uppdrag**

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Användare och grupper|Inkluderar|Välj användare och grupper – Välj specifik säkerhetsgrupp som innehåller riktade användare|Börja med säkerhetsgrupp inklusive pilotanvändare|
||Utesluta|Säkerhetsgrupp för undantag. tjänstkonton (appidentiteter)|Medlemskap ändrat vid behov tillfälligt|
|Molnappar|Inkluderar|Markera de appar som du vill att den här regeln ska gälla för. Välj till exempel Office 365 Exchange Online||
|Villkor|Konfigurerad|Ja|Konfigurera klientappar|
|Klientappar|Konfigurerad|Ja|Mobilappar och skrivbordsklienter, Andra klienter (välj båda)|

**Åtkomstkontroller**

|Type (Typ)|Egenskaper|Värden|Kommentar|
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

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Användare|Inkluderar|Alla användare|Markerade|
||Utesluta|Ingen||
|Villkor|Användarrisk|High|Markerade|

**Kontroller**

| Type (Typ) | Egenskaper | Värden                  | Kommentar |
|:-----|:-----------|:------------------------|:------|
|      | Access     | Tillåt åtkomst            | Sant  |
|      | Access     | Kräv lösenordsändring | Sant  |

**Recension:** ej tillämpligt

> [!NOTE]
> Var noga med att aktivera den här principen genom att välja **På**. Överväg också att använda verktyget [Vad händer om](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) för att testa principen

## <a name="define-app-protection-policies"></a>Definiera principer för appskydd
App-principer (APP) definierar vilka appar som är tillåtna och vilka åtgärder de kan vidta med organisationens data. De val som finns i APP gör det möjligt för organisationer att skräddarsy skyddet efter sina specifika behov. För vissa kanske det inte är uppenbart vilka principinställningar som krävs för att implementera ett fullständigt scenario. För att hjälpa organisationer att prioritera härdning av mobila klientslutpunkter har Microsoft infört taxonomi för sitt APP-dataskyddsramverk för iOS- och Android-hantering av mobilappar. 

APP-ramverket för dataskydd är indelat i tre olika konfigurationsnivåer, där varje nivå bygger ut den tidigare nivån: 

- Enterprise grundläggande dataskydd säkerställer att appar skyddas med en PIN-kod och krypteras och utför selektiva rensningsåtgärder. För Android-enheter validerar den här nivån Android-enhetsintyg. Det här är en konfiguration på ingångsnivå som ger liknande dataskyddskontroll i Exchange Online-postlådeprinciper och introducerar IT och användarpopulationen till APP. 
- Enterprise förbättrad dataskydd introducerar APP dataläckage förebyggande mekanismer och minimikrav os. Det här är den konfiguration som gäller för de flesta mobila användare som använder arbets- eller skoldata. 
- Enterprise high data protection introducerar avancerade dataskyddsmekanismer, förbättrad PIN-konfiguration och APP Mobile Threat Defense. Den här konfigurationen är önskvärd för användare som har åtkomst till högriskdata. 

Om du vill se de specifika rekommendationerna för varje konfigurationsnivå och de minsta appar som måste skyddas läser du [Ramverket för dataskydd med hjälp av appskyddsprinciper](https://docs.microsoft.com/mem/intune/apps/app-protection-framework). 

Med hjälp av principerna i konfigurationer för [identitets- och enhetsåtkomst](microsoft-365-policies-configurations.md)mappas nivåerna För baslinje och känsligt skydd noggrant med de förbättrade dataskyddsinställningarna på nivå 2. Den starkt reglerade skyddsnivån mappar nära till nivå 3-inställningarna för högt dataskydd på nivå 3.

|Skyddsnivå |Princip för appskydd  |Mer information  |
|---------|---------|---------|
|Baslinje     | [Förbättrad dataskydd på nivå 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | De principinställningar som tillämpas på nivå 2 innehåller alla principinställningar som rekommenderas för nivå 1 och lägger bara till eller uppdaterar de principinställningar som finns under för att implementera fler kontroller och en mer sofistikerad konfiguration än nivå 1.         |
|Känslig     | [Förbättrad dataskydd på nivå 2](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)        | De principinställningar som tillämpas på nivå 2 innehåller alla principinställningar som rekommenderas för nivå 1 och lägger bara till eller uppdaterar de principinställningar som finns under för att implementera fler kontroller och en mer sofistikerad konfiguration än nivå 1.        |
|Mycket reglerad     | [Företagsnivå 3 högt dataskydd](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)        | De principinställningar som tillämpas på nivå 3 innehåller alla principinställningar som rekommenderas för nivå 1 och 2 och lägger bara till eller uppdaterar de principinställningar som finns under för att implementera fler kontroller och en mer sofistikerad konfiguration än nivå 2.        |

Om du vill skapa en ny appskyddsprincip för varje plattform (iOS och Android) i Microsoft Endpoint Manager med hjälp av raminställningarna för dataskydd kan administratörer:
1. Skapa principer manuellt genom att följa stegen i [Hur du skapar och distribuerar appskyddsprinciper med Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/app-protection-policies).
2. Importera exempelramverket [För konfiguration av appskyddsprincip JSON](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) med [Intunes PowerShell-skript](https://github.com/microsoftgraph/powershell-intune-samples).

## <a name="require-apps-that-support-intune-app-protection-policies"></a>Kräv appar som stöder Intune-appskyddsprinciper
Med villkorlig åtkomst kan organisationer begränsa åtkomsten till godkända (moderna autentiseringskompatibla) iOS- och Android-klientappar med Intune-appskyddsprinciper som tillämpas på dem. Flera principer för villkorlig åtkomst krävs, där varje princip riktar sig till alla potentiella användare. Information om hur du skapar dessa principer finns i [Kräv appskyddsprincip för molnappåtkomst med villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Följ "Steg 1: Konfigurera en Azure AD-princip för villkorlig åtkomst för Office 365" i [Scenario 1: Office 365-appar kräver godkända appar med appskyddsprinciper](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), vilket gör att Outlook för iOS och Android, men blockerar OAuth-kompatibla Exchange ActiveSync-klienter från att ansluta till Exchange Online.

   > [!NOTE]
   > Den här principen säkerställer att mobila användare kan komma åt alla Office-slutpunkter med hjälp av tillämpliga appar.

2. Om du aktiverar mobil åtkomst till Exchange Online implementerar du [Block ActiveSync-klienter] (secure-email-recommended-policies.md#block-activesync-clients), vilket förhindrar att Exchange ActiveSync-klienter utnyttjar grundläggande autentisering från att ansluta till Exchange Online.

   Ovanstående principer utnyttjar bidragskontrollerna [Kräv godkänd klientapp](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) och [Kräv appskyddsprincip](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Inaktivera äldre autentisering för andra klientappar på iOS- och Android-enheter. Mer information finns i [Blockera klienter som inte stöder modern autentisering](#block-clients-that-dont-support-modern-authentication).

## <a name="define-device-compliance-policies"></a>Definiera principer för enhetsefterlevnad

Principer för enhetsefterlevnad definierar de krav som enheter måste följa för att markeras som kompatibla. Skapa Intune-principer för enhetsefterlevnad från Azure-portalen. 

Skapa en princip för varje plattform:
- Android
- Android-företag
- Ios
- Macos
- Windows Phone 8.1
- Windows 8.1 och senare
- Windows 10 och senare

Om du vill skapa principer för enhetsefterlevnad loggar du in på Microsoft Azure-portalen med dina administrationsuppgifter och navigerar sedan till **Intune > Enhetsefterlevnad**. Välj **Skapa princip**.

Följande inställningar rekommenderas för Windows 10.

**Enhetens hälsa: Utvärderingsregler för Windows Health Attestation Service**

|Egenskaper|Värden|Kommentar|
|:---------|:-----|:----|
|Kräv BitLocker|Kräver||
|Kräv säker start aktiveras på enheten|Kräver||
|Kräv kodintegritet|Kräver||


**Enhetsegenskaper**

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Version av operativsystemet|Alla|Inte konfigurerad||

För att alla ovanstående principer ska anses distribuerade måste de vara inriktade på användargrupper. Du kan göra detta genom att skapa principen (på Spara) eller senare genom att välja **Hantera distribution** i avsnittet **Princip** (samma nivå som Lägg till).

**Systemsäkerhet**

|Type (Typ)|Egenskaper|Värden|Kommentar|
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
|Försvarare|Windows Defender Antimalware|Kräver||
||Minsta version för Windows Defender Antimalware||Stöds endast för Windows 10-skrivbordet. Microsoft rekommenderar versioner högst fem bakom från den senaste versionen|
||Windows Defender Antimalware-signatur uppdaterad|Kräver||
||Realtidsskydd|Kräver|Stöds endast för Windows 10-skrivbordet|

**Microsoft Defender ATP**

|Type (Typ)|Egenskaper|Värden|Kommentar|
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
