---
title: Konfigurera inställningar för skräppost i Exchange Online-postlådor
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du konfigurerar inställningarna för skräppost i Exchange Online-postlådor. Många av dessa inställningar är tillgängliga för användare i Outlook eller Outlook på webben.
ms.openlocfilehash: a0b2bce985c642a2069d51cbd3103b6fd044ff17
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588458"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Konfigurera inställningar för skräppost i Exchange Online-postlådor

I Microsoft 365-organisationer med postlådor i Exchange Online styrs organisationens anti-spam-inställningar av Exchange Online Protection (EOP). Mer information finns [i Skydd mot skräppost i EOP](anti-spam-protection.md).

Men det finns också specifika inställningar mot skräppost som administratörer kan konfigurera på enskilda postlådor i Exchange Online:

- **Aktivera eller inaktivera skräppostregeln**: Skräppostregeln är en dold inkorgsregel med namnet Skräppostregel som är aktiverad som standard i alla postlådor. Regeln om skräppost styr följande funktioner:

  - **Flytta meddelanden till mappen Skräppost baserat på anti-spam-policyer:** När en anti-spam-princip har konfigurerats med åtgärden **Flytta meddelande till skräppostmappen** för en skräppostfiltreringsdom flyttas skräppostfiltrets regel meddelandet till skräppostmappen när meddelandet har levererats till postlådan. Mer information om skräppostfiltreringsutslag i policyer mot skräppost finns [i Konfigurera policyer mot skräppost i EOP](configure-your-spam-filter-policies.md). På samma sätt, om nolltimmars automatisk rensning (ZAP) bestämmer ett levererat meddelande är spam eller phish, flyttar skräppostfiltret regeln meddelandet till mappen Skräppost för **Flytta meddelande till skräppostmappen** skräppostfiltrering dom åtgärder. Mer information om ZAP finns i [Zero-hour auto purge (ZAP) i Exchange Online](zero-hour-auto-purge.md).

  - **Skräppostinställningar som användarna konfigurerar själva i Outlook eller Outlook på webben:** Samlingen _safelist_ är listan Betrodda avsändare, listan Betrodda mottagare och listan Blockera avsändare i varje postlåda. Posterna i dessa listor avgör om skräppostregeln flyttar meddelandet till inkorgen eller mappen Skräppost. Användare kan konfigurera samlingen för safelist för sin egen postlåda i Outlook eller Outlook på webben (tidigare kallat Outlook Web App). Administratörer kan konfigurera samlingen för safelist på alla användares postlåda.

När skräppostregeln är aktiverad i postlådan kan EOP flytta meddelanden till mappen Skräppost baserat på skräppostfiltreringsåtgärden **Flytta meddelande till mappen Skräppost** eller listan Blockerade avsändare i postlådan och förhindra att meddelanden levereras till mappen Skräppost (baserat på listan Betrodda avsändare i postlådan).

 När skräppostregeln är inaktiverad i postlådan kan EOP inte flytta meddelanden till mappen Skräppost baserat på skräppostfiltreringsåtgärden Flytta meddelande till mappen Skräppost eller **insamlingen** för safelist i postlådan.

Administratörer kan använda Exchange Online PowerShell för att inaktivera, aktivera och visa status för skräppostregeln på postlådor. Administratörer kan också använda Exchange Online PowerShell för att konfigurera poster i samlingen safelist på postlådor (listan Betrodda avsändare, listan Betrodda mottagare och listan Blockera avsändare).

