---
title: Felsöka AutoPilot-enhetsfel
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Lär dig felsöka AutoPilot enhet filfel.
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982749"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="8c8f4-103">Felsöka AutoPilot-enhetsfel</span><span class="sxs-lookup"><span data-stu-id="8c8f4-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="8c8f4-104">Meddelanden om filfel enhet</span><span class="sxs-lookup"><span data-stu-id="8c8f4-104">Device file error messages</span></span>

<span data-ttu-id="8c8f4-105">Här är info om fel visas när du arbetar med filer i Microsoft 365 Business AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="8c8f4-106">**Felkod**</span><span class="sxs-lookup"><span data-stu-id="8c8f4-106">**Error code**</span></span>|<span data-ttu-id="8c8f4-107">**Att försöka åtgärda**</span><span class="sxs-lookup"><span data-stu-id="8c8f4-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8c8f4-108">Ogiltig begäran brödtext</span><span class="sxs-lookup"><span data-stu-id="8c8f4-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="8c8f4-109">Detta fel bör inträffa sällan, om du ser felet, försök igen.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="8c8f4-110">Maskinvaru-hashvärdet för en enhet inte är korrekt.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="8c8f4-p101">Om det här felet visas innebär det att det värde som du angav i CSV-filen för maskinvaru-hash av en enhet inte är korrekt. Kontrollera först att värdet är korrekt. Om du tror att värdet är korrekt, men det här felet sker fortfarande fråga maskinvaruleverantören för hjälp.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-p101">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="8c8f4-114">Enhet som är tilldelad till en annan innehavare</span><span class="sxs-lookup"><span data-stu-id="8c8f4-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="8c8f4-p102">Om det här felet visas innebär det att värdet som anges i CSV-filen för serienumret eller produktnyckeln för en eller flera enheter inte är korrekt. Kontrollera först att värdet är korrekt. Om du tror att värdet är korrekt, men det här felet sker fortfarande fråga maskinvaruleverantören för hjälp.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-p102">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="8c8f4-118">CSV-filen innehåller ett ogiltigt serienummer eller produktnyckel</span><span class="sxs-lookup"><span data-stu-id="8c8f4-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="8c8f4-p103">Om du ser felet innebär det att enheten som uppstod när du registrerar redan registrerats av en annan organisation. Lös problemet genom att be maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-p103">If you see this error it means that the device you are tyring to register is already registered by an other organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="8c8f4-121">Den här enheten stöds inte för installation med hjälp av AutoPilot</span><span class="sxs-lookup"><span data-stu-id="8c8f4-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="8c8f4-p104">Detta fel innebär att enheten inte uppfyller kraven för distribution av AutoPilot. Enheter måste uppfylla dessa krav:</span><span class="sxs-lookup"><span data-stu-id="8c8f4-p104">This error means the device does not meet AutoPilot deployment requirements. Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="8c8f4-124">Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="8c8f4-125">Nya enheter som inte har genomgått Windows välkomstprogram.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="8c8f4-126">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="8c8f4-126">Device not found</span></span>  <br/> |<span data-ttu-id="8c8f4-p105">Detta fel innebär att en eller flera enheter i CSV-filen inte har registrerats för din organisation. Lös problemet genom att be maskinvaruleverantören om hjälp.</span><span class="sxs-lookup"><span data-stu-id="8c8f4-p105">This error means that one or more devices in your CSV file is not registered to your organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
