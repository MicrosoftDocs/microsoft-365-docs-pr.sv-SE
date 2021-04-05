---
title: Identifiera och blockera potentiellt oönskade program med Microsoft Defender ATP för Linux
description: Identifiera och blockera potentiellt oönskade program (PUA) med Microsoft Defender ATP för Linux.
keywords: microsoft, defender, atp, linux, pua, pus
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
ms.openlocfilehash: a6f2e2057ca78cb0e1114ed86829cd931dc1cd2b
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587557"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="6c52a-104">Identifiera och blockera potentiellt oönskade program med Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="6c52a-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6c52a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6c52a-105">**Applies to:**</span></span>
- [<span data-ttu-id="6c52a-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6c52a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6c52a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c52a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6c52a-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6c52a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6c52a-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6c52a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6c52a-110">Skyddsfunktionen för potentiellt oönskade program (PUA) i Defender för Endpoint för Linux kan identifiera och blockera PUA-filer på slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="6c52a-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint for Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="6c52a-111">Dessa program betraktas inte som virus, skadlig programvara eller andra typer av hot, men kan utföra åtgärder på slutpunkter som negativt påverkar deras prestanda eller användning.</span><span class="sxs-lookup"><span data-stu-id="6c52a-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="6c52a-112">PUA kan också hänvisa till program som anses ha dåligt rykte.</span><span class="sxs-lookup"><span data-stu-id="6c52a-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="6c52a-113">Dessa program kan öka risken för att nätverket smittas med skadlig programvara, orsaka att skadlig programvara blir svårare att identifiera och kan slösa PÅ IT-resurser i att rensa program.</span><span class="sxs-lookup"><span data-stu-id="6c52a-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="6c52a-114">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="6c52a-114">How it works</span></span>

<span data-ttu-id="6c52a-115">Defender för Endpoint för Linux kan identifiera och rapportera PUA-filer.</span><span class="sxs-lookup"><span data-stu-id="6c52a-115">Defender for Endpoint for Linux can detect and report PUA files.</span></span> <span data-ttu-id="6c52a-116">När PUA-filer konfigureras i blockeringsläge flyttas de till karantän.</span><span class="sxs-lookup"><span data-stu-id="6c52a-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="6c52a-117">När en PUA upptäcks på en slutpunkt behåller Defender för Endpoint för Linux ett register över smittan i hothistoriken.</span><span class="sxs-lookup"><span data-stu-id="6c52a-117">When a PUA is detected on an endpoint, Defender for Endpoint for Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="6c52a-118">Historiken kan visualiseras från Microsoft Defender Säkerhetscenter-portalen eller `mdatp` kommandoradsverktyget.</span><span class="sxs-lookup"><span data-stu-id="6c52a-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="6c52a-119">Hotnamnet innehåller ordet "Program".</span><span class="sxs-lookup"><span data-stu-id="6c52a-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="6c52a-120">Konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="6c52a-120">Configure PUA protection</span></span>

<span data-ttu-id="6c52a-121">PUA-skydd i Defender för Slutpunkt för Linux kan konfigureras på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="6c52a-121">PUA protection in Defender for Endpoint for Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="6c52a-122">**Av**: PUA-skydd är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="6c52a-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="6c52a-123">**Granskning:** PUA-filer rapporteras i produktloggarna, men inte i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="6c52a-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="6c52a-124">Ingen information om smittan lagras i hothistoriken och ingen åtgärd vidtas av produkten.</span><span class="sxs-lookup"><span data-stu-id="6c52a-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="6c52a-125">**Blockering:** PUA-filer rapporteras i produktloggarna och i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="6c52a-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="6c52a-126">En inspelning av smittan lagras i produktens hothistorik och åtgärder vidtas.</span><span class="sxs-lookup"><span data-stu-id="6c52a-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="6c52a-127">Som standard konfigureras PUA-skydd i **granskningsläge.**</span><span class="sxs-lookup"><span data-stu-id="6c52a-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="6c52a-128">Du kan konfigurera hur PUA-filer hanteras från kommandoraden eller från hanteringskonsolen.</span><span class="sxs-lookup"><span data-stu-id="6c52a-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="6c52a-129">Använd kommandoradsverktyget för att konfigurera PUA-skydd:</span><span class="sxs-lookup"><span data-stu-id="6c52a-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="6c52a-130">I terminalen kör du följande kommando för att konfigurera PUA-skydd:</span><span class="sxs-lookup"><span data-stu-id="6c52a-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="6c52a-131">Använd hanteringskonsolen för att konfigurera PUA-skydd:</span><span class="sxs-lookup"><span data-stu-id="6c52a-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="6c52a-132">I ditt företag kan du konfigurera PUA-skydd från en hanteringskonsol, till exempel a6 eller Ansible, på ungefär samma sätt som andra produktinställningar konfigureras.</span><span class="sxs-lookup"><span data-stu-id="6c52a-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="6c52a-133">Mer information finns i avsnittet Inställningar [för hottyp](linux-preferences.md#threat-type-settings) i artikeln [Ange inställningar för Defender för slutpunkt för Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="6c52a-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint for Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6c52a-134">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="6c52a-134">Related articles</span></span>

- [<span data-ttu-id="6c52a-135">Ange inställningar för Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="6c52a-135">Set preferences for Defender for Endpoint for Linux</span></span>](linux-preferences.md)
