---
title: Hantera ett komprometterat e-postkonto
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Lär dig hur du känner igen och hanterar ett komprometterat e-postkonto ned tillgängliga verktyg i Microsoft 365.
ms.openlocfilehash: adf1ded6fb88cc26e96840dc2a8bfe20300205dc
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588222"
---
# <a name="responding-to-a-compromised-email-account"></a>Hantera ett komprometterat e-postkonto

**Sammanfattning** Lär dig hur du känner igen och hanterar ett komprometterat e-postkonto i Microsoft 365.

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>Vad är ett komprometterat e-postkonto i Microsoft 365?

Åtkomst till Microsoft 365-postlådor, data och andra tjänster styrs genom användningen av autentiseringsuppgifter, t.ex. ett användarnamn och lösenord eller en PIN-kod. När någon annan än den avsedda användaren stjäl de här autentiseringsuppgifterna anses de stulna uppgifterna ha komprometterats. Angriparen kan använda dem för att logga in som den ursprungliga användaren och utföra illegala åtgärder.
Med hjälp av de stulna autentiseringsuppgifterna kan angriparen komma åt användarens Microsoft 365-postlåda, SharePoint-mappar eller filer i användarens OneDrive. En vanligt förekommande åtgärd är att angriparen skickar e-postmeddelanden i den ursprungliga användarens namn till mottagare både inom och utanför organisationen. När angriparen skickar data via e-post till externa mottagare kallas det för dataexfiltrering.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>Symptom hos ett komprometterat Microsoft-e-postkonto

Användarna kan lägga märka till och rapportera ovanliga aktiviteter i sina Microsoft 365-postlådor. Här är några vanliga tecken:

- Misstänkt aktivitet, t.ex. saknade eller borttagna e-postmeddelanden.

- Andra användare kan få e-postmeddelanden från det skadade kontot utan att motsvarande e-postmeddelanden finns i mappen **Skickat** hos avsändaren.

- Förekomsten av inkorgsregler som inte har skapats av den avsedda användaren eller administratören. Reglerna kan automatiskt vidarebefordra e-postmeddelanden till okända adresser eller flytta dem till någon av mapparna **Anteckningar**, **Skräppost** eller **RSS-prenumerationer**.

- Användarens visningsnamn kan ändras i den globala adresslistan.

- Användarens postlåda hindras från att skicka e-post.

- Mapparna Skickat och Borttaget i Microsoft Outlook eller Outlook på webben (tidigare Outlook Web App) innehåller vanliga meddelanden för hackade konton, t. ex. ”Jag är fast i London, skicka pengar”.

- Ovanliga profiländringar av t.ex. namn eller telefonnummer, eller uppdatering av postnumret.

- Ovanliga ändringar av autentiseringsuppgifter, till exempel flera ändringar av lösenordet krävs.

- Vidarebefordring av e-post har lagts till nyligen.

- En ovanlig signatur har nyligen lagts till, t.ex. en förfalskad banksignatur eller en signatur för ett receptbelagt läkemedel.

Om en användare rapporterar något av ovanstående symptom bör du utföra ytterligare utredningar. Säkerhets- och efterlevnadscenter för Microsoft 365 och Azure-portalen tillhandahåller verktyg som hjälper dig att undersöka aktiviteter hos ett användarkonto som du misstänker kan ha komprometterats.

- **Enhetliga granskningsloggar i Säkerhets- och efterlevnadscenter**: Granska alla aktiviteter för det misstänkta kontot genom att filtrera resultaten för datumintervallet från före den misstänkta aktiviteten till dagens datum. Filtrera inte på aktiviteterna under sökningen.

