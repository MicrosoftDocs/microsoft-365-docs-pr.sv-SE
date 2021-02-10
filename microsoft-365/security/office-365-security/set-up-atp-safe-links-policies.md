---
title: Konfigurera principer för säkra länkar i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Administratörer kan ta reda på hur de visar, skapar, ändrar och tar bort principer för säkra länkar och globala inställningar för säkra länkar i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71ea33f1f6fbebf6d87a4b42ad3bd96a60597b90
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166273"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Konfigurera principer för säkra länkar i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](office-365-atp.md). Om du är hemanvändare och vill ha information om säkra länkar i Outlook kan du [läsa Mer Outlook.com säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Säkra länkar är en funktion i Microsoft Defender för [Office 365](office-365-atp.md) som ger URL-genomsökning av inkommande e-postmeddelanden i e-postflödet och tidpunkten för klickverifiering av URL:er och länkar i e-postmeddelanden och på andra platser. Mer information finns i [Säkra länkar i Microsoft Defender för Office 365.](atp-safe-links.md)

Det finns ingen inbyggd eller standardprincip för säkra länkar. För att få säker länkskanning av URL:er måste du skapa en eller flera principer för säkra länkar enligt beskrivningen i den här artikeln.

> [!NOTE]
> Du konfigurerar de globala inställningarna för skydd mot **säkra länkar utanför** principerna för säkra länkar. Instruktioner finns i Konfigurera [globala inställningar för Säkra länkar i Microsoft Defender för Office 365.](configure-global-settings-for-safe-links.md)

Du kan konfigurera principer för säkra länkar i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Microsoft Defender för Office 365-tilläggsprenumerationer).

Grunderna i en princip för säkra länkar är:

- Principen för säkra **länkar:** Aktivera skydd mot säkra länkar, aktivera URL-genomsökning i realtid, ange om du vill vänta med att skanning i realtid slutförs innan meddelandet levereras, aktivera genomsökning för interna meddelanden, ange om användaren ska klicka på URL-adresser och ange om användarna ska kunna klicka på webbadressen.
- **Regeln för säkra länkar:** Anger prioritet och mottagarfilter (vem principen gäller för).

Skillnaden mellan dessa två element är inte uppenbara när du hanterar säkerhetschefer i Säkerhets- och & Efterlevnadscenter:

- När du skapar en princip för säkra länkar skapar du i själva verket en regel för säkra länkar och den associerade principen för säkra länkar samtidigt som du använder samma namn för båda.
- När du ändrar en princip för säkra länkar ändras regeln för säkra länkar om inställningarna är relaterade till namn, prioritet, aktiverade eller inaktiverade, och mottagarnas filter ändrar regeln för säkra länkar. Alla andra inställningar ändrar den associerade principen för säkra länkar.
- När du tar bort en princip för säkra länkar tas regeln för säkra länkar och den tillhörande principen för säkra länkar bort.

