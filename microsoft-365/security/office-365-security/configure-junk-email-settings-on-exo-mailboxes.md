---
title: Konfigurera inställningar för skräppost i Exchange Online-postlådor
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur de konfigurerar skräppostinställningarna i Exchange Online-postlådor. Många av de här inställningarna är tillgängliga för användare i Outlook eller Outlook på webben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2aa75376a431ded5abf44ad17ddad4f0ac731fa8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165697"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Konfigurera inställningar för skräppost i Exchange Online-postlådor

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

I Microsoft 365-organisationer med postlådor i Exchange Online styrs inställningarna för skydd mot skräppost i organisationen av Exchange Online Protection (EOP). Mer information finns i [Skydd mot skräppost i EOP.](anti-spam-protection.md)

Men det finns också särskilda inställningar för skydd mot skräppost som administratörer kan konfigurera för enskilda postlådor i Exchange Online:

- **Aktivera eller inaktivera skräppostregeln:** Skräppostregeln är en dold inkorgsregel med namnet Skräppostregel som är aktiverad som standard i alla postlådor. Skräppostregeln styr följande funktioner:

  - Flytta meddelanden till mappen Skräppost baserat på principer mot **skräppost:** När en princip  mot skräppost är konfigurerad med åtgärden Flytta meddelandet till mappen Skräppost för en skräppostfiltreringsregel, flyttar skräppostfilterregeln meddelandet till mappen Skräppost när meddelandet har levererats till postlådan. Mer information om skräppostfiltreringsprinciper i principer mot skräppost finns i Konfigurera principer för skydd [mot skräppost i EOP.](configure-your-spam-filter-policies.md) Om ZAP (Zero-Hour Auto Purge) på samma sätt bestämmer att ett levererat meddelande är skräppost eller  nätfiske flyttar skräppostfiltret meddelandet till mappen Skräppost för att flytta meddelandet till skräppostmappens filtreringsåtgärder. Mer information om ZAP finns i [Zap (Zero-hour auto purge) i Exchange Online.](zero-hour-auto-purge.md)

  - **Skräppostinställningar** som användarna konfigurerar åt sig själva i  Outlook eller Outlook på webben: Samlingen Betrodda avsändare är listan Betrodda avsändare, Listan Betrodda mottagare och Listan Spärrade avsändare i varje postlåda. Posterna i listorna avgör om skräppostregeln flyttar meddelandet till Inkorgen eller mappen Skräppost. Användare kan konfigurera samlingen med listor över säkra listor för sin egen postlåda i Outlook eller Outlook på webben (hette tidigare Outlook Web App). Administratörer kan konfigurera samlingslistan för alla användares postlådor.

När skräppostregeln har aktiverats för postlådan kan EOP flytta meddelanden till mappen Skräppost  baserat på skräppostfiltreringsåtgärden Flytta meddelandet till mappen Skräppost eller listan Spärrade avsändare i postlådan och förhindra att meddelanden levereras till mappen Skräppost (baserat på listan Betrodda avsändare i postlådan).

 När skräppostregeln är inaktiverad för postlådan kan EOP inte flytta meddelanden till mappen  Skräppost baserat på skräppostfiltreringsåtgärden Flytta meddelandet till mappen Skräppost eller listan över säkra i postlådan.

Administratörer kan använda Exchange Online PowerShell för att inaktivera, aktivera och visa status för skräppostregeln för postlådor. Administratörer kan också använda Exchange Online PowerShell för att konfigurera poster i listan över betrodda postlådor (listan Betrodda avsändare, Listan Betrodda mottagare och Spärrade avsändare).

