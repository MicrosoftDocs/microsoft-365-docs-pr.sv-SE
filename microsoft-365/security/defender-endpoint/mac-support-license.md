---
title: Felsöka licensproblem för Microsoft Defender för slutpunkt på Mac
description: Felsöka licensproblem i Microsoft Defender för slutpunkt på Mac.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, prestanda
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
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244986"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="3dca7-104">Felsöka licensproblem för Microsoft Defender för slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="3dca7-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3dca7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3dca7-105">**Applies to:**</span></span>

- [<span data-ttu-id="3dca7-106">Microsoft Defender för Endpoint för macOS</span><span class="sxs-lookup"><span data-stu-id="3dca7-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="3dca7-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3dca7-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3dca7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3dca7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3dca7-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3dca7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3dca7-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3dca7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="3dca7-111">När du går igenom Microsoft Defender för Slutpunkt på [macOS](microsoft-defender-endpoint-mac.md) och [testa manuell](mac-install-manually.md) distribution eller ett PoC (Proof Of Concept) kan du få följande felmeddelande:</span><span class="sxs-lookup"><span data-stu-id="3dca7-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Bild på licensfel](images/no-license-found.png)

<span data-ttu-id="3dca7-113&quot;>**Meddelande:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3dca7-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;3dca7-114&quot;>Ingen licens hittades</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3dca7-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;3dca7-115&quot;>Det verkar som att din organisation inte har någon licens för Microsoft 365 Enterprise prenumeration.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3dca7-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;3dca7-116&quot;>Kontakta administratören om du behöver hjälp.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3dca7-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;3dca7-117&quot;>**Orsak:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3dca7-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;3dca7-118&quot;>Du har distribuerat och/eller installerat Microsoft Defender för Slutpunkt för macOS-paketet (&quot;Ladda ned installationspaket"), men du kanske har kört konfigurationsskriptet ("Hämta onboarding-paket") eller så har du inte tilldelat någon licens till användaren.</span><span class="sxs-lookup"><span data-stu-id="3dca7-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package"), but you might have run the configuration script ("Download onboarding package"), or you have not assigned a license to the user.</span></span>

<span data-ttu-id="3dca7-119">**Lösning:**</span><span class="sxs-lookup"><span data-stu-id="3dca7-119">**Solution:**</span></span>

<span data-ttu-id="3dca7-120">Följ de MicrosoftDefenderATPOnboardingMacOs.py som beskrivs här: [Klientkonfiguration](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="3dca7-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>
