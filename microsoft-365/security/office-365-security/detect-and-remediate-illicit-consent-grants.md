---
title: Upptäcka och reparera bidrag för olaglig medgivande
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
description: Lär dig hur du känner igen och reparerar otillåtet medgivande i Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b534d53166c09cf77993948cf1c448e21c8cd330
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203101"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Upptäcka och reparera bidrag för olaglig medgivande

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Sammanfattning**  Lär dig hur du känner igen och reparerar otillåtet medgivande i Office 365.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Vad är godkännandet för medgivande i Office 365?

Vid intrång i ett otillåtet medgivande ger angriparen ett Azure-registrerat program som begär åtkomst till data, till exempel kontakt information, e-post eller dokument. Angriparen får ett råd för slutanvändaren att få åtkomst till sina data via nätfiske eller genom att injicera illegal kod på en betrodd webbplats. När olaglig ansökan har beviljats har den åtkomst nivå till data utan att ett organisations konto behövs. De vanliga reparations stegen, som att återställa lösen ord för överstigta konton eller kräva multifaktorautentisering (MFA) på konton, är inte effektiva mot denna typ av attacker, eftersom dessa är tredjepartsprogram och är utanför organisationen.

Dessa attacker utnyttjar en interaktions modell som förutsätter att den enhet som anropar informationen är automatisering och inte är en mänsklig.