> [!NOTE]
> Meddelanden från avsändare som användare har lagt till i sina egna listor över betrodda avsändare hoppar över anslutningsfiltrering som en del av EOP (SCL är -1). Om du vill hindra användare från att lägga till poster i listan Betrodda avsändare i Outlook kan du använda grupprincip som nämns i avsnittet Om skräppostinställningar i  [Outlook](#about-junk-email-settings-in-outlook) senare i den här artikeln. Principfiltrering, innehållsfiltrering och Defender för Office 365-kontroller tillämpas fortfarande på meddelandena.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan bara använda Exchange Online PowerShell för att göra det som beskrivs i den här artikeln. Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i Exchange Online innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du  rollen E-postmottagare (som tilldelas rollgrupperna  Organisationshantering, Mottagarhantering och  Anpassade e-postmottagare som  standard) eller rollen Användaralternativ (som tilldelas rollgrupperna Organisationshantering och Supportavdelning som standard).    Information om hur du lägger till användare i rollgrupper i Exchange Online [finns i Ändra rollgrupper i Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) Observera att användare med standardbehörigheter kan göra samma procedurer i sin egen postlåda, så länge de har [åtkomst till Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)

- I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- Betrodda avsändare för delade postlådor synkroniseras inte till Azure AD och EOP som design.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Använda Exchange Online PowerShell för att aktivera eller inaktivera skräppostregeln i en postlåda

> [!NOTE]
> Du kan bara använda cmdleten **Set-MailboxJunkEmailConfiguration** för att inaktivera skräppostregeln för en postlåda som har öppnats i Outlook (i cachelagrat Exchange-läge) eller Outlook på webben. Om postlådan inte har öppnats visas följande felmeddelande: Om du vill dölja det här felet för massåtgärder kan du lägga till kommandot `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **Set-MailboxJunkEmailConfiguration.**

Om du vill aktivera eller inaktivera skräppostregeln för en postlåda använder du följande syntax:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

I det här exemplet inaktiveras skräppostregeln för Ori Epsteins postlåda.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

I det här exemplet inaktiveras skräppostregeln för alla användarpostlådor i organisationen.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Detaljerad information om syntax och parametrar finns i [Set-MailboxJunkEmailConfiguration.](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)

> [!NOTE]
>
> - Om användaren aldrig har öppnat sin postlåda kan du få ett felmeddelande när du kör det föregående kommandot. Om du vill dölja det här felet för gruppåtgärder lägger du till `-ErrorAction SilentlyContinue` **kommandot Set-MailboxJunkEmailConfiguration.**
>
> - Även om du inaktiverar skräppostregeln kan Outlook-skräppostfiltret (beroende på hur det är konfigurerat) också avgöra om ett meddelande är skräppost, och kan flytta meddelanden till Inkorgen eller mappen Skräppost baserat på dess egen skräppostprognos och samlingen med listor över säkra listor för postlådan. Mer information finns i avsnittet [Om skräppostinställningar i Outlook i](#about-junk-email-settings-in-outlook) den här artikeln.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Använd någon av följande metoder för att kontrollera att du har aktiverat eller inaktiverat skräppostregeln för en postlåda:

- Ersätt _\<MailboxIdentity\>_ med postlådans namn, alias eller e-postadress och kör följande kommando för att verifiera värdet **för den aktiverade** egenskapen:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Använda Exchange Online PowerShell för att konfigurera samlingen listor över säkra listor för en postlåda

I samlingen listor över betrodda avsändare för en postlåda finns listan Betrodda avsändare, listan Betrodda mottagare och listan Spärrade avsändare. Som standard kan användare konfigurera samlingen listor över säkra listor i sina egna postlådor i Outlook eller Outlook på webben. Administratörer kan använda motsvarande parametrar i cmdleten **Set-MailboxJunkEmailConfiguration** till att konfigurera samlingen listor över säkra listor för en användares postlåda. Dessa parametrar beskrivs i följande tabell.

****

|Parameter för Set-MailboxJunkEmailConfiguration|Outlook på webben-inställning|
|---|---|
|_BlockedSendersAndDomains_|**Flytta e-post från dessa avsändare eller domäner till mappen Skräppost**|
|_ContactsTrusted_|**Lita på e-post från mina kontakter**|
|_TrustedListsOnly_|**Endast e-postmeddelanden från adresser i listan Betrodda avsändare och domäner och Betrodda distributionslistor är betrodda**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Flytta inte e-post från dessa avsändare till mappen Skräppost**|
|

<sup>\*</sup>**Kommentarer:**

- I Exchange Online identifieras **inte domänposter** i listan Betrodda avsändare eller _parametern TrustedSendersAndDomains,_ så använd bara e-postadresser. I fristående EOP med katalogsynkronisering synkroniseras inte domänposter som standard, men du kan aktivera synkronisering för domäner. Mer information finns i [KB3019657.](https://support.microsoft.com/help/3019657)

- Du kan inte direkt ändra listan Betrodda mottagare med hjälp av cmdleten **Set-MailboxJunkEmailConfiguration** _(parametern TrustedRecipientsAndDomains_ fungerar inte). När du ändrar listan Betrodda avsändare synkroniseras ändringarna med listan Betrodda mottagare.

Använd följande syntax om du vill konfigurera samlingen listor över säkra i en postlåda:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Om du vill ange flera värden och skriva över befintliga poster för parametrarna _BlockedSendersAndDomains_ och _TrustedSendersAndDomains_ använder du följande `"<Value1>","<Value2>"...` syntax: Använd följande syntax om du vill lägga till eller ta bort ett eller flera värden utan att påverka andra befintliga poster: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

Det här exemplet konfigurerar följande inställningar för samlingen lista över säkra listor i Ori Epsteins postlåda:

- Lägg till värdet shopping@fabrikam.com listan Spärrade avsändare.

- Ta bort chris@fourthcoffee.com listan Betrodda avsändare och Betrodda mottagare.

- Konfigurerar kontakter i mappen Kontakter som ska hanteras som betrodda avsändare.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

Det här exemplet tar bort contoso.com domänlistan från listan Spärrade avsändare i alla användarpostlådor i organisationen.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Detaljerad information om syntax och parametrar finns i [Set-MailboxJunkEmailConfiguration.](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)

> [!NOTE]
>
> - Om användaren aldrig har öppnat sin postlåda kan du få ett felmeddelande när du kör tidigare kommandon. Om du vill dölja det här felet för gruppåtgärder lägger du till `-ErrorAction SilentlyContinue` **kommandot Set-MailboxJunkEmailConfiguration.**
>
> - Även om skräppostregeln är inaktiverad för postlådan kan du ändå konfigurera samlingen lista över säkra e-postmeddelanden och Outlooks skräppostfilter kan flytta meddelanden till Inkorgen eller mappen Skräppost. Mer information finns i avsnittet [Om skräppostinställningar i Outlook i](#about-junk-email-settings-in-outlook) den här artikeln.
>
> - Outlooks skräppostfilter har ytterligare inställningar för listor över betrodda avsändare (till exempel att automatiskt lägga till personer som jag skickar e-post **till i listan Betrodda avsändare).** Mer information finns i Använda [skräppostfilter för att styra vilka meddelanden som visas.](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Gör så här för att verifiera att du har konfigurerat samlingen listor över säkra listor för en postlåda:

- Ersätt _\<MailboxIdentity\>_ med postlådans namn, alias eller e-postadress och kör följande kommando för att verifiera egenskapsvärdena:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Om listan med värden är för lång använder du följande syntax:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Om skräppostinställningar i Outlook

Om du vill aktivera, inaktivera och konfigurera inställningarna för skräppostfilter på klientsidan som är tillgängliga i Outlook använder du grupprincip. Mer information finns i administrationsmallfiler (ADMX/ADML) och [anpassningsverktyget](https://support.microsoft.com/help/2252421)för Office för [Microsoft 365-program för företag, Office 2019 och Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) och hur du distribuerar skräppostinställningar, till exempel listan Betrodda avsändare, med hjälp av grupprincip.

När   \>  \> **Outlook-skräppostfiltret** är inställt på standardvärdet Ingen automatisk filtrering i alternativen för skräppost i hemmet , försöker inte Outlook klassificera sina meddelanden som \> skräppost, men använder fortfarande samlingen betrodda avsändare (listan Betrodda avsändare, listan Betrodda mottagare och Spärrade avsändare) för att flytta meddelanden till mappen Skräppost efter leverans. Mer information om de här inställningarna finns i [Översikt över skräppostfiltret.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

När Outlook-skräppostfiltret är  inställt på Låg eller Hög använder Outlooks skräppostfilter sin egen SmartScreen-filterteknik för att identifiera och flytta skräppost till mappen Skräppost. Den här klassificeringen för skräppost skiljer sig från den SCL (Spam Confidence Level) som avgörs av EOP. Outlook ignorerar SCL från EOP (om inte EOP har markerat meddelandet för att hoppa över skräppostfiltrering) och använder sina egna kriterier för att avgöra om meddelandet är skräppost. Naturligtvis är det möjligt att skräpposten från EOP och Outlook kan vara densamma. Mer information om de här inställningarna [finns i Ändra skyddsnivån i skräppostfiltret.](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)

> [!NOTE]
> I november 2016 slutade Microsoft producera uppdateringar av skräppostdefinitioner för SmartScreen-filtren i Exchange och Outlook. De befintliga definitionerna av skräppost på SmartScreen finns kvar, men deras effektivitet kommer sannolikt att försämras med tiden. Mer information finns i [inaktuellt stöd för SmartScreen i Outlook och Exchange.](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)

Så skräppostfiltret i Outlook kan använda postlådans lista över säkra listor och sin egen klassificering av skräppost för att flytta meddelanden till mappen Skräppost, även om skräppostregeln är inaktiverad i postlådan.

Både Outlook och Outlook på webben har stöd för samlingen listor över säkra. Samlingen lista över säkra filer sparas i Exchange Online-postlådan, så ändringar i samlingen lista över säkra listor i Outlook visas i Outlook på webben, och vice versa.

## <a name="limits-for-junk-email-settings"></a>Begränsningar för skräppostinställningar

Samlingslistan över betrodda avsändare (listan Betrodda avsändare, Listan Betrodda mottagare och Spärrade avsändare) som lagras i användarens postlåda synkroniseras också med EOP. Med katalogsynkronisering synkroniseras samlingen listor över säkra till Azure AD.

- Samlingslistan över säkra listor i användarens postlåda har en gräns på 510 kB, som omfattar alla listor, plus ytterligare inställningar för skräppostfilter. Om en användare överskrider den här gränsen får de ett Outlook-fel som ser ut så här:

  > Kan inte/Kan inte lägga till i serverns skräppostlistor. Du är större än den storlek som tillåts på servern. Skräppostfiltret på servern inaktiveras tills dina skräppostlistor har förminskats till den storlek som tillåts av servern.

  Mer information om den här gränsen och hur du ändrar den finns i [KB2669081.](https://support.microsoft.com/help/2669081)

- Följande synkroniseringsgränser finns för den synkroniserade listan över säkra listor i EOP:

  - 1 024 poster totalt i listan Betrodda avsändare, listan Betrodda mottagare och externa kontakter om Betrodd e-post från **mina** kontakter har aktiverats.
  - Totalt 500 poster i listan Spärrade avsändare och Spärrade domäner.

  När gränsen för 1024 har nåtts inträffar följande:

  - Listan slutar att acceptera poster i PowerShell och Outlook på webben, men inget fel visas.

    Outlook-användare kan fortsätta att lägga till fler än 1 024 poster tills de når Gränsen för Outlook på 510 KB. Outlook kan använda de här ytterligare posterna så länge ett EOP-filter inte blockerar meddelandet innan det levereras till postlådan (e-postflödesregler, förfalskningskydd osv.).

- Med katalogsynkronisering synkroniseras posterna till Azure AD i följande ordning:

  1. E-postkontakter **om Betrodd e-post från mina kontakter** är aktiverat.
  2. Listan Betrodda avsändare och Betrodda mottagare kombineras, avpliceras och sorteras i alfabetisk ordning när en ändring görs för de första 1024 posterna.

  De första 1024 posterna används och relevant information märks i meddelanderubrikerna.

  Poster över 1 024 som inte synkroniserades till Azure AD bearbetas av Outlook (inte Outlook på webben) och ingen information stämplas i meddelanderubrikerna.

Som du ser minskar  antalet betrodda avsändare och betrodda mottagare som kan synkroniseras genom att inställningen Lita på e-post från kontakter. Om det här är viktigt rekommenderar vi att du använder grupprincip att inaktivera den här funktionen:

- Filnamn: outlk16.opax
- Principinställning: **Lita på e-post från kontakter**
