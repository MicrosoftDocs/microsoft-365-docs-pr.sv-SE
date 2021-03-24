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
description: Administratörer kan läsa om hur de konfigurerar inställningarna för skräppost i Exchange Online-postlådor. Många av de här inställningarna är tillgängliga för användare i Outlook eller Outlook på webben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7e5d99198e539a46c240fadd2a7a8201236026f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073410"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Konfigurera inställningar för skräppost i Exchange Online-postlådor

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online styrs organisationens inställningar för skydd mot skräppost med Exchange Online Protection (EOP). Mer information finns i [Skydd mot skräppost i EOP.](anti-spam-protection.md)

Men det finns också särskilda inställningar för skydd mot skräppost som administratörer kan konfigurera för enskilda postlådor i Exchange Online:

- **Aktivera eller inaktivera skräppostregeln:** Skräppostregeln är en dold inkorgsregel med namnet Skräppostregel som aktiveras som standard i alla postlådor. Skräppostregeln styr följande funktioner:

  - Flytta meddelanden till mappen Skräppost baserat på principer för **skräppostskydd:** När en  princip mot skräppost är konfigurerad med åtgärden Flytta meddelandet till mappen Skräppost för en skräppostfiltreringsprincip flyttar skräppostfilterregeln meddelandet till mappen Skräppost när meddelandet har levererats till postlådan. Mer information om skräppostfiltreringsprinciper i principer mot skräppost finns i Konfigurera principer för skydd [mot skräppost i EOP.](configure-your-spam-filter-policies.md) Om ZAP (Zero-hour Auto Purge) på samma sätt bestämmer att ett levererat meddelande är skräppost eller  nätfiske flyttar skräppostfilterregeln meddelandet till mappen Skräppost för Flytta meddelandet till skräppostmappens filtrering av skräppost. Mer information om ZAP finns i [Zap (Zero-hour auto purge) i Exchange Online.](zero-hour-auto-purge.md)

  - **Skräppostinställningar** som användarna konfigurerar åt sig själva i  Outlook eller Outlook på webben: Samlingslistan över betrodda avsändare är listan Betrodda avsändare, listan Betrodda mottagare och Listan Spärrade avsändare i varje postlåda. Posterna i de här listorna avgör om skräppostregeln flyttar meddelandet till Inkorgen eller mappen Skräppost. Användare kan konfigurera samlingen safelist för sin egen postlåda i Outlook eller Outlook på webben (hette tidigare Outlook Web App). Administratörer kan konfigurera samlingslistan för alla användares postlådor.

När skräppostregeln har aktiverats för postlådan kan EOP flytta meddelanden till mappen Skräppost  baserat på åtgärden skräppostfiltreringsåtgärden Flytta meddelandet till mappen Skräppost eller listan Spärrade avsändare i postlådan och förhindra att meddelanden levereras till mappen Skräppost (baserat på listan Betrodda avsändare i postlådan).

 När skräppostregeln är inaktiverad för postlådan kan EOP inte flytta meddelanden till mappen  Skräppost baserat på åtgärden skräppostfiltreringsåtgärden Flytta meddelandet till mappen Skräppost eller samlingen lista över säkra e-postmeddelanden i postlådan.

Administratörer kan använda Exchange Online PowerShell för att inaktivera, aktivera och visa status för skräppostregeln för postlådor. Administratörer kan också använda Exchange Online PowerShell för att konfigurera poster i listan över betrodda avsändare för postlådor (listan Betrodda avsändare, Listan Betrodda mottagare och Spärrade avsändare).

