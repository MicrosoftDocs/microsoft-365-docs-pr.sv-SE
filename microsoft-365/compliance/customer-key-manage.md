---
title: Hantera kundnyckel
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: När du har ställt in kundnyckeln, lär dig hur du hanterar den genom att återställa AKV-nycklar och hantera behörigheter och skapa och tilldela principer för datakryptering.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345064"
---
# <a name="manage-customer-key"></a>Hantera kundnyckel

När du har konfigurerat kundnyckeln för Office 365, måste du skapa och tilldela en eller flera principer för datakryptering (DEP). När du har tilldelat dep:erna kan du hantera dina nycklar enligt beskrivningen i den här artikeln. Läs mer om kundnyckel i relaterade ämnen.

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>Skapa en dep för användning med flera arbetsbelastningar för alla användare i klientorganisationen

Innan du börjar bör du kontrollera att du har slutfört de uppgifter som krävs för att konfigurera Kunden. Mer information finns i [Konfigurera kundnyckel.](customer-key-set-up.md) För att skapa DEP behöver du URI:erna för nyckelvalvet som du fick under installationen. Mer information finns i [Hämta URI för varje Azure Key Vault-nyckel.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)

Följ de här anvisningarna om du vill skapa en deP för flera arbetsbelastningar:
  
1. Använd ett arbets- eller skolkonto som har globala administratörs- eller efterlevnadsadministratörsbehörigheter i din organisation på din lokala dator och anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.

2. Om du vill skapa en DEP använder du New-M365DataAtRestEncryptionPolicy-cmdleten.

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   Var:

   - *PolicyName* är det namn du vill använda för principen. Namn får inte innehålla blanksteg. Till exempel Contoso_Global.

   - *KeyVaultURI1* är URI:t för den första nyckeln i principen. Till exempel <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.

   - *KeyVaultURI2* är URI:t för den andra nyckeln i principen. Till exempel <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>. Avgränsa de två URI:erna med ett kommatecken och ett blanksteg.

   - *Principbeskrivning* är en användarvänlig beskrivning av principen som hjälper dig att komma ihåg vad principen gäller. Du kan ta med blanksteg i beskrivningen. Till exempel "Rotprincip för flera arbetsbelastningar för alla användare i klientorganisationen".

Exempel:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>Tilldela princip för flera arbetsbelastningar

Tilldela dep genom att använda Set-M365DataAtRestEncryptionPolicyAssignment cmdleten. När du tilldelar principen Microsoft 365 krypteras data med den nyckel som identifieras i dep.

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 Där *PolicyName* är namnet på principen. Till exempel Contoso_Global.

Exempel:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>Skapa en deP för användning Exchange Online postlådor

Innan du börjar bör du kontrollera att du har slutfört de uppgifter som krävs för att konfigurera Azure Key Vault. Mer information finns i [Konfigurera kundnyckel.](customer-key-set-up.md) Du utför de här stegen genom att fjärransluta till ett Exchange Online med Windows PowerShell.

En DEP är kopplad till en uppsättning nycklar som lagras i Azure Key Vault. Du tilldelar en dep till en postlåda i Microsoft 365. Microsoft 365 kryptera postlådan med hjälp av de nycklar som identifieras i principen. För att skapa DEP behöver du URI:erna för nyckelvalvet som du fick under installationen. Mer information finns i [Hämta URI för varje Azure Key Vault-nyckel.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)

Kom ihåg! När du skapar en DEP anger du två nycklar i två olika Azure-nyckelvalv. Skapa de här nycklarna i två separata Azure-regioner för att säkerställa georedundans.

Följ de här stegen om du vill skapa en deP för användning med en postlåda:
  
