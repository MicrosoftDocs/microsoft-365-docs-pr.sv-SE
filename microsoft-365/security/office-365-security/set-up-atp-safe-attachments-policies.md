---
title: Konfigurera principer för säkra bifogade filer i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Lär dig hur du definierar principer för säkra bifogade filer för att skydda din organisation från skadliga filer via e-post.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca0bfb7ba91f86fee187cfe3445c0dd6c8d4ad56
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845498"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Konfigurera principer för säkra bifogade filer i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Den här artikeln är avsedd för företags kunder som har [Microsoft Defender för Office 365](office-365-atp.md). Om du är hem användare letar efter information om genomsökning av bifogade filer i Outlook, se [avancerad Outlook.com säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Säkra bifogade filer är en funktion i [Microsoft Defender för Office 365](office-365-atp.md) som använder en virtuell miljö för att kontrol lera bilagor i inkommande e-postmeddelanden efter att de har skannats av [skydd mot skadlig program vara i Exchange Online Protection (EOP)](anti-malware-protection.md), men innan de levereras till mottagarna. Mer information finns i avsnitten [om säkra bifogade filer i Microsoft Defender för Office 365](atp-safe-attachments.md).

Det finns ingen inbyggd eller standard princip för säker bifogad fil. Om du vill söka efter säkra bilagor i e-postbilagor måste du skapa en eller flera principer för säker bifogad fil enligt beskrivningen i den här artikeln.

Du kan konfigurera principer för säkra bifogade filer i fältet säkerhets & efterlevnad eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Defender för Office 365-tilläggs prenumerationer).

De grundläggande delarna i en policy för principer för bifogade filer är:

- **Principen för säker bifogad fil** : anger åtgärderna för okända identifieringar av skadlig program vara om du vill skicka meddelanden med bifogade filer till en viss e-postadress och om det inte går att slutföra säkra bilagor.
- **Regeln för säker bifogad fil** : anger de prioritets-och mottagar filter (som principen gäller för).

Skillnaden mellan dessa två element är inte uppenbar när du hanterar Safe Attachment-principer i säkerhets & Compliance Center:

- När du skapar en policy för säker bifogade filer skapar du verkligen en regel för säker bifogad fil och den associerade principen för säker bifogad fil samtidigt med samma namn för båda.
- När du ändrar en policy för en säker bifogad fil kan inställningar som gäller namn, prioritet, aktive rad eller inaktive rad och mottagar filter ändra regeln för säker bifogade filer. Alla andra inställningar ändrar den associerade principen för säker bifogad fil.
- När du tar bort en princip för säker bifogad fil tas reglerna för den säkra bifogade filen och den associerade principen för säker bifogade filer bort

I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat. Mer information finns i [använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för säker bifogade filer](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) längre fram i den här artikeln.