> [!NOTE]
> Meddelanden från avsändare som användare har lagt till i sina egna listor över betrodda avsändare hoppar över anslutningsfiltrering som en del av EOP (SCL är -1). Om du vill hindra användare från att lägga till poster i listan Betrodda avsändare i Outlook använder du Grupprincip som nämns i avsnittet Om skräppostinställningar i  [Outlook](#about-junk-email-settings-in-outlook) längre fram i den här artikeln. Principfiltrering, innehållsfiltrering och Defender för Office 365-kontroller kommer fortfarande att tillämpas på meddelandena.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan bara använda Exchange Online PowerShell för att göra procedurerna i den här artikeln. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha tilldelats behörigheter i Exchange Online innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du  rollen E-postmottagare (som är tilldelad  rollgrupperna Organisationshantering, Mottagarhantering  och Anpassade e-postmottagare  som standard) eller rollen Användaralternativ (som är tilldelad rollgrupperna Organisationshantering och Supportavdelning som standard).   Information om hur du lägger till användare i rollgrupper i Exchange Online finns [i Ändra rollgrupper i Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups) Observera att användare med standardbehörigheter kan göra samma procedurer för sin egen postlåda, så länge de har [åtkomst till Exchange Online PowerShell.](/powershell/exchange/disable-access-to-exchange-online-powershell)

- I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- Betrodda avsändare för delade postlådor synkroniseras inte till Azure AD och EOP som design.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Använda Exchange Online PowerShell för att aktivera eller inaktivera skräppostregeln i en postlåda

> [!NOTE]
> Du kan bara använda cmdleten **Set-MailboxJunkEmailConfiguration** till att inaktivera skräppostregeln för en postlåda som har öppnats i Outlook (i cachelagrat Exchange-läge) eller Outlook på webben. Om postlådan inte har öppnats får du felmeddelandet: Om du vill dölja det här felet för massåtgärder kan du lägga till i `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` kommandot **Set-MailboxJunkEmailConfiguration.**

Om du vill aktivera eller inaktivera skräppostregeln för en postlåda använder du följande syntax:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

I det här exemplet inaktiveras skräppostregeln på Ori Epokens postlåda.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

Det här exemplet inaktiverar skräppostregeln för alla användarpostlådor i organisationen.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Detaljerad information om syntax och parametrar finns i [Set-MailboxJunkEmailConfiguration.](/powershell/module/exchange/set-mailboxjunkemailconfiguration)

> [!NOTE]
>
> - Om användaren aldrig har öppnat sin postlåda kan du få ett felmeddelande när du kör föregående kommando. För att dölja det här felet för gruppåtgärder lägger `-ErrorAction SilentlyContinue` du till i kommandot **Set-MailboxJunkEmailConfiguration.**
>
> - Även om du inaktiverar skräppostregeln kan Outlooks skräppostfilter (beroende på hur det har konfigurerats) också avgöra om ett meddelande är skräppost, och kan flytta meddelanden till Inkorgen eller mappen Skräppost utifrån dess egna skräppostprognos och samlingen med listor över säkra listor i postlådan. Mer information finns i avsnittet [Om skräppostinställningar i Outlook i](#about-junk-email-settings-in-outlook) den här artikeln.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Gör på något av följande sätt för att verifiera att du har aktiverat eller inaktiverat skräppostregeln för en postlåda:

- Ersätt med postlådans namn, alias eller e-postadress och kör följande _\<MailboxIdentity\>_ kommando för att verifiera värdet **för** egenskapen Enabled:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Använda Exchange Online PowerShell för att konfigurera samlingen safelist för en postlåda

En postlådas samling med betrodda avsändare innehåller listan Betrodda avsändare, listan Betrodda mottagare och Listan Spärrade avsändare. Som standard kan användare konfigurera samlingen safelist i sin egen postlåda i Outlook eller Outlook på webben. Administratörer kan använda motsvarande parametrar i cmdleten **Set-MailboxJunkEmailConfiguration** till att konfigurera samlingen safelist för en användares postlåda. Dessa parametrar beskrivs i följande tabell.

****

|Parameter för Set-MailboxJunkEmailConfiguration|Outlook på webben-inställning|
|---|---|
|_BlockedSendersAndDomains_|**Flytta e-post från dessa avsändare eller domäner till mappen Skräppost**|
|_ContactsTrusted_|**Lita på e-post från mina kontakter**|
|_TrustedListsOnly_|**Lita bara på e-post från adresser i listan Betrodda avsändare och domäner och Betrodda distributionslistor**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Flytta inte e-post från dessa avsändare till mappen Skräppost**|
|

<sup>\*</sup>**Kommentarer:**

- I Exchange Online identifieras inte **domänposter** i listan Betrodda avsändare eller _parametern TrustedSendersAndDomains,_ så använd bara e-postadresser. I fristående EOP med katalogsynkronisering synkroniseras inte domänposter som standard, men du kan aktivera synkronisering för domäner. Mer information finns i [KB3019657.](https://support.microsoft.com/help/3019657)

- Du kan inte direkt ändra listan Betrodda mottagare med hjälp av cmdleten **Set-MailboxJunkEmailConfiguration** _(parametern TrustedRecipientsAndDomains_ fungerar inte). Du ändrar listan Betrodda avsändare så synkroniseras ändringarna med listan Betrodda mottagare.

Använd följande syntax för att konfigurera samlingslistan över säkra i en postlåda:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Om du vill ange flera värden och skriva över befintliga poster för parametrarna _BlockedSendersAndDomains_ och _TrustedSendersAndDomains_ ska du använda följande syntax: `"<Value1>","<Value2>"...` . Om du vill lägga till eller ta bort ett eller flera värden utan att påverka andra befintliga poster använder du följande syntax: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

I det här exemplet konfigurerar vi följande inställningar för samlingen safelist i Ori Ep följda postlåda:

- Lägg till shopping@fabrikam.com i listan Spärrade avsändare.

- Ta bort värdet chris@fourthcoffee.com listan Betrodda avsändare och Betrodda mottagare.

- Konfigurerar kontakter i mappen Kontakter så att de hanteras som betrodda avsändare.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

Det här exemplet tar contoso.com domänpostlådor från listan Spärrade avsändare i alla användarpostlådor i organisationen.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Detaljerad information om syntax och parametrar finns i [Set-MailboxJunkEmailConfiguration.](/powershell/module/exchange/set-mailboxjunkemailconfiguration)

> [!NOTE]
>
> - Om användaren aldrig har öppnat sin postlåda kan du få ett felmeddelande när du kör tidigare kommandon. För att dölja det här felet för gruppåtgärder lägger `-ErrorAction SilentlyContinue` du till i kommandot **Set-MailboxJunkEmailConfiguration.**
>
> - Även om skräppostregeln är inaktiverad för postlådan kan du fortfarande konfigurera den lista över säkra e-postmeddelanden och Outlooks skräppostfilter kan flytta meddelanden till Inkorgen eller mappen Skräppost. Mer information finns i avsnittet [Om skräppostinställningar i Outlook i](#about-junk-email-settings-in-outlook) den här artikeln.
>
> - Skräppostfiltret i Outlook har ytterligare inställningar för listan över betrodda avsändare (till exempel Lägg automatiskt till personer som jag skickar **e-post till i listan Betrodda avsändare).** Mer information finns i Använda [skräppostfilter för att styra vilka meddelanden som visas.](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Verifiera att du har konfigurerat den lista över säkra samlingar för en postlåda genom att använda någon av följande metoder:

- Ersätt _\<MailboxIdentity\>_ med postlådans namn, alias eller e-postadress och kör följande kommando för att verifiera egenskapsvärdena:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Om listan med värden är för lång kan du använda följande syntax:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Om skräppostinställningar i Outlook

Om du vill aktivera, inaktivera och konfigurera de klientbaserade inställningarna för skräppostfilter som är tillgängliga i Outlook använder du Grupprincip. Mer information finns i Administrationsmallfiler (ADMX/ADML) och Verktyget för Office-anpassning för [Microsoft 365-appar för företag, Office 2019 och Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) och Så här distribuerar du skräppostinställningar, till exempel listan Betrodda [avsändare,](https://support.microsoft.com/help/2252421)med hjälp av Grupprincip.

När Outlook-skräppostfiltret är inställt  på standardvärdet  Ingen automatisk filtrering i Alternativ för skräppost i hemmet försöker Outlook inte klassificera klassificeringar som skräppost, men använder fortfarande listan betrodda avsändare (listan Betrodda avsändare, listan Betrodda mottagare och Spärrade avsändare) för att flytta meddelanden till mappen Skräppost efter \>  \>  \> leveransen. Mer information om de här inställningarna finns [i Översikt över skräppostfiltret.](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)

När Outlook-skräppostfiltret är  inställt på Låg eller Hög använder Outlook-skräppostfiltret en egen SmartScreen-filterteknik för att identifiera och flytta skräppost till mappen Skräppost. Den här klassificering av skräppost är en annan än den SCL-nivå (Spam Confidence Level) som bestäms av EOP. Faktum är att Outlook ignorerar SCL från EOP (om inte EOP har markerat meddelandet för att hoppa över skräppostfiltrering) och använder sina egna villkor för att avgöra om meddelandet är skräppost. Det är naturligtvis möjligt att skräppostmeddelandet från EOP och Outlook kan vara detsamma. Mer information om de här inställningarna [finns i Ändra skyddsnivån i skräppostfiltret.](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)

> [!NOTE]
> I november 2016 slutade Microsoft producera uppdateringar av skräppostdefinitioner för SmartScreen-filtren i Exchange och Outlook. De befintliga definitionerna av skräppost på SmartScreen finns kvar, men deras effektivitet kommer sannolikt att försämras med tiden. Mer information finns i [Inaktuellt stöd för SmartScreen i Outlook och Exchange.](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)

Därför kan skräppostfiltret i Outlook använda postlådans lista över säkra listor och sin egen klassificering av skräppost för att flytta meddelanden till mappen Skräppost, även om skräppostregeln är inaktiverad i postlådan.

Både Outlook och Outlook på webben har stöd för samlingen safelist. Samlingslistan över säkra listor sparas i Exchange Online-postlådan, så ändringar i den lista över säkra samlingar i Outlook visas i Outlook på webben och vice versa.

## <a name="limits-for-junk-email-settings"></a>Begränsningar för skräppostinställningar

Samlingssamlingen lista över betrodda avsändare (listan Betrodda avsändare, Betrodda mottagare och Spärrade avsändare) som lagras i användarens postlåda synkroniseras också med EOP. Med katalogsynkronisering synkroniseras samlingen lista över säkra filer till Azure AD.

- Samlingslistan över säkra listor i användarens postlåda har en begränsning på 510 kB, som omfattar alla listor samt ytterligare inställningar för skräppostfilter. Om en användare överskrider den här gränsen får de ett Outlook-felmeddelande som ser ut så här:

  > Det går inte att lägga till skräppostlistor på servern. Du är större än den tillåtna storleken på servern. Skräppostfiltret på servern inaktiveras tills skräppostlistorna har minskats till den storlek som tillåts av servern.

  Mer information om den här gränsen och hur du ändrar den finns i [KB2669081](https://support.microsoft.com/help/2669081).

- Den synkroniserade listan över säkra listor i EOP har följande synkroniseringsgränser:

  - Totalt 1 024 poster i listan Betrodda avsändare, listan Betrodda mottagare och externa kontakter om Betrodd e-post från **mina** kontakter har aktiverats.
  - Totalt 500 poster i listan Spärrade avsändare och Spärrade domäner.

  När gränsen för 1024-bidrag har nåtts inträffar följande:

  - Listan slutar att acceptera poster i PowerShell och Outlook på webben, men inget fel visas.

    Outlook-användare kan fortsätta att lägga till fler än 1 024 poster tills de når gränsen för Outlook på 510 kB. Outlook kan använda de här ytterligare posterna så länge ett EOP-filter inte blockerar meddelandet före leverans till postlådan (e-postflödesregler, skydd mot förfalskning osv.).

- Med katalogsynkronisering synkroniseras posterna till Azure AD i följande ordning:

  1. E-postkontakter **om Lita på e-post från mina** kontakter är aktiverat.
  2. Listan Betrodd avsändare och Betrodd mottagare kombineras, avpliceras och sorteras i alfabetisk ordning när en ändring görs för de första 1024 posterna.

  De första 1024 posterna används och relevant information stämplas i meddelandehuvudet.

  Poster över 1024 som inte synkroniserades till Azure AD bearbetas av Outlook (inte Outlook på webben) och ingen information stämplas i meddelanderubrikerna.

Om du aktiverar inställningen  Lita på e-post från mina kontakter minskar du antalet betrodda avsändare och betrodda mottagare som kan synkroniseras. Om det här är ett orosmoment rekommenderar vi att du använder Grupprincip för att inaktivera funktionen:

- Filnamn: outlk16.opax
- Principinställning: **Lita på e-post från kontakter**