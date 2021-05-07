---
title: Kundnyckel för Microsoft 365 på klientorganisation (allmänt tillgänglig förhandsversion)
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
- m365solution-mip
- m365initiative-compliance
description: Lär dig konfigurera kundnyckel för dina data inom Microsoft 365 på innehavarnivå.
ms.openlocfilehash: 90ad08059d6b71583850368a70e32167b9defe88
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162923"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Översikt över kundnyckel för Microsoft 365 på innehavarnivå (offentlig förhandsversion)

Med nycklar som du anger kan du skapa en datakrypteringsprincip (DEP) och tilldela den till klientorganisationen. Den klientomfattande dep som du skapar krypterar följande data:

- Teams dina chattmeddelanden (1:1-chattar, gruppchattar, möteschattar och kanalkonversationer)
- Teams mediemeddelanden (bilder, kodstycken, videomeddelanden, ljudmeddelanden, wiki-bilder)
- Teams samtals- och mötesinspelningar som lagras Teams lagringsutrymme
- Teams chattaviseringar
- Teams förslag på chattar av Cortana
- Teams statusmeddelanden
- Information om användare och Exchange Online
- Exchange Online-postlådor som inte redan är krypterade nyckel-DEP:er för kunder på programnivå
- Exakt MIP-data (EDM) – (scheman för datafiler, regelpaket och salter som används för att hashtagga känsliga data)

För Microsofts informationsskydd Microsoft Teams krypteras nya data från den tidpunkt då du tilldelar klientorganisationen en kundnyckel på klientnivå. Den offentliga förhandsgranskningen stöder inte kryptering av tidigare data. I Exchange Online krypterar Kundnyckel alla befintliga och nya data.

Du kan skapa flera DEP:er per klientorganisation men du kan bara tilldela en dep i taget. När du tilldelar DEP påbörjas krypteringen automatiskt men tar lite tid att slutföra beroende på storleken på klientorganisationen.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>Principer på klientorganisationsnivå ger bredare kontroll till kundnyckeln för Microsoft 365

Om du redan har kundnyckel konfigurerad för Exchange Online och Sharepoint Online får du information om hur den nya offentliga förhandsversionen på innehavarnivå passar in.

Krypteringsprincipen på klientnivå som du skapar krypterar alla data för Microsoft Teams och Exchange Online i Microsoft 365. Men om du Exchange Online kundnyckel-DEP:er till enskilda postlådor, åsidosätter dock inte principen på klientnivå de dep:erna. Klientprincipen krypterar bara postlådor som inte redan har tilldelats en kundnyckel DEP på postlådenivå. När du krypterar en användarpostlåda med en deP på klientnivå krypteras allt innehåll. Mer information om vad som krypteras med en DEP på programnivå finns i [Tjänstkryptering med kundnyckel.](customer-key-overview.md)

## <a name="data-that-isnt-encrypted-with-customer-key-at-the-tenant-level"></a>Data som inte krypteras med kundnyckel på innehavarnivå

Kundnyckeln krypterar inte följande typer av data på innehavarnivå. I stället Microsoft 365 andra typer av kryptering för att skydda dessa data.

- Exchange onlinepostlådor som du redan har krypterat med en kundnyckel-DEP på programnivå. Postlådor som inte har en tilldelad kundnyckel DEP krypteras med deP på klientnivå. Den här ordningen innebär att vissa postlådor kan vara krypterade med en DEP på klientnivå och vissa postlådor som krypteras med dep:ar på programnivå.
- SharePoint och OneDrive för företag att använda kundnyckel på programnivå. Med en enda deP krypteras innehåll i SharePoint för en enskild geo.
- Microsoft Teams filer och vissa Teams samtals- och mötesinspelningar som sparats i OneDrive för företag och SharePoint krypteras av en SharePoint online-dep.

Alla arbetsbelastningar eller scenarier som inte stöds av kundnyckel för närvarande Microsoft 365.

- Andra Microsoft 365 arbetsbelastningar som Yammer, Planner och så vidare.
- Teams Livehändelser och fråge&A i livehändelser. Det Teams scenariot är det enda scenariot som inte krypteras av kundnyckel på innehavarnivå.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Konfigurera kundnyckel på klientnivå (offentlig förhandsversion)

