---
title: Definiera hur mobila enheter uppdateras av Microsoft Defender Antivirus
description: Hantera hur mobila enheter, till exempel bärbara datorer, ska uppdateras med uppdateringar för Microsoft Defender Antivirus Protection.
keywords: uppdateringar, skydd, schemalägg uppdateringar, batteri, mobil enhet, bärbar dator, anteckningsbok, välja till, microsoft update, wsus, åsidosätt
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
ms.openlocfilehash: 143b0cb4bac1d3307e440f98fa4278f38e07c7f2
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269546"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a><span data-ttu-id="62120-104">Hantera uppdateringar för mobila enheter och virtuella datorer(VM)</span><span class="sxs-lookup"><span data-stu-id="62120-104">Manage updates for mobile devices and virtual machines (VMs)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="62120-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="62120-105">**Applies to:**</span></span>

- [<span data-ttu-id="62120-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="62120-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="62120-107">Mobila enheter och virtuella maskiner kan kräva mer konfiguration för att säkerställa att prestanda inte påverkas av uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="62120-107">Mobile devices and VMs may require more configuration to ensure performance is not impacted by updates.</span></span>

<span data-ttu-id="62120-108">Det finns två inställningar som är användbara för dessa enheter:</span><span class="sxs-lookup"><span data-stu-id="62120-108">There are two settings that are useful for these devices:</span></span>

- <span data-ttu-id="62120-109">Registrera dig för Microsoft Update på mobila datorer utan WSUS-anslutning</span><span class="sxs-lookup"><span data-stu-id="62120-109">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>
- <span data-ttu-id="62120-110">Förhindra säkerhetsintelligensuppdateringar när de körs på batteri</span><span class="sxs-lookup"><span data-stu-id="62120-110">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="62120-111">Följande artiklar kan också vara användbara i dessa situationer:</span><span class="sxs-lookup"><span data-stu-id="62120-111">The following articles may also be useful in these situations:</span></span>
- [<span data-ttu-id="62120-112">Konfigurera schemalagda och uppläsningssökningar</span><span class="sxs-lookup"><span data-stu-id="62120-112">Configuring scheduled and catch-up scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="62120-113">Hantera uppdateringar för slutpunkter som är in uppdaterade</span><span class="sxs-lookup"><span data-stu-id="62120-113">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="62120-114">Distributionsguide för Microsoft Defender Antivirus i en VDI-miljö (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="62120-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a><span data-ttu-id="62120-115">Registrera dig för Microsoft Update på mobila datorer utan WSUS-anslutning</span><span class="sxs-lookup"><span data-stu-id="62120-115">Opt in to Microsoft Update on mobile computers without a WSUS connection</span></span>

<span data-ttu-id="62120-116">Du kan använda Microsoft Update för att hålla Säkerhetsinformation på mobila enheter som kör Microsoft Defender Antivirus uppdaterat när de inte är anslutna till företagsnätverket eller annars inte har en WSUS-anslutning.</span><span class="sxs-lookup"><span data-stu-id="62120-116">You can use Microsoft Update to keep Security intelligence on mobile devices running Microsoft Defender Antivirus up to date when they are not connected to the corporate network or don't otherwise have a WSUS connection.</span></span> 

<span data-ttu-id="62120-117">Det innebär att skyddsuppdateringar kan levereras till enheter (via Microsoft Update) även om du har angett att WSUS ska åsidosätta Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="62120-117">This means that protection updates can be delivered to devices (via Microsoft Update) even if you have set WSUS to override Microsoft Update.</span></span>

<span data-ttu-id="62120-118">Du kan registrera dig för Microsoft Update på den mobila enheten på något av följande sätt:</span><span class="sxs-lookup"><span data-stu-id="62120-118">You can opt in to Microsoft Update on the mobile device in one of the following ways:</span></span>

- <span data-ttu-id="62120-119">Ändra inställningen med Grupprincip.</span><span class="sxs-lookup"><span data-stu-id="62120-119">Change the setting with Group Policy.</span></span>
- <span data-ttu-id="62120-120">Använd VBScript för att skapa ett skript och kör det sedan på varje dator i nätverket.</span><span class="sxs-lookup"><span data-stu-id="62120-120">Use a VBScript to create a script, then run it on each computer in your network.</span></span>
- <span data-ttu-id="62120-121">Registrera dig manuellt på alla datorer i nätverket via **menyn** Inställningar.</span><span class="sxs-lookup"><span data-stu-id="62120-121">Manually opt in every computer on your network through the **Settings** menu.</span></span>

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a><span data-ttu-id="62120-122">Använd grupprincip för att registrera dig för Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="62120-122">Use Group Policy to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="62120-123">På hanteringsdatorn för grupprinciper öppnar du [Konsolen](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))för grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och väljer **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="62120-123">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="62120-124">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="62120-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="62120-125">Välj **Principer** och **sedan Administrativa mallar.**</span><span class="sxs-lookup"><span data-stu-id="62120-125">Select **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="62120-126">Expandera trädet till **Windows-komponenterna**  >  **Microsoft Defender Antivirus** Signature  >  **Updates**.</span><span class="sxs-lookup"><span data-stu-id="62120-126">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**.</span></span>

5. <span data-ttu-id="62120-127">Ange **Tillåt säkerhetsintelligensuppdateringar från Microsoft Update** **till** Aktiverat och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="62120-127">Set **Allow security intelligence updates from Microsoft Update** to **Enabled**, and then select  **OK**.</span></span>


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a><span data-ttu-id="62120-128">Använda VBScript för att registrera sig för Microsoft Update</span><span class="sxs-lookup"><span data-stu-id="62120-128">Use a VBScript to opt in to Microsoft Update</span></span>

1. <span data-ttu-id="62120-129">Använd anvisningarna i [MSDN-artikeln Välja att Microsoft Update ska användas för](/windows/win32/wua_sdk/opt-in-to-microsoft-update) att skapa VBScript-koden.</span><span class="sxs-lookup"><span data-stu-id="62120-129">Use the instructions in the MSDN article [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) to create the VBScript.</span></span>

2. <span data-ttu-id="62120-130">Kör VBScript-koden som du skapade på varje dator i nätverket.</span><span class="sxs-lookup"><span data-stu-id="62120-130">Run the VBScript you created on each computer in your network.</span></span>

### <a name="manually-opt-in-to-microsoft-update"></a><span data-ttu-id="62120-131">Registrera dig för Microsoft Update manuellt</span><span class="sxs-lookup"><span data-stu-id="62120-131">Manually opt in to Microsoft Update</span></span>

1. <span data-ttu-id="62120-132">Öppna **Windows Update** i & **säkerhetsinställningarna** på den dator som du vill registrera dig för.</span><span class="sxs-lookup"><span data-stu-id="62120-132">Open **Windows Update** in **Update & security** settings on the computer you want to opt in.</span></span>

2. <span data-ttu-id="62120-133">Välj **Avancerade** alternativ.</span><span class="sxs-lookup"><span data-stu-id="62120-133">Select **Advanced** options.</span></span>

3. <span data-ttu-id="62120-134">Markera kryssrutan för Ge mig **uppdateringar för andra Microsoft-produkter när jag uppdaterar Windows.**</span><span class="sxs-lookup"><span data-stu-id="62120-134">Select the checkbox for **Give me updates for other Microsoft products when I update Windows**.</span></span>

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a><span data-ttu-id="62120-135">Förhindra säkerhetsintelligensuppdateringar när de körs på batteri</span><span class="sxs-lookup"><span data-stu-id="62120-135">Prevent Security intelligence updates when running on battery power</span></span>

<span data-ttu-id="62120-136">Du kan konfigurera Microsoft Defender Antivirus för att bara ladda ned uppdateringar om datorn är ansluten till en kabelansluten strömkälla.</span><span class="sxs-lookup"><span data-stu-id="62120-136">You can configure Microsoft Defender Antivirus to only download protection updates when the PC is connected to a wired power source.</span></span> 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a><span data-ttu-id="62120-137">Använda grupprinciper för att förhindra säkerhetsintelligensuppdateringar på batterikraft</span><span class="sxs-lookup"><span data-stu-id="62120-137">Use Group Policy to prevent security intelligence updates on battery power</span></span>

1.  <span data-ttu-id="62120-138">Öppna Grupprinciphanteringskonsol på hanteringsdatorn för [grupprinciper,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))välj det grupprincipobjekt du vill konfigurera och öppna det för redigering.</span><span class="sxs-lookup"><span data-stu-id="62120-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), choose the Group Policy Object you want to configure, and open it for editing.</span></span>

2.  <span data-ttu-id="62120-139">Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**</span><span class="sxs-lookup"><span data-stu-id="62120-139">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3.  <span data-ttu-id="62120-140">Välj **Principer** och **sedan Administrativa mallar.**</span><span class="sxs-lookup"><span data-stu-id="62120-140">Select **Policies** then **Administrative templates**.</span></span>

4.  <span data-ttu-id="62120-141">Expandera trädet till **Windows-komponenter** Microsoft Defender Antivirus Signature Updates och ange sedan Tillåt säkerhetsintelligensuppdateringar när  >    >   **batterikraften körs** till **Inaktiverad.**</span><span class="sxs-lookup"><span data-stu-id="62120-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Updates**, and then set **Allow security intelligence updates when running on battery power** to **Disabled**.</span></span> <span data-ttu-id="62120-142">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="62120-142">Then select **OK**.</span></span> 

<span data-ttu-id="62120-143">Den här åtgärden förhindrar att uppdateringar laddas ned när datorn är på batterinivå.</span><span class="sxs-lookup"><span data-stu-id="62120-143">This action prevents protection updates from downloading when the PC is on battery power.</span></span>

## <a name="related-articles"></a><span data-ttu-id="62120-144">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="62120-144">Related articles</span></span>

- [<span data-ttu-id="62120-145">Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer</span><span class="sxs-lookup"><span data-stu-id="62120-145">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="62120-146">Uppdatera och hantera Microsoft Defender Antivirus i Windows 10</span><span class="sxs-lookup"><span data-stu-id="62120-146">Update and manage Microsoft Defender Antivirus in Windows 10</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)