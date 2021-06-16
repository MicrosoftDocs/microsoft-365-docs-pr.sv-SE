---
title: Konfigurera principer Valv Länkar i Microsoft Defender för Office 365
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
description: Administratörer kan läsa mer om hur de visar, skapar, ändrar och tar bort Valv-principer och globala Valv-länkar i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 40ae52cfce53c3fa14253a94e72f1a2bccda9a86
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929833"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Konfigurera principer Valv Länkar i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](defender-for-office-365.md). Om du är hemanvändare och vill ha information om säkra länkar i Outlook kan du läsa [Mer Outlook.com-säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Valv Länkar är en funktion i [Microsoft Defender](defender-for-office-365.md) för Office 365 som ger URL-skanning av inkommande e-postmeddelanden i e-postflödet och tidpunkten för klickverifiering av URL:er och länkar i e-postmeddelanden och på andra platser. Mer information finns i artikeln [Valv i Microsoft Defender för Office 365](safe-links.md).

Det finns ingen inbyggd eller standardprincip för Valv länkar. Om du Valv länkar för genomsökning av URL:er måste du skapa en eller flera Valv länkar enligt beskrivningen i den här artikeln.

> [!NOTE]
> Du konfigurerar de globala inställningarna Valv skydd **vid länkar utanför** Valv Principer för länkar. Anvisningar finns i [Konfigurera globala inställningar för Valv i Microsoft Defender för Office 365.](configure-global-settings-for-safe-links.md)

Du kan konfigurera principer för Valv-länkar i Microsoft 365 Defender-portalen eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Microsoft Defender för Office 365-tilläggsprenumerationer).

De grundläggande elementen i en Valv-länkprincip är:

- Principen för säkra **länkar:** Aktivera skydd mot Valv-länkar, aktivera URL-genomsökning i realtid, ange om du vill vänta på att skanning i realtid ska slutföras innan meddelandet levereras, aktivera genomsökning av interna meddelanden, ange om användaren ska klicka på URL-adresser och ange om de vill tillåta att användare klickar på samma webbadress.
- **Regeln säkra länkar:** Anger prioritet och mottagarfilter (vem principen gäller för).

> [!IMPORTANT]
> Administratörer bör överväga olika konfigurationsinställningar för Säkra länkar. Ett av de tillgängliga alternativen är att inkludera användaridentifierande information i Säkra länkar. Med den här funktionen kan *säkerhets ops-team* undersöka potentiella användarintrång, vidta korrigerande åtgärder och begränsa dyrbara överträdelser.

Skillnaden mellan dessa två element är inte uppenbara när du hanterar Valv Länkar i Microsoft 365 Defender-portalen:

- När du skapar Valv princip för länkar skapar du egentligen en regel för säkra länkar och den tillhörande principen för säkra länkar samtidigt med samma namn för båda.
- När du ändrar en Valv-länkprincip ändras regeln för säkra länkar om namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter. Alla andra inställningar ändrar den associerade principen för säkra länkar.
- När du tar Valv princip för säkra länkar och den tillhörande principen för säkra länkar tas den bort.

I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat. Mer information finns i avsnittet Använda Exchange Online PowerShell eller [fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) för att konfigurera Valv-länkar längre fram i den här artikeln.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com/>. Om du vill gå **direkt Valv sidan** Länkar använder du <https://security.microsoft.com/safelinksv2> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:
  - Om du vill skapa, ändra och ta bort Valv-länkar måste du  vara medlem i rollgrupperna Organisationshantering  eller Säkerhetsadministratör  i Microsoft 365 Defender-portalen och medlem i rollgruppen Organisationshantering i Exchange Online. 
  - För skrivskyddade åtkomst Valv länkar måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**

  Mer information finns i [Behörigheter i Microsoft 365 Defender-portalen](permissions-in-the-security-and-compliance-center.md) och [Behörigheter i Exchange Online.](/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  > 
  > - Om du lägger till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna  de behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  . - **Rollgruppen Skrivskyddade** organisationshantering i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) även skrivskyddade funktioner för funktionen.