> [!NOTE]
> I området globala inställningar i inställningar för säker bifogade filer konfigurerar du funktioner som inte är beroende av principer för säker bifogad fil. Anvisningar finns i [Aktivera ATP för SharePoint-, OneDrive-och Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) och [Safe-dokument i Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Använd om du vill gå direkt till sidan **betrodda bifogade filer** <https://protection.office.com/safeattachmentv2> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Om du vill visa, skapa, ändra och ta bort principer för säkra bifogade filer måste du vara medlem i någon av följande roll grupper:

  - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
  - **Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- De rekommenderade inställningarna för principer för säkra bifogade filer finns i [Inställningar för säkra bifogade filer](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

- Tillåt upp till 30 minuter för att en ny eller uppdaterad princip ska tillämpas.

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>Skapa principer för säkra bifogade filer med hjälp av säkerhets & efterlevnad

Om du skapar en anpassad princip för säker bifogade filer i säkerhets & Compliance Center skapas regeln för säker bifogad fil och den associerade principen för säker bifogad fil med samma namn för båda.

1. I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.

2. På sidan **betrodda bifogade filer** klickar du på **skapa**.

3. Guiden **ny princip för säkert bifogade filer** öppnas. På sidan **namnge din policy** konfigurerar du följande inställningar:

   - **Namn** : Ange ett unikt, beskrivande namn på principen.

   - **Beskrivning** : Ange en valfri beskrivning av principen.

   När du är klar klickar du på **Nästa**.

4. På sidan **Inställningar** som visas konfigurerar du följande inställningar:

   - **Säkra bifogade filer okänt antivirus program** : Välj något av följande värden:

     - **Av** : vanligt vis rekommenderar vi inte det här värdet.
     - **Övervaka**
     - **Block** : det här är standardvärdet och det rekommenderade värdet i säkerhets principer för standard-och Strict- [förvalda](preset-security-policies.md).
     - **Byter**
     - **Dynamisk leverans (för hands version)**

     Dessa värden förklaras i [princip inställningar för säkra bifogade filer](atp-safe-attachments.md#safe-attachments-policy-settings).

   - **Skicka bilagan till följande e-post adress** : för åtgärds värden **blockera** , **övervaka** eller **ersätta** kan du välja **Aktivera omdirigering** för att skicka meddelanden som innehåller bifogade filer med skadlig kod till angiven intern eller extern e-postadress för analys och undersökning.

     Rekommendationen för standard-och strikta princip inställningar är att aktivera omdirigering. Mer information finns i [Inställningar för säkra bifogade filer](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).

   - **Använda ovanstående markering om genomsökning av skadlig kod för bifogade filer eller fel inträffar** : åtgärden som anges av **osäkra bifogade filer inget svar på skadlig program** vara tas med när säkra bilagor inte kan slutföras. Välj alltid det här alternativet om du väljer **Aktivera omdirigering**. Annars kan meddelanden gå förlorade.

   När du är klar klickar du på **Nästa**.

5. **På sidan som** visas anger du vilka interna mottagare som principen gäller för.

   Du kan bara använda ett villkor eller undantag en gång, men du kan ange flera värden för villkoret eller undantaget. Flera värden för samma villkor eller undantag använder ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_ ). Olika villkor och undantag använder OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_ ).

   Klicka på **Lägg till ett villkor**. I den nedrullningsbara List rutan som visas väljer du ett villkor under **används om** :

   - **Mottagaren är** : anger en eller flera post lådor, e-postkonton eller e-postkontakter i din organisation.
   - **Mottagaren är medlem i** : anger en eller flera grupper i din organisation.
   - **Mottagande domän är** : Anger mottagare i en eller flera av de godkända domänerna som har konfigurerats i din organisation.

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

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>Använda säkerhets & Compliance Center för att visa principer för säkra bifogade filer

1. I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.

2. På sidan **betrodda bifogade filer** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).

   Princip detaljerna visas i ett flyg utåt

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>Använda säkerhets & Compliance Center för att ändra principer för säkra bifogade filer

1. I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.

2. På sidan **betrodda bifogade filer** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).

3. I princip informationen som visas klickar du på **Redigera princip**.

Tillgängliga inställningar i rutan Lägg på som visas är identiska med de som beskrivs i avsnittet [använda säkerhets & efterlevnad för att skapa principer för säker bifogade filer](#use-the-security--compliance-center-to-create-safe-attachments-policies) .

Om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principer kan du läsa följande avsnitt.

### <a name="enable-or-disable-safe-attachments-policies"></a>Aktivera eller inaktivera principer för säkra bifogade filer

1. I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.

2. Observera värdet i kolumnen **status** :

   - Flytta reglaget till vänster ![Inaktivera princip](../../media/scc-toggle-off.png) Om du vill inaktivera principen.

   - Flytta reglaget till höger ![Aktivera princip](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) för att aktivera policyn.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Ange prioritet för principer för säkra bifogade filer

Som standard ges principer för säkra bifogade filer en prioritet som baseras på den ordning de skapades i (nyare principer är lägre prioritet än äldre regler). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

Principer för säkra bifogade filer visas i den ordning de behandlas (den första principen har **prioritet** svärdet 0).

**Obs!** i säkerhets & Compliance Center kan du bara ändra prioriteten för principen för säkra bifogade filer när du har skapat den. I PowerShell kan du åsidosätta standard prioriteten när du skapar regeln för Safe Attachments (som kan påverka prioriteten för befintliga regler).

Du ändrar prioriteten för en princip genom att flytta principen uppåt eller nedåt i listan (du kan inte ändra **prioritetsnumret** direkt i Säkerhets- och efterlevnadscenter).

1. I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.

2. På sidan **betrodda bifogade filer** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).

3. I den princip information som visas klickar du på knappen tillgänglig prioritet.

   - Principen för säkra bifogade filer med **prioritet** svärdet **0** har bara knappen **minska prioritet** tillgänglig.

   - Principen för säkra bifogade filer med lägst **prioritet** (till exempel **3** ) har bara knappen **öka prioritet** tillgänglig.

   - Om du har tre eller fler principer för säkra bifogade filer har principer mellan de högsta och lägsta prioriteterna både knappen **öka prioritet** och knappen för att **minska prioriteten** tillgängliga.

4. Klicka på **öka prioritet** eller **minska prioritet** för att ändra **prioritet** svärdet.

5. Klicka på **Stäng** när du är klar.

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>Använda säkerhets & efterlevnad för att ta bort principer för säkra bifogade filer

1. I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**.

2. På sidan **betrodda bifogade filer** väljer du en princip i listan och klickar på den (markerar inte kryss rutan).

3. I princip detaljerna som visas klickar du på **ta bort princip** och sedan på **Ja** i varnings dialog rutan som visas.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer för skyddade bifogade filer

