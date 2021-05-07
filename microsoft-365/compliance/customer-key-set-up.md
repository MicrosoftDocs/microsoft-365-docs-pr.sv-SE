---
title: Konfigurera kundnyckel på programnivå
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
description: Lär dig konfigurera kundnyckel för Microsoft 365 för Exchange Online, Skype för företag, SharePoint Online, OneDrive för företag och Teams filer.
ms.openlocfilehash: a7a0c807b8778960d423d6b7d8afc20430ba89ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162190"
---
# <a name="set-up-customer-key-at-the-application-level"></a>Konfigurera kundnyckel på programnivå

Med kundnyckeln styr du organisationens krypteringsnycklar och konfigurerar sedan Microsoft 365 att använda dem för att kryptera dina data i vila i Microsofts datacenter. Med andra ord tillåter kundnyckel att kunderna lägger till ett krypteringslager som hör till dem, med sina nycklar. Data i vila omfattar data från Exchange Online och Skype för företag som lagras i postlådor och filer som lagras i SharePoint Online och OneDrive för företag.

Du måste konfigurera Azure innan du kan använda kundnyckel för Office 365. I den här artikeln beskrivs de steg du behöver följa för att skapa och konfigurera nödvändiga Azure-resurser och sedan anvisningar för hur du konfigurerar kundnyckeln i Office 365. När du har slutfört Azure-konfigurationen kan du avgöra vilken princip och därmed vilka nycklar som ska tilldelas till postlådor och filer i organisationen. Postlådor och filer som du inte tilldelar någon princip för kommer att använda krypteringsprinciper som kontrolleras och hanteras av Microsoft. Mer information om kundnyckel eller en allmän översikt finns i [Tjänstkryptering med kundnyckel i Office 365.](customer-key-overview.md)
  
> [!IMPORTANT]
> Vi rekommenderar starkt att du följer metodtipsen i den här artikeln. De kallas för **TIPS och** **VIKTIGT.** Med Kundnyckel får du kontroll över rotkrypteringsnycklar vars omfattning kan vara lika stor som hela organisationen. Det innebär att misstag som görs med dessa nycklar kan ha stor påverkan och kan leda till avbrott i tjänsten eller oåterkallelig förlust av dina data.
  
## <a name="before-you-set-up-customer-key"></a>Innan du anger kundnyckel

Innan du börjar bör du kontrollera att du har rätt licensiering för din organisation. Använd en betald, fakturerad Azure-prenumeration med hjälp företagsavtal tjänstleverantör eller molntjänstleverantör. Azure-prenumerationer som köpts med abonnemang med betala efter användning eller med kreditkort stöds inte för kundnyckel. Från den 1 april 2020 erbjuds kundnyckel i Office 365 i Office 365 E5, M365 E5, M365 E5 efterlevnad och M365 E5 Information Protection & Governance SKU:er. Office 365 Advanced Compliance SKU är inte längre tillgängligt för inköp av nya licenser. Befintliga Office 365 Advanced Compliance-licenser kommer att fortsätta stödjas.

Läs Dokumentationen för Azure Key Vault för att förstå begreppen och procedurerna [i den här](/azure/key-vault/) artikeln. Bekanta dig även med termerna som används i Azure, till exempel [Azure AD-klientorganisation.](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)

FastTrack används endast för att samla in information om klientorganisationen och tjänsten som krävs för att registrera en kundnyckel. Kundnyckelerbjudandena publiceras via FastTrack så att det är praktiskt för dig och våra partner att skicka in den information som krävs på samma sätt. FastTrack gör det också enkelt att arkivera de data som du tillhandahåller i erbjudandet.
  
Om du behöver mer support utöver dokumentationen kontaktar du Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) eller en Microsoft-partner för att få hjälp. Skicka feedback om kundnyckel, inklusive dokumentation, genom att skicka dina idéer, förslag och perspektiv för att customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Översikt över steg för att konfigurera kundnyckel

Konfigurera kundnyckel genom att slutföra dessa uppgifter i den angivna ordningen. Resten av den här artikeln innehåller detaljerade anvisningar för varje aktivitet, eller länkar till mer information för varje steg i processen.
  