> [!IMPORTANT]
> Misstänker du att du har problem med olaglig medgivande-bidrag från en app, just nu? Microsoft Cloud App Security (MCAS) har verktyg för att upptäcka, undersöka och åtgärda dina OAuth-appar. Den här MCAS artikeln har en själv studie kurs som innehåller information om hur du kommer igång med [riskfyllda OAuth-appar](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth). Du kan också ange [principer för OAuth-appar](https://docs.microsoft.com/cloud-app-security/app-permission-policy) för att undersöka programbegärda behörigheter, vilka användare som auktoriserar dessa program och hur de kan godkänna eller förbjuda dessa behörighets begär Anden.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Vad ser ett otillåtet medgivande i Office 365?

Du måste söka i **gransknings loggen** för att hitta tecken, även kallade anslags indikationer (IOC). För organisationer med många Azure-registrerade program och en stor användar bas är det bästa sättet att granska dina organisationers godkännanden varje vecka.

### <a name="steps-for-finding-signs-of-this-attack"></a>Anvisningar för att hitta tecken på det här angreppet

1. Öppna **säkerhets & Compliance Center** på <https://protection.office.com> .

2. Navigera till **Sök** och välj **gransknings loggs ökning**.

3. Sök (alla aktiviteter och alla användare) och ange start datum och slutdatum om det behövs och klicka sedan på **Sök**.

4. Klicka på **filtrera resultat** och ange medgivande till programmet i **aktivitets** fältet.

5. Klicka på resultatet för att visa aktivitetens uppgifter. Klicka på **Mer information** om du vill ha mer information om aktiviteten. Kontrol lera om IsAdminContent är true.

> [!NOTE]
>
> Det kan ta från 30 minuter upp till 24 timmar innan motsvarande Gransknings logg post visas i Sök resultatet när en händelse inträffar.
>
> Den tid som en gransknings post bevaras och sökbar i gransknings loggen beror på din Microsoft 365-prenumeration och speciellt typen för den licens som är tilldelad till en viss användare. Mer information finns i [Gransknings logg](../../compliance/search-the-audit-log-in-security-and-compliance.md).
>
> Om det här värdet är sant betyder det att någon med global administratörs åtkomst kan ha beviljat omfattande åtkomst till data. Om det här är oväntat, vidta åtgärder för att [Bekräfta ett angrepp](#how-to-confirm-an-attack).

## <a name="how-to-confirm-an-attack"></a>Så bekräftar du ett angrepp

Om du har en eller flera instanser av IOCs ovan måste du göra ytterligare undersökningar för att bekräfta att attacket har genomförts. Du kan använda någon av följande tre metoder för att bekräfta angreppet:

- Inventerings program och deras behörigheter med Azure Active Directory-portalen. Den här metoden är fullständig, men du kan bara kontrol lera en användare i taget, om du har många användare att kontrol lera.

- Inventerings program och deras behörigheter med PowerShell. Det här är den snabbaste och mest omfattande metoden, med minsta möjliga omkostnader.

- Be dina användare individuellt kontrol lera deras appar och behörigheter och rapportera resultatet tillbaka till administratörerna för reparation.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventera appar med åtkomst i organisationen

Du kan göra detta för dina användare med antingen Azure Active Directory-portalen eller PowerShell eller låta dina användare individuellt räkna upp sin program åtkomst.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Steg för att använda Azure Active Directory-portalen

Du kan leta upp program som en enskild användare har beviljat behörigheter med via [Azure Active Directory-portalen](https://portal.azure.com/).

1. Logga in på Azure-portalen med administratörs behörighet.

2. Välj Azure Active Directory-bladet.

3. Välj **Användare**.

4. Välj den användare du vill granska.

5. Välj **program**.

Då visas de program som har tilldelats till användaren och vilken behörighet de har.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Anvisningar för att låta användarna räkna upp sin program åtkomst

Låt användarna gå med https://myapps.microsoft.com och granska sin egen program åtkomst där. De bör kunna se alla program med Access, Visa information om dem (inklusive åtkomstscope) och kunna återkalla behörigheter till misstänkta och olagliga appar.

### <a name="steps-for-doing-this-with-powershell"></a>Anvisningar för hur du gör detta med PowerShell

Det enklaste sättet att kontrol lera godkännandet för ett otillåtet medgivande är att köra [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)som kommer att dumpa alla behörigheter för OAuth-godkännanden och OAuth-appar för alla användare i ditt innehav i en. csv-fil.

#### <a name="pre-requisites"></a>Förutsättningar

- Azure AD PowerShell-biblioteket installerat.

- Global administratörs behörighet på innehavaren som skriptet ska köra på.

- Lokal administratör på den dator som kör skripten.

> [!IMPORTANT]
> Vi ***rekommenderar starkt*** att du kräver multifaktorautentisering på ditt administratörs konto. Det här manuset stöder MFA-verifikation.

1. Logga in på datorn som du kör skriptet från med lokal administratörs behörighet.

2. Ladda ned eller kopiera [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) -skriptet från GitHub till en mapp som du vill köra skriptet från. Det här kommer att vara samma mapp som utgångs filen "permissions.csv" skrivs till.

3. Öppna en PowerShell-instans som administratör och öppna mappen där du sparade skriptet.

4. Anslut till din katalog med cmdleten [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) .

5. Kör det här PowerShell-kommandot:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Skriptet skapar en fil med namnet Permissions.csv. Följ de här anvisningarna för att söka efter illegala program behörigheter:

1. I kolumnen ConsentType (kolumn G) söker du efter värdet "AllPrinciples". Med AllPrincipals-behörigheten kan klient programmet komma åt allt innehåll i innehavet. Microsoft 365-program behöver den här behörigheten för att fungera korrekt. Alla program som inte kommer från Microsoft med den här behörigheten bör ses över noggrant.

2. I kolumnen permission (kolumn F) granska de behörigheter som varje ombuds program har till innehåll. Leta efter "Läs-och" Skriv "-behörighet eller" *. Alla "tillstånd" och Läs dessa noggrant eftersom de kanske inte är lämpliga.

3. Granska de specifika användare som har meddelade medgivanden. Om högkvalitativa och högkvalitativa användare har olämpligt skickade beviljade, bör du undersöka ytterligare.

4. Leta efter program som verkar vara misstänkta i kolumnen ClientDisplayName (kolumn C). Appar med felstavade namn, Super bland-namn eller hackare kan ses över noggrant.

## <a name="determine-the-scope-of-the-attack"></a>Fastställ omfattningen för angreppet

När du har slutfört inventeringen kan du granska **gransknings loggen** för att ta reda på vad som är fallet. Sök efter berörda användare, de tids ramar som olaglig ansökan hade till gång till i organisationen och de behörigheter appen hade. Du kan söka i **gransknings loggen** i [säkerhets-och kompatibilitetstillstånd för Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

> [!IMPORTANT]
> Gransknings-och gransknings kontroll för [post lådor](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) [för administratörer och användare](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) måste ha Aktiver ATS innan det angrips för att få den här informationen.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Så här stoppar och reparerar du en olaglig attack för godkännande

När du har identifierat ett program med olaglig behörighet kan du ta bort det på flera sätt.

- Du kan återkalla Programets behörighet i Azure Active Directory-portalen genom att:

  - Navigera till den berörda användaren i användar bladet i **Azure Active Directory** .

  - Välj **program**.

  - Välj illegal ansökan.

  - Klicka på **ta bort** i detalj nivån.

- Du kan återkalla OAuth medgivande-beviljande med PowerShell genom att följa stegen i [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).

- Du kan återkalla roll tilldelningen för tjänst program med PowerShell genom att följa stegen i [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).

- Du kan också inaktivera inloggning för det berörda kontot helt och hållet, som i sin tur inaktiverar program åtkomst till data på det kontot. Det här är inte idealiskt för slutanvändarens produktivitet, men om du arbetar med att begränsa effekten snabbt kan det vara en livskraftig kortsiktig åtgärd.

- Du kan stänga av integrerade program för ditt innehav. Det här är ett drastiskt steg som inaktiverar möjligheten för slutanvändarna att ge tillstånd från en klient organisation. Detta förhindrar att användarna oavsiktligt tillåter åtkomst till ett skadligt program. Detta rekommenderas inte eftersom det kraftigt försämrar användarnas förmåga att vara produktiv med tredjepartsprogram. Du kan göra det genom att följa stegen i [Aktivera eller inaktivera integrerade appar](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps).

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Skydda Microsoft 365 som en expert på cybersäkerhet

Din Microsoft 365-prenumeration innehåller kraftfulla säkerhetsfunktioner som du kan använda för att skydda dina data och dina användare. Använd [Säkerhetsöversikt för Microsoft 365 – de vanligaste prioriteringarna för de första 30 dagarna, 90 dagarna och bortom](security-roadmap.md) för att implementera Microsofts metodtips för att skydda din Microsoft 365-klientorganisation.

- Uppgifter som ska utföras under de första 30 dagarna. De har omedelbar effekt och påverkar inte användarna i någon större utsträckning.

- Uppgifter som ska utföras inom 90 dagar. De tar lite längre tid att planera och implementera men förbättrar din säkerhet avsevärt.

- Efter 90 dagar. De här förbättringarna uppnås under de första 90 dagarna.

## <a name="see-also"></a>Se även:

- [Oväntat program i listan Mina program](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) gör att administratörer genom olika åtgärder kan ta sig vidare efter att det finns oväntade program med åtkomst till data.

- Att [integrera program med Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) är en högkvalitativ översikt över medgivande och behörigheter.

- [Problem med att utveckla mitt program](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) ger länkar till olika godkännande relaterade artiklar.

- [Program-och tjänst huvud objekt i Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) ger en översikt över de program-och tjänst huvud objekt som är kärnan i program modellen.

- [Hantera åtkomst till program](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) är en översikt över de funktioner som administratörer har för att hantera användar åtkomst till appar.
