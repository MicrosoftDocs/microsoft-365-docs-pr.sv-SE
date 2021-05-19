---
title: Identifiera och åtgärda medgivandesstipend
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Lär dig hur du känner igen och åtgärdar de medgivande som medgivande förser oss med attack Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e5675a7a83bb62bae80f20e8e7c86fde38599ec6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538309"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Identifiera och åtgärda medgivandesstipend

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Sammanfattning**  Lär dig hur du känner igen och åtgärdar de medgivande som medgivande förser oss med angrepp i Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Vad är det för attack mot medgivande som krävs för att Office 365?

I en attack med medgivande från medgivande skapar attackeraren ett Azure-registrerat program som begär åtkomst till data, till exempel kontaktinformation, e-post eller dokument. Då luras en slutanvändare att bevilja åtkomst till sina data via en nätfiskeattack eller genom att mata in kod från en betrodd webbplats. När programmet med programmet har beviljats medgivande har det åtkomst på kontonivå till data utan att ett organisationskonto behövs. Normal åtgärdssteg, t.ex. återställning av lösenord för konton som bryter mot konton eller krav på multifaktorautentisering (MFA) på konton, är inte gällande mot den här typen av attack, eftersom det är program från tredje part som inte ingår i organisationen.

Dessa attacker utnyttjar en interaktionsmodell som antas vara entitet som anropar informationen är automation och inte en person.

> [!IMPORTANT]
> Misstänker du att du har problem med att få medgivande från en app, just nu? Microsoft Cloud App Security (MCAS) finns verktyg för att identifiera, undersöka och åtgärda OAuth-apparna. Den här MCAS-artikeln innehåller en självstudiekurs som beskriver hur du [undersöker riskfyllda OAuth-appar.](/cloud-app-security/investigate-risky-oauth) Du kan också ange [OAuth-appprinciper](/cloud-app-security/app-permission-policy) för att undersöka begärda behörigheter för appar, vilka användare som ska auktorisera dessa appar och godkänna eller förbjuda dessa behörighetsförfrågningar.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Hur ser en undantagsmedgivande bevilja attack ut i Office 365?

Du måste söka i **granskningsloggen** för att hitta tecken, även kallade indikatorer på kompromettering (IOC) för den här attacken. För organisationer med många Azure-registrerade program och en stor användarbas är det bäst att granska organisationens medgivande varje vecka.

### <a name="steps-for-finding-signs-of-this-attack"></a>Steg för att hitta tecken på den här attacken

1. Öppna **Säkerhets- & Efterlevnadscenter** på <https://protection.office.com> .

2. Gå till **Sök** och välj **Granskningsloggsökning**.

3. Sök (alla aktiviteter och alla användare) och ange startdatum och slutdatum om det behövs och klicka sedan på **Sök.**

4. Klicka **på Filtrera** resultat och ange godkännande till programmet i **fältet** Aktivitet.

5. Klicka på resultatet om du vill se information om aktiviteten. Klicka **på Mer information** för att visa information om aktiviteten. Kontrollera om IsAdminContent är inställt på Sant.

