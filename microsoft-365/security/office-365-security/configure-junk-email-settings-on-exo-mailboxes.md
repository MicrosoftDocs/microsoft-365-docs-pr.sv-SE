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
description: Administratörer kan läsa mer om hur du konfigurerar inställningar för skräp post i Exchange Online-postlådor. Många av de här inställningarna är tillgängliga för användare i Outlook eller Outlook på webben.
ms.openlocfilehash: 5da4aad41f5c5f00f65fa1ceb4fc4c0fad773779
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653047"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Konfigurera inställningar för skräppost i Exchange Online-postlådor

I Microsoft 365-organisationer med post lådor i Exchange Online styrs inställningar för skydd mot skräp post av Exchange Online Protection (EOP). Mer information finns i [skydd mot skräp post i EOP](anti-spam-protection.md).

Men det finns även särskilda inställningar för att förhindra skräp post som administratörer kan konfigurera på enskilda post lådor i Exchange Online:

- **Aktivera eller inaktivera skräp post regeln**: skräp post regeln är en dold inkorg med namnet skräp post regel som är aktiverat som standard i alla post lådor. Regeln för skräp post styr följande funktioner:

  - **Flytta meddelanden till mappen skräp post baserat på principer för**skräp post: när en princip för skräp post har kon figurer ATS med åtgärden **Flytta meddelande till mappen skräp post** för filtrering av skräp post Verdict flyttas meddelandet till mappen skräp post när meddelandet levereras till post lådan. Mer information om filtrering av skräp post verdicts i principer för skräp post hantering finns i [Konfigurera principer för skräp post i EOP](configure-your-spam-filter-policies.md). På samma sätt gäller att automatisk rensning av en tom timme (ZAP) bestämmer att ett levererat meddelande är skräp post eller Phish, att skräp post filter regeln flyttar meddelandet till mappen skräp post för **att flytta meddelande till mappen skräp post** filtrering Verdict åtgärder. Om du vill ha mer information om ZAP, se [Rensa tom timme (Zap) i Exchange Online](zero-hour-auto-purge.md).

  - **Inställningar för skräp post som användare konfigurerar för sig själva i Outlook eller Outlook på webben**: _säker lista-samlingen_ är listan Betrodda avsändare, listan Betrodda mottagare och listan Spärrade avsändare för varje post låda. Posterna i dessa listor avgör om skräp post regeln flyttar meddelandet till Inkorgen eller mappen skräp post. Användare kan konfigurera säker lista-samlingen för sin egen post låda i Outlook eller Outlook på webben (tidigare Outlook Web App). Administratörer kan konfigurera säker lista-samlingen i vilken användare som helst.

När skräp post regeln är aktive rad på post lådan kan EOP flytta meddelanden till mappen skräp post baserat på åtgärd för skräp post filtrering Verdict **Flytta meddelandet till mappen skräp post** eller listan Spärrade avsändare på post lådan och förhindra att meddelanden skickas till mappen för skräp post (baserat på listan Betrodda avsändare på post lådan).

 När skräp post regeln är inaktive rad på post lådan kan EOP inte flytta meddelanden till mappen skräp post baserat på åtgärd för skräp post filtrering Verdict **Flytta meddelandet till mappen skräp post** eller säker lista samlingen i post lådan.

Administratörer kan använda Exchange Online PowerShell för att inaktivera, aktivera och Visa status för skräp post regeln i post lådor. Administratörer kan även använda Exchange Online PowerShell för att konfigurera poster i säker lista-samlingen på post lådor (listan Betrodda avsändare, listan Betrodda mottagare och listan med spärrade avsändare).