> [!NOTE]
> Meddelanden från avsändare som användare har lagt till i sina egna listor över betrodda avsändare hoppar över anslutningsfiltrering som en del av EOP (SCL är -1). Om du vill hindra användare från att lägga till poster i listan Betrodda avsändare i Outlook använder du Grupprincip som nämns i avsnittet [Om skräppost i Outlook](#about-junk-email-settings-in-outlook) senare i det här avsnittet. Atp-kontroller (Content filtering, Advanced Threat Protection) tillämpas fortfarande på meddelandena.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan bara använda Exchange Online PowerShell för att utföra dessa procedurer. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Du måste tilldelas behörigheter innan du kan göra dessa procedurer. Du behöver rollen **E-postmottagare** (som tilldelas rollgrupperna **Organisationshantering,** **Mottagarhantering**och **Anpassade e-postmottagare** som standard) eller rollen **Användaralternativ** (som tilldelas rollgrupperna **Organisationshantering** och **HelpDesk** som standard). Information om hur du lägger till användare i rollgrupper i Exchange Online finns [i Ändra rollgrupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups). Observera att en användare med standardbehörigheter kan göra samma procedurer på sin egen postlåda, så länge de har [åtkomst till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).

- I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- Betrodda avsändare för delade postlådor synkroniseras inte med Azure AD och EOP avsiktligt.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Använda Exchange Online PowerShell för att aktivera eller inaktivera skräppostregeln i en postlåda

> [!NOTE]
> Du kan bara använda cmdleten **Set-MailboxJunkEmailConfiguration** för att inaktivera skräppostregeln på en postlåda som har öppnats i Outlook (i cachelagrat Exchange-läge) eller Outlook på webben. Om postlådan inte har öppnats visas felet: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` Om du vill ignorera det här felet för massåtgärder kan du lägga till i kommandot `-ErrorAction SlientlyContinue` **Set-MailboxJunkEmailConfiguration.**

Om du vill aktivera eller inaktivera skräppostregeln på en postlåda använder du följande syntax:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

I det här exemplet inaktiveras skräppostregeln på Ori Epsteins postlåda.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

I det här exemplet inaktiveras skräppostregeln för alla användarpostlådor i organisationen.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Detaljerad syntax- och parameterinformation finns i [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
> 
> - Om användaren aldrig har öppnat sin postlåda kan du få ett felmeddelande när du kör föregående kommando. Om du vill ignorera det här felet för massåtgärder lägger `-ErrorAction SlientlyContinue` du till i kommandot **Set-MailboxJunkEmailConfiguration.**
> 
> - Även om du inaktiverar skräppostregeln kan Outlook Junk Email Filter (beroende på hur det är konfigurerat) också avgöra om ett meddelande är skräppost och kan flytta meddelanden till mappen Inkorgen eller Skräppost baserat på dess egna skräppostutlåtande och safelist-samlingen på postlådan. Mer information finns [i avsnittet Om skräppostinställningar i Outlook](#about-junk-email-settings-in-outlook) i det här avsnittet.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du vill kontrollera att du har aktiverat eller inaktiverat skräppostregeln på en postlåda använder du någon av följande procedurer:

- Ersätt _\<MailboxIdentity\>_ med postlådans namn, alias eller e-postadress och kör följande kommando för att verifiera **egenskapsvärdet Aktiverad:**

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Använda Exchange Online PowerShell för att konfigurera insamlingen för safelist på en postlåda

Samlingen för en värdelista i en postlåda innehåller listan Betrodda avsändare, listan Betrodda mottagare och listan Blockerade avsändare. Som standard kan användarna konfigurera samlingen för säker lista på sin egen postlåda i Outlook eller Outlook på webben. Administratörer kan använda motsvarande parametrar i cmdleten **Set-MailboxJunkEmailConfiguration** för att konfigurera samlingen safelist på en användares postlåda. Dessa parametrar beskrivs i följande tabell.

|||
|---|---|
|**Parameter på Set-MailboxJunkEmailConfiguration**|**Outlook på webbinställningen**|
|_BlockeradeSändareOchDomäner_|**Flytta e-post från dessa avsändare eller domäner till mappen Skräppost**|
|_Betrodda kontakter_|**Lita på e-post från mina kontakter**|
|_TrustedListsOnly_|**Lita bara på e-post från adresser i listan Betrodda avsändare och domäner och säkra e-postlistor**|
|_TrustedSendersOchDomäner_<sup>\*</sup>|**Flytta inte e-post från dessa avsändare till mappen Skräppost**|
|

<sup>\*</sup>**Anmärkningar:**

- I Exchange Online identifieras inte **domänposter** i listan Betrodda avsändare eller _TrustedSendersAndDomains,_ så använd bara e-postadresser. I fristående EOP med katalogsynkronisering synkroniseras domänposter inte som standard, men du kan aktivera synkronisering för domäner. Mer information finns i [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange).

- Du kan inte ändra listan Betrodda mottagare direkt med hjälp av cmdleten **Set-MailboxJunkEmailConfiguration** (parametern _TrustedRecipientsAndDomains_ fungerar inte). Du ändrar listan Betrodda avsändare och ändringarna synkroniseras med listan Betrodda mottagare.

Om du vill konfigurera safelist-samlingen på en postlåda använder du följande syntax:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Om du vill ange flera värden och skriva över alla befintliga poster för parametrarna _BlockedSendersAndDomains_ och _TrustedSendersAndDomains_ använder du följande syntax: `"<Value1>","<Value2>"...` . Om du vill lägga till eller ta bort ett eller flera värden utan att påverka andra befintliga poster använder du följande syntax:`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

I det här exemplet konfigureras följande inställningar för samlingen för safelist på Ori Epsteins postlåda:

- Lägg till värdet shopping@fabrikam.com i listan Blockerade avsändare.

- Ta bort värdet chris@fourthcoffee.com från listan Betrodda avsändare och listan Betrodda mottagare.

- Konfigurerar kontakter i mappen Kontakter så att de behandlas som betrodda avsändare.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

I det här exemplet tas domänen contoso.com bort från listan Blockerade avsändare i alla användarpostlådor i organisationen.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Detaljerad syntax- och parameterinformation finns i [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
> 
> - Om användaren aldrig har öppnat sin postlåda kan du få ett felmeddelande när du kör de tidigare kommandona. Om du vill ignorera det här felet för massåtgärder lägger `-ErrorAction SlientlyContinue` du till i kommandot **Set-MailboxJunkEmailConfiguration.**
> 
> - Även om skräppostregeln är inaktiverad i postlådan kan du fortfarande konfigurera samlingen för safelist och skräppostfiltret i Outlook kan flytta meddelanden till inkorgen eller mappen Skräppost. Mer information finns [i avsnittet Om skräppostinställningar i Outlook](#about-junk-email-settings-in-outlook) i det här avsnittet.
> 
> - Outlook Skräppostfilter har ytterligare inställningar för safelist-samling (till exempel **lägger jag automatiskt till personer som jag e-postar i listan Betrodda avsändare).** Mer information finns i [Använda skräppostfilter för att styra vilka meddelanden som visas](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)i .

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Om du vill kontrollera att du har konfigurerat insamlingen för säker lista på en postlåda använder du något av följande:

- Ersätt _\<MailboxIdentity\>_ med postlådans namn, alias eller e-postadress och kör följande kommando för att verifiera egenskapsvärdena:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Om listan med värden är för lång använder du den här syntaxen:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Om inställningar för skräppost i Outlook

Om du vill aktivera, inaktivera och konfigurera inställningarna för skräppostfilter på klientsidan som är tillgängliga i Outlook använder du Grupprincip. Mer information finns i [Administrativa mallfiler (ADMX/ADML) och Anpassningsverktyg för Office för Microsoft 365-appar för företag, Office 2019 och Office 2016](https://www.microsoft.com/download/details.aspx?id=49030) och [Hur du distribuerar skräppostinställningar, till exempel listan Betrodda avsändare, med hjälp av Grupprincip](https://support.microsoft.com/help/2252421/how-to-deploy-junk-email-settings-such-as-the-safe-senders-list-by-usi).

När skräppostfiltret i Outlook är inställt på standardvärdet **Ingen automatisk filtrering** i alternativ för skräppost i **hemmet** försöker Outlook inte klassificera massage \> **Junk** \> **Junk E-Mail Options** \> **Options**som skräppost, men använder fortfarande samlingen för betrodda användare (listan Betrodda avsändare, listan Betrodda mottagare och listan Blockerade avsändare) för att flytta meddelanden till mappen Skräppost efter leverans. Mer information om dessa inställningar finns [i Översikt över skräppostfiltret](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

När skräppostfiltret i Outlook är inställt på **Låg** eller **Hög**använder skräppostfiltret i Outlook sin egen SmartScreen-filterteknik för att identifiera och flytta skräppost till mappen Skräppost. Denna spam klassificering är skild från spam förtroende nivå (SCL) som bestäms av EOP. I själva verket ignorerar Outlook SCL från EOP (om inte EOP markerade meddelandet för att hoppa över skräppostfiltrering) och använder sina egna kriterier för att avgöra om meddelandet är skräppost. Naturligtvis är det möjligt att spam dom från EOP och Outlook kan vara densamma. Mer information om dessa inställningar finns [i Ändra skyddsnivå i skräppostfiltret](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> I november 2016 slutade Microsoft att producera uppdateringar av skräppostdefinition för SmartScreen-filtren i Exchange och Outlook. De befintliga SmartScreen-spamdefinitionerna lämnades på plats, men deras effektivitet kommer sannolikt att försämras med tiden. Mer information finns i [Inaktuella stöd för SmartScreen i Outlook och Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Så, Outlook Junk Email Filter kan använda brevlådans safelist samling och sin egen spam klassificering för att flytta meddelanden till skräppost mappen, även om skräppost regeln är inaktiverad i brevlådan.

Outlook och Outlook på webben stöder båda insamlingen för safelist. Samlingen för safelist sparas i Exchange Online-postlådan, så ändringar i samlingen för safelist i Outlook visas i Outlook på webben och tvärtom.

## <a name="limits-for-junk-email-settings"></a>Gränser för inställningar för skräppost

Den safelist-samling (listan Betrodda avsändare, listan Betrodda mottagare och listan Blockerade avsändare) som lagras i användarens postlåda synkroniseras också med EOP. Med katalogsynkronisering synkroniseras safelist-samlingen med Azure AD.

- Den safelist-samlingen i användarens postlåda har en gräns på 510 KB, som innehåller alla listor, plus ytterligare inställningar för skräppostfilter. Om en användare överskrider den här gränsen visas ett Outlook-fel som ser ut så här:

  > Det går inte/lägger inte till i serverns skräppostlistor. Du är över den storlek som tillåts på servern. Skräppostfiltret på servern inaktiveras tills skräppostlistorna har reducerats till den storlek som servern tillåter.

  Mer information om den här gränsen och hur du ändrar den finns i [KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit).

- Den synkroniserade safelist-samlingen i EOP har följande synkroniseringsgränser:

  - Totalt antal poster i listan Betrodda avsändare, listan Betrodda mottagare och externa kontakter om **Förtroende-e-post från mina kontakter** är aktiverat.
  - Totalt 500 poster i listan Blockerade avsändare och blockerade domäner.

  När 1024-ingångsgränsen har uppnåtts händer följande:

  - Listan slutar acceptera poster i PowerShell och Outlook på webben, men inget fel visas.

    Outlook-användare kan fortsätta att lägga till fler än 1024 poster tills de når Outlook-gränsen på 510 kB. Outlook kan använda dessa ytterligare poster, så länge ett EOP-filter inte blockerar meddelandet före leverans till postlådan (regler för e-postflöde, anti-förfalskning, etc.).

- Med katalogsynkronisering synkroniseras posterna till Azure AD i följande ordning:

  1. E-postkontakter om **Förtroende-e-post från mina kontakter** är aktiverat.
  2. Listan Säker avsändare och listan Säker mottagare kombineras, avd dupliceras och sorteras i alfabetisk ordning när en ändring görs för de första 1024-posterna.

  De första 1024-posterna används och relevant information stämplas i meddelanderubrikerna.

  Poster över 1024 som inte synkroniserades med Azure AD bearbetas av Outlook (inte Outlook på webben) och ingen information stämplas i meddelanderubrikerna.

Som du kan se minskar om du aktiverar **inställningen Förtroende-e-post från mina kontakter** antalet betrodda avsändare och säkra mottagare som kan synkroniseras. Om detta är ett problem rekommenderar vi att du använder Grupprincip för att inaktivera den här funktionen:

- Filnamn: outlk16.opax
- Principinställning: **Lita på e-post från kontakter**