> [!NOTE]
>
> Det kan ta från 30 minuter till 24 timmar innan motsvarande granskningsloggpost visas i sökresultatet efter att en händelse inträffat.
>
> Hur lång tid som en granskningspost behålls och är sökbar i granskningsloggen beror på din Microsoft 365-prenumeration, och specifikt vilken typ av licens som tilldelas till en viss användare. Mer information finns i [Granskningslogg](../../compliance/search-the-audit-log-in-security-and-compliance.md).
>
> Om det här värdet är sant anger det att någon med global administratörsåtkomst kan ha beviljat bred åtkomst till data. Om detta är oväntat, vidta åtgärder för [att bekräfta en attack](#how-to-confirm-an-attack).

## <a name="how-to-confirm-an-attack"></a>Så här bekräftar du ett angrepp

Om du har en eller flera instanser av IOCs som anges ovan, måste du undersöka ytterligare för att bekräfta att attacken inträffade. Du kan använda någon av följande tre metoder för att bekräfta attacken:

- Inventeringsprogram och deras behörigheter via Azure Active Directory. Den här metoden är noggrann, men du kan bara kontrollera en användare i taget vilket kan ta lång tid om du har många användare att kontrollera.

- Inventeringsprogram och deras behörigheter med hjälp av PowerShell. Det här är den snabbaste och mest genomgående metoden med minsta möjliga overhead.

- Be användarna kontrollera appar och behörigheter individuellt och rapportera resultaten till administratörerna för åtgärd.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventeringsprogram med åtkomst i din organisation

Du kan göra detta för dina användare med Azure Active Directory-portalen eller PowerShell eller ha användarna individuellt räkna upp deras programåtkomst.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Steg för att använda Azure Active Directory portalen

Du kan slå upp de program som en enskild användare har beviljats behörighet till via [Azure Active Directory portalen.](https://portal.azure.com/)

1. Logga in på Azure Portal med administrativa rättigheter.

2. Markera Azure Active Directory blad.

3. Välj **Användare**.

4. Markera den användare som du vill granska.

5. Välj **Program.**

Då visas de appar som tilldelats användaren och vilka behörigheter programmen har.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Steg för att användarna ska räkna upp sin programåtkomst

Be användarna gå till https://myapps.microsoft.com och granska sin egen programåtkomst där. De bör kunna se alla appar som har åtkomst, visa information om dem (inklusive omfattningen av åtkomst) och kunna återkalla behörigheter till misstänkta eller misstänkta appar.

### <a name="steps-for-doing-this-with-powershell"></a>Anvisningar för hur du gör det med PowerShell

Det enklaste sättet att verifiera Attack med medgivande bevilja är att köra [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), som då tar bort alla OAuth-medgivandetillägg och OAuth-appar för alla användare i ditt innehavare i en .csv fil.

#### <a name="pre-requisites"></a>Förutsättningar

- Azure AD PowerShell-biblioteket installerat.

- Globala administratörsrättigheter för klientorganisationen som skriptet körs mot.

- Lokal administratör på datorn som kör skripten från.

> [!IMPORTANT]
> Vi ***rekommenderar att*** du kräver multifaktorautentisering på ditt administratörskonto. Det här skriptet har stöd för MFA-autentisering.

1. Logga in på den dator som du kör skriptet från med lokala administratörsrättigheter.

2. Ladda ned eller [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) skriptet GitHub en mapp som du ska köra skriptet från. Det här blir samma mapp som utdatafilen "permissions.csv" skrivs till.

3. Öppna en PowerShell-instans som administratör och öppna den mapp där du sparade skriptet.

4. Anslut till katalogen med hjälp [Anslut-AzureAD-cmdleten.](/powershell/module/azuread/connect-azuread)

5. Kör det här PowerShell-kommandot:

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Skriptet skapar en fil med namnet Permissions.csv. Följ de här anvisningarna om du vill söka efter beviljad behörighet för program:

1. I kolumnen ConsentType (kolumn G) söker du efter värdet "AllPrinciples". Med behörigheten AllPrincipals kan klientprogrammet få åtkomst till innehållet från alla i innehavare. Inbyggda Microsoft 365-program behöver den här behörigheten för att fungera korrekt. Alla program som inte är Microsoft-program med den här behörigheten bör granskas noggrant.

2. I kolumnen Behörighet (kolumn F) granskar du behörigheterna som varje delegerat program har till innehållet. Leta efter behörigheterna "Läsa" och "Skriva" eller "*. Alla" och granska dessa noggrant eftersom de kanske inte är lämpliga.

3. Granska de specifika användare som har beviljats medgivande. Om användare med hög profil eller hög effekt beviljas olämpliga medgivanden bör du undersöka ytterligare.

4. Leta efter appar som verkar misstänkta i kolumnen ClientDisplayName (kolumn C). Appar med felstavade namn, supert bland namn eller hackares namn bör granskas noggrant.

## <a name="determine-the-scope-of-the-attack"></a>Fastställa attackens omfattning

När du har slutfört inventeringen av programåtkomst granskar du **granskningsloggen** för att fastställa den fullständiga omfattningen av intrånget. Sök efter de användare som påverkas, de tidsramar som det aktuella programmet hade åtkomst till din organisation och vilka behörigheter appen hade. Du kan söka i **granskningsloggen** [i Säkerhets- & Kompatibilitetscenter.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

> [!IMPORTANT]
> [Granskning av](../../compliance/enable-mailbox-auditing.md) [postlådor och aktivitet för administratörer och användare måste](../../compliance/turn-audit-log-search-on-or-off.md) ha aktiverats före attacken för att du ska kunna få den här informationen.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Så här stoppar och åtgärdar du en attack med medgivande för medgivande

När du har identifierat ett program med behörighet att skapa behörigheter kan du ta bort den åtkomsten på flera olika sätt.

- Du kan återkalla programmets behörighet i den Azure Active Directory portalen genom att:

  - Navigera till den aktuella användaren i **Azure Active Directory i användarbladet.**

  - Välj **Program.**

  - Välj programmet med en begäran om ett program för inbjudna.

  - Klicka **på Ta** bort i detaljgranskningen nedåt.

- Du kan återkalla OAuth-medgivande till PowerShell genom att följa stegen i [Remove-AzureADOAuth2PermissionGrant.](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)

- Du kan återkalla rolltilldelningen i Tjänstapp med PowerShell genom att följa stegen i [Remove-AzureADServiceAppRoleAssignment.](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)

- Du kan också inaktivera inloggningen för det aktuella kontot helt och hållet, vilket i sin tur inaktiverar appåtkomst till data i det kontot. Det här är förstås inte perfekt för slutanvändarens produktivitet, men om du arbetar för att begränsa påverkan snabbt kan det vara en gångbar åtgärd på kort sikt.

- Du kan inaktivera integrerade program under ditt innehavare. Det här är ett avsevärt steg som inaktiverar möjligheten för slutanvändare att bevilja medgivande i hela klientorganisationen. Det förhindrar att användarna oavsiktligt beviljar åtkomst till ett skadligt program. Det här rekommenderas inte särskilt mycket eftersom det allvarligt försämrar dina användares förmåga att vara produktiv med program från tredje part. Det kan du göra genom att följa anvisningarna i [Aktivera eller inaktivera integrerade appar.](../../admin/misc/user-consent.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Skydda Microsoft 365 som en expert på cybersäkerhet

Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare. Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.

- Uppgifter som ska utföras under de första 30 dagarna. De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.

- Uppgifter som ska utföras inom 90 dagar. De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.

- Efter 90 dagar. De här förbättringarna uppnås under de första 90 dagarna.

## <a name="see-also"></a>Se även:

- [Oväntade program i programlistan leder](/azure/active-directory/application-access-unexpected-application) administratörer genom olika åtgärder som de kan vilja utföra när oväntade program har åtkomst till data.

- [Att integrera program Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) en översikt över medgivande och behörigheter.

- [Problem med att utveckla mitt](/azure/active-directory/active-directory-application-dev-development-content-map) program innehåller länkar till olika medgivanderelaterade artiklar.

- [Application and service principal objects in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.

- [Hantera åtkomst till appar](/azure/active-directory/active-directory-managing-access-to-apps) är en översikt över de funktioner som administratörer har för att hantera användaråtkomst till appar.
