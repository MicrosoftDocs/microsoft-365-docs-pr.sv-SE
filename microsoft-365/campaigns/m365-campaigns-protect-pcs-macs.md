---
title: Skydda ohanterade Windows 10-datorer och Mac-datorer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Skydda mot nätfiske och andra attacker med Microsoft 365 för kampanjer.
ms.openlocfilehash: 0cd96cb73ad3d0b38ab1e5ff31c913d97528c2d4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632797"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a><span data-ttu-id="18d8a-103">Skydda ohanterade Windows 10-datorer och Mac-datorer</span><span class="sxs-lookup"><span data-stu-id="18d8a-103">Protect unmanaged Windows 10 PCs and Macs</span></span>

<span data-ttu-id="18d8a-104">Du kan hantera Windows 10-datorer och Mac-datorer genom att registrera dem i Microsoft Intune, vilket gör att du kan se till att de är felfria och säkra innan du öppnar data i din miljö.</span><span class="sxs-lookup"><span data-stu-id="18d8a-104">You can manage Windows 10 PCs and Macs by enrolling them in Microsoft Intune, which allows you to ensure they're healthy and secure before accessing data in your environment.</span></span> <span data-ttu-id="18d8a-105">Men många kampanjer och småföretag inkluderar personal som tar med sina egna enheter (byod), som inte kommer att hanteras av organisationen.</span><span class="sxs-lookup"><span data-stu-id="18d8a-105">However, many campaigns and small businesses include staff who bring their own devices (byod), which will not be managed by the organization.</span></span> <span data-ttu-id="18d8a-106">För dessa ohanterade datorer och Mac-datorer använder du den här artikeln för att säkerställa att minsta säkerhetsfunktioner är konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="18d8a-106">For these unmanaged PCs and Macs, use this article to ensure that minimum security capabilities are configured.</span></span> 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a><span data-ttu-id="18d8a-107">Skydda en dator med Windows 10 eller mac</span><span class="sxs-lookup"><span data-stu-id="18d8a-107">Protect a computer running Windows 10 or a Mac</span></span>

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
<span data-ttu-id="18d8a-108">Om din Windows 10-dator eller Mac inte hanteras av din organisation måste du konfigurera dessa säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="18d8a-108">If your Windows 10 PC or Mac is not managed by your organization, be sure to configure these security capabilities.</span></span>

## <a name="windows-10"></a>[<span data-ttu-id="18d8a-109">Windows 10</span><span class="sxs-lookup"><span data-stu-id="18d8a-109">Windows 10</span></span>](#tab/Windows10)
<span data-ttu-id="18d8a-110">**Aktivera enhetskryptering**</span><span class="sxs-lookup"><span data-stu-id="18d8a-110">**Turn on device encryption**</span></span><p>

<span data-ttu-id="18d8a-111">Enhetskryptering är tillgängligt på ett brett spektrum av Windows-enheter och hjälper till att skydda dina data genom att kryptera dem.</span><span class="sxs-lookup"><span data-stu-id="18d8a-111">Device encryption is available on a wide range of Windows devices and helps protect your data by encrypting it.</span></span> <span data-ttu-id="18d8a-112">Om du aktiverar enhetskryptering kan endast behöriga personer komma åt din enhet och dina data.</span><span class="sxs-lookup"><span data-stu-id="18d8a-112">If you turn on device encryption, only authorized individuals will be able to access your device and data.</span></span> <span data-ttu-id="18d8a-113">Instruktioner finns [i aktivera enhetskryptering.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption)</span><span class="sxs-lookup"><span data-stu-id="18d8a-113">See [turn on device encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) for instructions.</span></span>

 <span data-ttu-id="18d8a-114">Om enhetskryptering inte är tillgängligt på enheten kan du aktivera [standardBitLocker-kryptering](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) i stället.</span><span class="sxs-lookup"><span data-stu-id="18d8a-114">If device encryption isn't available on your device, you can turn on standard [BitLocker encryption](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) instead.</span></span> <span data-ttu-id="18d8a-115">(BitLocker är inte tillgängligt i Windows 10 Home Edition.)</span><span class="sxs-lookup"><span data-stu-id="18d8a-115">(BitLocker isn't available on Windows 10 Home edition.)</span></span> 


<span data-ttu-id="18d8a-116">**Skydda enheten med Windows Security**</span><span class="sxs-lookup"><span data-stu-id="18d8a-116">**Protect your device with Windows Security**</span></span><p>
<span data-ttu-id="18d8a-117">Om du har Windows 10 får du det senaste antivirusskyddet med Windows Security.</span><span class="sxs-lookup"><span data-stu-id="18d8a-117">If you have Windows 10, you'll get the latest antivirus protection with Windows Security.</span></span> <span data-ttu-id="18d8a-118">När du startar Windows 10 för första gången är Windows Security aktiverat och aktivt hjälper till att skydda datorn genom att söka efter skadlig programvara (skadlig programvara), virus och säkerhetshot.</span><span class="sxs-lookup"><span data-stu-id="18d8a-118">When you start up Windows 10 for the first time, Windows Security is on and actively helping to protect your PC by scanning for malware (malicious software), viruses, and security threats.</span></span> <span data-ttu-id="18d8a-119">Windows Security använder realtidsskydd för att skanna allt du laddar ned eller kör på datorn.</span><span class="sxs-lookup"><span data-stu-id="18d8a-119">Windows Security uses real-time protection to scan everything you download or run on your PC.</span></span>

<span data-ttu-id="18d8a-120">Windows Update hämtar uppdateringar för Windows Security automatiskt för att skydda datorn och skydda den från hot.</span><span class="sxs-lookup"><span data-stu-id="18d8a-120">Windows Update downloads updates for Windows Security automatically to help keep your PC safe and protect it from threats.</span></span>