- Vi rekommenderar inställningar för att Valv principer för länkar i Valv [principinställningar för länkar.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

- Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.

- [Nya funktioner läggs kontinuerligt till i Microsoft Defender för Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365). När nya funktioner läggs till kan du behöva justera dina befintliga principer Valv Länkar.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>Använda Defender Microsoft 365 portalen för att skapa Valv länkar

När du skapar Valv egen princip för Microsoft 365 Defender-portalen skapas regeln för säkra länkar och den tillhörande principen för säkra länkar samtidigt med samma namn för båda.

1. I Microsoft 365 Defender-portalen går du till **Principer & principer för** hot \> **Valv** \> **.**

2. På sidan **Valv klickar** du på **Skapa**.

3. Principguiden **Valv Länkar** öppnas. Konfigurera **följande inställningar på** sidan Namnge principen:

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

   Klicka på **Nästa** när du är klar.

4. På **Inställningar** som visas konfigurerar du följande inställningar:

   - **Välj åtgärden för okända potentiellt skadliga URL-adresser i meddelanden:** Välj **På** för att Valv skydd mot länkar i e-postmeddelanden.

   - **Välj åtgärden för okända eller potentiellt skadliga URL-adresser** i Microsoft Teams : Välj På för att aktivera Valv skydd för länkar i Teams. 

   - **Använd URL-skanning i realtid** för misstänkta länkar och länkar som pekar på filer: Välj den här inställningen om du vill aktivera genomsökning i realtid av länkar i e-postmeddelanden.

   - **Vänta tills URL-skanningen** är klar innan du levererar meddelandet : Välj den här inställningen om du vill vänta på att URL-skanningen i realtid ska slutföras innan meddelandet levereras.

   - Använd Valv länkar till e-postmeddelanden som skickas inom organisationen: Välj den här inställningen om du vill använda principen **Valv-länkar** för meddelanden mellan interna avsändare och interna mottagare.

   - **Spåra inte användarklick: Låt den** här inställningen vara avmarkerad om du vill aktivera uppföljningsanvändaren klick på URL:er i e-postmeddelanden.

   - **Tillåt inte att användare klickar sig fram till** den ursprungliga URL:en: Välj den här inställningen om du vill blockera användare från att klicka till den ursprungliga URL:en på [varningssidor.](safe-links.md#warning-pages-from-safe-links)

   - **Skriva inte om följande URL:er:** Ger åtkomst till angivna URL:er som annars skulle blockeras av Valv Länkar.

     I rutan skriver du webbadressen eller värdet som du vill använda och klickar sedan på ![Knappikonen Lägg till](../../media/ITPro-EAC-AddIcon.png).

     Om du vill ta bort en befintlig post markerar du den och klickar på ![Knappikonen Ta bort](../../media/ITPro-EAC-DeleteIcon.png).

     Information om [postsyntax finns i Postsyntax för listan "Ange inte om följande URL:er".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Detaljerad information om dessa inställningar finns i inställningar [Valv för](safe-links.md#safe-links-settings-for-email-messages) e-postmeddelanden och inställningar Valv länkar [för Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).

   Fler rekommenderade värden för principinställningarna Standard och Strikt finns i Valv [principinställningar för Länkar.](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

   Klicka på **Nästa** när du är klar.

5. På sidan **Används på** som visas identifierar du de interna mottagare som principen gäller för.

   Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_).

   Klicka **på Lägg till ett villkor.** I listrutan som visas väljer du ett villkor under **Används om:**

   - **Mottagaren är: Anger** en eller flera postlådor, e-postanvändare eller e-postkontakter i organisationen.
   - **Mottagaren är medlem i**: Anger en eller flera grupper i organisationen.
   - **Mottagande domän är**: Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.

   När du har valt villkoret visas motsvarande listruta med rutan **Valfri av dessa.**

   - Klicka i rutan och bläddra igenom listan med värden du vill välja.
   - Klicka i rutan och börja skriva för att filtrera listan och välja ett värde.
   - Om du vill lägga till ytterligare värden klickar du i ett tomt område i rutan.
   - Om du vill ta bort enskilda poster klickar **du på Ta** bort ikon för ![ ](../../media/scc-remove-icon.png) värdet.
   - Om du vill ta bort hela villkoret klickar du **på Ta** bort ikon ![ för ](../../media/scc-remove-icon.png) villkoret.

   Om du vill lägga till ytterligare ett villkor klickar **du på Lägg till ett** villkor och väljer ett återstående värde under Används **om**.

   Om du vill lägga till undantag klickar **du på Lägg till ett** villkor och väljer ett undantag under Utom **om**. Inställningarna och beteendet är likadana som villkoren.

   Klicka på **Nästa** när du är klar.

6. Granska **inställningarna på sidan** Granska dina inställningar som visas. Du kan klicka **på Redigera** för varje inställning för att ändra den.

   Klicka på Slutför när du är **klar.**

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>Använda Defender Microsoft 365 portalen för att visa Valv principer för länkar

1. I Microsoft 365 Defender-portalen går du till **Principer & principer för** hot \> **Valv** \> **.**

2. På **Valv länkar** väljer du en princip i listan och klickar på den (markera inte kryssrutan).

   Principinformationen visas i en flyg ut

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>Använda Defender Microsoft 365 portalen för att ändra Valv länkar

1. I Microsoft 365 Defender-portalen går du till ***Principer & principer för** hot \> **Valv** \> **.**

2. På **Valv länkar** väljer du en princip i listan och klickar på den (markera inte kryssrutan).

3. I den utfällna menyn med principinformation klickar du på **Redigera princip**.

De tillgängliga inställningarna som visas är identiska med de som beskrivs i avsnittet [använda Defender Microsoft 365 för att skapa Valv-länkar.](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)

Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.

### <a name="enable-or-disable-safe-links-policies"></a>Aktivera eller inaktivera Valv länkar

1. I Microsoft 365 Defender-portalen går du till **Principer & principer för** hot \> **Valv** \> **.**

2. Observera värdet i **kolumnen** Status:

   - Flytta växlingsknappen åt vänster om du vill inaktivera principen: ![Inaktivera principen](../../media/scc-toggle-off.png).

   - Flytta växlingsknappen åt höger om du vill aktivera principen: ![Aktivera princip](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>Ange prioriteten för Valv-länkar

Som standard prioriteras Valv-länkar-principer som baseras på den ordning de skapades i (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

Valv Länkprinciper visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).

> [!NOTE]
> I Microsoft 365 Defender-portalen kan du bara ändra prioritet för Valv Länkar när du har skapat den. I PowerShell kan du åsidosätta standardprioritet när du skapar regeln om säkra länkar (vilket kan påverka prioriteringen för befintliga regler).

Om du vill ändra prioriteten för en princip flyttar du principen uppåt  eller nedåt i listan (du kan inte direkt ändra prioritetsnumret i Microsoft 365 Defender-portalen).

1. I Microsoft 365 Defender-portalen går du till **Principer & principer för** hot \> **Valv** \> **.**

2. På **Valv länkar** väljer du en princip i listan och klickar på den (markera inte kryssrutan).

3. I den policyinformation som visas klickar du på knappen med tillgänglig prioritet:

   - Principen Valv med **prioritetsvärdet** **0** har endast knappen **Minska** prioritet tillgänglig.

   - Principen Valv med det lägsta värdet **för** Prioritet (till exempel **3**) har endast knappen **Öka** prioritet tillgänglig.

   - Om du har tre eller fler Valv-länkar finns det både knapparna  Öka prioritet och Minska prioritet mellan de högsta och lägsta  prioritetsvärdena.

4. Klicka **på Öka prioritet** eller Minska **prioritet** om du vill ändra värdet **för** Prioritet.

5. Klicka på **Stäng** när du är klar.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>Använda Defender-Microsoft 365 för att ta bort principer Valv Länkar

1. I Microsoft 365 Defender-portalen går du till **Principer & principer för** hot \> **Valv** \> **.**

2. På **Valv länkar** väljer du en princip i listan och klickar på den (markera inte kryssrutan).

3. I policyinformationen som visas klickar du på Ta **bort princip** och sedan på **Ja i** varningsdialogrutan som visas.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera Valv-länkar

Som tidigare beskrivits består en Valv-länkprincip av en princip för säkra länkar och en regel för säkra länkar.

I PowerShell visas skillnaden mellan principer för säkra länkar och regler för säkra länkar. Du hanterar principer för säkra länkar med hjälp av cmdletarna **\* -SafeLinksPolicy** och hanterar regler för säkra länkar med hjälp av cmdletarna **\* -SafeLinksRule.**

- I PowerShell skapar du först principen för säkra länkar och sedan skapar du den regel för säkra länkar som identifierar principen som regeln gäller för.
- I PowerShell ändrar du inställningarna i principen för säkra länkar och regeln om säkra länkar separat.
- När du tar bort en princip för säkra länkar från PowerShell tas inte motsvarande regel för säkra länkar bort automatiskt och vice versa.

### <a name="use-powershell-to-create-safe-links-policies"></a>Använda PowerShell för att skapa Valv-länkar

Att skapa Valv princip för Länkar i PowerShell är en process i två steg:

1. Skapa principen för säkra länkar.
2. Skapa den regel för säkra länkar som anger principen för säkra länkar som regeln gäller för.

> [!NOTE]
> 
> - Du kan skapa en ny regel för säkra länkar och tilldela en befintlig princip för säkra länkar som inte har associerats till den. En regel för säkra länkar kan inte associeras med mer än en princip för säkra länkar.
> 
> - Du kan konfigurera följande inställningar för nya principer för säkra länkar i PowerShell som inte är tillgängliga i Microsoft 365 Defender-portalen förrän du har skapat principen:
> 
>   - Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på **cmdleten New-SafeLinksRule).**
>   - Ange prioritet för principen vid skapandet _(Priority_ _\<Number\>_ ) på **New-SafeLinksRule-cmdleten).**
> 
> - En ny princip för säkra länkar som du skapar i PowerShell visas inte i Microsoft 365 Defender-portalen förrän du tilldelar principen till en regel för säkra länkar.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Steg 1: Använda PowerShell för att skapa en princip för säkra länkar

Använd följande syntax för att skapa en princip för säkra länkar:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - Mer information om postsyntaxen för parametern _DoNotRewriteUrls_ finns i Postsyntax för listan "Ange inte om följande URL:er". [](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)
> 
> - Ytterligare syntax som du kan använda för parametern _DoNotRewriteUrls_ när du ändrar befintliga principer för säkra länkar med hjälp av cmdleten **Set-SafeLinksPolicy** finns i avsnittet Använda [PowerShell](#use-powershell-to-modify-safe-links-policies) för att ändra principer för säkra länkar längre fram i den här artikeln.

I det här exemplet skapas en princip för säkra länkar med namnet Contoso Alla med följande värden:

- Aktivera URL-skanning och skriva om den i e-postmeddelanden.
- Aktivera URL-skanning i Teams (endast TAP Preview).
- Aktivera genomsökning i realtid av klickade URL:er, inklusive klickade länkar som pekar på filer.
- Vänta tills URL-skanningen är klar innan du levererar meddelandet.
- Aktivera URL-genomsökning och skriva om interna meddelanden.
- Spåra användarklick relaterade till Valv-länkskydd (vi använder inte parametern _DoNotTrackUserClicks_ och standardvärdet är $false vilket innebär att användarklickningar spåras).
- Tillåt inte att användare klickar sig fram till den ursprungliga URL:en.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Detaljerad information om syntax och parametrar finns [i New-SafeLinksPolicy.](/powershell/module/exchange/new-safelinkspolicy)

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Steg 2: Använda PowerShell för att skapa en regel för säkra länkar

Använd följande syntax för att skapa en regel för säkra länkar:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

I det här exemplet skapas en regel för säkra länkar med namnet Contoso Alla med följande villkor:

- Regeln är kopplad till principen För säkra länkar med namnet Contoso Alla.
- Regeln gäller för alla mottagare i contoso.com domän.
- Eftersom vi inte använder _parametern Priority_ används standardprioritet.
- Regeln är aktiverad (vi använder inte parametern _Enabled_ och standardvärdet är `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Detaljerad information om syntax och parametrar finns [i New-SafeLinksRule.](/powershell/module/exchange/new-safelinksrule)

### <a name="use-powershell-to-view-safe-links-policies"></a>Använda PowerShell för att visa principer för säkra länkar

Använd följande syntax för att visa befintliga principer för säkra länkar:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Det här exemplet returnerar en sammanfattningslista över alla principer för säkra länkar.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

Det här exemplet returnerar detaljerad information om principen för säkra länkar som heter Contoso-chefer.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Detaljerad information om syntax och parametrar finns i [Get-SafeLinksPolicy.](/powershell/module/exchange/get-safelinkspolicy)

### <a name="use-powershell-to-view-safe-links-rules"></a>Använda PowerShell för att visa regler för säkra länkar

Om du vill visa befintliga regler för säkra länkar använder du följande syntax:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Det här exemplet returnerar en sammanfattningslista över alla regler för säkra länkar.

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

Det här exemplet returnerar detaljerad information om regeln Contoso Executives som heter Säkra länkar.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Detaljerad information om syntax och parametrar finns i [Get-SafeLinksRule.](/powershell/module/exchange/get-safelinksrule)

### <a name="use-powershell-to-modify-safe-links-policies"></a>Använda PowerShell för att ändra principer för säkra länkar

Du kan inte byta namn på en princip för säkra länkar i PowerShell **(Set-SafeLinksPolicy-cmdleten** har ingen _namnparameter)._ När du byter namn Valv princip för Microsoft 365 Defender-portalen byter du bara namn på regeln för säkra _länkar._

Den enda ytterligare faktorn för att ändra principer för säkra länkar i PowerShell är den tillgängliga syntaxen för parametern _DoNotRewriteUrls_ (listan ["Ange](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)inte om följande URL:er"):

- Om du vill lägga till värden som ska ersätta befintliga poster använder du följande syntax: `"Entry1","Entry2,..."EntryN"` .
- Om du vill lägga till eller ta bort värden utan att påverka andra befintliga poster använder du följande syntax: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Annars är samma inställningar tillgängliga när du skapar en princip för säkra länkar enligt beskrivningen i steg [1:](#step-1-use-powershell-to-create-a-safe-links-policy) Använda PowerShell för att skapa en princip för säkra länkar längre fram i den här artikeln.

Använd följande syntax för att ändra en princip för säkra länkar:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [Set-SafeLinksPolicy.](/powershell/module/exchange/set-safelinkspolicy)

### <a name="use-powershell-to-modify-safe-links-rules"></a>Använda PowerShell för att ändra regler för säkra länkar

Den enda inställning som inte är tillgänglig när du ändrar en regel för säkra länkar i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel. Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för säkra länkar.

Annars är samma inställningar tillgängliga när du skapar en regel som beskrivs i steg [2:](#step-2-use-powershell-to-create-a-safe-links-rule) Använd PowerShell för att skapa en regel för säkra länkar längre fram i den här artikeln.

Använd följande syntax för att ändra en regel för säkra länkar:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Detaljerad information om syntax och parametrar finns [i Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Använda PowerShell för att aktivera eller inaktivera regler för säkra länkar

Om du aktiverar eller inaktiverar en regel för säkra länkar i PowerShell aktiveras eller inaktiveras hela Valv Links-principen (regeln för säkra länkar och den tilldelade principen för säkra länkar).

Om du vill aktivera eller inaktivera en regel för säkra länkar i PowerShell använder du följande syntax:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

I det här exemplet inaktiveras regeln För säkra länkar med namnet Marknadsföringsavdelningen.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Enable-SafeLinksRule och](/powershell/module/exchange/enable-safelinksrule) [Disable-SafeLinksRule.](/powershell/module/exchange/disable-safelinksrule)

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Använda PowerShell för att ange prioritet för regler för säkra länkar

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Ange prioritet för en regel för säkra länkar i PowerShell med följande syntax:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-SafeLinksRule** i stället.

Detaljerad information om syntax och parametrar finns [i Set-SafeLinksRule.](/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-remove-safe-links-policies"></a>Använda PowerShell för att ta bort principer för säkra länkar

När du använder PowerShell för att ta bort en princip för säkra länkar tas motsvarande regel för säkra länkar inte bort.

Använd följande syntax för att ta bort en princip för säkra länkar i PowerShell:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

Det här exemplet tar bort principen för säkra länkar med namnet Marknadsföringsavdelningen.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksPolicy.](/powershell/module/exchange/remove-safelinkspolicy)

### <a name="use-powershell-to-remove-safe-links-rules"></a>Använda PowerShell för att ta bort regler för säkra länkar

När du använder PowerShell för att ta bort en regel för säkra länkar tas motsvarande princip för säkra länkar inte bort.

Använd följande syntax för att ta bort en regel för säkra länkar i PowerShell:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

Det här exemplet tar bort regeln om säkra länkar med namnet Marknadsföringsavdelningen.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-SafeLinksRule.](/powershell/module/exchange/remove-safelinksrule)

Kontrollera att Valv söker igenom meddelanden genom att titta i tillgängliga Microsoft Defender Office 365. Mer information finns i [Visa rapporter för Defender för Office 365](view-reports-for-mdo.md) och Använda [Utforskaren i Microsoft 365 Defender-portalen.](threat-explorer.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Kontrollera att du har skapat, ändrat eller tagit bort principer Valv länkar genom att göra något av följande:

- I Defender Microsoft 365 portalen går du till **Principer för & principer** för hot \> **Valv** \> **.** Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.** Om du vill visa mer information väljer du principen i listan och visar informationen i den utfäll plats du vill ha.

- I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du med namnet på principen eller regeln, kör följande kommando och \<Name\> kontrollerar inställningarna:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```