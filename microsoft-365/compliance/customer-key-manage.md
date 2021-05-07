---
title: Hantera kundnyckel
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: När du har ställt in kundnyckeln, lär dig hur du hanterar den genom att återställa AKV-nycklar och hantera behörigheter och dina principer för datakryptering.
ms.openlocfilehash: 284a8ff24fef2f7e8b807477c99e20aaf593552e
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162546"
---
# <a name="manage-customer-key"></a>Hantera kundnyckel

När du har ställt in kundnyckel för Office 365 kan du hantera dina nycklar enligt beskrivningen i den här artikeln. Läs mer om kundnyckel i relaterade ämnen.

## <a name="restore-azure-key-vault-keys"></a>Återställa Azure-nyckelvalvsnycklar

Innan du utför en återställning använder du de återställningsfunktioner som tillhandahålls av mjuk borttagning. Alla nycklar som används med kundnyckeln måste ha mjuk borttagning aktiverad. Mjuk borttagning fungerar som en papperskorg och tillåter återställning i upp till 90 dagar utan att du behöver återställa den. Återställning bör endast krävas i extrema eller ovanliga omständigheter, till exempel om nyckeln eller nyckelvalvet går förlorat. Om du måste återställa en nyckel för användning med Azure PowerShell kör du cmdleten Restore-AzureKeyVaultKey följande:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Till exempel:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Om nyckelns valv redan innehåller en nyckel med samma namn misslyckas återställningsåtgärden. Restore-AzKeyVaultKey alla viktiga versioner och alla metadata för nyckeln, inklusive nyckelnamnet.
  
## <a name="manage-key-vault-permissions"></a>Hantera behörigheter för nyckelvalv

Flera cmdlets är tillgängliga som gör att du kan visa och, om det behövs, ta bort behörigheter för nyckelvalv. Du kan behöva ta bort behörigheter, till exempel när en anställd lämnar gruppen. För var och en av dessa uppgifter använder du Azure PowerShell. Mer information om Azure Powershell finns i [Översikt över Azure PowerShell](/powershell/azure/).

Om du vill visa behörigheter för nyckelvalv kör du Get-AzKeyVault-cmdleten.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Till exempel:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Om du vill ta bort en administratörs behörigheter kör du Remove-AzKeyVaultAccessPolicy cmdleten:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Till exempel:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Hantera datakrypteringsprinciper (DEP) med kundnyckel

Kundnyckel hanterar DEP:er olika mellan de olika tjänsterna. Du kan till exempel skapa olika antal DEP för de olika tjänsterna.

