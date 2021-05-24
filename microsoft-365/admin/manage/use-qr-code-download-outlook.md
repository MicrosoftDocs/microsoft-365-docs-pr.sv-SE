---
title: Använd en QR-kod för att logga in Outlook mobilapparna
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
description: Lär dig hur du använder en QR-kod för att autentisera och ladda ned Outlook mobil.
ms.openlocfilehash: 2c1853a6ea1dd1a5d2ad30b975d1dbd23b942040
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636004"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="7b8c7-103">Använd en QR-kod för att logga in Outlook mobilapparna</span><span class="sxs-lookup"><span data-stu-id="7b8c7-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b8c7-104">Den här funktionen är endast tillgänglig för organisationer som har aktiverat Riktad version Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-104">This feature is only available to organizations that have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7b8c7-105">Om du vill aktivera Riktad version och lära dig mer om hur det fungerar kan [du läsa Konfigurera alternativen Standard eller Riktad version.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="7b8c7-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="7b8c7-106">Vi kommer att utöka till fler organisationer under de kommande veckorna via en offentlig förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="7b8c7-107">Offentlig förhandsgranskning ger tidig åtkomst Microsoft 365 funktioner.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="7b8c7-108">Som Microsoft 365 kan du göra det möjligt för användarna att logga in på Outlook för Android- eller iOS-appen på sina mobila enheter utan att behöva ange sitt användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="7b8c7-109">Genom att skanna en QR-kod kan användarna autentisera och logga in på Outlook mobil.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="7b8c7-110">I Outlook på webben eller andra datorprogram Outlook kan användare se meddelanden om att de kan använda Outlook sina mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="7b8c7-111">De här meddelandena kan hanteras av administratören med hjälp Exchange Powershell.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="7b8c7-112">Om användare väljer att själva SMS ett SMS för att ladda ned appen på sin mobila enhet visas en QR-kod på datorn.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="7b8c7-113">De kommer att kunna skanna QR-koden för att logga in Outlook sin telefon eller surfplatta.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="7b8c7-114">Den här QR-koden är en kort token som endast kan lösas in en gång.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="7b8c7-115">I vissa fall måste användarna autentisera sig igen på datorn för att QR-koden ska skapas.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-115">In some cases, your users must re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="7b8c7-116">Använda Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b8c7-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="7b8c7-117">Den här funktionen är på som standard.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-117">This feature is on by default.</span></span> <span data-ttu-id="7b8c7-118">Följ stegen nedan om du vill inaktivera den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="7b8c7-119">[Anslut till Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="7b8c7-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="7b8c7-120">Med PowerShell kan du inaktivera meddelanden som informerar användarna om Outlook-mobilapparna.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="7b8c7-121">Det förhindrar också att inloggningsflödet för QR-koden visas.</span><span class="sxs-lookup"><span data-stu-id="7b8c7-121">This also prevents the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a><span data-ttu-id="7b8c7-122">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="7b8c7-122">Related content</span></span>

<span data-ttu-id="7b8c7-123">[Konfigurera alternativen Standard eller Riktad version](release-options-in-office-365.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="7b8c7-123">[Set up the Standard or Targeted release options](release-options-in-office-365.md) (article)</span></span>\
<span data-ttu-id="7b8c7-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (artikel)</span><span class="sxs-lookup"><span data-stu-id="7b8c7-124">[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (article)</span></span>