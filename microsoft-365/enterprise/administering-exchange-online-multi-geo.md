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
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552013"
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

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>Ansluta till en Geo-plats i Exchange Online PowerShell

Följande anslutnings instruktioner fungerar för konton som är eller inte har kon figurer ATS för multifaktorautentisering (MFA).

1. Öppna modulen EXO v2 i ett Windows PowerShell-fönster genom att köra följande kommando:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. I det här exemplet är admin@contoso.onmicrosoft.com administratörs konto och mål-geo-platsen där post lådans olga@contoso.onmicrosoft.com finns.

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. Ange lösen ordet för admin@contoso.onmicrosoft.com i meddelandet som visas. Om kontot är konfigurerat för MFA måste du också ange säkerhets koden.

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

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>Flytta en inaktiv post låda till en viss geo

Du kan inte flytta inaktiva post lådor som bevaras i enlighet (till exempel post lådor på rättsliga håll) genom att ändra deras **PreferredDataLocation** -värde. Gör så här om du vill flytta en inaktiv post låda till en annan geo:

1. Återställ den inaktiva post lådan. Anvisningar finns i [återställa en inaktiv post låda](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).

2. Förhindra att hanteraren för hanterade mappar bearbetar den återställda post lådan genom att ersätta den \<MailboxIdentity\> med namn, alias, konto eller e-postadress för post lådan och köra följande kommando i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. Tilldela en **Exchange Online abonnemang 2** -licens till den återställda post lådan. Det här steget krävs för att återställa post lådan på den juridiska processen. Anvisningar finns i [tilldela licenser till användare](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

4. Konfigurera **PreferredDataLocation** -värdet i post lådan enligt beskrivningen i föregående avsnitt.

5. När du har bekräftat att post lådan har flyttats till den nya geo-platsen placerar du den återställda post lådan igen i arbets gruppen. Anvisningar finns i [lägga till en post låda med undantag](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).

6. När du har verifierat att den kvarhållna processen är på plats kan du låta den hanterade mappstrukturen bearbeta post lådan igen genom att ersätta den \<MailboxIdentity\> med namn, alias, konto eller e-postadress för post lådan och köra följande kommando i [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. Gör post lådan inaktiv igen genom att ta bort det användar konto som är kopplat till post lådan. Anvisningar finns i [ta bort en användare från din organisation](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user). I det här steget ges även Exchange Online abonnemang 2-licensen för andra användnings områden.

**Obs!** när du flyttar en inaktiv post låda till en annan Geo-plats kan du påverka innehållet Sök resultat eller möjligheten att söka i post lådan från den tidigare geo-platsen. Mer information finns i [söka efter och exportera innehåll i multi-geo-miljöer](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Skapa nya moln post lådor på en viss Geo-plats

Om du vill skapa en ny post låda på en specifik Geo-plats måste du göra något av följande:

- Konfigurera **PreferredDataLocation** -värdet enligt beskrivningen ovan [flytta en befintlig moln-Only-postlåda till ett specifikt Geo-plats-](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) avsnitt *innan* du skapar post lådan i Exchange Online. Konfigurera till exempel värdet **PreferredDataLocation** för en användare innan du tilldelar en licens.

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