- **Granskningsloggar för administratörer i EAC**: I Exchange Online kan du använda administrationscentret för Exchange (EAC) för att söka efter och visa poster i granskningsloggen för administratörer. I granskningsloggen för administratörer registreras vissa åtgärder baserat på Exchange Online PowerShell-cmdletar, utförda av administratörer och användare som har tilldelats administratörsbehörigheter. Poster i granskningsloggen för administratörer innehåller information om vilken cmdlet som kördes, vilka parametrar som användes, vem som körde cmdleten och vilka objekt som påverkades.

- **Inloggningsloggar för Azure AD och andra riskrapporter på Azure AD-portalen**: Granska värdena i följande kolumner:

  - Granska IP-adress

  - inloggningsplatser

  - inloggningstider

  - lyckad eller misslyckad inloggning

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>Så kan du skydda och återställa e-postfunktionen till ett konto eller en postlåda i Microsoft 365 som misstänks ha komprometterats

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Även efter att du har återskapat åtkomsten till ditt konto kan angriparen ha lagt till bakdörrsposter som gör det möjligt för angripare att återta kontrollen av kontot.

Du måste utföra alla följande steg för att återta åtkomsten till ditt konto så snabbt som möjligt, för att se till att kaparen inte återtar kontrollen av ditt konto. De här åtgärderna hjälper dig att ta bort alla eventuella bakdörrsposter som kaparen kan ha lagt till på ditt konto. När du har utfört de här stegen rekommenderar vi att du kör en viruskontroll för att se till att datorn inte är komprometterad.

### <a name="step-1-reset-the-users-password"></a>Steg 1 Återställ användarens lösenord

> [!WARNING]
> Skicka inte det nya lösen ordet till den avsedda användaren via e-post, eftersom angriparen fortfarande har tillgång till postlådan.

