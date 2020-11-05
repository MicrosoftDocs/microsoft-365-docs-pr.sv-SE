---
title: Vanliga frågor och svar när du aktiverar Microsoft 365 Defender
description: Få svar på de vanligaste frågorna om licensiering, behörigheter, inledande inställningar och andra produkter och tjänster relaterade till att aktivera Microsoft 365 Defender
keywords: Vanliga frågor, FAQ, GCC, kom igång, aktivera MTP, Microsoft Threat Protection, M365, säkerhet, data plats, nödvändiga behörigheter, licens kvalificering, sidan Inställningar
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3dae9f208f5bb08d694322eb9f7cff35986930da
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920496"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a><span data-ttu-id="30e68-104">Vanliga frågor och svar när du aktiverar Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30e68-104">Frequently asked questions when turning on Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="30e68-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="30e68-105">**Applies to:**</span></span>
- <span data-ttu-id="30e68-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30e68-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="30e68-107">Läs svar på de vanligaste frågorna om att aktivera [Microsoft 365 Defender](microsoft-threat-protection.md), inklusive nödvändiga licenser och behörigheter, distribuera Support tjänster och Start Inställningar.</span><span class="sxs-lookup"><span data-stu-id="30e68-107">Read responses to the most commonly asked questions about turning on [Microsoft 365 Defender](microsoft-threat-protection.md), including required licenses and permissions, deploying support services, and initial settings.</span></span>

