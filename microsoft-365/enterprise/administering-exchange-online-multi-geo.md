---
title: Administrera Exchange Online postlådor i en miljö med flera geografiska miljöer
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
description: Lär dig hur du Exchange Online fler geoinställningar i din Microsoft 365-miljö med PowerShell.
ms.openlocfilehash: c8f06318313c4192fc2b3a289727933c5a54f3ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905590"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Administrera Exchange Online postlådor i en miljö med flera geografiska miljöer

Exchange Online PowerShell krävs för att visa och konfigurera flera geoegenskaper i Microsoft 365 miljö. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

Du behöver [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 eller senare i v1.x för att kunna se egenskapen **PreferredDataLocation** för användarobjekt. Användarobjekt som synkroniseras via AAD Anslut till AAD kan inte få sitt **PreferredDataLocation-värde** direkt ändrat via AAD PowerShell. Användarobjekt som bara är molnbaserade kan ändras via AAD PowerShell. Information om hur du ansluter till Azure AD PowerShell finns [Anslut till PowerShell.](connect-to-microsoft-365-powershell.md)

I Exchange Online geomiljöer behöver du inte göra några manuella steg för att lägga till geos i klientorganisationen. När du får ett meddelandecenterinlägg som säger att multi-geo är redo Exchange Online, kommer alla tillgängliga geos att vara klara och konfigurerade att användas.

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Anslut direkt till en geoplats med hjälp Exchange Online PowerShell

PowerShell Exchange Online vanligtvis till den centrala geoplatsen. Men du kan också ansluta direkt till satellitgeoplatser. På grund av prestandaförbättringar rekommenderar vi att ansluta direkt till satellit geoplatsen när du bara hanterar användare på den platsen.

Kraven för installation och användning av EXO V2-modulen beskrivs i [Installera och underhålla EXO V2-modulen.](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

När du Exchange Online powershell till en viss geoplats skiljer sig *ConnectionUri-parametern* från de vanliga anslutningsinstruktionerna. Resten av kommandona och värdena är desamma.

Mer specifikt måste du lägga till `?email=<emailaddress>` värdet i slutet av värdet för _ConnectionUri._ `<emailaddress>` är e-postadressen **till alla** postlådor på den geografiska målplatsen. Dina behörigheter till den postlådan eller relationen till dina autentiseringsuppgifter är inte en faktor. e-postadressen talar bara om Exchange Online PowerShell var du ska ansluta.

Microsoft 365 eller Microsoft 365 GCC behöver kunder vanligtvis inte använda _parametern ConnectionUri_ för att ansluta till Exchange Online PowerShell. Men om du vill ansluta till en viss geoplats måste du använda _ConnectionUri-parameter_ så att du kan `?email=<emailaddress>` använda det i värdet.

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>Anslut till en geoplats i Exchange Online PowerShell

Följande anslutningsinstruktioner fungerar för konton som är eller inte har konfigurerats för multifaktorautentisering (MFA).

1. I ett Windows PowerShell läser du in EXO V2-modulen genom att köra följande kommando:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. I följande exempel admin@contoso.onmicrosoft.com administratörskontot, och den geografiska målplatsen är den plats postlådan olga@contoso.onmicrosoft.com finns.

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. Ange lösenordet för den admin@contoso.onmicrosoft.com i uppmaningen som visas. Om kontot har konfigurerats för MFA måste du också ange säkerhetskoden.

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>Visa tillgängliga geoplatser som är konfigurerade i din Exchange Online organisation

Om du vill se en lista över konfigurerade geoplatser i Microsoft 365 Multi-Geo kör du följande kommando i Exchange Online PowerShell:

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>Visa den centrala geoplatsen för din Exchange Online organisation

Om du vill visa klientorganisationens centrala geoplats kör du följande kommando i Exchange Online PowerShell:

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>Hitta en postlådas geoplats

**Cmdlet:en Get-Mailbox** i Exchange Online PowerShell visar följande multigeorelaterade egenskaper för postlådor:

- **Databas:** De tre första bokstäverna i databasnamnet motsvarar geokoden som anger var postlådan finns för närvarande. För onlinearkivpostlådor **ska egenskapen ArchiveDatabase** användas.

- **MailboxRegion:** Anger den geoplatskod som angetts av administratören (synkroniserad från **PreferredDataLocation** i Azure AD).

- **MailboxRegionLastUpdateTime**: Anger när MailboxRegion uppdaterades senast (antingen automatiskt eller manuellt).

Om du vill visa de här egenskaperna för en postlåda använder du följande syntax:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

Om du till exempel vill se information om platsen för postlådan chris@contoso.onmicrosoft.com du följande kommando:

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

Kommandots utdata ser ut så här:

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> Om geoplatskoden i databasnamnet inte stämmer överens med värdet **MailboxRegion** sätts postlådan automatiskt till en kö för en relation och flyttas till den geoplats som anges av **värdet MailboxRegion** (Exchange Online letar efter en felaktig matchning mellan dessa egenskapsvärden).

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Flytta en befintlig molnbaserad postlåda till en viss geoplats

En användare med endast molnet är en användare som inte synkroniseras till klientorganisationen via AAD Anslut. Den här användaren skapades direkt i Azure AD. Använd **cmdletarna Get-MsolUser** och **Set-MsolUser** i Azure AD-modulen för Windows PowerShell för att visa eller ange den geoplats där en molnbaserad användares postlåda ska lagras.

Om du vill **visa värdet PreferredDataLocation** för en användare använder du följande syntax i Azure AD PowerShell:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Om du till exempel vill **visa värdet PreferredDataLocation** för michelle@contoso.onmicrosoft.com kör du följande kommando:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Om du vill **ändra värdet PreferredDataLocation** för ett användarobjekt med enbart molnet använder du följande syntax i Azure AD PowerShell:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Om du till exempel vill ställa in **värdet PreferredDataLocation** till den europeiska unionen (EUR) för användaren michelle@contoso.onmicrosoft.com, kör du följande kommando:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - Som nämndes tidigare kan du inte använda den här proceduren för synkroniserade användarobjekt från en lokal Active Directory. Du måste ändra värdet **för PreferredDataLocation i** Active Directory och synkronisera det med hjälp av AAD Anslut. Mer information finns i Azure Active Directory Anslut [synkronisering: Konfigurera önskad dataplats för Microsoft 365 resurser.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)
>
> - Hur lång tid det tar att flytta en postlåda till en ny geoplats beror på flera faktorer:
>
>   - Storlek och typ av postlåda.
>   - Antalet postlådor som flyttas.
>   - Tillgängligheten för flyttningsresurser.

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>Flytta en inaktiv postlåda till en viss geo

Du kan inte flytta inaktiva postlådor som bevaras i efterlevnadssyfte (till exempel postlådor för bevarande av juridiska skäl) genom att ändra deras **PreferredDataLocation-värde.** Så här flyttar du en inaktiv postlåda till en annan geopostlåda:

1. Återställa den inaktiva postlådan. Instruktioner finns i Återställa [en inaktiv postlåda.](../compliance/recover-an-inactive-mailbox.md)

2. Förhindra assistenten för hanterade mappar från att bearbeta den återställda postlådan genom att ersätta med namn, alias, konto eller e-postadress för postlådan och köra följande kommando \<MailboxIdentity\> [i Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. Tilldela en **licens Exchange Online abonnemang 2 till** den återskapade postlådan. Det här steget krävs för att placera postlådan i Bevarande av juridiska skäl igen. Anvisningar finns i [Tilldela licenser till användare.](../admin/manage/assign-licenses-to-users.md)

4. Konfigurera värdet **PreferredDataLocation** för postlådan enligt beskrivningen i föregående avsnitt.

5. När du har bekräftat att postlådan har flyttats till den nya geoplatsen placerar du den återskapade postlådan i Bevarande av juridiska skäl. Anvisningar finns i Placera [en postlåda i bevarande av juridiska skäl.](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold)

6. När du har verifierat att bevarande av juridiska skäl är på plats kan du låta assistenten för hanterade mappar bearbeta postlådan igen genom att ersätta med namn, alias, konto eller e-postadress för postlådan och köra följande kommando i \<MailboxIdentity\> [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. Gör postlådan inaktiv igen genom att ta bort användarkontot som är kopplat till postlådan. Instruktioner finns i Ta [bort en användare från organisationen.](../admin/add-users/delete-a-user.md) Det här steget släpper även Exchange Online abonnemang 2 för annan användning.

**Obs!** När du flyttar en inaktiv postlåda till en annan geoplats kan du påverka sökresultaten för innehåll eller möjligheten att söka i postlådan från den tidigare geoplatsen. Mer information finns i [Söka efter och exportera innehåll i multigeobaserade miljöer.](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Skapa nya molnbaserade postlådor på en viss geoplats

Om du vill skapa en ny postlåda på en viss geoplats måste du göra något av följande:

- Konfigurera **värdet preferredDataLocation** enligt beskrivningen i föregående Flytta en befintlig postlåda  med enbart molnet till ett visst område för [geoplats](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) innan du skapar postlådan i Exchange Online. Konfigurera till exempel värdet **PreferredDataLocation för** en användare innan du tilldelar en licens.

- Tilldela en licens samtidigt som du anger **värdet PreferredDataLocation.**

Om du vill skapa en ny molnlicensierad användare (inte AAD Anslut synkroniserad) på en viss geoplats använder du följande syntax i Azure AD PowerShell:

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

I det här exemplet skapas ett nytt användarkonto för Elizabeth Förgrundsman med följande värden:

- Användarens huvudnamn: ebrunner@contoso.onmicrosoft.com
- Förnamn: Elizabeth
- Efternamn: Så här gör du
- Visningsnamn: Elizabeth Förnamn
- Lösenord: slumpmässigt genererad och visas i resultatet av kommandot (eftersom vi inte använder parametern *Lösenord)*
- Licens: `contoso:ENTERPRISEPREMIUM` (E5)
- Plats: Australien (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Mer information om hur du skapar nya användarkonton och hittar värden för LicenseAssignment i Azure AD PowerShell finns i Skapa användarkonton med [PowerShell](create-user-accounts-with-microsoft-365-powershell.md) och Visa licenser och tjänster [med PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)

> [!NOTE]
> Om du använder Exchange Online PowerShell för att aktivera en postlåda och behöver att postlådan skapas direkt på den geoplats som anges i **PreferredDataLocation** måste du använda en Exchange Online-cmdlet, till exempel **Enable-Mailbox** eller **New-Mailbox** direkt mot molntjänsten. Om du använder cmdleten **Enable-RemoteMailbox** i en lokal Exchange PowerShell skapas postlådan på den centrala geoplatsen.

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>Introducera befintliga lokala postlådor på en viss geoplats

Du kan använda vanliga onboarding-verktyg och -processer för att migrera en postlåda från en lokal Exchange-organisation till Exchange Online, inklusive instrumentpanelen för migrering i [EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)och [cmdleten New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) i Exchange Online PowerShell.

Det första steget är att verifiera att ett användarobjekt finns för varje postlåda som ska introduceras, och kontrollera att rätt **PreferredDataLocation-värde** har konfigurerats i Azure AD. Onboarding-verktygen respekterar **värdet för PreferredDataLocation** och migrerar postlådorna direkt till den angivna geoplatsen.

Du kan också använda följande steg för att registrera postlådor direkt på en viss geoplats med hjälp av cmdleten [New-MoveRequest](/powershell/module/exchange/new-moverequest) i Exchange Online PowerShell.

1. Kontrollera att användarobjektet finns för varje postlåda som ska introduceras och att **PreferredDataLocation** är inställt på önskat värde i Azure AD. Värdet för **PreferredDataLocation synkroniseras** med attributet **MailboxRegion** för motsvarande e-postanvändarobjekt i Exchange Online.

2. Anslut direkt till den specifika satellit geoplatsen med hjälp av anslutningsanvisningarna från tidigare i det här avsnittet.

3. I Exchange Online PowerShell lagrar du de lokala administratörsautentiseringsuppgifter som används för att utföra en postlådemigrering i en variabel genom att köra följande kommando:

   ```powershell
   $RC = Get-Credential
   ```

4. I Exchange Online PowerShell skapar du en **ny New-MoveRequest** som liknar följande exempel:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. Upprepa steg #4 för varje postlåda du behöver migrera från lokala platser Exchange till den satellitgeoplats du är ansluten till.

6. Om du behöver migrera ytterligare postlådor till olika satellitplatser upprepar du steg 2 till 4 för varje specifik plats.

## <a name="multi-geo-reporting"></a>Multigeorapportering

**Rapporten Multi-Geo Usage Reports** Microsoft 365 administrationscentret visar antalet användare per geoplats. Rapporten visar användardistribution för den aktuella månaden och innehåller historiska data för de senaste 6 månaderna.

## <a name="see-also"></a>Se även

[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)