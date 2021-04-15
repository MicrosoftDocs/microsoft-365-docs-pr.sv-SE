---
title: Konfigurera hur användare kan interagera med Microsoft Defender AV
description: Konfigurera hur slutanvändare interagerar med Microsoft Defender AV, vilka meddelanden de ser och om de kan åsidosätta inställningar.
keywords: slutpunkt, användare, interaktion, meddelanden, nedlåst läge för användargränssnittet, huvudlöst läge, dölj gränssnitt
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: df9f87e725575bad2f36cf7b016d257e766e523b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765233"
---
# <a name="configure-end-user-interaction-with-microsoft-defender-antivirus"></a><span data-ttu-id="05bed-104">Konfigurera interaktion med slutanvändare med Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="05bed-104">Configure end-user interaction with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="05bed-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="05bed-105">**Applies to:**</span></span>

- [<span data-ttu-id="05bed-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="05bed-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="05bed-107">Du kan konfigurera hur användare av slutpunkter i nätverket kan interagera med Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="05bed-107">You can configure how users of the endpoints on your network can interact with Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="05bed-108">Det här gäller oavsett om de ser Microsoft Defender Antivirus-gränssnittet, vilka meddelanden de ser och om de kan åsidosätta grupprincipinställningar som distribuerats globalt lokalt.</span><span class="sxs-lookup"><span data-stu-id="05bed-108">This includes whether they see the Microsoft Defender Antivirus interface, what notifications they see, and if they can locally override globally-deployed Group Policy settings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="05bed-109">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="05bed-109">In this section</span></span>

<span data-ttu-id="05bed-110">Ämne</span><span class="sxs-lookup"><span data-stu-id="05bed-110">Topic</span></span> | <span data-ttu-id="05bed-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="05bed-111">Description</span></span> 
---|---
[<span data-ttu-id="05bed-112">Konfigurera meddelanden som visas på slutpunkter</span><span class="sxs-lookup"><span data-stu-id="05bed-112">Configure notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md) | <span data-ttu-id="05bed-113">Konfigurera och anpassa ytterligare meddelanden, anpassad text för meddelanden och meddelanden om omstarter för åtgärd</span><span class="sxs-lookup"><span data-stu-id="05bed-113">Configure and customize additional notifications, customized text for notifications, and notifications about reboots for remediation</span></span>
[<span data-ttu-id="05bed-114">Hindra användare från att se eller interagera med användargränssnittet i Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="05bed-114">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="05bed-115">Dölja användargränssnittet för användare</span><span class="sxs-lookup"><span data-stu-id="05bed-115">Hide the user interface from users</span></span>
[<span data-ttu-id="05bed-116">Hindra användare från att lokalt ändra principinställningar</span><span class="sxs-lookup"><span data-stu-id="05bed-116">Prevent users from locally modifying policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) | <span data-ttu-id="05bed-117">Hindra (eller tillåt) användare från att åsidosätta principinställningar för sina enskilda slutpunkter</span><span class="sxs-lookup"><span data-stu-id="05bed-117">Prevent (or allow) users from overriding policy settings on their individual endpoints</span></span>