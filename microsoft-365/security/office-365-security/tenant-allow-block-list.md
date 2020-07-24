---
title: Hantera tillåtna och blockerade webbadresser och filer i listan Tillåt/blockera klient
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du konfigurerar URL- och filposter i listan Tillåt/blockera klient i säkerhets- & Compliance Center.
ms.openlocfilehash: db34abf28b5ead8106eb0b1447052d63072b2da3
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391572"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a>Hantera webbadresser och filer i listan över tillåtna/blockerade klientorganisationer

> [!NOTE]
> Funktionerna som beskrivs i det här avsnittet är i förhandsversion, kan komma att ändras och är inte tillgängliga i alla organisationer.

I Microsoft 365-organisationer med postlådor i Exchange Online- eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kanske du inte håller med om EOP-filtreringsdomen. Ett bra meddelande kan till exempel markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (ett falskt negativt).

Listan Tillåt/blockera innehavare i Security & Compliance Center ger dig ett sätt att manuellt åsidosätta Microsoft 365-filtreringsutlåtandena. Listan Tillåt/blockera klienter används under e-postflödet och vid tidpunkten för användarens klick. Du kan ange webbadresser och filer som ska tillåtas eller blockeras i listan Tillåt/blockera klient.

I det här avsnittet beskrivs hur du konfigurerar poster i listan Tillåt/blockera klient i Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt till sidan **Tillåt/blockera lista för klienter** använder du <https://protection.office.com/tenantAllowBlockList> .

- Du anger filer med hjälp av sha256-hash-värdet för filen. Om du vill hitta SHA256-hash-värdet för en fil i Windows kör du följande kommando i en kommandotolk:

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Perceptuella hash-värden (pHash) är inte tillåtna.

- De tillgängliga URL-värdena beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klient](#url-syntax-for-the-tenant-allowblock-list) senare i det här avsnittet.

- Med listan Tillåt/blockera klient kan högst 500 poster för webbadresser och 500 poster för filh hashar.

- En post ska vara aktiv inom 15 minuter.

- Blockposter har företräde framför tillåta transaktioner.

- Som standard upphör posterna i listan Tillåt/blockera klient att gälla efter 30 dagar. Du kan ange ett datum eller ange att de aldrig ska upphöra att gälla.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:

  - Om du vill lägga till och ta bort värden från listan Tillåt/blockera klient måste du vara medlem i någon av följande rollgrupper:

    - **Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).
    - **Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - För skrivskyddad åtkomst till listan Tillåt/blockera klient måste du vara medlem i någon av följande rollgrupper:

    - **Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).
    - **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Använda security & Compliance Center för att skapa URL-poster i listan Tillåt/blockera klient

Mer information om syntaxen för URL-poster finns i [URL-syntaxen för avsnittet Tillåt/blockera klient](#url-syntax-for-the-tenant-allowblock-list) senare i det här avsnittet.

1. Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.

2. Kontrollera att fliken **Webbadresser** är markerad på sidan **Tillåt/blockera lista** för klienter och klicka sedan på **Lägg till**

3. Konfigurera följande inställningar i utfällbara **url:er** som visas:

   - **Lägg till webbadresser med jokertecken:** Ange en URL per rad, upp till högst 20.

   - **Blockera/tillåt**: Välj om du vill **tillåta** eller **blockera** de angivna webbadresserna.

   - **Upphör aldrig att gälla**: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla för att ange ](../../media/scc-toggle-off.png) **utgångsdatum** för transaktionerna.

     eller

     - Flytta växlingsknappen åt höger för att konfigurera posterna så att de aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Valfri anmärkning:** Ange beskrivande text för posterna.

4. När du är klar klickar du på **Lägg till**.

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Använda Security & Compliance Center för att skapa filposter i listan Tillåt/blockera klient

1. Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.

2. På sidan **Tillåt/blockera lista för klienter** väljer du fliken **Filer** och klickar sedan på **Lägg till**.

3. Konfigurera följande inställningar i utfällbara **filer** som visas:

   - **Lägg till fil hashar:** Ange ett SHA256 hash-värde per rad, upp till maximalt 20.

   - **Blockera/Tillåt**: Välj om du vill **tillåta** eller **blockera** de angivna filerna.

   - **Upphör aldrig att gälla**: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla för att ange ](../../media/scc-toggle-off.png) **utgångsdatum** för transaktionerna.

     eller

     - Flytta växlingsknappen åt höger för att konfigurera posterna så att de aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Valfri anmärkning:** Ange beskrivande text för posterna.

4. När du är klar klickar du på **Lägg till**.

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>Använda Security & Compliance Center för att visa URL- och filposter i listan Tillåt/blockera klient

1. Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.

