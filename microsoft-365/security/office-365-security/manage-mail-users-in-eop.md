---
title: Hantera e-postanvändare i fristående EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Läs mer om hur du hanterar e-postanvändare i Exchange Online Protection (EOP), inklusive hur du hanterar användare med katalogsynkronisering, EAC och PowerShell.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910624"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Hantera e-postanvändare i fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor är e-postanvändare den grundläggande typen av användarkonto. En e-postanvändare har kontouppgifter i den fristående EOP-organisationen och kan komma åt resurser (har tilldelats behörigheter). En e-postanvändares e-postadress är extern (till exempel i din lokala e-postmiljö).

> [!NOTE]
> När du skapar en e-postanvändare är motsvarande användarkonto tillgängligt i administrationscentret för Microsoft 365. När du skapar ett användarkonto i administrationscentret för Microsoft 365 kan du inte använda det kontot till att skapa en e-postanvändare.

Den rekommenderade metoden för att skapa och hantera e-postanvändare i [](#use-directory-synchronization-to-manage-mail-users) fristående EOP är att använda katalogsynkronisering enligt beskrivningen i avsnittet Använda katalogsynkronisering för att hantera e-postanvändare längre fram i den här artikeln.

För fristående EOP-organisationer med ett litet antal användare kan du lägga till och hantera e-postanvändare i Administrationscenter för Exchange (EAC) eller i fristående EOP PowerShell enligt beskrivningen i den här artikeln.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Information om hur du öppnar administrationscentret för Exchange (EAC) finns i [Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- När du skapar e-postanvändare i EOP PowerShell kan det uppstå begränsningar. Dessutom använder EOP PowerShell-cmdlets en batchbearbetningsmetod som resulterar i en fördröjning på några minuter innan resultatet av kommandona visas.

- Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du rollerna Skapa **(skapa)** och E-postmottagare **(ändra),** som tilldelas rollgrupperna Organisationshantering **(globala** administratörer) och Mottagarhantering som standard.  Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [Administrationscenter för Exchange i Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Har du problem? Be om hjälp i Exchange-forumen. Gå till [Exchange Online Protection-forumet.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Använda Exchange admin center för att hantera e-postanvändare

### <a name="use-the-eac-to-create-mail-users"></a>Använda EAC för att skapa e-postanvändare

1. Gå till Mottagarnas kontakter **i** EAC \> 

2. Klicka **på ny** ny ikon ![ ](../../media/ITPro-EAC-AddIcon.png) . På sidan **Ny e-postanvändare** som öppnas konfigurerar du följande inställningar. Inställningar som är markerade med <sup>\*</sup> ett är obligatoriska.

   - **Förnamn**

   - **Initialer:** Personens initial för mellannamn.

   - **Efternamn**

   - <sup>\*</sup>**Visningsnamn:** Som standard visas värdena från rutorna **Förnamn,** **Initialer** **och Efternamn.** Du kan acceptera eller ändra det här värdet. Värdet ska vara unikt och får vara högst 64 tecken.

   - <sup>\*</sup>**Alias:** Ange ett unikt alias, upp till 64 tecken, för användaren

   - **Extern e-postadress:** Ange användarens e-postadress. Domänen ska vara extern i den molnbaserade organisationen.

   - <sup>\*</sup>**Användar-ID:** Ange det konto som personen kommer att använda för att logga in på tjänsten. Användar-ID består av ett användarnamn till vänster om at-symbolen (@) och en domän på höger sida.

   - <sup>\*</sup>**Nytt lösenord** <sup>\*</sup> **och Bekräfta lösenordet:** Ange och skriv lösenordet för kontot igen. Kontrollera att lösenordet uppfyller kraven på lösenordslängd, komplexitet och historik för din organisation.

3. När du är klar klickar du på Spara **för att** skapa e-postanvändaren.

### <a name="use-the-eac-to-modify-mail-users"></a>Använda EAC för att ändra e-postanvändare

1. Gå till Mottagare i **EAC.** \> 

2. Markera den e-postanvändare som du vill ändra och klicka sedan på **redigera** ![ redigeringsikonen ](../../media/ITPro-EAC-AddIcon.png) .

3. På sidan för e-postanvändares egenskaper som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.

   Klicka på **Spara** när du är klar.

#### <a name="general"></a>Allmänt

Använd fliken **Allmänt om** du vill visa eller ändra grundläggande information om e-postanvändaren.

- **Förnamn**

- **Initialer**

- **Efternamn**

- **Visningsnamn:** Det här namnet visas i organisationens adressbok, på raderna Till och Från i e-postmeddelanden och i listan över kontakter i EAC. Namnet får inte innehålla tomma blanksteg före eller efter visningsnamnet.

- **Användar-ID:** Det här är användarens konto i Microsoft 365. Du kan inte ändra det här värdet här.

#### <a name="contact-information"></a>Kontaktinformation

Använd fliken **Kontaktinformation** för att visa eller ändra användarens kontaktinformation. Informationen på den här sidan visas i adressboken.

- **Gata**
- **Ort**
- **Delstat/provins**
- **Postnummer**
- **Land/region**
- **Telefon, arbete**
- **Mobiltelefon**
- **Fax**
- **Fler alternativ**

  - **Office**
  - **Telefon hem**
  - **Webbsida**
  - **Kommentarer**

#### <a name="organization"></a>Organisation

Använd fliken **Organisation** om du vill spela in detaljerad information om användarens roll i organisationen.

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Använda EAC för att ta bort e-postanvändare

1. Gå till Mottagare i **EAC.** \> 

2. Markera den e-postanvändare du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.

## <a name="use-powershell-to-manage-mail-users"></a>Använda PowerShell för att hantera e-postanvändare

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Använda fristående EOP PowerShell för att visa e-postanvändare

Om du vill returnera en sammanfattningslista över alla e-postanvändare i fristående EOP PowerShell kör du följande kommando:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Om du vill visa detaljerad information om en viss e-postanvändare ersätter du med namnet, alias eller kontonamnet för e-postanvändaren och \<MailUserIdentity\> kör följande kommandon:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Detaljerad information om syntax och parametrar finns i [Hämta mottagare](/powershell/module/exchange/get-recipient) och [Hämta användare.](/powershell/module/exchange/get-user)

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Använda fristående EOP PowerShell för att skapa e-postanvändare

Om du vill skapa e-postanvändare i fristående EOP PowerShell använder du följande syntax:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Anmärkningar**:

- Parametern _Name_ är obligatorisk, har en maxlängd på 64 tecken och måste vara unik. Om du inte använder _parametern DisplayName_ används värdet för _parametern Name_ för visningsnamnet.
- Om du inte använder _aliasparametern_ används vänster sida av _MicrosoftOnlineServicesID-parametern_ för aliaset.
- Om du inte använder _parametern ExternalEmailAddress_ används _värdet för MicrosoftOnlineServicesID_ för den externa e-postadressen.

I det här exemplet skapas en e-postanvändare med följande inställningar:

- Det här namnet ärZenZeng och visningsnamnet är Zen Zeng.
- Förnamnet är Zeng och efternamnet är Zeng.
- Aliaset är alias.
- Den externa e-postadressen är jzeng@tailspintoys.com.
- Kontonamnet är jeffreyz@contoso.onmicrosoft.com.
- Lösenordet är Pa$$word 1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Detaljerad information om syntax och parametrar finns i [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Använda fristående EOP PowerShell för att ändra e-postanvändare

Om du vill ändra befintliga e-postanvändare i fristående EOP PowerShell använder du följande syntax:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

I det här exemplet anges den externa e-postadressen för Pilar Pinilla.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

I det här exemplet sätts företagsegenskapen för alla e-postanvändare till Contoso.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Detaljerad information om syntax och parametrar finns i [Set-EOPMailUser.](/powershell/module/exchange/set-eopmailuser)

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Använda fristående EOP PowerShell för att ta bort e-postanvändare

Om du vill ta bort e-postanvändare i fristående EOP PowerShell ersätter du med namnet, aliaset eller kontonamnet för e-postanvändaren och \<MailUserIdentity\> kör följande kommando:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

I det här exemplet tas e-postanvändaren för Zen Zeng bort.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Detaljerad information om syntax och parametrar finns i [Remove-EOPMailUser.](/powershell/module/exchange/remove-eopmailuser)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Kontrollera att du har skapat, ändrat eller tagit bort e-postanvändare i fristående EOP genom att använda någon av följande metoder:

- Gå till Mottagare i **EAC.** \>  Kontrollera att e-postanvändaren finns med i listan (eller inte). Markera e-postanvändaren och visa informationen i fönstret Information, eller klicka på **Redigera** ![ redigera-ikonen ](../../media/ITPro-EAC-AddIcon.png) om du vill visa inställningarna.

- I fristående EOP PowerShell kör du följande kommando för att verifiera att e-postanvändaren visas (eller inte visas):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Ersätt \<MailUserIdentity\> med namnet, alias eller kontonamnet för e-postanvändaren och kör följande kommandon för att verifiera inställningarna:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Använda katalogsynkronisering för att hantera e-postanvändare

I fristående EOP är katalogsynkronisering tillgänglig för kunder med lokal Active Directory. Du kan synkronisera dessa konton till Azure Active Directory (Azure AD), där kopior av kontona lagras i molnet. När du synkroniserar dina befintliga användarkonton med Azure Active  Directory kan du visa de användarna i fönstret Mottagare i Exchange admin center (EAC) eller i fristående EOP PowerShell.

**Anmärkningar**:

- Om du använder katalogsynkronisering för att hantera mottagarna kan du fortfarande lägga till och hantera användare i administrationscentret för Microsoft 365, men de synkroniseras inte med din lokala Active Directory. Det beror på att katalogsynkronisering bara synkroniserar mottagare från din lokala Active Directory till molnet.

- Vi rekommenderar att du använder katalogsynkronisering för följande funktioner:

  - **Listor över betrodda avsändare och spärrade** avsändare i Outlook: När de synkroniseras till tjänsten har de här listorna företräde framför skräppostfiltrering i tjänsten. Då kan användare hantera sina egna listor över Betrodda avsändare och Spärrade avsändare med enskilda avsändare och domänposter. Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Dbeb-blockering (Directory Based Edge Blocking):** Mer information om DBEB finns i Använda katalogbaserad edge-blockering för att avvisa meddelanden som [skickas till ogiltiga mottagare.](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

  - **Åtkomst till karantän för slutanvändarna:** För att komma åt meddelanden i karantän måste mottagarna ha ett giltigt användar-ID och lösenord i tjänsten. Mer information om karantän finns i [Hitta och släppa meddelanden i karantän som en användare.](find-and-release-quarantined-messages-as-a-user.md)

  - E-postflödesregler (kallas även **transportregler):** När du använder katalogsynkronisering överförs dina befintliga Active Directory-användare och grupper automatiskt till molnet och du kan sedan skapa e-postflödesregler som är anpassade för specifika användare och/eller grupper utan att du behöver lägga till dem manuellt i tjänsten. Observera att [dynamiska distributionsgrupper](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) inte kan synkroniseras via katalogsynkronisering.

Få nödvändiga behörigheter och förbereda för katalogsynkronisering enligt beskrivningen i [Vad är hybrididentitet med Azure Active Directory?](/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Synkronisera kataloger med Azure Active Directory Connect (AAD Connect)

1. Aktivera katalogsynkronisering enligt beskrivningen [i Azure AD Connect-synkronisering: Förstå och anpassa synkronisering](/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Installera och konfigurera en lokal dator för att köra AAD Connect enligt beskrivningen [i Krav för Azure AD Connect.](/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Välj vilken installationstyp som ska användas för Azure AD Connect:](/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Anpassad](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Direktautentisering](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> När du slutför konfigurationsguiden för Azure Active Directory-synkroniseringsverktyget **skapas MSOL_AD_SYNC-kontot** i Active Directory-skogen. Det här kontot används för att läsa och synkronisera din lokala Active Directory-information. För att katalogsynkroniseringen ska fungera korrekt kontrollerar du att TCP 443 på den lokala katalogsynkroniseringsservern är öppen.

När du har konfigurerat synkroniseringen kontrollerar du att AAD Connect synkroniseras korrekt. Gå till Mottagare av kontakter **i** EAC och se att listan över användare synkroniserades korrekt från din \>  lokala miljö.