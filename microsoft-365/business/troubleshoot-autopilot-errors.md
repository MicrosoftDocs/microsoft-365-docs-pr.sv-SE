---
title: Felsöka AutoPilot-enhetsfel
f1.keywords:
- NOCSH
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Läs om hur du felsöker fel som kan visas när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business.
ms.openlocfilehash: 7569f18097a1f5959b3dd491958c78886e1e05d6
ms.sourcegitcommit: 41c0bc5cf50f4ca63b4286d1ea0f58ab82984b7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547480"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="f958b-103">Felsöka AutoPilot-enhetsfel</span><span class="sxs-lookup"><span data-stu-id="f958b-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="f958b-104">Felmeddelanden i enhetsfiler</span><span class="sxs-lookup"><span data-stu-id="f958b-104">Device file error messages</span></span>

<span data-ttu-id="f958b-105">Här är information om några av de fel du kan se när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="f958b-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="f958b-106">**Felkod**</span><span class="sxs-lookup"><span data-stu-id="f958b-106">**Error code**</span></span>|<span data-ttu-id="f958b-107">**Fix för att prova**</span><span class="sxs-lookup"><span data-stu-id="f958b-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f958b-108">Ogiltigt begärandeorgan</span><span class="sxs-lookup"><span data-stu-id="f958b-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="f958b-109">Det här felet bör inträffa sällan, om du ser det här felet, försök åtgärden igen.</span><span class="sxs-lookup"><span data-stu-id="f958b-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="f958b-110">Maskinvaruhash-värdet för en enhet är inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="f958b-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="f958b-111">Om det här felet visas betyder det att värdet du angav i CSV-filen för maskinvaruhash för en enhet inte är korrekt.</span><span class="sxs-lookup"><span data-stu-id="f958b-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="f958b-112">Kontrollera först att värdet har skrivits korrekt.</span><span class="sxs-lookup"><span data-stu-id="f958b-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="f958b-113">Om du tror att värdet är korrekt, men det här felet fortfarande pågår, ber du maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="f958b-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="f958b-114">Enhet som tilldelats en annan klient</span><span class="sxs-lookup"><span data-stu-id="f958b-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="f958b-115">Om det här felet visas betyder det att värdet du angav i CSV-filen för antingen serienumret eller produktnyckeln för en eller flera enheter inte är korrekt.</span><span class="sxs-lookup"><span data-stu-id="f958b-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="f958b-116">Kontrollera först att värdet har skrivits korrekt.</span><span class="sxs-lookup"><span data-stu-id="f958b-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="f958b-117">Om du tror att värdet är korrekt, men det här felet fortfarande pågår, ber du maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="f958b-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="f958b-118">CSV-filen innehåller ett ogiltigt serienummer eller produktnyckel</span><span class="sxs-lookup"><span data-stu-id="f958b-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="f958b-119">Om felet visas betyder det att enheten som du försöker registrera redan är registrerad av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="f958b-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="f958b-120">Om du vill åtgärda det här felet ber du maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="f958b-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="f958b-121">Den här enheten stöds inte för installation med hjälp av AutoPilot</span><span class="sxs-lookup"><span data-stu-id="f958b-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="f958b-122">Det här felet innebär att enheten inte uppfyller AutoPilot-distributionskraven.</span><span class="sxs-lookup"><span data-stu-id="f958b-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="f958b-123">Enheter måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="f958b-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="f958b-124">Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="f958b-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="f958b-125">Nya enheter som inte har gått igenom Windows out-of-box-upplevelse.</span><span class="sxs-lookup"><span data-stu-id="f958b-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="f958b-126">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="f958b-126">Device not found</span></span>  <br/> |<span data-ttu-id="f958b-127">Det här felet innebär att en eller flera enheter i CSV-filen inte är registrerad i din organisation.</span><span class="sxs-lookup"><span data-stu-id="f958b-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="f958b-128">Om du vill åtgärda detta ber du maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="f958b-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