**Exchange Online och Skype för företag:** Du kan skapa upp till 50 dep. Instruktioner finns i Skapa [en datakrypteringsprincip (DEP) för användning med Exchange Online och Skype för företag.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

**SharePoint Online, OneDrive för företag och Teams filer:** En dep gäller data på en geografisk plats, som även kallas _geo._ Om du använder multi-geofunktionen i Office 365 kan du skapa en DEP per geo. Om du inte använder multi-geo kan du skapa en DEP. Normalt skapar du DEP när du anger kundnyckel. Anvisningar finns i Skapa [en datakrypteringsprincip (DEP) för varje data SharePoint Online OneDrive för företag geo.](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Visa de DEP:er som du har skapat för Exchange Online och Skype för företag

Om du vill visa en lista över alla DEP:er som du har skapat för Exchange Online och Skype för företag med PowerShell-cmdleten Get-DataEncryptionPolicy slutför du dessa steg.

1. Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Om du vill returnera alla DEP:er i organisationen kör du Get-DataEncryptionPolicy-cmdleten utan några parametrar.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Mer information om Get-DataEncryptionPolicy cmdlet finns i [Get-DataEncryptionPolicy.](/powershell/module/exchange/get-dataencryptionpolicy)

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Tilldela en DEP innan du migrerar en postlåda till molnet

När du tilldelar Microsoft 365 krypteras innehållet i postlådan med den tilldelade dataleverantören under migreringen. Den här processen är mer effektiv än att migrera postlådan, tilldela DEP och sedan vänta på att krypteringen sker, som kan ta timmar eller möjligt dagar.

Om du vill tilldela en DEP till en postlåda innan du migrerar Office 365 den kör du cmdleten Set-MailUser i Exchange Online PowerShell:

1. Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Kör Set-MailUser cmdlet.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Där *GeneralMailboxOrMailUserIdParameter* anger en postlåda, och *DataEncryptionPolicyIdParameter* är ID för DEP. Mer information om Set-MailUser-cmdleten finns [i Set-MailUser.](/powershell/module/exchange/set-mailuser)

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Fastställa dep som tilldelats en postlåda

Ta reda på vilken DEP som tilldelats en postlåda med Get-MailboxStatistics cmdlet. Cmdleten returnerar en unik identifierare (GUID).
  
1. Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Där *GeneralMailboxOrMailUserIdParameter* anger en postlåda och DataEncryptionPolicyID returnerar GUID för DEP. Mer information om Get-MailboxStatistics-cmdlet finns i [Get-MailboxStatistics.](/powershell/module/exchange/get-mailboxstatistics)
  
2. Kör Get-DataEncryptionPolicy för att ta reda på eget namn på den dep som postlådan är tilldelad till.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Där *GUID* är det GUID som returneras av Get-MailboxStatistics-cmdleten i föregående steg.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Kontrollera att kundnyckeln har slutfört krypteringen

Oavsett om du precis har rullat en kundnyckel, tilldelat en ny DEP eller migrerat en postlåda kan du följa stegen i det här avsnittet för att säkerställa att krypteringen slutförs.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Verifiera krypteringen är klar för Exchange Online och Skype för företag

Det kan ta lite tid att kryptera en postlåda. Vi rekommenderar att du väntar 72 timmar innan du försöker verifiera krypteringen efter att du har ändrat en DEP eller första gången du tilldelar en dep till en postlåda.
  
Använd Get-MailboxStatistics för att avgöra om en postlåda är krypterad.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Egenskapen IsEncrypted returnerar värdet **true** om postlådan är krypterad och värdet **false** om postlådan inte krypteras.

Tiden för att slutföra postlådeflyttningar beror på storleken på postlådan. Om kundnyckeln inte helt har krypterat postlådan efter 72 timmar från det att du tilldelar en ny dep kontaktar du Microsofts support för att få hjälp. Cmdleten New-MoveRequest inte längre tillgänglig för lokala postlådeflyttningar. Mer information [finns i](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) det här meddelandet.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Verifiera krypteringen är klar för SharePoint Online, OneDrive för företag och Teams filer

Kontrollera status för kryptering genom att köra cmdleten Get-SPODataEncryptionPolicy följande:

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

Utdata från den här cmdleten innehåller:
  
- Primärnyckelns URI.

- Den sekundära nyckelns URI.

- Krypteringsstatus för geo. Möjliga tillstånd är:

  - **Avregistrerade:** Kryptering av kundnyckel har ännu inte tillämpats.

  - **Registrerar:** Kundnyckelkryptering har tillämpats och dina filer håller på att krypteras. Om nyckeln för geo registrerar dig visas även information om vilken procentandel av webbplatserna i geo som är slutförda så att du kan övervaka krypteringsförloppet.

  - **Registrerad:** Customer Key-kryptering har använts och alla filer på alla webbplatser har krypterats.

  - **Rullande:** En viktig roll är under utveckling. Om nyckeln för geo distribueras visas även information om vilken procentandel av webbplatserna som har slutfört nyckelrullningen så att du kan övervaka förloppet.

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Återställ från kundnyckel till Microsoft-hanterade nycklar

För kundnyckel på klientorganisationsnivå måste du kontakta Microsoft med en förfrågan om att "ta bort" från kundnyckeln. Begäran hanteras av teknikteamet för samtal.

För Kundnyckel på programnivå gör du det genom att ta bort en DEP från postlådor med PowerShell-cmdleten Set-mailbox och ange `DataEncryptionPolicy` till `$NULL` . När du kör den här cmdleten kopplas den tilldelade DEP:n bort och postlådan krypteras på nytt med den DEP som är kopplad till standardnycklar från Microsoft. Du kan inte ta bort dep som används av Microsoft-hanterade nycklar. Om du inte vill använda Microsoft hanterade nycklar kan du tilldela en annan kundnyckel DEP till postlådan.

Om du vill ta bort dep från en postlåda med hjälp Set-Mailbox PowerShell-cmdleten slutför du de här stegen.

1. Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Kör Set-Mailbox cmdlet.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Återkalla dina nycklar och starta datarensningssökvägen

Du styr återkallelsen av alla rotnycklar, inklusive tillgänglighetsnyckeln. Kundnyckel ger dig kontroll över olika aspekter av utgångsplaneringen av kraven på regler. Om du bestämmer dig för att återkalla dina nycklar för att tömma data och avsluta tjänsten tar tjänsten bort tillgänglighetsnyckeln när datarensningen har slutförts. Du kan inte utföra datarensning för en princip på klientorganisationsnivå.

Microsoft 365 granskar och verifierar datarensningssökvägen. Mer information finns i SSAE 18 SOC 2-rapporten som finns på [Service Trust Portal](https://servicetrust.microsoft.com/). Dessutom rekommenderar Microsoft följande dokument:

- [Guide för riskbedömning och efterlevnad för finansiella institutioner i Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Att tänka på när det gäller att avsluta planeringen i O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Sökvägen för datarensning skiljer sig något mellan de olika tjänsterna.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Återkalla dina kundnycklar och tillgänglighetsnyckeln för Exchange Online och Skype för företag

När du initierar datarensningssökvägen för Exchange Online och Skype för företag kan du ange en permanent begäran om datarensning för en DEP. Om du gör det tas krypterade data i postlådorna som deP har tilldelats permanent bort.

Eftersom du bara kan köra PowerShell-cmdleten mot en DEP i taget bör du överväga att tilldela en enda dep till alla dina postlådor innan du påbörjar datarensningssökvägen.

> [!WARNING]
> Använd inte datarensningssökvägen för att ta bort en delmängd av dina postlådor. Den här processen är endast avsedd för kunder som avslutar tjänsten.

Så här påbörjar du datarensningen:

1. Ta bort radbytes- och borttagningsbehörigheter för "O365 Exchange Online" från Azure-nyckelvalv.

2. Använd ett arbets- eller skolkonto med global administratörsbehörighet i din organisation och [anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

3. För varje DEP som innehåller postlådor som du vill ta bort kör du cmdleten [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) enligt följande.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Om kommandot inte fungerar bör du kontrollera att du har tagit bort behörigheterna Exchange Online båda nycklarna i Azure Key Vault enligt tidigare i den här uppgiften.När du har ställt in bytet PermanentDataPurgeRequested med cmdleten Set-DataEncryptionPolicy kan du inte längre tilldela den här DEP till postlådor.

4. Kontakta Microsofts support och begär Data Purge eDocument.

    Microsoft skickar ett juridiskt dokument till dig på din begäran för att bekräfta och auktorisera databorttagning. Den person i din organisation som registrerat sig som godkännare i FastTrack-erbjudandet under introduktionen måste signera dokumentet. Normalt är det här en chef eller annan utsedd person i ditt företag som har en laglig behörighet att signera arbetet för din organisations räkning.

5. När din representant har signerat den juridiska dokumentet ska du skicka tillbaka den till Microsoft (vanligtvis via en eDoc-signatur).

    När Microsoft har tagit emot det juridiska dokumentet kör Microsoft cmdlets för att starta datarensningen som först tar bort principen, markerar postlådorna för permanent borttagning och tar sedan bort tillgänglighetsnyckeln. När datarensningen har slutförts har data rensats bort, är otillgängliga för Exchange Online och kan inte återställas.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Återkalla dina kundnycklar och tillgänglighetsnyckeln för online SharePoint, OneDrive för företag och Teams filer

Så här påbörjar du datarensningen för SharePoint Online, OneDrive för företag och Teams genom att utföra följande steg:

1. Återkalla Azure-nyckelvalvsåtkomst. Alla nyckelvalvsadministratörer måste godkänna att återkalla åtkomsten.

   Du tar inte bort Azure Key Vault för SharePoint Online. Nyckelvalv kan delas mellan flera olika SharePoint Online-klientorganisation och DEP:er.

2. Kontakta Microsoft om du vill ta bort tillgänglighetsnyckeln.

    När du kontaktar Microsoft för att ta bort tillgänglighetsnyckeln skickar vi ett juridiskt dokument till dig. Den person i din organisation som registrerat sig som godkännare i FastTrack-erbjudandet under introduktionen måste signera dokumentet. Normalt är det här en chef eller annan person i företaget som har en laglig behörighet att signera arbetet åt din organisation.

3. När din representant signerar det juridiska dokumentet bör du skicka tillbaka det till Microsoft (oftast via en eDoc-signatur).

   När Microsoft får det juridiska dokumentet kör vi cmdlets för att utlösa datarensningen som utför kryptoborttagning av klientnyckeln, webbplatsnyckeln och alla enskilda nycklar per dokument, vilket oåterkalleligen bryter nyckelhierarkin. När cmdletarna för datarensning är klara har dina data rensats bort.

## <a name="related-articles"></a>Relaterade artiklar

- [Tjänstkryptering med kundnyckel](customer-key-overview.md)

- [Läs mer om tillgänglighetsnyckeln](customer-key-availability-key-understand.md)

- [Konfigurera kundnyckel](customer-key-set-up.md)

- [Rulla eller rotera Customer Key eller en tillgänglighetsnyckel](customer-key-availability-key-roll.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Tjänstkryptering](office-365-service-encryption.md)