---
title: Vanliga identitets- och enhetsåtkomstprinciper – Microsoft 365 Enterprise | Microsoft Dokument
description: I artikeln beskrivs principerna för Microsoft-rekommendationer om hur du tillämpar principer och konfigurationer för identitets- och enhetsåtkomst.
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
ms.openlocfilehash: 272e8a76cdb3a1555f561bd56e63422f14394904
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808600"
---
# <a name="common-identity-and-device-access-policies"></a>Vanliga principer för identitets- och enhetsåtkomst
I den här artikeln beskrivs de vanliga rekommenderade principerna för att skydda åtkomsten till molntjänster, inklusive lokala program som publiceras med Azure AD Application Proxy. 

Den här vägledningen beskriver hur du distribuerar de rekommenderade principerna i en nyligen etablerad miljö. Genom att ställa in dessa principer i en separat labbmiljö kan du förstå och utvärdera de rekommenderade principerna innan du iscensätter distributionen till dina förproduktions- och produktionsmiljöer. Din nyligen etablerade miljö kan vara endast moln eller hybrid.  

## <a name="policy-set"></a>Principuppsättning 

Följande diagram illustrerar den rekommenderade uppsättningen principer. Den visar vilken nivå av skydd varje princip gäller för och om principerna gäller för datorer eller telefoner och surfplattor, eller båda kategorierna av enheter. Det anger också var dessa principer är konfigurerade.

![Vanliga principer för att konfigurera identitet s- och enhetsåtkomst](../media/Identity_device_access_policies_byplan.png)


I resten av den här artikeln beskrivs hur du konfigurerar dessa principer. 

Användning av multifaktorautentisering rekommenderas innan enheter inskrivningsenheter i Intune för att garantera att enheten är i den avsedda användarens ägo. Du måste också registrera enheter i Intune innan du tillämpar enhetsefterlevnadsprinciper.

Om du vill ge dig tid att utföra dessa uppgifter rekommenderar vi att du implementerar originalprinciper i den ordning som anges i den här tabellen. Mfa-politiken för känsligt och starkt reglerat skydd kan dock genomföras när som helst.