Dessa steg liknar varandra men är inte identiska med stegen för att konfigurera kundnyckel på programnivå. Använd bara den här offentliga förhandsversionen med testdata i testklienterna. Använd inte den här versionen med produktionsdata eller produktionsmiljön. Om du redan har en produktionsdistribution av Kundnyckel kan du använda de här stegen för att konfigurera kundnyckeln på innehavarnivå i en testmiljö. När du har tilldelat en dep på klientorganisationsnivå kan du starta valideringsprocessen och kontakta m365ck@microsoft.com frågor och problem. Du kan också hitta dokumenterade verifieringssteg i den offentliga förhandsversionen av Verifieringsinstruktioner för [kryptering av data i](https://aka.ms/CustomerKey/PublicPreviewValidation)vila för Microsoft 365 .

Du utför de flesta av dessa uppgifter genom att fjärransluta till Azure PowerShell. För bästa resultat bör du använda version 4.4.0 eller senare av Azure PowerShell.

Innan du börjar:

- Du måste använda ett arbets- eller skolkonto som har rollen efterlevnadsadministratör för att konfigurera kundnyckel på innehavarnivå.
- Se till att du har rätt licensiering för din organisation. Använd en betald, fakturerad Azure-prenumeration med hjälp företagsavtal tjänstleverantör eller molntjänstleverantör. Azure-prenumerationer som köpts med abonnemang med betala efter användning eller med kreditkort stöds inte för kundnyckel. Från och med den 1 april 2020 erbjuds kundnyckel i Office 365 i Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance och Microsoft 365 E5 Information Protection & Governance SKU:er. Office 365 Advanced Compliance SKU är inte längre tillgängligt för nya licenser. Befintliga Office 365 Advanced Compliance-licenser kommer att fortsätta stödjas. Även om tjänsten kan aktiveras med minst en lämpligt licensierad användare under klientorganisationen bör du fortfarande se till att alla användare som drar nytta av tjänsten har lämpliga licenser.

### <a name="create-two-new-azure-subscriptions"></a>Skapa två nya Azure-prenumerationer

Kundnyckel kräver två nycklar för varje datakrypteringsprincip (DEP). Om du vill skapa två nycklar måste du skapa två Azure-prenumerationer. Vi rekommenderar att du har separata medlemmar i organisationen som konfigurerar en nyckel i varje prenumeration. Använd endast de här Azure-prenumerationerna för att administrera krypteringsnycklar för Microsoft 365. Om du följer de här riktlinjerna kan du skydda organisationen om en av dina operatörer oavsiktligt, avsiktligt eller skadligt tar bort, eller på annat sätt felmanar de nycklar som de ansvarar för.

Det finns ingen praktisk gräns för antalet Azure-prenumerationer som du kan skapa för din organisation. Om du följer metodfelet minimerar du risken för felet samtidigt som du hanterar de resurser som används av kundnyckeln.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrera Azure-prenumerationer för att använda en obligatorisk bevarandeperiod

Den tillfälliga eller permanenta förlust av rotkrypteringsnycklar kan störa eller till och med skada tjänsteåtgärden, vilket kan leda till dataförlust. Därför krävs ett starkt skydd av de resurser som används med Kundnyckel. Alla Azure-resurser som används med customer key erbjuder skyddsmetoder utöver standardkonfigurationen. Azure-prenumerationer kan märkas eller registreras på ett sätt som förhindrar omedelbar och oåterkallelig uppsägning. Den här processen kallas registrering för en obligatorisk bevarandeperiod. De steg som krävs för att registrera Azure-prenumerationer under en obligatorisk bevarandeperiod kräver samarbete med Microsoft. Den här processen kan ta upp till fem arbetsdagar. Tidigare kallades den här processen för Avbryt inte.
  
Innan du kontaktar Microsoft 365 behöver du utföra följande steg för varje Azure-prenumeration som du använder med kundnyckel. Kontrollera att du har [Azure PowerShell Az-modulen](/powershell/azure/new-azureps-module-az) installerad innan du börjar.

1. Logga in med Azure PowerShell. Anvisningar finns i [Logga in med Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Kör cmdleten Register-AzProviderFeature registrera dina prenumerationer för att använda en obligatorisk bevarandeperiod. Utför den här åtgärden för varje prenumeration.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Kontakta Microsoft för att slutföra processen på [m365ck@microsoft.com](mailto:m365ck@microsoft.com). Ta med följande innehåll i e-postmeddelandet:

   **Ämne**: Kundnyckel för \<*Your tenant's fully-qualified domain name*\>

   **Brödtext:** Prenumerations-IDt för vilka du vill att den obligatoriska bevarandetiden ska slutföras.
   Utdata från Get-AzProviderFeature för varje prenumeration.

   Service Level Agreement (SLA) för slutförande av denna process är fem arbetsdagar när Microsoft har meddelats (och verifierats) att du har registrerat dina prenumerationer för att använda en obligatorisk bevarandeperiod.

4. När du får ett meddelande från Microsoft om att registreringen är klar kan du kontrollera status för din registrering genom att köra kommandot Get-AzProviderFeature nedan. Om kommandot Get-AzProviderFeature registrerat returneras värdet **Registrerad för egenskapen** **Registreringstillstånd.** Utför den här åtgärden för varje prenumeration.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Kör kommandot Register-AzResourceProvider slutför processen. Utför den här åtgärden för varje prenumeration.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Skapa ett Azure Key Vault premium i varje prenumeration

Stegen för att skapa ett nyckelvalv beskrivs i Komma igång med [Azure Key Vault,](/azure/key-vault/general/overview)som hjälper dig att installera och starta Azure PowerShell, ansluta till din Azure-prenumeration, skapa en resursgrupp och skapa ett nyckelvalv i den resursgruppen.
  
När du skapar ett nyckelvalv måste du välja en SKU: antingen Standard eller Premium. Standard-SKU gör att Azure-nyckelvalvsnycklar skyddas med programvara – det finns inget HSM-nyckelskydd (Hardware Security Module) – och SKU för Premium tillåter användning av HSMs för skydd av nyckelvalvsnycklar. Kundnyckel accepterar nyckelvalv som använder antingen SKU, men Microsoft rekommenderar starkt att du bara använder Premium SKU. Kostnaden för åtgärder med nycklar av båda typer är densamma, så den enda kostnadsskillnaden är kostnaden per månad för varje HSM-skyddad nyckel. Mer [information finns i Priser för nyckelvalv.](https://azure.microsoft.com/pricing/details/key-vault/)
  
> [!IMPORTANT]
> Använd SKU Premium tangentvalven och HSM-skyddade nycklar för produktionsdata och använd endast SKU-nyckelvalv och -nycklar för test- och valideringssyften.

Använd ett vanligt prefix för nyckelvalv och inkludera en förkortning av användningen och omfattningen av nyckelvalvet och nyckelnycklarna. För Contoso-tjänsten där valven ska finnas i Nordamerika är ett möjligt par namn Contoso-O365-NA-VaultA1 och Contoso-O365-NA-VaultA2. Valvnamn är globalt unika strängar i Azure, så du kan behöva prova varianter av dina önskade namn ifall de önskade namnen redan anspråks av andra Azure-kunder. När de har konfigurerats kan namn på valv inte ändras, så det är bäst att ha en skriven plan för installation och använda en andra person för att verifiera att planen körs korrekt.

Om möjligt skapar du dina valv i icke-parade regioner. Parade Azure-regioner erbjuder hög tillgänglighet över feldomäner för tjänster. Därför kan regionala par ses som varandras säkerhetskopieringsregion. En Azure-resurs som placeras i ett område får automatiskt fel av den parade regionen. Om du väljer regioner för två valv som används i en datakrypteringsprincip där regionerna är parade innebär det att bara ett totalt av två regioner med tillgänglighet används. De flesta geografiska områden har bara två regioner, så det går ännu inte att välja icke-parade regioner. Om möjligt väljer du två icke-parade regioner för de två valven som används med en datakrypteringsprincip. Det här scenariot har fördelar från totalt fyra regioner med tillgänglighet. Mer information finns i [Affärskontinui- och katastrofåterställning (BCDR): Azure-parade](/azure/best-practices-availability-paired-regions) regioner för en aktuell lista med regionala par.

### <a name="assign-permissions-to-each-key-vault"></a>Tilldela behörigheter till varje nyckelvalv

För varje nyckelvalv måste du definiera tre separata uppsättningar behörigheter för kundnyckel, beroende på din implementering. Du måste till exempel definiera en uppsättning behörigheter för var och en av följande:
  
- **Nyckelvalvsadministratörer** som utför den dagliga hanteringen av ditt nyckelvalv för organisationen. Dessa uppgifter omfattar säkerhetskopiering, skapa, hämta, importera, lista och återställa.

  > [!IMPORTANT]
  > Den uppsättning behörigheter som tilldelas nyckelvalvsadministratörer inkluderar inte behörighet att ta bort nycklar. Det här är avsiktligt och en viktig övning. Vanligtvis raderas inte krypteringsnycklarna eftersom data raderas permanent. Det är alltid bra att inte ge den här behörigheten till nyckelvalvsadministratörer som standard. Reservera i stället detta för viktiga valv-deltagare och tilldela det bara till en administratör på kort sikt när en tydlig förståelse av konsekvenserna förstås.
  
  Om du vill tilldela de här behörigheterna till en användare i organisationen loggar du in på din Azure-prenumeration Azure PowerShell. Anvisningar finns i [Logga in med Azure PowerShell](/powershell/azure/authenticate-azureps).

   Kör cmdleten Set-AzKeyVaultAccessPolicy för att tilldela nödvändiga behörigheter.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Till exempel:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Viktiga valv-deltagare** som kan ändra behörigheter för själva Azure-nyckelvalvet. Du behöver ändra de här behörigheterna när anställda lämnar eller går med i teamet, eller i sällsynta fall som nyckelvalvsadministratörer verkligen behöver behörighet att ta bort eller återställa en nyckel. Den här uppsättningen viktiga valv-deltagare måste tilldelas rollen Deltagare på nyckelvalvet. Du kan tilldela den här rollen med hjälp av Azure Resource Manager. Detaljerade instruktioner finns i Använda [Access Control Role-Based att hantera åtkomsten](/azure/active-directory/role-based-access-control-configure) till dina Azure-prenumerationsresurser. Den administratör som skapar en prenumeration har den här behörigheten som standard, och möjligheten att tilldela andra administratörer rollen Deltagare.

- **Microsoft 365 data i en restkrypteringstjänst** som gör arbetet med kundnyckeln på klientnivå. Om du vill ge Microsoft 365 behörighet kör du **cmdleten Set-AzKeyVaultAccessPolicy** med följande syntax:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Var:

  - *Valvnamn* är namnet på nyckelvalvet som du skapade.

  Exempel: För Microsoft 365 data i tjänsten Rest Encryption ersätter du *Microsoft 365 appID* med`c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Aktivera och bekräfta en mjuk borttagning på nyckelvalven

När du snabbt kan återställa dina nycklar är det mindre sannolikt att det blir ett utökat avbrott i tjänsten på grund av oavsiktligt eller skadligt borttagna nycklar. Aktivera den här konfigurationen, så kallad Mjuk borttagning, innan du kan använda dina nycklar med kundnyckeln. Om du aktiverar Mjuk borttagning kan du återställa nycklar eller valv inom 90 dagar från borttagningen utan att behöva återställa dem från säkerhetskopian.
  
Aktivera Mjuk borttagning på nyckelvalven genom att utföra följande steg:
  
1. Logga in på din Azure-prenumeration med Windows PowerShell. Anvisningar finns i [Logga in med Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Kör [cmdleten Get-AzKeyVault.](/powershell/module/az.keyvault/get-azkeyvault) I det här exemplet *är valvnamnet* namnet på nyckelvalvet som du aktiverar mjuk borttagning för:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Bekräfta att mjuk borttagning har konfigurerats för nyckelvalvet genom att köra **cmdleten Get-AzKeyVault.** Om mjuk borttagning har konfigurerats korrekt för nyckelvalvet returnerar _egenskapen Mjuk_ borttagning aktiverad värdet **Sant:**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Lägg till en nyckel i varje nyckelvalv genom att skapa eller importera en nyckel

Det finns två sätt att lägga till nycklar i ett Azure-nyckelvalv: du kan skapa en nyckel direkt i nyckelvalv eller så kan du importera en nyckel. Att skapa en nyckel direkt i nyckelvalv är den mindre komplicerade metoden, medan importen av en nyckel ger total kontroll över hur nyckeln genereras. Använd RSA-tangenterna. Azure Key Vault har inte stöd för radbrytning och avklippning med ellipsiska kurvtangenter.
  
Om du vill skapa en nyckel direkt i nyckelvalvet kör du [cmdleten Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) enligt följande:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Var:

- *Valvnamn* är namnet på nyckelvalvet där du vill skapa nyckeln.

- *nyckelns* namn är det namn du vill ge den nya nyckeln.

  > [!TIP]
  > Namnnycklar med liknande namngivningskonventioner som beskrivs ovan för nyckelvalv. På så sätt kan strängen beskrivas på egen hand i verktyg som bara visar nyckelnamnet.
  
Om du har för avsikt att skydda nyckeln med en HSM ska du se till att du anger **HSM** som värde för _parametern Destination,_ annars anger du **Programvara**.

Ett exempel:
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>Kontrollera återställningsnivån för dina nycklar

Microsoft 365 kräver att Azure Key Vault-prenumerationen är inställd på Avbryt inte och att nycklarna som används av Kundnyckel har mjuk borttagning aktiverad. Du kan bekräfta de här inställningarna genom att titta på återställningsnivån för dina nycklar.
  
Om du vill kontrollera återställningsnivån för en nyckel kör Azure PowerShell cmdleten i Get-AzKeyVaultKey följande:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Om egenskapen _Återställningsnivå_ returnerar något annat än värdet **återställningsbar+Skyddadsubscription,** måste du granska den här artikeln och kontrollera att du har följt alla steg för att placera prenumerationen i listan Avbryt inte och att du har aktiverat "mjuk borttagning" på vart och ett av dina nyckelvalv. Sedan skickar du en skärmbild av resultatet i `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` e-post till m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Back up Azure Key Vault

Precis efter att du skapat en nyckel eller ändrat den ska du säkerhetskopiera nyckeln och spara kopior av säkerhetskopian, både online och offline. Anslut inte offlinekopior till något nätverk. Lagra dem istället i en fysisk säker eller kommersiell lagringsfunktion. Minst en kopia av säkerhetskopian bör lagras på en plats som är tillgänglig om en katastrof inträffar. Säkerhetskopierings blobbar är det enda sättet att återställa nyckelmaterial om en nyckel nyckel för nyckelvalv permanent raderas eller på annat sätt återges obrukbar. Nycklar som är externa till Azure Key Vault och som importerats till Azure Key Vault är inte berättigade som en säkerhetskopia eftersom de metadata som krävs för att kundnyckel ska använda nyckeln inte finns med den externa nyckeln. Endast en säkerhetskopia från Azure-nyckelvalv kan användas för återställningsåtgärder med kundnyckel. Därför är det viktigt att du gör en säkerhetskopia av Azure Key Vault när en nyckel har laddats upp eller skapats.
  
Om du vill skapa en säkerhetskopia av en Azure Key Vault-nyckel kör du [cmdleten Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) enligt följande:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Kontrollera att utdatafilen använder suffixet `.backup` .
  
Utdatafilen från den här cmdleten är krypterad och kan inte användas utanför Azure Key Vault. Säkerhetskopian kan endast återställas till den Azure-prenumeration som säkerhetskopian togs från.
  
Till exempel:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Verifiera konfigurationsinställningar för Azure-nyckelvalv

Det är valfritt att utföra en verifiering innan du använder tangenter i en deP, men rekommenderas starkt. I synnerhet om du använder steg för att konfigurera andra nycklar och valv än de som beskrivs i det här avsnittet bör du verifiera hälsotillståndet för dina Azure Key Vault-resurser innan du konfigurerar kundnyckel.
  
Kontrollera att dina nycklar har aktiverats genom att radbrytKey och unwrapKey aktiveras:
  
Kör [cmdleten Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) enligt följande:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Leta rätt på Access-principen och efter GUID (Microsoft 365) i utdata. Alla tre åtgärderna skaffa, radbrytNyckel och unwrapKey måste visas under Behörigheter till nycklar.
  
Om konfiguration av åtkomstprincipen är felaktig kör du cmdleten Set-AzKeyVaultAccessPolicy följande:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Exempel: För Microsoft 365 data i tjänsten Rest Encryption ersätter du *Microsoft 365 appID* med`c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Kontrollera att ett utgångsdatum inte har angetts för dina nycklar genom att köra [cmdlet:en Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) enligt följande:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

En utgången nyckel kan inte användas av kundnyckel och åtgärder som försökt med en utgången nyckel kommer att misslyckas och kan eventuellt resultera i avbrott i tjänsten. Vi rekommenderar starkt att nycklar som används med kundnyckel inte har något utgångsdatum. När ett utgångsdatum har angetts kan det inte tas bort, men det kan ändras till ett annat datum. Om en nyckel måste användas med ett utgångsdatum ändrar du förfallodatumet till 9999-12-31. Nycklar med ett utgångsdatum som är inställt på ett annat datum än 9999-12-31 Microsoft 365 valideras.
  
Om du vill ändra ett utgångsdatum som har ställts in på ett annat värde än 9999-12-31 kör du cmdleten [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) enligt följande:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Hämta URI för varje Azure Key Vault-nyckel

När du har slutfört alla steg i Azure för att konfigurera dina nyckelvalv och lagt till dina nycklar kör du följande kommando för att hämta URI:t för nyckeln i varje nyckelvalv. Du måste använda dessa URI:er när du skapar och tilldelar varje deP senare, så spara informationen på ett säkert ställe. Kom ihåg att köra det här kommandot en gång för varje nyckelvalv.
  
I Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Konfigurera principen för kryptering av kundnycklar för klientorganisationen

Du måste ha tilldelats behörigheter innan du kan köra dessa cmdlets. Även om den här artikeln innehåller alla parametrar för cmdlet:arna kan det hända att du inte har åtkomst till vissa parametrar om de inte ingår i de behörigheter som tilldelats dig. Du hittar de behörigheter som krävs för att köra en cmdlet eller parameter i din organisation i Hitta de behörigheter som krävs för att köra [Exchange cmdlet.](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)

### <a name="create-policy"></a>Skapa princip

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

Beskrivning: Aktivera efterlevnadsadministratören för att skapa en ny datakrypteringsprincip (DEP) med två AKV-rotnycklar. När den har skapats kan en princip sedan tilldelas med Set-M365DataAtRestEncryptionPolicyAssignment cmdlet. Det kan ta upp till 24 timmar innan de nya tangenterna verkställs när du först har tilldelning av tangenter eller roterat tangenterna. Om det tar mer än 24 timmar innan den nya dep:n verkställs kontaktar du Microsoft.

Exempel:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parametrar:

| Namn | Beskrivning | Valfritt (Y/N) |
|----------|----------|---------|
|Namn|Eget namn på datakrypteringsprincipen|N|
|AzureKeyIDs|Anger två URI-värden för Azure-nyckelvalvsnycklar, avgränsade med kommatecken, som ska kopplas till datakrypteringsprincipen|N|
|Beskrivning|Beskrivning av datakrypteringsprincipen|N|

### <a name="assign-policy"></a>Tilldela princip

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

Beskrivning: Den här cmdleten används för att konfigurera standardprincip för datakryptering. Den här principen används för att kryptera data över alla supportarbetsbelastningar.

Exempel:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

Parametrar:

| Namn | Beskrivning | Valfritt (Y/N) |
|----------|----------|---------|
-DataEncryptionPolicy|Anger vilken datakrypteringsprincip som måste tilldelas. anger du antingen principnamnet eller princip-ID: t.|N|

### <a name="modify-or-refresh-policy"></a>Ändra eller uppdatera princip

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Beskrivning: Cmdleten kan användas för att ändra eller uppdatera en befintlig princip. Den kan även användas för att aktivera eller inaktivera en princip. Det kan ta upp till 24 timmar innan de nya tangenterna verkställs när du först har tilldelning av tangenter eller roterat tangenterna. Om det tar mer än 24 timmar innan den nya dep:n verkställs kontaktar du Microsoft.

Exempel:

Inaktivera en datakrypteringsprincip.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

Uppdatera en datakrypteringsprincip.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

Parametrar:

| Namn | Beskrivning | Valfritt (Y/N) |
|----------|----------|---------|
|-Identity|Anger den datakrypteringsprincip som du vill ändra.|N|
|-Uppdatera|Använd uppdateringsknappen för att uppdatera datakrypteringsprincipen när du har roterat någon av de associerade nycklarna i Azure-nyckelvalvet. Du behöver inte ange något värde med den här växeln.|Y|
|-Enabled|Parametern Enabled aktiverar eller inaktiverar datakrypteringsprincipen. Innan du inaktiverar en princip måste du ta bort den från klientorganisationen. Giltiga värden är:</br > $true: Principen är aktiverad</br > $false: Principen är inaktiverad.|Y|
|-Name|Parametern Name anger det unika namnet för datakrypteringsprincipen.|Y|
|-Beskrivning|Beskrivningsparametern anger en valfri beskrivning för datakrypteringsprincipen.|Y|

### <a name="get-policy-details"></a>Få policyinformation

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Beskrivning: Den här cmdleten innehåller alla M365DataAtRest-krypteringsprinciper som skapas för klientorganisationen eller information om en viss princip.

Exempel:

Det här exemplet returnerar en sammanfattningslista med principerna för M365DatAtRest-kryptering i organisationen.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

Det här exemplet returnerar detaljerad information för datakrypteringsprincipen "NAM-princip".

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

Parametrar:

| Namn | Beskrivning | Valfritt (Y/N) |
|----------|----------|---------|
|-Identity|Anger den datakrypteringsprincip som du vill visa detaljerad information för.|Y|

### <a name="get-policy-assignment-info"></a>Hämta information om principtilldelning

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

Beskrivning: Den här cmdleten visar den princip som för närvarande är tilldelad till klientorganisationen.

## <a name="offboarding-from-customer-key-at-the-tenant-level"></a>Offboarding från kundnyckel på klientnivå

Om du behöver återgå till nycklar som hanteras av Microsoft kan du göra det. När du offboard krypteras dina data på samma sätt med standardkryptering som stöds av varje enskild arbetsbelastning. Till exempel Exchange Online standardkryptering med microsoft-hanterade nycklar.

Om du bestämmer dig för att ta bort klientorganisationen från kundnyckel på klientnivå kan du skicka [e m365ck@microsoft.com](mailto:m365ck@microsoft.com) med en begäran om att inaktivera tjänsten för klientorganisationen.

> [!IMPORTANT]
> Offboarding är inte samma sak som datarensning. En data tar bort permanent crypto-deletes din organisations data från Microsoft 365, offboarding gör det inte. Du kan inte utföra datarensning för en princip på klientorganisationsnivå. Mer information om datarensningssökväg finns i [Återkalla dina nycklar och starta datarensningen av sökvägen.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

## <a name="about-the-availability-key"></a>Om tillgänglighetsnyckeln

Mer information om tillgänglighetsnyckeln finns i [Läs mer om tillgänglighetsnyckeln](customer-key-availability-key-understand.md).

## <a name="key-rotation"></a>Nyckelrotation

Mer information om roterande eller rullningsnycklar som du använder med kundnycklar finns i [Rulla eller rotera en kundnyckel eller en tillgänglighetsnyckel.](customer-key-availability-key-roll.md) När du uppdaterar DEP för att använda den nya versionen av nycklarna kör du cmdleten Set-M365DataAtRestEncryptionPolicy som beskrivs tidigare i den här artikeln.

## <a name="related-articles"></a>Relaterade artiklar

- [Tjänstkryptering med kundnyckel](customer-key-overview.md)

- [Rulla eller rotera Customer Key eller en tillgänglighetsnyckel](customer-key-availability-key-roll.md)

- [Läs mer om tillgänglighetsnyckeln](customer-key-availability-key-understand.md)

- [Tjänstkryptering](office-365-service-encryption.md)