**I Azure och Microsoft FastTrack:**
  
Du utför de flesta av dessa uppgifter genom att fjärransluta till Azure PowerShell. För bästa resultat bör du använda version 4.4.0 eller senare av Azure PowerShell.
  
- [Skapa två nya Azure-prenumerationer](#create-two-new-azure-subscriptions)

- [Registrera Azure-prenumerationer för att använda en obligatorisk bevarandeperiod](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  Registreringen kan ta från en till fem arbetsdagar.

- [Skicka en begäran om att aktivera kundnyckel för Office 365](#submit-a-request-to-activate-customer-key-for-office-365)

När du har skapat de två nya Azure-prenumerationerna måste du skicka in en begäran om kundnyckelerbjudandet genom att fylla i ett webbformulär som finns på Microsoft FastTrack-portalen. **FastTrack-teamet kan inte hjälpa dig med kundnyckeln. Office bara använder FastTrack-portalen** så att du kan skicka formuläret och för att hjälpa oss att spåra relevanta erbjudanden för kundnyckel.

- [Skapa ett Azure Key Vault premium i varje prenumeration](#create-a-premium-azure-key-vault-in-each-subscription)

- [Tilldela behörigheter till varje nyckelvalv](#assign-permissions-to-each-key-vault)

- [Aktivera och bekräfta en mjuk borttagning på nyckelvalven](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [Lägg till en nyckel i varje nyckelvalv genom att skapa eller importera en nyckel](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Kontrollera återställningsnivån för dina nycklar](#check-the-recovery-level-of-your-keys)

- [Back up Azure Key Vault](#back-up-azure-key-vault)

- [Verifiera konfigurationsinställningar för Azure-nyckelvalv](#validate-azure-key-vault-configuration-settings)

- [Hämta URI för varje Azure Key Vault-nyckel](#obtain-the-uri-for-each-azure-key-vault-key)

**I Office 365:**
  
Exchange Online och Skype för företag:
  
- [Skapa en datakrypteringsprincip (DEP) för användning Exchange Online och Skype för företag](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [Tilldela en dep till en postlåda](#assign-a-dep-to-a-mailbox)

- [Validera postlådekryptering](#validate-mailbox-encryption)

SharePoint Online och OneDrive för företag:
  
- [Skapa en datakrypteringsprincip (DEP) för SharePoint Online OneDrive för företag geo](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [Verifiera filkryptering för SharePoint Online, OneDrive för företag och Teams filer](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Utföra uppgifter i Azure Key Vault och Microsoft FastTrack för kundnyckel

Utför de här uppgifterna i Azure Key Vault. Du måste slutföra de här stegen oavsett om du har för avsikt att konfigurera kundnyckel för Exchange Online och Skype för företag eller för SharePoint Online-, OneDrive för företag- och Teams-filer eller för alla tjänster som stöds i Office 365.
  
### <a name="create-two-new-azure-subscriptions"></a>Skapa två nya Azure-prenumerationer

Kundnyckel kräver två Azure-prenumerationer. Vi rekommenderar att du skapar nya Azure-prenumerationer för användning med kundnyckeln. Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned. Du kan till exempel använda ett arbets- eller skolkonto som har global administratörsbehörighet i organisationen. Detaljerade anvisningar finns i [Registrera dig för Azure som organisation.](/azure/active-directory/fundamentals/sign-up-organization)
  
> [!IMPORTANT]
> Kundnyckel kräver två nycklar för varje datakrypteringsprincip (DEP). För att uppnå detta måste du skapa två Azure-prenumerationer. Vi rekommenderar att du har separata medlemmar i organisationen som konfigurerar en nyckel i varje prenumeration. Du bör endast använda dessa Azure-prenumerationer för att administrera krypteringsnycklar för Office 365. Det här skyddar organisationen om en av dina operatörer oavsiktligt, avsiktligt eller skadligt tar bort eller på annat sätt felmanar de nycklar som de ansvarar för.
>

Det finns ingen praktisk gräns för antalet Azure-prenumerationer som du kan skapa för din organisation. Om du följer de här metodtipsen minimeras påverkan på människor, samtidigt som du kan hantera resurser som används av kundnyckeln.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Skicka en begäran om att aktivera kundnyckel för Office 365

När du har slutfört Azure-stegen måste du skicka en erbjudandebegäran i [Microsoft FastTrack-portalen.](https://fasttrack.microsoft.com/) När du har skickat en begäran via FastTrack-webbportalen verifierar Microsoft Azure Key Vault-konfigurationsdata och kontaktinformation som du angett. De val du gör i erbjudandeformuläret om behörig sansvariga i din organisation är avgörande och nödvändiga för slutförande av registreringen av kundnyckel. Organisationens sansvariga säkerställer äktheten i alla begäran om att återkalla och förstöra alla nycklar som används med en policy för datakryptering av kundnycklar. Du måste göra det här steget en gång för att aktivera kundnyckel för Exchange Online och Skype för företag och en andra gång för att aktivera kundnyckel för SharePoint Online och OneDrive för företag.
  
Gör så här om du vill skicka ett erbjudande om att aktivera kundnyckel:
  
1. Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation och logga in på [Microsoft FastTrack-portalen.](https://fasttrack.microsoft.com/)

2. När du är inloggad bläddrar du till **instrumentpanelen**.

3. Välj **Distribuera** i navigeringsfältet **ELLER** välj Visa **alla distributionsresurser** på kortet Distribuera information och granska listan med aktuella erbjudanden. 

4. Välj informationskortet för erbjudandet som gäller dig:

   - **Exchange Online och Skype för företag:** Välj nyckeln **Begär krypteringsnyckel för Exchange onlineerbjudandet.**

   - **SharePoint Online, OneDrive och Teams filer:** Välj nyckeln **Begär krypteringsnyckel för Sharepoint och OneDrive** erbjudandet.

5. När du har granskat erbjudandeinformationen väljer du **Fortsätt till steg 2.**

6. Fyll i all tillämplig information och önskad information i erbjudandeformuläret. Var särskilt uppmärksam på dina val för vilka svarande i din organisation som du vill godkänna den permanenta och bestående krypteringsnyckeln och data. När du har slutfört formuläret väljer du **Skicka.**

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Registrera Azure-prenumerationer för att använda en obligatorisk bevarandeperiod

Den tillfälliga eller permanenta förlust av rotkrypteringsnycklar kan störa eller till och med skada tjänsteåtgärden, vilket kan leda till dataförlust. Därför krävs ett starkt skydd av de resurser som används med Kundnyckel. Alla Azure-resurser som används med customer key erbjuder skyddsmetoder utöver standardkonfigurationen. Du kan tagga eller registrera Azure-prenumerationer under en *obligatorisk bevarandeperiod.* En obligatorisk bevarandeperiod förhindrar omedelbar och oåterkallelig uppsägning av Azure-prenumerationen. De steg som krävs för att registrera Azure-prenumerationer under en obligatorisk bevarandeperiod kräver samarbete Microsoft 365 teamet. Detta kan ta från en till fem arbetsdagar. Tidigare kallades den obligatoriska lagringsperioden ibland för "Avbryt inte".
  
Innan du kontaktar Microsoft 365 behöver du göra följande för varje Azure-prenumeration som du använder med kundnyckel. Kontrollera att du har [Azure PowerShell Az-modulen](/powershell/azure/new-azureps-module-az) installerad innan du börjar.
  
1. Logga in med Azure PowerShell. Anvisningar finns i [Logga in med Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Kör cmdleten Register-AzProviderFeature registrera dina prenumerationer för att använda en obligatorisk bevarandeperiod. Slutför den här åtgärden för varje prenumeration.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Kontakta Microsoft för att slutföra processen. Kontakta SharePoint- OneDrive för företag om ditt [spock@microsoft.com](mailto:spock@microsoft.com). Om Exchange Online och Skype för företag kontaktar du [exock@microsoft.com](mailto:exock@microsoft.com). Inkludera följande information i e-postmeddelandet:

   **Ämne**: Kundnyckel för \<*Your tenant's fully qualified domain name*\>

   **Brödtext:** Ta med de prenumerations-IDn som du vill slutföra den obligatoriska lagringsperioden för och resultatet av prenumerationen Get-AzProviderFeature för varje prenumeration.

   Service Level Agreement (SLA) för slutförande av denna process är fem arbetsdagar när Microsoft har meddelats (och verifierats) att du har registrerat dina prenumerationer för att använda en obligatorisk bevarandeperiod.

4. När du får ett meddelande från Microsoft om att registreringen är klar kan du kontrollera status för din registrering genom att köra kommandot Get-AzProviderFeature nedan. Om kommandot Get-AzProviderFeature registrerat returneras värdet **Registrerad för egenskapen** **Registreringstillstånd.** Slutför det här steget för varje prenumeration.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Kör kommandot Register-AzResourceProvider slutför processen. Slutför det här steget för varje prenumeration.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Skapa ett Azure Key Vault premium i varje prenumeration

Stegen för att skapa ett nyckelvalv beskrivs i Komma igång med [Azure Key Vault,](/azure/key-vault/general/overview)som hjälper dig att installera och starta Azure PowerShell, ansluta till din Azure-prenumeration, skapa en resursgrupp och skapa ett nyckelvalv i den resursgruppen.
  
När du skapar ett nyckelvalv måste du välja en SKU: antingen Standard eller Premium. Standard-SKU gör att Azure-nyckelvalvsnycklar skyddas med programvara – det finns inget HSM-nyckelskydd (Hardware Security Module) – och SKU för Premium tillåter användning av HSMs för skydd av nyckelvalvsnycklar. Kundnyckel accepterar nyckelvalv som använder antingen SKU, men Microsoft rekommenderar starkt att du bara använder Premium SKU. Kostnaden för åtgärder med nycklar av båda typer är densamma, så den enda kostnadsskillnaden är kostnaden per månad för varje HSM-skyddad nyckel. Mer [information finns i Priser för nyckelvalv.](https://azure.microsoft.com/pricing/details/key-vault/)
  
> [!IMPORTANT]
> Använd SKU Premium tangentvalven och HSM-skyddade nycklar för produktionsdata och använd endast SKU-nyckelvalv och -nycklar för test- och valideringssyften.
  
För varje Microsoft 365 tjänst där du kommer att använda Kundnyckel skapar du ett nyckelvalv i var och en av de två Azure-prenumerationer som du skapade. Till exempel Exchange Online och Skype för företag eller SharePoint Online och OneDrive för företag, skapar du bara ett par valv. För att aktivera kundnyckel för Exchange Online och SharePoint Online skapar du två par nyckelvalv.
  
Använd en namngivningskonvention för nyckelvalv som återspeglar den avsedda användningen av deP som du associerar valven med. Se avsnittet Metodtips nedan för rekommendationer om namngivningskonventioner.
  
Skapa en separat, parad uppsättning valv för varje datakrypteringsprincip. När Exchange Online datakrypteringsprincipens omfattning väljs av dig när du tilldelar principen till postlådan. En postlåda kan bara ha en tilldelad princip och du kan skapa upp till 50 principer. Omfattningen av en princip SharePoint Online omfattar alla data inom en organisation på en geografisk plats eller _geo._

Skapandet av nyckelvalv kräver också att du skapar Azure-resursgrupper, eftersom nyckelvalv behöver lagringskapacitet (men små) och loggning av nyckelvalv, om det är aktiverat, genererar även lagrade data. Vi rekommenderar att du använder separata administratörer för att hantera varje resursgrupp, med den administration som överensstämmer med den uppsättning administratörer som hanterar alla relaterade kundnyckelresurser.
  
> [!IMPORTANT]
> För att maximera tillgängligheten ska nyckelvalven vara i regioner nära Microsoft 365 tjänst. Om din organisation Exchange Online Nordamerika kan du till exempel placera nyckelvalven i Nordamerika. Om din Exchange Online finns i Europa kan du placera nyckelvalven i Europa.
> 
> Använd ett vanligt prefix för nyckelvalv och inkludera en förkortning av användningen och omfattningen av nyckelvalv och nycklar (t.ex. för Contoso SharePoint-tjänsten där valven ska finnas i Nordamerika, ett möjligt par namn är Contoso-O365SP-NA-VaultA1 och Contoso-O365SP-NA-VaultA2. Valvnamn är globalt unika strängar i Azure, så du kan behöva prova varianter av dina önskade namn ifall de önskade namnen redan anspråks av andra Azure-kunder. Från och med juli 2017 går det inte att ändra namn på valv, så det är bäst att ha en skriftlig plan för installation och använda en andra person för att verifiera att planen körs korrekt.
> 
> Om möjligt skapar du dina valv i icke-parade regioner. Parade Azure-regioner erbjuder hög tillgänglighet över feldomäner för tjänster. Därför kan regionala par ses som varandras säkerhetskopieringsregion. Det innebär att en Azure-resurs som placeras i en region automatiskt blir felaktig genom det parade området. Därför innebär valet av regioner för två valv som används i en datakrypteringsprincip där regionerna är parade att bara ett totalt av två regioner med tillgänglighet används. De flesta geografiska områden har bara två regioner, så det går ännu inte att välja icke-parade regioner. Om möjligt väljer du två icke-parade regioner för de två valven som används med en datakrypteringsprincip. Det här drar nytta av totalt fyra regioner med tillgänglighet. Mer information finns i [Affärskontinui- och katastrofåterställning (BCDR): Azure-parade](/azure/best-practices-availability-paired-regions) regioner för en aktuell lista med regionala par.
  
### <a name="assign-permissions-to-each-key-vault"></a>Tilldela behörigheter till varje nyckelvalv

Du måste definiera tre separata uppsättningar behörigheter för varje nyckelvalv, beroende på din implementering. Du måste till exempel definiera en uppsättning behörigheter för vart och ett av följande:
  
- **Viktiga valv-administratörer** som håller i den dagliga hanteringen av ditt nyckelvalv för din organisation. Dessa uppgifter omfattar säkerhetskopiering, skapa, hämta, importera, lista och återställa.

  > [!IMPORTANT]
  > Den uppsättning behörigheter som tilldelas nyckelvalvsadministratörer inkluderar inte behörighet att ta bort nycklar. Det här är avsiktligt och en viktig övning. Vanligtvis raderas inte krypteringsnycklarna eftersom data raderas permanent. Det är alltid bra att inte ge den här behörigheten till nyckelvalvsadministratörer som standard. Reservera i stället detta för viktiga valv-deltagare och tilldela det bara till en administratör på kort sikt när en tydlig förståelse av konsekvenserna förstås.
  
  Om du vill tilldela de här behörigheterna till en användare i organisationen loggar du in på din Azure-prenumeration Azure PowerShell. Anvisningar finns i [Logga in med Azure PowerShell](/powershell/azure/authenticate-azureps).

- Kör cmdleten Set-AzKeyVaultAccessPolicy för att tilldela nödvändiga behörigheter.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Till exempel:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Viktiga valv-deltagare** som kan ändra behörigheter för själva Azure-nyckelvalvet. Du måste ändra de här behörigheterna när anställda lämnar eller går med i teamet. I den sällsynta fall där nyckelvalvsadministratörer verkligen behöver behörighet att ta bort eller återställa en nyckel måste du också ändra behörigheterna. Den här uppsättningen viktiga valv-deltagare måste tilldelas rollen **Deltagare på** nyckelvalvet. Du kan tilldela den här rollen med hjälp av Azure Resource Manager. Detaljerade instruktioner finns i Använda [Access-Role-Based för att hantera åtkomst till dina Azure-prenumerationsresurser](/azure/active-directory/role-based-access-control-configure)med hjälp av Access Control. Administratören som skapar en prenumeration har den här åtkomsten implicit, och möjligheten att tilldela andra administratörer till deltagarrollen.

- Om du tänker använda kundnyckel med Exchange Online och Skype för företag måste du ge behörighet till Microsoft 365 att använda nyckelvalvet åt Exchange Online och Skype för företag. På samma sätt, om du tänker använda kundnyckel med SharePoint Online och OneDrive för företag, måste du lägga till behörighet för Microsoft 365 att använda nyckelvalvet för SharePoint Online och OneDrive för företag. Om du vill ge Microsoft 365 behörighet kör du **cmdleten Set-AzKeyVaultAccessPolicy** med följande syntax:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Var:

    - *Valvnamn* är namnet på nyckelvalvet som du skapade.

    - Ersätt Exchange Online och Skype för företag det *Office 365 id:t* med`00000002-0000-0ff1-ce00-000000000000`

    - Ersätt SharePoint *APPID* OneDrive för företag, Teams online och Office 365 med`00000003-0000-0ff1-ce00-000000000000`

  Exempel: Ange behörigheter för Exchange Online och Skype för företag:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Exempel: Ange behörigheter för SharePoint Online, OneDrive för företag och Teams filer:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Aktivera och bekräfta en mjuk borttagning på nyckelvalven

När du snabbt kan återställa dina nycklar är det mindre sannolikt att det blir ett utökat avbrott i tjänsten på grund av oavsiktligt eller skadligt borttagna nycklar. Du måste aktivera den här konfigurationen, så kallad mjuk borttagning, innan du kan använda dina nycklar med kundnyckeln. Om du aktiverar Mjuk borttagning kan du återställa nycklar eller valv inom 90 dagar från borttagningen utan att behöva återställa dem från säkerhetskopian.
  
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

Om du vill importera en nyckel direkt till nyckelvalvet måste du ha en nCipher nShield-säkerhetsmodul för maskinvara.
  
Vissa organisationer föredrar den här metoden för att testa sina nycklar och sedan ger den här metoden även följande resultat:
  
- I verktygsuppsättningen som används för import ingår att intyget från nCipher att den nyckel Exchange-nyckel (KEK) som används för att kryptera den nyckel som du skapar inte kan exporteras och genereras i en äkta HSM som tillverkats av nCipher.

- Verktygsuppsättningen inkluderar intyg från nCipher att Azure Key Vault Security World också skapades på en äkta HSM som tillverkats av nCipher. Det här bevisar för dig att Microsoft även använder äkta nCipher-maskinvara.

Kontrollera med din säkerhetsgrupp för att avgöra om ovanstående deltagare krävs. Detaljerade steg för att skapa en lokal nyckel och importera den till ditt nyckelvalv finns i Skapa och överföra [HSM-skyddade](/azure/key-vault/keys/hsm-protected-keys)nycklar för Azure Key Vault. Använd Azure-anvisningarna för att skapa en nyckel i varje nyckelvalv.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Kontrollera återställningsnivån för dina nycklar

Microsoft 365 kräver att Azure Key Vault-prenumerationen är inställd på Avbryt inte och att nycklarna som används av Kundnyckel har mjuk borttagning aktiverad. Du kan bekräfta prenumerationsinställningarna genom att titta på återställningsnivån för dina nycklar.
  
Om du vill kontrollera återställningsnivån för en nyckel kör Azure PowerShell cmdleten i Get-AzKeyVaultKey följande:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Om egenskapen _Återställningsnivå_ returnerar något annat än värdet **Återställningsbar+SkyddadSubscription,** kontrollera att du har lagt prenumerationen i listan Avbryt inte och att du har mjuk borttagning aktiverat på vart och ett av dina nyckelvalv.
  
### <a name="back-up-azure-key-vault"></a>Back up Azure Key Vault

Omedelbart efter att du skapat en nyckel eller ändrat den, ska du säkerhetskopiera och lagra kopior av säkerhetskopian, både online och offline. Offlinekopior ska inte anslutas till något nätverk, till exempel i en fysisk säker eller kommersiell lagringsfunktion. Minst en kopia av säkerhetskopian ska lagras på en plats som blir tillgänglig vid en katastrof. Säkerhetskopierings blobbar är det enda sättet att återställa nyckelmaterial om en nyckel nyckel för nyckelvalv permanent raderas eller på annat sätt återges obrukbar. Nycklar som är externa till Azure-nyckelvalv och som importerats till Azure Key Vault är inte berättigade som en säkerhetskopia eftersom metadata som krävs för att kundnyckeln ska använda nyckeln inte finns med den externa nyckeln. Endast en säkerhetskopia från Azure-nyckelvalv kan användas för återställningsåtgärder med kundnyckel. Därför måste du skapa en säkerhetskopia av Azure-nyckelvalv efter att du har laddat upp eller skapat en nyckel.
  
Om du vill skapa en säkerhetskopia av en Azure Key Vault-nyckel kör du [cmdleten Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) enligt följande:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Kontrollera att utdatafilen använder suffixet `.backup` .
  
Utdatafilen från den här cmdleten är krypterad och kan inte användas utanför Azure Key Vault. Säkerhetskopian kan endast återställas till den Azure-prenumeration som säkerhetskopian togs från.
  
> [!TIP]
> För utdatafilen väljer du en kombination av ditt valvnamn och nyckelnamn. Det här gör att filnamnet själv beskriver det. Det säkerställer också att namn på säkerhetskopior inte kolliderar.
  
Till exempel:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Verifiera konfigurationsinställningar för Azure-nyckelvalv

Det är valfritt att validera innan du använder nycklar i en deP, men rekommenderas starkt. Om du använder steg för att konfigurera andra nycklar och valv än de som beskrivs i den här artikeln ska du verifiera hälsotillståndet för dina Azure Key Vault-resurser innan du konfigurerar kundnyckeln.
  
Så här kontrollerar du att dina nycklar `get` har , och aktiverade `wrapKey` `unwrapKey` åtgärder:
  
Kör [cmdleten Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) enligt följande:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Leta rätt på Access-principen och efter GUID (Exchange Online) eller GUID (SharePoint Online Identity) i utdata. Alla tre av ovanstående behörigheter måste visas under Behörigheter till nycklar.
  
Om konfiguration av åtkomstprincipen är felaktig kör du cmdleten Set-AzKeyVaultAccessPolicy följande:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Till exempel för Exchange Online och Skype för företag:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Till exempel kan du SharePoint Online och OneDrive för företag:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

Kontrollera att ett utgångsdatum inte är inställt för dina nycklar genom att köra [cmdlet:en Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) enligt följande:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Kundnyckel kan inte använda en förfallen nyckel. Åtgärder som försökts med en utgången nyckel kommer att misslyckas och kan leda till avbrott i tjänsten. Vi rekommenderar starkt att nycklar som används med kundnyckel inte har något utgångsdatum. När ett utgångsdatum har angetts kan det inte tas bort, men det kan ändras till ett annat datum. Om en nyckel måste användas med ett utgångsdatum ändrar du förfallodatumet till 9999-12-31. Nycklar med ett utgångsdatum som är inställt på ett annat datum än 9999-12-31 Microsoft 365 valideras.
  
Om du vill ändra ett utgångsdatum som har ställts in på ett annat värde än 9999-12-31 kör du cmdleten [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) enligt följande:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Ange inte utgångsdatum för krypteringsnycklar som du använder med kundnyckel.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Hämta URI för varje Azure Key Vault-nyckel

När du har ställt in nyckelvalven och lagt till dina nycklar kör du följande kommando för att hämta URI:en för nyckeln i varje nyckelvalv. Du måste använda dessa URI:er när du skapar och tilldelar varje deP senare, så spara informationen på ett säkert ställe. Kör det här kommandot en gång för varje nyckelvalv.
  
I Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Konfigurera kundnyckel för Exchange Online och Skype för företag

Innan du börjar bör du kontrollera att du har slutfört de uppgifter som krävs för att konfigurera Azure Key Vault. Mer [information finns i Utföra uppgifter i Azure-tangentvalvet och Microsoft FastTrack](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) för kundnyckel.
  
Om du vill konfigurera kundnyckel för Exchange Online och Skype för företag måste du utföra de här stegen genom att fjärransluta till Exchange Online med Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Skapa en datakrypteringsprincip (DEP) för användning Exchange Online och Skype för företag

En DEP är kopplad till en uppsättning nycklar som lagras i Azure Key Vault. Du tilldelar en dep till en postlåda i Microsoft 365. Microsoft 365 kryptera postlådan med hjälp av de nycklar som identifieras i principen. För att skapa DEP behöver du URI:erna för nyckelvalv du fick tidigare. Instruktioner [finns i Hämta URI för varje Azure Key Vault-nyckel.](#obtain-the-uri-for-each-azure-key-vault-key)
  
Kom ihåg! När du skapar en DEP anger du två nycklar i två olika Azure-nyckelvalv. Skapa de här nycklarna i två separata Azure-regioner för att säkerställa georedundans.
  
Följ de här stegen om du vill skapa DEP:
  
1. Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation på din lokala dator och anslut [till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) i ett Windows PowerShell fönster.

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
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
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
  
### <a name="validate-mailbox-encryption"></a>Validera postlådekryptering

Det kan ta lite tid att kryptera en postlåda. Vid tilldelning av första gången måste postlådan även helt flytta från en databas till en annan innan tjänsten kan kryptera postlådan. Vi rekommenderar att du väntar 72 timmar innan du försöker verifiera krypteringen efter att du har ändrat en DEP eller första gången du tilldelar en dep till en postlåda.
  
Använd Get-MailboxStatistics för att avgöra om en postlåda är krypterad.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Egenskapen IsEncrypted returnerar värdet **True** om postlådan är krypterad och värdet **false** om postlådan inte krypteras. Tiden för att slutföra postlådeflyttningar beror på antalet postlådor som du tilldelar en deP för första gången och storleken på postlådorna. Om postlådorna inte har krypterats efter en vecka från den tidpunkt då du tilldelade dep:et ska du kontakta Microsoft.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: Konfigurera kundnyckel för SharePoint Online, OneDrive för företag och Teams filer

Innan du börjar bör du kontrollera att du har slutfört de uppgifter som krävs för att konfigurera Azure Key Vault. Mer [information finns i Utföra uppgifter i Azure-tangentvalvet och Microsoft FastTrack](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) för kundnyckel.
  
Om du vill konfigurera kundnyckeln för SharePoint Online-, OneDrive för företag- och Teams-filer utför du de här stegen genom att fjärransluta till SharePoint Online med Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>Skapa en datakrypteringsprincip (DEP) för SharePoint Online OneDrive för företag geo

Du kopplar en DEP till en uppsättning nycklar som lagras i Azure Key Vault. Du använder en DEP för alla dina data på en geografisk plats, även kallad geo. Om du använder multi-geofunktionen i Office 365 kan du skapa en DEP per geo med möjlighet att använda olika nycklar per geo. Om du inte använder multi-geo kan du skapa en deP i organisationen för användning med SharePoint Online, OneDrive för företag och Teams filer. Microsoft 365 använder nycklar som identifieras i DATAkod för att kryptera data i geoinformationen. För att skapa DEP behöver du URI:erna för nyckelvalv du fick tidigare. Instruktioner [finns i Hämta URI för varje Azure Key Vault-nyckel.](#obtain-the-uri-for-each-azure-key-vault-key)
  
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

### <a name="validate-file-encryption"></a>Verifiera filkryptering

 Om du vill verifiera kryptering av SharePoint Online-, OneDrive för företag- och Teams-filer ansluter du till [SharePoint Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)och använder sedan cmdleten Get-SPODataEncryptionPolicy för att kontrollera status för din klientorganisation. Egenskapen _Delstat_ returnerar värdet registrerat **om** Customer Key-kryptering har aktiverats och alla filer på alla webbplatser har krypterats. Om kryptering fortfarande pågår returnerar den här cmdleten värdet av **att registrera**.

## <a name="related-articles"></a>Relaterade artiklar

- [Tjänstkryptering med kundnyckel](customer-key-overview.md)

- [Hantera kundnyckel](customer-key-manage.md)

- [Rulla eller rotera Customer Key eller en tillgänglighetsnyckel](customer-key-availability-key-roll.md)

- [Läs mer om tillgänglighetsnyckeln](customer-key-availability-key-understand.md)

- [Tjänstkryptering](office-365-service-encryption.md)