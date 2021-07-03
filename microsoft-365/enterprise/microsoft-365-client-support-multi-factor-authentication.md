---
title: 'Microsoft 365 Stöd för klientprogram: Multifaktorautentisering'
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: I den här artikeln lär du dig vilka plattformar, klienter och PowerShell-moduler som har stöd för multifaktorautentisering för Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8749c05e3f7ce5dacf7d3ed1eaa46a46a20482d5
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286459"
---
# <a name="microsoft-365-client-app-support-multi-factor-authentication"></a><span data-ttu-id="07115-103">Microsoft 365 Stöd för klientprogram: Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="07115-103">Microsoft 365 Client App Support: Multi-factor authentication</span></span>

<span data-ttu-id="07115-104">*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="07115-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="07115-105">För att ge ytterligare säkerhetsnivå för inloggningar kan klienter vara konfigurerade för att använda multifaktorautentisering (MFA), som använder både ett användarlösenord och en annan metod för användarverifiering baserat på:</span><span class="sxs-lookup"><span data-stu-id="07115-105">To provide an additional level of security for sign-ins, clients may be configured to use multi-factor authentication (MFA), which uses both a user password and another user verification method based on:</span></span>

- <span data-ttu-id="07115-106">En man som äger den är inte lätt duplicerad, till exempel en smartphone.</span><span class="sxs-lookup"><span data-stu-id="07115-106">Something  in their possession that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="07115-107">Något som användaren har unikt och korrekt, till exempel fingeravtryck, ansikte eller annat biometriskt attribut</span><span class="sxs-lookup"><span data-stu-id="07115-107">Something the user has uniquely and biologically, such as their fingerprints, face, or other biometric attribute</span></span>

<span data-ttu-id="07115-108">Läs mer om [multifaktorautentisering](/azure/active-directory/authentication/multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="07115-108">Learn more about [multi-factor authentication](/azure/active-directory/authentication/multi-factor-authentication).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="07115-109">Klienter som stöds & plattformar</span><span class="sxs-lookup"><span data-stu-id="07115-109">Supported clients & platforms</span></span>

<span data-ttu-id="07115-110">De senaste versionerna av följande klienter och plattformar har stöd för multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="07115-110">The latest versions of the following clients and platforms support multi-factor authentication.</span></span> <span data-ttu-id="07115-111">Mer information om plattformsstöd i Microsoft 365 finns i [Systemkrav för Microsoft 365.](/microsoft-365/microsoft-365-and-office-resources)</span><span class="sxs-lookup"><span data-stu-id="07115-111">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Multi-factor authentication services support table](../includes/microsoft-365-client-support-modern-authentication-include.md)]

## <a name="supported-powershell-modules"></a><span data-ttu-id="07115-112">PowerShell-moduler som stöds</span><span class="sxs-lookup"><span data-stu-id="07115-112">Supported PowerShell modules</span></span>

- [<span data-ttu-id="07115-113">Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="07115-113">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview)
- [<span data-ttu-id="07115-114">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="07115-114">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="07115-115">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="07115-115">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
