---
title: Felsöka AutoPilot-enhetsfel
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Lär dig hur du felsöker fel som kan visas när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business Premium.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578096"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="bb3f4-103">Felsöka AutoPilot-enhetsfel</span><span class="sxs-lookup"><span data-stu-id="bb3f4-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="bb3f4-104">Felmeddelanden om enhetsfil</span><span class="sxs-lookup"><span data-stu-id="bb3f4-104">Device file error messages</span></span>

<span data-ttu-id="bb3f4-105">Här finns information om några av de fel som kan visas när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="bb3f4-106">**Felkod**</span><span class="sxs-lookup"><span data-stu-id="bb3f4-106">**Error code**</span></span>|<span data-ttu-id="bb3f4-107">**Prova genom att åtgärda**</span><span class="sxs-lookup"><span data-stu-id="bb3f4-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bb3f4-108">Ogiltig begärans brödtext</span><span class="sxs-lookup"><span data-stu-id="bb3f4-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="bb3f4-109">Det här felet bör sällan inträffa om du ser det här felet och prova åtgärden igen.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="bb3f4-110">Maskinvaruhashvärdet för en enhet är inte rätt.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="bb3f4-111">Om du ser det här felet innebär det att värdet du angav i CSV-filen för maskinvaruhash för en enhet inte är rätt.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="bb3f4-112">Kontrollera först att värdet har skrivits in korrekt.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="bb3f4-113">Om du tror att värdet är rätt, men det här felet kvarstår, ber du din maskinvaruleverantör om hjälp.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="bb3f4-114">Enhet tilldelad till en annan klientorganisation</span><span class="sxs-lookup"><span data-stu-id="bb3f4-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="bb3f4-115">Om du ser det här felet innebär det att värdet som du angav i CSV-filen för antingen serienumret eller produktnyckeln för en eller flera enheter inte är korrekt.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="bb3f4-116">Kontrollera först att värdet har skrivits in korrekt.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="bb3f4-117">Om du tror att värdet är rätt, men det här felet kvarstår, ber du din maskinvaruleverantör om hjälp.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="bb3f4-118">CSV-filen innehåller ett ogiltigt serienummer eller produktnyckel</span><span class="sxs-lookup"><span data-stu-id="bb3f4-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="bb3f4-119">Om du ser det här felet innebär det att enheten som du försöker registrera redan är registrerad av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="bb3f4-120">Om du vill åtgärda det här felet ber du din maskinvaruleverantör om hjälp.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="bb3f4-121">Den här enheten stöds inte för konfiguration med hjälp av AutoPilot</span><span class="sxs-lookup"><span data-stu-id="bb3f4-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="bb3f4-122">Det här felet innebär att enheten inte uppfyller AutoPilot-distributionskraven.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="bb3f4-123">Enheter måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="bb3f4-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="bb3f4-124">Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="bb3f4-125">Nya enheter som inte redan Windows kommer att vara helt nya.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="bb3f4-126">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="bb3f4-126">Device not found</span></span>  <br/> |<span data-ttu-id="bb3f4-127">Det här felet innebär att en eller flera enheter i CSV-filen inte är registrerade i din organisation.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="bb3f4-128">Om du vill lösa detta ber du din maskinvaruleverantör om hjälp.</span><span class="sxs-lookup"><span data-stu-id="bb3f4-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