<span data-ttu-id="30e68-108">Instruktioner om hur du aktiverar tjänsten finns [i Aktivera Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="30e68-108">For instructions on how to turn on the service, [read Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a><span data-ttu-id="30e68-109">Jag har ingen Microsoft 365 E5-licens.</span><span class="sxs-lookup"><span data-stu-id="30e68-109">I don’t have a Microsoft 365 E5 license.</span></span> <span data-ttu-id="30e68-110">Kan jag fortfarande använda Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="30e68-110">Can I still use Microsoft 365 Defender?</span></span>

<span data-ttu-id="30e68-111">Kunder med följande icke-E5 licenser kan använda Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="30e68-111">Customers with the following non-E5 licenses can use Microsoft 365 Defender:</span></span>

- <span data-ttu-id="30e68-112">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="30e68-112">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="30e68-113">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="30e68-113">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="30e68-114">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="30e68-114">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="30e68-115">Defender för Office 365 (abonnemang 2)</span><span class="sxs-lookup"><span data-stu-id="30e68-115">Defender for Office 365 (Plan 2)</span></span>
 
<span data-ttu-id="30e68-116">En fullständig lista över licenser som stöds finns i [licensierings kraven](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="30e68-116">For a full list of supported licenses, [read the licensing requirements](prerequisites.md#licensing-requirements).</span></span>

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a><span data-ttu-id="30e68-117">Behöver jag installera eller distribuera något för att komma igång med Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="30e68-117">Do I need to install or deploy anything to start using Microsoft 365 Defender?</span></span>

<span data-ttu-id="30e68-118">Nej, Microsoft 365 Defender konsoliderar data från Microsoft 365-säkerhetstjänster som du redan har distribuerat.</span><span class="sxs-lookup"><span data-stu-id="30e68-118">No, Microsoft 365 Defender consolidates data from Microsoft 365 security services that you have already deployed.</span></span> <span data-ttu-id="30e68-119">När du har aktiverat det kommer incident-, automatiserings-och jakt upplevelser att fungera inom omfattningen för de distribuerade produkterna.</span><span class="sxs-lookup"><span data-stu-id="30e68-119">Once you turn it on, incident, automation, and hunting experiences will start working within the scope of the deployed products.</span></span> <span data-ttu-id="30e68-120">Om ingen av de här produkterna distribueras korrekt visas inga data i Microsoft 365 Defender och det går inte att vidta någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="30e68-120">If none of these products are properly deployed, Microsoft 365 Defender will not display any data and is unable to take any action.</span></span>

<span data-ttu-id="30e68-121">För att optimera din Microsoft 365 Defender-upplevelse rekommenderar vi att du distribuerar *alla* [Microsoft 365-säkerhetsprodukter och-tjänster](deploy-supported-services.md)som stöds.</span><span class="sxs-lookup"><span data-stu-id="30e68-121">To optimize your Microsoft 365 Defender experiences, we recommend deploying *all* supported [Microsoft 365 security products and services](deploy-supported-services.md).</span></span>

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a><span data-ttu-id="30e68-122">Var är Microsoft 365 Defender och lagrar mina data?</span><span class="sxs-lookup"><span data-stu-id="30e68-122">Where does Microsoft 365 Defender process and store my data?</span></span>
<span data-ttu-id="30e68-123">Microsoft 365 Defender väljer automatiskt en optimal plats för data centret där konsoliderade data behandlas och lagras.</span><span class="sxs-lookup"><span data-stu-id="30e68-123">Microsoft 365 Defender automatically selects an optimal location for the data center where consolidated data is processed and stored.</span></span> <span data-ttu-id="30e68-124">Om du har Microsoft Defender för slut punkt väljer den platsen som används av Defender för slut punkten.</span><span class="sxs-lookup"><span data-stu-id="30e68-124">If you have Microsoft Defender for Endpoint, it selects the same location used by Defender for Endpoint.</span></span>

>[!NOTE]
><span data-ttu-id="30e68-125">Microsoft Defender för slut punkt tillhandahåller automatiskt bestämmelser i EU-datacenter när de aktive ras via Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="30e68-125">Microsoft Defender for Endpoint automatically provisions in European Union (EU) data centers when turned on through Azure Defender.</span></span> <span data-ttu-id="30e68-126">Microsoft 365 Defender tillhandahåller automatiskt samma EU-datacentertjänster för kunder som har etablerat Microsoft Defender för slut punkter på det här sättet.</span><span class="sxs-lookup"><span data-stu-id="30e68-126">Microsoft 365 Defender will automatically provision in the same EU data center for customers who have provisioned Microsoft Defender for Endpoint in this manner.</span></span> 

<span data-ttu-id="30e68-127">Data Center platsen visas innan och efter det att tjänsten har etablerats på inställnings sidan för Microsoft 365 Defender ( **inställningar > Microsoft 365 Defender** ).</span><span class="sxs-lookup"><span data-stu-id="30e68-127">The data center location is shown before and after the service is provisioned in the settings page for Microsoft 365 Defender ( **Settings > Microsoft 365 Defender** ).</span></span> <span data-ttu-id="30e68-128">Om du föredrar att använda en annan data Center plats väljer du **behöver hjälp?** i Microsoft 365 säkerhets Center för att kontakta Microsofts support.</span><span class="sxs-lookup"><span data-stu-id="30e68-128">If you prefer to use another data center location, select **Need help?** in the Microsoft 365 security center to contact Microsoft support.</span></span>

## <a name="where-can-i-access-microsoft-365-defender"></a><span data-ttu-id="30e68-129">Var kan jag komma åt Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="30e68-129">Where can I access Microsoft 365 Defender?</span></span>

<span data-ttu-id="30e68-130">Microsoft 365 Defender finns i Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="30e68-130">Microsoft 365 Defender is available in Microsoft 365 security center.</span></span> <span data-ttu-id="30e68-131">Gå till säkerhets Center genom att bläddra till webb adressen [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="30e68-131">To go to the security center, browse to the URL [https://security.microsoft.com](https://security.microsoft.com).</span></span>

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a><span data-ttu-id="30e68-132">Vilka behörigheter behöver jag för att få åtkomst till Microsoft 365 Defender i Microsoft 365 säkerhets Center?</span><span class="sxs-lookup"><span data-stu-id="30e68-132">What permissions do I need to access Microsoft 365 Defender in Microsoft 365 security center?</span></span>

<span data-ttu-id="30e68-133">Konton tilldelade följande Azure Active Directory (AD)-roller kan komma åt Microsoft 365 Defender-funktioner och-data:</span><span class="sxs-lookup"><span data-stu-id="30e68-133">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>

- <span data-ttu-id="30e68-134">Global administratör</span><span class="sxs-lookup"><span data-stu-id="30e68-134">Global administrator</span></span>
- <span data-ttu-id="30e68-135">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="30e68-135">Security administrator</span></span>
- <span data-ttu-id="30e68-136">Säkerhets ansvarig</span><span class="sxs-lookup"><span data-stu-id="30e68-136">Security Operator</span></span>
- <span data-ttu-id="30e68-137">Global läsare</span><span class="sxs-lookup"><span data-stu-id="30e68-137">Global Reader</span></span>
- <span data-ttu-id="30e68-138">Säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="30e68-138">Security Reader</span></span>

>[!NOTE]
><span data-ttu-id="30e68-139">Rollbaserad åtkomst kontroll inställningar i Microsoft Defender för slut punkten påverkar åtkomsten till data.</span><span class="sxs-lookup"><span data-stu-id="30e68-139">Role-based access control settings in Microsoft Defender for Endpoint influence access to data.</span></span> <span data-ttu-id="30e68-140">Mer information finns i [Hantera åtkomst till Microsoft 365 Defender](mtp-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="30e68-140">For more information, read about [managing access to Microsoft 365 Defender](mtp-permissions.md).</span></span>

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a><span data-ttu-id="30e68-141">Vilken tidszon är Microsoft 365 Defender standard?</span><span class="sxs-lookup"><span data-stu-id="30e68-141">What time zone does Microsoft 365 Defender default to?</span></span>
<span data-ttu-id="30e68-142">Som standard visar Microsoft 365 Defender tidsinformation i UTC-tidszonen.</span><span class="sxs-lookup"><span data-stu-id="30e68-142">By default, Microsoft 365 Defender displays time information in the UTC time zone.</span></span> <span data-ttu-id="30e68-143">Du kan ändra den här inställningen för att använda din lokala tidszon.</span><span class="sxs-lookup"><span data-stu-id="30e68-143">You can change this setting to use your local time zone.</span></span> [<span data-ttu-id="30e68-144">Lär dig hur du ställer in tids zonen</span><span class="sxs-lookup"><span data-stu-id="30e68-144">Learn about setting the time zone</span></span>](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a><span data-ttu-id="30e68-145">Hur kan jag lära dig mer om nya funktioner och UI-uppdateringar för Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="30e68-145">How can I learn about new Microsoft 365 Defender feature and UI updates?</span></span>

<span data-ttu-id="30e68-146">Microsoft ger regelbundet information via de olika kanalerna, bland annat:</span><span class="sxs-lookup"><span data-stu-id="30e68-146">Microsoft regularly provides information through the various channels, including:</span></span>

- <span data-ttu-id="30e68-147">[Meddelande Center](../../admin/manage/message-center.md) i administrations Center för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="30e68-147">The [message center](../../admin/manage/message-center.md) in Microsoft 365 admin center</span></span>
- <span data-ttu-id="30e68-148">Blogposts i [microsofts 365 säkerhets &-kompatibilitet teknisk community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span><span class="sxs-lookup"><span data-stu-id="30e68-148">Blogposts in the [Microsoft 365 security & compliance tech community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)</span></span>

<span data-ttu-id="30e68-149">Få de senaste allmänt tillgängliga upplevelserna genom att aktivera [förhands gransknings funktionerna](preview.md).</span><span class="sxs-lookup"><span data-stu-id="30e68-149">Get the latest publicly available experiences by turning on [preview features](preview.md).</span></span>

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="30e68-150">Är Microsoft 365 Defender tillgängligt för AMERIKANSKt community-moln (GCC) eller GCC High?</span><span class="sxs-lookup"><span data-stu-id="30e68-150">Is Microsoft 365 Defender available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="30e68-151">För tillfället är den inte tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="30e68-151">At the moment, it is not available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="30e68-152">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="30e68-152">Related topics</span></span>

- [<span data-ttu-id="30e68-153">Översikt över Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30e68-153">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- <span data-ttu-id="30e68-154">[Aktivera Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="30e68-154">[Turn on Microsoft 365 Defender](mtp-enable.md).</span></span>
- [<span data-ttu-id="30e68-155">Licens krav och andra förutsättningar</span><span class="sxs-lookup"><span data-stu-id="30e68-155">Licensing requirements and other prerequisites</span></span>](prerequisites.md)
- [<span data-ttu-id="30e68-156">Distribuera tjänster som stöds</span><span class="sxs-lookup"><span data-stu-id="30e68-156">Deploy supported services</span></span>](deploy-supported-services.md)
- [<span data-ttu-id="30e68-157">Aktivera förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="30e68-157">Turn on preview features</span></span>](preview.md)
