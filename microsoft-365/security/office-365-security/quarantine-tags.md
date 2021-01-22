---
title: Karantäntaggar
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Administratörer kan ta reda på hur de kan använda karantäntaggar för att styra vad användarna kan göra med meddelanden i karantän.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6f18ad6ce1c8b12d38aef377ab663ca679a703e5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928908"
---
# <a name="quarantine-tags"></a>Karantäntaggar

> [!NOTE]
> De funktioner som beskrivs i den här artikeln är för närvarande i förhandsversion, är inte tillgängliga för alla och kan komma att ändras.

Med karantäntaggar i Exchange Online Protection (EOP) kan administratörer styra vad användare kan göra med meddelanden i karantän baserat på hur meddelandet kom i karantän.

EOP har traditionellt tillåtit eller förhindrat [](find-and-release-quarantined-messages-as-a-user.md) vissa nivåer av interaktivitet för meddelanden i karantän och [i skräppost-aviseringar för slutanvändare.](use-spam-notifications-to-release-and-report-quarantined-messages.md) Slutanvändarna kan till exempel visa och släppa meddelanden som satt i karantän genom skräppostfiltrering som skräppost eller massutskick, men de kan inte visa eller släppa meddelanden som satt i karantän som nätfiske i karantän.

För [funktioner som stöds](#step-2-assign-a-quarantine-tag-to-supported-features)anger karantäntaggar vad användare tillåts att göra i skräppost-aviseringar för slutanvändare och i de meddelanden i karantän som sätts i karantän (meddelanden där användaren är mottagare). Standardtaggar för karantän tilldelas automatiskt för att tillämpa historiska funktioner för slutanvändare på meddelanden i karantän. Du kan också skapa och tilldela anpassade karantäntaggar för att tillåta eller förhindra att slutanvändare utför särskilda åtgärder på meddelanden i karantän.

De enskilda behörigheterna kombineras i följande förinställda behörighetsgrupper:

- Ingen åtkomst
- Begränsad åtkomst
- Fullständig åtkomst

De tillgängliga enskilda behörigheterna och vad som ingår eller inte ingår i de förinställda behörighetsgrupperna beskrivs i följande tabell:

|Behörighet|Ingen åtkomst|Begränsad åtkomst|Fullständig åtkomst|
|---|:---:|:---:|:---:|
|**Allow sender** _(PermissionToAllowSender)_|||![Bockmarkering](../../media/checkmark.png)|
|**Blockera avsändare** _(PermissionToBlockSender)_||![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|**Delete** _(PermissionToDelete)_||![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|**Preview** _(PermissionToPreview)_||![Bockmarkering](../../media/checkmark.png)|![Bockmarkering](../../media/checkmark.png)|
|**Tillåt mottagare att släppa ett meddelande från karantän** _(PermissionToRelease)_|||![Bockmarkering](../../media/checkmark.png)|
|**Tillåt mottagare att begära att ett meddelande ska släppas från karantän** _(PermissionToRequestRelease)_||![Bockmarkering](../../media/checkmark.png)||
|

Om du inte gillar standardbehörigheterna i de förinställda behörighetsgrupperna kan du använda anpassade behörigheter när du skapar eller ändrar anpassade karantäntaggar. Mer information om vad varje behörighet gör finns i avsnittet om taggbehörighet [för](#quarantine-tag-permission-details) karantän senare i den här artikeln.

Du skapar och tilldelar karantäntaggar i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med Exchange Online-postlådor, fristående EOP PowerShell i EOP-organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Gå direkt till sidan **med taggar för karantän** genom att <https://protection.office.com/quarantineTags> öppna.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Om du vill visa, skapa, ändra eller ta bort  karantäntaggar  måste du vara medlem i rollerna Organisationshantering eller Säkerhetsadministratör i Säkerhets- [& Efterlevnadscenter.](permissions-in-the-security-and-compliance-center.md)

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a>Steg 1: Skapa karantäntaggar i Säkerhets- & Efterlevnadscenter

1. Gå till policyn för & och  välj sedan karantäntaggar i Säkerhets- och \>  **efterlevnadscenter.**

2. På sidan **Karantän-taggar** väljer du **Lägg till anpassad tagg.**

3. Guiden **Ny tagg** öppnas. Ange ett **kort men** unikt namn i fältet Taggnamn på sidan **Taggnamn.** Du måste identifiera och välja taggen efter namn i kommande steg. Klicka på Nästa när du är **klar.**

4. Välj **något av följande** värden på sidan För mottagarmeddelandeåtkomst:
   - **Ingen åtkomst**
   - **Begränsad åtkomst**
   - **Fullständig åtkomst**

   De enskilda behörigheterna som ingår i behörighetsgrupperna beskrivs tidigare i den här artikeln.

   Om du vill ange anpassade behörigheter **väljer du Ange specifik åtkomst (avancerat)** och konfigurerar följande inställningar:

     - **Välj inställning för släppåtgärd:** Välj ett av följande värden:
       - **Ingen utgivningsåtgärd:** Det här är standardvärdet.
       - **Tillåt mottagare att släppa ett meddelande från karantän**
       - **Tillåt mottagare att begära att ett meddelande ska släppas från karantän**

     - **Välj ytterligare åtgärder som mottagarna kan utföra för meddelanden** i karantän: Markera några, alla eller inget av följande värden:
       - **Ta bort**
       - **Förhandsgranska**
       - **Tillåt avsändare**
       - **Spärra avsändare**

   De här behörigheterna och deras påverkan på meddelanden i karantän [](#quarantine-tag-permission-details) och i skräppost-aviseringar för slutanvändare beskrivs i avsnittet om taggbehörighet för karantän senare i den här artikeln.

   Klicka på Nästa när du är **klar.**

5. Granska **inställningarna** på sammanfattningssidan som visas. Du kan klicka **på Redigera** för varje inställning för att ändra den.

   Klicka på Skicka när du är **klar.**

6. Klicka **på** Klar på bekräftelsesidan som visas.

Nu är du redo att tilldela karantäntaggen till en karantänfunktion enligt beskrivningen i [steg 2.](#step-2-assign-a-quarantine-tag-to-supported-features)

### <a name="create-quarantine-tags-in-powershell"></a>Skapa karantäntaggar i PowerShell

Om du hellre vill använda PowerShell för att skapa karantäntaggar ansluter du till Exchange Online PowerShell eller Exchange Online Protection PowerShell och använder cmdleten **New-QuarantineTag.** Du har två olika metoder att välja bland:

- Använd _parametern EndUserQuarantinePermissionsValue._
- Använd _parametern EndUserQuarantinePermissions._

De här metoderna beskrivs i följande avsnitt.

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>Använda parametern EndUserQuarantinePermissionsValue

Om du vill skapa en karantäntagg _med hjälp av parametern EndUserQuarantinePermissionsValue_ ska du använda följande syntax:

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

Parametern _EndUserQuarantinePermissionsValue_ använder ett decimalvärde som konverteras från ett binärt värde. Det binära värdet motsvarar de tillgängliga karantänbehörigheterna för slutanvändare i en viss ordning. För varje behörighet är värdet 1 lika med Sant och värdet 0 är falskt.

Den ordning och de värden som krävs för varje enskild behörighet i förinställda behörighetsgrupper beskrivs i följande tabell:

****

|Behörighet|Ingen åtkomst|Begränsad åtkomst|Fullständig åtkomst|
|---|:---:|:---:|:---:|
|PermissionToAllowSender|0|0|1|
|PermissionToBlockSender|0|1|1|
|PermissionToDelete|0|1|1|
|PermissionToDownload<sup>\*</sup>|0|0|0|
|PermissionToPreview|0|1|1|
|PermissionToRelease<sup>\*\*</sup>|0|0|1|
|PermissionToRequestRelease<sup>\*\*</sup>|0|1|0|
|PermissionToViewHeader<sup>\*</sup>|0|0|0|
|Binärt värde|00000000|01101010|11101100|
|Decimalvärde att använda|0|106|236|

<sup>\*</sup> Det här värdet är för närvarande alltid 0. För PermissionToViewHeader döljer inte värdet 0  knappen Visa meddelanderubrik i information om det karantän-meddelandet (knappen är alltid tillgänglig).

<sup>\*\*</sup> Ange inte 1 för båda dessa värden. Ange 0 för en till 1 och en annan eller ange 0 för båda.

I det här exemplet skapas ett nytt taggnamn för karantän, NoAccess, som tilldelar behörigheterna Ingen åtkomst enligt beskrivningen i föregående tabell.

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

Använd värdet 106 för begränsad åtkomst. För fullständig åtkomstbehörighet använder du värdet 236.

För anpassade behörigheter använder du föregående tabell för att få det binära värde som motsvarar de behörigheter du vill ha. Konvertera det binära värdet till ett decimalvärde och använd decimalvärdet för _parametern EndUserQuarantinePermissionsValue._

Detaljerad information om syntax och parametrar finns i [New-QuarantineTag.](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>Använda parametern EndUserQuarantinePermissions

Så här skapar du en karantäntagg med hjälp av _EndUserQuarantinePermissionsValue:_

A. Lagra ett behörighetsobjekt i karantän för en variabel med cmdleten **New-QuarantinePermissions.**

<p>

B. Använd variabeln som _värdet EndUserQuarantinePermissions_ i **kommandot Ny karantäntag.**

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>Steg A: Lagra ett behörighetsobjekt i karantän för en variabel

Använd följande syntax:

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

Standardvärdet för oanvända parametrar är, så du behöver `$false` bara använda parametrarna där du vill ange `$true` värdet.

Följande exempel visar hur du skapar behörighetsobjekt som motsvarar de förinställda behörighetsgrupperna:

- **Ingen åtkomst:**

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **Begränsad åtkomst:**

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **Fullständig åtkomst:**

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

Om du vill se de värden du har angett kör du variabelnamnet som ett kommando (till exempel kör `$NoAccess` kommandot).

För anpassade behörigheter ska du inte ange både parametrarna _PermissionToRelease_ och _PermissionToRequestRelease._ `$true` Ange en till `$true` och lämna den andra `$false` som, eller lämna båda `$false` som.

Du kan också ändra en befintlig objektvariabel för behörigheter när du har skapat den, men innan du använder den med hjälp av cmdleten **Set-QuarantinePermissions.**

Detaljerad information om syntax och parametrar finns [i New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) [och Set-QuarantinePermissions.](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>Steg B: Använda variabeln i New-QuarantineTag kommando

När du har skapat och lagrat behörighetsobjektet i en variabel använder du variabeln för parametervärdet _EndUserQuarantinePermission_ i **följande** kommando för karantäntag:

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

I det här exemplet skapas en ny karantäntagg med namnet LimitedAccess med `$LimitedAccess` behörighetsobjektet som beskrevs och skapades i föregående steg.

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

Detaljerad information om syntax och parametrar finns [i New-QuarantineTag.](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a>Steg 2: Tilldela en karantäntagg till funktioner som stöds

I _skyddsfunktioner_ som stöds som sätt meddelanden eller filer i karantän (automatiskt eller som en konfigurerbar åtgärd) kan du tilldela en karantäntagg till de tillgängliga karantänåtgärderna. Funktioner som sätt meddelanden i karantän och tillgängligheten för karantäntaggar beskrivs i följande tabell:

****

|Funktion|Stöds karantäntaggar?|Standardtaggar för karantän som används|
|---|:---:|---|
|[Principer för skydd mot skräppost:](configure-your-spam-filter-policies.md) <ul><li>**Spam** _(SpamAction)_</li><li>**Skräppost med högt förtroende** _(HighConfidenceSpamAction)_</li><li>**Nätfiskemeddelande** _(PhishSpamAction)_</li><li>**Nätfiskemeddelande med hög konfidens** _(HighConfidencePhishAction)_</li><li>**Massutskick** _(BulkSpamAction)_</li></ul>|Ja|<ul><li>DefaultSpamTag (fullständig åtkomst)</li><li>DefaultHighConfSpamTag (fullständig åtkomst)</li><li>DefaultPhishTag (Fullständig åtkomst)</li><li>DefaultHighConfPhishTag (ingen åtkomst)</li><li>DefaultBulkTag (fullständig åtkomst)</li></ul>
|Principer mot nätfiske: <ul><li>[Spoof Intelligence Protection](set-up-anti-phishing-policies.md#spoof-settings) _(AuthenticationFailAction)_</li><li>[Personifieringsskydd:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup> <ul><li>**Om e-post skickas av en imiterad användare** _(TargetedUserProtectionAction)_</li><li>**Om e-post skickas med en imiterad domän** _(TargetedDomainProtectionAction)_</li><li>**Postlådeinformation** \> **Om e-post skickas av en imiterad användare** _(MailboxIntelligenceProtectionAction)_</li></ul></li></ul></ul>|Nej|ej a|
|[Principer för skydd mot skadlig](configure-anti-malware-policies.md)programvara: Alla identifierade meddelanden sätts alltid i karantän.|Nej|ej a|
|[Säkra bifogade filer i SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md)|Nej|ej a|
|[E-postflödesregler](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transportregler) med åtgärden: Leverera meddelandet till den **värdinde karantänen** _(karantän)._|Nej|ej a|
|

<sup>\*</sup> Inställningar för personifieringsskydd är endast tillgängliga i principer mot nätfiske i Microsoft Defender för Office 365.

Om du är nöjd med slutanvändarbehörigheterna som anges av standardtaggarna för karantän behöver du inte göra något. Om du vill anpassa slutanvändarfunktionerna (tillgängliga knappar) i skräppost-aviseringar för slutanvändare eller i information i karantän kan du tilldela en anpassad karantäntagg.

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a>Tilldela karantäntaggar i principer för skydd mot skräppost i Säkerhets- & Efterlevnadscenter

Fullständiga instruktioner för hur du skapar och ändrar principer för skydd mot skräppost beskrivs i Konfigurera principer för skydd [mot skräppost i EOP.](configure-your-spam-filter-policies.md)

1. I Säkerhets- & Efterlevnadscenter går du till **Policy för** hantering \> **av** hot och väljer \> sedan **Skräppostskydd.** Eller <https://protection.office.com/antispam> öppna.

2. Hitta och välj en befintlig policy för skydd mot skräppost om du vill redigera eller skapa en ny policy för skydd mot skräppost.

3. Expandera avsnittet Skräppost- och massåtgärder i den **utfällande policyinformationen.**

4. Om du har  valt karantänmeddelande för åtgärden av en  tillgänglig skräppostfiltrering som avgörs är rutan Använd karantänprinciptagg tillgänglig så att du kan välja karantäntaggen för den aktuella bedömningspolicyn.

   **Obs!** När du skapar en ny princip visar en tom karantäntagg för en skräppostfiltrering vilken karantäntagg som används som standard för den bedömning som ska användas. När du senare redigerar principen ersätts de tomma värdena med de faktiska namnen på karantäntaggarna enligt beskrivningen i föregående tabell.

   ![Sätt taggar i karantän i en princip mot skräppost](../../media/quarantine-tags-in-anti-spam-policies.png)

5. Klicka på **Spara** när du är klar.

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a>Tilldela karantäntaggar i principer för skydd mot skräppost i PowerShell

Om du hellre vill använda PowerShell för att tilldela karantäntaggar i principer mot skräppost ska du ansluta till Exchange Online PowerShell eller Exchange Online Protection PowerShell och använda följande syntax:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**Anmärkningar**:

- Standardvärdet för parametern _HighConfidencePhishAction_ är karantän, så du behöver inte ange åtgärder för karantän för identifiering av nätfiske med hög konfidens i de nya principerna för skydd mot skräppost. För alla andra skräppostfiltreringsutskick i nya eller befintliga principer för skydd mot skräppost är karantäntaggen bara effektiv om åtgärdsvärdet är Karantän. Om du vill se åtgärdsvärdena i befintliga principer för skydd mot skräppost kör du följande kommando:

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  Mer information om standardåtgärdsvärdena och de rekommenderade åtgärdsvärdena för Standard och Strikt finns i [principinställningarna för EOP-skydd mot skräppost.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

- En skräppostfiltrering som skulle vara utan en motsvarande karantäntaggsparameter innebär att [standardtaggen](#step-2-assign-a-quarantine-tag-to-supported-features) för karantänen används för den aktuella aktuella frågan.

  Du behöver bara ersätta en standardtagg för karantän med en anpassad karantäntagg om du vill ändra standardkapaciteten för slutanvändare för meddelanden i karantän.

- En ny policy mot skräppost i PowerShell kräver en princip för skräppostfilter (inställningar) med cmdleten **New-HostedContentFilterPolicy** och en ny skräppostfilterregel (mottagarfilter) med cmdleten **New-HostedContentFilterRule.** Instruktioner finns i Använda [PowerShell för att skapa principer för skydd mot skräppost.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)

I det här exemplet skapas en ny policy för skräppostfilter med namnet Research Department med följande inställningar:

- Åtgärden för all skräppostfiltrering är inställd på karantän.
- Den anpassade karantäntaggen NoAccess som tilldelar **inga** åtkomstbehörigheter ersätter alla standardtaggar i karantän som inte redan tilldelar **Inga åtkomstbehörigheter** som standard.

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).

I det här exemplet ändras den befintliga policyn för skräppostfilter med namnet Human Resources. Åtgärden för karantänen för skräppost är inställd på karantän och den anpassade karantäntaggen NoAccess tilldelas.

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a>Konfigurera meddelandeinställningar för global karantän i Säkerhets- & Efterlevnadscenter

Med de globala inställningarna för karantäntaggar kan du anpassa skräppost-aviseringarna för slutanvändaren som skickas till mottagare av meddelanden som har satts i karantän. Mer information om dessa meddelanden finns i [skräppost-aviseringar för slutanvändaren.](use-spam-notifications-to-release-and-report-quarantined-messages.md)

1. Gå till policyn för & och  välj sedan karantäntaggar i Säkerhets- och \>  **efterlevnadscenter.**

2. Välj Globala **inställningar på** sidan **karantäntaggar.**

3. I **meddelandeinställningarna för karantän** som öppnas konfigurerar du några eller alla av följande inställningar:

   - **Använd mitt företags logotyp:** Välj det här alternativet om du vill ersätta standardlogotypen för Microsoft som används högst upp i skräppost-aviseringarna för slutanvändaren. Innan du gör det måste du följa instruktionerna i Anpassa [Microsoft 365-temat](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) för din organisation för att ladda upp din anpassade logotyp.

     Följande skärmbild visar en anpassad logotyp i en skräppost-avisering för slutanvändaren:

     ![En anpassad logotyp i en skräppost-avisering för slutanvändare](../../media/quarantine-tags-esn-customization-logo.png)

   - **Välj språk:** Skräppost-aviseringar för slutanvändare har redan lokaliserats baserat på mottagarens språkinställningar. Du kan ange anpassad text på olika språk för **värdena visningsnamn och** **ansvarsfriskrivning.**

     Välj minst ett språk i den första språkrutan och klicka sedan på **Lägg till.** Du kan välja flera språk genom att klicka **på Lägg till** efter varje. I rutan för avsnittsspråk visas alla språk som du har valt:

     ![Valda språk i rutan för det andra språket i meddelandeinställningarna för global karantän för karantäntaggar](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **Visningsnamn:** Anpassa avsändarens visningsnamn som används i skräppost-aviseringar för slutanvändaren.

     För varje språk som du har lagt till väljer du språket i den andra språkrutan (klicka inte på X) och anger det textvärde du vill ha i rutan **Visningsnamn.**

     Följande skärmbild visar det anpassade visningsnamnet i en skräppost-avisering för slutanvändaren:

     ![Ett anpassat visningsnamn för avsändare i en skräppost-avisering för slutanvändaren](../../media/quarantine-tags-esn-customization-display-name.png)

   - **Ansvarsfriskrivning:** Lägg till en anpassad ansvarsfriskrivning längst ned i skräppost-aviseringar för slutanvändaren. Lokaliserad text, **en ansvarsfriskrivning från din organisation:** inkluderas alltid först, följt av den text du anger.

     För varje språk som du har lagt till väljer du språket i den andra språkrutan (klicka inte på X) och ange det textvärde du vill ha i rutan **Ansvarsfriskrivning.**

     På följande skärmbild visas den anpassade ansvarsfriskrivningen i en skräppost-avisering för slutanvändare:

     ![En anpassad ansvarsfriskrivning längst ned i en skräppost-avisering för slutanvändare](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a>Visa karantäntaggar i Säkerhets- & Efterlevnadscenter

1. Gå till policyn för & och  välj sedan karantäntaggar i Säkerhets- \>  och **efterlevnadscenter.**

- Om du vill visa inställningarna för inbyggda eller anpassade karantäntaggar väljer du karantäntaggen i listan (markera inte kryssrutan).

- Om du vill visa de globala inställningarna väljer **du Globala inställningar**

### <a name="view-quarantine-tags-in-powershell"></a>Visa karantäntaggar i PowerShell

Om du hellre vill använda PowerShell för att visa karantäntaggar gör du något av följande:

- Om du vill visa en sammanfattningslista över alla inbyggda eller anpassade taggar kör du följande kommando:

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- Om du vill visa inställningarna för inbyggda eller anpassade karantäntaggar ersätter du med namnet på \<TagName\> karantäntaggen och kör följande kommando:

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- Om du vill visa de globala inställningarna kör du följande kommando:

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a>Ta bort karantäntaggar i Säkerhets- & Efterlevnadscenter

**Anmärkningar**:

- Du kan inte ta bort inbyggda karantäntaggar.

- Innan du tar bort en anpassad karantäntagg kontrollerar du att den inte används. Kör till exempel följande kommando i PowerShell:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  Om karantäntaggen används ersätter du [den tilldelade karantäntaggen](#step-2-assign-a-quarantine-tag-to-supported-features) innan du tar bort den.

1. Gå till policyn för & och  välj sedan karantäntaggar i Säkerhets- och \>  **efterlevnadscenter.**

2. På sidan **Karantän-taggar** väljer du den anpassade karantäntagg du vill ta bort och klickar på Ta **bort taggen.**

3. Klicka **på Ta bort** tagg i bekräftelsedialogrutan som visas.

### <a name="remove-quarantine-tags-in-powershell"></a>Ta bort karantäntaggar i PowerShell

Om du hellre vill använda PowerShell för att ta bort en anpassad karantäntagg ersätter du med namnet på karantäntaggen \<TagName\> och kör följande kommando:

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

Detaljerad information om syntax och parametrar finns i [Ta bort karantän.](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)

## <a name="quarantine-tag-permission-details"></a>Information om taggbehörighet i karantän

I följande avsnitt beskrivs effekterna av förinställda behörighetsgrupper och enskilda behörigheter i information om meddelanden i karantän och i skräppost-aviseringar för slutanvändare.

### <a name="preset-permissions-groups"></a>Förinställda behörighetsgrupper

De enskilda behörigheterna som ingår i förinställda behörighetsgrupper visas i tabellen i början av den här artikeln.

#### <a name="no-access"></a>Ingen åtkomst

Om karantäntaggen tilldelar **inga åtkomstbehörigheter** (inga behörigheter) får användarna fortfarande vissa grundläggande funktioner:

- **Information om meddelanden i karantän:** **Knappen Visa meddelanderubrik** är alltid tillgänglig.

  ![Tillgängliga knappar i meddelandeinformation i karantän om karantäntaggen ger användaren inga åtkomstbehörigheter](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **Skräppost-aviseringar för slutanvändare:** **Knappen** Granska som tar användaren till meddelandet i karantän är alltid tillgänglig.

  ![Tillgängliga knappar i skräppostmeddelandet för slutanvändaren om karantäntaggen ger användaren inga åtkomstbehörigheter](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>Begränsad åtkomst

Om karantäntaggen tilldelar **behörigheterna** begränsad åtkomst får användarna följande funktioner:

- **Information om meddelanden i karantän:** Följande knappar är tillgängliga:
  - **Begär version**
  - **Visa meddelanderubrik**
  - **Förhandsgranskningsmeddelande**
  - **Spärra avsändare**
  - **Ta bort från karantän**

  ![Tillgängliga knappar i meddelandeinformation i karantän om karantäntaggen ger användaren begränsad åtkomstbehörighet](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **Skräppost-aviseringar för slutanvändare:** Följande knappar är tillgängliga:
  - **Spärra avsändare**
  - **Granska**

  ![Tillgängliga knappar i skräppostmeddelandet för slutanvändaren om karantäntaggen ger användaren begränsad åtkomstbehörighet](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>Fullständig åtkomst

Om karantäntaggen tilldelar **fullständig åtkomst** (alla tillgängliga behörigheter) får användarna följande funktioner:

- **Information om meddelanden i karantän:** Följande knappar är tillgängliga:
  - **Släpp meddelande**
  - **Visa meddelanderubrik**
  - **Förhandsgranskningsmeddelande**
  - **Spärra avsändare**
  - **Tillåt avsändare**
  - **Ta bort från karantän**

  ![Tillgängliga knappar i meddelandeinformation i karantän om karantäntaggen ger användaren fullständig åtkomst](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **Skräppost-aviseringar för slutanvändare:** Följande knappar är tillgängliga:
  - **Spärra avsändare**
  - **Version**
  - **Granska**

  ![Tillgängliga knappar i skräppostmeddelandet för slutanvändaren om karantäntaggen ger användaren fullständig åtkomst](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>Enskilda behörigheter

> [!NOTE]
> Kom ihåg att användarna alltid får knapparna som beskrivs i [avsnittet Ingen](#no-access) åtkomst. Dessa knappar ingår inte i de enskilda behörighetsbeskrivningarna.

#### <a name="allow-sender-permission"></a>Tillåt avsändarbehörighet

Tillåt **avsändarbehörighet** _(PermissionToAllowSender)_ styr åtkomsten till knappen som gör att användare enkelt kan lägga till avsändaren i karantän i sin lista med betrodda avsändare.

- **Information om meddelanden i karantän:**
  - **Tillåt att avsändarens** behörighet är **aktiverad: Knappen Tillåt** avsändare är tillgänglig.
  - **Tillåt avsändarbehörighet** inaktiverad: **Knappen Tillåt** avsändare är inte tillgänglig.

- **Skräppost-aviseringar för slutanvändare:** Ingen effekt.

Mer information om listan Betrodda avsändare finns i Förhindra att betrodda avsändare [blockeras](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) och Använda Exchange Online PowerShell för att konfigurera samlingen med listor över betrodda [avsändare för en postlåda.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)

#### <a name="block-sender-permission"></a>Blockera avsändarbehörighet

Behörigheten **Blockera avsändare** _(PermissionToBlockSender)_ styr åtkomsten till knappen som gör att användare enkelt kan lägga till avsändaren i karantän i listan Spärrade avsändare.

- **Information om meddelanden i karantän:**
  - **Behörigheten** Blockera avsändare aktiverad: **Knappen Spärra** avsändare är tillgänglig.
  - **Spärra avsändarbehörighet** inaktiverad: **Knappen Spärra** avsändare är inte tillgänglig.

- **Skräppost-aviseringar för slutanvändare:**
  - **Behörigheten Blockera** avsändare inaktiverad: **Knappen Spärra** avsändare är inte tillgänglig.
  - **Behörigheten** Blockera avsändare aktiverad: **Knappen Spärra** avsändare är tillgänglig.

Mer information om listan Spärrade avsändare [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) finns i Spärra meddelanden från någon och Använda Exchange Online PowerShell för att konfigurera samlingen med listor över betrodda avsändare [för en postlåda.](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)

#### <a name="delete-permission"></a>Ta bort behörighet

Behörigheten **Ta** bort _(PermissionToDelete)_ styr möjligheten för användare att ta bort sina meddelanden (meddelanden där användaren är mottagare) från karantän.

- **Information om meddelanden i karantän:**
  - **Ta** bort behörighet aktiverad: **Knappen Ta bort från** karantän är tillgänglig.
  - **Ta** bort behörighet inaktiverad: **Knappen Ta bort från** karantän är inte tillgänglig.

- **Skräppost-aviseringar för slutanvändare:** Ingen effekt.

#### <a name="preview-permission"></a>Förhandsgranskningsbehörighet

_Förhandsgranskningsbehörigheten (PermissionToPreview)_ styr möjligheten för användare att förhandsgranska sina meddelanden i karantän. 

- **Information om meddelanden i karantän:**
  - **Behörighet** för förhandsgranskning aktiverad: **Knappen Förhandsgranskningsmeddelande** är tillgänglig.
  - **Förhandsgranskningsbehörighet** inaktiverad: **Knappen Förhandsgranskningsmeddelande** är inte tillgänglig.

- **Skräppost-aviseringar för slutanvändare:** Ingen effekt.

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>Tillåt mottagare att släppa ett meddelande från karantän-behörighet

Allow **recipients to release a message from quarantine** permission _(PermissionToRelease)_ controls the ability of users to release their quarantined messages directly and without the approval of an admin.

- **Information om meddelanden i karantän:**
  - Behörighet aktiverad: Knappen **Släpp meddelande** är tillgänglig.
  - Behörighet inaktiverad: **Knappen Släpp meddelande** är inte tillgänglig.

- **Skräppost-aviseringar för slutanvändare:**
  - Behörighet aktiverad: **Knappen Släpp** är tillgänglig.
  - Behörighet inaktiverad: **Knappen** Släpp är inte tillgänglig.

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>Tillåt mottagare att begära att ett meddelande ska släppas från karantänsbehörighet

Allow **recipients to request a message to be released from quarantine** permission _(PermissionToRequestRelease)_ controls the ability of users to request _the_ release of their quarantined messages. Meddelandet släpps bara när en administratör godkänt begäran.

- **Information om meddelanden i karantän:**
  - Behörighet aktiverad: **Knappen Begär version** är tillgänglig.
  - Behörighet inaktiverad: **Knappen Släpp av** begäran är inte tillgänglig.

- **Skräppost-aviseringar för slutanvändare:** Knappen **Släpp** är inte tillgänglig.
