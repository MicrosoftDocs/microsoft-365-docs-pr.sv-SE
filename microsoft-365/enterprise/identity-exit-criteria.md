---
title: 'Fas 2: Avslutsvillkor för identitetsinfrastruktur'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Kontrollera att din konfiguration uppfyller Microsoft 365 Enterprise-villkoren för identitetsbaserade tjänster och infrastruktur.
ms.openlocfilehash: 433dec5e84c88dc6422619293f435f2d7199ea2e
ms.sourcegitcommit: 08a4ee7765f3eba42f0c037c5c564c581e45df3e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42807629"
---
# <a name="phase-2-identity-infrastructure-exit-criteria"></a>Fas 2: Avslutsvillkor för identitetsinfrastruktur

![Fas 2 – Identitet](../media/deploy-foundation-infrastructure/identity_icon-small.png)

Kontrollera att identitetsinfrastrukturen uppfyller följande krav och att du har övervägt de som är valfria.

Se också [Krav](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites) för ytterligare rekommendationer om identitetsinfrastruktur.

<a name="crit-identity-global-admin"></a>
## <a name="required-your-global-administrator-accounts-are-protected"></a>Obligatoriskt: dina globala administratörskonton skyddas 

Du har [skyddat dina globala Office 365-administratörskonton](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) för att hindra att autentiseringsuppgifter komprometteras av angripare, vilket kan leda till intrång i din Microsoft 365-prenumeration.

Om du hoppar över det här kravet kan dina globala administratörskonton vara sårbara för attacker och intrång, vilket gör det möjligt för en angripare att få tillgång till dina data i hela systemet och hämta, förstöra eller använda dina data i utpressningssyfte.

