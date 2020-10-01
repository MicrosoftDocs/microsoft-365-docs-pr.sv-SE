---
title: Konfigurera principer för säkra länkar i Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur du visar, skapar, ändrar och tar bort principer för säkra länkar och globala inställningar för säkra länkar i Office 365 Avancerat skydd (ATP).
ms.openlocfilehash: 58088955a6909238c1fe5202688e0b8d1ab8e6c6
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327231"
---
# <a name="set-up-safe-links-policies-in-office-365-atp"></a>Konfigurera principer för säkra länkar i Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md). Om du är hem användare letar efter information om Safelinks i Outlook kan du läsa mer i [avancerad Outlook.com-säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Säkra länkar är en funktion i [Office 365 Avancerat skydd (ATP)](office-365-atp.md) som tillhandahåller URL-genomsökning av inkommande e-postmeddelanden i e-postflöde och när du klickar på verifiering av URL-adresser och länkar i e-postmeddelanden och på andra platser. Mer information finns i [säkra länkar i Office 365 ATP](atp-safe-links.md).

Det finns inga inbyggda eller standard principer för säkra länkar. För att få säker sökning efter URL-adresser måste du skapa en eller flera principer för säkra länkar enligt beskrivningen i den här artikeln.

Du kan konfigurera principer för säkra länkar i säkerhets & efterlevnad eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Office 365 ATP-tilläggs prenumerationer).

De grundläggande delarna i en policy för säkra länkar är:

- **Principen för säkra länkar**: Aktivera skyddad länk skydd, aktivera URL-genomsökning i real tid, ange om du vill vänta på att genomsökning i real tid ska slutföras innan du levererar meddelandet, aktiverar skanning för interna meddelanden, anger om du vill spåra användare klickar på URL-adresser och ange om du vill tillåta användare att klicka på återträff till den ursprungliga URL-adressen.
- **Regeln för säkra länkar**: anger de prioritets-och mottagar filter (som principen gäller för).

Skillnaden mellan dessa två element är inte uppenbar när du hanterar Safe Links-principer i säkerhets & Compliance Center:

- När du skapar en policy för säkra länkar skapar du verkligen en regel för ett säkert länkar och den associerade principen för säkra länkar samtidigt med samma namn för båda.
- När du ändrar en princip för ett säkert länkar kan inställningar som är relaterade till namn, prioritet, aktiverade eller inaktiverade och mottagar filter ändra regeln för säkra länkar. Alla andra inställningar ändrar policyn för associerade säkra länkar.
- När du tar bort en princip för ett säkert länkar tas reglerna för säkra länkar och den associerade principen för säkra länkar bort.

I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat. Mer information finns i [använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för Safe Links](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) i den här artikeln.

