---
title: Felsöka AutoPilot-enhetsfel
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Läs om hur du felsöker fel i Autopilotenhetsfiler.
ms.openlocfilehash: 1b5358bd6686c2548e82ec5297ac0ad675835718
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2019
ms.locfileid: "38718708"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="61784-103">Felsöka AutoPilot-enhetsfel</span><span class="sxs-lookup"><span data-stu-id="61784-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="61784-104">Felmeddelanden för enhetsfil</span><span class="sxs-lookup"><span data-stu-id="61784-104">Device file error messages</span></span>

<span data-ttu-id="61784-105">Här är information om några av de fel som du kan se när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="61784-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="61784-106">**Felkod**</span><span class="sxs-lookup"><span data-stu-id="61784-106">**Error code**</span></span>|<span data-ttu-id="61784-107">**Fix för att försöka**</span><span class="sxs-lookup"><span data-stu-id="61784-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="61784-108">Ogiltigt begäranbrödtext</span><span class="sxs-lookup"><span data-stu-id="61784-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="61784-109">Det här felet bör inträffa sällan, om du ser det här felet, försök igen.</span><span class="sxs-lookup"><span data-stu-id="61784-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="61784-110">Maskinvaru-hash-värde för en enhet är inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="61784-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="61784-111">Om du ser det här felet innebär det att värdet som du angav i CSV-filen för maskinvaru-hash för en enhet inte är korrekt.</span><span class="sxs-lookup"><span data-stu-id="61784-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="61784-112">Kontrollera först att värdet har skrivits korrekt.</span><span class="sxs-lookup"><span data-stu-id="61784-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="61784-113">Om du tror att värdet är korrekt, men det här felet fortfarande händer, be maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="61784-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="61784-114">Enhet tilldelad till en annan klientorganisation</span><span class="sxs-lookup"><span data-stu-id="61784-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="61784-115">Om du ser det här felet betyder det att värdet som du angav i CSV-filen för antingen serienumret eller produktnyckeln för en eller flera enheter inte är korrekt.</span><span class="sxs-lookup"><span data-stu-id="61784-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="61784-116">Kontrollera först att värdet har skrivits korrekt.</span><span class="sxs-lookup"><span data-stu-id="61784-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="61784-117">Om du tror att värdet är korrekt, men det här felet fortfarande händer, be maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="61784-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="61784-118">CSV-filen innehåller ett ogiltigt serienummer eller produkt nyckel</span><span class="sxs-lookup"><span data-stu-id="61784-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="61784-119">Om du ser det här felet innebär det att enheten som du försöker registrera redan har registrerats av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="61784-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="61784-120">Om du vill åtgärda det här felet kan du be maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="61784-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="61784-121">Den här enheten stöds inte för installation med hjälp av AutoPilot</span><span class="sxs-lookup"><span data-stu-id="61784-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="61784-122">Det här felet innebär att enheten inte uppfyller Autopilotdistributionskrav.</span><span class="sxs-lookup"><span data-stu-id="61784-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="61784-123">Enheter måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="61784-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="61784-124">Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="61784-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="61784-125">Nya enheter som inte har gått igenom Windows out-of-Box-upplevelse.</span><span class="sxs-lookup"><span data-stu-id="61784-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="61784-126">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="61784-126">Device not found</span></span>  <br/> |<span data-ttu-id="61784-127">Det här felet innebär att en eller flera enheter i CSV-filen inte är registrerade i din organisation.</span><span class="sxs-lookup"><span data-stu-id="61784-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="61784-128">Du åtgärdar detta genom att be maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="61784-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
