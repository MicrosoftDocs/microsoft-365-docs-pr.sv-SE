---
title: Hantera dina tillåtna och block i klientorganisationens lista över tillåtna/blockerade
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratörer kan ta reda på hur de konfigurerar tillåts och spärras i listan över tillåtna eller blockerade klienter i säkerhetsportalen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e460f4e93f7b87faaead8b87ba561224e38938
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515214"
---
# <a name="manage-the-tenant-allowblock-list"></a>Hantera Klientorganisationens Tillåt/blockera listan

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> Funktionerna som beskrivs i den här artikeln är förhandsversioner, kan komma att ändras och är inte tillgängliga i alla organisationer.
>
> Du kan för **stunden inte** konfigurera tillåtna objekt i klientorganisationens lista över tillåtna/blockerade objekt.

I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kanske du inte håller med om EOP-filtreringens bedömning. Ett bra meddelande kan till exempel markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (falskt negativa).

Klientorganisationens lista över tillåtna/blockerade i Säkerhets- & efterlevnadscenter ger dig ett sätt att manuellt åsidosätta filtreringsvillkoren i Microsoft 365. Klientorganisationens lista över tillåtna/blockerade används under e-postflödet och när användaren klickar. Du kan ange URL:er eller filer som alltid ska blockeras.

I den här artikeln beskrivs hur du konfigurerar poster i listan över tillåtna och blockerade klientorganisationer i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Om du vill gå direkt **till sidan Tillåt/blockera klientorganisation** använder du <https://protection.office.com/tenantAllowBlockList> .

- Du anger filer med hjälp av SHA256-hashvärdet för filen. Om du vill hitta SHA256-hashvärdet för en fil i Windows kör du följande kommando i en kommandotolk:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Värden för perceptuell hash (pHash) stöds inte.

- Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klientorganisation senare](#url-syntax-for-the-tenant-allowblock-list) i den här artikeln.

- Klientorganisationens lista över tillåtna/blockerade kan högst 500 poster för URL:er och 500 poster för filshashar.

- Det maximala antalet tecken för varje post är:
  - Filshashar = 64
  - URL = 250

- En post ska vara aktiv inom 30 minuter.

- Som standard förfaller poster i klientorganisationens lista över tillåtna/blockerade poster efter 30 dagar. Du kan ange ett datum eller ange att de aldrig ska upphöra att gälla.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:
  - Om du vill lägga till och ta bort värden från klientorganisationens lista över tillåtna/blockerade måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**
  - För skrivskyddad åtkomst till klientorganisationens lista över tillåtna/blockerade måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**

  Mer information finns under [Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > 
  > - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  > - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & center för att skapa URL-poster i klientorganisationens lista över tillåtna/blockerade adresser

Mer information om syntaxen för URL-poster finns i URL-syntaxen för avsnittet [Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) senare i den här artikeln.

1. Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**

2. Kontrollera att **fliken URL:er är** markerad på sidan **Tillåt/blockera** klientorganisation och klicka sedan på **Blockera**

3. I den **utfällna** menyn Blockera URL:er som visas konfigurerar du följande inställningar:

   - **Lägg till URL-adresser som** ska blockeras: Ange en URL per rad, upp till maximalt 20.

   - **Upphör aldrig** att gälla: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad (inaktiverad) och ange ![ ](../../media/scc-toggle-off.png) **utgångsdatumet** för posterna med hjälp av rutan Förfallodatum.

       eller

     - Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png).

   - **Valfritt:** Ange beskrivande text för posterna.

4. Klicka på Lägg till när du är **klar.**

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & Center för efterlevnad för att skapa filposter i klientorganisationens lista över tillåtna/blockerade filer

1. Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**

2. Välj fliken **Filer på sidan Tillåt/blockera** **för** klientorganisation och klicka sedan på **Blockera.**

3. I den **utfällna menyn** Lägg till filer för att blockera som visas konfigurerar du följande inställningar:

   - **Lägga till filshashar:** Ange ett SHA256-hashvärde per rad, upp till maximalt 20.

   - **Upphör aldrig** att gälla: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad (inaktiverad) och ange ![ ](../../media/scc-toggle-off.png) **utgångsdatumet** för posterna med hjälp av rutan Förfallodatum.

     eller

     - Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png).

   - **Valfritt:** Ange beskrivande text för posterna.