Vid behov kan [Steg 1](identity-create-protect-global-admins.md#identity-global-admin) hjälpa dig att uppfylla detta krav.

### <a name="how-to-test"></a>Så testar man

Använd följande steg för att kontrollera att du har skyddat dina globala administratörskonton:

1. Kör det här kommandot i Azure Active Directory PowerShell för Graph vid kommandotolken i PowerShell. Du bör bara se listan med dedikerade globala administratörskonton.
   ```powershell
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. Logga in på Office 365 med vart och ett av kontona från steg 1. Varje inloggning bör kräva Azure-multifaktorautentisering och den starkaste formen av sekundär autentisering som finns tillgänglig i din organisation.

> [!Note]
> Mer information om hur du installerar Azure Active Directory PowerShell för Graph-moduler och loggar in på Office 365 finns under [Ansluta till Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

<a name="crit-identity-pim"></a>
## <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a>Valfritt: du har konfigurerat privilegierad identitetshantering så att den globala administratörsrollen kan användas på begäran

Du har använt anvisningarna i [Konfigurera Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) för att aktivera PIM i din Azure AD-klientorganisation och konfigurera dina globala administratörskonton som giltiga administratörer.

Du har också använt rekommendationerna i [Säkrare åtkomst för hybrid- och molndistributioner i Azure AD ](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)för att utveckla en roadmap som säkrar att behörig åtkomst skyddas mot cyberangrepp.

Om du hoppar över det här alternativet är dina globala administratörskonton sårbara för fortlöpande online-angrepp, och om de komprometteras kan det innebära att en angripare kan hämta, förstöra eller använda dina känsliga uppgifter i utpressningssyfte.

Vid behov kan [Steg 1](identity-create-protect-global-admins.md#identity-pim) hjälpa dig med detta alternativ.

<a name="crit-identity-pam"></a>
## <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a>Valfritt: Du har konfigurerat behörighetshantering i Office 365

Du har använt informationen i [Konfigurera behörighetshantering i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) för att aktivera behörighet och skapa en eller flera policyer för behörig åtkomst inom organisationen. Du har konfigurerat dessa principer och just-in-time-åtkomst är aktiverad för åtkomst till känsliga data eller åtkomst till kritiska konfigurationsinställningar.

Vid behov kan [Steg 1](identity-create-protect-global-admins.md#identity-pam) hjälpa dig att uppfylla detta krav. 

<a name="crit-password-prot"></a>
## <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a>Valfritt: Azure AD-lösenordsskydd förbjuder användning av svaga lösenord

Du har aktiverat förbudet mot svaga lösenord [i molnet](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) och för dina [lokala AD DS (Active Directory Domain Services)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) för globalt blockerade lösenord och, om du vill, anpassade termer.

Vid behov kan [Steg 2](identity-secure-your-passwords.md#identity-password-prot) hjälpa dig med detta alternativ.

<a name="crit-identity-pw-reset"></a>
## <a name="optional-users-can-reset-their-own-passwords"></a>Valfritt: Användare kan återställa sina egna lösenord

Du har använt [snabbdistribution av självbetjäning av lösenordsåterställning för Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) för att konfigurera återställning av lösenord för dina användare.

Om du inte uppfyller det här villkoret kommer användare att vara beroende av administratörer av användarkonton för att återställa sina lösenord, vilket innebär ytterligare framtida IT-administration.

Vid behov kan [Steg 2](identity-secure-your-passwords.md#identity-pw-reset) hjälpa dig med detta alternativ.

<a name="crit-identity-sso"></a>
## <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a>Valfritt: användare kan logga in med sömlös enkel inloggning i Azure AD

Du har aktiverat [Azure AD Connect: sömlös enkel inloggning](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) för organisationen för att förenkla användarnas inloggning i molnbaserade program, till exempel Office 365.

Om du hoppar över det här alternativet kan användarna bli ombedda att uppge autentiseringsuppgifter när de får åtkomst till fler program som använder Azure AD-klientorganisationen.

Vid behov kan [Steg 2](identity-secure-your-passwords.md#identity-sso) hjälpa dig med detta alternativ.

<a name="crit-identity-custom-sign-in"></a>
## <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a>Valfritt: Inloggningsskärmen i Office 365 anpassas för din organisation

Du har använt [Lägga till företagsanpassning på sidorna för inloggning och åtkomst till panelen](https://aka.ms/aadpaddbranding) för att lägga till organisationens varumärke på inloggningssidan för Office 365.

Om du hoppar över det här alternativet visas en allmän inloggningsskärm i Office 365 för dina användare och de kanske inte är säkra på att de loggar in på organisationens webbplats.

Vid behov kan [Steg 2](identity-secure-your-passwords.md#identity-custom-sign-in) hjälpa dig med detta alternativ.


<a name="crit-identity-mfa"></a>
## <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a>Valfritt: Azure multifaktorautentisering har aktiverats för dina användare

Du har använt [Planera för Azure multifaktorautentisering](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) och [Principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) för att aktivera Azure multifaktorautentisering (MFA) för dina användarkonton.

Om du hoppar över det här alternativet kommer dina användarkonton att vara sårbara för kompromettering av autentiseringsuppgifter genom cyberangrepp. Om lösenordet till ett användarkonto har komprometterats är alla resurser och funktioner för kontot, t. ex. administratörsroller, tillgängliga för angriparen. Det gör det möjligt för angriparen att kopiera, förstöra eller använda interna dokument och andra data i utpressningssyfte.

Vid behov kan [Steg 3](identity-secure-user-sign-ins.md#identity-mfa) hjälpa dig med detta alternativ.

### <a name="how-to-test"></a>Så testar man

1.  Skapa ett testanvändarkonto och tilldela dem en licens. 
2.  Konfigurera multifaktorautentisering med Azure för testanvändarkontot med den extra verifieringsmetoden som du använder för verkliga användarkonton, t. ex. att skicka textmeddelanden till telefonen. 
3.  Logga in på Office 365-portalen med ditt testanvändarkonto.
4.  Kontrollera att MFA uppmanar dig om ytterligare verifieringsinformation och -resultat i en lyckad autentisering. 
5.  Ta bort testanvändarkontot.

<a name="crit-identity-ident-prot"></a>
## <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-e5-only"></a>Valfritt: Azure AD-identitetsskydd är aktiverat för att skydda mot kompromettering av autentiseringsuppgifter (endast Microsoft 365 E5)

Du har aktiverat Azure AD Identity Protection för:

- Åtgärda potentiella identitetssårbarheter.
- Upptäck möjliga försök till intrång i autentiseringsuppgifter.
- Undersök och åtgärda fortlöpande misstänkta identitetstillbud.

Om du hoppar över det här alternativet kan du inte upptäcka eller automatiskt bekämpa försök till kompromettering av autentiseringsuppgifter eller undersöka identitetsrelaterade incidenter. Detta gör din organisation potentiellt utsatt för kompromettering av autentiseringsuppgifter och därmed ett hot mot organisationens känsliga data.

Vid behov kan [Steg 3](identity-secure-user-sign-ins.md#identity-ident-prot) hjälpa dig med detta alternativ.


### <a name="how-to-test"></a>Så testar man

1. Skapa ett testanvändarkonto med ett första lösenord.
2. Använd anvisningarna i [Låt användare återställa sina egna lösenord i Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) för att återställa lösenordet för testanvändarkontot.
3. Logga ut och logga sedan in på testanvändarkontot med hjälp av lösenordsåterställning.
4. Ta bort testanvändarkontot.

<a name="crit-identity-sync"></a>
## <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a>Obligatoriskt för hybrididentiteter: användare och grupper synkroniseras med Azure AD

Om du har en befintlig lokal AD DS (Active Directory Domain Services) har du använt Azure AD Connect för att synkronisera användarkonton och -grupper från din lokala AD DS till Azure AD-klientorganisationen.

Med katalogsynkronisering kan användarna logga in på Office 365 och andra Microsoft-molntjänster med samma autentiseringsuppgifter som de använder för att logga in på sina datorer och komma åt lokala resurser.

Vid behov kan [Steg 4](identity-add-user-accounts.md#identity-sync) hjälpa dig med detta krav.

Om du hoppar över det här kravet kommer du att ha två uppsättningar användarkonton och -grupper:

- Användarkonton och -grupper som finns i din lokala AD DS
- Användarkonton och -grupper som finns i din Azure AD-klientorganisation

I det här läget måste de två uppsättningarna användarkonton och -grupper hanteras manuellt av både IT-administratörer och användare. Detta kommer oundvikligen att leda till osynkroniserade konton, deras lösenord och grupper.

### <a name="how-to-test"></a>Så testar man
Verifiera att autentisering med lokala autentiseringsuppgifter fungerar korrekt genom att logga in på Office-portalen med dina lokala autentiseringsuppgifter.

Du kontrollerar att katalogsynkronisering fungerar genom att göra följande:

1.  Skapa en ny testgrupp i AD DS.
2.  Vänta på synkroniseringstid.
3.  Kontrollera att namnet på den nya testgruppen visas i Azure AD-klientorganisationen.

<a name="crit-identity-sync-health"></a>
## <a name="optional-directory-synchronization-is-monitored"></a>Valfritt: Active Directory-synkroniseringen övervakas

Du har använt [Azure AD Connect Health med synkronisering](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (för lösenordssynkronisering) eller [Med Azure AD Connect Health med AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (för federerad autentisering) och har distribuerat Azure AD Connect Health, vilket inbegriper:

- Installera Azure AD Connect Health-agenten på var och en av dina lokala identitetsservrar.
- Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.

Om du hoppar över det här alternativet kan du bättre utvärdera tillståndet för den molnbaserade identitetsinfrastrukturen.

Vid behov kan [Steg 4](identity-add-user-accounts.md#identity-sync-health) hjälpa dig med detta alternativ.

### <a name="how-to-test"></a>Så testar man
Azure AD Connect Health-portalen visar aktuell och korrekt status för lokala domänkontrollanter och pågående synkronisering.


<a name="crit-identity-pw-writeback"></a>
## <a name="optional-password-writeback-is-enabled-for-your-users"></a>Valfritt: tillbakaskrivning av lösenord är aktiverat för dina användare

Du har använt anvisningarna i [Azure AD-SSPR med tillbakaskrivning av lösenord](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) för att aktivera tillbakaskrivning av lösenord för Azure AD-klientorganisationen för Microsoft 365 Enterprise-abonnemanget.

Om du hoppar över det här alternativet måste användare som inte är anslutna till ditt lokala nätverk återställa eller låsa upp AD DS-lösenordet via en IT-administratör.

Vid behov kan [Steg 4](identity-add-user-accounts.md#identity-pw-writeback) hjälpa dig med detta alternativ.

>[!Note]
>Tillbakaskrivning av lösenord krävs för att fullt ut använda skyddsfunktioner för Azure AD, t. ex. för att begära att användare ska ändra sina lokala lösenord när Azure AD har upptäckt en stor risk för kontointrång.
>

### <a name="how-to-test"></a>Så testar man

Du testar tillbakaskrivning av lösenord genom att ändra ditt lösenord i Office 365. Du bör kunna använda kontot och det nya lösenordet för att komma åt lokala AD DS-resurser.

1. Skapa ett testanvändarkonto i din lokala AD DS, tillåt att katalogsynkroniseringen utförs och ge den sedan en Microsoft 365 Enterprise-licens i administrationscentret för Microsoft 365.
2. Logga in på datorn och Office-portalen med hjälp av autentiseringsuppgifterna för testanvändarkontot från en fjärransluten dator som är ansluten till din lokala AD DS-domän.
3. Välj **Inställningar > Inställningar för Office 365 > Lösenord > Ändra lösenord**.
4. Skriv ditt nuvarande lösenord, skriv ett nytt lösenord och bekräfta det.
5. Logga ut från Office-portalen och fjärrdatorn och logga sedan in på datorn med testanvändarkontot och det nya lösenordet. Detta bekräftar att du kunde ändra lösenordet för ett lokalt AD DS-användarkonto med Azure AD-klientorganisationen.

### <a name="how-to-test"></a>Så testar man

Logga in på Office 365-portalen med ditt användarkontonamn och Azure multifaktorautentisering. Du bör se dina anpassade varumärkeselement på inloggningssidan.


<a name="crit-identity-self-service-groups"></a>
## <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a>Valfritt: Självbetjäning av grupphantering har aktiverats för vissa Azure AD-säkerhetsgrupper och Office 365-grupper

Du har fastställt vilka grupper som är lämpliga för självbetjäningshantering, instruerat deras ägare i arbetsflöden och ansvarsområden för grupphantering, och [konfigurerat självbetjäningshantering i Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) för dessa grupper.

Om du hoppar över det här alternativet måste alla uppgifter för Azure AD-grupphantering utföras av IT-administratörer.

Vid behov kan [Steg 5](identity-use-group-management.md#identity-self-service-groups) hjälpa dig med detta alternativ.

### <a name="how-to-test"></a>Så testar man
1.  Skapa ett testanvändarkonto för Azure AD med Azure-portalen.
2.  Logga in med testanvändarkontot och skapa en säkerhetstestgrupp för Azure AD.
3.  Logga ut och logga sedan in med ditt IT-administratörskonto.
4.  Konfigurera säkerhetstestgruppen för självbetjäningshantering för testanvändarkontot.
5.  Logga ut och logga sedan in med ditt testanvändarkonto.
6.  Använd Azure-portalen för att lägga till medlemmar i säkerhetstestgruppen.
7.  Ta bort säkerhetstestgruppen och testanvändarkontot.

<a name="crit-identity-dyn-groups"></a>
## <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a>Valfritt: inställningar för dynamiska gruppmedlemskap lägger automatiskt till användarkonton i grupper baserat på användarkontons attribut

Du har fastställt uppsättningen av dynamiska grupper i Azure AD och använt anvisningarna i [Attributbaserade dynamiska gruppmedlemskap i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) för att skapa grupperna och reglerna som avgör uppsättningen användarkontoattribut och värdena för gruppmedlemskap.

Om du hoppar över det här alternativet måste gruppmedlemskap göras manuellt när nya konton läggs till eller när attribut för användarkonton ändras med tiden. Om någon till exempel flyttas från försäljningsavdelningen till ekonomiavdelningen blir du tvungen att:

- Uppdatera värdet för det användarkontots avdelningsattribut.
- Manuellt ta bort dem från försäljningsgruppen.
- Manuellt lägga till dem till ekonomigruppen.

Om försäljnings- och redovisningsgrupperna var dynamiska skulle du bara behöva ändra användarkontots avdelningsvärde.

Vid behov kan [Steg 5](identity-use-group-management.md#identity-dyn-groups) hjälpa dig med detta alternativ.

### <a name="how-to-test"></a>Så testar man

1. Skapa en dynamisk testgrupp i Azure AD med Azure-portalen och konfigurera en regel för avdelningen motsvarande “test1”.
2. Skapa ett testanvändarkonto i Azure AD och ställ in egenskapen för avdelningen till “test1”.
3. Kontrollera egenskaperna för användarkontot för att säkerställa att det har blivit medlem i den dynamiska testgruppen.
4. Ändra värdet hos avdelningen för testanvändarkontot till “test2”.
5. Kontrollera egenskaperna för användarkontot för att säkerställa att det har inte längre är medlem i den dynamiska testgruppen.
6. Ta bort den dynamiska testgruppen och testanvändarkontot.

<a name="crit-identity-group-license"></a>
## <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a>Valfritt: Gruppbaserad licensiering för att automatiskt tilldela och ta bort licenser till användarkonton baserat på gruppmedlemskap

Du har [aktiverat gruppbaserad licensiering](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) för lämpliga Azure AD-säkerhetsgrupper, så att dina Microsoft 365 Enterprise-licenser tilldelas eller tas bort automatiskt.

Om du hoppar över det här alternativet blir du tvungen att manuellt:

- Tilldela licenser till nya användare som du vill ska ha åtkomst.
- Ta bort licenser från användare som inte längre finns i din organisation eller som inte längre har åtkomst.

Vid behov kan [Steg 5](identity-use-group-management.md#identity-group-license) hjälpa dig med detta alternativ.

### <a name="how-to-test"></a>Så testar man

1. Skapa en säkerhetstestgrupp i Azure AD med Azure-portalen och konfigurera gruppbaserad licensering för att tilldela Microsoft 365 Enterprise-licens.
2. Skapa ett testanvändarkonto i Azure AD och lägg till det i säkerhetstestgruppen.
3. Kontrollera egenskaperna för användarkontot i administrationscentret för Microsoft 365 för att säkerställa att det har tilldelats Microsoft 365 Enterprise-licensen.
4. Ta bort testanvändarkontot från säkerhetstestgruppen.
5. Kontrollera egenskaperna för användarkontot för att säkerställa att det har inte har Microsoft 365 Enterprise-licensen tilldelad längre.
6. Ta bort säkerhetstestgruppen och testanvändarkontot.


<a name="crit-identity-access-reviews"></a>
## <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a>Valfritt: åtkomstgranskningar som konfigurerats och används för att övervaka åtkomst

Du har använt de här artiklarna för att konfigurera olika typer av åtkomstgranskningar och övervaka gruppmedlemskap, åtkomst till företagsprogram och rolluppgifter:

- [Grupper och appar](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD-roller](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure-resursroller](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Vid behov kan [Steg 6](identity-configure-identity-governance.md#identity-access-reviews) hjälpa dig med detta alternativ.


## <a name="results-and-next-steps"></a>Resultat och nästa steg

Din identitetsinfrastruktur i Microsoft 365-molnet använder stark autentisering, skyddade administratörskonton och förenklad användaråtkomst och -hantering.

|||
|:-------|:-----|
|![Fas 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)| Om du följer stegen för slutpunkt till slutpunkt-distribution av Microsoft 365 Enterprise, är nästa fas [Windows 10 Enterprise](windows10-infrastructure.md). |

