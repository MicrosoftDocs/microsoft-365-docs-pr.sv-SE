---
title: Konfigurera principer för säkra bifogade filer i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Läs mer om hur du definierar principer för säkra bifogade filer för att skydda organisationen från skadliga filer i e-postmeddelanden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e96babff19ea981b953d35929813b1e08c000e32
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207365"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Konfigurera principer för säkra bifogade filer i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](whats-new-in-defender-for-office-365.md). Om du är hemanvändare och vill ha information om skanning av bifogade filer i Outlook kan du läsa [Mer Outlook.com säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Säkra bifogade filer är en funktion i Microsoft Defender för [Office 365](whats-new-in-defender-for-office-365.md) som använder en virtuell miljö för att kontrollera bifogade filer i inkommande e-postmeddelanden när de har genomsökts av skydd mot skadlig programvara [i Exchange Online Protection (EOP),](anti-malware-protection.md)men innan de levereras till mottagarna. Mer information finns i Säkra [bifogade filer i Microsoft Defender för Office 365.](safe-attachments.md)

Det finns ingen inbyggd eller standardprincip för säkra bifogade filer. För att kunna skanna bifogade filer i e-postmeddelanden måste du skapa en eller flera principer för säkra bifogade filer enligt beskrivningen i den här artikeln.

Du kan konfigurera principer för säkra bifogade filer i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor men med tilläggsprenumerationer för Defender för Office 365).

De grundläggande elementen i en princip för säkra bifogade filer är:

- **Principen för** säkra bifogade filer: Anger åtgärder för okänd identifiering av skadlig programvara, om du vill skicka meddelanden med bifogade filer från skadlig programvara till en viss e-postadress och om meddelanden ska levereras om genomsökningen efter säkra bifogade filer inte kan slutföras.
- **Regeln för säkra bifogade** filer: Anger prioritet och mottagarfilter (vem principen gäller för).

Skillnaden mellan dessa två element är inte uppenbara när du hanterar säkerhet och säkerhet i & efterlevnadscenter:

- När du skapar en princip för säkra bifogade filer skapar du i själva verket en regel för säkra bifogade filer och den associerade principen för säkra bifogade filer samtidigt som du använder samma namn för båda.
- När du ändrar en princip för säkra bifogade filer ändras regeln för säkra bifogade filer när du ändrar inställningar för namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter. Alla andra inställningar ändrar den associerade principen för säkra bifogade filer.
- När du tar bort en princip för säkra bifogade filer tas regeln för säkra bifogade filer och den tillhörande principen för säkra bifogade filer bort.

I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat. Mer information finns i avsnittet Använda [Exchange Online PowerShell eller fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) för att konfigurera principer för säkra bifogade filer längre fram i den här artikeln.

