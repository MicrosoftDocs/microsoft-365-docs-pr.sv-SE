---
title: Hantera tillåt och block i listan över tillåtna/blockerade klientorganisation
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
description: Administratörer kan ta reda på hur de konfigurerar tillåts och block i listan över tillåtna/blockerade klienter i säkerhetsportalen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 12139708fc5cde133819713fd7185435e594a1a9
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809185"
---
# <a name="manage-the-tenant-allowblock-list"></a>Hantera Klientorganisationens Tillåt/blockera listan

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> Funktionerna som beskrivs i den här artikeln är förhandsversioner, kan komma att ändras och är inte tillgängliga i alla organisationer.  Om din organisation inte har de förfalskningsfunktioner som beskrivs i den här artikeln kan du läsa mer om den äldre hanteringsupplevelsen för förfalskningsfunktioner i Hantera förfalskningsavsändare med hjälp av [förfalskningsprincip](walkthrough-spoof-intelligence-insight.md)och förfalskningsinformation i EOP.
>
> Du kan för **stunden inte** konfigurera tillåtna URL-adresser eller filobjekt i listan över tillåtna/blockerade klienter.

I Microsoft 365 organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor, kanske du inte instämmer i EOP-filtrerings förlopp. Till exempel kan ett bra meddelande markeras som dåligt (falskt positivt) eller så kan ett felaktigt meddelande tillåtas (falskt negativt).

Med klientorganisationens lista över tillåtna/blockerade & säkerhets- och efterlevnadscenter får du ett sätt att manuellt åsidosätta Microsoft 365 filtrera överensstämmelser. Klientorganisationens lista över tillåtna/blockerade används under e-postflödet och när användaren klickar. Du kan ange följande typer av åsidosättningar:

- URL:er som ska blockeras.
- Filer som ska blockeras.
- Förfalskningsavsändare som ska tillåta eller blockera. Om du åsidosätter blockeringen av tillåtande eller blockering av förfalskningsinformation [blir](learn-about-spoof-intelligence.md)den falska avsändaren en  manuell tillåta- eller blockeringspost som bara visas på fliken Förfalskning i innehavarlistan över tillåtna/blockerade avsändare. Här kan du även manuellt skapa tillåta eller blockera poster för förfalskningsavsändare innan de identifieras av förfalskningsinformation.

Den här artikeln beskriver hur du konfigurerar poster i listan Över tillåtna/blockerade klientorganisationer i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>. Använd för att gå direkt **till sidan För att tillåta/blockera** klientorganisation. <https://protection.office.com/tenantAllowBlockList>

