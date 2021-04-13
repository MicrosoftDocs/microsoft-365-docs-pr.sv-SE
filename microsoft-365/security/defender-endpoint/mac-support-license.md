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
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689119"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="c43fc-104">Felsöka licensproblem för Microsoft Defender för slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="c43fc-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c43fc-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c43fc-105">**Applies to:**</span></span>

- [<span data-ttu-id="c43fc-106">Microsoft Defender för Slutpunkt på macOS</span><span class="sxs-lookup"><span data-stu-id="c43fc-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="c43fc-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c43fc-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c43fc-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c43fc-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c43fc-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c43fc-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c43fc-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c43fc-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c43fc-111">När du går igenom Microsoft Defender för Slutpunkt på [macOS](microsoft-defender-endpoint-mac.md) och [testa manuell](mac-install-manually.md) distribution eller ett PoC (Proof Of Concept) kan du få följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="c43fc-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Bild på licensfel](images/no-license-found.png)

<span data-ttu-id="c43fc-113&quot;>**Meddelande:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c43fc-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;c43fc-114&quot;>Ingen licens hittades</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c43fc-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;c43fc-115&quot;>Det verkar som att din organisation inte har någon licens för Microsoft 365 Enterprise-prenumeration.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c43fc-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;c43fc-116&quot;>Kontakta administratören om du behöver hjälp.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c43fc-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;c43fc-117&quot;>**Orsak:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;c43fc-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;c43fc-118&quot;>Du har distribuerat och/eller installerat Microsoft Defender för slutpunkt på macOS-paket (&quot;Ladda ned installationspaket") men du kanske har kört konfigurationsskriptet ("Hämta onboarding package").</span><span class="sxs-lookup"><span data-stu-id="c43fc-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="c43fc-119">**Lösning:**</span><span class="sxs-lookup"><span data-stu-id="c43fc-119">**Solution:**</span></span>

<span data-ttu-id="c43fc-120">Följ de MicrosoftDefenderATPOnboardingMacOs.py som beskrivs här: [Klientkonfiguration](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="c43fc-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