2. Välj fliken **Webbadresser** eller fliken **Filer.**

Klicka på följande kolumnrubriker för att sortera i stigande eller fallande ordning:

- **Värde**: URL:en eller filhh.
- **Åtgärd**: **Blockera** eller **tillåt**.
- **Senast uppdaterat datum**
- **Utgångsdatum**
- **Observera**

Klicka på **Gruppera** om du vill gruppera transaktionerna efter **Åtgärd** (**Block** eller **Tillåt**) eller **Ingen**.

Klicka på **Sök,** ange hela eller delar av en URL eller ett filvärde och tryck sedan på RETUR för att hitta ett visst värde. När du är klar klickar du på **Rensa** ![ sökikonen Rensa sökning ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .

Klicka på **Filter**. Konfigurera någon av följande inställningar i **utfällbara filter** som visas:

- **Åtgärd**: Välj **Tillåt,** **Blockera** eller båda.

- **Upphör aldrig att gälla:** Välj av ![ (Växla ](../../media/scc-toggle-off.png) av) eller på ( ![ Växla på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).

- **Senast uppdaterad**: Välj ett startdatum (**Från**), ett slutdatum (**Till**) eller båda.

- **Utgångsdatum**: Välj ett startdatum (**Från**), ett slutdatum (**Till**) eller båda.

När du är klar klickar du på **Använd**.

Om du vill ta bort befintliga filter klickar du på **Filtrera**och klickar på **Rensa filter**i det utfällbara **filter som** visas.

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>Använda Security & Compliance Center för att ändra URL- och filposter i listan Tillåt/blockera klient

Du kan inte ändra själva URL:en: eller filvärdet. I stället måste du ta bort posten och återskapa den.

1. Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.

2. Välj fliken **Webbadresser** eller fliken **Filer.**

3. Markera den post som du vill ändra och klicka sedan på **Ikonen Redigera** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) redigera.

4. Konfigurera följande inställningar i utfällbara utfällbara inställningar:

   - **Blockera/tillåt**: Välj **Tillåt** eller **Blockera**.

   - **Upphör aldrig att gälla**: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad ( ![ Stäng av ) och använd rutan Upphör att gälla ](../../media/scc-toggle-off.png) **för** att ange förfallodatumet för transaktionen.

     eller

     - Flytta växlingsknappen åt höger för att konfigurera posten så att den aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Valfri anmärkning:** Ange beskrivande text för posten.

5. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>Använd säkerhets- & Compliance Center för att ta bort URL- och filposter från listan Tillåt/blockera klient

1. Gå till Tillåt/blockera listor för **&-efterlevnad** i säkerhets- & \> **Policy** \> **efterlevnadscenter**.

2. Välj fliken **Webbadresser** eller fliken **Filer.**

3. Markera den post som du vill ta bort och klicka sedan på **Ikonen Ta bort borttagning** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. Klicka på **Ta bort**i varningsdialogrutan som visas.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera listan Tillåt/blockera klient

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att lägga till URL- och filposter i listan Tillåt/blockera klient

Om du vill lägga till URL- och filposter i listan Tillåt/blockera klienter använder du följande syntax:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

I det här exemplet läggs en URL-blockpost för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com). Eftersom vi inte använde parametrarna ExpirationDate eller NoExpiration upphör posten att gälla efter 30 dagar.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

I det här exemplet läggs en fil tillåta post för de angivna filer som aldrig upphör att gälla.

Detaljerad syntax- och parameterinformation finns i [Ny-KlientEns 111111.For](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)detailed syntax and parameter information, see New-TenantAllowBlockListItems .

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att visa URL- och filposter i listan Tillåt/blockera klient

Om du vill visa URL- och filposter i listan Tillåt/blockera klienter använder du följande syntax:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

I det här exemplet returneras alla blockerade webbadresser.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

