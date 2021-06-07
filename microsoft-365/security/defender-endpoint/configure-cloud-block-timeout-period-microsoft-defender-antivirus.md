---
title: Konfigurera Microsoft Defender Antivirus tidsperiod för blockering av molntjänster
description: Du kan konfigurera hur länge Microsoft Defender Antivirus att blockera en fil från att köras medan du väntar på ett molnbestämande.
keywords: Microsoft Defender Antivirus, program mot skadlig programvara, säkerhet, defender, moln, timeout, blockering, punkt, sekunder
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789093"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="07aa3-104">Konfigurera tidsgräns för blockering i molnet</span><span class="sxs-lookup"><span data-stu-id="07aa3-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="07aa3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="07aa3-105">**Applies to:**</span></span>

- [<span data-ttu-id="07aa3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="07aa3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="07aa3-107">När Microsoft Defender Antivirus hittar en misstänkt fil kan den förhindra att filen körs när den frågar [Microsoft Defender Antivirus molntjänsten.](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="07aa3-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="07aa3-108">Standardtiden då filen [blockeras är](configure-block-at-first-sight-microsoft-defender-antivirus.md) 10 sekunder.</span><span class="sxs-lookup"><span data-stu-id="07aa3-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="07aa3-109">Om du är säkerhetsadministratör kan du ange mer tid att vänta innan filen får köras.</span><span class="sxs-lookup"><span data-stu-id="07aa3-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="07aa3-110">Om du utökar tidsgränsperioden för molnblockering får du tillräckligt med tid för att få ett ordentligt beslut Microsoft Defender Antivirus molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="07aa3-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="07aa3-111">Krav för att använda den utökade timeout för molnblockering</span><span class="sxs-lookup"><span data-stu-id="07aa3-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="07aa3-112">[Blocket vid första synen](configure-block-at-first-sight-microsoft-defender-antivirus.md) och förutsättningarna måste vara aktiverade innan du kan ange en längre tidsgräns.</span><span class="sxs-lookup"><span data-stu-id="07aa3-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="07aa3-113">Ange den utökade tidsgränsperioden med hjälp av Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="07aa3-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="07aa3-114">Du kan ange tidsgränssperioden för molnblockering med en [slutpunktssäkerhetsprincip i Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span><span class="sxs-lookup"><span data-stu-id="07aa3-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="07aa3-115">Gå till Endpoint Manager ( ) [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) och logga in.</span><span class="sxs-lookup"><span data-stu-id="07aa3-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="07aa3-116">Välj **Slutpunktssäkerhet** och välj **sedan** Antivirus under **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="07aa3-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="07aa3-117">Välj (eller skapa) en antivirusprincip.</span><span class="sxs-lookup"><span data-stu-id="07aa3-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="07aa3-118">Expandera **Molnskydd i** avsnittet **Konfigurationsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="07aa3-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="07aa3-119">Ange sedan mer tid i sekunder från 1 sekund till 50 sekunder i rutan Utökad **timeout** för Defender Cloud i sekunder.</span><span class="sxs-lookup"><span data-stu-id="07aa3-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="07aa3-120">Det du anger läggs till i standardinställningarna på 10 sekunder.</span><span class="sxs-lookup"><span data-stu-id="07aa3-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="07aa3-121">(Det här steget är valfritt) Gör eventuella andra ändringar i din antivirusprincip.</span><span class="sxs-lookup"><span data-stu-id="07aa3-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="07aa3-122">(Behöver du hjälp?</span><span class="sxs-lookup"><span data-stu-id="07aa3-122">(Need help?</span></span> <span data-ttu-id="07aa3-123">Se [Inställningar för Microsoft Defender Antivirus princip i Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span><span class="sxs-lookup"><span data-stu-id="07aa3-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="07aa3-124">Välj **Nästa** och slutför konfigurationen av principen.</span><span class="sxs-lookup"><span data-stu-id="07aa3-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="07aa3-125">Ange den utökade tidsgränsperioden med grupprincip</span><span class="sxs-lookup"><span data-stu-id="07aa3-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="07aa3-126">Du kan använda grupprinciper för att ange en utökad tidsgräns för molnkontroller.</span><span class="sxs-lookup"><span data-stu-id="07aa3-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="07aa3-127">Öppna konsolen Grupprinciphantering på datorn för [grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="07aa3-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="07aa3-128">Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="07aa3-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="07aa3-129">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering och** välj sedan **Administrativa mallar**.</span><span class="sxs-lookup"><span data-stu-id="07aa3-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="07aa3-130">Expandera trädet för att **Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="07aa3-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="07aa3-131">Dubbelklicka på Konfigurera **utökad molnkontroll och** kontrollera att alternativet är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="07aa3-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="07aa3-132">Ange extra tid för att förhindra att filen körs medan du väntar på att molnen ska fastställas i molnet.</span><span class="sxs-lookup"><span data-stu-id="07aa3-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="07aa3-133">Ange den extra tiden i sekunder från 1 sekund till 50 sekunder.</span><span class="sxs-lookup"><span data-stu-id="07aa3-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="07aa3-134">Det du anger läggs till i standardinställningarna på 10 sekunder.</span><span class="sxs-lookup"><span data-stu-id="07aa3-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="07aa3-135">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="07aa3-135">Select **OK**.</span></span>

 