|Skyddsnivå|Politik|Mer information|
|:---------------|:-------|:----------------|
|**Originalplan**|[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](#require-mfa-based-on-sign-in-risk)| |
|        |[Blockera klienter som inte stöder modern autentisering](#block-clients-that-dont-support-modern-authentication)|Klienter som inte använder modern autentisering kan kringgå regler för villkorlig åtkomst, så det är viktigt att blockera dessa|
|        |[Högriskanvändare måste byta lösenord](#high-risk-users-must-change-password)|Tvingar användarna att ändra sitt lösenord när de loggar in om högriskaktivitet upptäcks för sitt konto|
|        |[Definiera principer för appskydd](#define-app-protection-policies)|En princip per plattform (iOS, Android, Windows).|
|        |[Kräv godkända appar](#require-approved-apps)|Tillämpar skydd för mobilappar för telefoner och surfplattor|
|        |[Definiera principer för enhetsefterlevnad](#define-device-compliance-policies)|En policy för varje plattform|
|        |[Kräv kompatibla datorer](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Upprätthåller intunehantering av datorer|
|**Känsliga**|[Kräv MFA när inloggningsrisken är *låg,* *medelhög* eller *hög*](#require-mfa-based-on-sign-in-risk)| |
|         |[Kräv kompatibla datorer *och* mobila enheter](#require-compliant-pcs-and-mobile-devices)|Tillämpar Intune-hantering för datorer och telefon/surfplattor|
|**Mycket reglerad**|[*Kräver alltid* MFA](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a>Tilldela principer till användare
Innan du konfigurerar principer identifierar du de Azure AD-grupper som du använder för varje skyddsnivå. Vanligtvis gäller originalskydd för alla i organisationen. En användare som ingår för både originalstöd och känsligt skydd kommer att ha alla baslinjeprinciper tillämpade plus känsliga principer. Skyddet är kumulativt och den mest restriktiva principen tillämpas. 

En rekommenderad metod är att skapa en Azure AD-grupp för uteslutning av villkorlig åtkomst. Lägg till den här gruppen i alla regler för villkorlig åtkomst under "Uteslut". Detta ger dig en metod för att ge åtkomst till en användare medan du felsöker åtkomstproblem. Detta rekommenderas endast som en tillfällig lösning. Övervaka den här gruppen för ändringar och se till att undantagsgruppen endast används som avsett. 

Följande diagram innehåller ett exempel på användartilldelning och undantag.

![Exempel på användartilldelning och undantag för MFA-regler](../media/identity-access-policies-assignment.png)

I illustrationen tilldelas "Topphemligt projekt X-team" en princip för villkorlig åtkomst som kräver MFA *alltid*. Var omdömesgill när du tillämpar högre skyddsnivåer för användarna. Medlemmar i den här projektgruppen måste tillhandahålla två former av autentisering varje gång de loggar in, även om de inte visar högreglerat innehåll.  

Alla Azure AD-grupper som skapats som en del av dessa rekommendationer måste skapas som Office 365-grupper. Detta är särskilt viktigt för distributionen av Azure Information Protection (AIP) när du skyddar dokument i SharePoint Online.

![Skärminspelning för att skapa Office 365-grupper](../media/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a>Kräv MFA baserat på inloggningsrisk
Innan du behöver MFA, använd först en MFA-registreringspolicy för identitetsskydd för att registrera användare för MFA. När användarna har registrerats kan du tillämpa MFA för inloggning. I [det nödvändiga arbetet](identity-access-prerequisites.md) ingår att registrera alla användare med MFA.

Så här skapar du en ny princip för villkorlig åtkomst: 

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorsstyrd åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

![Princip för certifikatutfärdare vid baslinje](../media/secure-email/CA-EXO-policy-1.png)

 I följande tabeller beskrivs principinställningarna för villkorlig åtkomst som ska implementeras för den här principen.

**Uppdrag**

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Användare och grupper|Inkluderar|Välj användare och grupper – Välj specifik säkerhetsgrupp som innehåller riktade användare|Börja med säkerhetsgrupp inklusive pilotanvändare|
||Utesluta|Undantagssäkerhetsgrupp; tjänstkonton (appidentiteter)|Medlemskap ändrat vid behov tillfälligt|
|Molnappar|Inkluderar|Välj de appar som du vill att den här regeln ska gälla för. Välj till exempel Office 365 Exchange Online||
|Villkor|Konfigurerad|Ja|Konfigurera specifika för din miljö och dina behov|
|Inloggningsrisk|Risknivå||Se vägledningen i följande tabell|

**Inloggningsrisk**

Tillämpa inställningarna baserat på den skyddsnivå du riktar dig till.

|Egenskap|Skyddsnivå|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Risknivå|Originalplan|Hög, medelhög|Kontrollera båda|
| |Känsliga|Hög, medelhög, låg|Kontrollera alla tre|
| |Mycket reglerad| |Lämna alla alternativ omarkerade för att alltid genomdriva MFA|

**Åtkomstkontroller**

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Bevilja|Bevilja åtkomst|Sant|Markerade|
||Kräv MFA|Sant|Check|
||Kräv att enheten markeras som kompatibel|Falska||
||Kräv hybrid Azure AD-ansluten enhet|Falska||
||Kräv godkänd klientapp|Falska||
||Kräv alla markerade kontroller|Sant|Markerade|

> [!NOTE]
> Var noga med att aktivera den här principen genom att välja **På**. Överväg också att använda [verktyget Tänk om](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) för att testa principen.



## <a name="block-clients-that-dont-support-modern-authentication"></a>Blockera klienter som inte stöder modern autentisering
1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorsstyrd åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

I följande tabeller beskrivs principinställningarna för villkorlig åtkomst som ska implementeras för den här principen.

**Uppdrag**

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Användare och grupper|Inkluderar|Välj användare och grupper – Välj specifik säkerhetsgrupp som innehåller riktade användare|Börja med säkerhetsgrupp inklusive pilotanvändare|
||Utesluta|Undantagssäkerhetsgrupp; tjänstkonton (appidentiteter)|Medlemskap ändrat vid behov tillfällig basis|
|Molnappar|Inkluderar|Välj de appar som du vill att den här regeln ska gälla för. Välj till exempel Office 365 Exchange Online||
|Villkor|Konfigurerad|Ja|Konfigurera klientappar|
|Klientappar|Konfigurerad|Ja|Mobilappar och skrivbordsklienter, Andra klienter (välj båda)|

**Åtkomstkontroller**

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Bevilja|Blockera åtkomst|Sant|Markerade|
||Kräv MFA|Falska||
||Kräv att enheten markeras som kompatibel|Falska||
||Kräv hybrid Azure AD-ansluten enhet|Falska||
||Kräv godkänd klientapp|Falska||
||Kräv alla markerade kontroller|Sant|Markerade|

> [!NOTE]
> Var noga med att aktivera den här principen genom att välja **På**. Överväg också att använda [verktyget Tänk om](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) för att testa principen.



## <a name="high-risk-users-must-change-password"></a>Högriskanvändare måste byta lösenord
För att säkerställa att alla högriskanvändares komprometterade konton tvingas utföra en lösenordsändring vid inloggandet måste du tillämpa följande princip.

Logga in på [Microsofthttps://portal.azure.com) Azure-portalen (](https://portal.azure.com/) med administratörsautentiseringsuppgifterna och navigera sedan till **Azure AD Identity Protection > användarriskprincip**.

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

**Recension:** ej tillämplig

> [!NOTE]
> Var noga med att aktivera den här principen genom att välja **På**. Överväg också att använda [verktyget Tänk om](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) för att testa principen

## <a name="define-app-protection-policies"></a>Definiera principer för appskydd
Appskyddsprinciper definierar vilka appar som är tillåtna och vilka åtgärder de kan vidta med organisationens data. Skapa Intune-appskyddsprinciper inifrån Azure-portalen. 

Skapa en princip för varje plattform:
- Ios
- Android
- Windows 10

Om du vill skapa en ny appskyddsprincip loggar du in på Microsoft Azure-portalen med administratörsautentiseringsuppgifterna och navigerar sedan till**appskyddsprinciper**för **klientappar** > . Välj **Skapa princip**.

Det finns små skillnader i appskyddsprincipalternativen mellan iOS och Android. Nedanstående policy är specifikt för Android. Använd detta som en guide för dina andra principer.

Den rekommenderade listan över appar innehåller följande:
- PowerPoint
- Excel
- Word
- Microsoft Teams
- Microsoft SharePoint
- Microsoft Visio Viewer
- OneDrive
- OneNote
- Outlook

I följande tabeller beskrivs de rekommenderade inställningarna:

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Omlokalisering av uppgifter|Förhindra Android-säkerhetskopiering|Ja|På iOS detta kommer särskilt att ropa iTunes och iCloud|
||Tillåt att appen överför data till andra appar|Principhanterade appar||
||Tillåt att appen tar emot data från andra appar|Principhanterade appar||
||Förhindra "Spara som"|Ja||
||Välj med vilka lagringtjänster företagsdata ska sparas|OneDrive för företag, SharePoint||
||Begränsa klippa ut, kopiera och klistra in med andra appar|Principhanterade appar med klistra in||
||Begränsa webbinnehåll som ska visas i den hanterade webbläsaren|Nej||
||Kryptera appdata|Ja|Välj iOS på iOS:N|
||Inaktivera appkryptering när enheten är aktiverad|Ja|Inaktivera den här inställningen för att undvika dubbel kryptering|
||Inaktivera synkronisering av kontakter|Nej||
||Inaktivera utskrift|Nej||
|Access|Kräv PIN-kod för åtkomst|Ja||
||Välj typ|Numeriska||
||Tillåt enkel PIN-kod|Nej||
||PIN-längd|6||
||Tillåt fingeravtryck i stället för PIN-kod|Ja||
||Inaktivera pinkod för appen när pinkoden för enheten hanteras|Ja||
||Kräv företagsautentiseringsuppgifter för åtkomst|Nej||
||Kontrollera åtkomstkravet på nytt efter (minuter)|30||
||Blockera skärmdump och Android-assistent|Nej|På iOS är detta inte ett tillgängligt alternativ|
|Säkerhetskrav för inloggning|Max PIN-försök|5|Återställ pin|
||Respitperiod offline|720|Blockera åtkomst|
||Offlineintervall (dagar) innan appdata rensas|90|Rensa data|
||Jailbroken/rotade enheter| |Rensa data|

Kom ihåg att välja "Skapa" när du är klar. Upprepa ovanstående steg och byt ut den valda plattformen (rullgardinsnedstreck) med iOS. Detta skapar två appprinciper, så när du har skapat principen, sedan tilldela grupper till principen och distribuera den.

Information om hur du redigerar principerna och tilldelar användarna dessa principer finns i [Så här skapar och tilldelar du principer för appskydd](https://docs.microsoft.com/intune/app-protection-policies). 

## <a name="require-approved-apps"></a>Kräv godkända appar
Så här kräver du godkända appar:

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorsstyrd åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

5. Ange ett principnamn och välj sedan de **användare och grupper** som du vill använda principen för.

6. Välj **Molnappar**.

7. Välj **Välj Appar**, välj önskade appar i listan **Cloud-appar.** Välj till exempel Office 365 Exchange Online. Välj **Välj** och **klar**.

8. Välj **Villkor**, välj **Enhetsplattformar**och välj sedan **Konfigurera**

9. Välj **Android** **Select device platforms**och **iOS**under **Inkludera**. Klicka på **Klar** och **Klar** igen

10. Välj **Bevilja** i avsnittet **Access-kontroller.**

11. Välj **Bevilja åtkomst**, välj **Kräv godkänd klientapp**. För flera kontroller väljer du **Kräv de markerade kontrollerna**och väljer sedan **Välj**. 

12. Välj **Skapa**.

## <a name="define-device-compliance-policies"></a>Definiera principer för enhetsefterlevnad

Enhetsefterlevnadsprinciper definierar de krav som enheter måste följa för att markeras som kompatibla. Skapa Intune-enhetsefterlevnadsprinciper inifrån Azure-portalen. 

Skapa en princip för varje plattform:
- Android
- Android företag
- Ios
- Macos
- Windows Phone 8.1
- Windows 8.1 och senare
- Windows 10 och senare

Om du vill skapa principer för enhetsefterlevnad loggar du in på Microsoft Azure-portalen med dina autentiseringsuppgifter och navigerar sedan till **Intune > Enhetsefterlevnad**. Välj **Skapa princip**.

Följande inställningar rekommenderas för Windows 10.

**Enhetshälsa: Utvärderingsregler för Windows Health Attestation Service**

|Egenskaper|Värden|Kommentar|
|:---------|:-----|:----|
|Kräv BitLocker|Kräver||
|Kräv att säker start aktiveras på enheten|Kräver||
|Kräv kodintegritet|Kräver||


**Enhetsegenskaper**

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Operativsystemversion|Alla|Inte konfigurerad||

För att alla ovanstående principer ska kunna betraktas som distribuerade måste de vara inriktade på användargrupper. Du kan göra detta genom att skapa principen (på Spara) eller senare genom att välja **Hantera distribution** i avsnittet **Princip** (samma nivå som Lägg till).

**Systemsäkerhet**

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Lösenord|Kräv ett lösenord för att låsa upp mobila enheter|Kräver||
||Enkla lösenord|Blockera||
||Typ av lösenord|Enheten särkod||
||Minsta lösenordslängd|6||
||Maximala minuter av inaktivitet innan lösenord krävs|15|Den här inställningen stöds för Android-versioner 4.0 och högre eller KNOX 4.0 och uppåt. För iOS-enheter stöds den för iOS 8.0 och högre|
||Förfallodatum för lösenord (dagar)|41||
||Antal tidigare lösenord för att förhindra återanvändning|5||
||Kräv lösenord när enheten returneras från inaktivt tillstånd (Mobil t.ex.|Kräver|Tillgänglig för Windows 10 och senare|
|Kryptering|Kryptering av datalagring på enheten|Kräver||
|Säkerhet för enheter|Brandvägg|Kräver||
||Antivirus|Kräver||
||Antispyware|Kräver|Den här inställningen kräver en antispionprogramlösning som är registrerad i Windows Security Center|
|Försvarare|Windows Defender Antimalware|Kräver||
||Windows Defender Antimalware minimiversion||Stöds endast för Windows 10-skrivbordet. Microsoft rekommenderar versioner högst fem efter från den senaste versionen|
||Windows Defender Antimalware signatur uppdaterad|Kräver||
||Skydd i realtid|Kräver|Stöds endast för Windows 10-skrivbordet|

**Microsoft Defender ATP**

|Type (Typ)|Egenskaper|Värden|Kommentar|
|:---|:---------|:-----|:----|
|Microsoft Defender Avancerade regler för skydd av hot|Kräv att enheten är på eller under maskinriskpoängen|Medium||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>Kräv kompatibla datorer (men inte kompatibla telefoner och surfplattor)
Innan du lägger till en princip för att kräva kompatibla datorer måste du registrera enheter för hantering i Intune. Användning av multifaktorautentisering rekommenderas innan enheter inskrivningsenheter i Intune för att garantera att enheten är i den avsedda användarens ägo. 

Så här kräver du kompatibla datorer:

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorsstyrd åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

5. Ange ett principnamn och välj sedan de **användare och grupper** som du vill använda principen för.

6. Välj **Molnappar**.

7. Välj **Välj Appar**, välj önskade appar i listan **Cloud-appar.** Välj till exempel Office 365 Exchange Online. Välj **Välj** och **klar**.

8. Om du vill kräva kompatibla datorer, men inte kompatibla telefoner och surfplattor, väljer du **Villkor** och **enhetsplattformar**. Välj **Välj enhetsplattformar** och välj **Windows** och **macOS**.

9. Välj **Bevilja** i avsnittet **Access-kontroller.**

10. Välj **Bevilja åtkomst**, välj **Kräv att enheten ska markeras som kompatibel**. För flera kontroller väljer du **Kräv alla markerade kontroller**och väljer sedan **Välj**. 

11. Välj **Skapa**.

Om ditt mål är att kräva kompatibla datorer *och* mobila enheter ska du inte välja plattformar. Detta upprätthåller efterlevnad för alla enheter. 

## <a name="require-compliant-pcs-and-mobile-devices"></a>Kräv kompatibla datorer *och* mobila enheter

Så här kräver du efterlevnad för alla enheter:

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorsstyrd åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

5. Ange ett principnamn och välj sedan de **användare och grupper** som du vill använda principen för.

6. Välj **Molnappar**.

7. Välj **Välj Appar**, välj önskade appar i listan **Cloud-appar.** Välj till exempel Office 365 Exchange Online. Välj **Välj** och **klar**.

8. Välj **Bevilja** i avsnittet **Access-kontroller.**

9. Välj **Bevilja åtkomst**, välj **Kräv att enheten ska markeras som kompatibel**. För flera kontroller väljer du **Kräv alla markerade kontroller**och väljer sedan **Välj**. 

10. Välj **Skapa**.

När du skapar den här principen ska du inte välja plattformar. Detta tvingar kompatibla enheter.


## <a name="next-steps"></a>Nästa steg

[Läs mer om principrekommendationer för att skydda e-post](secure-email-recommended-policies.md)