> [!NOTE]
> I det globala inställningsområdet i inställningarna för säkra bifogade filer konfigurerar du funktioner som inte är beroende av principer för säkra bifogade filer. Anvisningar finns i [Aktivera säkra bifogade filer för SharePoint, OneDrive och Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) och Säkra dokument i Microsoft [365 E5.](safe-docs.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. För att gå direkt till sidan **Säkra bifogade** filer använder du <https://protection.office.com/safeattachmentv2> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan utföra procedurerna i den här artikeln:
  - Om du vill skapa, ändra och ta bort principer för säkra  bifogade filer måste du vara medlem  i rollgrupperna  Organisationshantering eller Säkerhetsadministratör i säkerhets- och efterlevnadscentret för & och medlem i rollgruppen Organisationshantering i Exchange Online. 
  - För skrivskyddade åtkomst till principer för säkra bifogade filer måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare** i Säkerhets- och & Säkerhets- och efterlevnadscenter.

  Mer information finns i [Behörigheter i Säkerhets- & och Behörigheter](permissions-in-the-security-and-compliance-center.md) i Exchange [Online.](/exchange/permissions-exo/permissions-exo)

  **Anmärkningar**:

  - Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Vi rekommenderar inställningar för principer för säkra bifogade filer i inställningarna [för säkra bifogade filer.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Använd säkerhets- och & för att skapa principer för säkra bifogade filer

När du skapar en egen princip för säkra bifogade filer i Säkerhets- och &-efterlevnadscentret skapas en regel för säkra bifogade filer och att tillhörande princip för säkra bifogade filer samtidigt används med samma namn för båda.

1. I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**

2. På sidan **Säkra bifogade** filer klickar du på **Skapa**.

3. Guiden **Ny princip för bifogade** filer öppnas. Konfigurera **följande inställningar på** sidan Namnge principen:

   - **Namn**: Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning**: Ange en valfri beskrivning av principen.

   Klicka på Nästa när du är **klar.**

4. Konfigurera **följande** inställningar på sidan Inställningar som visas:

   - **Okänd information om säkra bifogade filer :** Välj något av följande värden:

     - **Av:** Normalt rekommenderar vi inte det här värdet.
     - **Övervaka**
     - **Block:** Det här är standardvärdet och det rekommenderade värdet i standard- och strikt [förinställda säkerhetsprinciper.](preset-security-policies.md)
     - **Ersätt**
     - **Dynamisk leverans (förhandsgranskningsfunktion)**

     De här värdena förklaras i [principinställningarna för säkra bifogade filer.](safe-attachments.md#safe-attachments-policy-settings)

   - **Skicka** bilagan till följande e-postadress: För åtgärdsvärdena **Block**,  **Bildskärm** eller Ersätt kan du välja Aktivera omdirigering för att skicka meddelanden som innehåller bifogade filer från skadlig programvara till den angivna interna eller externa e-postadressen för analys och undersökning. 

     Rekommendationen för standard- och strikt-principinställningarna är att aktivera omdirigering. Mer information finns i Inställningarna [för säkra bifogade filer.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

   - **Använd markeringen ovan** om genomsökning av skadlig programvara för  bifogade filer på tider eller fel inträffar: Åtgärden som anges av okänt svar på säkra bifogade filer används på meddelanden även om genomsökning av säkra bifogade filer inte kan slutföras. Om du valde det här alternativet ska du alltid **välja Aktiverad omdirigering.** Annars kan meddelanden gå förlorade.

   Klicka på Nästa när du är **klar.**

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

   Klicka på Nästa när du är **klar.**

6. Granska **inställningarna på sidan** Granska dina inställningar som visas. Du kan klicka **på Redigera** för varje inställning för att ändra den.

   Klicka på Slutför när du är **klar.**

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Använd Säkerhets- och & för att visa principer för säkra bifogade filer

1. I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**

2. På sidan **Säkra bifogade** filer väljer du en princip i listan och klickar på den (markera inte kryssrutan).

   Principinformationen visas i en flyg ut

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Använda Säkerhets- och & för att ändra principer för säkra bifogade filer

1. I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**

2. På sidan **Säkra bifogade** filer väljer du en princip i listan och klickar på den (markera inte kryssrutan).

3. I den utfällna menyn med principinformation klickar du på **Redigera princip**.

De tillgängliga inställningarna i flyget som visas är identiska med de som beskrivs i använda säkerhets- och & för att skapa principer för [säkra bifogade](#use-the-security--compliance-center-to-create-safe-attachments-policies) filer.

Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.

### <a name="enable-or-disable-safe-attachments-policies"></a>Aktivera eller inaktivera principer för säkra bifogade filer

1. I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**

2. Observera värdet i **kolumnen** Status:

   - Flytta reglaget åt vänster ![Inaktivera principen](../../media/scc-toggle-off.png) för att inaktivera principen.

   - Flytta reglaget åt höger ![Aktivera princip](../../media/scc-toggle-on.png) för att aktivera principen.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Ange prioritet för principer för säkra bifogade filer

Som standard prioriteras principer för säkra bifogade filer baserat på i vilken ordning de skapades (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

Principer för säkra bifogade filer visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).

**Obs!** I säkerhets- & säkerhets- och efterlevnadscentret kan du bara ändra prioriteten för principen för säkra bifogade filer när du har skapat den. I PowerShell kan du åsidosätta standardprioritet när du skapar regeln om säkra bifogade filer (vilket kan påverka prioriteringen för befintliga regler).

Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).

1. I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**

2. På sidan **Säkra bifogade** filer väljer du en princip i listan och klickar på den (markera inte kryssrutan).

3. I den policyinformation som visas klickar du på knappen med tillgänglig prioritet.

   - Principen för säkra bifogade filer med **prioritetsvärdet** **0** har endast **knappen Minska** prioritet tillgänglig.

   - Principen för säkra bifogade filer med det lägsta **värdet** (till exempel **3)** har endast knappen **Öka** prioritet tillgänglig.

   - Om du har tre eller fler principer för säkra bifogade filer, har principer mellan de högsta och lägsta prioritetsvärdena både knapparna Öka prioritet **och Minska** prioritet tillgängliga. 

4. Klicka **på Öka prioritet** eller Minska **prioritet** om du vill ändra värdet **för** Prioritet.

5. Klicka på **Stäng** när du är klar.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Använda Säkerhets- och & för att ta bort principer för säkra bifogade filer

1. I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.**

2. På sidan **Säkra bifogade** filer väljer du en princip i listan och klickar på den (markera inte kryssrutan).

3. I policyinformationen som visas klickar du på Ta **bort princip** och sedan på **Ja i** varningsdialogrutan som visas.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för säkra bifogade filer

Som tidigare beskrivits består en princip för säkra bifogade filer av en princip för säker bifogad fil och en regel för säker bifogad fil.

I PowerShell syns skillnaden mellan principer för säkra bifogade filer och regler för säkra bifogade filer. Du hanterar principer för säkra bifogade filer med cmdletarna **\* -SafeAttachmentPolicy** och hanterar regler för säkra bifogade filer med cmdlets **\* -SafeAttachmentRule.**

- I PowerShell skapar du först principen för säkra bifogade filer. Sedan skapar du den regel för säkra bifogade filer som identifierar principen som regeln gäller för.
- I PowerShell ändrar du inställningarna i principen för säkra bifogade filer och regeln om säker bifogad fil separat.
- När du tar bort en princip för säkra bifogade filer från PowerShell tas motsvarande regel för säkra bifogade filer inte bort automatiskt, och vice versa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Använda PowerShell för att skapa principer för säkra bifogade filer

Att skapa en princip för säkra bifogade filer i PowerShell är en process i två steg:

1. Skapa principen för säkra bifogade filer.
2. Skapa den regel för säkra bifogade filer som anger principen för säkra bifogade filer som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny regel för säkra bifogade filer och tilldela en befintlig princip för säkra bifogade filer som inte har associerats till den. En regel för säkra bifogade filer kan inte associeras med mer än en princip för säkra bifogade filer.

- Du kan konfigurera följande inställningar för nya principer för säkra bifogade filer i PowerShell som inte är tillgängliga i Säkerhets- och &-efterlevnadscenter förrän du har skapat principen:
  - Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på **cmdleten New-SafeAttachmentRule).**
  - Ange prioritet för principen vid skapande (_Prioritet_ _\<Number\>_ ) på **cmdleten New-SafeAttachmentRule).**

- En ny princip för säkra bifogade filer som du skapar i PowerShell visas inte i Säkerhets- och &-efterlevnadscenter förrän du tilldelar principen till en regel för säkra bifogade filer.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Steg 1: Använda PowerShell för att skapa en princip för säkra bifogade filer

Använd följande syntax för att skapa en princip för säkra bifogade filer:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

I det här exemplet skapas en princip för säkra bifogade filer med namnet Contoso Alla med följande värden:

- Blockera meddelanden som innehåller skadlig programvara genom genomsökning av säkra dokument (vi använder inte parametern _Action_ och standardvärdet är `Block` ).
- Omdirigering är aktiverat och meddelanden som innehåller skadlig programvara skickas till sec-ops@contoso.com för analys och undersökning.
- Om genomsökning av säkra bifogade filer inte är tillgängligt eller stöter på fel levereras inte meddelandet (vi använder inte parametern _ActionOnError_ och standardvärdet är `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Detaljerad information om syntax och parametrar finns i [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Steg 2: Använda PowerShell för att skapa en regel för säkra bifogade filer

Använd följande syntax för att skapa en regel för säkra bifogade filer:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

I det här exemplet skapas en regel för säkra bifogade filer med namnet Contoso Alla med följande villkor:

- Regeln är kopplad till principen för säkra bifogade filer med namnet Contoso All.
- Regeln gäller för alla mottagare i contoso.com domän.
- Eftersom vi inte använder _parametern Priority_ används standardprioritet.
- Regeln är aktiverad (vi använder inte parametern _Enabled_ och standardvärdet är `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Detaljerad information om syntax och parametrar finns [i New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Använda PowerShell för att visa principer för säkra bifogade filer

Använd följande syntax för att visa befintliga principer för säkra bifogade filer:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Det här exemplet returnerar en sammanfattning av alla principer för säkra bifogade filer.

```PowerShell
Get-SafeAttachmentPolicy
```

Det här exemplet returnerar detaljerad information om principen för säkra bifogade filer som heter Contoso-chefer.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Detaljerad information om syntax och parametrar finns i [Get-SafeAttachmentPolicy.](/powershell/module/exchange/get-safeattachmentpolicy)

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Använda PowerShell för att visa regler för säkra bifogade filer

Om du vill visa befintliga regler för säkra bifogade filer använder du följande syntax:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

Det här exemplet returnerar en sammanfattning av alla regler för säkra bifogade filer.

```PowerShell
Get-SafeAttachmentRule
```

Om du vill filtrera listan efter aktiverade eller inaktiverade regler kör du följande kommandon:

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

Det här exemplet returnerar detaljerad information om regeln för säkra bifogade filer som heter Contoso-chefer.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Detaljerad information om syntax och parametrar finns i [Get-SafeAttachmentRule.](/powershell/module/exchange/get-safeattachmentrule)

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Använda PowerShell för att ändra principer för säkra bifogade filer

Du kan inte byta namn på en princip för säkra bifogade filer i PowerShell **(cmdleten Set-SafeAttachmentPolicy** har ingen _namnparameter)._ När du byter namn på en princip för säkra bifogade filer i Säkerhets- & Säkerhets- och efterlevnadscenter byter du bara namn på regeln om säkra bifogade _filer._

Annars är samma inställningar tillgängliga när du skapar en princip för säkra bifogade filer enligt beskrivningen i steg [1:](#step-1-use-powershell-to-create-a-safe-attachment-policy) Använda PowerShell för att skapa en princip för säkra bifogade filer längre fram i den här artikeln.

Använd följande syntax för att ändra en princip för säkra bifogade filer:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Använda PowerShell för att ändra regler för säkra bifogade filer

Den enda inställning som inte är tillgänglig när du ändrar en regel för säkra bifogade filer i PowerShell är parametern _Enabled_ som gör att du kan skapa en inaktiverad regel. Nästa avsnitt innehåller information om hur du aktiverar eller inaktiverar befintliga regler för säkra bifogade filer.

Annars är samma inställningar tillgängliga när du skapar en regel som beskrivs i steg [2:](#step-2-use-powershell-to-create-a-safe-attachment-rule) Använd PowerShell för att skapa en regel för säkra bifogade filer längre fram i den här artikeln.

Använd följande syntax för att ändra en regel för säkra bifogade filer:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [Set-SafeAttachmentRule.](/powershell/module/exchange/set-safeattachmentrule)

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Använda PowerShell för att aktivera eller inaktivera regler för säkra bifogade filer

Om du aktiverar eller inaktiverar en regel för säkra bifogade filer i PowerShell aktiveras eller inaktiveras hela principen för bifogade filer (regeln för säkra bifogade filer och principen för bifogade filer).

Om du vill aktivera eller inaktivera en regel för säkra bifogade filer i PowerShell använder du följande syntax:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

I det här exemplet inaktiveras regeln för säker bifogad fil med namnet Marketing Department.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) och [Disable-SafeAttachmentRule.](/powershell/module/exchange/disable-safeattachmentrule)

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Använda PowerShell för att ange prioritet för regler för säkra bifogade filer

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Om du vill ange prioriteten för en regel för säkra bifogade filer i PowerShell använder du följande syntax:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Obs!** Om du vill ange prioriteten för en ny regel när du skapar den använder du parametern _Priority_ i cmdleten **New-SafeAttachmentRule** i stället.

Detaljerad information om syntax och parametrar finns i [Set-SafeAttachmentRule.](/powershell/module/exchange/set-safeattachmentrule)

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Använda PowerShell för att ta bort principer för säkra bifogade filer

När du använder PowerShell för att ta bort en princip för säkra bifogade filer, tas motsvarande regel för säkra bifogade filer inte bort.

Om du vill ta bort en princip för säkra bifogade filer i PowerShell använder du följande syntax:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

Det här exemplet tar bort principen för säkra bifogade filer med namnet Marknadsföringsavdelningen.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-SafeAttachmentPolicy.](/powershell/module/exchange/remove-safeattachmentpolicy)

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Använda PowerShell för att ta bort regler för säkra bifogade filer

När du använder PowerShell för att ta bort en regel för säkra bifogade filer, tas motsvarande princip för säkra bifogade filer inte bort.

Om du vill ta bort en regel för säkra bifogade filer i PowerShell använder du följande syntax:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

I det här exemplet tas regeln om säker bifogad fil bort med namnet Marknadsföringsavdelningen.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-SafeAttachmentRule.](/powershell/module/exchange/remove-safeattachmentrule)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Kontrollera att du har skapat, ändrat eller tagit bort principer för säkra bifogade filer genom att göra något av följande:

- I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för \>  \> **hothanteringspolicy för säkra bifogade filer.** Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.** Om du vill visa mer information väljer du principen i listan och visar informationen i den utfäll plats du vill ha.

- I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du med namnet på principen eller regeln, kör följande kommando \<Name\> och kontrollerar inställningarna:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Kontrollera att Säkra bifogade filer söker igenom meddelanden genom att titta i tillgängliga Defender-rapporter för Office 365-rapporter. Mer information finns i Visa rapporter för Defender för [Office 365](view-reports-for-mdo.md) och Använda Utforskaren i [Säkerhets- & efterlevnadscenter.](threat-explorer.md)