I det här exemplet returneras information om det angivna filhh-värdet.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Detaljerad syntax- och parameterinformation finns i [Hämta-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att ändra URL- och filposter i listan Tillåt/blockera klient

Du kan inte ändra själva URL:en: eller filvärdet. I stället måste du ta bort posten och återskapa den.

Om du vill ändra URL- och filposter i listan Tillåt/blockera klienter använder du följande syntax:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

I det här exemplet ändras förfallodatumet för den angivna posten.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Detaljerad syntax- och parameterinformation finns i [Ange-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a>Använda PowerShell för att ta bort URL- och filposter från listan Tillåt/blockera klient

Om du vill ta bort URL- och filposter från listan Tillåt/blockera klienter använder du följande syntax:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

I det här exemplet tas den angivna URL-posten bort från listan Tillåt/blockera klient.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Detaljerad syntax- och parameterinformation finns i [Ta bort-klientEnAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>URL-syntax för listan Tillåt/blockera klient

- IP4v- och IPv6-adresser är tillåtna, men TCP/UDP-portar är det inte.

- Filnamnstillägg är inte tillåtna (till exempel test.pdf).

- Unicode stöds inte, men Punycode är.

- Värdnamn är tillåtna om alla följande satser är sanna:

  - Värdnamnet innehåller en punkt.
  - Det finns minst ett tecken till vänster om perioden.
  - Det finns minst två tecken till höger om perioden.

  Till exempel `t.co` är tillåtet, `.com` eller är inte `contoso.` tillåtna.

- Undervägar är inte underförstådda.

  Innehåller till exempel `contoso.com` inte `contoso.com/a` .

- Jokertecken (*) tillåts i följande scenarier:

  - Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.

    Till exempel `*.contoso.com` är tillåtet, `*contoso.com` är inte tillåtet.

  - Ett höger jokertecken måste följa ett snedstreck (/) för att ange en bana.

    Till exempel `contoso.com/*` är tillåtet, `contoso.com*` eller är inte `contoso.com/ab*` tillåtna.

  - Alla underbanor är inte underförstådda av ett höger jokertecken.

    Innehåller till exempel `contoso.com/*` inte `contoso.com/a` .

  - `*.com*`är ogiltigt (inte en lösningsbar domän och det högra jokertecknet följer inte ett snedstreck).

  - Jokertecken är inte tillåtna i IP-adresser.

- Tilde -tecknet (~) är tillgängligt i följande scenarier:

  - En vänster tilde innebär en domän och alla underdomäner.

    Till exempel `~contoso.com` innehåller `contoso.com` och `*.contoso.com` .

- URL-poster som innehåller protokoll (till exempel `http://` `https://` , eller ) `ftp://` misslyckas, eftersom URL-poster gäller för alla protokoll.

- Ett användarnamn eller lösenord stöds inte eller krävs inte.

- Citattecken (' eller ") är ogiltiga tecken.

- En webbadress bör innehålla alla omdirigeringar där det är möjligt.

### <a name="url-entry-scenarios"></a>Scenarier för URL-post

Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.

#### <a name="scenario-no-wildcards"></a>Scenario: Inga jokertecken

**Inträde**:`contoso.com`

- **Tillåt matchning**: contoso.com

- **Tillåt inte matchad:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
- **Blockera matchning:**

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blocket matchas inte:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: Vänster jokertecken (underdomän)

**Inträde**:`*.contoso.com`

- **Tillåt matchning** och **blockmatchning:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Tillåt inte matchade** och **Blockera matchas inte:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: Höger jokertecken högst upp i banan

**Inträde**:`contoso.com/a/*`

- **Tillåt matchning** och **blockmatchning:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Tillåt inte matchade** och **Blockera matchas inte:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com
  
#### <a name="scenario-left-tilde"></a>Scenario: Vänster tilde

**Inträde**:`~contoso.com`

- **Tillåt matchning** och **blockmatchning:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Tillåt inte matchade** och **Blockera matchas inte:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: Höger jokertecken suffix

**Inträde**:`contoso.com/*`

- **Tillåt matchning** och **blockmatchning:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Tillåt inte matchade** och **Blockera inte matchas:** contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: Vänster jokertecken underdomän och höger jokertecken suffix

**Inträde**:`*.contoso.com/*`

- **Tillåt matchning** och **blockmatchning:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Tillåt inte matchade** och **Blockera inte matchas:** contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: Vänster och höger tilde

**Inträde**:`~contoso.com~`

- **Tillåt matchning** och **blockmatchning:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Tillåt inte matchade** och **Blockera matchas inte:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: IP-adress

**Inträde**:`1.2.3.4`

- **Tillåt matchning** och **blockmatchning:** 1.2.3.4

- **Tillåt inte matchade** och **Blockera matchas inte:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-adress med höger jokertecken

**Inträde**:`1.2.3.4/*`

- **Tillåt matchning** och **blockmatchning:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Exempel på ogiltiga poster

Följande poster är ogiltiga:

- **Domänvärden som saknas eller är ogiltiga:**

  - Contoso
  - \*.contoso.\*
  - \*.com (på marknaden)
  - \*Pdf

- **Jokertecken på text eller utan mellanrumstecken:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-adresser med portar:**

  - contoso.com:443
  - abc.contoso.com:25

- **Icke-beskrivande jokertecken:**

  - \*
  - \*.\*

- **Jokertecken i mitten:**

  - conto \* so.com
  - conto ~so.com

- **Dubbla jokertecken**

  - contoso.com/\*\*
  - contoso.com/\*/\*
