---
title: Felsöka installationsproblem för Microsoft Defender ATP för Mac
description: Felsöka installationsproblem i Microsoft Defender ATP för Mac.
keywords: microsoft, defender, atp, mac, installera
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 60b50f3944a2cdd995b4877e22123018267ff044
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070274"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="9263c-104">Felsöka installationsproblem för Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="9263c-104">Troubleshoot installation issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9263c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9263c-105">**Applies to:**</span></span>

- [<span data-ttu-id="9263c-106">Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="9263c-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="9263c-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9263c-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9263c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9263c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9263c-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="9263c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9263c-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="9263c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a><span data-ttu-id="9263c-111">Installationen misslyckades</span><span class="sxs-lookup"><span data-stu-id="9263c-111">Installation failed</span></span>

<span data-ttu-id="9263c-112">För manuell installation står det "Ett fel inträffade under installationen" på sidan Sammanfattning i installationsguiden.</span><span class="sxs-lookup"><span data-stu-id="9263c-112">For manual installation, the Summary page of the installation wizard says, "An error occurred during installation.</span></span> <span data-ttu-id="9263c-113">Installationsprogrammet påträffade ett fel som orsakade att installationen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="9263c-113">The Installer encountered an error that caused the installation to fail.</span></span> <span data-ttu-id="9263c-114">Kontakta programvarutillverkaren för att få hjälp."</span><span class="sxs-lookup"><span data-stu-id="9263c-114">Contact the software manufacturer for assistance."</span></span> <span data-ttu-id="9263c-115">För MDM-distributioner visas det också som ett allmänt installationsfel.</span><span class="sxs-lookup"><span data-stu-id="9263c-115">For MDM deployments, it displays as a generic installation failure as well.</span></span>

<span data-ttu-id="9263c-116">Även om vi inte visar ett exakt fel för slutanvändaren så sparar vi en loggfil med installationsförloppet i `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="9263c-116">While we do not display an exact error to the end user, we keep a log file with installation progress in `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="9263c-117">Varje installationssession läggs till i den här loggfilen.</span><span class="sxs-lookup"><span data-stu-id="9263c-117">Each installation session appends to this log file.</span></span> <span data-ttu-id="9263c-118">Du kan endast `sed` använda följande för att mata ut den senaste installationen:</span><span class="sxs-lookup"><span data-stu-id="9263c-118">You can use `sed` to output the last installation session only:</span></span>

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

<span data-ttu-id="9263c-119">I det här exemplet föregås den faktiska orsaken av `[ERROR]` .</span><span class="sxs-lookup"><span data-stu-id="9263c-119">In this example, the actual reason is prefixed with `[ERROR]`.</span></span>
<span data-ttu-id="9263c-120">Installationen misslyckades eftersom det inte går att nedgradera mellan dessa versioner.</span><span class="sxs-lookup"><span data-stu-id="9263c-120">The installation failed because a downgrade between these versions is not supported.</span></span>

## <a name="mdatp-install-log-missing-or-not-updated"></a><span data-ttu-id="9263c-121">MDATP-installationslogg saknas eller har inte uppdaterats</span><span class="sxs-lookup"><span data-stu-id="9263c-121">MDATP install log missing or not updated</span></span>

<span data-ttu-id="9263c-122">I sällsynta fall lämnar installationen ingen spårning i filen /Library/Logs/Microsoft/mdatp/install.log.</span><span class="sxs-lookup"><span data-stu-id="9263c-122">In rare cases, installation leaves no trace in MDATP's /Library/Logs/Microsoft/mdatp/install.log file.</span></span>
<span data-ttu-id="9263c-123">Du kan kontrollera att en installation har hänt och analysera möjliga fel genom att fråga macOS-loggar (det här är användbart i MDM-distribution när det inte finns något klientgränssnitt).</span><span class="sxs-lookup"><span data-stu-id="9263c-123">You can verify that an installation happened and analyze possible errors by querying macOS logs (this is helpful in MDM deployment, when there is no client UI).</span></span> <span data-ttu-id="9263c-124">Vi rekommenderar att du använder ett smalt tidsfönster för att köra en fråga och att du filtrerar efter loggningsprocessens namn eftersom det kommer att finnas en stor mängd information.</span><span class="sxs-lookup"><span data-stu-id="9263c-124">We recommend that you use a narrow time window to run a query, and that you filter by the logging process name, as there will be a huge amount of information.</span></span>

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