1. Följ rutinerna för att återställa ett lösenord för Microsoft 365-appar för företag för någon annan i [Återställa lösenord för Microsoft 365-appar för företag](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

**Anmärkningar**:

- Kontrollera att lösenordet är starkt och att det innehåller gemener, versaler, minst en siffra och minst ett specialtecken.

- Återanvänd aldrig något av ditt senaste fem lösenord. Även om kravet för lösenordshistorik gör att du kan återanvända ett lösenord du använt nyligen bör du välja något som angriparen inte kan gissa.

- Om din lokala identitet är federerad med Microsoft 365 måste du ändra ditt lösenord lokalt och därefter informera administratören om skadan.

> [!TIP]
> Vi rekommenderar att du aktiverar multifaktorautentisering (MFA) för att förhindra kompromettering, i synnerhet för konton med administratörsbehörigheter.  Du kan läsa mer om MFA [här](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Steg 2 Ta bort misstänkta adresser för vidarebefordran av e-post

1. Öppna **administrationscentret för Microsoft 365 > Aktiva användare**.

2. Leta reda på användarkontot i fråga och visa **E-postinställningar**.

3. Under **Vidarebefordran av e-post** klickar du på **Redigera**.

4. Ta bort eventuella misstänkta vidarebefordringsadresser.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Steg 3 Inaktivera alla misstänkta inkorgsregler

1. Logga in i användarens postlåda med hjälp av Outlook på webben.

2. Klicka på kugghjulsikonen och klicka på **E-post**.

3. Klicka på **Regler för inkorgen och rensning** och granska reglerna.

4. Inaktivera eller ta bort misstänkta regler.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Steg 4 Tillåt att användaren skickar e-post

Om den misstänkt komprometterade postlådan har använts på ett otillåtet sätt för att skicka skräppost, är det sannolikt att postlådan har hindrats från att skicka e-post.

Om du vill tillåta att en postlåda skickar e-post igen följer du procedurerna i [Ta bort en användare från portalen med åtkomstbegränsade användare efter att användaren har skickat skräppost](removing-user-from-restricted-users-portal-after-spam.md).

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Steg 5 valfritt: Blockera inloggning på användarkontot

> [!IMPORTANT]
> Du kan blockera inloggning på det misstänkt komprometterade kontot tills du anser att det är säkert att aktivera åtkomst igen.

1. Gå till administrationscentret för Microsoft 365.

2. I administrationscentret för Microsoft 365 väljer du **Användare**.

3. Markera den anställda du vill blockera och välj sedan **Redigera** bredvid **Inloggningsstatus** i användarfönstret.

4. I fönstret **Inloggningsstatus** väljer du **Inloggning blockerad** och sedan **Spara**.

5. I det nedre vänstra navigeringsfönstret i administrationscentret expanderar du **Administratörscentra** och väljer **Exchange**.

6. I administrationscentret för Exchange går du till **Mottagare > Postlådor**.

7. Markera användaren och under **Mobila enheter** på sidan med användaregenskaper klickar du på **Inaktivera Exchange ActiveSync** och **Inaktivera OWA för enheter** och svarar **Ja** på båda.

8. Under **E-postanslutning** väljer du **Inaktivera** och svarar **Ja**.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Steg 6 valfritt: Ta bort det misstänkt komprometterade kontot från alla administrativa rollgrupper

> [!NOTE]
> Medlemskap i administratörsgruppen kan återställas när kontot har skyddats.

1. Logga in på administrationscentret för Microsoft 365 med ett globalt administratörskonto och öppna **Aktiva användare**.

2. Leta reda på det misstänkt komprometterade kontot och kontrollera manuellt om det finns några administrativa roller som tilldelats kontot.

3. Öppna **Säkerhets- och efterlevnadscenter**.

4. Klicka på **Behörigheter**.

5. Granska rollgrupperna manuellt för att se om det misstänkt komprometterade kontot är medlem i någon av dem.  Om så är fallet:

   a. Klicka på rollgruppen och klicka på **Redigera rollgrupp**.

   b. Klicka på **Välj medlemmar** och **Redigera** för att ta bort användaren från rollgruppen.

6. Öppna **administrationscentret för Exchange**.

7. Klicka på **Behörigheter**.

8. Granska rollgrupperna manuellt för att se om det misstänkt komprometterade kontot är medlem i någon av dem. Om så är fallet:

   a. Klicka på rollgruppen och klicka på **Redigera**.

   b. Klicka på avsnittet **Medlemmar** för att ta bort användaren från rollgruppen.

### <a name="step-7-optional-additional-precautionary-steps"></a>Steg 7 Valfritt: Ytterligare försiktighetsåtgärder

1. Var noga med att verifiera dina skickade meddelanden. Du kanske måste meddela personer i din kontaktlista att ditt konto har komprometterats. Angriparen kan ha bett om att få pengar genom så kallad förfalskning, t.ex. att du var fast i ett annat land och behövde pengar, eller så kan angriparen ha skickat ett virus för att kapa deras datorer.

2. Andra tjänster som har använt Exchange-kontot som ett alternativt e-postkonto kan ha komprometterats. Utför först de här stegen för din Microsoft 365-prenumeration och därefter för dina övriga konton.

3. Kontrollera att din kontaktinformation, t. ex. telefonnummer och adresser, är korrekt.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Skydda Microsoft 365 som en expert på cybersäkerhet

Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare.  Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.

- Uppgifter som ska utföras under de första 30 dagarna.  De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.

- Uppgifter som ska utföras inom 90 dagar. De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.

- Efter 90 dagar. De här förbättringarna uppnås under de första 90 dagarna.

## <a name="see-also"></a>Se även

- [Identifiera och reparera Outlook-regler och inmatningsattacker i anpassade formulär i Microsoft 365](detect-and-remediate-outlook-rules-forms-attack.md)

- [Klagomålscenter för brottslighet på Internet](https://www.ic3.gov/preventiontips.aspx)

- [Tillsynsmyndigheten för värdepapper – Bedrägerier genom nätfiske](https://www.sec.gov/investor/pubs/phishing.htm)

- Om du vill rapportera skräppost direkt till Microsoft och din administratör [använder du tillägget Rapportera meddelande](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
