---
title: Karantän koder
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Administratörer kan lära sig att använda karantän koder för att kontrol lera vad användarna kan göra i sina karantän meddelanden.
ms.openlocfilehash: 498a5f45fa62481f7f4f8dfe5ece8a51a038f99a
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616014"
---
# <a name="quarantine-tags"></a>Karantän koder

> [!NOTE]
> De funktioner som beskrivs i den här artikeln är för närvarande i för hands versionen, är inte tillgängliga för alla och kan komma att ändras.

Med karantän-Taggar i Exchange Online Protection (EOP) kan administratörer kontrol lera vilka användare som kan göra till sina karantän meddelanden baserat på hur meddelandet kom i karantän.

EOP har traditionellt tillåtit eller förhindrat vissa interaktivitet för meddelanden i [karantän](find-and-release-quarantined-messages-as-a-user.md) och [aviseringar om slutanvändare](use-spam-notifications-to-release-and-report-quarantined-messages.md). Slutanvändare kan till exempel se och släppa meddelanden som satts i karantän av filtrering som skräp post eller bulk, men de kan inte Visa eller släppa meddelanden som satts i karantän som nätfiske med hög exakthet.

För [skydds funktioner som stöds](#step-2-assign-a-quarantine-tag-to-supported-features)kan du ange vilka användare som får göra-meddelanden och i sina karantän meddelanden i karantän (meddelanden där användaren är en mottagare). Standard karantän koder tilldelas automatiskt för att påtvinga de historiska funktionerna för slutanvändare i karantän meddelanden. Eller så kan du skapa och tilldela egna karantän koder för att tillåta eller förhindra att slutanvändare utför vissa åtgärder i karantän meddelanden.

De enskilda behörigheterna kombineras till följande förvalda behörighets grupper:

- Ingen åtkomst
- Begränsad åtkomst
- Full åtkomst

De tillgängliga enskilda behörigheterna och vad som ingår eller inte ingår i de förinställda behörighets grupperna beskrivs i följande tabell:

|Tillåtelse|Ingen åtkomst|Begränsad åtkomst|Full åtkomst|
|---|:---:|:---:|:---:|
|**Tillåt avsändare** (_PermissionToAllowSender_)|||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Spärra avsändare** (_PermissionToBlockSender_)||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Ta bort** (_PermissionToDelete_)||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Förhandsgranska** (_PermissionToPreview_)||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Tillåt att mottagare släpper ett meddelande från karantän** (_PermissionToRelease_)|||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**Tillåt mottagare att begära att ett meddelande släpps från karantän** (_PermissionToRequestRelease_)||![Bockmarkering](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

Om du inte gillar standard behörigheterna i gruppen för förvalda behörigheter kan du använda anpassade behörigheter när du skapar eller ändrar egna karantän koder. Mer information om vad de här behörigheterna gör finns i avsnittet [behörighets information om karantänen](#quarantine-tag-permission-details) längre fram i den här artikeln.

Du skapar och tilldelar karantän koder i säkerhets & efterföljandekrav eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med Exchange Online-postlådor, fristående EOP PowerShell in EOP-organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Öppna för att gå direkt till sidan **karantän etiketter** <https://protection.office.com/quarantineTags> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Om du vill visa, skapa, ändra eller ta bort karantän koder måste du vara medlem i rollerna **organisations hantering** eller **säkerhets administratör** i [säkerhets & efterlevnad](permissions-in-the-security-and-compliance-center.md).

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a>Steg 1: skapa karantän koder i centret säkerhets & efterlevnad

1. I fönstret säkerhets & efterlevnad går du till **Threat Management** \> **policy** och väljer sedan **Quarantine-Taggar**.

2. På sidan **karantän etiketter** väljer du **Lägg till anpassad tagg**.

3. Guiden **ny tagg** öppnas. Ange ett kort men unikt namn i fältet **taggnamn** på sidan **taggnamn** . Du måste identifiera och markera taggen efter namn i kommande steg. När du är klar klickar du på **Nästa**.

4. Välj något av följande värden på sidan **mottagar meddelande åtkomst** :
   - **Ingen åtkomst**
   - **Begränsad åtkomst**
   - **Full åtkomst**

   De enskilda behörigheter som ingår i de här behörighets grupperna beskrivs tidigare i den här artikeln.

   Om du vill ange anpassade behörigheter väljer du **ange specifik åtkomst (avancerat)** och konfigurerar följande inställningar:

     - **Välj inställningar för släpp**: Välj något av följande värden:
       - **Ingen släpp-åtgärd**: det här är standardvärdet.
       - **Tillåt att mottagare släpper ett meddelande från karantän**
       - **Tillåt mottagare att begära att ett meddelande släpps från karantän**

     - **Välj ytterligare åtgärder som mottagarna kan ta med i karantänen**: Välj några, alla eller inga av följande värden:
       - **Ta bort**
       - **Automatisk**
       - **Tillåt avsändare**
       - **Spärra avsändare**

   De här behörigheterna och deras inverkan på meddelanden i karantän och meddelanden om skräp post beskrivs i avsnittet [behörigheter för karantän tag](#quarantine-tag-permission-details) längre fram i den här artikeln.

   När du är klar klickar du på **Nästa**.

5. Granska inställningarna på **sammanfattnings** sidan som visas. Du kan klicka på **Redigera** på varje inställning för att ändra den.

   När du är klar klickar du på **Skicka**.

6. Klicka på **klar** på bekräftelse sidan som visas.

Nu är du redo att koppla karantän tag gen till en karantän funktion enligt beskrivningen i [steg 2](#step-2-assign-a-quarantine-tag-to-supported-features) .

### <a name="create-quarantine-tags-in-powershell"></a>Skapa karantän koder i PowerShell

Om du hellre vill använda PowerShell för att skapa karantän koder ansluter du till Exchange Online PowerShell eller Exchange Online Protection PowerShell och använder cmdleten **New-QuarantineTag** . Du kan välja mellan två olika metoder:

- Använd parametern _EndUserQuarantinePermissionsValue_ .
- Använd parametern _EndUserQuarantinePermissions_ .

De här metoderna beskrivs i följande avsnitt.

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>Använda parametern EndUserQuarantinePermissionsValue

Om du vill skapa en karantän etikett med parametern _EndUserQuarantinePermissionsValue_ använder du följande syntax:

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

Parametern _EndUserQuarantinePermissionsValue_ använder ett Decimal värde som konverteras från ett binärt värde. Det binära värdet motsvarar de tillgängliga karantän behörigheterna för slutanvändare i en viss ordning. För varje behörighet är värdet 1 lika med sant och värdet 0 är falskt.

Den obligatoriska beställningen och värdena för varje enskild behörighet i de fördefinierade behörighets grupperna beskrivs i följande tabell:

****

|Tillåtelse|Ingen åtkomst|Begränsad åtkomst|Full åtkomst|
|---|:---:|:---:|:---:|
|PermissionToAllowSender|siffrorna|siffrorna|9.1|
|PermissionToBlockSender|siffrorna|9.1|9.1|
|PermissionToDelete|siffrorna|9.1|9.1|
|PermissionToDownload<sup>\*</sup>|siffrorna|siffrorna|siffrorna|
|PermissionToPreview|siffrorna|9.1|9.1|
|PermissionToRelease<sup>\*\*</sup>|siffrorna|siffrorna|9.1|
|PermissionToRequestRelease<sup>\*\*</sup>|siffrorna|9.1|siffrorna|
|PermissionToViewHeader<sup>\*</sup>|siffrorna|siffrorna|siffrorna|
|Binärt värde|00000000|01101010|11101100|
|Decimal värde som ska användas|siffrorna|106|236|

<sup>\*</sup> För närvarande är det här värdet alltid 0. För PermissionToViewHeader döljer värdet 0 inte knappen **Visa meddelande rubrik** i information om det mellanliggande meddelandet (knappen är alltid tillgänglig).

<sup>\*\*</sup> Ange inte båda värdena till 1. Ange en till 1 och den andra till 0, eller Ställ in båda på 0.

I det här exemplet skapas ett nytt namn på en karantäns etikett utan åtkomst behörighet enligt beskrivningen i föregående tabell.

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

Använd värdet 106 för begränsade åtkomst behörigheter. Använd värdet 236 för full åtkomst behörighet.

Använd den föregående tabellen för att få det binära värdet som motsvarar de behörigheter som du vill använda. Konvertera det binära värdet till ett Decimal värde och Använd det decimala värdet för parametern _EndUserQuarantinePermissionsValue_ .

Detaljerad information om syntax och parametrar finns i [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>Använda parametern EndUserQuarantinePermissions

Gör så här om du vill skapa en karantän etikett med hjälp av parametern _EndUserQuarantinePermissionsValue_ :

Kallas. Lagra ett karantän objekt i en variabel med cmdleten **New-QuarantinePermissions** .

<p>

H. Använd variabeln som _EndUserQuarantinePermissions_ -värde i kommandot **ny-QuarantineTag** .

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>Steg A: lagra ett karantän objekt i en variabel

Använd följande syntax:

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

Standardvärdet för eventuella oanvända parametrar är `$false` så du behöver bara använda parametrarna där du vill ange värdet `$true` .

I följande exempel visas hur du skapar behörighets objekt som motsvarar de fördefinierade behörighets grupperna:

- **Ingen åtkomst**:

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **Begränsad åtkomst**:

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **Fullständig åtkomst**:

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

Om du vill se de värden som du har angett kör du variabel namnet som ett kommando (till exempel kör kommandot `$NoAccess` ).

För anpassade behörigheter ska du inte ange parametrarna _PermissionToRelease_ och _PermissionToRequestRelease_ till `$true` . Ange en till `$true` och lämna den andra som `$false` , eller lämna båda som `$false` .

Du kan också ändra en befintlig behörighets objekt variabel efter att du har skapat den med hjälp av cmdleten **set-QuarantinePermissions** .

Detaljerad information om syntax och parametrar finns i [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) och [set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>Steg B: Använd variabeln i kommandot New-QuarantineTag

När du har skapat och sparat behörighets objekt i en variabel, Använd variabeln _EndUserQuarantinePermission_ parameter värde i följande **nya-QuarantineTag-** kommando:

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

I det här exemplet skapas en ny Quarantine-tagg med namnet LimitedAccess med `$LimitedAccess` behörighets objekt som beskrivs och skapades i föregående steg.

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

Detaljerad information om syntax och parametrar finns i [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a>Steg 2: tilldela en karantän etikett till funktioner som stöds

I skydds funktioner som _stöds_ i karantän meddelanden och filer (automatiskt eller som en konfigurerbar åtgärd) kan du tilldela en Quarantine-tagg till de tillgängliga karantän åtgärderna. Funktioner som karantän meddelanden och tillgänglighet för karantän koder beskrivs i följande tabell:

****

|Funktion|Finns det stöd för karantän?|Standard karantän koder|
|---|:---:|---|
|[Principer för skräp post](configure-your-spam-filter-policies.md): <ul><li>**Spam** (_SpamAction_)</li><li>**Snabb meddelanden med hög exakthet** (_HighConfidenceSpamAction_)</li><li>**Phishing-e-post** (_PhishSpamAction_)</li><li>**E-post med hög exakthet** (_HighConfidencePhishAction_)</li><li>**Mass utskick via e-post** (_BulkSpamAction_)</li></ul>|Ja|<ul><li>DefaultSpamTag (fullständig åtkomst)</li><li>DefaultHighConfSpamTag (fullständig åtkomst)</li><li>DefaultPhishTag (fullständig åtkomst)</li><li>DefaultHighConfPhishTag (ingen åtkomst)</li><li>DefaultBulkTag (fullständig åtkomst)</li></ul>
|Skydd mot nätfiske: <ul><li>[Skydd mot förfalsknings information](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</li><li>[Personifieringsnivå](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup> <ul><li>**Om e-post skickas av en personifierad användare** (_TargetedUserProtectionAction_)</li><li>**Om e-post skickas av en domänkontrollant** (_TargetedDomainProtectionAction_)</li><li>**Post lådans intelligens** \> **Om e-post skickas av en personifierad användare** (_MailboxIntelligenceProtectionAction_)</li></ul></li></ul></ul>|Nej|ej tillämpligt|
|[Principer mot skadlig program vara](configure-anti-malware-policies.md): alla upptäckta meddelanden alltid är i karantän.|Nej|ej tillämpligt|
|[ATP för SharePoint, OneDrive och Microsoft Teams](atp-for-spo-odb-and-teams.md)|Nej|ej tillämpligt|
|[Regler för e-postflöden](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (kallas även transport regler) med åtgärden: **leverera meddelandet till den värdbaserade karantänen** (_karantän_).|Nej|ej tillämpligt|
|

<sup>\*</sup> Inställningarna för skydd mot personifiering är endast tillgängliga i skydd mot nätfiske i Microsoft Defender för Office 365.

Om du är nöjd med de slut användar behörigheter som tillhandahålls av standard karantän taggarna behöver du inte göra något. Om du vill anpassa slutanvändarens funktioner (tillgängliga knappar) i aviseringar om slutanvändare eller i karantän meddelanden, kan du tilldela en egen karantän etikett.

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a>Tilldela karantän koder i principer för skydd mot skräp post i säkerhets & efterlevnad

Fullständiga anvisningar för hur du skapar och ändrar principer för skräp post beskrivs i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md).

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> och väljer sedan **anti-spam**. Eller öppna <https://protection.office.com/antispam> .

2. Leta reda på och välj en befintlig policy mot skräp post som du vill redigera eller skapa en ny policy mot skräp post.

3. I den utfällbara princip informationen expanderar du avsnittet **skräp post och Mass åtgärder** .

4. Om du har valt **karantän meddelande** för en tillgänglig spam-Verdict är rutan **Använd karantän princip** tillgänglig för dig att välja karantän tag gen för den Verdict.

   **Obs!** när du skapar en ny princip anger ett tomt karantän värde för en skräp post filtrering Verdict att standard karantänen för den Verdict används. När du senare redigerar principen ersätts de tomma värdena med de faktiska standard namnen på karantänen enligt beskrivningen i föregående tabell.

   ![Alternativ för karantän i en policy för skräp post](../../media/quarantine-tags-in-anti-spam-policies.png)

5. Klicka på **Spara** när du är klar.

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a>Tilldela karantän koder i en policy för skydd mot skräp post i PowerShell

Om du hellre vill använda PowerShell för att tilldela karantän koder i principer för skräp post anslutning ansluter du till Exchange Online PowerShell eller Exchange Online Protection PowerShell och använder följande syntax:

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**Anmärkningar**:

- Standardvärdet för parametern _HighConfidencePhishAction_ är karantän, så du behöver inte ange karantäns åtgärden för att få en hög exakthet för nät fiske igenkänning i nya principer för skräp post skydd. För all annan filtrering av skräp post verdicts i nya eller befintliga principer för skräp post hantering är karantän tag gen bara effektiv om åtgärd svärdet är Quarantine. Om du vill visa åtgärds värden i befintliga principer för skräp post meddelanden kör du följande kommando:

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  Information om standard åtgärds värden och rekommenderade åtgärds värden för standard och Strict finns i [EOP princip inställningar](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)för borttagning av skräp post.

- Filtrering av skräp post Verdict utan motsvarande kod för en karantän innebär att [standard karantänen](#step-2-assign-a-quarantine-tag-to-supported-features) för den Verdict används.

  Du behöver bara ersätta en standard karantän etikett med ett anpassat karantän märke om du vill ändra standard funktioner för slutanvändare i karantän meddelanden.

- En ny skydd mot skräp post i PowerShell kräver en filter princip (inställningar) för skräp post med hjälp av cmdleten **New-HostedContentFilterPolicy** och en ny regel för skräp post filter (mottagar filter) med cmdleten **New-HostedContentFilterRule** . Anvisningar finns i [använda PowerShell för att skapa principer för skräp post skydd](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).

I det här exemplet skapas en ny skräp post filter princip med följande inställningar:

- Åtgärden för all skräp post filtrering verdicts är inställd på Quarantine.
- Den anpassade Quarantine-taggen med namnet noaccess som tilldelar **inga Access** -behörigheter ersätter eventuella standard karantäns flaggor som inte redan tilldelar **åtkomst** behörigheter som standard.

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

Detaljerad information om syntax och parametrar finns i [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).

I det här exemplet ändras den befintliga filtret för skräp post filter som heter Human Resources. Åtgärden för skräp post karantänen Verdict är inställd på Quarantine och den anpassade karantäns tag gen är tilldelad.

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

Detaljerad information om syntax och parametrar finns i [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a>Konfigurera inställningar för globala karantän meddelanden i centret för säkerhets &

Med globala inställningar för karantän koder kan du anpassa avsändare av slutanvändare som skickas till mottagare av meddelanden som satts i karantän. Mer information om dessa meddelanden finns i aviseringar om avanmälan till [slutanvändare](use-spam-notifications-to-release-and-report-quarantined-messages.md).

1. I fönstret säkerhets & efterlevnad går du till **Threat Management** \> **policy** och väljer sedan **Quarantine-Taggar**.

2. På sidan **karantän etiketter** väljer du **globala inställningar**.

3. I fönstret **Inställningar för karantän meddelanden** som öppnas konfigurerar du vissa eller alla av följande inställningar:

   - **Använd min företags logo typ**: Välj det här alternativet om du vill ersätta Microsofts standard logo typ som används överst i meddelanden om avanmälan till slutanvändare. Innan du gör det måste du följa instruktionerna i [Anpassa Microsoft 365-temat för din organisation](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) för att överföra din anpassade logo typ.

     Följande skärm bild visar en egen logo typ i en avisering om avanmälan till slutanvändare:

     ![En egen logo typ i en avisering om avanmälan till slutanvändare](../../media/quarantine-tags-esn-customization-logo.png)

   - **Välj språk**: skräp post meddelanden är redan lokaliserade baserat på mottagarens språk inställningar. Du kan ange anpassad text på olika språk för **visnings namn** och **fri skrivnings** värden.

     Välj minst ett språk i rutan första språk och klicka sedan på **Lägg till**. Du kan välja flera språk genom att klicka på **Lägg till** efter varje. I rutan avsnitts språk visas alla språk som du har valt:

     ![Valda språk i rutan andra språk i den globala karantänen inställningar för karantäns meddelanden](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **Visnings namn**: anpassa avsändarens visnings namn som används i meddelanden med slutanvändare.

     För varje språk som du har lagt till väljer du det språk som du vill använda i rutan andra språk (Klicka inte på X) och anger önskat text värde i rutan **visnings namn** .

     Följande skärm bild visar det anpassade visnings namnet i en avisering om avanmälan till slutanvändare:

     ![Ett anpassat avsändar namn i en avisering om skräp post](../../media/quarantine-tags-esn-customization-display-name.png)

   - **Fri** skrivning: lägga till en egen ansvars friskrivning längst ned i meddelanden om avanmälan till slutanvändare. Den lokaliserade texten, **en fri skrivning från din organisation:** tas alltid med först, följt av den text som du anger.

     För varje språk som du har lagt till väljer du det språk som du vill använda i rutan andra språk (Klicka inte på X) och anger det text värde du vill ha i rutan **fri skrivning** .

     Följande skärm bild visar den anpassade fri skrivnings funktionen i en avisering om avanmälan till slutanvändare:

     ![En egen fri skrivning längst ned i en avisering om avanmälan till slutanvändare](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a>Visa karantän koder i centret för säkerhets &

1. I fönstret säkerhets & efterlevnad går du till **Threat Management** \> **policy** och väljer sedan **Quarantine-Taggar**.

- Om du vill visa inställningarna för inbyggda eller anpassade Quarantine-Taggar markerar du karantän tag gen i listan (Markera inte kryss rutan).

- Om du vill visa de globala inställningarna väljer du **globala inställningar**

### <a name="view-quarantine-tags-in-powershell"></a>Visa karantän koder i PowerShell

Om du hellre vill använda PowerShell för att Visa karantän koder gör du något av följande:

- Om du vill visa en sammanfattnings lista över alla inbyggda och anpassade taggar kör du följande kommando:

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- Om du vill visa inställningarna för inbyggda eller anpassade karantän koder ersätter du \<TagName\> namnet på karantän tag gen och kör följande kommando:

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- Om du vill visa de globala inställningarna kör du följande kommando:

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

Detaljerad information om syntax och parametrar finns i [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a>Ta bort karantän koder i säkerhets & efterlevnad

**Anmärkningar**:

- Du kan inte ta bort inbyggda karantän koder.

- Innan du tar bort en egen karantän etikett kontrollerar du att den inte används. Kör till exempel följande kommando i PowerShell:

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  Om du använder Quarantine-taggen ersätter du [den tilldelade karantän tag gen](#step-2-assign-a-quarantine-tag-to-supported-features) innan du tar bort den.

1. I fönstret säkerhets & efterlevnad går du till **Threat Management** \> **policy** och väljer sedan **Quarantine-Taggar**.

2. På sidan **karantäns etiketter** väljer du den anpassade Quarantine-tagg som du vill ta bort och klickar på **ta bort-taggen**.

3. Klicka på **ta bort tagg** i bekräftelse dialog rutan som visas.

### <a name="remove-quarantine-tags-in-powershell"></a>Ta bort karantän koder i PowerShell

Om du hellre vill använda PowerShell för att ta bort en egen karantän etikett ersätter du \<TagName\> namnet på karantän etiketten och kör följande kommando:

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

Detaljerad information om syntax och parametrar finns i [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).

## <a name="quarantine-tag-permission-details"></a>Information om behörighet för karantän tag

I följande avsnitt beskrivs effekterna av de förvalda behörighets grupperna och enskilda behörigheter i detalj meddelanden i karantän och aviseringar om slutanvändare.

### <a name="preset-permissions-groups"></a>Gruppen förinställda behörigheter

De enskilda behörigheter som ingår i de förinställda behörighets grupperna visas i tabellen i början av den här artikeln.

#### <a name="no-access"></a>Ingen åtkomst

Om **Ingen åtkomst** behörighet tilldelas (inga behörigheter) för fältet karantän får användarna ändå vissa bas linje funktioner:

- **Detaljer i karantän**: knappen **Visa meddelande rubrik** är alltid tillgänglig.

  ![Tillgängliga knappar i information om karantänen för meddelanden om Quarantine-taggen ger användaren ingen åtkomst behörighet](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **Aviseringar om slutanvändare**: knappen **Granska** som tar användaren till meddelandet i karantän är alltid tillgänglig.

  ![Tillgängliga knappar i meddelandet om att skicka skräp post till slutanvändaren ger användaren ingen åtkomst behörighet](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>Begränsad åtkomst

Om funktionen för karantän tilldelar de **begränsade åtkomst** behörigheterna får användarna följande funktioner:

- **Detaljer i karantän**: följande knappar är tillgängliga:
  - **Begäran släpp**
  - **Visa meddelande rubrik**
  - **Förhandsgranska meddelande**
  - **Spärra avsändare**
  - **Ta bort från karantän**

  ![Tillgängliga knappar i information om karantänen för meddelanden om Quarantine-taggen ger användare begränsad åtkomst behörighet](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **Meddelanden om avanmälan till slutanvändare**: följande knappar är tillgängliga:
  - **Spärra avsändare**
  - **Översikt**

  ![Tillgängliga knappar i meddelandet om att den här funktionen är klar om Quarantine-taggen ger användare begränsad åtkomst behörighet](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>Full åtkomst

Om den här flaggan tilldelar **full åtkomst** behörighet (alla tillgängliga behörigheter) får användarna följande funktioner:

- **Detaljer i karantän**: följande knappar är tillgängliga:
  - **Släpp meddelande**
  - **Visa meddelande rubrik**
  - **Förhandsgranska meddelande**
  - **Spärra avsändare**
  - **Tillåt avsändare**
  - **Ta bort från karantän**

  ![Tillgängliga knappar i information om karantänen för meddelanden om Quarantine-taggen ger användaren full åtkomst behörighet](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **Meddelanden om avanmälan till slutanvändare**: följande knappar är tillgängliga:
  - **Spärra avsändare**
  - **Version**
  - **Översikt**

  ![Tillgängliga knappar i meddelandet om att karantänen avvisas om Quarantine-taggen ger användaren full åtkomst behörighet](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>Enskilda behörigheter

> [!NOTE]
> Kom ihåg att användarna alltid får de knappar som beskrivs i avsnittet [Ingen åtkomst](#no-access) . De här knapparna är inte inkluderade i de enskilda behörighets beskrivningarna.

#### <a name="allow-sender-permission"></a>Tillåt avsändarens tillstånd

Alternativet **Tillåt avsändare** kontrollerar åtkomsten till knappen som gör att användare enkelt kan lägga till avsändaren av meddelandet i listan Betrodda avsändare.

- **Detaljer i karantänen**:
  - **Tillåt avsändarens** behörighet aktiverat: knappen **Tillåt avsändare** är tillgänglig.
  - **Tillåt avsändarens** behörighet inaktive rad: knappen **Tillåt avsändare** är inte tillgänglig.

- **Meddelanden om avanmälan till slutanvändare**: ingen effekt.

Om du vill ha mer information om listan Betrodda avsändare kan du läsa förhindra att betrodda avsändare [blockeras](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) och [använda Exchange Online PowerShell för att konfigurera säker lista-samlingen på en post låda](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).

#### <a name="block-sender-permission"></a>Förhindra avsändare

Behörigheten **Blockera avsändare** (_PermissionToBlockSender_) styr åtkomsten till knappen som gör att användare enkelt kan lägga till avsändaren för meddelande i listan över spärrade avsändare.

- **Detaljer i karantänen**:
  - **Blockering av avsändare** är aktiverat: knappen **block avsändare** är tillgänglig.
  - **Förhindra att avsändaren** har inaktiverats: knappen **Spärra avsändare** är inte tillgänglig.

- **Meddelanden om avanmälan till slutanvändare**:
  - **Förhindra att avsändaren** har inaktiverats: knappen **Spärra avsändare** är inte tillgänglig.
  - **Blockering av avsändare** är aktiverat: knappen **block avsändare** är tillgänglig.

Mer information om listan Spärrade avsändare finns i [blockera meddelanden från någon](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) och [använda Exchange Online PowerShell för att konfigurera säker lista-samlingen i en post låda](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).

#### <a name="delete-permission"></a>Ta bort behörighet

Behörigheten **ta bort** (_PermissionToDelete_) styr möjligheten för användare att ta bort sina meddelanden (meddelanden där användaren är en mottagare) från karantän.

- **Detaljer i karantänen**:
  - **Borttagnings** behörighet aktive rad: knappen **ta bort från karantän** är tillgänglig.
  - **Borttagnings** behörighet avaktiverad: knappen **ta bort från karantän** är inte tillgänglig.

- **Meddelanden om avanmälan till slutanvändare**: ingen effekt.

#### <a name="preview-permission"></a>För hands version

Med funktionen för **förhands granskning** (_PermissionToPreview_) kan användarna förhandsgranska sina meddelanden i karantänen.

- **Detaljer i karantänen**:
  - **Förhands gransknings** behörighet aktive rad: knappen **Förhandsgranska meddelande** är tillgänglig.
  - För **hands versionen** är inaktive rad: knappen för **förhands granskning** är inte tillgänglig.

- **Meddelanden om avanmälan till slutanvändare**: ingen effekt.

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>Tillåt att mottagare släpper ett meddelande från karantän behörighet

**Tillåt att mottagarna kan släppa ett meddelande från karantän** tillstånd (_PermissionToRelease_) styr möjligheten för användarna att släppa sina karantän meddelanden direkt och utan godkännande från en administratör.

- **Detaljer i karantänen**:
  - Behörighet aktive rad: knappen för att **frigöra meddelande** är tillgänglig.
  - Inaktive rad behörighet: knappen för att **frigöra meddelande** är inte tillgänglig.

- **Meddelanden om avanmälan till slutanvändare**:
  - Behörighet aktive rad: knappen **släpp** är tillgänglig.
  - Inaktive rad behörighet: knappen **släpp** är inte tillgänglig.

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>Tillåt att mottagare kan begära att ett meddelande släpps från karantän behörighet

**Tillåt att mottagarna kan begära att ett meddelande släpps från karantän** tillstånd (_PermissionToRequestRelease_) styr möjligheten för användarna att _begära_ utgivningen av sina karantän meddelanden. Meddelandet släpps bara efter att en administratör godkänt begäran.

- **Detaljer i karantänen**:
  - Behörighet aktive rad: knappen för att **släppa begäran** är tillgänglig.
  - Inaktive rad behörighet: knappen för att **släppa begäran** är inte tillgänglig.

- **Avisering om avanmälan till slutanvändare**: knappen **släpp** är inte tillgänglig.
