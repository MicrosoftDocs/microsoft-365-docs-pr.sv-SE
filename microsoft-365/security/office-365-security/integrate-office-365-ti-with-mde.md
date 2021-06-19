---
title: Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Endpoint
f1.keywords:
- NOCSH
keywords: integrera, Microsoft Defender, Microsoft Defender för Slutpunkt
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Använd Microsoft Defender för Office 365 microsoft Defender för slutpunkt om du vill få mer detaljerad information om hot mot dina enheter och e-postinnehåll.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028887"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="86305-104">Använda Microsoft Defender för Office 365 tillsammans med Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="86305-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="86305-105">[Microsoft Defender för Office 365](defender-for-office-365.md) kan konfigureras för att fungera med [Microsoft Defender för slutpunkt.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="86305-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="86305-106">Genom att integrera Microsoft Defender för Office 365 med Microsoft Defender för Endpoint kan du hjälpa dina säkerhetsåtgärder att övervaka teamet och vidta åtgärder snabbt om användarnas enheter är på risk.</span><span class="sxs-lookup"><span data-stu-id="86305-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="86305-107">När integration har aktiverats kan teamet för säkerhetsåtgärder till exempel se de enheter som eventuellt påverkas av ett upptäckt e-postmeddelande, samt hur många aviseringar som nyligen har genererats för dessa enheter i Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="86305-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="86305-108">I följande bild visas hur fliken **Enheter ser** ut när du har aktiverat Microsoft Defender för slutpunktsintegrering:</span><span class="sxs-lookup"><span data-stu-id="86305-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![När Microsoft Defender för slutpunkt är aktiverat visas en lista över enheter med aviseringar.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="86305-110">I det här exemplet kan du se att mottagarna av det identifierade e-postmeddelandet har fyra enheter och en har en avisering.</span><span class="sxs-lookup"><span data-stu-id="86305-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="86305-111">Om du klickar på länken för en enhet öppnas sidan [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (tidigare Microsoft Defender Säkerhetscenter).</span><span class="sxs-lookup"><span data-stu-id="86305-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="86305-112">Den Microsoft 365 Defender portalen ersätter Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="86305-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="86305-113">Se [Microsoft Defender för Slutpunkt i Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="86305-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="86305-114">Krav</span><span class="sxs-lookup"><span data-stu-id="86305-114">Requirements</span></span>

- <span data-ttu-id="86305-115">Din organisation måste ha Microsoft Defender för Office 365 (eller Office 365 E5) och Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="86305-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="86305-116">Du måste vara global administratör eller ha en säkerhetsadministratörsroll (till exempel säkerhetsadministratör) som tilldelats Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86305-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="86305-117">(Se [Behörigheter i Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="86305-117">(See [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="86305-118">Du måste ha tillgång [till Utforskaren (eller identifieringar i realtid).](threat-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="86305-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="86305-119">Integrera Microsoft Defender för Office 365 med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="86305-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="86305-120">Integrering av Microsoft Defender för Office 365 med Microsoft Defender för slutpunkt konfigureras i både Defender för Slutpunkt och Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="86305-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="86305-121">Som global administratör eller säkerhetsadministratör går du till [https://security.microsoft.com](https://security.microsoft.com) och loggar in.</span><span class="sxs-lookup"><span data-stu-id="86305-121">As a global administrator or a security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> <span data-ttu-id="86305-122">(Då kommer du till Microsoft 365 Defender portalen.)</span><span class="sxs-lookup"><span data-stu-id="86305-122">(This takes you to the Microsoft 365 Defender portal.)</span></span>

2. <span data-ttu-id="86305-123">I navigeringsfönstret väljer du **E-& för samarbete** \> **i Utforskaren.**</span><span class="sxs-lookup"><span data-stu-id="86305-123">In the navigation pane, choose **Email & collaboration** \> **Explorer**.</span></span>

3. <span data-ttu-id="86305-124">Klicka på **MDE-Inställningar i skärmens övre högra Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="86305-124">In the upper right corner of the screen, click **MDE Settings**.</span></span>

4. <span data-ttu-id="86305-125">I dialogrutan Microsoft Defender för slutpunktsanslutning aktiverar du Microsoft **Defender Anslut microsoft Defender för slutpunkt.**</span><span class="sxs-lookup"><span data-stu-id="86305-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE-anslutning":::

5. <span data-ttu-id="86305-127">Gå till Microsoft 365 Defender portalen ( [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="86305-127">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="86305-128">I navigeringsfältet väljer **du Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="86305-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="86305-129">Välj sedan **Avancerade funktioner** under **Allmänt.**</span><span class="sxs-lookup"><span data-stu-id="86305-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="86305-130">Rulla ned **till Office 365 Threat Intelligence-anslutning** och aktivera anslutningen.</span><span class="sxs-lookup"><span data-stu-id="86305-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 för hotinformation](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="86305-132">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="86305-132">Related articles</span></span>

[<span data-ttu-id="86305-133">Funktioner för undersökning av hot och svar i Office 365</span><span class="sxs-lookup"><span data-stu-id="86305-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="86305-134">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="86305-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="86305-135">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="86305-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
