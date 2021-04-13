---
title: Konfigurera timeout-perioden för blockering av moln i Microsoft Defender Antivirus
description: Du kan konfigurera hur länge microsoft Defender Antivirus blockerar en fil från att köras medan du väntar på att molnen ska fastställas i molnet.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, moln, tidsgräns, blockering, punkt, sekunder
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691066"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="08b8c-104">Konfigurera tidsgränsen för molnblockering</span><span class="sxs-lookup"><span data-stu-id="08b8c-104">Configure the cloud block timeout period</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="08b8c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="08b8c-105">**Applies to:**</span></span>

- [<span data-ttu-id="08b8c-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="08b8c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="08b8c-107">När Microsoft Defender Antivirus hittar en misstänkt fil kan den förhindra att filen körs när den frågar [microsoft Defender Antivirus-molntjänsten.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="08b8c-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="08b8c-108">Standardtiden då filen [blockeras är](configure-block-at-first-sight-microsoft-defender-antivirus.md) 10 sekunder.</span><span class="sxs-lookup"><span data-stu-id="08b8c-108">The default period that the file will be [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="08b8c-109">Du kan ange ytterligare en tid att vänta innan filen får köras.</span><span class="sxs-lookup"><span data-stu-id="08b8c-109">You can specify an additional period of time to wait before the file is allowed to run.</span></span> <span data-ttu-id="08b8c-110">På så sätt får du tillräckligt med tid för att få ett ordentligt avgörande från molntjänsten Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="08b8c-110">This can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="08b8c-111">Krav för att använda den utökade timeout för molnblockering</span><span class="sxs-lookup"><span data-stu-id="08b8c-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="08b8c-112">[Blocket vid första synen](configure-block-at-first-sight-microsoft-defender-antivirus.md) och förutsättningarna måste vara aktiverade innan du kan ange en längre tidsgräns.</span><span class="sxs-lookup"><span data-stu-id="08b8c-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period"></a><span data-ttu-id="08b8c-113">Ange den utökade tidsgränsperioden</span><span class="sxs-lookup"><span data-stu-id="08b8c-113">Specify the extended timeout period</span></span>

<span data-ttu-id="08b8c-114">Du kan använda grupprinciper för att ange en utökad tidsgräns för molnkontroller.</span><span class="sxs-lookup"><span data-stu-id="08b8c-114">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="08b8c-115">På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="08b8c-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="08b8c-116">I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="08b8c-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="08b8c-117">Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus > MpEngine**</span><span class="sxs-lookup"><span data-stu-id="08b8c-117">Expand the tree to **Windows components > Microsoft Defender Antivirus > MpEngine**</span></span>

4. <span data-ttu-id="08b8c-118">Dubbelklicka på Konfigurera **utökad molnkontroll och** kontrollera att alternativet är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="08b8c-118">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> <span data-ttu-id="08b8c-119">Ange ytterligare tid för att förhindra att filen körs medan du väntar på ett molnbestämande.</span><span class="sxs-lookup"><span data-stu-id="08b8c-119">Specify the additional amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="08b8c-120">Du kan ange den ytterligare tiden i sekunder från 1 sekund till 50 sekunder.</span><span class="sxs-lookup"><span data-stu-id="08b8c-120">You can specify the additional time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="08b8c-121">Den här gången läggs till i standardinställningen på 10 sekunder.</span><span class="sxs-lookup"><span data-stu-id="08b8c-121">This time will be added to the default 10 seconds.</span></span>

5. <span data-ttu-id="08b8c-122">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="08b8c-122">Click **OK**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="08b8c-123">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="08b8c-123">Related topics</span></span>

- [<span data-ttu-id="08b8c-124">Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="08b8c-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="08b8c-125">Använd nästa generations antivirusprogram genom moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="08b8c-125">Use next-generation antivirus technologies through cloud-delivered protection</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="08b8c-126">Konfigurera blocket vid första synen</span><span class="sxs-lookup"><span data-stu-id="08b8c-126">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="08b8c-127">Aktivera moln levererat skydd</span><span class="sxs-lookup"><span data-stu-id="08b8c-127">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)