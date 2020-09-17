---
title: Administrera Exchange Online-postlådor i en multi-geo-miljö
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Lär dig hur du hanterar Exchange Online multi-geo-inställningar i din Microsoft 365-miljö med PowerShell.
ms.openlocfilehash: ea7090cd65634138f9677960beab7770825a6e86
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950682"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Administrera Exchange Online-postlådor i en multi-geo-miljö

Exchange Online PowerShell krävs för att visa och konfigurera multi geo-egenskaper i din Microsoft 365-miljö. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Du behöver [Microsoft Azure Active Directory PowerShell modul](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v 1.1.166.0 eller senare i v1. x för att se egenskapen **PreferredDataLocation** för användar objekt. De användar objekt som synkroniseras via AAD Connect into AAD kan inte ha sitt **PreferredDataLocation** -värde direkt ändrat via AAD PowerShell. Endast molnbaserade användar objekt kan ändras via AAD PowerShell. Information om hur du ansluter till Azure AD PowerShell finns i [ansluta till PowerShell](connect-to-microsoft-365-powershell.md).

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Ansluta direkt till en Geo-plats med Exchange Online PowerShell

Normalt ansluter Exchange Online PowerShell till Central geo-platsen. Men du kan också ansluta direkt till satellit platser på andra ställen. På grund av förbättringar av prestanda rekommenderar vi att du ansluter direkt till satellitens Geo plats när du bara hanterar användare på den platsen.

Kraven för att installera och använda EXO v2 finns beskrivna i [Installera och underhålla EXO v2-modulen](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

Om du vill ansluta Exchange Online PowerShell till en specifik Geo-plats är *ConnectionUri* -parametern annorlunda än de vanliga anslutnings anvisningarna. Resten av kommandona och värdena är desamma.

Specifikt måste du lägga till `?email=<emailaddress>` värdet i slutet av _ConnectionUri_ -värdet. `<emailaddress>` är e-postadressen till **alla** post lådor på Geo-platsen för mål. Din behörighet till post lådan eller relationen till dina autentiseringsuppgifter är inte en faktor; e-postadressen säger bara till Exchange Online PowerShell för anslutning.

Microsoft 365 eller Microsoft 365 GCC-kunder behöver vanligt vis inte använda parametern _ConnectionUri_ för att ansluta till Exchange Online PowerShell. Men om du vill ansluta till en specifik Geo-plats måste du använda _ConnectionUri_ parameter så att du kan använda `?email=<emailaddress>` i värdet.

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a>Ansluta till en Geo-plats i Exchange Online PowerShell med multifaktorautentisering (MFA)

1. Öppna modulen EXO v2 i ett Windows PowerShell-fönster genom att köra följande kommando:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. I det här exemplet är admin@contoso.onmicrosoft.com administratörs konto och mål-geo-platsen där post lådans olga@contoso.onmicrosoft.com finns.

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a>Ansluta till en Geo-plats i Exchange Online PowerShell utan MFA

1. Öppna modulen EXO v2 i ett Windows PowerShell-fönster genom att köra följande kommando:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. Kör följande kommando:

   ```powershell
   $UserCredential = Get-Credential
   ```

   I dialog rutan **begäran om autentiseringsuppgifter för Windows PowerShell** anger du ditt arbets-eller skol konto och lösen ord och klickar sedan på **OK**.

3. I det här exemplet är mål-geo platsen där olga@contoso.onmicrosoft.com finns.

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>Visa tillgängliga geo-platser som är konfigurerade i din Exchange Online-organisation

Om du vill visa en lista över konfigurerade geo-platser i Microsoft 365 multi-geo kör du följande kommando i Exchange Online PowerShell:

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>Visa Central geo-platsen för din Exchange Online-organisation

Om du vill visa klient organisationens centrala Geo-plats kör du följande kommando i Exchange Online PowerShell:

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>Hitta geo-platsen för en post låda

Cmdleten **Get-Mailbox** in Exchange Online PowerShell visar följande multi-geo-relaterade egenskaper i post lådorna:

- **Databas**: de första 3 bokstäverna i databas namnet motsvarar geo-koden, vilket anger var post lådan finns. För online-arkiv-post lådor ska egenskapen **ArchiveDatabase** användas.

- **MailboxRegion**: anger den Geo-plats kod som angavs av administratören (synkroniserad från **PREFERREDDATALOCATION** i Azure AD).

- **MailboxRegionLastUpdateTime**: anger när MailboxRegion senast uppdaterades (antingen automatiskt eller manuellt).

Använd följande syntax för att visa de här egenskaperna för en post låda:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

Om du till exempel vill visa geo-platsens information om chris@contoso.onmicrosoft.com kör du följande kommando:

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

Kommandot ser ut så här:

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> Om den Geo-plats koden i databas namnet inte stämmer överens med **MailboxRegion** -värdet kommer post lådan automatiskt att placeras i en kö för lagring och flyttas till den Geo-plats som anges i **MailboxRegion** -värdet (Exchange Online letar efter en avvikelse mellan dessa egenskaps värden).

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Flytta en befintlig brev låde post låda till en specifik Geo-plats

En användare som endast är en molnad användare är inte synkroniserad med klient organisationen via AAD Connect. Denna användare skapades direkt i Azure AD. Använd cmdletarna **Get-MsolUser** och **set-MSOLUSER** i Azure AD-modulen för Windows PowerShell för att visa eller ange den Geo-plats där en användares post låda i molnet lagras.

Om du vill visa **PreferredDataLocation** -värdet för en användare använder du denna syntax i Azure AD PowerShell:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Om du till exempel vill visa **PreferredDataLocation** -värdet för användar Michelle@contoso.onmicrosoft.com kör du följande kommando:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Om du vill ändra **PreferredDataLocation** -värdet för ett objekt i molnet kan du använda följande syntax i Azure AD PowerShell:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Om du till exempel vill ange **PreferredDataLocation** -värdet till EU (EUR) geo för User Michelle@contoso.onmicrosoft.com kör du följande kommando:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - Som tidigare nämnts kan du inte använda den här proceduren för synkroniserade användar objekt från lokala Active Directory. Du måste ändra värdet för **PreferredDataLocation** i Active Directory och synkronisera det med hjälp av AAD Connect. Mer information finns i [Azure Active Directory Connect Sync: konfigurera önskad data plats för Microsoft 365-resurser](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).
>
> - Hur lång tid det tar att hitta en post låda på en ny Geo-plats beror på flera faktorer:
>
>   - Storlek och typ av post låda.
>   - Antalet post lådor som flyttas.
>   - Tillgängligheten för att flytta resurser.

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a>Flytta inaktiverade post lådor som har en tvist kvar

Inaktiverade post lådor i tvist spärr som bevaras för eDiscovery kan inte flyttas genom att ändra deras **PreferredDataLocation** -värde i inaktiverat läge. Så här flyttar du en inaktive rad post låda i en tvist:

1. Koppla tillfälligt en licens till post lådan.

2. Ändra **PreferredDataLocation**.

3. Ta bort licensen från post lådan efter att den har flyttats till den valda geo-platsen för att den ska vara inaktive rad.

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Skapa nya moln post lådor på en viss Geo-plats

Om du vill skapa en ny post låda på en specifik Geo-plats måste du göra något av följande:

- Konfigurera **PreferredDataLocation** -värdet enligt beskrivningen i föregående avsnitt *innan* post lådan skapas i Exchange Online. Konfigurera till exempel värdet **PreferredDataLocation** för en användare innan du tilldelar en licens.

- Tilldela en licens samtidigt ställer du in **PreferredDataLocation** -värdet.

Om du vill skapa en ny moln-licensierad användare (inte AAD Connect Synchronized) på en specifik Geo-plats använder du följande syntax i Azure AD PowerShell:

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

I det här exemplet skapas ett nytt användar konto för Elizabeth Brunner med följande värden:

- Användarens huvud namn: ebrunner@contoso.onmicrosoft.com
- Förnamn: Elizabeth
- Efter namn: Brunner
- Visnings namn: Elizabeth Brunner
- Lösen ord: skapas och visas slumpmässigt i resultatet av kommandot (eftersom det inte använder *lösen ords* parametern)
- Licens: `contoso:ENTERPRISEPREMIUM` (E5)
- Plats: Australien (Australien)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Mer information om hur du skapar nya användar konton och hittar LicenseAssignment värden i Azure AD PowerShell finns i [skapa användar konton med PowerShell](create-user-accounts-with-microsoft-365-powershell.md) och [Visa licenser och tjänster med PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

> [!NOTE]
> Om du använder Exchange Online PowerShell för att aktivera en post låda och behöver post lådan på en Geo-plats som anges i **PreferredDataLocation**, måste du använda en Exchange Online-cmdlet, till exempel **Aktivera-post låda** eller **ny-post låda** direkt mot moln tjänsten. Om du använder cmdleten **Enable-RemoteMailbox** i lokal Exchange PowerShell skapas post lådan på den centrala geo-platsen.

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>Befintliga lokala post lådor på en viss Geo-plats

Du kan använda standardinställningarna för inbyggda verktyg och processer för att migrera en post låda från en lokal Exchange-organisation till Exchange Online, inklusive [instrument panelen för migrering i UK](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)och cmdleten [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) i Exchange Online PowerShell.

Det första steget är att verifiera att ett User-objekt finns för varje post låda som ska registreras och att rätt **PreferredDataLocation** -värde är konfigurerat i Azure AD. De inbyggda verktygen påverkar **PreferredDataLocation** -värdet och migrerar post lådorna direkt till angiven Geo-plats.

Eller så kan du använda följande steg för att hantera post lådor direkt i en viss Geo-plats med den nya cmdleten [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) i Exchange Online PowerShell.

1. Verifiera att användarobjektet finns för varje post låda som ska registreras och att **PreferredDataLocation** är inställt på önskat värde i Azure AD. Värdet för **PreferredDataLocation** synkroniseras till attributet **MailboxRegion** för motsvarande e-postanvändarnamn i Exchange Online.

2. Anslut direkt till den specifika satellit platsen med anslutnings anvisningarna från tidigare i det här avsnittet.

3. I Exchange Online PowerShell kan du lagra de lokala administratörs uppgifterna som används för att utföra en migrering av post lådor i en variabel genom att köra följande kommando:

   ```powershell
   $RC = Get-Credential
   ```

4. I Exchange Online PowerShell kan du skapa ett nytt **nytt-MoveRequest** som liknar det här exemplet:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. Upprepa steg #4 för varje post låda som du måste migrera från lokalt Exchange till den satellitbaserade geo platsen du är ansluten till.

6. Om du behöver migrera ytterligare post lådor till olika satellit platser upprepar du steg 2 till 4 för varje specifik plats.

## <a name="multi-geo-reporting"></a>Multi-geo-rapportering

**Flera geo rapporter för användning** i administrations centret för Microsoft 365 visar antalet användare per Geo-plats. I rapporten visas användar distribution för den aktuella månaden och historik för de senaste sex månaderna.

## <a name="see-also"></a>Se även

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