> [!NOTE]
> Du konfigurerar globala inställningar för skydd mot säkra länkar **utanför** principer för säkra länkar. Anvisningar finns i [Konfigurera globala inställningar för säkra länkar i Office 365 ATP](configure-global-settings-for-safe-links.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Använd om du vill gå direkt till sidan **Safe Links för ATP** <https://protection.office.com/safelinksv2> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- För att visa, skapa, ändra och ta bort principer för säkra länkar måste du vara medlem i någon av följande roll grupper:

  - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
  - **Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- För de rekommenderade inställningarna för principer för säkra länkar, se [princip inställningar för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

- Tillåt upp till 30 minuter för att en ny eller uppdaterad princip ska tillämpas.

- [Nya funktioner läggs hela tiden till för ATP](office-365-atp.md#new-features-in-office-365-atp). När nya funktioner läggs till kan du behöva justera dina befintliga principer för säker länkar.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Skapa principer för säkra länkar med hjälp av säkerhets & efterlevnad

Om du skapar en anpassad princip för säkra länkar i säkerhets & Compliance Center skapas regeln för säkra länkar och den associerade principen för Safe Links samtidigt med samma namn för båda.

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.

2. Klicka på **skapa**på sidan **Safe Links** .

3. Guiden **ny princip för säkra länkar** öppnas. På sidan **namnge din policy** konfigurerar du följande inställningar:

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

   När du är klar klickar du på **Nästa**.

4. På sidan **Inställningar** som visas konfigurerar du följande inställningar:

   - **Välj åtgärd för okända URL-adresser i meddelanden**: Välj **på**.

   - **Välj åtgärd för okända URL-adresser i meddelanden**: **Välj eller låt** **standardvärdet** vara markerat.

   - **Använda URL-genomsökning i real tid för misstänkta länkar och länkar som pekar på filer**: Välj den här inställningen för att aktivera genomsökning i real tid med länkar i e-postmeddelanden.

   - **Vänta på att URL-genomsökningen ska slutföras innan du levererar meddelandet**: Välj den här inställningen för att vänta på att URL-genomsökning i real tid ska slutföras innan meddelandet levereras.

   - **Använd Safe Links för e-postmeddelanden som skickas inom organisationen**: Välj den här inställningen om du vill tillämpa principen för säkra länkar i meddelanden mellan interna avsändare och interna mottagare.

   - **Spåra inte användare**Klicka på: låt den här inställningen vara avmarkerad för att aktivera spårnings användaren på URL: er i e-postmeddelanden.

   - **Tillåt inte att användare klickar genom till ursprunglig URL**: Välj den här inställningen för att hindra användare från att klicka dig fram till den ursprungliga URL-adressen i [varnings sidor](atp-safe-links.md#warning-pages-from-safe-links).

   - **Skriv inte om följande webb adresser**: tillåter åtkomst till angivna URL-adresser som annars skulle blockeras av säkra länkar.

     Skriv URL: en eller det värde du vill använda i rutan och klicka sedan på ![Ikonen Lägg till knapp](../../media/ITPro-EAC-AddIcon.png).

     Om du vill ta bort en befintlig post markerar du den och klickar sedan på ![Ikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.png).

     Syntaxen för inmatning finns i [syntaxen för listan "Skriv inte om följande URL: er"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

   Detaljerad information om dessa inställningar finns i [Inställningar för säkra Länkar för e-postmeddelanden](atp-safe-links.md#safe-links-settings-for-email-messages) och [Inställningar för säkra Länkar för Microsoft Teams](atp-safe-links.md#safe-links-settings-for-microsoft-teams).

   Fler rekommenderade värden för standard-och strikta princip inställningar finns i [princip inställningar för säkra länkar](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

   När du är klar klickar du på **Nästa**.

5. **På sidan som** visas anger du vilka interna mottagare som principen gäller för.

   Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

   Klicka på **Lägg till ett villkor**. I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om**:

   - **Mottagaren är**: anger en eller flera post lådor, e-postkonton eller e-postkontakter i din organisation.
   - **Mottagaren är medlem i**: anger en eller flera grupper i din organisation.
   - **Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.

   När du har valt villkoret visas en motsvarande listruta med en **av dessa** rutor.

   - Klicka i rutan och bläddra igenom listan med värden att välja.
   - Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.
   - Om du vill lägga till fler värden klickar du i ett tomt område i rutan.
   - Om du vill ta bort enskilda poster klickar du på **ta bort** - ![ ikonen ](../../media/scc-remove-icon.png) för värdet.
   - Om du vill ta bort hela villkoret klickar du på **ta bort** ![ ikonen Ta bort ](../../media/scc-remove-icon.png) .

   Om du vill lägga till ytterligare villkor klickar du på **Lägg till ett villkor** och väljer ett återstående värde under **används om**.

   Om du vill lägga till undantag klickar du på **Lägg till ett villkor** och väljer ett undantag under **utom om**. Inställningarna och beteendet är likadana som villkoren.

   När du är klar klickar du på **Nästa**.

6. Granska inställningarna på sidan **Granska inställningar** som visas. Du kan klicka på **Redigera** på varje inställning för att ändra den.

   När du är klar klickar du på **Slutför**.

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Använda tjänsten säkerhets & efterlevnad för att visa principer för säkra länkar

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.

2. På sidan **Safe Links** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).

   Princip detaljerna visas i ett flyg utåt

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Använda inställningarna för säkerhets & efterlevnad för att ändra principer för säkra länkar

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.

2. På sidan **Safe Links** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).

3. I princip informationen som visas klickar du på **Redigera princip**.

Tillgängliga inställningar i rutan Lägg på och som visas är identiska med de som beskrivs i avsnittet [använda säkerhets & efterlevnad för att skapa principer för säkra länkar](#use-the-security--compliance-center-to-create-safe-links-policies) .

Om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principer kan du läsa följande avsnitt.

### <a name="enable-or-disable-safe-links-policies"></a>Principer för att aktivera och inaktivera säkra länkar

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.

2. Observera värdet i kolumnen **status** :

   - Flytta växlingsknappen åt vänster om du vill inaktivera principen: ![Inaktivera princip](../../media/scc-toggle-off.png).

   - Flytta växlingsknappen åt höger om du vill aktivera principen: ![Aktivera princip](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Ange prioritet för principer för säkra länkar

Som standard ges principer för säkra länkar en prioritet som baseras på den ordning de skapades i (nyare policys är lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

Principer för säkra länkar visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0).

**Obs!** i säkerhets & Compliance Center kan du bara ändra prioriteten för principen för säkra länkar när du har skapat den. I PowerShell kan du åsidosätta standard prioriteten när du skapar regeln för säkra länkar (som kan påverka prioriteringen för befintliga regler).

Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.

2. På sidan **Safe Links** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).

3. I princip detaljerna som visas klickar du på knappen tillgänglig prioritet:

   - Principen för säkra länkar med **prioritet** svärdet **0** har bara knappen **minska prioritet** tillgänglig.

   - Principen för säkra länkar med det lägsta **prioritet** svärdet (till exempel **3**) har bara knappen **öka prioritet** tillgänglig.

   - Om du har tre eller fler Safe Link-principer har de principer som gäller för de högsta och lägsta värdena både knappen **öka prioritet** och knappen för att **minska prioriteten** tillgängliga.

4. Klicka på **öka prioritet** eller **minska prioritet** för att ändra **prioritet** svärdet.

5. Klicka på **Stäng** när du är klar.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Använda inställningarna för säkerhets & efterlevnad för att ta bort principer för säkra länkar

1. I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**.

2. På sidan **Safe Links** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).

3. I princip detaljerna som visas klickar du på **ta bort princip**och sedan på **Ja** i varnings dialog rutan som visas.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för säkra länkar

Som du redan har beskrivit innehåller en policy för Safe Links en princip för säkra länkar och en regel för säkra länkar.

I PowerShell är skillnaden mellan principer för säkra länkar och regler för säkra länkar uppenbar. Du hanterar principer för säkra länkar genom att använda cmdletarna ** \* -SafeLinksPolicy** och du hanterar reglerna för säkra länkar genom att använda cmdlet ** \* -SafeLinksRule** .

- I PowerShell skapar du principen för säkra länkar först och skapar sedan regeln för säkra länkar som identifierar den princip som regeln gäller för.
- I PowerShell ändrar du inställningarna för principen för säkra länkar och regeln för säkra länkar var för sig.
- När du tar bort en princip för säkra länkar från PowerShell tas inte den motsvarande regeln för Safe-länkar bort automatiskt och vice versa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Använda PowerShell för att skapa principer för säkra länkar

Att skapa en princip för säkra länkar i PowerShell är en process i två steg:

1. Skapa principen för säkra länkar.
2. Skapa regeln för säkra länkar som anger principen för säkra länkar som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny regel för ett säkert länkar och koppla en befintlig princip för osäkra länkar till den. En regel för säkert länkar kan inte kopplas till fler än en princip för säkra länkar.

- Du kan konfigurera följande inställningar på nya principer för säkra länkar i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän du har skapat principen:

  - Skapa den nya principen som inaktive rad (_aktive rad_ `$false` på **New-SafeLinksRule-** cmdleten).
  - Ange prioriteten för principen när den skapas (_prioritet_ _\<Number\>_ ) på den **nya SafeLinksRule-** cmdleten.

- En ny princip för säkra länkar som du skapar i PowerShell visas inte i fönstret säkerhets & efterlevnad förrän du tilldelar principen en regel för ett säkert länkar.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Steg 1: använda PowerShell för att skapa en policy för säkra länkar

Använd den här syntaxen om du vill skapa en princip för säkra länkar:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**Anmärkningar**:

- Mer information om syntaxen för _DoNotRewriteUrls_ finns i [syntaxen för listan "Skriv inte om följande URL-adresser"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list).

- Ytterligare syntax som du kan använda för _DoNotRewriteUrls_ -parametern när du ändrar befintliga principer för säkra länkar med hjälp av cmdleten **set-SafeLinksPolicy** finns i avsnittet [använda PowerShell för att ändra principer för Safe Links](#use-powershell-to-modify-safe-links-policies) senare i den här artikeln.

I det här exemplet skapas en princip för säkra länkar med namnet contoso alla med följande värden:

- Aktivera URL-genomsökning och omskrivning i e-postmeddelanden.
- Aktivera URL-genomsökning i Teams (tryck bara på för hands version).
- Aktivera genomsökning i real tid med URL-adresser, inklusive klickade på länkar som pekar på filer.
- Vänta på att URL-genomsökningen ska slutföras innan du levererar meddelandet.
- Aktivera URL-genomsökning och omskrivning för interna meddelanden.
- Spåra användar klickningar relaterade till skydd mot säkra länkar (vi använder inte parametern _DoNotTrackUserClicks_ och standardvärdet är $false, vilket innebär att användare klickar på spåras).
- Tillåt inte användare att klicka dig fram till original-URL: en.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Detaljerad information om syntax och parametrar finns i [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Steg 2: använda PowerShell för att skapa en regel för säkra länkar

Använd den här syntaxen om du vill skapa en regel för säkra länkar:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

I det här exemplet skapas en regel för säkra länkar som heter Contoso alla med följande villkor:

- Regeln kopplas till principen för säkra länkar med namnet contoso all.
- Regeln gäller för alla mottagare i contoso.com-domänen.
- Eftersom vi inte använder _prioritets_ parametern används standard prioriteten.
- Regeln är aktive rad (vi använder inte den _aktiverade_ parametern och standardvärdet är `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Detaljerad information om syntax och parametrar finns i [New-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Använda PowerShell för att visa principer för säkra länkar

Använd följande syntax för att visa befintliga principer för säkra länkar:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

I det här exemplet returneras en sammanfattande lista över alla principer för säkra länkar.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

I det här exemplet returneras detaljerad information för principen för säkra länkar som heter Contoso-chefer.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Detaljerad information om syntax och parametrar finns i [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy).

### <a name="use-powershell-to-view-safe-links-rules"></a>Använda PowerShell för att visa regler för säkra länkar

Använd följande syntax för att visa befintliga regler för säkra länkar:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

I det här exemplet returneras en sammanfattande lista över alla regler för säker länk.

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

I det här exemplet returneras detaljerad information för regeln för säkra länkar som heter Contoso-chefer.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Detaljerad information om syntax och parametrar finns i [Get-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule).

### <a name="use-powershell-to-modify-safe-links-policies"></a>Använda PowerShell för att ändra principer för säkra länkar

Det går inte att byta namn på en policy för säkra länkar i PowerShell (cmdleten **set-SafeLinksPolicy** , saknar _namn_ parameter). När du byter namn på en policy för säkra länkar i säkerhets &s kontroll namn ändras inte _regeln_för säkra länkar.

Det enda alternativet för att ändra principer för säkra länkar i PowerShell är den tillgängliga syntaxen för parametern _DoNotRewriteUrls_ (alternativet ["Skriv inte om följande URL-adresser"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)):

- Om du vill lägga till värden som ersätter befintliga poster kan du använda följande syntax: `"Entry1","Entry2,..."EntryN"` .
- Använd följande syntax för att lägga till eller ta bort värden utan att påverka andra befintliga poster: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

I annat fall är samma inställningar tillgängliga när du skapar en princip för säkra länkar enligt beskrivningen i [steg 1: använda PowerShell för att skapa en princip för säkra länkar](#step-1-use-powershell-to-create-a-safe-links-policy) i den här artikeln.

Använd den här syntaxen om du vill ändra en princip för ett säkert länkar:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy).

### <a name="use-powershell-to-modify-safe-links-rules"></a>Använda PowerShell för att ändra regler för säkra länkar

Den enda inställning som inte är tillgänglig när du ändrar en regel för ett säkert länkar i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en regel för inaktivitet. Information om hur du aktiverar eller inaktiverar befintliga Safe Links-regler finns i nästa avsnitt.

I annat fall är samma inställningar tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en regel för ett säkert länkar](#step-2-use-powershell-to-create-a-safe-links-rule) i den här artikeln.

Om du vill ändra en regel för ett säkert länkar använder du följande syntax:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Använda PowerShell för att aktivera eller inaktivera regler för säkra länkar

När du aktiverar eller inaktiverar en regel för ett säkert länkar i PowerShell aktive ras eller inaktive ras hela principen för säkra länkar (reglerna för säkra länkar och tilldelnings principen för tilldelade säkra länkar).

Använd den här syntaxen om du vill aktivera eller inaktivera en regel för ett säkert länkar i PowerShell:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

Det här exemplet inaktiverar regeln för säkra länkar som heter marknadsförings avdelningen.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Aktivera-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) och [disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule).

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Använda PowerShell för att ange prioritet för regler för säkra länkar

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Använd följande syntax för att ange prioriteten för en regel för säkra länkar i PowerShell:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

**Obs!** om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-SafeLinksRule** cmdlet i stället.

Detaljerad information om syntax och parametrar finns i [set-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule).

### <a name="use-powershell-to-remove-safe-links-policies"></a>Använda PowerShell för att ta bort principer för säkra länkar

När du använder PowerShell för att ta bort en princip för säkra länkar tas inte den motsvarande regeln för Safe Links bort.

Använd den här syntaxen om du vill ta bort en princip för säkra länkar i PowerShell:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

Det här exemplet tar bort policyn för säkra länkar som heter marknadsförings avdelningen.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Använda PowerShell för att ta bort regler för säkra länkar

När du använder PowerShell för att ta bort en regel för ett säkert länkar tas inte motsvarande principer för säkra länkar bort.

Använd den här syntaxen om du vill ta bort en regel för säkra länkar i PowerShell:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

Det här exemplet tar bort regeln för säkra länkar som heter marknadsförings avdelningen.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule).

Om du vill kontrol lera att de säkra länkarna är att söka igenom meddelanden markerar du de tillgängliga avancerade skydds rapporterings rapporterna. Mer information finns i [Visa rapporter om Office 365 ATP](view-reports-for-atp.md) och [använda utforskaren i säkerhets & Compliance Center](threat-explorer.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Gör något av följande för att kontrol lera att du har skapat, ändrat eller tagit bort principer för säkra länkar:

- I säkerhets & Compliance Center går du till **Threat Management** \> **policy** - \> **säkra länkar**. Verifiera listan med principer, deras **status** värden och deras **prioriterade** värden. Om du vill visa mer information väljer du den i listan och visar detaljerna i Lägg utåt.

- I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du \<Name\> med namnet på principen eller regeln, kör följande kommando och kontrollerar inställningarna:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
