---
title: Konfigurera principer Valv för bifogade filer i Microsoft Defender för Office 365
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
description: Lär dig mer om hur du Valv principer för bifogade filer för att skydda organisationen från skadliga filer i e-post.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e516a16ff28c762e154fd908312df65ea48699bc
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108229"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Konfigurera principer Valv för bifogade filer i Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](whats-new-in-defender-for-office-365.md). Om du är hemanvändare och vill ha information om skanning av bifogade filer i Outlook, se [Avancerad Outlook.com-säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Valv Bifogade filer är en funktion i [Microsoft Defender](whats-new-in-defender-for-office-365.md) för Office 365 som använder en virtuell miljö för att kontrollera bifogade filer i inkommande e-postmeddelanden efter att de har genomsökts av skydd mot skadlig programvara i [Exchange Online Protection (EOP),](anti-malware-protection.md)men före leverans till mottagarna. Mer information finns i Valv [i Microsoft Defender för Office 365](safe-attachments.md).

Det finns ingen inbyggd eller standardprincip för Valv för bifogade filer. Om du Valv att söka igenom bifogade filer i e-postmeddelanden, måste du skapa en eller Valv principer för bifogade filer enligt beskrivningen i den här artikeln.

Du kan konfigurera principer för Valv-bilagor i Microsoft 365 Defender-portalen eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online– fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Defender för Office 365-tilläggsprenumerationer).

De grundläggande elementen i en princip Valv bifogade filer är:

- **Principen för** säkra bifogade filer: Anger åtgärder för okänd identifiering av skadlig programvara, om du vill skicka meddelanden med bifogade filer från skadlig programvara till en viss e-postadress och om det inte går att skicka meddelanden om Valv genomsökning av bifogade filer inte kan slutföras.
- **Regeln för säkra bifogade** filer: Anger prioritet och mottagarfilter (vem principen gäller för).

Skillnaden mellan dessa två element är inte uppenbara när du hanterar principer Valv bilagor i Microsoft 365 Defender portalen:

- När du skapar Valv princip för bifogade filer skapar du egentligen en regel för säkra bifogade filer och den associerade principen för säkra bifogade filer samtidigt, med samma namn för båda.
- När du ändrar Valv en princip för bifogade filer ändras regeln för säker bifogad fil med inställningar för namn, prioritet, aktiverad eller inaktiverad, och mottagarfilter. Alla andra inställningar ändrar den associerade principen för säkra bifogade filer.
- När du tar bort Valv princip för bifogade filer tas regeln för säkra bifogade filer och den tillhörande principen för säkra bifogade filer bort.

I Exchange Online PowerShell eller fristående EOP PowerShell hanterar du policyn och regeln separat. Mer information finns i avsnittet Använda Exchange Online PowerShell eller [fristående EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) för att konfigurera Valv principer för bifogade filer längre fram i den här artikeln.

