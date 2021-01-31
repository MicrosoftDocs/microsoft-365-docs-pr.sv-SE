---
title: Använda en QR-kod för att logga in på Outlook Mobile-apparna
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Lär dig hur du använder en QR-kod för att autentisera och ladda ned Outlook Mobile.
ms.openlocfilehash: 2d62a49b93fa7bd5f2d747525de7244e8014e6a7
ms.sourcegitcommit: b8e9b2ecdc4927b67088c5fffb1585424c66fb10
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50050784"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="5804d-103">Använda en QR-kod för att logga in på Outlook Mobile-apparna</span><span class="sxs-lookup"><span data-stu-id="5804d-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5804d-104">Den här Microsoft 365-funktionen är en offentlig förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="5804d-104">This Microsoft 365 feature is in public preview.</span></span> <span data-ttu-id="5804d-105">Offentlig förhandsversion ger tidig åtkomst till Microsoft 365-funktioner.</span><span class="sxs-lookup"><span data-stu-id="5804d-105">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="5804d-106">Som Microsoft 365-administratör kan du låta användarna logga in på Outlook för Android- eller iOS-appen på sina mobila enheter utan att behöva ange sitt användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="5804d-106">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="5804d-107">Genom att skanna en QR-kod kan användare autentisera och logga in i Outlook Mobile på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="5804d-107">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="5804d-108">I Outlook på webben eller andra Outlook-skrivbordsprogram kanske användarna ser meddelanden om att de kan använda Outlook på sina mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="5804d-108">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="5804d-109">De här meddelandena kan hanteras av administratören med Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="5804d-109">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="5804d-110">Om användare väljer att själva skicka ett SMS för att ladda ned appen på sin mobila enhet visas en QR-kod på datorn.</span><span class="sxs-lookup"><span data-stu-id="5804d-110">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="5804d-111">De kommer att kunna skanna QR-koden för att logga in i Outlook på sin telefon eller surfplatta.</span><span class="sxs-lookup"><span data-stu-id="5804d-111">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="5804d-112">Den här QR-koden är ett kort löst token som bara kan lösas in en gång.</span><span class="sxs-lookup"><span data-stu-id="5804d-112">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="5804d-113">I vissa fall måste användarna autentisera igen på sin dator för att kunna generera QR-koden.</span><span class="sxs-lookup"><span data-stu-id="5804d-113">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="5804d-114">Använda Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="5804d-114">Use Exchange PowerShell</span></span>

<span data-ttu-id="5804d-115">Den här upplevelsen är på som standard.</span><span class="sxs-lookup"><span data-stu-id="5804d-115">This experience is on by default.</span></span> <span data-ttu-id="5804d-116">Följ stegen nedan om du vill inaktivera den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="5804d-116">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="5804d-117">[Anslut till Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="5804d-117">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="5804d-118">Med PowerShell kan du inaktivera meddelanden som informerar användarna om Outlook-mobilapparna.</span><span class="sxs-lookup"><span data-stu-id="5804d-118">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="5804d-119">Det förhindrar också att inloggningsflödet för QR-kod visas.</span><span class="sxs-lookup"><span data-stu-id="5804d-119">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-Organization -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="5804d-120">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="5804d-120">Related topics</span></span>

[<span data-ttu-id="5804d-121">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="5804d-121">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)