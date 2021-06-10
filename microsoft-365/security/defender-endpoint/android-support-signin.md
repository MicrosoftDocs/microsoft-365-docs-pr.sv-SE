---
title: Felsöka problem med Microsoft Defender för slutpunkt på Android
description: Felsöka problem med Microsoft Defender för slutpunkt på Android
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mde, android, molnet, anslutningar, kommunikation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246362"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="f850d-104">Felsöka problem med Microsoft Defender för slutpunkt på Android</span><span class="sxs-lookup"><span data-stu-id="f850d-104">Troubleshooting issues on Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f850d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f850d-105">**Applies to:**</span></span>
- [<span data-ttu-id="f850d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f850d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f850d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f850d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f850d-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f850d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f850d-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f850d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="f850d-110">Vid registrering av en enhet kan du eventuellt se inloggningsproblem när appen har installerats.</span><span class="sxs-lookup"><span data-stu-id="f850d-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="f850d-111">Under introduktionen kan du stöta på inloggningsproblem när appen är installerad på din enhet.</span><span class="sxs-lookup"><span data-stu-id="f850d-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="f850d-112">I den här artikeln finns lösningar på inloggningsproblem.</span><span class="sxs-lookup"><span data-stu-id="f850d-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="f850d-113">Inloggningen misslyckades – oväntat fel</span><span class="sxs-lookup"><span data-stu-id="f850d-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="f850d-114">**Inloggningen misslyckades:** *Oväntat fel, försök senare*</span><span class="sxs-lookup"><span data-stu-id="f850d-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Bild på inloggningsfelet Oväntat fel](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="f850d-116">**Meddelande:**</span><span class="sxs-lookup"><span data-stu-id="f850d-116">**Message:**</span></span>

<span data-ttu-id="f850d-117">Oväntat fel, försök senare</span><span class="sxs-lookup"><span data-stu-id="f850d-117">Unexpected error, try later</span></span>

<span data-ttu-id="f850d-118">**Orsak:**</span><span class="sxs-lookup"><span data-stu-id="f850d-118">**Cause:**</span></span>

<span data-ttu-id="f850d-119">Du har en äldre version av appen "Microsoft Authenticator" installerad på enheten.</span><span class="sxs-lookup"><span data-stu-id="f850d-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="f850d-120">**Lösning:**</span><span class="sxs-lookup"><span data-stu-id="f850d-120">**Solution:**</span></span>

<span data-ttu-id="f850d-121">Installera den senaste versionen och [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) från Google Play Store och försök igen</span><span class="sxs-lookup"><span data-stu-id="f850d-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="f850d-122">Inloggningen misslyckades – ogiltig licens</span><span class="sxs-lookup"><span data-stu-id="f850d-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="f850d-123">**Inloggningen misslyckades:** *Ogiltig licens. Kontakta administratören*</span><span class="sxs-lookup"><span data-stu-id="f850d-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Bild på inloggningen misslyckades, kontakta administratören](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="f850d-125">**Meddelande:** *Ogiltig licens, kontakta administratören*</span><span class="sxs-lookup"><span data-stu-id="f850d-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="f850d-126">**Orsak:**</span><span class="sxs-lookup"><span data-stu-id="f850d-126">**Cause:**</span></span>

<span data-ttu-id="f850d-127">Du har inte Microsoft 365 licens kopplad, eller så har organisationen ingen licens för Microsoft 365 Enterprise prenumeration.</span><span class="sxs-lookup"><span data-stu-id="f850d-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="f850d-128">**Lösning:**</span><span class="sxs-lookup"><span data-stu-id="f850d-128">**Solution:**</span></span>

<span data-ttu-id="f850d-129">Kontakta administratören om du behöver hjälp.</span><span class="sxs-lookup"><span data-stu-id="f850d-129">Contact your administrator for help.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="f850d-130">Rapportera osäker webbplats</span><span class="sxs-lookup"><span data-stu-id="f850d-130">Report unsafe site</span></span>

<span data-ttu-id="f850d-131">Nätfiskewebbplatser utger sig för att vara betrodda webbplatser i syfte att skaffa personlig eller ekonomisk information.</span><span class="sxs-lookup"><span data-stu-id="f850d-131">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="f850d-132">Gå till [sidan Ge feedback om nätverksskydd](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om du vill rapportera en webbplats som kan vara en nätfiskewebbplats.</span><span class="sxs-lookup"><span data-stu-id="f850d-132">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="f850d-133">Nätfiskesidor blockeras inte på vissa OEM-enheter</span><span class="sxs-lookup"><span data-stu-id="f850d-133">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="f850d-134">**Gäller för:** Endast vissa OEM-maskiner</span><span class="sxs-lookup"><span data-stu-id="f850d-134">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="f850d-135">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="f850d-135">**Xiaomi**</span></span>

<span data-ttu-id="f850d-136">Nätfiske och skadliga webbhot som upptäcks av Defender för Endpoint för Android blockeras inte på vissa Xiaomi-enheter.</span><span class="sxs-lookup"><span data-stu-id="f850d-136">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="f850d-137">Följande funktioner fungerar inte på de här enheterna.</span><span class="sxs-lookup"><span data-stu-id="f850d-137">The following functionality doesn't work on these devices.</span></span>

![Bild på webbplatsen som rapporterats som osäker](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="f850d-139">**Orsak:**</span><span class="sxs-lookup"><span data-stu-id="f850d-139">**Cause:**</span></span>

<span data-ttu-id="f850d-140">Xiaomi-enheter har en ny behörighetsmodell.</span><span class="sxs-lookup"><span data-stu-id="f850d-140">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="f850d-141">Det förhindrar att Defender för Slutpunkt för Android visar popup-fönster medan det körs i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="f850d-141">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="f850d-142">Behörighet för Xiaomi-enheter: "Visa popup-fönster när de körs i bakgrunden".</span><span class="sxs-lookup"><span data-stu-id="f850d-142">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Bild på popup-inställning](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="f850d-144">**Lösning:**</span><span class="sxs-lookup"><span data-stu-id="f850d-144">**Solution:**</span></span>

<span data-ttu-id="f850d-145">Aktivera den behörighet som krävs på Xiaomi-enheter.</span><span class="sxs-lookup"><span data-stu-id="f850d-145">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="f850d-146">Visa popup-fönster när du körs i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="f850d-146">Display pop-up windows while running in the background.</span></span>
