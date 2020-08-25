---
title: Hantera ett komprometterat e-postkonto
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Lär dig hur du känner igen och hanterar ett komprometterat e-postkonto ned tillgängliga verktyg i Microsoft 365.
ms.openlocfilehash: cfd20b0d5e6e13343346761b9b909a333b9a6ff5
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827523"
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

Följ anvisningarna i [återställa ett företags lösen ord för någon](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).

> [!IMPORTANT]
>
> - Skicka inte det nya lösen ordet till den avsedda användaren via e-post, eftersom angriparen fortfarande har tillgång till postlådan.
>
> - Kontrollera att lösenordet är starkt och att det innehåller gemener, versaler, minst en siffra och minst ett specialtecken.
>
> - Återanvänd aldrig något av ditt senaste fem lösenord. Även om kravet för lösenordshistorik gör att du kan återanvända ett lösenord du använt nyligen bör du välja något som angriparen inte kan gissa.
>
> - Om din lokala identitet är federerad med Microsoft 365 måste du ändra ditt lösenord lokalt och därefter informera administratören om skadan.
>
> - Se till att uppdatera applösenord. Applösenord återkallas inte automatiskt när ett lösenord för ett användarkonto återställs. Användaren ska ta bort befintliga applösenord och skapa nya. För instruktioner, se [Skapa och ta bort applösenord från sidan Ytterligare säkerhetsverifiering](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).
>
> - Vi rekommenderar att du aktiverar multifaktorautentisering (MFA) för att förhindra kompromettering, i synnerhet för konton med administratörsbehörigheter. Mer information om MFA finns i [Konfigurera multifaktorautentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Steg 2 Ta bort misstänkta adresser för vidarebefordran av e-post

1. Öppna Administrationscenter för Microsoft 365 på <https://admin.microsoft.com>

2. Gå till **användare** \> **aktiva användare**. Hitta användarkontot i fråga och välj användare (rad) utan att markera kryssrutan.

3. I den information som visas, väljer du fliken **e-post**.

4. Om värdet i avsnittet **vidarebefordra e-post** **tillämpas**klickar du på **hantera e-postvidarebefordran**. I **Hantera e vidarebefordran** flyout som visas klart **vidarebefordra all e-post som skickas till denna brevlåda**, och klicka sedan på **Spara ändringar**.

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

1. Öppna Administrationscenter för Microsoft 365 och gå till **användare** \> **aktiva användare**.

2. Hitta och välj användarkontot, klicka på ![More-ikonen](../../media/ITPro-EAC-MoreOptionsIcon.png) och välj sedan **Redigera inloggningsstatus**.

3. I fönstret **Blockera inloggning** väljer du **Blockera användaren från att logga in**, och klickar sedan på **Spara ändringar**.

4. Öppna Exchange administrations centret (EAC) på <admin.protection.outlook.com/ecp/> och gå till **Mottagare> Mailboxes**.

5. Hitta och välj markera användaren. Gör följande steg i detaljrutan:

   - Gör följande steg i avsnittet **Telefon- och röstfunktioner**:

     - Välj **inaktivera Exchange ActiveSync** och klicka sedan på **Ja** i varningen som visas.
     - Välj **inaktivera OWA för enheter** och klicka sedan på **Ja** i varningen som visas.

   - Gå till avsnittet **e-postanslutning** för Outlook på webben. Klicka på **inaktivera** och klicka sedan på **Ja** i varningen som visas.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Steg 6 valfritt: Ta bort det misstänkt komprometterade kontot från alla administrativa rollgrupper

> [!NOTE]
> Medlemskap i administratörsgruppen kan återställas när kontot har skyddats.

1. Logga in med ett globalt administratörskonto:

2. Gör följande steg i Administrationscenter för Microsoft 365:

   1. Gå till **användare** \> **aktiva användare**.
   2. Hitta och välj användarkontot, klicka på ![More-ikonen](../../media/ITPro-EAC-MoreOptionsIcon.png) och välj sedan **Hantera roller**.
   3. Ta bort alla administrativa roller som tilldelas kontot. När du är klar klickar du på **Spara ändringar**.

3. I säkerhets & Compliance Center på <https://protection.office.com>gör du så här:

   Välj **behörigheter**. Välj varje roll grupp i listan och leta efter användar kontot i **Medlemmar** delen av den information som visas. Om rollgruppen innehåller användarkontot gör du följande steg:

   a. Klicka på **redigera** bredvid **medlemmar**.
   b. I **redigerar väljer du medlemmar** utfällbar som visas klickar du på **redigera**.
   c. I **Välj medlemmar** utfällbar som visas väljer du användar konto och klickar sedan på **ta bort**. När du är klar klickar du på **klar** **Spara**och **sedan**stänga.

4. Gör följande steg i EAC på <admin.protection.outlook.com/ecp/>:

   Välj **behörigheter**, markera varje roll grupp manuellt och kontrol lera sedan användar kontona i avsnittet **medlemmar** i informations fönstret.  Om rollgruppen innehåller användarkontot gör du följande steg:

   a. Välj roll gruppen och klicka på **redigera** ![redigera ikonen](../../media/ITPro-EAC-EditIcon.png).
   b. Gå till avsnittet **medlem**, Välj användar kontot och klicka sedan på **ta bort** ![ta bort ikonen](../../media/ITPro-EAC-RemoveIcon.gif). Klicka på **Spara** när du är klar.

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
