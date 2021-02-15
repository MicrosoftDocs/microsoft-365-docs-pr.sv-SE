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
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242360"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="9447e-103">Använda en QR-kod för att logga in på Outlook Mobile-apparna</span><span class="sxs-lookup"><span data-stu-id="9447e-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9447e-104">Den här funktionen är endast tillgänglig för organisationer som har aktiverat riktad version i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9447e-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9447e-105">Mer information om hur du aktiverar Riktad version finns i Konfigurera standard- eller [riktad version.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="9447e-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="9447e-106">Vi kommer att utöka till fler organisationer under de kommande veckorna via en offentlig förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="9447e-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="9447e-107">Offentlig förhandsversion ger tidig åtkomst till Microsoft 365-funktioner.</span><span class="sxs-lookup"><span data-stu-id="9447e-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="9447e-108">Som Microsoft 365-administratör kan du låta användarna logga in på Outlook för Android- eller iOS-appen på sina mobila enheter utan att behöva ange sitt användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="9447e-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="9447e-109">Genom att skanna en QR-kod kan användarna autentisera och logga in på Outlook Mobile på ett säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="9447e-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="9447e-110">I Outlook på webben eller andra Outlook-skrivbordsprogram kanske användarna ser meddelanden om att de kan använda Outlook på sina mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="9447e-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="9447e-111">De här meddelandena kan hanteras av administratören med Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="9447e-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="9447e-112">Om användare väljer att själva skicka ett SMS för att ladda ned appen på sin mobila enhet visas en QR-kod på datorn.</span><span class="sxs-lookup"><span data-stu-id="9447e-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="9447e-113">De kommer att kunna skanna QR-koden för att logga in i Outlook på sin telefon eller surfplatta.</span><span class="sxs-lookup"><span data-stu-id="9447e-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="9447e-114">Den här QR-koden är ett kort löst token som bara kan lösas in en gång.</span><span class="sxs-lookup"><span data-stu-id="9447e-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="9447e-115">I vissa fall måste användarna autentisera igen på sin dator för att kunna generera QR-koden.</span><span class="sxs-lookup"><span data-stu-id="9447e-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="9447e-116">Använda Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="9447e-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="9447e-117">Den här funktionen är på som standard.</span><span class="sxs-lookup"><span data-stu-id="9447e-117">This feature is on by default.</span></span> <span data-ttu-id="9447e-118">Följ stegen nedan om du vill inaktivera den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="9447e-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="9447e-119">[Anslut till Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="9447e-119">[Connect to Exchange PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="9447e-120">Med PowerShell kan du inaktivera meddelanden som informerar användarna om Outlook-mobilapparna.</span><span class="sxs-lookup"><span data-stu-id="9447e-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="9447e-121">Det förhindrar också att inloggningsflödet för QR-kod visas.</span><span class="sxs-lookup"><span data-stu-id="9447e-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="9447e-122">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9447e-122">Related topics</span></span>

[<span data-ttu-id="9447e-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="9447e-123">Set-OrganizationConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