- Du anger filer genom att använda hashvärdet SHA256 för filen. Om du vill hitta hashvärdet SHA256 för en fil i Windows kör du följande kommando i kommandotolken:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Ett exempelvärde är `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Perceptuella hash-värden (pHash) stöds inte.

- Tillgängliga URL-värden beskrivs i [URL-syntaxen för avsnittet Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) senare i den här artikeln.

- Klientorganisationens lista över tillåtna/blockerade tillåter maximalt 500 poster för URL:er och 500 poster för filshashar.

- Det maximala antalet tecken för varje post är:
  - Filshashar = 64
  - URL = 250

- En post ska vara aktiv inom 30 minuter.

- Som standard förfaller poster i klientorganisationens lista över tillåtna/blockerade användare efter 30 dagar. Du kan ange ett datum eller ange att de aldrig ska upphöra.

- Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter i Exchange Online innan du kan genomföra procedurerna i den här artikeln:
  - **URL:er och filer:**
    - Om du vill lägga till och ta bort värden från klientorganisationens lista över tillåtna/blockerade användare måste du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.** 
    - För skrivskyddad åtkomst till listan över tillåtna/blockerade klientorganisationer måste du vara medlem i rollgrupperna **Global Reader** **eller Säkerhetsläsare.**
  - **Förfalskning**: En av följande kombinationer:
    - **Organisationshantering**
    - **Säkerhetsadministratör** <u>och</u> **endast visa-konfiguration** **eller organisationshantering – endast visa.**

  Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).
  >
  > - Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & efterlevnadscenter för att skapa blockera URL-poster i klientorganisationens lista över tillåtna/blockerade adresser

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. På sidan **Lista över tillåtna/blockerade** klientorganisation kontrollerar du att **fliken URL:er** är markerad och klickar sedan på **Blockera**

3. I den **utfällna** menyn Blockera URL:er som visas konfigurerar du följande inställningar:

   - **Lägg till URL:er som ska** blockeras: Ange en URL per rad, upp till högst 20. Mer information om syntaxen för URL-poster finns i URL-syntaxen för avsnittet [Tillåt/blockera klientorganisation](#url-syntax-for-the-tenant-allowblock-list) längre fram i den här artikeln.

   - **Upphör aldrig** att gälla: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. 

       eller

     - Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png).

   - **Valfritt:** Ange beskrivande text för posterna.

4. När du är klar klickar du på Lägg **till**.

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & säkerhets- och efterlevnadscenter för att skapa blockeringsfilposter i klientorganisationens lista över tillåtna/blockerade filer

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. På sidan **Lista över tillåtna/blockerade** klientorganisation väljer du **fliken** Filer och klickar sedan på **Blockera**.

3. I den **utfällna menyn** Lägg till filer för att blockera som visas konfigurerar du följande inställningar:

   - **Lägga till filhashar:** Ange ett SHA256-hashvärde per rad, upp till högst 20.

   - **Upphör aldrig** att gälla: Gör något av följande:

     - Kontrollera att inställningen är inaktiverad (inaktiverad) och ange utgångsdatumet för posterna ![ ](../../media/scc-toggle-off.png) i rutan Förfaller. 

     eller

     - Flytta reglaget till höger för att konfigurera posterna så att de aldrig upphör att gälla: ![Växlingsknapp aktiverad](../../media/scc-toggle-on.png).

   - **Valfritt:** Ange beskrivande text för posterna.

4. När du är klar klickar du på Lägg **till**.

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & säkerhets- och efterlevnadscenter för att skapa tillåta eller blockera förfalskning av avsändare i listan Tillåt/blockera klientorganisation

**Anmärkningar**:

- Endast kombinationen _av_ den förfalskningsanvändaren och avsändarinfrastrukturen som definierats i domänparet är specifikt tillåten eller blockerad från förfalskning. 
- När du konfigurerar en tillåta- eller blockeringspost för ett domänpar visas inte längre meddelanden från det domänparet i förfalskningsinformation.
- Poster för falska avsändare upphör aldrig att gälla.

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. Välj **fliken Förfalskning på sidan Lista** över tillåtna/blockerade **klientorganisation** och klicka sedan på Lägg **till.**

3. I den **utfällna menyn** Lägg till ny domänpar som visas konfigurerar du följande inställningar:

   - **Lägga till nya domänpar med jokertecken:** Ange ett domänpar per rad, upp till maximalt 20. Mer information om syntaxen för falska avsändarposter finns i syntaxen för domänpar för posterna för falska avsändare i avsnittet [Tillåt/blockera](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) lista för klientorganisation längre fram i den här artikeln.

   - **Förfalskningstyp:** Välj något av följande värden:
     - **Internt**: Förfalskningsavsändare finns i en domän som tillhör din organisation (en [godkänd domän).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **Extern:** Den falska avsändaren finns i en extern domän.

   - **Åtgärd:** Välj **Tillåt** eller **Blockera**.

4. När du är klar klickar du på Lägg **till**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & kompatibilitetscenter för att visa poster i listan över tillåtna/blockerade klientorganisationen

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. Välj den flik du vill använda. Vilka kolumner som är tillgängliga beror på vilken flik du valde:

   - **URL:er:**
     - **Värde:** URL:en.
     - **Åtgärd:** **Värdeblocket**.
     - **Datum för senaste uppdatering**
     - **Förfallodatum**
     - **Obs!**

   - **Filer**
     - **Värde:** Filens hash-kod.
     - **Åtgärd:** **Värdeblocket**.
     - **Datum för senaste uppdatering**
     - **Förfallodatum**
     - **Obs!**

   - **Förfalskning**
     - **Spoofed användare**
     - **Skicka infrastruktur**
     - **Förfalskningstyp:** värdet **Internt eller** **Externt**.
     - **Åtgärd:** **Värdeblockering** eller **Tillåt**.

   Du kan klicka på en kolumnrubrik om du vill sortera i stigande eller fallande ordning.

   Du kan gruppera **resultatet genom** att klicka på Gruppera. Vilka värden som är tillgängliga beror på vilken flik du valde:

   - **URL:er:** Du kan gruppera resultatet efter **åtgärd.**
   - **Filer:** Du kan gruppera resultatet efter **åtgärd.**
   - **Avsändardomäner för BCL-förbikoppling:** **Gruppen** är inte tillgänglig på den här fliken.
   - **Förfalskning:** Du kan gruppera resultaten efter **Åtgärds-** **eller förfalskningstyp.**

   Klicka **på** Sök , ange hela eller en del av ett värde och tryck sedan på RETUR för att hitta ett visst värde. När du är klar klickar du på **Rensa sökning Ikonen** Rensa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) sökning.

   Filtrera **resultatet genom** att klicka på Filter. Vilka värden som är tillgängliga **i den utfällade** filterflik som visas beror på vilken flik du valde:

   - **URL:er**
     - **Åtgärd**
     - **Upphör aldrig att gälla**
     - **Datum för senaste uppdatering**
     - **Förfallodatum**

   - **Filer**
     - **Åtgärd**
     - **Upphör aldrig att gälla**
     - **Datum för senaste uppdatering**
     - **Förfallodatum**

   - **Sender domains for BCL bypass**
     - **Upphör aldrig att gälla**
     - **Datum för senaste uppdatering**
     - **Förfallodatum**

   - **Förfalskning**
     - **Åtgärd**
     - **Förfalskningstyp**

   När du är klar klickar du på **Använd**. Om du vill ta bort befintliga  **filter klickar** du på Filter och sedan på Rensa filter i den **utfällklara filterfällan som visas.**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Använd Säkerhets- & säkerhets- och efterlevnadscenter för att ändra poster i listan över tillåtna/blockerade klientorganisationen

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. Välj den flik som innehåller den typ av post som du vill ändra:
   - **URL:er**
   - **Filer**
   - **Sender domains for BCL bypass**
   - **Förfalskning**

3. Markera den post som du vill  ändra och klicka sedan på redigera ![ redigeringsikonen ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) . Vilka värden som du kan ändra i den utfäll plats som visas beror på vilken flik du valde i föregående steg:

   - **URL:er**
     - **Upphör aldrig att** gälla och/eller förfallodatum.
     - **Valfri anteckning**

   - **Filer**
     - **Upphör aldrig att** gälla och/eller förfallodatum.
     - **Valfri anteckning**

   - **Sender domains for BCL bypass**
     - **Upphör aldrig att** gälla och/eller förfallodatum.

   - **Förfalskning**
     - **Åtgärd:** Du kan ändra värdet till **Tillåt** eller **Blockera.**

4. Klicka på **Spara** när du är klar.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Använda Säkerhets- & säkerhets- och efterlevnadscenter för att ta bort poster från listan över tillåtna/blockerade klientorganisationen

1. I Säkerhets- & säkerhets- och efterlevnadscenter går du till **listan** över \>  \> **tillåtna/blockerade hotprinciper för klientorganisationen.**

2. Välj den flik som innehåller den typ av post som du vill ta bort:
   - **URL:er**
   - **Filer**
   - **Sender domains for BCL bypass**
   - **Förfalskning**

3. Markera den post som du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) bort.

4. Klicka på Ta bort i varningsdialogrutan som **visas.**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Använd Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera innehavarlistan över tillåtna/blockerade

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>Använda PowerShell för att lägga till blockeringsfiler eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser

Använd följande syntax för att lägga till blockeringsfiler eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

I det här exemplet läggs en post för blockering av filer till för de angivna filerna som aldrig förfaller.

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

I det här exemplet läggs en blockerings-URL-post till för contoso.com och alla underdomäner (till exempel contoso.com, www.contoso.com och xyz.abc.contoso.com). Eftersom vi inte använder parametrarna Förfallodatum eller NoExpiration upphör posten att gälla efter 30 dagar.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a>Använd PowerShell för att lägga till posterna tillåta eller blockera förfalskning av avsändare i klientorganisationens lista över tillåtna/blockerade avsändare

Om du vill lägga till förfalskningsposter från klientorganisationens lista över tillåtna/blockerade avsändare använder du följande syntax:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Detaljerad information om syntax och parametrar finns i [New-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/new-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att visa blockera fil- eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser

Om du vill visa blockeringsfil- eller URL-poster i klientorganisationens lista över tillåtna/blockerade adresser använder du följande syntax:

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

Det här exemplet returnerar information om det angivna hash-värdet för filen.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

I det här exemplet returneras alla blockerade URL-adresser.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListItems.](/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att visa tillåta eller blockera förfalskning av avsändare i klientorganisationens lista över tillåtna/blockerade avsändare

Använd följande syntax för att visa falska avsändarposter i listan Tillåt/blockera klientorganisation:

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

Det här exemplet returnerar alla falska avsändarposter i listan över tillåtna/blockerade klientorganisationen.

```powershell
Get-TenantAllowBlockListSpoofItems
```

Det här exemplet returnerar alla interna poster med tillåta förfalskning.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

Det här exemplet returnerar alla externa poster för spärrade avsändare.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

Detaljerad information om syntax och parametrar finns i [Get-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/get-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att ändra blockeringsfiler och URL-poster i klientorganisationens lista över tillåtna/blockerade adresser

Använd följande syntax för att ändra blockeringsfiler och URL-poster i klientorganisationens lista över tillåtna/blockerade adresser:

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

I det här exemplet ändras förfallodatumet för den angivna blockerings-URL-posten.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListItems.](/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Använda PowerShell för att ändra posterna för tillåta eller blockera förfalskning av avsändare i listan över tillåtna/blockerade klientorganisationen

Om du vill ändra tillåta eller blockera förfalskning av avsändare i listan över tillåtna eller blockerade avsändare använder du följande syntax:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

I det här exemplet ändras en förfalskningspost från tillåts till blockering.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Detaljerad information om syntax och parametrar finns i [Set-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/set-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>Använda PowerShell för att ta bort URL-adresser eller filposter från klientorganisationens lista över tillåtna/blockerade adresser

Använd följande syntax för att ta bort fil- och URL-poster från klientorganisationens lista över tillåtna/blockerade adresser:

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

Det här exemplet tar bort den angivna blockerings-URL-posten från klientorganisationens lista över tillåtna/blockerade adresser.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListItems.](/powershell/module/exchange/remove-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>Använda PowerShell för att ta bort tillåta eller blockera förfalskning av avsändare från klientorganisationens lista över tillåtna/blockerade avsändare

Om du vill ta bort tillåta eller blockera förfalskning av avsändare från klientorganisationens lista över tillåtna/blockerade avsändare använder du följande syntax:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Detaljerad information om syntax och parametrar finns i [Remove-TenantAllowBlockListSpoofItems.](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>URL-syntax för klientorganisationens lista över tillåtna/blockerade

- IP4v- och IPv6-adresser är tillåtna, men INTE TCP-/UDP-portar.

- Filnamnstillägg är inte tillåtna (till exempel test.pdf).

- Unicode stöds inte, men punycode stöds.

- Hostnames tillåts om alla följande uttryck är sanna:
  - Värdnamnet innehåller en punkt.
  - Det finns minst ett tecken till vänster om perioden.
  - Det finns minst två tecken till höger om perioden.

  Till exempel är `t.co` tillåtet eller `.com` inte `contoso.` tillåtet.

- Undervägar är inte underförstådda.

  Exempelvis `contoso.com` ingår inte `contoso.com/a` .

- Jokertecken (*) tillåts i följande scenarier:

  - Ett vänster jokertecken måste följas av en punkt för att ange en underdomän.

    Är till exempel `*.contoso.com` tillåtet, `*contoso.com` är inte tillåtet.

  - Ett höger jokertecken måste följa ett snedstreck (/) om du vill ange en sökväg.

    Till exempel är `contoso.com/*` tillåtet eller `contoso.com*` inte `contoso.com/ab*` tillåtet.

  - Alla undervägar kan inte underförstådas med ett rätt jokertecken.

    Exempelvis `contoso.com/*` ingår inte `contoso.com/a` .

  - `*.com*` är ogiltig (inte en lösbar domän och att rätt jokertecken inte följer ett snedstreck).

  - Jokertecken tillåts inte i IP-adresser.

- Tecknet tilde (~) är tillgängligt i följande scenarier:

  - Ett vänster tilde-namn antyder en domän och alla underdomäner.

    Exempel: `~contoso.com` inkluderar `contoso.com` och `*.contoso.com` .

- URL-poster som innehåller protokoll (till exempel , eller ) kommer att `http://` `https://` `ftp://` misslyckas, eftersom URL-poster tillämpas på alla protokoll.

- Ett användarnamn eller lösenord stöds inte eller krävs inte.

- Citattecken (' eller ") är ogiltiga tecken.

- En URL bör innehålla alla omdirigeringar där det är möjligt.

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

- **Blockera matchas inte:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Scenario: Vänster jokertecken (underdomän)

**Post:**`*.contoso.com`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Tillåt ej matchad** och **Blockera ej matchad:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Scenario: Höger jokertecken högst upp i sökvägen

**Post:**`contoso.com/a/*`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Tillåt ej matchad** och **Blockera ej matchad:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Scenario: Vänster tilde

**Post:**`~contoso.com`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Tillåt ej matchad** och **Blockera ej matchad:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Scenario: Höger suffix för jokertecken

**Post:**`contoso.com/*`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Tillåt ej matchad** och **Blockera ej matchad**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Scenario: Vänster underdomän med jokertecken och höger suffix för jokertecken

**Post:**`*.contoso.com/*`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Tillåt ej matchad** och **Blockera ej matchad**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Scenario: Vänster och höger tilde

**Post:**`~contoso.com~`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Tillåt ej matchad** och **Blockera ej matchad:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Scenario: IP-adress

**Post:**`1.2.3.4`

- **Tillåt matchning** och **Blockeringsmatchning**: 1.2.3.4

- **Tillåt ej matchad** och **Blockera ej matchad:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-adress med rätt jokertecken

**Post:**`1.2.3.4/*`

- **Tillåt matchning** och **Blockeringsmatchning:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Exempel på ogiltiga poster

Följande poster är ogiltiga:

- **Värden som saknas eller är ogiltiga:**

  - contoso
  - \*CONTOSO.\*
  - \*.com
  - \*.pdf

- **Jokertecken på text eller utan avståndstecken:**

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
  - conto~so.com

- **Dubbla jokertecken**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Domänparsyntax för falska avsändarposter i listan Över tillåtna/blockerade klientorganisationen

Ett domänpar för en förfalskningsavsändare i innehavarlistan över tillåtna/blockerade avsändare har följande syntax: `<Spoofed user>, <Sending infrastructure>` .

- **Förfalskningsanvändare:** Det här värdet innefattar e-postadressen till den kapade  användaren som visas i rutan Från i e-postklienter. Den här adressen kallas även `5322.From` för adressen. Giltiga värden är:
  - En enskild e-postadress (till exempel chris@contoso.com).
  - En e-postdomän (till exempel contoso.com).
  - Jokertecknet (till exempel \* ).

- **Skicka infrastruktur:** Det här värdet anger källan till meddelanden från den kapade användaren. Giltiga värden är:
  - Domänen som finns i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress (till exempel fabrikam.com).
  - Om käll-IP-adressen inte har någon PTR-post identifieras den avsändande infrastrukturen som \<source IP\> /24 (till exempel 192.168.100.100/24).

Här är några exempel på giltiga domänpar för att identifiera förfalskningsavsändare:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

Det maximala antalet falska avsändarposter är 1 000. 

Genom att lägga till ett domänpar tillåts *eller* blockeras bara kombinationen av den förfalskningsanvändaren *och* avsändarinfrastrukturen. E-post från förfalskningsanvändare från någon källa tillåts inte heller e-post från den avsändande infrastrukturkällan för någon förfalskningsanvändare. 

Du kan till exempel lägga till en tillåt-post för följande domänpar:

- **Domän:** gmail.com
- **Infrastruktur:** tms.mx.com

Endast meddelanden från den *domänen och* sändning av infrastrukturpar tillåts förfalskning. Andra avsändare som försöker kapa gmail.com-post är inte tillåtna. Meddelanden från avsändare i andra domäner med ursprung i tms.mx.com kontrolleras med förfalskningsinformation.