Som du redan har beskrivit innehåller en policy för säker bifogade filer och en regel för säker bifogad fil.

I PowerShell är skillnaden mellan principer för säker bilaga och regler för säker bifogad fil synlig. Du hanterar principer för säker bilaga genom att använda cmdletarna **\* -SafeAttachmentPolicy** och du hanterar regler för säkerhets bilagor genom att använda cmdlet **\* -SafeAttachmentRule** .

- I PowerShell skapar du principen för säker bifogad fil först och skapar sedan regeln för säker bifogad fil som identifierar den princip som regeln gäller för.
- I PowerShell ändrar du inställningarna för principen för säker bifogad fil och regeln för säker bifogad fil separat.
- När du tar bort en princip för en säker bifogad fil från PowerShell tas inte motsvarande regel för säker bilaga automatiskt bort och vice versa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Använda PowerShell för att skapa principer för säkra bifogade filer

Att skapa en policy för säker bifogad fil i PowerShell är en process i två steg:

1. Skapa principen för säker bifogad fil.
2. Skapa regeln för säker bifogad fil som anger den policy för säker bifogad fil som regeln gäller för.

 **Anmärkningar** :

- Du kan skapa en ny regel för en säker bilaga och koppla en befintlig, icke associerad princip för säker bifogad fil till den. En regel för säker bifogad fil kan inte kopplas till fler än en princip för säker bifogad fil.

- Du kan konfigurera följande inställningar i nya principer för säker bifogade filer i PowerShell som inte är tillgängliga i säkerhets & Compliance Center förrän du har skapat principen:
  - Skapa den nya principen som inaktive rad ( _aktive rad_ `$false` på **New-SafeAttachmentRule-** cmdleten).
  - Ange prioriteten för principen när den skapas ( _prioritet_ _\<Number\>_ ) på den **nya SafeAttachmentRule-** cmdleten.

- En ny princip för säker bifogad fil som du skapar i PowerShell visas inte i säkerhets & Compliance Center förrän du tilldelar principen till en regel för säker bifogad fil.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Steg 1: använda PowerShell för att skapa en policy för säker bifogad fil

Använd den här syntaxen om du vill skapa en policy för säker bifogad fil:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

I det här exemplet skapas en policy för säker bifogad fil med namnet contoso alla med följande värden:

- Blockera meddelanden som innehåller skadlig kod för genomsökning av säkra dokument (vi använder inte parametern _åtgärd_ och standardvärdet `Block` ).
- Omdirigering är aktiverat och meddelanden som innehåller skadlig kod skickas till sec-ops@contoso.com för analys och undersökning.
- Om det inte går att söka efter säkra bifogade filer eller om du stöter på fel ska du inte skicka meddelandet (vi använder inte parametern _ActionOnError_ och standardvärdet `$true` ).

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

