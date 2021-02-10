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
ms.openlocfilehash: a81db5ec933f1d0d6e2944103be53c0169dde62f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165685"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="4855d-103">Konfigurera S/MIME-inställningar i Exchange Online för Outlook på webben</span><span class="sxs-lookup"><span data-stu-id="4855d-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4855d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="4855d-104">**Applies to**</span></span>
- [<span data-ttu-id="4855d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4855d-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="4855d-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="4855d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="4855d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4855d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="4855d-108">Som administratör för Exchange Online kan du konfigurera Outlook på webben (tidigare Outlook Web App) så att s/MIME-skyddade meddelanden kan skickas och tas emot.</span><span class="sxs-lookup"><span data-stu-id="4855d-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="4855d-109">Använd **cmdletarna Get-SmimeConfig** och **Set-SmimeConfig** för att visa och hantera den här funktionen i Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4855d-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="4855d-110">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4855d-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="4855d-111">Detaljerad information om syntax och parametrar finns i [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) och [Set-SmimeConfig.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="4855d-111">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="4855d-112">Att tänka på för nya Microsoft Edge (Chromium-baserad)</span><span class="sxs-lookup"><span data-stu-id="4855d-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="4855d-113">Om du vill använda S/MIME i Outlook på webben i den nya [webbläsaren Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) måste du (eller en annan administratör) ange och konfigurera Microsoft Edge-webbläsarprincipen med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i den nya Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="4855d-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="4855d-114">Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="4855d-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="4855d-115">Observera att det krävs domän anslutna eller Azure AD-anslutna enheter för att kunna använda den här principen, så att du måste använda S/MIME i den nya Webbläsaren Microsoft Edge på ett effektivt sätt för domän anslutna eller Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="4855d-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="4855d-116">Mer information om **policyn ExtensionInstallForcelist** finns [i ExtensionInstallForcelist.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)</span><span class="sxs-lookup"><span data-stu-id="4855d-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="4855d-117">Det här steget är en förutsättning för att du ska kunna använda nya Microsoft Edge. Den ersätter inte den S/MIME-kontroll som installeras av användare.</span><span class="sxs-lookup"><span data-stu-id="4855d-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="4855d-118">Användare uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben vid första användningen av S/MIME.</span><span class="sxs-lookup"><span data-stu-id="4855d-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="4855d-119">Användare kan också proaktivt gå till **S/MIME** i sina Outlook på webben-inställningar för att få nedladdningslänken för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="4855d-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="4855d-120">Att tänka på när det gäller Chrome</span><span class="sxs-lookup"><span data-stu-id="4855d-120">Considerations for Chrome</span></span>

<span data-ttu-id="4855d-121">Om du vill använda S/MIME i Outlook på webben i webbläsaren Google Chrome måste du (eller någon annan administratör) ange och konfigurera Chromium-principen med namnet **ExtensionInstallForcelist** för att installera Microsoft S/MIME-tillägget i Chrome.</span><span class="sxs-lookup"><span data-stu-id="4855d-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="4855d-122">Principvärdet är `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="4855d-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="4855d-123">Observera också att det krävs domänbaserade datorer för att kunna använda den här principen, så att du måste använda S/MIME i Chrome på ett effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="4855d-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="4855d-124">Mer information om **policyn ExtensionInstallForcelist** finns [i ExtensionInstallForcelist.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)</span><span class="sxs-lookup"><span data-stu-id="4855d-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="4855d-125">Det här steget krävs för att använda Chrome. Den ersätter inte den S/MIME-kontroll som installeras av användare.</span><span class="sxs-lookup"><span data-stu-id="4855d-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="4855d-126">Användare uppmanas att ladda ned och installera S/MIME-kontrollen i Outlook på webben vid första användningen av S/MIME.</span><span class="sxs-lookup"><span data-stu-id="4855d-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="4855d-127">Användare kan också proaktivt gå till **S/MIME** i sina Outlook på webben-inställningar för att få nedladdningslänken för kontrollen.</span><span class="sxs-lookup"><span data-stu-id="4855d-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="4855d-128">Mer information</span><span class="sxs-lookup"><span data-stu-id="4855d-128">For more information</span></span>

[<span data-ttu-id="4855d-129">S/MIME för signering och kryptering av meddelanden</span><span class="sxs-lookup"><span data-stu-id="4855d-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