4. Klicka på Lägg till när du är **klar.**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & efterlevnadscenter för att visa poster i klientorganisationens lista över tillåtna/blockerade

1. Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**

2. Välj **fliken URL:er** eller **fliken** Filer.

Klicka på följande kolumnrubriker för att sortera i stigande eller fallande ordning:

- **Värde:** URL:en eller filens hashtagg.
- **Datum för senaste uppdatering**
- **Förfallodatum**
- **Obs!**

Klicka **på Sök,** ange hela eller en del av ett värde och tryck sedan på RETUR för att hitta ett visst värde. När du är klar klickar du på **ikonen Rensa** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) sökning.

Klicka **på Filtrera.** I den **utfällna** menyn Filter som visas konfigurerar du någon av följande inställningar:

- **Upphör aldrig** att gälla: Välj ![ av: Aktivera ](../../media/scc-toggle-off.png) eller ![ ](../../media/scc-toggle-on.png) inaktivera.

- **Senast uppdaterad:** Välj ett startdatum **(Från),** ett slutdatum **(Till)** eller både och.

- **Förfallodatum:** Välj ett startdatum **(Från),** ett slutdatum **(Till)** eller båda.

Klicka på Använd när du är **klar.**

Om du vill ta bort befintliga  **filter klickar** du på Filter och sedan på Rensa filter i den **utfällklara filterfällan som visas.**

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & Center för efterlevnad för att ändra blockeringsposter i klientorganisationens lista över tillåtna/blockerade

Du kan inte ändra befintliga blockerade URL-adresser eller filvärden i en post. Om du vill ändra dessa värden måste du ta bort och återskapa posten.

1. Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**

2. Välj **fliken URL:er** eller **fliken** Filer.

3. Markera den blockpost som du vill ändra och klicka sedan **på** ikonen ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Redigera.

4. Konfigurera följande inställningar i den utfällo som visas:

   - **Upphör aldrig** att gälla: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad (inaktiverad) och ange förfallodatumet med hjälp av rutan ![ ](../../media/scc-toggle-off.png) Förfallodatum. 

       eller

     - Flytta reglaget till höger för att konfigurera posten så att den aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png).

   - **Valfritt** meddelande: Ange beskrivande text för posten.

5. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Använda Säkerhets- & för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade

1. Gå till innehavarlistan & över  tillåtna och blockerade hothanteringsprinciper i Säkerhets- \>  \> **och efterlevnadscenter.**

2. Välj **fliken URL:er** eller **fliken** Filer.

3. Markera den blockpost du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) bort.

4. Klicka på Ta bort i **varningsdialogrutan som visas.**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera klientorganisationens lista över tillåtna/blockerade

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a>Använda PowerShell för att lägga till blockeringsposter i klientorganisationens lista över tillåtna/blockerade

Använd följande syntax för att lägga till blockeringsposter i klientorganisationens lista över tillåtna/blockerade:

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

Det här exemplet lägger till en blockerings-URL-post för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com). Eftersom vi inte använder parametrarna Förfallodatum eller NoExpiration går posten ut efter 30 dagar.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

I det här exemplet läggs en blockeringsfilpost till för de angivna filerna som aldrig förfaller.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att visa poster i klientorganisationens lista över tillåtna/blockerade

För att visa poster i klientorganisationens lista över tillåtna/blockerade, använder du följande syntax:

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

I det här exemplet returneras alla blockerade URL:er.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Det här exemplet returnerar information för det angivna hashvärdet för filen.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att ändra blockeringsposter i klientorganisationens lista över tillåtna/blockerade

Du kan inte ändra befintliga URL- eller filvärden inom en blockeringspost. Om du vill ändra dessa värden måste du ta bort och återskapa posten.

Använd följande syntax för att ändra blockeringsposter i klientorganisationens lista över tillåtna/blockerade:

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

I det här exemplet ändras förfallodatumet för den angivna blockeringsposten.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a>Använda PowerShell för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade

Använd följande syntax för att ta bort blockeringsposter från klientorganisationens lista över tillåtna/blockerade:

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