> [!NOTE]
> I det globala inställningsområdet i Valv för bifogade filer konfigurerar du funktioner som inte är beroende Valv principer för bifogade filer. Anvisningar finns i [Aktivera Valv för bifogade filer SharePoint, OneDrive,](turn-on-mdo-for-spo-odb-and-teams.md) Microsoft Teams och [Valv dokument i Microsoft 365 E5](safe-docs.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>. Om du vill gå direkt **Valv bifogade filer** använder du <https://security.microsoft.com/safeattachmentv2> .

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du behöver behörighet innan du kan göra procedurerna i den här artikeln:
  - Om du vill skapa, ändra och ta bort Valv-principer för  bifogade  filer måste du vara medlem i rollgrupperna Organisationshantering eller Säkerhetsadministratör i Microsoft 365 Defender-portalen  och medlem i rollgruppen Organisationshantering i Exchange Online. 
  - För skrivskyddade åtkomst Valv principer för bifogade filer måste du vara  medlem i rollgrupperna **Global Reader** eller Säkerhetsläsare i Microsoft 365 Defender portalen.

  Mer information finns i [Behörigheter i Microsoft 365 Defender och](permissions-microsoft-365-security-center.md) Behörigheter i [Exchange Online.](/exchange/permissions-exo/permissions-exo)

  **Anmärkningar**:

  - Om du lägger till användare i Azure Active Directory-rollen i Administrationscenter för Microsoft 365 får användarna de  behörigheter som krävs i Microsoft 365 Defender-portalen och behörigheter för andra funktioner Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

- Vi rekommenderar inställningar för att Valv principer för bifogade filer i Valv [Inställningar för bifogade filer.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>Använda Microsoft 365 Defender för att skapa principer för Valv och bilagor

När du skapar Valv egen princip för bifogade filer i Microsoft 365 Defender-portalen skapas en regel för säker bifogad fil och tillhörande princip för säkra bifogade filer samtidigt med samma namn för båda.

1. I Microsoft 365 Defender går du till avsnittet Principer för **&** e&-post och samarbete & Principer för hot mot regler i Valv \>  \>  \>  \> **bilagor.**

2. På sidan **Valv klickar** du på Skapa ![ ikon ](../../media/m365-cc-sc-create-icon.png) **Skapa**.

3. Principguiden öppnas. Konfigurera **följande inställningar på** sidan Namnge principen:
   - **Namn**: Ange ett unikt, beskrivande namn på principen.
   - **Beskrivning**: Ange en valfri beskrivning av principen.

   Klicka på **Nästa** när du är klar.

4. På sidan **Användare och domäner** som visas identifierar du de interna mottagare som principen gäller för (mottagarvillkor):
   - **Användare**: De angivna postlådorna, e-postanvändarna eller e-postkontakterna i organisationen.
   - **Grupper**: De angivna distributionsgrupper, e-postaktiverade säkerhetsgrupper eller Microsoft 365-grupper i organisationen.
   - **Domäner**: Alla mottagare i den angivna [godkända domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) i organisationen.

   Klicka i lämplig ruta, börja skriva in ett värde och välj det värde du vill använda i resultatet. Upprepa det här steget så många gånger som det behövs. Om du vill ta bort ett befintligt värde klickar du Ta bort ![Ta bort-ikonen](../../media/m365-cc-sc-remove-selection-icon.png) bredvid värdet.

   För användare eller grupper kan du använda de flesta identifierare (namn, visningsnamn, alias, e-postadress, kontonamn osv.), men motsvarande visningsnamn visas i resultatet. Om du vill visa alla tillgängliga värden för användare anger du en asterisk (\*) för sig själv.

   Använd ELLER-logik (till exempel _\<recipient1\>_ eller _\<recipient2\>_) för flera värden i samma villkor. Använd OCH-logik (till exempel _\<recipient1\>_ och _\<member of group 1\>_) för olika villkor.

   - **Exkludera dessa användare, grupper och domäner**: Om du vill lägga till undantag för interna mottagare som principen gäller för (Mottagarundantag), väljer du det här alternativet och konfigurerar undantagen. Inställningarna och beteendet är likadana som villkoren.

   Klicka på **Nästa** när du är klar.

5. På **Inställningar** konfigurerar du följande inställningar:

   - **Valv bifogade filer som är okänt svar från** skadlig programvara: Välj något av följande värden:
     - **Av:** Normalt rekommenderar vi inte det här värdet.
     - **Övervaka**
     - **Block:** Det här är standardvärdet och det rekommenderade värdet i standard- och strikt [förinställda säkerhetsprinciper.](preset-security-policies.md)
     - **Ersätt**
     - **Dynamisk leverans (förhandsgranskningsfunktion)**

     Dessa värden förklaras i Valv [för bifogade filer.](safe-attachments.md#safe-attachments-policy-settings)

   - **Omdirigera** meddelanden med identifierade bifogade filer: Om du väljer Aktivera omdirigering kan du ange en e-postadress i rutan Skicka meddelanden som innehåller **blockerade,** övervakade eller ersatta bifogade filer i den angivna e-postadressrutan för att skicka meddelanden som innehåller bifogade filer som innehåller skadlig programvara för analys och undersökning.

     Rekommendationen för standard- och strikt-principinställningarna är att aktivera omdirigering. Mer information finns i Valv [Inställningar för bifogade filer](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

   - Använd svaret för identifiering av **bifogade filer** i Valv om genomsökningen inte kan **slutföras (timeout** eller fel): Åtgärden som anges av Valv Okänd respons på skadlig programvara tillämpas på meddelanden även om Valv Genomsökning av bifogade filer inte kan slutföras. Om du valde det här alternativet ska du alltid välja **Aktivera omdirigering och** ange en e-postadress för att skicka meddelanden som innehåller bifogade filer som är bifogade till skadlig programvara. Annars kan meddelanden gå förlorade.

   Klicka på **Nästa** när du är klar.

6. Granska inställningarna på sidan **Granska** som visas. Du kan välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet. Eller så kan du klicka på **Föregående** eller välj den specifika sidan i guiden.

   När du är klar klickar du på **Skicka.**

7. På bekräftelsesidan som visas klickar du på **Klar**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>Använda Microsoft 365 Defender för att visa principer Valv bifogade filer

1. I Microsoft 365 Defender går du till avsnittet Principer för **&** e&-post och samarbete & Principer för hot mot regler i Valv \>  \>  \>  \> **bilagor.**

2. På **Valv bifogade** filer visas följande egenskaper i listan med principer:
   - **Namn**
   - **Status**
   - **Prioritet**

3. När du väljer en princip genom att klicka på namnet visas principinställningarna i en utfällbladstext.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>Använda Microsoft 365 Defender för att ändra principer för Valv och bilagor

1. I Microsoft 365 Defender går du till avsnittet Principer för **&** e&-post och samarbete & Principer för hot mot regler i Valv \>  \>  \>  \> **bilagor.**

2. På sidan **Valv bifogade** filer väljer du en princip i listan genom att klicka på namnet.

3. I den utfällda menyn för principinformationen kan du välja **Redigera** i varje avsnitt om du vill ändra inställningarna i avsnittet. Mer information om inställningarna finns i avsnittet Använda Microsoft 365 Defender [för](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies) att skapa Valv principer för bifogade filer längre fram i den här artikeln.  

Läs följande avsnitt om du vill aktivera eller inaktivera en princip eller ange prioritetsordning för principen.

### <a name="enable-or-disable-safe-attachments-policies"></a>Aktivera eller inaktivera principer Valv för bifogade filer

1. I Microsoft 365 Defender går du till avsnittet Principer för **&** e&-post och samarbete & Principer för hot mot regler i Valv \>  \>  \>  \> **bilagor.**

2. På sidan **Valv bifogade** filer väljer du en princip i listan genom att klicka på namnet.

3. Högst upp i den utfällda menyn principinformation ser du något av följande värden:
   - **Princip inaktiverad**: Om du vill aktivera principen klickar du på ![ikonen Aktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivera** .
   - **Princip aktiverad**: Om du vill inaktivera principen klickar du på ![ikonen Inaktivera](../../media/m365-cc-sc-turn-on-off-icon.png) **Inaktivera**.

4. I bekräftelsedialogrutan som visas klickar du på **Aktivera** eller **Inaktivera**.

5. Klicka **Stäng** i den utfällda menyn principinformation.

Tillbaka på huvudsidan kommer värdet **Status** för principen att vara **På** eller **Av**.

### <a name="set-the-priority-of-safe-attachments-policies"></a>Ange prioriteten för principer Valv för bifogade filer

Som standard har Valv för bifogade filer en prioritet som baseras på i vilken ordning de skapades (nyare principer har lägre prioritet än äldre principer). Ett lägre prioritetsnummer innebär att principen har högre prioritet (0 är det högsta), och principerna bearbetas i prioritetsordning (principer med högre prioritet bearbetas före principer med lägre prioritet). Inga två policyer kan ha samma prioritet, och policyhantering stannar efter att den första policyn har tillämpats.

För mer information om ordningsföljden och hur flera policyer utvärderas och tillämpas, se [Order och prioritet för e-postskydd](how-policies-and-protections-are-combined.md).

Valv Principer för bifogade filer visas i den ordning de bearbetas (den första principen har **prioritetsvärdet** 0).

**Obs!** I Microsoft 365 Defender kan du bara ändra prioritet för Valv för bifogade filer när du har skapat den. I PowerShell kan du åsidosätta standardprioritet när du skapar regeln om säkra bifogade filer (vilket kan påverka prioriteringen för befintliga regler).

Om du vill ändra prioriteten för en princip klickar du på **Öka prioritet** eller **Minska prioritet** i egenskaperna för principen (du kan inte direkt ändra numret för **Prioritet** i Microsoft 365 Defender-portalen). Det är bara meningsfullt att ändra prioritet för en princip om du har flera principer.

1. I Microsoft 365 Defender går du till avsnittet Principer för **&** e&-post och samarbete & Principer för hot mot regler i Valv \>  \>  \>  \> **bilagor.**

2. På sidan **Valv bifogade** filer väljer du en princip i listan genom att klicka på namnet.

3. Högst upp i den utfällliga policyinformationen  som visas  visas Öka prioritet eller Minska prioritet baserat på det aktuella prioritetsvärdet och antalet principer:
   - Principen med **prioritetsvärdet** **0** har bara alternativet **Minska** prioritet tillgängligt.
   - Principen med det lägsta **prioritetsvärdet** (till exempel **3)** har endast alternativet **Öka** prioritet tillgängligt.
   - Om du har tre eller fler principer har principerna mellan de högsta och lägsta prioritetsvärdena både alternativen Öka **prioritet** **och Minska** prioritet tillgängliga.

   Klicka ![ikonen Öka prioritet](../../media/m365-cc-sc-increase-icon.png) **Öka prioritet** eller ![Ikonen Minska prioritet](../../media/m365-cc-sc-decrease-icon.png) **Minska prioritet** om du vill ändra värdet **Prioritet**.

4. Klicka **Stäng** i den utfällda menyn principinformation när du är klar.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>Använda Microsoft 365 Defender för att ta bort principer för Valv och bilagor

1. I Microsoft 365 Defender går du till avsnittet Principer för **&** e&-post och samarbete & Principer för hot mot regler i Valv \>  \>  \>  \> **bilagor.**

2. På sidan **Valv bifogade** filer väljer du en anpassad princip i listan genom att klicka på namnet på principen.

3. Längst upp i den utfällda menyn policyinformation som visas klickar du på ![ikonen Fler åtgärder](../../media/m365-cc-sc-more-actions-icon.png) **Fler åtgärder** \> ![ikonen Ta bort princip](../../media/m365-cc-sc-delete-icon.png) **Ta bort princip**.

4. I bekräftelsedialogrutan som visas klickar du på **Ja**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera principer Valv för bifogade filer

Som tidigare beskrivits består en princip Valv bifogade filer av en princip för säker bifogad fil och en regel för säker bifogad fil.

I PowerShell syns skillnaden mellan principer för säkra bifogade filer och regler för säkra bifogade filer. Du hanterar principer för säkra bifogade filer med cmdletarna **\* -SafeAttachmentPolicy** och hanterar regler för säkra bifogade filer med cmdlets **\* -SafeAttachmentRule.**

- I PowerShell skapar du först principen för säkra bifogade filer. Sedan skapar du den regel för säkra bifogade filer som identifierar principen som regeln gäller för.
- I PowerShell ändrar du inställningarna i principen för säkra bifogade filer och regeln om säker bifogad fil separat.
- När du tar bort en princip för säkra bifogade filer från PowerShell tas motsvarande regel för säkra bifogade filer inte bort automatiskt, och vice versa.

### <a name="use-powershell-to-create-safe-attachments-policies"></a>Använda PowerShell för att skapa Valv principer för bifogade filer

Att skapa Valv en princip för bifogade filer i PowerShell är en process i två steg:

1. Skapa principen för säkra bifogade filer.
2. Skapa den regel för säkra bifogade filer som anger principen för säkra bifogade filer som regeln gäller för.

 **Anmärkningar**:

- Du kan skapa en ny regel för säkra bifogade filer och tilldela en befintlig princip för säkra bifogade filer som inte har associerats till den. En regel för säkra bifogade filer kan inte associeras med mer än en princip för säkra bifogade filer.

- Du kan konfigurera följande inställningar för nya principer för säkra bifogade filer i PowerShell som inte är tillgängliga i Microsoft 365 Defender-portalen förrän du har skapat principen:
  - Skapa den nya principen som _inaktiverad (aktiverad_ `$false` på **cmdleten New-SafeAttachmentRule).**
  - Ange prioritet för principen vid skapande (_Prioritet_ _\<Number\>_ ) på **cmdleten New-SafeAttachmentRule).**

- En ny princip för säkra bifogade filer som du skapar i PowerShell visas inte i Microsoft 365 Defender-portalen förrän du tilldelar principen till en regel för säkra bifogade filer.

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>Steg 1: Använda PowerShell för att skapa en princip för säkra bifogade filer

Använd följande syntax för att skapa en princip för säkra bifogade filer:

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

I det här exemplet skapas en princip för säkra bifogade filer med namnet Contoso Alla med följande värden:

- Blockera meddelanden som innehåller skadlig programvara genom Valv dokumentskanning (vi använder inte parametern _Action_ och standardvärdet är `Block` ).
- Omdirigering är aktiverat och meddelanden som innehåller skadlig programvara skickas till sec-ops@contoso.com för analys och undersökning.
- Om Valv bifogade filer inte är tillgängligt eller stöter på fel, leverera inte meddelandet (vi använder inte parametern _ActionOnError_ och standardvärdet är `$true` ).

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

Du kan inte byta namn på en princip för säkra bifogade filer i PowerShell **(cmdleten Set-SafeAttachmentPolicy** har ingen _namnparameter)._ När du byter namn Valv en princip för Valv bifogade filer i Microsoft 365 Defender-portalen byter du bara namn på regeln om säkra bifogade _filer._

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

Om du aktiverar eller inaktiverar en regel för säkra bifogade filer i PowerShell aktiveras eller inaktiveras hela Valv-principen för bifogade filer (regeln om säker bifogad fil och principen för bifogade filer).

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

Kontrollera att du har skapat, ändrat eller tagit bort Valv principer för bifogade filer genom att göra något av följande:

- I Microsoft 365 Defender går du till avsnittet Principer för **&** e&-post och samarbete & Principer för hot mot regler i Valv \>  \>  \>  \> **bilagor.** Kontrollera listan med principer, deras **statusvärden** och deras **prioritetsvärden.** Om du vill visa mer information väljer du principen i listan genom att klicka på namnet och visa informationen i den utfällovyn.

- I Exchange Online PowerShell eller Exchange Online Protection PowerShell ersätter du med namnet på principen eller regeln, kör följande kommando och \<Name\> kontrollerar inställningarna:

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

Kontrollera att Valv bifogade filer söker igenom meddelanden genom att titta i den tillgängliga Defender Office 365 av rapporter. Mer information finns i [Visa rapporter för Defender för Office 365](view-reports-for-mdo.md) och Använda [Utforskaren i Microsoft 365 Defender portal.](threat-explorer.md)
