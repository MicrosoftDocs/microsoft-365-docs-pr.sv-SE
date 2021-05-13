---
title: Rulla eller rotera Customer Key eller en tillgänglighetsnyckel
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
description: Lär dig hur du får kundens rotnycklar som lagras i Azure-nyckelvalvet som används med kundnyckeln. Tjänsterna omfattar Exchange Online, Skype för företag, SharePoint Online, OneDrive för företag och Teams filer.
ms.openlocfilehash: 892d77959bec1fb33b0ea6bcfaa8c530dd9b8911
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345124"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Rulla eller rotera Customer Key eller en tillgänglighetsnyckel

> [!CAUTION]
> Använd bara en krypteringsnyckel som du använder med Kundnyckel när dina säkerhets- och efterlevnadskrav kräver att du ska rulla nyckeln. Dessutom ska du inte ta bort några nycklar som är eller har kopplats till principer. När du använder tangenterna krypteras innehåll med tidigare nycklar. Till exempel krypteras aktiva postlådor om ofta, inaktiva, frånkopplade och inaktiverade postlådor fortfarande krypteras med de tidigare nycklarna. SharePoint Online säkerhetskopierar innehåll för återställnings- och återställningssyfte, så det kan fortfarande finnas arkiverat innehåll med hjälp av äldre nycklar.

## <a name="about-rolling-the-availability-key"></a>Om att distribuera tillgänglighetsnyckeln

Microsoft visar inte direkt kontroll över tillgänglighetsnyckeln för kunder. Du kan till exempel bara rulla (rotera) de nycklar som du äger i Azure Key Vault. Microsoft 365 att samla tillgänglighetsnycklarna i ett internt definierat schema. Det finns inget serviceavtal på servicenivå (SLA) för dessa nyckelrullningar. Microsoft 365 roterar tillgänglighetsnyckeln med hjälp Microsoft 365 en automatiserad och icke-manuell process. Microsoft-administratörer kan starta processen. Nyckeln förs över med automatiserade mekanismer utan direkt åtkomst till nyckellagret. Åtkomst till den hemliga lagret för tillgänglighetsnyckeln tillhandahålls inte till Microsoft-administratörer. Rullning av tillgänglighetsnyckel utnyttjar samma mekanism som användes för att först generera nyckeln. Mer information om tillgänglighetsnyckeln finns i [Förstå tillgänglighetsnyckeln](customer-key-availability-key-understand.md).

> [!IMPORTANT]
> Exchange Online och Skype för företag av tillgänglighetsnycklar kan distribueras effektivt av kunder som skapar en ny dep, eftersom en unik tillgänglighetsnyckel genereras för varje deP du skapar. Tillgänglighetsnycklar för SharePoint Online-, OneDrive för företag- och Teams-filer finns på skogsnivå och delas mellan DEP:er och kunder, vilket innebär att rullning bara sker enligt ett internt definierat schema hos Microsoft. För att minimera risken för att inte rullande tillgänglighetsnyckeln varje gång en ny DEP skapas, rullar SharePoint, OneDrive och Teams klientorganisationens mellanliggande nyckel (TIK), nyckeln radbruten av kundens rotnycklar och tillgänglighetsnyckel varje gång en ny DEP skapas.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Begära en ny version av varje befintlig rotnyckel som du vill slå upp

När du rullar en nyckel begär du en ny version av en befintlig nyckel. Om du vill begära en ny version av en befintlig nyckel använder du samma cmdlet [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey)med samma syntax som du använde för att skapa nyckeln från början. När du har distribuerat en nyckel som är kopplad till en datakrypteringsprincip (DEP) kör du en annan cmdlet för att säkerställa att Kundnyckel börjar använda den nya nyckeln. Gör detta steg i varje Azure Key Vault (AKV).

Till exempel:

