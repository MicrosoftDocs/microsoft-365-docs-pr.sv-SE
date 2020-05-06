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
ms.openlocfilehash: 2ed3f3c6289c4663c6bebecdf9ab03eacd94e373
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035100"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="8d69f-103">Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="8d69f-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="8d69f-104">Som administratör för Exchange Online kan du konfigurera Outlook på webben (tidigare kallat Outlook Web App) så att s/mime-skyddade meddelanden kan skickas och ta emot.</span><span class="sxs-lookup"><span data-stu-id="8d69f-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="8d69f-105">Använd cmdletsna **Get-SmimeConfig** och **Set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d69f-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="8d69f-106">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="8d69f-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="8d69f-107">Detaljerad syntax- och parameterinformation finns i [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) och [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="8d69f-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="8d69f-108">Överväganden för nya Microsoft Edge (Krom-baserade)</span><span class="sxs-lookup"><span data-stu-id="8d69f-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="8d69f-109">Om du vill använda S/MIME i Outlook på webben i den nya [Microsoft Edge-webbläsaren](https://www.microsoft.com/windows/microsoft-edge) måste du (eller en annan administratör) ange och konfigurera microsoft edge-webbläsarprincipen **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i nya Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="8d69f-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in new Microsoft Edge.</span></span> <span data-ttu-id="8d69f-110">Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span><span class="sxs-lookup"><span data-stu-id="8d69f-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="8d69f-111">Och observera att tillämpa denna princip kräver domän-anslutna datorer, så att använda S / MIME i den nya Microsoft Edge webbläsare kräver effektivt domän-anslutna datorer.</span><span class="sxs-lookup"><span data-stu-id="8d69f-111">And note that applying this policy requires domain-joined computers, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined computers.</span></span>

<span data-ttu-id="8d69f-112">Mer information om principen **ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span><span class="sxs-lookup"><span data-stu-id="8d69f-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="8d69f-113">Det här steget är en förutsättning för att använda nya Microsoft Edge. Den ersätter inte S/MIME-kontrollen som installeras av användare.</span><span class="sxs-lookup"><span data-stu-id="8d69f-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="8d69f-114">Användare uppmanas att hämta och installera S/MIME-kontrollen i Outlook på webben under den första användningen av S/MIME.</span><span class="sxs-lookup"><span data-stu-id="8d69f-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="8d69f-115">Eller så kan användare proaktivt gå till **S/MIME** i sina Outlook på webbinställningarna för att få nedladdningslänken för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="8d69f-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="8d69f-116">Överväganden för Chrome</span><span class="sxs-lookup"><span data-stu-id="8d69f-116">Considerations for Chrome</span></span>

<span data-ttu-id="8d69f-117">Om du vill använda S/MIME i Outlook på webben i webbläsaren Google Chrome måste du (eller en annan administratör) ange och konfigurera Chromium-principen **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i Chrome.</span><span class="sxs-lookup"><span data-stu-id="8d69f-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="8d69f-118">Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span><span class="sxs-lookup"><span data-stu-id="8d69f-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="8d69f-119">Och observera att tillämpa den här principen kräver domänanslutna datorer, så att använda S/MIME i Chrome kräver effektivt domänanslutna datorer.</span><span class="sxs-lookup"><span data-stu-id="8d69f-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="8d69f-120">Mer information om principen **ExtensionInstallForcelist** finns i [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span><span class="sxs-lookup"><span data-stu-id="8d69f-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="8d69f-121">Det här steget är en förutsättning för att använda Chrome. Den ersätter inte S/MIME-kontrollen som installeras av användare.</span><span class="sxs-lookup"><span data-stu-id="8d69f-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="8d69f-122">Användare uppmanas att hämta och installera S/MIME-kontrollen i Outlook på webben under den första användningen av S/MIME.</span><span class="sxs-lookup"><span data-stu-id="8d69f-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="8d69f-123">Eller så kan användare proaktivt gå till **S/MIME** i sina Outlook på webbinställningarna för att få nedladdningslänken för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="8d69f-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="8d69f-124">Mer information</span><span class="sxs-lookup"><span data-stu-id="8d69f-124">For more information</span></span>

[<span data-ttu-id="8d69f-125">S/MIME för signering och kryptering av meddelanden</span><span class="sxs-lookup"><span data-stu-id="8d69f-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
