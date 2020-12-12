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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Lär dig hur du hanterar e-postanvändare i Exchange Online Protection (EOP), inklusive att använda Directory-synkronisering, UK och PowerShell för att hantera användare.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a8258a63fe0fbf4a6b5641fbdef213f25de2e4dd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658839"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Hantera e-postanvändare i fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor är e-postanvändarna grundläggande användar konto. En e-postanvändare har kontoautentiseringsuppgifter i din fristående EOP-organisation och kan komma åt resurser (har tilldelade behörigheter). E-postadressen till en e-postanvändare är extern (till exempel i din lokala e-postmiljö).

> [!NOTE]
> När du skapar en e-postanvändare finns motsvarande användar konto i administrations centret för Microsoft 365. När du skapar ett användar konto i administrations centret för Microsoft 365 kan du inte använda det kontot för att skapa en e-postanvändare.

Den rekommenderade metoden för att skapa och hantera e-postanvändare i fristående EOP är att använda profilsynkronisering enligt beskrivningen i avsnittet [använda katalog-synkronisering för att hantera e-postanvändare](#use-directory-synchronization-to-manage-mail-users) i den här artikeln.

För fristående EOP-organisationer med ett fåtal användare kan du lägga till och hantera e-postanvändare i administrations centret för Exchange (UK) eller fristående EOP PowerShell enligt beskrivningen i den här artikeln.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna administrations centret för Exchange (UK) läser du [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- När du skapar e-postanvändare i EOP PowerShell kan du stöta på begränsning. Dessutom använder PowerShell-cmdlets för EOP en grupp bearbetnings metod som resulterar i ett par minuter innan resultatet av kommandona visas.

- Du måste ha behörighet i Exchange Online Protection innan du kan göra det i den här artikeln. Du behöver bara skapa **e-postmottagare** och **e-postmottagare** (ändra), som har tilldelats roll grupperna **organisations hantering** (globala administratörer) och **mottagar hantering** . Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i Exchange-forumen. Gå till [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Använda administrations centret för Exchange för att hantera e-postanvändare

### <a name="use-the-eac-to-create-mail-users"></a>Använda UK för att skapa e-postanvändare

1. Gå till **mottagare** \> **kontakter** i UK.

2. Klicka på **ny** ![ ny ikon ](../../media/ITPro-EAC-AddIcon.png) . På sidan **ny e-postanvändare** som öppnas konfigurerar du följande inställningar. Inställningar som är markerade med <sup>\*</sup> är obligatoriska.

   - **Förnamn**

   - **Initialer**: personens initialer för mellan namn.

   - **Efter namn**

   - <sup>\*</sup>**Visnings namn**: den här rutan visar som standard värdena i rutorna för **förnamn**, **initialer** och **efter namn** . Du kan acceptera det här värdet eller ändra det. Värdet ska vara unikt och får innehålla högst 64 tecken.

   - <sup>\*</sup>**Alias**: Ange ett unikt alias med upp till 64 tecken för användaren

   - **Extern e-post adress**: Ange användarens e-postadress. Domänen bör vara extern för den molnbaserade organisationen.

   - <sup>\*</sup>**Användar-ID**: Ange det konto som personen ska använda för att logga in på tjänsten. Användar-ID: t består av ett användar namn på vänster sida av snabel-a (@) och en domän på höger sida.

   - <sup>\*</sup>**Nytt lösen** ord och <sup>\*</sup> **Bekräfta lösen ord**: Ange och ange lösen ordet för kontot igen. Kontrol lera att lösen ordet uppfyller kraven för lösen ord, komplexitet och historik för din organisation.

3. När du är klar klickar du på **Spara** för att skapa e-postkontot.

### <a name="use-the-eac-to-modify-mail-users"></a>Använda UK för att ändra e-postanvändare

1. Gå till **mottagare** \> **kontakter** i UK.

2. Markera den e-postanvändare som du vill ändra och klicka sedan på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-AddIcon.png) .

3. På sidan med egenskaper för e-postkonton som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.

   Klicka på **Spara** när du är klar.

#### <a name="general"></a>Allmänt

Använd fliken **Allmänt** för att visa eller ändra grundläggande information om e-postkontot.

- **Förnamn**

- **Initialer**

- **Efter namn**

- **Visnings namn**: det här namnet visas i organisationens adress bok på raderna till: och från: i e-post och i listan med kontakter i UK. Det här namnet får inte innehålla tomma blank steg före eller efter visnings namnet.

- **Användar-ID**: det här är användarens konto i Microsoft 365. Du kan inte ändra detta värde här.

#### <a name="contact-information"></a>Kontakt information

Använd fliken **kontakt information** för att visa eller ändra användarens kontakt information. Informationen på den här sidan visas i adress boken.

- **Gatu**
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

Använd fliken **organisation** för att registrera detaljerad information om användarens roll i organisationen.

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Använda UK för att ta bort e-postanvändare

1. Gå till **mottagare** \> **kontakter** i UK.

2. Markera den e-postanvändare som du vill ta bort och klicka sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>Använda PowerShell för att hantera e-postanvändare

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Använda fristående EOP PowerShell för att visa e-postanvändare

Om du vill returnera en sammanfattnings lista över alla e-postanvändare i fristående EOP PowerShell kör du följande kommando:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Om du vill visa detaljerad information om en viss e-postanvändare ersätter du \<MailUserIdentity\> med namn, alias eller konto namn för e-postkontot och kör följande kommandon:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Detaljerad information om syntax och parametrar finns i [Hämta-mottagare](https://docs.microsoft.com/powershell/module/exchange/get-recipient) och [få-användare](https://docs.microsoft.com/powershell/module/exchange/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Använda fristående EOP PowerShell för att skapa e-postanvändare

Om du vill skapa e-postanvändare i fristående EOP PowerShell använder du följande syntax:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Anmärkningar**:

- Parametern _namn_ är obligatorisk, har en maximal längd på 64 tecken och måste vara unik. Om du inte använder parametern _DisplayName_ används värdet för _namn_ parametern som visnings namn.
- Om du inte använder _Ali Aset_ används den vänstra sidan av parametern _MicrosoftOnlineServicesID_ för aliaset.
- Om du inte använder parametern _ExternalEmailAddress_ används värdet _MicrosoftOnlineServicesID_ för den externa e-postadressen.

I det här exemplet skapas en e-postanvändare med följande inställningar:

- Namnet är JeffreyZeng och visnings namnet är Jeffrey Zeng.
- Förnamnet är Jeffrey och efter namnet är Zeng.
- Aliaset är jeffreyz.
- Den externa e-postadressen är jzeng@tailspintoys.com.
- Konto namnet är jeffreyz@contoso.onmicrosoft.com.
- Lösen ordet är pa $ $word 1.

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Detaljerad information om syntax och parametrar finns i [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Använda fristående EOP PowerShell för att ändra e-postanvändare

Om du vill ändra befintliga e-postanvändare i fristående EOP PowerShell använder du följande syntax:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

I det här exemplet anges den externa e-postadressen för pilar Pinilla.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

I det här exemplet anges företags egenskapen för alla e-postanvändare till contoso.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Detaljerad information om syntax och parametrar finns i [set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Använda fristående EOP PowerShell för att ta bort e-postanvändare

Om du vill ta bort e-postkonton i fristående EOP PowerShell ersätter du \<MailUserIdentity\> med namn, alias eller konto namn för e-postanvändaren och kör följande kommando:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

Det här exemplet tar bort e-postkontot för Jeffrey Zeng.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Detaljerad information om syntax och parametrar finns i [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Så här kontrollerar du att du har skapat, ändrat eller tagit bort e-postanvändare i fristående EOP:

- Gå till **mottagare** \> **kontakter** i UK. Kontrol lera att e-postmeddelandet finns med i listan (eller inte listat). Markera e-postkontot och Visa informationen i informations fönstret eller klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-AddIcon.png) för att visa inställningarna.

- I fristående EOP PowerShell kör du följande kommando för att kontrol lera att e-postmeddelandet är listad (eller inte listad):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Ersätt \<MailUserIdentity\> med namn, alias eller konto namn för e-postkontot och kör följande kommandon för att kontrol lera inställningarna:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Använda Katalogduplicering för att hantera e-postanvändare

I fristående EOP är Directory-synkronisering tillgängligt för kunder med lokal Active Directory. Du kan synkronisera dessa konton med Azure Active Directory (Azure AD), där kopior av kontona lagras i molnet. När du synkroniserar dina befintliga användar konton till Azure Active Directory kan du visa dessa användare i fönstret **mottagare** i administrations centret för Exchange (UK) eller i fristående EOP PowerShell.

**Anmärkningar**:

- Om du använder katalog synkronisering för att hantera mottagarna kan du ändå lägga till och hantera användare i administrations centret för Microsoft 365, men de kommer inte att synkroniseras med din lokala Active Directory. Detta beror på att Active Directory-synkroniseringen bara synkroniserar mottagare från din lokala aktiva katalog till molnet.

- Du rekommenderas att använda profilsynkronisering med följande funktioner:

  - Listorna **Betrodda avsändare och spärrade avsändare i Outlook**: när du synkroniserar till tjänsten får de här listorna högre prioritet än skräp post filtrering i tjänsten. Då kan användarna hantera sin egen lista över betrodda avsändare och spärrade avsändare med enskilda avsändare och domän poster. Mer information finns i [Konfigurera inställningar för skräppost i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Mappbaserade Edge-blockering (DBEB)**: Mer information om DBEB finns i [använda katalogbaserade Edge-blockering för att neka meddelanden skickade till ogiltiga mottagare](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Slutanvändare åtkomst till karantän**: för att få åtkomst till deras karantän meddelanden måste mottagarna ha ett giltigt användar-ID och lösen ord i tjänsten. Mer information om karantän finns i [hitta och släppa meddelanden i karantän som en användare](find-and-release-quarantined-messages-as-a-user.md).

  - **Regler för e-postflöde (kallas även transport regler)**: när du använder katalog synkronisering laddas de befintliga Active Directory-användarna och-grupperna automatiskt till molnet, och du kan skapa regler för e-postflöde som riktar sig till specifika användare och/eller grupper utan att behöva lägga till dem manuellt i tjänsten. Observera att [dynamiska distributions grupper](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) inte kan synkroniseras med katalog synkronisering.

Skaffa nödvändiga behörigheter och förbereda för Active Directory-synkronisering enligt beskrivningen i [Vad är hybrid identitet med Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Synkronisera kataloger med Azure Active Directory Connect (AAD Connect)

1. Aktivera katalog synkronisering enligt beskrivningen i [Azure AD Connect-synkronisering: förstå och anpassa synkronisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Installera och konfigurera en lokal dator för att köra AAD Connect enligt beskrivningen i [förutsättningar för Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).

3. [Välj vilken Installations typ som ska användas för Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Företagsanpassade](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Direktautentisering](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> När du är klar med konfigurations guiden för Azure Active Directory-Synkroniseringshanteraren skapas **MSOL_AD_Sync** -kontot i Active Directory-skogen. Det här kontot används för att läsa och synkronisera din lokala Active Directory-information. För att Active Directory-synkroniseringen ska fungera korrekt kontrollerar du att TCP 443 på den lokala katalogpartitionen är öppen.

När du har konfigurerat din synkronisering måste du kontrol lera att AAD Connect är synkroniserat korrekt. I UK går du till **mottagare** - \> **kontakter** och visar att listan över användare har synkroniserats korrekt från din lokala miljö.