<span data-ttu-id="18d8a-121">Om du har en tidigare version av Windows och använder Microsoft Security Essentials är det en bra idé att flytta till Windows Security.</span><span class="sxs-lookup"><span data-stu-id="18d8a-121">If you have an earlier version of Windows and are using Microsoft Security Essentials, it's a good idea to move to Windows Security.</span></span> <span data-ttu-id="18d8a-122">Mer information finns i [Skydda min enhet med Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span><span class="sxs-lookup"><span data-stu-id="18d8a-122">For more information, see [help protect my device with Windows Security](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).</span></span>

<span data-ttu-id="18d8a-123">**Aktivera Windows-brandväggen**</span><span class="sxs-lookup"><span data-stu-id="18d8a-123">**Turn on Windows Firewall**</span></span><p>
<span data-ttu-id="18d8a-124">Du bör alltid köra Windows-brandväggen även om du har aktiverat en annan brandvägg.</span><span class="sxs-lookup"><span data-stu-id="18d8a-124">You should always run Windows Firewall even if you have another firewall turned on.</span></span> <span data-ttu-id="18d8a-125">Om du inaktiverar Windows-brandväggen kan enheten (och nätverket, om du har en) bli mer sårbara för obehörig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="18d8a-125">Turning off Windows Firewall might make your device (and your network, if you have one) more vulnerable to unauthorized access.</span></span> <span data-ttu-id="18d8a-126">Instruktioner finns [i Aktivera eller inaktivera Windows-brandväggen](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="18d8a-126">See [Turn Windows Firewall on or off](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) for instructions</span></span>

## <a name="mac"></a>[<span data-ttu-id="18d8a-127">Mac</span><span class="sxs-lookup"><span data-stu-id="18d8a-127">Mac</span></span>](#tab/Mac)
<span data-ttu-id="18d8a-128">**Använda FileVault för att kryptera din Mac-disk**</span><span class="sxs-lookup"><span data-stu-id="18d8a-128">**Use FileVault to encrypt your Mac disk**</span></span><p>
<span data-ttu-id="18d8a-129">Diskkryptering skyddar data när enheter försvinner eller blir stulna.</span><span class="sxs-lookup"><span data-stu-id="18d8a-129">Disk encryption protects data when devices are lost or stolen.</span></span> <span data-ttu-id="18d8a-130">FileVault full disk kryptering hjälper till att förhindra obehörig åtkomst till informationen på startdisken.</span><span class="sxs-lookup"><span data-stu-id="18d8a-130">FileVault full-disk encryption helps prevent unauthorized access to the information on your startup disk.</span></span> <span data-ttu-id="18d8a-131">Se [använda FileVault för att kryptera startdisken på din Mac](https://support.apple.com/HT204837) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="18d8a-131">See [use FileVault to encrypt the startup disk on your Mac](https://support.apple.com/HT204837) for instructions.</span></span>

<span data-ttu-id="18d8a-132">**Skydda din mac från skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="18d8a-132">**Protect your mac from malware**</span></span><p>
<span data-ttu-id="18d8a-133">Microsoft rekommenderar att du installerar och använder tillförlitligt antivirusprogram på din Mac.</span><span class="sxs-lookup"><span data-stu-id="18d8a-133">Microsoft recommends that you install and use reliable antivirus software on your Mac.</span></span> <span data-ttu-id="18d8a-134">Se följande artikel för en lista med alternativ: [Bästa Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span><span class="sxs-lookup"><span data-stu-id="18d8a-134">See the following article for a list of choices: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).</span></span>

<span data-ttu-id="18d8a-135">Du kan också minska risken för skadlig kod genom att endast använda programvara från tillförlitliga källor.</span><span class="sxs-lookup"><span data-stu-id="18d8a-135">You can also reduce the risk of malware by using software only from reliable sources.</span></span> <span data-ttu-id="18d8a-136">Med inställningarna i säkerhets- & sekretessinställningarna kan du ange de programvarukällor som är installerade på din Mac.</span><span class="sxs-lookup"><span data-stu-id="18d8a-136">The settings in Security & Privacy preferences allow you to specify the sources of software installed on your Mac.</span></span> <span data-ttu-id="18d8a-137">Mer information finns i [skydda din Mac från skadlig kod](https://support.apple.com/kb/PH25087).</span><span class="sxs-lookup"><span data-stu-id="18d8a-137">For more information, see [protect your Mac from malware](https://support.apple.com/kb/PH25087).</span></span>

<span data-ttu-id="18d8a-138">**Aktivera brandväggsskydd**</span><span class="sxs-lookup"><span data-stu-id="18d8a-138">**Turn on firewall protection**</span></span><p>
<span data-ttu-id="18d8a-139">Använd brandväggsinställningar för att skydda din Mac från oönskad kontakt som initieras av andra datorer när du är ansluten till Internet eller ett nätverk.</span><span class="sxs-lookup"><span data-stu-id="18d8a-139">Use firewall settings to protect your Mac from unwanted contact initiated by other computers when you're connected to the Internet or a network.</span></span> <span data-ttu-id="18d8a-140">Utan det här skyddet kan din Mac vara mer sårbar för obehörig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="18d8a-140">Without this protection, your Mac might be more vulnerable to unauthorized access.</span></span> <span data-ttu-id="18d8a-141">Se [om programmet brandväggen](https://support.apple.com/HT201642) för instruktioner.</span><span class="sxs-lookup"><span data-stu-id="18d8a-141">See [about the application firewall](https://support.apple.com/HT201642) for instructions.</span></span>
