---
title: Konfigurera S/MIME-inställningar – Exchange Online för Outlook på webben
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: En kort beskrivning av vilka Exchange Online-administratörer som måste göra för att visa och konfigurera S/MIME-inställningarna i Outlook på webben i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9acd7d4523754c1e07ece8fb0344d9f888c0ee3d
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825707"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="2f4fd-103">Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="2f4fd-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="2f4fd-104">Som administratör för Exchange Online kan du konfigurera Outlook på webben (tidigare Outlook Web App) för att tillåta att S/MIME-skyddade meddelanden skickas och tas emot.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="2f4fd-105">Använd cmdletarna **Get-SmimeConfig** och **set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="2f4fd-106">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2f4fd-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="2f4fd-107">Detaljerad information om syntax och parametrar finns i [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) och [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="2f4fd-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="2f4fd-108">Överväganden för nya Microsoft Edge (Krombaserade)</span><span class="sxs-lookup"><span data-stu-id="2f4fd-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="2f4fd-109">Om du vill använda S/MIME i Outlook på webben i den nya webbläsaren [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) måste du (eller någon annan administratör) ange och konfigurera policyn för Microsoft Edge-webbläsaren med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i den nya Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="2f4fd-110">Principens värde är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="2f4fd-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="2f4fd-111">Tänk på att om du tillämpar den här principen krävs domänanslutna eller Azure AD-anslutna enheter, så med S/MIME i den nya Microsoft Edge-webbläsaren krävs effektiv domän anslutna eller Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-111">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="2f4fd-112">Mer information om **ExtensionInstallForcelist** policy finns i [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="2f4fd-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="2f4fd-113">Det här steget är en förutsättning för att du ska kunna använda nya Microsoft Edge; den ersätter inte S/MIME-kontrollen som är installerad av användare.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="2f4fd-114">Användare uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben under den första användningen av S/MIME.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="2f4fd-115">Eller så kan användarna aktivera nedladdnings länken för kontrollen genom att gå till **S/MIME** i sina Outlook-inställningar.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="2f4fd-116">Överväganden för Chrome</span><span class="sxs-lookup"><span data-stu-id="2f4fd-116">Considerations for Chrome</span></span>

<span data-ttu-id="2f4fd-117">Om du vill använda S/MIME i Outlook på webben i din Google Chrome-webbläsare måste du (eller någon annan administratör) ange och konfigurera den krom principen med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i Chrome.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="2f4fd-118">Principens värde är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="2f4fd-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="2f4fd-119">Tänk på att om du tillämpar den här principen måste domänanslutna datorer, och om du använder S/MIME i Chrome effektivt krävs domänanslutna datorer.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="2f4fd-120">Mer information om **ExtensionInstallForcelist** policy finns i [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="2f4fd-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="2f4fd-121">Det här steget är en förutsättning för att du ska kunna använda Chrome; den ersätter inte S/MIME-kontrollen som är installerad av användare.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="2f4fd-122">Användare uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben under den första användningen av S/MIME.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="2f4fd-123">Eller så kan användarna aktivera nedladdnings länken för kontrollen genom att gå till **S/MIME** i sina Outlook-inställningar.</span><span class="sxs-lookup"><span data-stu-id="2f4fd-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="2f4fd-124">Mer information</span><span class="sxs-lookup"><span data-stu-id="2f4fd-124">For more information</span></span>

[<span data-ttu-id="2f4fd-125">S/MIME för signering och kryptering av meddelanden</span><span class="sxs-lookup"><span data-stu-id="2f4fd-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
