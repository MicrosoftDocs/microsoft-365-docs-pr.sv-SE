---
title: Konfigurera S/MIME-inställningar – Exchange Online för Outlook på webben
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: En kort beskrivning av vad Exchange Online-administratörer behöver göra för att visa och konfigurera S/MIME-inställningarna i Outlook på webben i Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b9f4e6c33369640ad66956568959dd02b01c4fb9
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517491"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="95817-103">Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="95817-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="95817-104">Som administratör för Exchange Online kan du konfigurera Outlook på webben (tidigare kallat Outlook Web App) så att s/mime-skyddade meddelanden kan skickas och ta emot.</span><span class="sxs-lookup"><span data-stu-id="95817-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="95817-105">Använd cmdletsna **Get-SmimeConfig** och **Set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95817-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="95817-106">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="95817-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="95817-107">Detaljerad syntax- och parameterinformation finns i [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) och [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="95817-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="95817-108">Överväganden för nya Microsoft Edge (Krom-baserade)</span><span class="sxs-lookup"><span data-stu-id="95817-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="95817-109">Om du vill använda S/MIME i Outlook på webben i den nya [microsoft edge-webbläsaren](https://www.microsoft.com/windows/microsoft-edge) måste du (eller en annan administratör) ange och konfigurera microsoft edge-webbläsarprincipen **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i den nya Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="95817-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="95817-110">Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="95817-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="95817-111">Och observera att tillämpa den här principen kräver domänanslutna eller Azure AD-anslutna enheter, så att använda S/MIME i den nya Microsoft Edge-webbläsaren kräver effektivt domänanslutna eller Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="95817-111">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="95817-112">Mer information om principen **ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="95817-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="95817-113">Det här steget är en förutsättning för att använda nya Microsoft Edge. Den ersätter inte S/MIME-kontrollen som installeras av användare.</span><span class="sxs-lookup"><span data-stu-id="95817-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="95817-114">Användare uppmanas att hämta och installera S/MIME-kontrollen i Outlook på webben under sin första användning av S/MIME.</span><span class="sxs-lookup"><span data-stu-id="95817-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="95817-115">Eller, användare kan proaktivt gå till **S / MIME** i sin Outlook på webben inställningar för att få nedladdningslänken för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="95817-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="95817-116">Överväganden för Chrome</span><span class="sxs-lookup"><span data-stu-id="95817-116">Considerations for Chrome</span></span>

<span data-ttu-id="95817-117">Om du vill använda S/MIME i Outlook på webben i webbläsaren Google Chrome måste du (eller en annan administratör) ställa in och konfigurera Chromium-principen **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i Chrome.</span><span class="sxs-lookup"><span data-stu-id="95817-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="95817-118">Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="95817-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="95817-119">Och observera att tillämpa denna princip kräver domän-anslutna datorer, så att använda S / MIME i Chrome effektivt kräver domän-anslutna datorer.</span><span class="sxs-lookup"><span data-stu-id="95817-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="95817-120">Mer information om principen **ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="95817-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="95817-121">Det här steget är en förutsättning för att använda Chrome. Den ersätter inte S/MIME-kontrollen som installeras av användare.</span><span class="sxs-lookup"><span data-stu-id="95817-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="95817-122">Användare uppmanas att hämta och installera S/MIME-kontrollen i Outlook på webben under sin första användning av S/MIME.</span><span class="sxs-lookup"><span data-stu-id="95817-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="95817-123">Eller, användare kan proaktivt gå till **S / MIME** i sin Outlook på webben inställningar för att få nedladdningslänken för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="95817-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="95817-124">Mer information</span><span class="sxs-lookup"><span data-stu-id="95817-124">For more information</span></span>

[<span data-ttu-id="95817-125">S/MIME för signering och kryptering av meddelanden</span><span class="sxs-lookup"><span data-stu-id="95817-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
