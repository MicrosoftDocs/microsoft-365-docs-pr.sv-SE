---
title: Felsöka AutoPilot-enhetsfel
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Lär dig hur du felsöker fel som kan visas när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business Premium.
ms.openlocfilehash: 0c0742e5bf17c85cedfb421cabfd87c0e2184ba5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635053"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="e2ff8-103">Felsöka AutoPilot-enhetsfel</span><span class="sxs-lookup"><span data-stu-id="e2ff8-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="e2ff8-104">Felmeddelanden för enhetsfil</span><span class="sxs-lookup"><span data-stu-id="e2ff8-104">Device file error messages</span></span>

<span data-ttu-id="e2ff8-105">Här finns information om några av de fel som kan visas när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="e2ff8-106">**Felkod**</span><span class="sxs-lookup"><span data-stu-id="e2ff8-106">**Error code**</span></span>|<span data-ttu-id="e2ff8-107">**Åtgärdat för att försöka**</span><span class="sxs-lookup"><span data-stu-id="e2ff8-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e2ff8-108">Ogiltig begärandetext</span><span class="sxs-lookup"><span data-stu-id="e2ff8-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="e2ff8-109">Det här felet bör inträffa sällan, om du ser det här felet, försök åtgärden igen.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="e2ff8-110">Maskinvaruhhh-värdet för en enhet är inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="e2ff8-111">Om det här felet visas betyder det att värdet som du angav i CSV-filen för maskinvaruhhen för en enhet inte är korrekt.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="e2ff8-112">Kontrollera först att värdet har skrivits korrekt.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="e2ff8-113">Om du tror att värdet är korrekt, men det här felet fortfarande händer, fråga maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="e2ff8-114">Enhet som tilldelats en annan klient</span><span class="sxs-lookup"><span data-stu-id="e2ff8-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="e2ff8-115">Om du ser det här felet betyder det att värdet som du angav i CSV-filen för antingen serienumret eller produktnyckeln för en eller flera enheter inte är korrekt.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="e2ff8-116">Kontrollera först att värdet har skrivits korrekt.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="e2ff8-117">Om du tror att värdet är korrekt, men det här felet fortfarande händer, fråga maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="e2ff8-118">CSV-filen innehåller ett ogiltigt serienummer eller produktnyckel</span><span class="sxs-lookup"><span data-stu-id="e2ff8-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="e2ff8-119">Om du ser det här felet betyder det att enheten du försöker registrera redan är registrerad av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="e2ff8-120">Lös det här felet genom att be maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="e2ff8-121">Den här enheten stöds inte för installation med autopilot</span><span class="sxs-lookup"><span data-stu-id="e2ff8-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="e2ff8-122">Det här felet innebär att enheten inte uppfyller distributionskraven för Autopilot.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="e2ff8-123">Enheter måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="e2ff8-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="e2ff8-124">Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="e2ff8-125">Nya enheter som inte har varit via Windows out-of-box-upplevelse.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="e2ff8-126">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="e2ff8-126">Device not found</span></span>  <br/> |<span data-ttu-id="e2ff8-127">Det här felet innebär att en eller flera enheter i CSV-filen inte är registrerade i din organisation.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="e2ff8-128">Du kan åtgärda detta genom att be maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="e2ff8-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
