---
title: Hantera e-postanvändare i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Lär dig mer om hur du hanterar e-postanvändare i Exchange Online Protection (EOP), inklusive att använda katalogsynkronisering, EAC och PowerShell för att hantera användare.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e40465901747bcbd006d437fa527a9803aad1e24
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208651"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Hantera e-postanvändare i fristående EOP

I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor är e-postanvändare den grundläggande typen av användarkonto. En e-postanvändare har kontouppgifter i din fristående EOP-organisation och kan komma åt resurser (har tilldelats behörigheter). En e-postanvändares e-postadress är extern (till exempel i din lokala e-postmiljö).

> [!NOTE]
> När du skapar en e-postanvändare är motsvarande användarkonto tillgängligt i microsoft 365-administrationscentret. När du skapar ett användarkonto i administrationscentret för Microsoft 365 kan du inte använda det kontot för att skapa en e-postanvändare.

Den rekommenderade metoden för att skapa och hantera e-postanvändare i fristående EOP är att använda katalogsynkronisering enligt beskrivningen i avsnittet [Använd katalogsynkronisering för att hantera e-postanvändare](#use-directory-synchronization-to-manage-mail-users) senare i det här avsnittet.

För fristående EOP-organisationer med ett litet antal användare kan du lägga till och hantera e-postanvändare i Administrationscenter för Exchange (EAC) eller i fristående EOP PowerShell enligt beskrivningen i det här avsnittet.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna Administrationscenter för Exchange (EAC) finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- När du skapar e-postanvändare i EOP PowerShell kan du stöta på begränsning. EOP PowerShell-cmdlets använder också en batchbearbetningsmetod som resulterar i en spridningsfördröjning på några minuter innan resultaten av kommandona är synliga.

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Du behöver som standard rollerna För skapande av e-postmottagare (skapa) och E-postmottagare (ändra) som har tilldelats rollgrupperna OrganizationManagement (global admins) och RecipientManagement som standard. Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i Exchange-forumen. Besök [forumet för Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Använda administrationscentret för Exchange för att hantera e-postanvändare

### <a name="use-the-eac-to-create-mail-users"></a>Använda EAC för att skapa e-postanvändare

1. Gå till **Mottagare** \> **Kontakter i** EAC

2. Klicka på **Ny** ![ ny ikon ](../../media/ITPro-EAC-AddIcon.png) . Konfigurera följande inställningar på **den nya e-postanvändarsidan** som öppnas. Inställningar markerade med en <sup>\*</sup> krävs.

   - **Förnamn**

   - **Initialer**: Personens mellersta initial.

   - **Efternamn**

   - <sup>\*</sup>**Visningsnamn**: Som standard visar den här rutan värdena från rutorna **Förnamn,** **Initialer**och **Efternamn.** Du kan acceptera det här värdet eller ändra det. Värdet ska vara unikt och ha en maximal längd på 64 tecken.

   - <sup>\*</sup>**Alias:** Ange ett unikt alias med upp till 64 tecken för användaren

   - **Extern e-postadress**: Ange användarens e-postadress. Domänen ska vara extern till din molnbaserade organisation.

   - <sup>\*</sup>**Användar-ID:** Ange det konto som personen ska använda för att logga in på tjänsten. Användar-ID:t består av ett användarnamn till vänster om symbolen at (@) (@) och en domän till höger.

   - <sup>\*</sup>**Nytt lösenord** och <sup>\*</sup> **Bekräfta lösenord**: Ange och ange lösenordet igen. Kontrollera att lösenordet uppfyller kraven för lösenordslängd, komplexitet och historik i din organisation.

3. När du är klar klickar du på **Spara** för att skapa e-postanvändaren.

### <a name="use-the-eac-to-modify-mail-users"></a>Använda EAC för att ändra e-postanvändare

1. Gå till **Mottagare** \> **kontakter**i EAC.

2. Markera den e-postanvändare som du vill ändra och klicka sedan på **Ikonen Redigera** ![ ](../../media/ITPro-EAC-AddIcon.png) redigera.

3. På sidan Egenskaper för e-postanvändare som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.

   Klicka på **Spara** när du är klar.

#### <a name="general"></a>Allmänt

Använd fliken **Allmänt** om du vill visa eller ändra grundläggande information om e-postanvändaren.

- **Förnamn**

- **Initialer**

- **Efternamn**

- **Visningsnamn**: Det här namnet visas i organisationens adressbok, på raderna Till och Från i e-post och i listan över kontakter i EAC. Det här namnet får inte innehålla tomma blanksteg före eller efter visningsnamnet.

- **Användar-ID:** Detta är användarens konto i Microsoft 365. Du kan inte ändra det här värdet här.

#### <a name="contact-information"></a>Kontaktuppgifter

Använd fliken **Kontaktinformation** om du vill visa eller ändra användarens kontaktinformation. Informationen på den här sidan visas i adressboken.

- **Street**
- **Ort**
- **Stat/provins**
- **Postnummer**
- **Land/region**
- **Telefon, arbete**
- **Mobiltelefon**
- **Fax**
- **Fler alternativ**

  - **Office**
  - **Telefon hem**
  - **Webbsida**
  - **Kommentar**

#### <a name="organization"></a>Organisation

Använd fliken **Organisation** om du vill registrera detaljerad information om användarens roll i organisationen.

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Använda EAC för att ta bort e-postanvändare

1. Gå till **Mottagare** \> **kontakter**i EAC.

2. Markera den e-postanvändare som du vill ta bort och klicka sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>Använda PowerShell för att hantera e-postanvändare

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Använda fristående EOP PowerShell för att visa e-postanvändare

Om du vill returnera en sammanfattningslista över alla e-postanvändare i fristående EOP PowerShell kör du följande kommando:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Om du vill visa detaljerad information om en viss e-postanvändare ersätter du \< E-postidentitet \> med e-postanvändarens namn, alias eller kontonamn och kör följande kommandon:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Detaljerad syntax- och parameterinformation finns i [Hämta mottagare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) och [hämta användare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Använda fristående EOP PowerShell för att skapa e-postanvändare

Om du vill skapa e-postanvändare i fristående EOP PowerShell använder du följande syntax:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Anmärkningar**:

- Parametern _Name_ krävs, har en maximal längd på 64 tecken och måste vara unik. Om du inte använder parametern _DisplayName_ används värdet för parametern _Name_ för visningsnamnet.
- Om du inte använder parametern _Alias_ används den vänstra sidan av _parametern MicrosoftOnlneServicesID_ för aliaset.
- Om du inte använder parametern _ExternalEmailAddress_ används _MicrosoftOnlineServicesID-värdet_ för den externa e-postadressen.

I det här exemplet skapas en e-postanvändare med följande inställningar:

- Namnet är JeffreyZeng och visningsnamnet är Jeffrey Zeng.
- Förnamnet är Jeffrey och efternamnet är Zeng.
- Alias är Jeffreyz.
- Den externa e-postadressen är jzeng@tailspintoys.com.
- Kontonamnet är jeffreyz@contoso.onmicrosoft.com.
- Lösenordet är Pa $ $word1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Detaljerad syntax- och parameterinformation finns i [Ny-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Använda fristående EOP PowerShell för att ändra e-postanvändare

Om du vill ändra befintliga e-postanvändare i fristående EOP PowerShell använder du följande syntax:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Textg>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

I det här exemplet anges den externa e-postadressen för Pilar Pinilla.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

I det här exemplet anges egenskapen Företag för alla e-postanvändare till Contoso.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Detaljerad syntax- och parameterinformation finns i [Ange-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Använda fristående EOP PowerShell för att ta bort e-postanvändare

Om du vill ta bort e-postanvändare i fristående EOP PowerShell \< ersätter du MailUserIdentity \> med e-postanvändarens namn, alias eller kontonamn och kör följande kommando:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

I det här exemplet tas e-postanvändaren bort för Jeffrey Zeng.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Detaljerad syntax- och parameterinformation finns i [Ta bort EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Om du vill kontrollera att du har skapat, ändrat eller tagit bort e-postanvändare i fristående EOP använder du något av följande:

- Gå till **Mottagare** \> **kontakter**i EAC. Kontrollera att e-postanvändaren finns med i listan (eller inte finns med i listan). Markera e-postanvändaren och visa informationen i informationsfönstret eller klicka på **Ikonen Redigera** redigera för att ![ visa ](../../media/ITPro-EAC-AddIcon.png) inställningarna.

- I fristående EOP PowerShell kör du följande kommando för att kontrollera att e-postanvändaren finns med i listan (eller inte finns med i listan):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Ersätt \< E-postidentitet \> med e-postanvändarens namn, alias eller kontonamn och kör följande kommandon för att verifiera inställningarna:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Använda katalogsynkronisering för att hantera e-postanvändare

I fristående EOP är katalogsynkronisering tillgänglig för kunder med lokal Active Directory. Du kan synkronisera dessa konton till Azure Active Directory (Azure AD), där kopior av kontona lagras i molnet. När du synkroniserar dina befintliga användarkonton till Azure Active Directory kan du visa dessa användare i fönstret Mottagare i **Administrationscenter** för Exchange (EAC) eller i fristående EOP PowerShell.

**Anmärkningar**:

- Om du använder katalogsynkronisering för att hantera mottagarna kan du fortfarande lägga till och hantera användare i Microsoft 365-administrationscentret, men de synkroniseras inte med den lokala Active Directory. Detta beror på att katalogsynkronisering bara synkroniserar mottagare från den lokala Active Directory till molnet.

- Användning av katalogsynkronisering rekommenderas för användning med följande funktioner:

  - **Outlook Safe Sender listor och blockerade avsändare listor:** När synkroniseras till tjänsten, dessa listor kommer att ha företräde framför spam filtrering i tjänsten. På så sätt kan användare hantera sin egen lista över betrodda avsändare och blockerad avsändare med enskilda avsändare och domänposter. Mer information finns i [Konfigurera inställningar för skräppost på Exchange Online-postlådor](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).

  - **Katalogbaserad kantblockering (DBEB):** Mer information om DBEB finns i [Använda katalogbaserad kantblockering för att avvisa meddelanden som skickas till ogiltiga mottagare](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Slutanvändarens åtkomst till karantän:** För att komma åt sina meddelanden i karantän måste mottagarna ha ett giltigt användar-ID och lösenord i tjänsten. Mer information om karantän finns i [Hitta och släppa meddelanden i karantän som användare](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).

  - **Regler för e-postflöde (kallas även transportregler):** När du använder katalogsynkronisering överförs dina befintliga Active Directory-användare och -grupper automatiskt till molnet och du kan sedan skapa regler för e-postflöde som riktar sig till specifika användare och/eller grupper utan att behöva lägga till dem manuellt i tjänsten. Observera att [dynamiska distributionsgrupper](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) inte kan synkroniseras via katalogsynkronisering.

Hämta nödvändiga behörigheter och förbereda för katalogsynkronisering enligt beskrivningen i [Vad är hybrididentitet med Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Synkronisera kataloger med Azure Active Directory Connect (AAD Connect)

1. Aktivera katalogsynkronisering enligt beskrivningen i [Azure AD Connect-synkronisering: Förstå och anpassa synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Installera och konfigurera en lokal dator för att köra AAD Connect enligt beskrivningen i [Förutsättningar för Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).

3. [Välj vilken installationstyp som ska användas för Azure AD Connect:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Anpassade](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Direktautentisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> När du är klar med konfigurationsguiden för Azure Active Directory Sync Tool skapas **MSOL_AD_SYNC-kontot** i Active Directory-skogen. Det här kontot används för att läsa och synkronisera din lokala Active Directory-information. För att katalogsynkroniseringen ska fungera korrekt kontrollerar du att TCP 443 på den lokala katalogsynkroniseringsservern är öppen.

När du har konfigurerat synkroniseringen måste du kontrollera att AAD Connect synkroniseras korrekt. I EAC går du till **Mottagare** \> **Kontakter** och visa att listan över användare har synkroniserats korrekt från din lokala miljö.
