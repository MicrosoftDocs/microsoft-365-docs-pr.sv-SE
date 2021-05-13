---
title: Konfigurera och validera undantag för Microsoft Defender för Slutpunkt i Linux
description: Tillhandahålla och validera undantag för Microsoft Defender för Endpoint på Linux. Undantag kan anges för filer, mappar och processer.
keywords: microsoft, defender, Microsoft Defender för Endpoint, linux, undantag, skanningar, antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bd506caa041af2585778fb3ecd7a40562463b17e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346420"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>Konfigurera och validera undantag för Microsoft Defender för Slutpunkt i Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Den här artikeln innehåller information om hur du definierar undantag som gäller för sökning på begäran, skydd och övervakning i realtid.

> [!IMPORTANT]
> Undantag som beskrivs i den här artikeln gäller inte för andra Defender för Endpoint på Linux-funktioner, inklusive identifiering och åtgärd på slutpunkt (Identifiering och åtgärd på slutpunkt). Filer som du undantar med de metoder som beskrivs i den här artikeln kan fortfarande utlösa Identifiering och åtgärd på slutpunkt aviseringar och andra identifieringar.

Du kan utesluta vissa filer, mappar, processer och process öppna filer från Defender för Slutpunkt på Linux-genomsökningar.

Undantag kan vara bra för att undvika felaktiga identifieringar av filer eller programvara som är unika eller anpassade för din organisation. De kan också vara användbara för att minska prestandaproblem som orsakas av Defender för Endpoint på Linux.

> [!WARNING]
> När du definierar undantag sänks skyddet som erbjuds av Defender för Endpoint på Linux. Du bör alltid utvärdera riskerna som är associerade med att implementera undantag och du bör endast utesluta filer som du är säker på inte är skadliga.

## <a name="supported-exclusion-types"></a>Undantagstyper som stöds

I följande tabell visas de undantagstyper som stöds av Defender för Slutpunkt på Linux.

Exkludering | Definition | Exempel
---|---|---
Filnamnstillägg | Alla filer med tillägget, var som helst på enheten | `.test`
Fil | En specifik fil som identifieras med den fullständiga sökvägen | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
Mapp | Alla filer under den angivna mappen (rekursivt) | `/var/log/`<br/>`/var/*/`
Process | En specifik process (anges antingen med den fullständiga sökvägen eller filnamnet) och alla filer som öppnas av den | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> Sökvägarna ovan måste vara hårda länkar, inte symboliska länkar, för att uteslutas. Du kan kontrollera om en sökväg är en symbolisk länk genom att köra `file <path-name>` .

Undantag för filer, mappar och processer stöder följande jokertecken:

Jokertecken | Beskrivning | Exempel | Matchningar | Matchar inte
---|---|---|---|---
\* |    Matchar valbara antal tecken inklusive inga (observera att när det här jokertecknet används inuti en sökväg kommer det bara att ersätta en mapp) | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
? | Matchar ett enstaka tecken | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>Så här konfigurerar du listan med undantag

### <a name="from-the-management-console"></a>Från hanteringskonsolen

Mer information om hur du konfigurerar undantag från Gör en klient, en ansible eller en annan hanteringskonsol finns i Ange inställningar för [Defender för slutpunkt i Linux.](linux-preferences.md)

### <a name="from-the-command-line"></a>Från kommandoraden

Kör följande kommando för att se tillgängliga växlar för hantering av undantag:

```bash
mdatp exclusion
```

> [!TIP]
> När du konfigurerar undantag med jokertecken måste du omge parametern med dubbla citattecken för att förhindra globbing.

Exempel:

- Lägga till ett undantag för ett filnamnstillägg:

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- Lägga till ett undantag för en fil:

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- Lägga till ett undantag för en mapp:

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- Lägga till ett undantag för en mapp med ett jokertecken i den:

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > Detta exkluderar endast sökvägar en nivå under */var/*, men inte mappar som är djupare kapslade; exempel: */var/this-subfolder/but-not-this-subfolder*.
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > Detta exkluderar alla sökvägar vars överordnade är */var/*; till exempel */var/this-subfolder/and-this-subfolder-as-well*.

    ```Output
    Folder exclusion configured successfully
    ```

- Lägg till ett undantag för en process:

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Validera undantagslistor med EICAR-testfilen

Du kan verifiera att undantagslistorna fungerar genom att hämta `curl` en testfil.

I följande Bash-kodstycke `test.txt` ersätter du med en fil som överensstämmer med dina undantagsregler. Om du till exempel har utelämnat `.testing` tillägget ersätter du `test.txt` med `test.testing` . Om du testar en sökväg bör du kontrollera att du kör kommandot inom den sökvägen.

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Om Defender för Slutpunkt på Linux rapporterar skadlig programvara fungerar regeln inte. Om det inte finns någon rapport om skadlig programvara, och den hämtade filen finns, fungerar undantaget. Du kan öppna filen för att bekräfta att innehållet är detsamma som det som beskrivs på [EICAR-testfilens webbplats](http://2016.eicar.org/86-0-Intended-use.html).

Om du inte har tillgång till Internet kan du skapa en egen EICAR-testfil. Skriv EICAR-strängen till en ny textfil med följande Bash-kommando:

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

Du kan också kopiera strängen till en tom textfil och försöka spara den med filnamnet eller i mappen som du försöker utelämna.

## <a name="allow-threats"></a>Tillåt hot

Förutom att utesluta att visst innehåll genomsöks kan du också konfigurera produkten så att den inte identifierar vissa klasser av hot (identifieras med hotnamnet). Var försiktig när du använder den här funktionen eftersom den kan lämna enheten oskyddad.

Kör följande kommando för att lägga till ett namn för hot i listan över tillåtna hot:

```bash
mdatp threat allowed add --name [threat-name]
```

Hotnamnet som associeras med en identifiering på din enhet kan erhållas med följande kommando:

```bash
mdatp threat list
```

Om du till exempel vill lägga `EICAR-Test-File (not a virus)` till (hotnamnet som är associerat med EICAR-identifieringen) i listan över tillåtna, kör du följande kommando:

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