Detaljerad information om syntax och parametrar finns i [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>Steg 2: använda PowerShell för att skapa en regel för säker bifogad fil

Använd den här syntaxen om du vill skapa en regel för en säker bifogad fil:

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

I det här exemplet skapas en Safe Attachment-regel med namnet contoso alla med följande villkor:

- Regeln kopplas till principen för säker bifogad fil med namnet contoso all.
- Regeln gäller för alla mottagare i contoso.com-domänen.
- Eftersom vi inte använder _prioritets_ parametern används standard prioriteten.
- Regeln är aktive rad (vi använder inte den _aktiverade_ parametern och standardvärdet är `$true` ).

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Detaljerad information om syntax och parametrar finns i [New-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule).

### <a name="use-powershell-to-view-safe-attachment-policies"></a>Använda PowerShell för att visa principer för säker bifogad fil

Använd följande syntax för att visa befintliga principer för säker bifogade filer:

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

I det här exemplet returneras en sammanfattnings lista över alla principer för säker bifogad fil.

```PowerShell
Get-SafeAttachmentPolicy
```

I det här exemplet returneras detaljerad information för principen för säker bifogad fil med contoso Executives.

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

Detaljerad information om syntax och parametrar finns i [Get-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy).

### <a name="use-powershell-to-view-safe-attachment-rules"></a>Använda PowerShell för att visa regler för säkerhets bifogade filer

Använd följande syntax för att visa befintliga regler för säker bifogade filer:

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

I det här exemplet returneras en sammanfattande lista över alla regler för säker bifogad fil.

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

I det här exemplet returneras detaljerad information för regeln för den säkra bifogade filen contoso-chefer.

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

Detaljerad information om syntax och parametrar finns i [Get-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule).

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>Använda PowerShell för att ändra principer för säker bifogad fil

Det går inte att byta namn på en policy för säker bifogad fil i PowerShell (cmdleten **set-SafeAttachmentPolicy** , har ingen _namn_ parameter). När du byter namn på en princip för ett säkert bifogade filer i säkerhets & Compliance Center byts du bara namn på _regeln_ för säker bifogad fil.

I annat fall är samma inställningar tillgängliga när du skapar en policy för säker bifogad fil enligt beskrivningen i [steg 1: använda PowerShell för att skapa en policy för säker bifogad fil](#step-1-use-powershell-to-create-a-safe-attachment-policy) i den här artikeln.

Använd den här syntaxen om du vill ändra en policy för en säker bifogad fil:

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy).

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>Använda PowerShell för att ändra regler för säkerhets bifogade filer

Den enda inställning som inte är tillgänglig när du ändrar en regel för en säker bilaga i PowerShell är den _aktiverade_ parametern som gör att du kan skapa en inaktive rad regel. Information om hur du aktiverar eller inaktiverar befintliga regler för säker bifogad fil finns i nästa avsnitt.

I annat fall är samma inställningar tillgängliga när du skapar en regel enligt beskrivningen i [steg 2: använda PowerShell för att skapa en regel för säker bifogad fil](#step-2-use-powershell-to-create-a-safe-attachment-rule) i den här artikeln.

Om du vill ändra en regel för en säker bifogad fil använder du följande syntax:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

Detaljerad information om syntax och parametrar finns i [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>Använda PowerShell för att aktivera eller inaktivera regler för säker bifogad fil

Aktivering eller inaktive ring av en regel för säker bifogad fil i PowerShell aktiverar eller inaktiverar hela den här principen för bifogade filer (Safe Attachment-regeln).

Använd den här syntaxen om du vill aktivera eller inaktivera en regel för en säker bilaga i PowerShell:

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

I det här exemplet inaktive ras regeln för den säkra bifogade filen marknadsförings avdelningen.

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

I det här exemplet aktiveras samma regel.

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Aktivera-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) och [disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule).

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>Använda PowerShell för att ange prioritet för regler för säker bifogad fil

Det högsta prioritetsvärde du kan ange för en regel är 0. Det lägsta värde du kan ange beror på antalet regler. Om du till exempel har fem regler kan du använda prioritetsvärden från 0 till 4. Om du ändrar prioriteten för en befintlig regel kan det ha en dominoeffekt på andra regler. Om du till exempel har fem anpassade regler (prioriteterna 0 till 4) och du ändrar prioriteten för en regel till 2 ändras den befintliga regeln med prioritet 2 till prioritet 3, och regeln med prioritet 3 ändras till prioritet 4.

Använd följande syntax för att ange prioriteten för en regel för en säker bilaga i PowerShell:

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

I det här exemplet anges prioriteten för regeln med namnet Marketing Department till 2. Alla befintliga regler som har en prioritet som är mindre än eller lika med 2 minskas med 1 (deras prioritetsnummer ökas med 1).’

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**Obs!** om du vill ange prioriteten för en ny regel när du skapar den kan du använda _prioritets_ parametern i **New-SafeAttachmentRule** cmdlet i stället.

Detaljerad information om syntax och parametrar finns i [set-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule).

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>Använda PowerShell för att ta bort principer för säker bifogad fil

När du använder PowerShell för att ta bort en princip för säker bifogad fil tas inte motsvarande regel för säker bifogad fil bort.

Använd den här syntaxen om du vill ta bort en princip för säker bifogad fil i PowerShell:

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

Det här exemplet tar bort policyn för säker bifogad fil med namnet marknadsförings avdelning.

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy).

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>Använda PowerShell för att ta bort regler för säker bilaga

När du använder PowerShell för att ta bort en regel för säker bifogad fil tas inte motsvarande princip för säker bifogad fil bort.

Använd den här syntaxen om du vill ta bort en regel för en säker bilaga i PowerShell:

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

Det här exemplet tar bort regeln marknadsförings avdelning.

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

Detaljerad information om syntax och parametrar finns i [Remove-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Gör något av följande om du vill kontrol lera att du har skapat, ändrat eller tagit bort principer för säker bifogade filer:

- I säkerhets & Compliance Center kan du gå till **Threat Management** \> **policy** - \> **säkra bifogade filer**. Verifiera listan med principer, deras **status** värden och deras **prioriterade** värden. Om du vill visa mer information väljer du den i listan och visar detaljerna i Lägg utåt.

- I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du \<Name\> med namnet på principen eller regeln, kör följande kommando och kontrollerar inställningarna:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Kontrol lera att de säkra bifogade filerna skannar meddelanden genom att titta i de tillgängliga Defender för Office 365-rapporterna. Mer information finns i [Visa rapporter för Defender för Office 365](view-reports-for-atp.md) och [använda utforskaren i säkerhets & Compliance Center](threat-explorer.md).
