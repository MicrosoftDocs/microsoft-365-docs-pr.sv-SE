---
title: Felsöka licensproblem för Microsoft Defender ATP för Mac
description: Felsöka licensproblem i Microsoft Defender ATP för Mac.
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: 645c3657bdd1540ac95b68460b4dff6d25627c2c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185937"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="cc601-104">Felsöka licensproblem för Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="cc601-104">Troubleshoot license issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cc601-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="cc601-105">**Applies to:**</span></span>

- [<span data-ttu-id="cc601-106">Microsoft Defender för Slutpunkt för Mac</span><span class="sxs-lookup"><span data-stu-id="cc601-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="cc601-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="cc601-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cc601-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc601-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cc601-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="cc601-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cc601-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="cc601-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="cc601-111">När du går igenom [Microsoft Defender](microsoft-defender-endpoint-mac.md) för Endpoint för Mac och testa [manuell](mac-install-manually.md) distribution eller använder PoC (Proof Of Concept) kan du få följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="cc601-111">While you are going through [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Bild på licensfel](images/no-license-found.png)

<span data-ttu-id="cc601-113">**Meddelande:**</span><span class="sxs-lookup"><span data-stu-id="cc601-113">**Message:**</span></span> 

<span data-ttu-id="cc601-114">Ingen licens hittades</span><span class="sxs-lookup"><span data-stu-id="cc601-114">No license found</span></span>

<span data-ttu-id="cc601-115">Det verkar som att din organisation inte har någon licens för Microsoft 365 Enterprise-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="cc601-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="cc601-116">Kontakta administratören om du behöver hjälp.</span><span class="sxs-lookup"><span data-stu-id="cc601-116">Contact your administrator for help.</span></span>

<span data-ttu-id="cc601-117">**Orsak:**</span><span class="sxs-lookup"><span data-stu-id="cc601-117">**Cause:**</span></span> 

<span data-ttu-id="cc601-118">Du har distribuerat och/eller installerat Microsoft Defender för slutpunkt för macOS-paketet ("Ladda ned installationspaket") men du kanske har kört konfigurationsskriptet ("Hämta registreringspaket").</span><span class="sxs-lookup"><span data-stu-id="cc601-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="cc601-119">**Lösning:**</span><span class="sxs-lookup"><span data-stu-id="cc601-119">**Solution:**</span></span>

<span data-ttu-id="cc601-120">Följ de MicrosoftDefenderATPOnboardingMacOs.py som beskrivs här: [Klientkonfiguration](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="cc601-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