I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat. Mer information finns i avsnittet Använda Exchange Online PowerShell eller [fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) för att konfigurera principer för säkra länkar längre fram i den här artikeln.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt **till sidan Säkra** länkar använder du <https://protection.office.com/safelinksv2> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:
  - Om du vill skapa, ändra och ta bort principer  för säkra  länkar måste du vara medlem i rollgrupperna Organisationshantering  eller Säkerhetsadministratör i Säkerhets- & och efterlevnadscenter och medlem i rollgruppen Organisationshantering i Exchange Online. 
  - För skrivskyddade åtkomst till principer för säkra länkar måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Säkerhets- & Efterlevnadscenter](permissions-in-the-security-and-compliance-center.md) [och Behörigheter i Exchange Online.](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  > 
  > - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  . - **Rollgruppen Skrivskyddade organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddsåtkomst till funktionen.

- Vi rekommenderar inställningar för principer för säkra länkar i [principinställningarna för Säkra länkar.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

- Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.

- [Nya funktioner läggs kontinuerligt till i Microsoft Defender för Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) När nya funktioner läggs till kan du behöva justera dina befintliga principer för säkra länkar.

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>Använda Säkerhets- & för att skapa principer för säkra länkar

Om du skapar en egen princip för säkra länkar i Säkerhets- & efterlevnadscenter skapas regeln för säkra länkar och den tillhörande principen för säkra länkar samtidigt som samma namn används för båda.

1. I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**

2. Klicka på **Skapa på** sidan Säkra **länkar.**

3. Guiden **Ny princip för säkra** länkar öppnas. Konfigurera **följande inställningar på** sidan Namnge principen:

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

   Klicka på Nästa när du är **klar.**

4. På sidan **Inställningar** som visas konfigurerar du följande inställningar:

   - **Välj åtgärden för okända potentiellt skadliga URL:er i** meddelanden: Välj **På** för att aktivera skydd mot säkra länkar för länkar i e-postmeddelanden.

   - **Välj åtgärden för okända eller potentiellt skadliga URL-adresser i Microsoft Teams:** Välj På för **att** aktivera skydd mot säkra länkar för länkar i Teams.

   - **Använd URL-genomsökning** i realtid för misstänkta länkar och länkar som pekar på filer: Välj den här inställningen om du vill aktivera sökning i realtid av länkar i e-postmeddelanden.

   - **Vänta tills URL-skanningen har slutförts innan** du levererar meddelandet: Välj den här inställningen om du vill vänta tills sökningen i realtid har slutförts innan meddelandet levereras.

   - **Tillämpa säkra länkar på e-postmeddelanden** som skickas inom organisationen: Välj den här inställningen om du vill tillämpa principen För säkra länkar på meddelanden mellan interna avsändare och interna mottagare.

   - **Spåra inte användarklick: Låt** den här inställningen vara avmarkerad om du vill aktivera uppföljningsanvändaren klick på URL-adresser i e-postmeddelanden.

   - **Tillåt inte att användare klickar till** den ursprungliga URL:en: Välj den här inställningen om du vill blockera användare från att klicka till den ursprungliga URL:en på [varningssidor.](atp-safe-links.md#warning-pages-from-safe-links)

   - **Skapa inte om följande URL:er:** Ger åtkomst till de angivna URL:er som annars skulle blockeras av säkra länkar.

     I rutan skriver du URL-adressen eller värdet som du vill använda och klickar sedan på ![Knappikonen Lägg till](../../media/ITPro-EAC-AddIcon.png).

     Om du vill ta bort en befintlig post markerar du den och klickar sedan på ![Knappikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.png).

     Mer information om [postsyntaxen finns i Postsyntax för listan "Ange inte följande URL:er".](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Detaljerad information om dessa inställningar finns i inställningarna [för Säkra länkar för e-postmeddelanden](atp-safe-links.md#safe-links-settings-for-email-messages) och inställningar för Säkra länkar för Microsoft [Teams.](atp-safe-links.md#safe-links-settings-for-microsoft-teams)

   Fler rekommenderade värden för principinställningarna Standard och Strikt finns i [principinställningarna för Säkra länkar.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)

   Klicka på Nästa när du är **klar.**

5. På sidan **Används på** som visas identifierar du de interna mottagare som principen gäller för.

   Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

   Klicka **på Lägg till ett villkor.** I listrutan som visas väljer du ett villkor under **Används om:**

   - **Mottagaren är: Anger** en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.
   - **Mottagaren är medlem i:** Anger en eller flera grupper i organisationen.
   - **Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.

   När du har valt villkoret visas en motsvarande listruta med **rutan Valfri av dessa.**

   - Klicka i rutan och bläddra igenom listan med värden för att välja.
   - Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.
   - Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.
   - Om du vill ta bort enskilda poster klickar **du på ta** ![ ](../../media/scc-remove-icon.png) bort-ikonen för värdet.
   - Om du vill ta bort hela villkoret klickar **du på ikonen** Ta bort i ![ ](../../media/scc-remove-icon.png) villkoret.

   Om du vill lägga till ytterligare ett villkor klickar **du på Lägg till ett** villkor och väljer ett återstående värde under Används **om.**

   Om du vill lägga till undantag **klickar du på Lägg till ett** villkor och väljer ett undantag under Utom **om.** Inställningarna och beteendet är likadana som villkoren.

   Klicka på Nästa när du är **klar.**

6. Granska **inställningarna på sidan** Granska dina inställningar som visas. Du kan klicka **på Redigera** för varje inställning för att ändra den.

   Klicka på Slutför när du är **klar.**

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>Använda säkerhets- & efterlevnadscenter för att visa principer för säkra länkar

1. I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**

2. På sidan **Säkra** länkar väljer du en princip i listan och klickar på den (markera inte kryssrutan).

   Principinformationen visas i en flyg utfällning

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>Använda Säkerhets- & säkerhets- och efterlevnadscenter för att ändra principer för säkra länkar

1. I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**

2. På sidan **Säkra** länkar väljer du en princip i listan och klickar på den (markera inte kryssrutan).

3. I den policyinformation som visas klickar du på **Redigera princip.**

De tillgängliga inställningarna i flyg utfällpunkten som visas är identiska med de som beskrivs i Använd säkerhets- och & [säkerhets-](#use-the-security--compliance-center-to-create-safe-links-policies) och efterlevnadscentret för att skapa avsnittet principer för säkra länkar.

Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.

### <a name="enable-or-disable-safe-links-policies"></a>Aktivera eller inaktivera principer för säkra länkar

1. I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**

2. Observera värdet i **kolumnen** Status:

   - Flytta växlingsknappen åt vänster om du vill inaktivera principen: ![Inaktivera principen](../../media/scc-toggle-off.png).

   - Flytta växlingsknappen åt höger om du vill aktivera principen: ![Aktivera princip](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Ange prioritet för principer för säkra länkar

Som standard prioriteras principer för säkra länkar som baseras på den ordning som de skapades i (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

Principer för säkra länkar visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).

> [!NOTE]
> I Säkerhets- & Efterlevnadscenter kan du bara ändra prioriteten för principen för säkra länkar efter att du har skapat den. I PowerShell kan du åsidosätta standardprioritet när du skapar regeln om säkra länkar (vilket kan påverka prioriteten för befintliga regler).

Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).

1. I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**

2. På sidan **Säkra** länkar väljer du en princip i listan och klickar på den (markera inte kryssrutan).

3. I policyinformationen som visas klickar du på den tillgängliga prioritetsknappen:

   - Principen Säkra länkar med **prioritetsvärdet** **0** har endast knappen **Minska** prioritet tillgänglig.

   - Principen Säkra länkar med det lägsta **prioritetsvärdet** (till exempel **3)** har endast knappen Öka **prioritet** tillgänglig.

   - Om du har tre eller fler principer för säkra länkar,  har principer mellan de högsta och lägsta prioritetsvärdena både knapparna Öka prioritet och **Minska** prioritet tillgängliga.

4. Klicka **på Öka prioritet** eller Minska **prioritet** om du vill ändra **prioritetsvärdet.**

5. Klicka på **Stäng** när du är klar.

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>Använda Säkerhets- & för att ta bort principer för säkra länkar

1. I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.**

2. På sidan **Säkra** länkar väljer du en princip i listan och klickar på den (markera inte kryssrutan).

3. I den policyinformation som visas klickar du på **Ta bort princip** och sedan på **Ja** i varningsdialogrutan som visas.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för säkra länkar

Som tidigare beskrivits består en princip för säkra länkar av en princip för säkra länkar och en regel för säkra länkar.

I PowerShell visas skillnaden mellan principer för säkra länkar och regler för säkra länkar. Du hanterar principer för säkra länkar med cmdlets **\* -SafeLinksPolicy** och hanterar regler för säkra länkar med cmdlet:arna **\* -SafeLinksRule.**

- I PowerShell skapar du först principen för säkra länkar och sedan skapar du den regel för säkra länkar som identifierar principen som regeln gäller för.
- I PowerShell ändrar du inställningarna i principen för säkra länkar och regeln om säkra länkar separat.
- När du tar bort en princip för säkra länkar från PowerShell tas inte motsvarande regel för säkra länkar bort automatiskt och vice versa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Använda PowerShell för att skapa principer för säkra länkar

Att skapa en princip för säkra länkar i PowerShell är en process i två steg:

1. Skapa principen för säkra länkar.
2. Skapa den regel för säkra länkar som anger principen för säkra länkar som regeln gäller för.

> [!NOTE]
> 
> - Du kan skapa en ny regel för säkra länkar och tilldela en befintlig, oassocierad princip för säkra länkar till den. En regel för säkra länkar kan inte associeras med mer än en princip för säkra länkar.
> 
> - Du kan konfigurera följande inställningar för nya principer för säkra länkar i PowerShell som inte är tillgängliga i Säkerhets- och &-efterlevnadscentret förrän du har skapat principen:
> 
>   - Skapa den nya principen som inaktiverad _(aktiverad_ `$false` för **cmdleten New-SafeLinksRule).**
>   - Ange prioriteten för principen när den skapas _(Priority)_ _\<Number\>_ på **cmdleten New-SafeLinksRule).**
> 
> - En ny princip för säkra länkar som du skapar i Power & Shell visas inte i Säkerhets- och efterlevnadscenter förrän du tilldelar principen till en regel för säkra länkar.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Steg 1: Använda PowerShell för att skapa en princip för säkra länkar

Använd följande syntax för att skapa en princip för säkra länkar:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - Mer information om postsyntaxen för parametern _DoNotRewriteUrls_ finns i Postsyntaxen för [listan "Ange](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)inte följande URL:er".
> 
> - Mer information om ytterligare syntax som du kan använda för parametern _DoNotRewriteUrls_ när du ändrar befintliga principer för säkra länkar med hjälp av cmdleten **Set-SafeLinksPolicy** finns i avsnittet Använda [PowerShell](#use-powershell-to-modify-safe-links-policies) för att ändra principer för säkra länkar senare i den här artikeln.

I det här exemplet skapas en princip för säkra länkar med namnet Contoso Alla med följande värden:

- Aktivera URL-genomsökning och omskrivning i e-postmeddelanden.
- Aktivera URL-genomsökning i Teams (endast TAP Preview).
- Aktivera genomsökning i realtid av klickade URL:er, inklusive klickade länkar som pekar på filer.
- Vänta tills URL-skanningen är klar innan du levererar meddelandet.
- Aktivera URL-skanning och skriva om interna meddelanden.
- Spåra användarklick relaterade till skydd mot säkra länkar (vi använder inte parametern _DoNotTrackUserClicks_ och standardvärdet är $false, vilket innebär att användarklick spåras).
- Tillåt inte att användare klickar sig fram till den ursprungliga URL:en.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Detaljerad information om syntax och parametrar finns i [New-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Steg 2: Använda PowerShell för att skapa en regel för säkra länkar

Använd följande syntax för att skapa en regel för säkra länkar:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

I det här exemplet skapas en regel för säkra länkar med namnet Contoso Alla med följande villkor:

- Regeln är kopplad till principen för säkra länkar med namnet Contoso All.
- Regeln gäller för alla mottagare i contoso.com domän.
- Eftersom vi inte använder _parametern Priority_ används standardprioritet.
- Regeln är aktiverad (vi använder inte parametern _Aktiverad_ och standardvärdet är `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Detaljerad information om syntax och parametrar finns [i New-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)

### <a name="use-powershell-to-view-safe-links-policies"></a>Använda PowerShell för att visa principer för säkra länkar

Om du vill visa befintliga principer för säkra länkar använder du följande syntax:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Det här exemplet returnerar en sammanfattning av alla principer för säkra länkar.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

I det här exemplet returneras detaljerad information för policyn för säkra länkar med namnet Contoso Executives.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Detaljerad information om syntax och parametrar finns i [Get-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)

### <a name="use-powershell-to-view-safe-links-rules"></a>Använda PowerShell för att visa regler för säkra länkar

Om du vill visa befintliga regler för säkra länkar använder du följande syntax:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Det här exemplet returnerar en sammanfattning av alla regler för säkra länkar.

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

I det här exemplet returneras detaljerad information för regeln om säkra länkar som heter Contoso-chefer.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Detaljerad information om syntax och parametrar finns [i Get-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)

### <a name="use-powershell-to-modify-safe-links-policies"></a>Använda PowerShell för att ändra principer för säkra länkar

Du kan inte byta namn på en princip för säkra länkar i PowerShell **(set-SafeLinksPolicy-cmdleten** har ingen _namnparameter)._ När du byter namn på en princip för säkra länkar & Säkerhets- och efterlevnadscenter byter du bara namn på regeln för säkra _länkar._

Den enda ytterligare överväganden för att ändra principer för säkra länkar i PowerShell är den tillgängliga syntaxen för parametern _DoNotRewriteUrls_ (listan ["Skriva](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)inte om följande URL:er"):

- Om du vill lägga till värden som ska ersätta befintliga poster använder du följande syntax: `"Entry1","Entry2,..."EntryN"` .
- Om du vill lägga till eller ta bort värden utan att påverka andra befintliga poster använder du följande syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Annars är samma inställningar tillgängliga när du skapar en princip för säkra länkar enligt beskrivningen i steg [1:](#step-1-use-powershell-to-create-a-safe-links-policy) Använda PowerShell för att skapa ett avsnitt för principen för säkra länkar tidigare i den här artikeln.

Använd följande syntax för att ändra en princip för säkra länkar:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns [i Set-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)

### <a name="use-powershell-to-modify-safe-links-rules"></a>Använda PowerShell för att ändra regler för säkra länkar

Den enda inställning som inte är tillgänglig när du ändrar en regel för säkra länkar i PowerShell är den aktiverade _parametern_ som gör att du kan skapa en inaktiverad regel. Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för säkra länkar.

Annars är samma inställningar tillgängliga när du skapar en regel enligt beskrivningen i steg [2:](#step-2-use-powershell-to-create-a-safe-links-rule) Använd PowerShell för att skapa ett avsnitt med en regel för säkra länkar tidigare i den här artikeln.

Använd följande syntax för att ändra en regel för säkra länkar:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Detaljerad information om syntax och parametrar finns [i Set-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Använda PowerShell för att aktivera eller inaktivera regler för säkra länkar

Aktivering eller inaktivering av en regel för säkra länkar i PowerShell aktiverar eller inaktiverar hela principen för säkra länkar (regeln om säkra länkar och den tilldelade principen för säkra länkar).

Använd följande syntax för att aktivera eller inaktivera en regel för säkra länkar i PowerShell:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

I det här exemplet inaktiveras regeln om säkra länkar med namnet Marknadsföringsavdelningen.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) och [Disable-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Använda PowerShell för att ange prioritet för regler för säkra länkar

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Använd följande syntax för att ange prioritet för en regel för säkra länkar i PowerShell:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Om du vill ange prioriteten för en  ny regel när du skapar den använder du prioritetsparametern i cmdleten **New-SafeLinksRule** i stället.

Detaljerad information om syntax och parametrar finns [i Set-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-remove-safe-links-policies"></a>Använda PowerShell för att ta bort principer för säkra länkar

När du använder PowerShell för att ta bort en princip för säkra länkar tas motsvarande regel för säkra länkar inte bort.

Använd följande syntax om du vill ta bort en princip för säkra länkar i PowerShell:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

Det här exemplet tar bort principen för säkra länkar med namnet Marknadsföringsavdelningen.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksPolicy.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)

### <a name="use-powershell-to-remove-safe-links-rules"></a>Använda PowerShell för att ta bort regler för säkra länkar

När du använder PowerShell för att ta bort en regel för säkra länkar tas motsvarande princip för säkra länkar inte bort.

Använd följande syntax för att ta bort en regel för säkra länkar i PowerShell:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

I det här exemplet tas regeln om säkra länkar bort med namnet Marknadsföringsavdelningen.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksRule.](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)

Kontrollera vilka Microsoft Defender-rapporter som är tillgängliga för Office 365-rapporter om du vill kontrollera att Säkra länkar söker igenom meddelanden. Mer information finns i [Visa rapporter för Defender för Office 365](view-reports-for-atp.md) och Använda Utforskaren i [Säkerhets- & Efterlevnadscenter.](threat-explorer.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Kontrollera att du har skapat, ändrat eller tagit bort principer för säkra länkar genom att göra något av följande:

- I Säkerhets- & Efterlevnadscenter går du till ATP **–** säkra \> **länkar för** \> **hothanteringspolicy.** Kontrollera listan över principer, deras **statusvärden** och deras **prioritetsvärden.** Om du vill visa mer information väljer du principen i listan och visar informationen i flyg ut.

- I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du med namnet på principen eller regeln, kör följande kommando \<Name\> och kontrollerar inställningarna:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