I det här exemplet tas den angivna blockerings-URL-posten bort från klientorganisationens lista över tillåtna/blockerade adresser.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems.](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>URL-syntax för klientorganisationens lista över tillåtna/blockerade

- IP4v- och IPv6-adresser är tillåtna, men TCP-/UDP-portar är inte tillåtna.

- Filnamnstillägg är inte tillåtna (till exempel test.pdf).

- Unicode stöds inte, men punycode stöds.

- Hostnames tillåts om alla följande uttryck är sanna:
  - Värdnamnet innehåller en punkt.
  - Det finns minst ett tecken till vänster om perioden.
  - Det finns minst två tecken till höger om perioden.

  Till exempel är `t.co` tillåtet eller `.com` är inte `contoso.` tillåtet.

- Undervägar är inte underförstådda.

  Exempel: `contoso.com` Inkluderar inte `contoso.com/a` .

- Jokertecken (*) tillåts i följande scenarier:

  - Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.

    Till exempel `*.contoso.com` tillåts, `*contoso.com` är inte tillåtet.

  - Ett höger jokertecken måste följa ett snedstreck (/) för att ange en sökväg.

    Till exempel är `contoso.com/*` tillåtet eller `contoso.com*` är inte `contoso.com/ab*` tillåtet.

  - Alla undervägar är inte underförstådda med ett rätt jokertecken.

    Exempel: `contoso.com/*` Inkluderar inte `contoso.com/a` .

  - `*.com*` är ogiltig (inte en lösbar domän och rätt jokertecken följer inte ett snedstreck).

  - Jokertecken är inte tillåtna i IP-adresser.

- Tecknet tilde (~) är tillgängligt i följande scenarier:

  - Ett vänster tilde-namn antyder en domän och alla underdomäner.

    Exempel: `~contoso.com` `contoso.com` innehåller och `*.contoso.com` .

- URL-poster som innehåller protokoll (till exempel, eller ) kommer att `http://` `https://` `ftp://` misslyckas, eftersom URL-poster gäller för alla protokoll.

- Ett användarnamn eller lösenord stöds inte eller krävs inte.

- Citattecken (' eller ") är ogiltiga tecken.

- En URL bör innehålla alla omdirigeringar om det är möjligt.

### <a name="url-entry-scenarios"></a>URL-inmatningsscenarier

Giltiga URL-poster och deras resultat beskrivs i följande avsnitt.

#### <a name="scenario-no-wildcards"></a>Scenario: Inga jokertecken

**Post:**`contoso.com`

- **Tillåt matchning:** contoso.com

- **Tillåt ej matchad:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blockmatchning:**

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blocket matchas inte:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: Vänster jokertecken (underdomän)

**Post:**`*.contoso.com`

- **Tillåt matchning** och **blockeringsmatchning:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Tillåt ej matchad** och **Blockera matchas inte:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: Höger jokertecken högst upp i sökvägen

**Post:**`contoso.com/a/*`

- **Tillåt matchning** och **blockeringsmatchning:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Tillåt ej matchad** och **Blockera matchas inte:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Scenario: Vänster tilde

**Post:**`~contoso.com`

- **Tillåt matchning** och **blockeringsmatchning:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Tillåt ej matchad** och **Blockera matchas inte:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: Höger suffix för jokertecken

**Post:**`contoso.com/*`

- **Tillåt matchning** och **blockeringsmatchning:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Tillåt ej matchad** och **Blockera matchas inte:** contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: Underdomän för vänster jokertecken och höger suffix för jokertecken

**Post:**`*.contoso.com/*`

- **Tillåt matchning** och **blockeringsmatchning:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Tillåt ej matchad** och **Blockera matchas inte:** contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: Vänster och höger tilde

**Post:**`~contoso.com~`

- **Tillåt matchning** och **blockeringsmatchning:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Tillåt ej matchad** och **Blockera matchas inte:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: IP-adress

**Post:**`1.2.3.4`

- **Tillåt matchning** och **blockeringsmatchning:** 1.2.3.4

- **Tillåt ej matchad** och **Blockera matchas inte:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-adress med rätt jokertecken

**Post:**`1.2.3.4/*`

- **Tillåt matchning** och **blockeringsmatchning:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Exempel på ogiltiga poster

Följande poster är ogiltiga:

- **Värden som saknas eller är ogiltiga:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*PDF

- **Jokertecken i text eller utan avståndstecken:**

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

- **Mellan jokertecken:**

  - conto \* so.com
  - conto~so.com

- **Dubbla jokertecken**

  - contoso.com/\*\*
  - contoso.com/\*/\*
