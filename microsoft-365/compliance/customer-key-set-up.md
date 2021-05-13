---
title: Konfigurera kundnyckel
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
description: Läs mer om hur du ställer in Microsoft 365.
ms.openlocfilehash: e187c01a355cc9b926e892cb3326b5a527c714a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344680"
---
# <a name="set-up-customer-key"></a>Konfigurera kundnyckel

Med kundnyckeln styr du organisationens krypteringsnycklar och konfigurerar sedan Microsoft 365 att använda dem för att kryptera dina data i vila i Microsofts datacenter. Med andra ord tillåter kundnyckel att kunderna lägger till ett krypteringslager som hör till dem, med sina nycklar.

Konfigurera Azure innan du kan använda kundnyckel för Office 365. I den här artikeln beskrivs de steg du behöver följa för att skapa och konfigurera nödvändiga Azure-resurser och sedan anvisningar för hur du konfigurerar kundnyckeln i Office 365. När du har konfigurerat Azure kan du bestämma vilken princip och därmed vilka nycklar som ska tilldelas för att kryptera data i Microsoft 365 arbetsbelastningar i organisationen. Mer information om kundnyckel eller en allmän översikt finns i [Tjänstkryptering med kundnyckel i Office 365.](customer-key-overview.md)
  
> [!IMPORTANT]
> Vi rekommenderar starkt att du följer metodtipsen i den här artikeln. De kallas för **TIPS och** **VIKTIGT.** Med Kundnyckel får du kontroll över rotkrypteringsnycklar vars omfattning kan vara lika stor som hela organisationen. Det innebär att misstag som görs med dessa nycklar kan ha stor påverkan och kan leda till avbrott i tjänsten eller oåterkallelig förlust av dina data.
  
## <a name="before-you-set-up-customer-key"></a>Innan du anger kundnyckel

Innan du börjar bör du kontrollera att du har rätt Azure-prenumerationer och -licensiering för din organisation. Använd betalda Azure-prenumerationer med en företagsavtal eller en molntjänstleverantör. Kreditkortsbaserade betalningar accepteras inte. Godkänna och konfigurera kontobehoven för fakturering. Prenumerationer som du fick via kostnadsfri, utvärderingsversion, sponsring, MSDN-prenumerationer och de som finns under äldre support är inte berättigade.

Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance och Microsoft 365 E5 Information Protection & Governance SKU:er erbjuder kundnyckel. Office 365 Advanced Compliance SKU är inte längre tillgängligt för inköp av nya licenser. Befintliga Office 365 Advanced Compliance-licenser kommer att fortsätta stödjas.

Läs Dokumentationen för Azure Key Vault för att förstå begreppen och procedurerna [i den här](/azure/key-vault/) artikeln. Bekanta dig även med termerna som används i Azure, till exempel [Azure AD-klientorganisation.](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)
  
Om du behöver mer support utöver dokumentationen kontaktar du Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) eller en Microsoft-partner för att få hjälp. Skicka feedback om kundnyckel, inklusive dokumentation, genom att skicka dina idéer, förslag och perspektiv för att customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Översikt över steg för att konfigurera kundnyckel

Konfigurera kundnyckel genom att slutföra dessa uppgifter i den angivna ordningen. Resten av den här artikeln innehåller detaljerade anvisningar för varje aktivitet, eller länkar till mer information för varje steg i processen.
  
**I Azure och Microsoft FastTrack:**
  
Du utför de flesta av dessa uppgifter genom att fjärransluta till Azure PowerShell. För bästa resultat bör du använda version 4.4.0 eller senare av Azure PowerShell.
  
