---
title: Identifiera och åtgärda beviljat medgivande för någon av de här medgivandena
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
description: Lär dig hur du känner igen och åtgärdar att medgivande från medgivande förser dig med angrepp i Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1c724bb3b201e0ddf1edea4794606c7083605e8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165445"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Identifiera och åtgärda beviljat medgivande för någon av de här medgivandena

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Sammanfattning**  Lär dig hur du känner igen och åtgärdar att medgivande från medgivande förser dig med angrepp i Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Vad är det för medgivande som godkänner angrepp i Office 365?

I ett medgivande från medgivande på begäran av en förälder skapar attackeraren ett Azure-registrerat program som begär åtkomst till data, till exempel kontaktinformation, e-post eller dokument. Attackeraren tricksar sedan en slutanvändare till att ge det programmet medgivande för att få åtkomst till sina data antingen genom en nätfiskeattack eller genom att mata in en säkerhetskod på en betrodd webbplats. När programmet med programmet för programmet för kontot har beviljats medgivande har det tillgång till data på kontonivå utan att ett organisationskonto behövs. Vanliga åtgärder som att återställa lösenord för konton som har brutits eller som kräver Multi-Factor Authentication (MFA) på konton, är inte effektiva mot den här typen av angrepp eftersom dessa är tredjepartsprogram och är externa för organisationen.

Dessa attacker utnyttjar en interaktionsmodell som antas vara entitet som anropar informationen är automation och inte en person.

