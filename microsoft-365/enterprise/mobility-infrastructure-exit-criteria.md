---
title: Exitkriterier för hantering av mobila enheter
description: Microsoft 365 Enterprise inkluderar hantering av mobila enheter med Microsoft Intune. Granska kraven och förutsättningarna, konfigurera Intune med din Azure Active Directory-resurs, registrera iOS-, macOS-, Android- och Windows-enheter, distribuera appar, skapa en konfigurera profil, använda en efterlevnadsprincip och aktivera villkorlig åtkomst för mobila enheter enhetshantering med Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-dokumentation, hantering av mobila enheter, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 3e8013426983584783488e6f937f8ba5b02d7a1a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805628"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a><span data-ttu-id="c4ac4-105">Exitkriterier för hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="c4ac4-105">Mobile device management infrastructure exit criteria</span></span>

![Fas 5: Hantering av mobila enheter](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

<span data-ttu-id="c4ac4-107">*Detta gäller E3- och E5-versionerna av Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c4ac4-107">*This applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c4ac4-108">Se till att konfigurationen uppfyller följande krav för infrastruktur för hantering av mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="c4ac4-108">Ensure that your configuration meets the following requirements for mobile device management infrastructure.</span></span>

- <span data-ttu-id="c4ac4-109">Intune är konfigurerat, inklusive skapandet av Azure Active Directory (Azure AD) användare och grupper för att tillämpa organisationens regler för enheter.</span><span class="sxs-lookup"><span data-stu-id="c4ac4-109">Intune is set up, including the creation of Azure Active Directory (Azure AD) users and groups to apply your organization's rules for devices.</span></span>
- <span data-ttu-id="c4ac4-110">Du har registrerat enheter i Intune så att enheterna kan ta emot de principer du skapar.</span><span class="sxs-lookup"><span data-stu-id="c4ac4-110">You have enrolled devices in Intune so that the devices can receive the policies you create.</span></span>
- <span data-ttu-id="c4ac4-111">Appar läggs till på enheter så att användarna får åtkomst till organisationens Microsoft 365-molntjänster, till exempel Exchange Online och SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c4ac4-111">Apps are added to devices so your users get access to your organization's Microsoft 365 cloud services, such as Exchange Online and SharePoint Online.</span></span>
- <span data-ttu-id="c4ac4-112">Funktioner och inställningar konfigureras och tillämpas på dina enheter med hjälp av Azure AD-användare och grupper som du skapar, vilket kan innefatta att aktivera antivirusprogram och begränsa specifika appar.</span><span class="sxs-lookup"><span data-stu-id="c4ac4-112">Features and settings are configured and applied to your devices using the Azure AD users and groups you create, which might include enabling anti-virus and restricting specific apps.</span></span>
- <span data-ttu-id="c4ac4-113">Efterlevnadsprinciper finns för att kräva en brandvägg eller en lösenordslängd på en enhet.</span><span class="sxs-lookup"><span data-stu-id="c4ac4-113">Compliance policies are in place to require a firewall or a password length on a device.</span></span> <span data-ttu-id="c4ac4-114">Om enheterna inte är kompatibla blockerar villkorlig åtkomst åtkomst till organisationens data.</span><span class="sxs-lookup"><span data-stu-id="c4ac4-114">If devices aren't compliant, Conditional Access blocks access to your organization's data.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="c4ac4-115">Resultat och nästa steg</span><span class="sxs-lookup"><span data-stu-id="c4ac4-115">Results and next steps</span></span>

<span data-ttu-id="c4ac4-116">Dina enheter är registrerade i Intune och konfigureras med lämpliga principer.</span><span class="sxs-lookup"><span data-stu-id="c4ac4-116">Your devices are enrolled in Intune and configured with the appropriate policies.</span></span>

|||
|:-------|:-----|
|![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| <span data-ttu-id="c4ac4-118">Om du följer faserna för distributionen från slutna till slutskede av Microsoft 365 Enterprise är nästa fas [informationsskydd](infoprotect-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="c4ac4-118">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [information protection](infoprotect-infrastructure.md).</span></span> |
