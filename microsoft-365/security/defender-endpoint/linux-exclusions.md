---
title: Konfigurera och validera undantag för Microsoft Defender ATP för Linux
description: Tillhandahålla och validera undantag för Microsoft Defender ATP för Linux. Undantag kan anges för filer, mappar och processer.
keywords: microsoft, defender, atp, linux, undantag, skanningar, antivirus
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
ms.openlocfilehash: fbc8fe7ef6f9af86debdeb0826865c88e86b2c6a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688195"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="a5a74-105">Konfigurera och validera undantag för Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="a5a74-105">Configure and validate exclusions for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a5a74-106">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="a5a74-106">**Applies to:**</span></span>
- [<span data-ttu-id="a5a74-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="a5a74-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a5a74-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a5a74-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a5a74-109">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="a5a74-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a5a74-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="a5a74-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a5a74-111">Den här artikeln innehåller information om hur du definierar undantag som gäller för sökning på begäran, skydd och övervakning i realtid.</span><span class="sxs-lookup"><span data-stu-id="a5a74-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5a74-112">Undantagen som beskrivs i den här artikeln gäller inte för andra Defender för Endpoint för Linux-funktioner, inklusive slutpunktsidentifiering och svar (EDR).</span><span class="sxs-lookup"><span data-stu-id="a5a74-112">The exclusions described in this article don't apply to other Defender for Endpoint for Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="a5a74-113">Filer som du undantar med hjälp av metoderna som beskrivs i den här artikeln kan fortfarande utlösa EDR-aviseringar och andra identifieringar.</span><span class="sxs-lookup"><span data-stu-id="a5a74-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="a5a74-114">Du kan utesluta vissa filer, mappar, processer och process öppna filer från Defender för Endpoint för Linux-genomsökningar.</span><span class="sxs-lookup"><span data-stu-id="a5a74-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Linux scans.</span></span>

<span data-ttu-id="a5a74-115">Undantag kan vara bra för att undvika felaktiga identifieringar av filer eller programvara som är unika eller anpassade för din organisation.</span><span class="sxs-lookup"><span data-stu-id="a5a74-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="a5a74-116">De kan också vara användbara för att minska prestandaproblem som orsakas av Defender för Endpoint för Linux.</span><span class="sxs-lookup"><span data-stu-id="a5a74-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="a5a74-117">När du definierar undantag sänks skyddet som erbjuds av Defender för Endpoint för Linux.</span><span class="sxs-lookup"><span data-stu-id="a5a74-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Linux.</span></span> <span data-ttu-id="a5a74-118">Du bör alltid utvärdera riskerna som är associerade med att implementera undantag och du bör endast utesluta filer som du är säker på inte är skadliga.</span><span class="sxs-lookup"><span data-stu-id="a5a74-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="a5a74-119">Undantagstyper som stöds</span><span class="sxs-lookup"><span data-stu-id="a5a74-119">Supported exclusion types</span></span>

<span data-ttu-id="a5a74-120">I följande tabell visas de undantagstyper som stöds av Defender för Endpoint för Linux.</span><span class="sxs-lookup"><span data-stu-id="a5a74-120">The follow table shows the exclusion types supported by Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="a5a74-121">Exkludering</span><span class="sxs-lookup"><span data-stu-id="a5a74-121">Exclusion</span></span> | <span data-ttu-id="a5a74-122">Definition</span><span class="sxs-lookup"><span data-stu-id="a5a74-122">Definition</span></span> | <span data-ttu-id="a5a74-123">Exempel</span><span class="sxs-lookup"><span data-stu-id="a5a74-123">Examples</span></span>
---|---|---
<span data-ttu-id="a5a74-124">Filnamnstillägg</span><span class="sxs-lookup"><span data-stu-id="a5a74-124">File extension</span></span> | <span data-ttu-id="a5a74-125">Alla filer med tillägget, var som helst på enheten</span><span class="sxs-lookup"><span data-stu-id="a5a74-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="a5a74-126">Fil</span><span class="sxs-lookup"><span data-stu-id="a5a74-126">File</span></span> | <span data-ttu-id="a5a74-127">En specifik fil som identifieras med den fullständiga sökvägen</span><span class="sxs-lookup"><span data-stu-id="a5a74-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="a5a74-128">Mapp</span><span class="sxs-lookup"><span data-stu-id="a5a74-128">Folder</span></span> | <span data-ttu-id="a5a74-129">Alla filer under den angivna mappen (rekursivt)</span><span class="sxs-lookup"><span data-stu-id="a5a74-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="a5a74-130">Process</span><span class="sxs-lookup"><span data-stu-id="a5a74-130">Process</span></span> | <span data-ttu-id="a5a74-131">En specifik process (anges antingen med den fullständiga sökvägen eller filnamnet) och alla filer som öppnas av den</span><span class="sxs-lookup"><span data-stu-id="a5a74-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="a5a74-132">Sökvägarna ovan måste vara hårda länkar, inte symboliska länkar, för att uteslutas.</span><span class="sxs-lookup"><span data-stu-id="a5a74-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="a5a74-133">Du kan kontrollera om en sökväg är en symbolisk länk genom att köra `file <path-name>` .</span><span class="sxs-lookup"><span data-stu-id="a5a74-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="a5a74-134">Undantag för filer, mappar och processer stöder följande jokertecken:</span><span class="sxs-lookup"><span data-stu-id="a5a74-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="a5a74-135">Jokertecken</span><span class="sxs-lookup"><span data-stu-id="a5a74-135">Wildcard</span></span> | <span data-ttu-id="a5a74-136">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a5a74-136">Description</span></span> | <span data-ttu-id="a5a74-137">Exempel</span><span class="sxs-lookup"><span data-stu-id="a5a74-137">Example</span></span> | <span data-ttu-id="a5a74-138">Matchningar</span><span class="sxs-lookup"><span data-stu-id="a5a74-138">Matches</span></span> | <span data-ttu-id="a5a74-139">Matchar inte</span><span class="sxs-lookup"><span data-stu-id="a5a74-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="a5a74-140">Matchar valbara antal tecken inklusive inga (observera att när det här jokertecknet används inuti en sökväg kommer det bara att ersätta en mapp)</span><span class="sxs-lookup"><span data-stu-id="a5a74-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="a5a74-141">?</span><span class="sxs-lookup"><span data-stu-id="a5a74-141">?</span></span> | <span data-ttu-id="a5a74-142">Matchar ett enstaka tecken</span><span class="sxs-lookup"><span data-stu-id="a5a74-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="a5a74-143">Så här konfigurerar du listan med undantag</span><span class="sxs-lookup"><span data-stu-id="a5a74-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="a5a74-144">Från hanteringskonsolen</span><span class="sxs-lookup"><span data-stu-id="a5a74-144">From the management console</span></span>

<span data-ttu-id="a5a74-145">Mer information om hur du konfigurerar undantag från Gör en klient, en ansible eller en annan hanteringskonsol finns i Ange inställningar för [Defender för Slutpunkt för Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="a5a74-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="a5a74-146">Från kommandoraden</span><span class="sxs-lookup"><span data-stu-id="a5a74-146">From the command line</span></span>

<span data-ttu-id="a5a74-147">Kör följande kommando för att se tillgängliga växlar för hantering av undantag:</span><span class="sxs-lookup"><span data-stu-id="a5a74-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="a5a74-148">När du konfigurerar undantag med jokertecken måste du omge parametern med dubbla citattecken för att förhindra globbing.</span><span class="sxs-lookup"><span data-stu-id="a5a74-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="a5a74-149">Exempel:</span><span class="sxs-lookup"><span data-stu-id="a5a74-149">Examples:</span></span>

- <span data-ttu-id="a5a74-150">Lägga till ett undantag för ett filnamnstillägg:</span><span class="sxs-lookup"><span data-stu-id="a5a74-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="a5a74-151">Lägga till ett undantag för en fil:</span><span class="sxs-lookup"><span data-stu-id="a5a74-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="a5a74-152">Lägga till ett undantag för en mapp:</span><span class="sxs-lookup"><span data-stu-id="a5a74-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="a5a74-153">Lägga till ett undantag för en mapp med ett jokertecken i den:</span><span class="sxs-lookup"><span data-stu-id="a5a74-153">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="a5a74-154">Detta exkluderar endast sökvägar en nivå under */var/*, men inte mappar som är djupare kapslade; exempel: */var/this-subfolder/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="a5a74-154">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="a5a74-155">Detta exkluderar alla sökvägar vars överordnade är */var/*; till exempel */var/this-subfolder/and-this-subfolder-as-well*.</span><span class="sxs-lookup"><span data-stu-id="a5a74-155">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="a5a74-156">Lägg till ett undantag för en process:</span><span class="sxs-lookup"><span data-stu-id="a5a74-156">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="a5a74-157">Validera undantagslistor med EICAR-testfilen</span><span class="sxs-lookup"><span data-stu-id="a5a74-157">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="a5a74-158">Du kan verifiera att undantagslistorna fungerar genom att hämta `curl` en testfil.</span><span class="sxs-lookup"><span data-stu-id="a5a74-158">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="a5a74-159">I följande Bash-kodstycke `test.txt` ersätter du med en fil som överensstämmer med dina undantagsregler.</span><span class="sxs-lookup"><span data-stu-id="a5a74-159">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="a5a74-160">Om du till exempel har utelämnat `.testing` tillägget ersätter du `test.txt` med `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="a5a74-160">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="a5a74-161">Om du testar en sökväg bör du kontrollera att du kör kommandot inom den sökvägen.</span><span class="sxs-lookup"><span data-stu-id="a5a74-161">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="a5a74-162">Om Defender för Slutpunkt för Linux rapporterar skadlig programvara fungerar inte regeln.</span><span class="sxs-lookup"><span data-stu-id="a5a74-162">If Defender for Endpoint for Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="a5a74-163">Om det inte finns någon rapport om skadlig programvara, och den hämtade filen finns, fungerar undantaget.</span><span class="sxs-lookup"><span data-stu-id="a5a74-163">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="a5a74-164">Du kan öppna filen för att bekräfta att innehållet är detsamma som det som beskrivs på [EICAR-testfilens webbplats](http://2016.eicar.org/86-0-Intended-use.html).</span><span class="sxs-lookup"><span data-stu-id="a5a74-164">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="a5a74-165">Om du inte har tillgång till Internet kan du skapa en egen EICAR-testfil.</span><span class="sxs-lookup"><span data-stu-id="a5a74-165">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="a5a74-166">Skriv EICAR-strängen till en ny textfil med följande Bash-kommando:</span><span class="sxs-lookup"><span data-stu-id="a5a74-166">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="a5a74-167">Du kan också kopiera strängen till en tom textfil och försöka spara den med filnamnet eller i mappen som du försöker utelämna.</span><span class="sxs-lookup"><span data-stu-id="a5a74-167">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="a5a74-168">Tillåt hot</span><span class="sxs-lookup"><span data-stu-id="a5a74-168">Allow threats</span></span>

<span data-ttu-id="a5a74-169">Förutom att utesluta att visst innehåll genomsöks kan du också konfigurera produkten så att den inte identifierar vissa klasser av hot (identifieras med hotnamnet).</span><span class="sxs-lookup"><span data-stu-id="a5a74-169">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="a5a74-170">Var försiktig när du använder den här funktionen eftersom den kan lämna enheten oskyddad.</span><span class="sxs-lookup"><span data-stu-id="a5a74-170">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="a5a74-171">Kör följande kommando för att lägga till ett namn för hot i listan över tillåtna hot:</span><span class="sxs-lookup"><span data-stu-id="a5a74-171">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="a5a74-172">Hotnamnet som associeras med en identifiering på din enhet kan erhållas med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="a5a74-172">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="a5a74-173">Om du till exempel vill lägga `EICAR-Test-File (not a virus)` till (hotnamnet som är associerat med EICAR-identifieringen) i listan över tillåtna, kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="a5a74-173">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