1. Använd ett arbets- eller skolkonto som har global administratörs- eller Exchange Online-administratörsbehörighet i din organisation på din lokala dator och anslut [till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.

2. Om du vill skapa en DEP använder du New-DataEncryptionPolicy-cmdleten genom att skriva följande kommando.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Var:

   - *PolicyName* är det namn du vill använda för principen. Namn får inte innehålla blanksteg. Till exempel USA_mailboxes.

   - *Principbeskrivning* är en användarvänlig beskrivning av principen som hjälper dig att komma ihåg vad principen gäller. Du kan ta med blanksteg i beskrivningen. Till exempel "Rotnyckel för postlådor i USA och dess territorier".

   - *KeyVaultURI1* är URI:t för den första nyckeln i principen. Till exempel <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* är URI:t för den andra nyckeln i principen. Till exempel <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Avgränsa de två URI:erna med ett kommatecken och ett blanksteg.

   Exempel:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

Detaljerad information om syntax och parametrar finns i [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).

### <a name="assign-a-dep-to-a-mailbox"></a>Tilldela en dep till en postlåda

Tilldela dep till en postlåda med hjälp av Set-Mailbox-cmdleten. När du tilldelar principen Microsoft 365 kryptera postlådan med nyckeln som identifieras i dep.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Där *MailboxIdParameter* anger en användarpostlåda. Mer information om Set-Mailbox-cmdleten finns [i Set-Mailbox](/powershell/module/exchange/set-mailbox).

I hybridmiljöer kan du tilldela en dep till de lokala e-postlådedata som synkroniseras till Exchange Online klientorganisation. Om du vill tilldela en DEP till denna synkroniserade postlådedata använder du cmdleten Set-MailUser postlådan. Mer information om e-postdata i hybridmiljön finns i lokala postlådor med Outlook för iOS och [Android med modern hybridautentisering.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Där *MailUserIdParameter* anger en e-postanvändare (kallas även e-postaktiverad användare). Mer information om Set-MailUser-cmdleten finns [i Set-MailUser.](/powershell/module/exchange/set-mailuser)

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>Skapa en deP för användning SharePoint Online OneDrive för företag och Teams filer

Innan du börjar bör du kontrollera att du har slutfört de uppgifter som krävs för att konfigurera Azure Key Vault. Mer information finns i [Konfigurera kundnyckel.](customer-key-set-up.md)
  
Om du vill konfigurera kundnyckeln för SharePoint Online-, OneDrive för företag- och Teams-filer utför du de här stegen genom att fjärransluta till SharePoint Online med Windows PowerShell.
  
Du kopplar en DEP till en uppsättning nycklar som lagras i Azure Key Vault. Du använder en DEP för alla dina data på en geografisk plats, även kallad geo. Om du använder multi-geofunktionen i Office 365 kan du skapa en DEP per geo med möjlighet att använda olika nycklar per geo. Om du inte använder multi-geo kan du skapa en deP i organisationen för användning med SharePoint Online, OneDrive för företag och Teams filer. Microsoft 365 använder nycklar som identifieras i DATAkod för att kryptera data i geoinformationen. För att skapa DEP behöver du URI:erna för nyckelvalvet som du fick under installationen. Mer information finns i [Hämta URI för varje Azure Key Vault-nyckel.](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key)
  
Kom ihåg! När du skapar en DEP anger du två nycklar i två olika Azure-nyckelvalv. Skapa de här nycklarna i två separata Azure-regioner för att säkerställa georedundans.
  
Om du vill skapa en DEP måste du fjärransluta till SharePoint Online med hjälp av Windows PowerShell.
  
1. Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation på din lokala [dator Anslut att SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)

2. I Microsoft Office SharePoint Online Management Shell kör du cmdleten Register-SPODataEncryptionPolicy följande:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Exempel:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   När du registrerar DEP börjar krypteringen på data i geo. Kryptering kan ta lite tid. Mer information om hur du använder den här parametern [finns i Register-SPODataEncryptionPolicy.](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps)

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>Visa de DEP:er som du har skapat Exchange Online postlådor

Om du vill visa en lista över alla DEPs du har skapat för postlådor använder du PowerShellGet-DataEncryptionPolicy-cmdleten.

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

Oavsett om du har rullat en kundnyckel, tilldelat en ny DEP eller migrerat en postlåda kan du följa stegen i det här avsnittet för att säkerställa att krypteringen slutförs.

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>Verifiera att krypteringen är Exchange Online postlådor

Det kan ta lite tid att kryptera en postlåda. För första gången som kryptering måste postlådan också helt flytta från en databas till en annan innan tjänsten kan kryptera postlådan.
  
Använd Get-MailboxStatistics för att avgöra om en postlåda är krypterad.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Egenskapen IsEncrypted returnerar värdet **True** om postlådan är krypterad och värdet **false** om postlådan inte krypteras. Tiden för att slutföra postlådeflyttningar beror på antalet postlådor som du tilldelar en deP för första gången och storleken på postlådorna. Om postlådorna inte har krypterats efter en vecka från den tidpunkt då du tilldelade dep:et ska du kontakta Microsoft.

Cmdleten New-MoveRequest inte längre tillgänglig för lokala postlådeflyttningar. Mer information [finns i](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) det här meddelandet.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Verifiera krypteringen är klar för SharePoint Online, OneDrive för företag och Teams filer

Kontrollera status för kryptering genom att köra cmdleten Get-SPODataEncryptionPolicy följande:

```PowerShell
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

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>Få information om de du använder med flera arbetsbelastningar

Gör så här för att få information om alla de de du har skapat för att använda med flera arbetsbelastningar:

1. Använd ett arbets- eller skolkonto som har globala administratörs- eller efterlevnadsadministratörsbehörigheter i din organisation på din lokala dator och anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.

   - Kör det här kommandot om du vill returnera listan över alla dep:er med flera arbetsbelastningar i organisationen.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - Kör det här kommandot om du vill returnera information om en viss DEP. Det här exemplet returnerar detaljerad information för den deP som heter "Contoso_Global".

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>Hämta information om dep-tilldelning med flera arbetsbelastningar

Följ de här stegen för att ta reda på vilken DEP som är tilldelad till din klientorganisation. 

1. Använd ett arbets- eller skolkonto som har globala administratörs- eller efterlevnadsadministratörsbehörigheter i din organisation på din lokala dator och anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.

2. Skriv det här kommandot.

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>Inaktivera en dep för flera arbetsbelastningar

Innan du inaktiverar en dep för flera arbetsbelastningar tar du bort dep från arbetsbelastningar i klientorganisationen. Inaktivera en deP som används med flera arbetsbelastningar genom att utföra följande steg:

1. Använd ett arbets- eller skolkonto som har globala administratörs- eller efterlevnadsadministratörsbehörigheter i din organisation på din lokala dator och anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.

2. Kör Set-M365DataAtRestEncryptionPolicy cmdlet.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

Där *PolicyName* är namnet på eller ett unikt ID för principen. Till exempel Contoso_Global.

Exempel:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

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

Flera cmdlets är tillgängliga som gör att du kan visa och, om det behövs, ta bort behörigheter för nyckelvalv. Du kan behöva ta bort behörigheter, till exempel när en anställd lämnar gruppen. För var och en av dessa uppgifter använder du Azure PowerShell. Mer information om Azure PowerShell finns i [Översikt över Azure PowerShell](/powershell/azure/).

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

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Återställ från kundnyckel till Microsoft-hanterade nycklar

Om du behöver återgå till nycklar som hanteras av Microsoft kan du göra det. När du offboard krypteras dina data på samma sätt med standardkryptering som stöds av varje enskild arbetsbelastning. Till exempel Exchange Online standardkryptering med microsoft-hanterade nycklar.

> [!IMPORTANT]
> Offboarding är inte samma sak som datarensning. En data tar bort permanent crypto-deletes din organisations data från Microsoft 365, offboarding gör det inte. Du kan inte rensa data för principen för flera arbetsbelastningar.

Om du bestämmer dig för att inte använda kundnyckel för att tilldela dep-adresser för flera arbetsbelastningar längre, måste du kontakta Microsofts support med en förfrågan om att "offboard" från kundnyckel. Be supportteamet att skicka en servicebegäran mot Microsoft 365 teamet med kundnyckel. Kontakta m365-ck@service.microsoft.com om du har frågor.

Om du inte längre vill kryptera enskilda postlådor med dep-adresser på postlådenivå kan du ta bort dep-adresser på postlådenivå från alla dina postlådor.

Om du vill ta bort postlåde-DEP:er använder Set-Mailbox PowerShell-cmdleten.

1. Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation [och anslut till Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Kör Set-Mailbox cmdlet.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

När du kör den här cmdleten kopplas den tilldelade DEP:n bort och postlådan krypteras på nytt med den DEP som är kopplad till standardnycklar som hanteras av Microsoft. Du kan inte ta bort dep som används av Microsoft-hanterade nycklar. Om du inte vill använda microsoft-hanterade nycklar kan du tilldela en annan kundnyckel DEP till postlådan.

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Återkalla dina nycklar och starta datarensningssökvägen

Du styr återkallelsen av alla rotnycklar, inklusive tillgänglighetsnyckeln. Kundnyckel ger dig kontroll över olika aspekter av utgångsplaneringen av kraven på regler. Om du bestämmer dig för att återkalla dina nycklar för att tömma data och avsluta tjänsten tar tjänsten bort tillgänglighetsnyckeln när datarensningen har slutförts. Detta stöds för kundnyckel-DEP som tilldelas till enskilda postlådor.

Microsoft 365 granskar och verifierar datarensningssökvägen. Mer information finns i SSAE 18 SOC 2-rapporten som finns på [Service Trust Portal](https://servicetrust.microsoft.com/). Dessutom rekommenderar Microsoft följande dokument:

- [Guide för riskbedömning och efterlevnad för finansiella institutioner i Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Att tänka på när det gäller att avsluta planeringen i O365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Rensning av DEP för flera arbetsbelastningar stöds inte för Microsoft 365 kundnyckel. Data i flera arbetsbelastningar används för att kryptera data över flera arbetsbelastningar för alla klientanvändare. Att tömma en sådan DEP kunde resultera i data från flera arbetsbelastningar blir otillgängliga. Om du bestämmer dig för att Microsoft 365 tjänster helt och hållet skulle du kunna följa den väg där klientorganisationen tas bort genom den dokumenterade processen. Se [hur du tar bort en klientorganisation i Azure Active Directoy.](/azure/active-directory/enterprise-users/directory-delete-howto)

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

- [Tjänst kryptering med kundnyckel](customer-key-overview.md)

- [Läs mer om tillgänglighetsnyckeln](customer-key-availability-key-understand.md)

- [Konfigurera kundnyckel](customer-key-set-up.md)

- [Rulla eller rotera Customer Key eller en tillgänglighetsnyckel](customer-key-availability-key-roll.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Tjänstkryptering](office-365-service-encryption.md)