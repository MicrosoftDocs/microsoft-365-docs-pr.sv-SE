---
title: Identifiera och blockera potentiellt oönskade program med Microsoft Defender ATP för Mac
description: Identifiera och blockera potentiellt oönskade program (PUA) med Hjälp av Microsoft Defender ATP för Mac.
keywords: microsoft, defender, atp, mac, pua, pus
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
ms.openlocfilehash: d52b8db069a2e1988cee9c19656116bf49ad9d60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070281"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="3cb6b-104">Identifiera och blockera potentiellt oönskade program med Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="3cb6b-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3cb6b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3cb6b-105">**Applies to:**</span></span>
- [<span data-ttu-id="3cb6b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3cb6b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3cb6b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cb6b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3cb6b-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3cb6b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3cb6b-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="3cb6b-110">Skyddsfunktionen för potentiellt oönskade program (PUA) i Microsoft Defender för Endpoint för Mac kan identifiera och blockera PUA-filer på slutpunkter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint for Mac can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="3cb6b-111">Dessa program betraktas inte som virus, skadlig programvara eller andra typer av hot, men kan utföra åtgärder på slutpunkter som negativt påverkar deras prestanda eller användning.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="3cb6b-112">PUA kan också hänvisa till program som anses ha dåligt rykte.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="3cb6b-113">Dessa program kan öka risken för att nätverket smittas med skadlig programvara, orsaka att skadlig programvara blir svårare att identifiera och kan slösa PÅ IT-resurser i att rensa program.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="3cb6b-114">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="3cb6b-114">How it works</span></span>

<span data-ttu-id="3cb6b-115">Microsoft Defender för Endpoint för Mac kan identifiera och rapportera PUA-filer.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-115">Microsoft Defender for Endpoint for Mac can detect and report PUA files.</span></span> <span data-ttu-id="3cb6b-116">När PUA-filer konfigureras i blockeringsläge flyttas de till karantän.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="3cb6b-117">När en PUA hittas på en slutpunkt visar Microsoft Defender för slutpunkt för Mac ett meddelande för användaren, om inte meddelanden har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint for Mac presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="3cb6b-118">Hotnamnet innehåller ordet "Program".</span><span class="sxs-lookup"><span data-stu-id="3cb6b-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="3cb6b-119">Konfigurera PUA-skydd</span><span class="sxs-lookup"><span data-stu-id="3cb6b-119">Configure PUA protection</span></span>

<span data-ttu-id="3cb6b-120">PUA-skydd i Microsoft Defender för Slutpunkt för Mac kan konfigureras på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="3cb6b-120">PUA protection in Microsoft Defender for Endpoint for Mac can be configured in one of the following ways:</span></span>

- <span data-ttu-id="3cb6b-121">**Av**: PUA-skydd är inaktiverat.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="3cb6b-122">**Granskning:** PUA-filer rapporteras i produktloggarna, men inte i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="3cb6b-123">Inget meddelande visas för användaren och ingen åtgärd vidtas av produkten.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="3cb6b-124">**Blockering:** PUA-filer rapporteras i produktloggarna och i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="3cb6b-125">Användaren får ett meddelande och en åtgärd vidtas av produkten.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="3cb6b-126">Som standard konfigureras PUA-skydd i **granskningsläge.**</span><span class="sxs-lookup"><span data-stu-id="3cb6b-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="3cb6b-127">Du kan konfigurera hur PUA-filer hanteras från kommandoraden eller från hanteringskonsolen.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="3cb6b-128">Använd kommandoradsverktyget för att konfigurera PUA-skydd:</span><span class="sxs-lookup"><span data-stu-id="3cb6b-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="3cb6b-129">I terminalen kör du följande kommando för att konfigurera PUA-skydd:</span><span class="sxs-lookup"><span data-stu-id="3cb6b-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="3cb6b-130">Använd hanteringskonsolen för att konfigurera PUA-skydd:</span><span class="sxs-lookup"><span data-stu-id="3cb6b-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="3cb6b-131">I ditt företag kan du konfigurera PUA-skydd från en hanteringskonsol, till exempel JAMF eller Intune, på ungefär samma sätt som andra produktinställningar konfigureras.</span><span class="sxs-lookup"><span data-stu-id="3cb6b-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="3cb6b-132">Mer information finns i avsnittet Inställningar [för hottyp](mac-preferences.md#threat-type-settings) i avsnittet Ange [inställningar för Microsoft Defender för slutpunkt för Mac.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="3cb6b-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3cb6b-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3cb6b-133">Related topics</span></span>

- [<span data-ttu-id="3cb6b-134">Ange inställningar för Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="3cb6b-134">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>](mac-preferences.md)