- [Skapa två nya Azure-prenumerationer](#create-two-new-azure-subscriptions)

- [Skicka en begäran om att aktivera kundnyckel för Office 365](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [Registrera Azure-prenumerationer för att använda en obligatorisk bevarandeperiod](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  Registreringen kan ta från en till fem arbetsdagar.

- [Skapa ett Azure Key Vault premium i varje prenumeration](#create-a-premium-azure-key-vault-in-each-subscription)

- [Tilldela behörigheter till varje nyckelvalv](#assign-permissions-to-each-key-vault)

- [Kontrollera att mjuk borttagning är aktiverat på nyckelvalven](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [Lägg till en nyckel i varje nyckelvalv genom att skapa eller importera en nyckel](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Kontrollera återställningsnivån för dina nycklar](#check-the-recovery-level-of-your-keys)

- [Back up Azure Key Vault](#back-up-azure-key-vault)

- [Verifiera konfigurationsinställningar för Azure-nyckelvalv](#validate-azure-key-vault-configuration-settings)

- [Hämta URI för varje Azure Key Vault-nyckel](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Utföra uppgifter i Azure Key Vault och Microsoft FastTrack för kundnyckel

Utför de här uppgifterna i Azure Key Vault. Du måste slutföra de här stegen för alla DEP:er du använder med kundnyckel.
  
### <a name="create-two-new-azure-subscriptions"></a>Skapa två nya Azure-prenumerationer

Kundnyckel kräver två Azure-prenumerationer. Vi rekommenderar att du skapar nya Azure-prenumerationer för användning med kundnyckeln. Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (Microsoft Azure Active Directory) tenant, you must create the new subscriptions using the same Azure AD tenant used with your organization where the DEPs will be assigned. Du kan till exempel använda ett arbets- eller skolkonto som har global administratörsbehörighet i organisationen. Detaljerade anvisningar finns i [Registrera dig för Azure som organisation.](/azure/active-directory/fundamentals/sign-up-organization)
  
> [!IMPORTANT]
> Kundnyckel kräver två nycklar för varje datakrypteringsprincip (DEP). För att uppnå detta måste du skapa två Azure-prenumerationer. Vi rekommenderar att du har separata medlemmar i organisationen som konfigurerar en nyckel i varje prenumeration. Du bör endast använda dessa Azure-prenumerationer för att administrera krypteringsnycklar för Office 365. Det här skyddar organisationen om en av dina operatörer oavsiktligt, avsiktligt eller skadligt tar bort eller på annat sätt felmanar de nycklar som de ansvarar för.

Det finns ingen praktisk gräns för antalet Azure-prenumerationer som du kan skapa för din organisation. Om du följer de här metodtipsen minimeras påverkan på människor, samtidigt som du kan hantera resurser som används av kundnyckeln.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Skicka en begäran om att aktivera kundnyckel för Office 365

När du har skapat de två nya Azure-prenumerationerna måste du skicka in rätt erbjudandeförfrågan för kundnyckel i [Microsoft FastTrack-portalen.](https://fasttrack.microsoft.com/) De val du gör i erbjudandeformuläret om auktoriserade beteckningar inom organisationen är avgörande och nödvändiga för att kunna slutföra registreringen av kundnyckel. De sansvariga i de valda rollerna i din organisation garanterar äktheten för alla förfrågningar om att återkalla och förstöra alla nycklar som används med en policy för datakryptering av kundnycklar. Du måste göra det här steget en gång för varje typ av kundnyckel DEP som du tänker använda för organisationen.

**FastTrack-teamet kan inte hjälpa dig med kundnyckeln. Office 365 bara fastTrack-portalen så att du kan skicka formuläret och hjälpa oss att spåra relevanta erbjudanden för kundnyckel. När du har skickat FastTrack-begäran kontaktar du motsvarande team för registrering av kundnyckel för att starta introduktionsprocessen.**
  
Gör så här om du vill skicka ett erbjudande om att aktivera kundnyckel:
  
1. Använd ett arbets- eller skolkonto som har global administratörsbehörighet i din organisation och logga in på [Microsoft FastTrack-portalen.](https://fasttrack.microsoft.com/)

2. När du är inloggad väljer du rätt domän.

3. För den valda domänen väljer **du Begär tjänster** i det övre navigeringsfältet och granskar listan med tillgängliga erbjudanden.

4. Välj informationskortet för erbjudandet som gäller dig:

   - **Flera Microsoft 365 arbetsbelastningar:** Välj nyckeln **Begär krypteringsnyckel för Microsoft 365** erbjudandet.

   - **Exchange Online och Skype för företag:** Välj nyckeln **Begär krypteringsnyckel för Exchange** erbjudandet.

   - **SharePoint Online, OneDrive och Teams filer:** Välj nyckeln **Begär krypteringsnyckel för ditt SharePoint och OneDrive för företag** erbjudande.

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

3. Kontakta Microsoft för att slutföra processen.

   - Om du vill göra det möjligt för kundnyckel att tilldela DEP till Exchange Online postlådor kontaktar [du exock@microsoft.com](mailto:exock@microsoft.com).

   - Om du vill att kundnyckeln ska kunna tilldela dep:er för att kryptera innehåll från SharePoint Online och OneDrive för företag (inklusive Teams-filer) för alla klientorganisationsanvändare kontaktar du [spock@microsoft.com](mailto:spock@microsoft.com).

   - Om du vill göra det möjligt för kundnyckel att tilldela dep:er för att kryptera innehåll i flera Microsoft 365-arbetsbelastningar (Exchange Online, Teams, MIP EDM) för alla användare i klientorganisationen kontaktar du [m365-ck@service.microsoft.com.](mailto:m365-ck@service.microsoft.com)

- Inkludera följande information i e-postmeddelandet:

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
  
För varje Microsoft 365 tjänst där du kommer att använda Kundnyckel skapar du ett nyckelvalv i var och en av de två Azure-prenumerationer som du skapade. Om du till exempel vill aktivera Kundnyckel för att använda DEPs för Exchange Online, SharePoint Online och scenarier med flera arbetsbelastningar, skapar du tre par nyckelvalv.
  
Använd en namngivningskonvention för nyckelvalv som återspeglar den avsedda användningen av deP som du associerar valven med. Se avsnittet Metodtips nedan för rekommendationer om namngivningskonventioner.
  
Skapa en separat, parad uppsättning valv för varje datakrypteringsprincip. När Exchange Online datakrypteringsprincipens omfattning väljs av dig när du tilldelar principen till postlådan. En postlåda kan bara ha en tilldelad princip och du kan skapa upp till 50 principer. Omfattningen av en princip SharePoint Online omfattar alla data inom en organisation på en geografisk plats eller _geo._ Omfattningen för en princip för flera arbetsbelastningar omfattar alla data i de arbetsbelastningar som stöds för alla användare.

Skapandet av nyckelvalv kräver också att du skapar Azure-resursgrupper, eftersom nyckelvalv behöver lagringskapacitet (men små) och loggning av nyckelvalv, om det är aktiverat, genererar även lagrade data. Vi rekommenderar att du använder separata administratörer för att hantera varje resursgrupp, med den administration som överensstämmer med den uppsättning administratörer som hanterar alla relaterade kundnyckelresurser.
  
> [!IMPORTANT]
> Om du vill maximera tillgängligheten placerar du nyckelvalven i regioner nära din Microsoft 365-tjänst Om din Exchange Online-organisation till exempel finns i Nordamerika kan du placera nyckelvalven i Nordamerika. Om din Exchange Online finns i Europa kan du placera nyckelvalven i Europa.
>
> Använd ett vanligt prefix för nyckelvalv och inkludera en förkortning av användningen och omfattningen av nyckelvalv och nycklar (t.ex. för Contoso SharePoint-tjänsten där valven ska finnas i Nordamerika, ett möjligt par namn är Contoso-CK-SP-NA-VaultA1 och Contoso-CK-SP-NA-VaultA2. Valvnamn är globalt unika strängar i Azure, så du kan behöva prova varianter av dina önskade namn ifall de önskade namnen redan anspråks av andra Azure-kunder. Från och med juli 2017 går det inte att ändra namn på valv, så det är bäst att ha en skriftlig plan för installation och använda en andra person för att verifiera att planen körs korrekt.
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
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Viktiga valv-deltagare** som kan ändra behörigheter för själva Azure-nyckelvalvet. Du måste ändra de här behörigheterna när anställda lämnar eller går med i teamet. I den sällsynta fall där nyckelvalvsadministratörer verkligen behöver behörighet att ta bort eller återställa en nyckel måste du också ändra behörigheterna. Den här uppsättningen viktiga valv-deltagare måste tilldelas rollen **Deltagare på** nyckelvalvet. Du kan tilldela den här rollen med hjälp av Azure Resource Manager. Detaljerade instruktioner finns i Använda [Access-Role-Based för att hantera åtkomst till dina Azure-prenumerationsresurser](/azure/active-directory/role-based-access-control-configure)med hjälp av Access Control. Administratören som skapar en prenumeration har den här åtkomsten implicit, och möjligheten att tilldela andra administratörer till deltagarrollen.

- **Behörigheter för Microsoft 365-program** för varje nyckelvalv du använder för kundnyckel, måste du ge wrapKey, unwrapKey och få behörigheter till motsvarande huvudnamn Microsoft 365 tjänst. 

Om du vill ge behörighet Microsoft 365 Service Principal kör du **cmdleten Set-AzKeyVaultAccessPolicy** med följande syntax:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Var:

   - *Valvnamn* är namnet på nyckelvalvet som du skapade.
   - Ersätt Exchange Online och Skype för företag det *Office 365 id:t* med`00000002-0000-0ff1-ce00-000000000000`
   - Ersätt SharePoint *APPID* OneDrive för företag, Teams online och Office 365 med`00000003-0000-0ff1-ce00-000000000000`
   - För policyn för flera arbetsbelastningar (Exchange, Teams MIP EDM) som gäller för alla klientorganisationsanvändare ersätter du *Office 365 appID* med`c066d759-24ae-40e7-a56f-027002b5d3e4`

  Exempel: Ange behörigheter för Exchange Online och Skype för företag:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Exempel: Ange behörigheter för SharePoint Online, OneDrive för företag och Teams filer:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a>Kontrollera att mjuk borttagning är aktiverat på nyckelvalven

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

Det finns två sätt att lägga till nycklar i ett Azure-nyckelvalv: du kan skapa en nyckel direkt i nyckelvalv eller så kan du importera en nyckel. Det är mindre komplicerat att skapa en nyckel direkt i nyckelvalv, men genom att importera en nyckel får du total kontroll över hur nyckeln genereras. Använd RSA-tangenterna. Azure Key Vault har inte stöd för radbrytning och avklippning med ellipsiska kurvtangenter.
  
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
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

Om du vill importera en nyckel direkt till nyckelvalvet måste du ha en nCipher nShield-säkerhetsmodul för maskinvara.
  
Vissa organisationer föredrar den här metoden för att testa sina nycklar och sedan ger den här metoden även följande resultat:
  
- I verktygsuppsättningen som används för import ingår att intyget från nCipher att den nyckel Exchange-nyckel (KEK) som används för att kryptera den nyckel som du skapar inte kan exporteras och genereras i en äkta HSM som tillverkats av nCipher.

- Verktygsuppsättningen inkluderar intyg från nCipher att Azure Key Vault Security World också skapades på en äkta HSM som tillverkats av nCipher. Det här bevisar att Microsoft även använder äkta nCipher-maskinvara.

Kontrollera med din säkerhetsgrupp för att avgöra om ovanstående deltagare krävs. Detaljerade steg för att skapa en lokal nyckel och importera den till ditt nyckelvalv finns i Skapa och överföra [HSM-skyddade](/azure/key-vault/keys/hsm-protected-keys)nycklar för Azure Key Vault. Använd Azure-anvisningarna för att skapa en nyckel i varje nyckelvalv.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Kontrollera återställningsnivån för dina nycklar

Microsoft 365 kräver att Azure Key Vault-prenumerationen är inställd på Avbryt inte och att nycklarna som används av Kundnyckel har mjuk borttagning aktiverad. Du kan bekräfta prenumerationsinställningarna genom att titta på återställningsnivån för dina nycklar.
  
Om du vill kontrollera återställningsnivån för en nyckel kör Azure PowerShell cmdleten i Get-AzKeyVaultKey följande:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Om egenskapen _Återställningsnivå_ returnerar något annat än värdet **Återställningsbar+SkyddadSubscription,** kontrollera att du har lagt prenumerationen i listan Avbryt inte och att du har mjuk borttagning aktiverat på vart och ett av dina nyckelvalv.
  
### <a name="back-up-azure-key-vault"></a>Back up Azure Key Vault

Omedelbart efter att du skapat en nyckel eller ändrat den, ska du säkerhetskopiera och lagra kopior av säkerhetskopian, både online och offline. Anslut inte offlinekopior till något nätverk. Spara dem i stället på en offlineplats, t.ex. i en fysisk säker eller kommersiell lagringsplats. Minst en kopia av säkerhetskopian bör lagras på en plats som är tillgänglig om en katastrof inträffar. Säkerhetskopierings blobbar är det enda sättet att återställa nyckelmaterial om en nyckel nyckel för nyckelvalv permanent raderas eller på annat sätt återges obrukbar. Nycklar som är externa till Azure-nyckelvalv och som importerats till Azure Key Vault är inte kvalificerade som en säkerhetskopia eftersom metadata som krävs för att kundnyckel ska kunna använda nyckeln inte finns med den externa nyckeln. Endast en säkerhetskopia från Azure-nyckelvalv kan användas för återställningsåtgärder med kundnyckel. Därför måste du skapa en säkerhetskopia av Azure-nyckelvalv efter att du har laddat upp eller skapat en nyckel.
  
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
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
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
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Till exempel kan du SharePoint Online och OneDrive för företag:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
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

När du har ställt in nyckelvalven och lagt till dina nycklar kör du följande kommando för att hämta URI:en för nyckeln i varje nyckelvalv. Du kommer att använda dessa URI:er när du skapar och tilldelar varje deP senare, så spara informationen på ett säkert ställe. Kör det här kommandot en gång för varje nyckelvalv.
  
I Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a>Nästa steg

När du har slutfört stegen i den här artikeln är du redo att skapa och tilldela DEP:er. Instruktioner finns i [Hantera kundnyckel.](customer-key-manage.md)

## <a name="related-articles"></a>Relaterade artiklar

- [Tjänst kryptering med kundnyckel](customer-key-overview.md)

- [Hantera kundnyckel](customer-key-manage.md)

- [Rulla eller rotera Customer Key eller en tillgänglighetsnyckel](customer-key-availability-key-roll.md)

- [Läs mer om tillgänglighetsnyckeln](customer-key-availability-key-understand.md)

- [Tjänstkryptering](office-365-service-encryption.md)