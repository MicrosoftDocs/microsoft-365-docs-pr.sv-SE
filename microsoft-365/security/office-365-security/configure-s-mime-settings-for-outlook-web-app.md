---
title: Konfigurera S/MIME-inställningar – Exchange Online för Outlook på webben
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: En kort beskrivning av vad Exchange Online-administratörer behöver göra för att visa och konfigurera S/MIME-inställningar i Outlook på webben i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ab1aaabf0e7651a5a84642c178c28961430eea0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906486"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="1e3c3-103">Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="1e3c3-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1e3c3-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="1e3c3-104">**Applies to**</span></span>
- [<span data-ttu-id="1e3c3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1e3c3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1e3c3-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="1e3c3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="1e3c3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e3c3-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="1e3c3-108">Som administratör för Exchange Online kan du konfigurera Outlook på webben (kallades tidigare för Outlook Web App) så att du kan skicka och ta emot S/MIME-skyddade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="1e3c3-109">Använd **cmdletarna Get-SmimeConfig** och **Set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="1e3c3-110">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1e3c3-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="1e3c3-111">Detaljerad information om syntax och parametrar finns i [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) och [Set-SmimeConfig.](/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="1e3c3-111">For detailed syntax and parameter information, see [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="1e3c3-112">Att tänka på för nya Microsoft Edge (Chromium-baserad)</span><span class="sxs-lookup"><span data-stu-id="1e3c3-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="1e3c3-113">Om du vill använda S/MIME i Outlook på webben i den nya [Webbläsaren Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) måste du (eller en annan administratör) konfigurera webbläsarprincipen för Microsoft Edge med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i den nya Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="1e3c3-114">Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="1e3c3-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="1e3c3-115">Observera att användning av den här principen kräver domän-anslutna eller Azure AD-anslutna enheter, så användning av S/MIME i den nya webbläsaren Microsoft Edge kräver effektivt domän-anslutna eller Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="1e3c3-116">Mer information om **principen ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="1e3c3-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="1e3c3-117">Det här steget krävs för att använda nya Microsoft Edge. Den ersätter inte den S/MIME-kontroll som installeras av användare.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="1e3c3-118">Användarna uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben vid första användningen av S/MIME.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="1e3c3-119">Eller så kan användare proaktivt gå till **S/MIME** i sina Outlook på webben-inställningar för att få nedladdningslänken för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="1e3c3-120">Att tänka på för Chrome</span><span class="sxs-lookup"><span data-stu-id="1e3c3-120">Considerations for Chrome</span></span>

<span data-ttu-id="1e3c3-121">Om du vill använda S/MIME i Outlook på webben i Google Chrome-webbläsaren måste du (eller en annan administratör) konfigurera Chromium-principen med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i Chrome.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="1e3c3-122">Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="1e3c3-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="1e3c3-123">Observera att det krävs domänbaserade datorer för att kunna använda den här principen, så det krävs att du verkligen använder domänbaserade datorer i Chrome.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="1e3c3-124">Mer information om **principen ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="1e3c3-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="1e3c3-125">Det här steget krävs för att använda Chrome. Den ersätter inte den S/MIME-kontroll som installeras av användare.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="1e3c3-126">Användarna uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben vid första användningen av S/MIME.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="1e3c3-127">Eller så kan användare proaktivt gå till **S/MIME** i sina Outlook på webben-inställningar för att få nedladdningslänken för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="1e3c3-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="1e3c3-128">Mer information</span><span class="sxs-lookup"><span data-stu-id="1e3c3-128">For more information</span></span>

[<span data-ttu-id="1e3c3-129">S/MIME för signering och kryptering av meddelanden</span><span class="sxs-lookup"><span data-stu-id="1e3c3-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)