1. Logga in på din Azure-prenumeration med Azure PowerShell. Anvisningar finns i [Logga in med Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Kör Add-AzKeyVaultKey cmdleten enligt följande exempel:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   I det här exemplet finns, eftersom en nyckel som heter **Contoso-CK-EX-NA-VaultA1-Key001** finns i **valvet Contoso-CK-EX-NA-VaultA1,** skapar cmdleten en ny version av nyckeln. Den här åtgärden bevarar de tidigare nyckelversionerna i versionshistoriken för nyckeln. Du behöver den föregående nyckelversionen för att dekryptera data som fortfarande krypteras. När du har rullat alla nycklar som är associerade med en DEP kör du en extra cmdlet för att säkerställa att kundnyckeln börjar använda den nya nyckeln. I följande avsnitt beskrivs cmdlet:arna i detalj.
  
## <a name="update-the-keys-for-multi-workload-deps"></a>Uppdatera nycklar för dep:er med flera arbetsbelastningar

När du rullar en av Azure Key Vault-tangenterna som är kopplade till en DEP som används med flera arbetsbelastningar, måste du uppdatera DEP så att de pekar på den nya nyckeln. Den här processen roterar inte tillgänglighetsnyckeln.

För att instruera kundnyckeln att använda den nya nyckeln för att kryptera flera arbetsbelastningar slutför du följande steg:

1. Använd ett arbets- eller skolkonto som har globala administratörs- eller efterlevnadsadministratörsbehörigheter i din organisation på din lokala dator och anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.

2. Kör Set-M365DataAtRestEncryptionPolicy cmdlet.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Refresh
   ```

Där *PolicyName* är namnet på eller ett unikt ID för principen. Till exempel Contoso_Global.

Exempel:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Refresh
```

## <a name="update-the-keys-for-exchange-online-deps"></a>Uppdatera nycklar för Exchange Online DEP

När du rullar en av Azure Key Vault-tangenterna som är kopplade till en DEP som används med Exchange Online och Skype för företag måste du uppdatera DEP:en så att den pekar på den nya nyckeln. Detta roterar inte tillgänglighetsnyckeln.

Om du vill instruera kundnyckeln att använda den nya nyckeln för att kryptera postlådor kör du cmdleten Set-DataEncryptionPolicy följande:

1. Kör Set-DataEncryptionPolicy cmdleten Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

2. Om du vill kontrollera värdet för egenskapen DataEncryptionPolicyID för postlådan använder du stegen i Avgöra vilken DEP som [tilldelats en postlåda.](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox) Värdet för den här egenskapen ändras när tjänsten tillämpar den uppdaterade nyckeln.
  
## <a name="update-the-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Uppdatera nycklar för SharePoint Online, OneDrive för företag och Teams filer

SharePoint Med Online kan du bara rulla en tangent i taget. Om du vill återställa båda tangenterna i ett nyckelvalv väntar du tills den första åtgärden har slutförts. Microsoft rekommenderar att du sprider dina åtgärder för att undvika det här problemet. När du rullar en av Azure Key Vault-tangenterna som är kopplade till en DEP som används med SharePoint Online och OneDrive för företag måste du uppdatera DEP:en så att den pekar på den nya nyckeln. Detta roterar inte tillgänglighetsnyckeln.

1. Kör Update-SPODataEncryptionPolicy cmdleten så här:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   När den här cmdleten startar nyckelrullningsåtgärden för SharePoint Online och OneDrive för företag slutförs inte åtgärden direkt.

2. Om du vill se förloppet för nyckelrullningsåtgärden kör du Get-SPODataEncryptionPolicy cmdlet så här:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Relaterade artiklar

- [Tjänstkryptering med kundnyckel för Office 365](customer-key-overview.md)

- [Konfigurera Customer Key för Office 365](customer-key-set-up.md)

- [Hantera Customer Key för Office 365](customer-key-manage.md)

- [Läs mer om tillgänglighetsnyckeln](customer-key-availability-key-understand.md)