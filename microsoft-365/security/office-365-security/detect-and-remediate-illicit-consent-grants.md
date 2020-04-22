---
title: Upptäcka och åtgärda bidrag för olagligt samtycke
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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Läs om hur du känner igen och åtgärdar attacken mot olagliga samtyckesbidrag i Office 365.
ms.openlocfilehash: 43ce8de2826006069b815a37208fe2a3834bf313
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637610"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Upptäcka och åtgärda bidrag för olagligt samtycke

**Sammanfattning**  Läs om hur du känner igen och åtgärdar attacken mot olagliga samtyckesbidrag i Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Vad är attacken mot det olagliga samtyckesbidraget i Office 365?

I en attack med otillåtet medgivande skapar angriparen ett Azure-registrerat program som begär åtkomst till data som kontaktinformation, e-post eller dokument. Angriparen lurar sedan en slutanvändare att bevilja programmet samtycke till att få tillgång till sina data antingen genom en nätfiskeattack eller genom att injicera olaglig kod på en betrodd webbplats. När den olagliga ansökan har beviljats samtycke har den tillgång till uppgifter på kontonivå utan att det behövs ett organisationskonto. Normala reparationssteg, som att återställa lösenord för konton som överskrids eller kräver MFA (MultiFaktor Authentication) på konton, är inte effektiva mot den här typen av angrepp, eftersom dessa är program från tredje part och är externa för organisationen. 

Dessa attacker utnyttjar en interaktionsmodell som förutsätter att entiteten som anropar informationen är automatisering och inte en människa.