> [!IMPORTANT]
> Misstänker du att du har problem med att få medgivande från en app, just nu? Microsoft Cloud App Security (MCAS) har verktyg för att identifiera, undersöka och åtgärda OAuth-apparna. Den här MCAS-artikeln innehåller en självstudiekurs som beskriver hur du [undersöker riskfyllda OAuth-appar.](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth) Du kan också ange [OAuth-appprinciper](https://docs.microsoft.com/cloud-app-security/app-permission-policy) för att undersöka vilka behörigheter som efterfrågas, vilka användare som godkänner dessa appar, och godkänna eller förbjuda dessa behörighetsbegäranden.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Hur ser en förälders medgivande ut för att bevilja attack i Office 365?

Du måste söka i **granskningsloggen för** att hitta tecken, även kallade indikatorer på kompromett (IOC) för den här attacken. För organisationer med många Azure-registrerade program och en stor användarbas är det bäst att granska organisationens medgivande beviljar varje vecka.

### <a name="steps-for-finding-signs-of-this-attack"></a>Steg för att hitta tecken på den här attacken

1. Öppna **Säkerhets- & Efterlevnadscenter** <https://protection.office.com> på.

2. Gå till **Sök** och välj **Granskningsloggsökning.**

3. Sök (alla aktiviteter och alla användare) och ange startdatum och slutdatum om det behövs och klicka sedan på **Sök.**

4. Klicka **på Filtrera** resultat och ange godkännande till programmet i **fältet** Aktivitet.

5. Klicka på resultatet om du vill se information om aktiviteten. Klicka **på Mer information** för att få information om aktiviteten. Kontrollera om IsAdminContent är inställt på Sant.

> [!NOTE]
>
> Det kan ta från 30 minuter till 24 timmar innan motsvarande granskningsloggpost visas i sökresultatet efter att en händelse inträffat.
>
> Hur lång tid som en granskningspost behålls och är sökbar i granskningsloggen beror på din Microsoft 365-prenumeration, och särskilt på vilken typ av licens som tilldelas till en viss användare. Mer information finns i [granskningsloggen.](../../compliance/search-the-audit-log-in-security-and-compliance.md)
>
> Om det här värdet är sant anger det att någon med global administratörsåtkomst kan ha beviljat bred åtkomst till data. Om det här är oväntat kan du vidta åtgärder [för att bekräfta en attack.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>Så här bekräftar du en attack

Om du har en eller flera instanser av IOCs som anges ovan måste du undersöka ytterligare för att bekräfta att attacken inträffade. Du kan använda någon av följande tre metoder för att bekräfta attacken:

- Inventeringsprogram och deras behörigheter med hjälp av Azure Active Directory-portalen. Den här metoden är genomgående, men du kan bara kontrollera en användare i taget, vilket kan ta mycket tid om du har många användare att kontrollera.

- Inventeringsprogram och deras behörigheter med hjälp av PowerShell. Det här är den snabbaste och mest genomgående metoden med minsta möjliga overhead.

- Be användarna individuellt kontrollera sina appar och behörigheter och rapportera resultaten till administratörerna för åtgärd.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventeringsprogram med åtkomst i din organisation

Du kan göra detta för dina användare med antingen Azure Active Directory-portalen eller PowerShell eller låt användarna räkna upp deras programåtkomst individuellt.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Anvisningar för hur du använder Azure Active Directory-portalen

Du kan slå upp de program som en enskild användare har beviljat behörighet till med hjälp av [Azure Active Directory-portalen.](https://portal.azure.com/)

1. Logga in på Azure Portal med administrativa rättigheter.

2. Välj Azure Active Directory-bladet.

3. Välj **Användare**.

4. Välj den användare som du vill granska.

5. Välj **program.**

Då visas de appar som tilldelats till användaren och vilka behörigheter programmen har.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Steg för att användarna ska räkna upp sin programåtkomst

Be användarna gå till https://myapps.microsoft.com och granska sina egna programåtkomst där. De bör kunna se alla appar som har åtkomst, visa information om dem (inklusive omfattningen av åtkomst) och kunna återkalla behörigheter till misstänkta appar eller använda appar som används igen.

### <a name="steps-for-doing-this-with-powershell"></a>Steg för att göra detta med PowerShell

Det enklaste sättet att verifiera ett medgivande för medgivande-attacken är att köra [Get-AzureADPSPermissions.ps1, ](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)som dådumpar alla OAuth-medgivandetillägg och OAuth-appar för alla användare i ditt innehavare i en CSV-fil.

#### <a name="pre-requisites"></a>Förutsättningar

- Azure AD PowerShell-biblioteket installerat.

- Globala administratörsrättigheter för klientorganisationen som skriptet ska köras mot.

- Lokal administratör på datorn som kör skripten från.

> [!IMPORTANT]
> Vi ***rekommenderar att*** du kräver multifaktorautentisering för ditt administratörskonto. Det här skriptet har stöd för MFA-autentisering.

1. Logga in på den dator som du kör skriptet från med lokala administratörsrättigheter.

2. Ladda ned eller [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) skriptet från GitHub till en mapp som du ska köra skriptet från. Det här blir samma mapp som utdatafilen "permissions.csv" skrivs till.

3. Öppna en PowerShell-instans som administratör och öppna den mapp där du sparade skriptet.

4. Anslut till katalogen med cmdleten [Connect-AzureAD.](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)

5. Kör det här PowerShell-kommandot:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Skriptet ger en fil med namnet Permissions.csv. Följ dessa steg för att söka efter beviljad behörighet för programmet:

1. I kolumnen ConsentType (kolumn G) söker du efter värdet "AllPrinciples". Med behörigheten AllPrincipals har klientprogrammet åtkomst till innehållet som gäller för alla i klientprogrammet. Ursprungliga Microsoft 365-program behöver den här behörigheten för att fungera korrekt. Alla program som inte är Microsoft-program med den här behörigheten bör granskas noggrant.

2. I kolumnen Behörighet (kolumn F) granskar du behörigheterna som varje delegerat program har till innehållet. Leta efter behörigheterna "Läsa" och "Skriva" eller "*. Alla" och granska dem noggrant eftersom de kanske inte är lämpliga.

3. Granska specifika användare som har beviljats medgivande. Om användare med hög profil eller hög effekt beviljas olämpliga medgivanden bör du undersöka ytterligare.

4. Leta efter appar som verkar misstänkta i kolumnen ClientDisplayName (kolumn C). Appar med felstavade namn, supersltande namn och hackarljud bör granskas noggrant.

## <a name="determine-the-scope-of-the-attack"></a>Fastställa attackens omfattning

När du har slutfört inventeringen av programåtkomst granskar du **granskningsloggen** för att fastställa den fullständiga omfattningen av intrånget. Sök efter de aktuella användarna, tidsramarna som det berörda programmet hade åtkomst till din organisation och vilka behörigheter appen hade. Du kan söka i **granskningsloggen** i Säkerhets- och [efterlevnadscenter för Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

> [!IMPORTANT]
> [Postlådegranskning](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) [och aktivitetsgranskning för administratörer](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) och användare måste ha aktiverats före attacken för att du ska få den här informationen.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Hur man stoppar och åtgärdar ett medgivande från en förälder för att bevilja attack

När du har identifierat ett program med behörigheten så kan du ta bort den åtkomsten på flera olika sätt.

- Du kan återkalla programmets behörighet i Azure Active Directory-portalen genom att:

  - Navigera till den aktuella användaren i **Azure Active Directory-användarbladet.**

  - Välj **program.**

  - Välj programmet med programmet som används.

  - Klicka **på Ta** bort i detaljgranskningen.

- Du kan återkalla OAuth-medgivandet med PowerShell genom att följa stegen i [Remove-AzureADOAuth2PermissionGrant.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)

- Du kan återkalla tjänstappens rolltilldelning med PowerShell genom att följa stegen i [Remove-AzureADServiceAppRoleAssignment.](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)

- Du kan också inaktivera inloggning för det påverkade kontot helt och hållet, vilket i sin tur inaktiverar appåtkomst till data i det kontot. Det här är naturligtvis inte perfekt för slutanvändarens produktivitet, men om du arbetar för att begränsa påverkan snabbt kan det vara en möjlig åtgärd på kort sikt.

- Du kan inaktivera integrerade program för ditt tiotal. Det här är ett avsevärt steg som inaktiverar möjligheten för slutanvändare att bevilja medgivande för hela klientorganisationen. Det förhindrar att användarna oavsiktligt beviljar åtkomst till ett skadligt program. Det rekommenderas inte särskilt mycket eftersom det allvarligt försämrar dina användares möjligheter att vara produktiva med program från tredje part. Det gör du genom att följa anvisningarna för [att aktivera eller inaktivera integrerade appar.](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Skydda Microsoft 365 som en expert på cybersäkerhet

Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare. Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.

- Uppgifter som ska utföras under de första 30 dagarna. De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.

- Uppgifter som ska utföras inom 90 dagar. De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.

- Efter 90 dagar. De här förbättringarna uppnås under de första 90 dagarna.

## <a name="see-also"></a>Se även:

- [Med oväntade program i programlistan](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) går administratörer igenom olika åtgärder som de kan vilja vidta när de har inse att det finns oväntade program som har åtkomst till data.

- [Integrering av program med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) är en översikt över medgivande och behörigheter på hög nivå.

- [Problem med att utveckla programmet](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) innehåller länkar till olika medgivanderelaterade artiklar.

- [Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.

- [Hantera åtkomst till appar](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) är en översikt över de funktioner som administratörer har för att hantera användaråtkomst till appar.