> [!NOTE]
> Meddelanden från avsändare som användare har lagt till i sina egna listor för betrodda avsändare kommer att hoppa över filtrering för EOP (SCL är-1). Om du inte vill att användarna ska kunna lägga till poster i listan Betrodda avsändare i Outlook kan du använda grup princip som nämns i [om inställningar för skräp post i Outlook](#about-junk-email-settings-in-outlook) avsnitt längre ned i det här avsnittet. Princip filtrering, innehålls filtrering och kontroll av avancerat skydd (ATP) tillämpas fortfarande på meddelanden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du kan bara använda Exchange Online PowerShell för att utföra dessa procedurer. Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Du måste ha behörighet för att kunna göra detta. För det specifika måste du ha rollen **e-postmottagare** (som **tilldelats roll grupperna** **organisations hantering**, **mottagar hantering**och **anpassade e-postmottagare** ) eller rollen **användar alternativ** (som tilldelats roll grupperna **organisations hantering** och supportavdelning som standard). Information om hur du lägger till användare i roll grupper i Exchange Online finns i [ändra roll grupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups). Observera att en användare med standard behörigheter kan göra samma procedur på sin egen post låda, så länge de har [åtkomst till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell).

- I fristående EOP-miljöer där EOP skyddar lokala Exchange-postlådor måste du konfigurera e-postflödesregler (kallas även för transportregler) i lokalt Exchange för att översätta utfallet av skräppostfiltreringen i EOP så att regeln för skräppost kan flytta meddelandet till mappen Skräppost. Mer information finns i [Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

- Betrodda avsändare för delade post lådor synkroniseras inte till Azure AD och EOP efter design.

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Använda Exchange Online PowerShell för att aktivera eller inaktivera regeln för skräp post i en post låda

> [!NOTE]
> Du kan bara använda cmdleten **set-MailboxJunkEmailConfiguration** för att inaktivera skräp post regeln för en post låda som har öppnats i Outlook (i cachelagrat Exchange-läge) eller i Outlook på webben. Om post lådan inte har öppnats får du felet: `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` om du inte vill att det här felet ska visas för Mass åtgärder kan du lägga till `-ErrorAction SlientlyContinue` kommandot **set-MailboxJunkEmailConfiguration** .

Om du vill aktivera eller inaktivera skräp post regeln i en post låda använder du följande syntax:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

I det här exemplet inaktive ras skräp post regeln för Ori Epstein.

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

Det här exemplet inaktiverar skräp post regeln för alla användar post lådor i organisationen.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

Detaljerad information om syntax och parametrar finns i [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Om användaren aldrig har öppnat post lådan kanske du får ett fel meddelande när du kör föregående kommando. Om du vill dölja det här felet för Mass åtgärder lägger `-ErrorAction SlientlyContinue` du till kommandot **set-MailboxJunkEmailConfiguration** .
>
> - Även om du inaktiverar skräp post regeln kan skräp post filtret i Outlook (beroende på hur det är konfigurerat) också avgöra om ett meddelande är skräp post och kan flytta meddelanden till Inkorgen eller mappen skräp post i post lådan. Mer information finns i avsnittet [om inställningar för skräp post i](#about-junk-email-settings-in-outlook) det här avsnittet.

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Kontrol lera att du har aktiverat eller inaktiverat skräp post regeln på en post låda genom att göra något av följande:

- Ersätt _\<MailboxIdentity\>_ med namn, alias eller e-postadress för post lådan och kör följande kommando för att kontrol lera värdet för egenskapen **Enabled** :

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Använda Exchange Online PowerShell för att konfigurera en säker lista-samling på en post låda

Säker lista-samlingen i en post låda inkluderar listan Betrodda avsändare, listan Betrodda mottagare och listan Spärrade avsändare. Som standard kan användare konfigurera säker lista-samlingen på sin egen post låda i Outlook eller Outlook på webben. Administratörer kan använda motsvarande parametrar i cmdleten **set-MailboxJunkEmailConfiguration** för att konfigurera säker lista-samlingen i en användares post låda. Dessa parametrar beskrivs i följande tabell.

****

|Parameter på set-MailboxJunkEmailConfiguration|Outlook på webben|
|---|---|
|_BlockedSendersAndDomains_|**Flytta e-post från dessa avsändare eller domäner till mappen skräp post**|
|_ContactsTrusted_|**Lita på e-post från mina kontakter**|
|_TrustedListsOnly_|**Lita bara på e-post från adresser i listan Mina betrodda avsändare och domäner samt säkra distributions listor**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Flytta inte e-post från dessa avsändare till mappen skräp post**|
|

<sup>\*</sup>**Anteckningar**:

- I Exchange Online känns inte **domän poster** i listan Betrodda avsändare eller _TrustedSendersAndDomains_ till att använda e-postadresser. I fristående EOP med Directory-synkronisering synkroniseras domän poster inte som standard, men du kan aktivera synkronisering för domäner. Mer information finns i [KB3019657](https://support.microsoft.com/help/3019657).

- Du kan inte direkt ändra listan Betrodda mottagare genom att använda cmdleten **set-MailboxJunkEmailConfiguration** (parametern _TrustedRecipientsAndDomains_ fungerar inte). Du kan ändra listan Betrodda avsändare och ändringarna synkroniseras till listan Betrodda mottagare.

Om du vill konfigurera säker lista-samlingen på en post låda använder du följande syntax:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Om du vill ange flera värden och skriva över befintliga poster för parametrarna _BlockedSendersAndDomains_ och _TrustedSendersAndDomains_ använder du följande syntax: `"<Value1>","<Value2>"...` . Använd följande syntax för att lägga till eller ta bort ett eller flera värden utan att påverka andra befintliga poster:`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

I det här exemplet konfigureras följande inställningar för säker lista-samlingen i Ori Epsteins post låda:

- Lägg till värdet shopping@fabrikam.com till listan Spärrade avsändare.

- Ta bort värdet chris@fourthcoffee.com från listan Betrodda avsändare och listan Betrodda mottagare.

- Konfigurerar kontakter i mappen kontakter så att de behandlas som betrodda avsändare.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

Det här exemplet tar bort domän contoso.com från listan Spärrade avsändare i alla användar post lådor i organisationen.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Detaljerad information om syntax och parametrar finns i [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Om användaren aldrig har öppnat post lådan kanske du får ett fel meddelande när du kör föregående kommandon. Om du vill dölja det här felet för Mass åtgärder lägger `-ErrorAction SlientlyContinue` du till kommandot **set-MailboxJunkEmailConfiguration** .
>
> - Även om skräp post regeln är inaktive rad i post lådan kan du ändå konfigurera säker lista-samlingen och skräp post filtret i Outlook kan flytta meddelanden till Inkorgen eller mappen skräp post. Mer information finns i avsnittet [om inställningar för skräp post i](#about-junk-email-settings-in-outlook) det här avsnittet.
>
> - Skräp post filtret i Outlook har ytterligare inställningar för säker lista-samlingen (du kan till exempel **automatiskt lägga till personer som jag skickar e-post till i listan Betrodda avsändare**). Mer information finns i [använda skräp post filter för att styra vilka meddelanden som visas](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>Hur vet du att det fungerade?

Så här kontrollerar du att du har konfigurerat säker lista-samlingen på en post låda:

- Ersätt _\<MailboxIdentity\>_ med namn, alias eller e-postadressen till post lådan och kör följande kommando för att verifiera egenskaps värden:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Om listan med värden är för lång använder du följande syntax:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Om inställningar för skräp post i Outlook

Använd grup princip för att aktivera, inaktivera och konfigurera inställningar för skräp post filtret på klient sidan som är tillgängliga i Outlook. Mer information finns i [administrativa mallfiler (ADMX/ADML) och Office Customization Tool för Microsoft 365-appar för Enterprise, Office 2019 och office 2016](https://www.microsoft.com/download/details.aspx?id=49030) och [hur du distribuerar inställningar för skräp post, till exempel listan Betrodda avsändare, med hjälp av grup princip](https://support.microsoft.com/help/2252421).

När skräp post filtret för Outlook är inställt på standardvärdet **ingen automatisk filtrering** för skräp post alternativ **för skräp posten i Outlook** \> **Junk** \> **Junk E-Mail Options** \> **Options**görs inget försök att klassificera massages som skräp post, men ändå används säker lista-samlingen (listorna Betrodda avsändare, betrodda mottagare och spärrade avsändare) för att flytta meddelanden till mappen skräp post. Mer information om dessa inställningar finns i [Översikt över skräp post filtret](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

När skräp post filtret i Outlook är inställt på **lågt** eller **högt**, använder skräp post filtret i Outlook sin egen SmartScreen-filter teknik för att identifiera och flytta skräp posten till mappen skräp post. Denna skräp klassificering är åtskild från säkerhets nivån för skräp post (SCL) som bestäms av EOP. I praktiken ignorerar Outlook SCL från EOP (om EOP inte har markerat meddelandet för att hoppa över skräp post filter) och använder ett eget villkor för att avgöra om meddelandet är skräp post. Självklart är det möjligt att skräp posten Verdict från EOP och Outlook kanske är samma. Mer information om de här inställningarna finns i [ändra skydds nivån för skräp post filtret](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> I november 2016 slutade Microsoft att skapa uppdateringar för skräp post definitioner för SmartScreen-filtren i Exchange och Outlook. De befintliga skräp post definitionerna för SmartScreen slutade på plats, men deras effektivitet kommer sannolikt att påverka tiden. Mer information finns i om [stöd för SmartScreen i Outlook och Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Så att skräp post filtret i Outlook kan använda post lådans säker lista-samling och dess egna skräp post klassificering för att flytta meddelanden till mappen skräp post även om skräp post regeln är inaktive rad i post lådan.

Outlook och Outlook på webben stöder båda funktionerna för säker lista. Säker lista-samlingen sparas i Exchange Online-postlådan, så ändringar i säker lista-samlingen i Outlook visas i Outlook på webben och vice versa.

## <a name="limits-for-junk-email-settings"></a>Begränsningar för inställningar för skräp post

Samlingen säker lista (listor för betrodda avsändare, listan Betrodda mottagare och listan med spärrade avsändare) som lagras i användarens post låda synkroniseras också med EOP. Med profilsynkronisering synkroniseras säker lista-samlingen till Azure AD.

- Säker lista-samlingen i användarens post låda har en gräns på 510 KB, vilket inkluderar alla listor, plus ytterligare inställningar för skräp post filter. Om en användare överskrider den här gränsen får de ett Outlook-fel som ser ut så här:

  > Det går inte att/inte lägga till skräp post listorna. Du överskrider den tillåtna storleken på servern. Skräp post filtret på servern kommer att inaktive ras tills listorna med skräp post har reducerats till den storlek som servern tillåter.

  Mer information om den här gränsen och hur du ändrar det finns på [KB2669081](https://support.microsoft.com/help/2669081).

- Den synkroniserade säker lista-samlingen i EOP har följande begränsningar för synkronisering:

  - 1024 totalt antal poster i listan Betrodda avsändare, listan Betrodda mottagare och externa kontakter om **lita på e-post från mina kontakter** är aktive rad.
  - 500 totalt antal poster i listan Spärrade avsändare och blockerade domäner.

  När post gränsen för 1024 nås inträffar följande:

  - Listan slutar att acceptera poster i PowerShell och Outlook på webben, men inget fel visas.

    Outlook-användare kan fortsätta att lägga till fler än 1024 poster tills de når Outlook-gränsen på 510 KB. I Outlook kan du använda dessa ytterligare poster, så länge ett EOP-filter inte blockerar meddelandet innan det levereras till post lådan (regler för e-postflöde, begränsning för dataförfalskning etc.).

- Med katalog synkronisering synkroniseras posterna med Azure AD i följande ordning:

  1. E-postkontakter om **lita på e-post från mina kontakter** är aktive rad.
  2. Listan Betrodda avsändare och betrodda mottagare kombineras, avdupliceras och sorteras alfabetiskt när en ändring görs för de första 1024-posterna.

  De första 1024-posterna används och relevant information stämplas i meddelande rubrikerna.

  Poster över 1024 som inte synkroniserats till Azure AD behandlas av Outlook (inte Outlook på webben), och ingen information stämplas i meddelande rubrikerna.

Som du ser och aktiverar alternativet för att **lita på e-post från mina kontakter** minskar antalet betrodda avsändare och betrodda mottagare som kan synkroniseras. Om det här är ett problem rekommenderar vi att du använder grup princip för att stänga av den här funktionen:

- Fil namn: Outlk16. opax
- Princip inställning: **lita på e-post från kontakter**