> [!IMPORTANT]
> Misstänker du att du har problem med olagliga samtyckesbidrag från en app just nu? Microsoft Cloud App Security (MCAS) har verktyg för att identifiera, undersöka och åtgärda dina OAuth-appar. Den här MCAS-artikeln har en självstudiekurs som beskriver hur du undersöker [riskfyllda OAuth-appar](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth). Du kan också ange [OAuth-appprinciper](https://docs.microsoft.com/cloud-app-security/app-permission-policy) för att undersöka appbesyrkade behörigheter, vilka användare som auktoriserar dessa appar och i stor utsträckning godkänner eller förbjuder dessa behörighetsbegäranden.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Hur ser en olaglig bidragsattack ut i Office 365?

Du måste söka i **granskningsloggen** för att hitta tecken, även kallade Indikatorer för kompromiss (IOK) av denna attack. För organisationer med många Azure-registrerade program och en stor användarbas är det bästa sättet att granska dina organisationers medgivandebidrag varje vecka.

### <a name="steps-for-finding-signs-of-this-attack"></a>Åtgärder för att hitta tecken på denna attack

1. Öppna **Security & Compliance Center** i din klientorganisation.

2. Navigera till **Sök** och välj **Granskningsloggsökning**.

3. Sök (alla aktiviteter och alla användare) och ange startdatum och slutdatum om det behövs och klicka sedan på **Sök**. 

4. Filtrera resultaten för Medgivande till programmet och Lägg till OAuth2PermissionGrant.

5. Klicka på resultatet för att se information om aktiviteten. Klicka på **Mer information** om du vill ha information om aktiviteten. Kontrollera om IsAdminContent är inställt på Sant.

> [!NOTE]
> * Det kan ta från 30 minuter upp till 24 timmar innan motsvarande granskningsloggpost visas i sökresultaten när en händelse inträffar. <br/><br/> Hur lång tid en granskningspost behålls och söks i granskningsloggen beror på din Microsoft 365-prenumeration och specifikt vilken typ av licens som tilldelas en viss användare. Mer information finns i [Granskningsloggen](../../compliance/search-the-audit-log-in-security-and-compliance.md).
Om det här värdet är sant anger det att någon med global administratörsåtkomst kan ha beviljat bred åtkomst till data. Om detta är oväntat, vidta åtgärder för att [bekräfta en attack](#how-to-confirm-an-attack).

## <a name="how-to-confirm-an-attack"></a>Så här bekräftar du en attack

Om du har en eller flera instanser av IOCs som anges ovan, måste du göra ytterligare undersökning för att positivt bekräfta att attacken inträffade. Du kan använda någon av dessa tre metoder för att bekräfta attacken.

- Inventeringsprogram och deras behörigheter med hjälp av Azure Active Directory-portalen. Denna metod är grundlig, men du kan bara kontrollera en användare i taget som kan vara mycket tidskrävande om du har många användare att kontrollera.

- Inventeringsprogram och deras behörigheter med PowerShell. Detta är den snabbaste och mest grundliga metoden, med minst mängd omkostnader.

- Be användarna att individuellt kontrollera sina appar och behörigheter och rapportera resultaten tillbaka till administratörerna för reparation.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventera appar med åtkomst i organisationen

Du kan göra detta för dina användare med antingen Azure Active Directory Portal eller PowerShell eller låta användarna räkna upp sin programåtkomst individuellt.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Steg för att använda Azure Active Directory Portal

Du kan slå upp de program som alla enskilda användare har beviljat behörigheter till med hjälp av [Azure Active Directory Portal](https://portal.azure.com/).

1. Logga in på Azure Portal med administrativa rättigheter.

2. Välj Azure Active Directory-bladet.

3. Välj **Användare**.

4. Markera den användare som du vill granska.

5. Välj **program**.

Detta visar de appar som är tilldelade till användaren och vilka behörigheter programmen har.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Steg för att få användarna att räkna upp sin programåtkomst

Låt användarna gå https://myapps.microsoft.com till och granska sin egen programåtkomst där. De bör kunna se alla appar med åtkomst, visa information om dem (inklusive åtkomstens omfattning) och kunna återkalla privilegier till misstänkta eller olagliga appar.

### <a name="steps-for-doing-this-with-powershell"></a>Steg för att göra detta med PowerShell

Det enklaste sättet att verifiera attacken mot otillåtet medgivande är att köra [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), som dumpar alla OAuth-bidrag och OAuth-appar för alla användare i din hyresrätt i en CSV-fil.

#### <a name="pre-requisites"></a>Förutsättningar

- Azure AD PowerShell-biblioteket är installerat.

- Globala administratörsrättigheter för klienten som skriptet ska köras mot.

- Lokal administratör på datorn som ska köra skripten från.

> [!IMPORTANT]
> Vi ***rekommenderar starkt*** att du behöver multifaktorautentisering på ditt administrativa konto. Det här skriptet stöder MFA-autentisering.

1. Logga in på datorn som du ska köra skriptet från med lokala administratörsrättigheter.

2. Hämta eller kopiera [Get-AzureADPSPermissions.ps1-skriptet](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) från GitHub till en mapp där du ska köra skriptet. Detta kommer att vara samma mapp som utdata "permissions.csv" fil kommer att skrivas.

3. Öppna en PowerShell-instans som administratör och öppna för mappen som du sparade skriptet till.

4. Anslut till din katalog med cmdlet [connect-AzureAD.](https://docs.microsoft.com/powershell/module/azuread/connect-azuread)

5. Kör det här PowerShell-kommandot:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Skriptet producerar en fil med namnet Permissions.csv. Följ dessa steg för att leta efter bidrag för otillåten ansökan:

1. Sök efter värdet "AllPrinciples" i kolumnen ConsentType (kolumn G). Behörigheten AllPrincipals gör att klientprogrammet kan komma åt allas innehåll i hyresrätt. Inbyggda Microsoft 365-program behöver den här behörigheten för att fungera korrekt. Alla program som inte kommer från Microsoft med den här behörigheten bör granskas noggrant.

2. I kolumnen Behörighet (kolumn F) granska de behörigheter som varje delegerat program har till innehåll. Leta efter behörigheten "Läs" och "Skriv" eller "*. Alla" tillstånd, och granska dessa noggrant eftersom de kanske inte är lämpliga.

3. Granska de specifika användare som har beviljat medgivanden. Om användare med hög profil eller hög påverkan har fått olämpliga medgivanden bör du undersöka vidare.

4. Leta efter appar som verkar misstänkta i kolumnen ClientDisplayName (kolumn C). Appar med felstavade namn, super intetsägande namn eller hackerklingande namn bör granskas noggrant.

## <a name="determine-the-scope-of-the-attack"></a>Bestäm omfattningen av attacken

När du har slutfört åtkomsten till inventeringsprogram granskar du **granskningsloggen** för att fastställa hela omfattningen av överträdelsen. Sök på de berörda användarna, tidsramarna som det olagliga programmet hade åtkomst till din organisation och de behörigheter som appen hade. Du kan söka i **granskningsloggen** i [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

> [!IMPORTANT]
> [Postlådegranskning](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) och [aktivitetsgranskning för administratörer och användare](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) måste ha aktiverats före attacken för att du ska få den här informationen.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Hur man kan stoppa och åtgärda en olaglig samtyckessanslagsattack

När du har identifierat ett program med olagliga behörigheter har du flera sätt att ta bort åtkomsten.

- Du kan återkalla programmets behörighet i Azure Active Directory Portal genom att:

  - Navigera till den berörda användaren i **Azure Active Directory User** blade.

  - Välj **program**.

  - Välj den olagliga applikationen.

  - Klicka på **Ta bort** i detaljgranskningen nedåt.

- Du kan återkalla OAuth-medgivandet med PowerShell genom att följa stegen i [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).

- Du kan återkalla tjänstapprolltilldelningen med PowerShell genom att följa stegen i [Ta bort AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- Du kan också inaktivera inloggning för det berörda kontot helt och hållet, vilket i sin tur inaktiverar appåtkomst till data i det kontot. Detta är inte idealiskt för slutanvändarens produktivitet, naturligtvis, men om du arbetar för att begränsa effekten snabbt, kan det vara en livskraftig kortsiktig sanering.

- Du kan stänga av integrerade program för din hyresrätt. Detta är ett drastiskt steg som inaktiverar slutanvändares möjlighet att bevilja samtycke på klientomfattande basis. Detta förhindrar att användarna oavsiktligt beviljar åtkomst till ett skadligt program. Detta rekommenderas inte starkt eftersom det allvarligt försämrar användarnas förmåga att vara produktiv med tredjepartsprogram. Du kan göra detta genom att följa stegen i [Aktivera eller inaktivera integrerade appar](https://docs.microsoft.com/office365/admin/misc/integrated-apps).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Säkra Microsoft 365 som ett cybersäkerhetsproffs

Din Microsoft 365-prenumeration levereras med en kraftfull uppsättning säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare. Använd [microsoft 365-säkerhetsfärdplanen – De högsta prioriteterna för de första 30 dagarna, 90 dagarna och längre för](security-roadmap.md) att implementera Microsofts rekommenderade metodtips för att skydda din Microsoft 365-klientorganisation.

- Uppgifter som ska utföras under de första 30 dagarna. De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.

- Uppgifter som ska utföras inom 90 dagar. De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.

- Efter 90 dagar. De här förbättringarna uppnås under de första 90 dagarna.

## <a name="see-also"></a>Se även:

- [Oväntat program i min programlista](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) går administratörer genom olika åtgärder som de kanske vill vidta efter att ha insett att det finns oväntade program med tillgång till data.

- [Att integrera program med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) är en översikt på hög nivå över medgivande och behörigheter.

- [Problem med att utveckla min ansökan](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) ger länkar till olika samtycke relaterade artiklar.

- [Principobjekt för program och tjänst i Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) ger en översikt över huvudobjekten för programmet och tjänsten som är centrala för programmodellen.

- [Hantera åtkomst till appar](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) är en översikt över de funktioner som administratörer har för att hantera användaråtkomst till appar.
