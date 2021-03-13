---
title: Aktivera modern autentisering för Office 2013 på Windows-enheter
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Lär dig ange registernycklar för att aktivera modern autentisering för enheter som har Microsoft Office 2013 installerat.
ms.openlocfilehash: 2a4be82328d391db7808cb9197ce259275b567c6
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "50758934"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="ff7b2-103">Aktivera modern autentisering för Office 2013 på Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="ff7b2-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="ff7b2-104">Om du vill aktivera modern autentisering för Windows-enheter som har Office 2013 installerat, måste du ange specifika registernycklar.</span><span class="sxs-lookup"><span data-stu-id="ff7b2-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="ff7b2-105">Aktivera modern autentisering för Office 2013-klienter</span><span class="sxs-lookup"><span data-stu-id="ff7b2-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="ff7b2-106">Modern autentisering redan är aktiverad för Office 2016-klienter så du behöver inte ange registernycklar för Office 2016.</span><span class="sxs-lookup"><span data-stu-id="ff7b2-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="ff7b2-p101">Om du vill aktivera modern autentisering för enheter med Windows (till exempel på bärbara datorer och surfplattor), som har Microsoft Office 2013 installerat, måste du ange följande registernycklar. Registernycklarna måste anges på varje enhet som du vill aktivera för modern autentisering:</span><span class="sxs-lookup"><span data-stu-id="ff7b2-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="ff7b2-109">**Registernyckel**</span><span class="sxs-lookup"><span data-stu-id="ff7b2-109">**Registry key**</span></span>|<span data-ttu-id="ff7b2-110">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ff7b2-110">**Type**</span></span>|<span data-ttu-id="ff7b2-111">**Värde**</span><span class="sxs-lookup"><span data-stu-id="ff7b2-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="ff7b2-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="ff7b2-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="ff7b2-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="ff7b2-113">REG_DWORD</span></span>  |<span data-ttu-id="ff7b2-114">1</span><span class="sxs-lookup"><span data-stu-id="ff7b2-114">1</span></span>  |
|<span data-ttu-id="ff7b2-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="ff7b2-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="ff7b2-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="ff7b2-116">REG_DWORD</span></span> |<span data-ttu-id="ff7b2-117">1</span><span class="sxs-lookup"><span data-stu-id="ff7b2-117">1</span></span> |
   
<span data-ttu-id="ff7b2-118">När du har angett registernycklarna kan du ange att Office 2013-enhetsprogram ska använda multifaktorautentisering [(MFA)](set-up-multi-factor-authentication.md) med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff7b2-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="ff7b2-p102">Om du för närvarande är inloggad med något av klientprogrammen måste du logga ut och logga in igen för att ändringen ska börja gälla. I annat fall är MRU- och roaminginställningarna otillgängliga tills ADAL-identiteten har upprättats.</span><span class="sxs-lookup"><span data-stu-id="ff7b2-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="ff7b2-121">Inaktivera modern autentisering på enheter</span><span class="sxs-lookup"><span data-stu-id="ff7b2-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="ff7b2-122">Du inaktiverar modern autentisering på en enhet genom att ange följande registernycklar på enheten:</span><span class="sxs-lookup"><span data-stu-id="ff7b2-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="ff7b2-123">**Registernyckel**</span><span class="sxs-lookup"><span data-stu-id="ff7b2-123">**Registry key**</span></span>|<span data-ttu-id="ff7b2-124">**Typ**</span><span class="sxs-lookup"><span data-stu-id="ff7b2-124">**Type**</span></span>|<span data-ttu-id="ff7b2-125">**Värde**</span><span class="sxs-lookup"><span data-stu-id="ff7b2-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="ff7b2-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="ff7b2-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="ff7b2-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="ff7b2-127">REG_DWORD</span></span>|<span data-ttu-id="ff7b2-128">0</span><span class="sxs-lookup"><span data-stu-id="ff7b2-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="ff7b2-129">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ff7b2-129">Related articles</span></span>
[<span data-ttu-id="ff7b2-130">Logga in på Office 2013 med en andra metod för verifiering</span><span class="sxs-lookup"><span data-stu-id="ff7b2-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[<span data-ttu-id="ff7b2-131">Outlook uppmanar dig att ange lösenord och använder inte modern autentisering för att ansluta till Office 365</span><span class="sxs-lookup"><span data-stu-id="ff7b2-131">Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365</span></span>](https://docs.microsoft.com/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)

  
