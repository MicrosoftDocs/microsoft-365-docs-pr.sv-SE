---
title: Aktivera modern autentisering för Office 2013 på Windows-enheter
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Lär dig att ange registernycklar för att aktivera modern autentisering för enheter som Microsoft Office 2013 installerat.
ms.openlocfilehash: d358cb2ffb4284a51779e5a7c1dc894052b9ebc0
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572291"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="0978f-103">Aktivera modern autentisering för Office 2013 på Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="0978f-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="0978f-104">Om du vill aktivera modern autentisering för Windows-enheter som har Office 2013 installerat, måste du ange specifika registernycklar.</span><span class="sxs-lookup"><span data-stu-id="0978f-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="0978f-105">Aktivera modern autentisering för Office 2013-klienter</span><span class="sxs-lookup"><span data-stu-id="0978f-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="0978f-106">Modern autentisering redan är aktiverad för Office 2016-klienter så du behöver inte ange registernycklar för Office 2016.</span><span class="sxs-lookup"><span data-stu-id="0978f-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="0978f-p101">Om du vill aktivera modern autentisering för enheter med Windows (till exempel på bärbara datorer och surfplattor), som har Microsoft Office 2013 installerat, måste du ange följande registernycklar. Registernycklarna måste anges på varje enhet som du vill aktivera för modern autentisering:</span><span class="sxs-lookup"><span data-stu-id="0978f-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="0978f-109">**Registernyckel**</span><span class="sxs-lookup"><span data-stu-id="0978f-109">**Registry key**</span></span>|<span data-ttu-id="0978f-110">**Typ**</span><span class="sxs-lookup"><span data-stu-id="0978f-110">**Type**</span></span>|<span data-ttu-id="0978f-111">**Värde**</span><span class="sxs-lookup"><span data-stu-id="0978f-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="0978f-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="0978f-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="0978f-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0978f-113">REG_DWORD</span></span>  |<span data-ttu-id="0978f-114">1</span><span class="sxs-lookup"><span data-stu-id="0978f-114">1</span></span>  |
|<span data-ttu-id="0978f-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="0978f-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="0978f-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0978f-116">REG_DWORD</span></span> |<span data-ttu-id="0978f-117">1</span><span class="sxs-lookup"><span data-stu-id="0978f-117">1</span></span> |
   
<span data-ttu-id="0978f-118">När du har ställt in registernycklarna kan du ställa Office 2013-enhetsappar för [att använda MFA (Multifactor Authentication)](set-up-multi-factor-authentication.md) med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0978f-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="0978f-p102">Om du för närvarande är inloggad med något av klientprogrammen måste du logga ut och logga in igen för att ändringen ska börja gälla. I annat fall är MRU- och roaminginställningarna otillgängliga tills ADAL-identiteten har upprättats.</span><span class="sxs-lookup"><span data-stu-id="0978f-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="0978f-121">Inaktivera modern autentisering på enheter</span><span class="sxs-lookup"><span data-stu-id="0978f-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="0978f-122">Du inaktiverar modern autentisering på en enhet genom att ange följande registernycklar på enheten:</span><span class="sxs-lookup"><span data-stu-id="0978f-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="0978f-123">**Registernyckel**</span><span class="sxs-lookup"><span data-stu-id="0978f-123">**Registry key**</span></span>|<span data-ttu-id="0978f-124">**Typ**</span><span class="sxs-lookup"><span data-stu-id="0978f-124">**Type**</span></span>|<span data-ttu-id="0978f-125">**Värde**</span><span class="sxs-lookup"><span data-stu-id="0978f-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="0978f-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="0978f-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="0978f-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="0978f-127">REG_DWORD</span></span>|<span data-ttu-id="0978f-128">0</span><span class="sxs-lookup"><span data-stu-id="0978f-128">0</span></span>|
   
## <a name="related-content"></a><span data-ttu-id="0978f-129">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="0978f-129">Related content</span></span>

<span data-ttu-id="0978f-130">[Logga in på Office 2013 med en andra verifieringsmetod](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (artikel)</span><span class="sxs-lookup"><span data-stu-id="0978f-130">[Sign in to Office 2013 with a second verification method](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (article)</span></span>

<span data-ttu-id="0978f-131">[Outlook för lösenord och använder inte modern autentisering för att ansluta till Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (artikel)</span><span class="sxs-lookup"><span data-stu-id="0978f-131">[Outlook prompts for password and doesn't use Modern Authentication to connect to Office 365](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) (article)</span></span>

