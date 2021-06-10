---
title: Omdirigering av konton Office 365 Säkerhets- och efterlevnadscenter till det nya Microsoft 365 Defender
description: Hur du omdirigerar från Defender för Office 365 att Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Komma igång med Microsoft 365 Defender, omdirigering av säkerhetscenter
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842531"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a><span data-ttu-id="eacd2-104">Omdirigera konton från Säkerhets- Office 365 Säkerhets- och efterlevnadscenter till Defender Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eacd2-104">Redirecting accounts from Office 365 Security and Compliance Center to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="eacd2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="eacd2-105">**Applies to:**</span></span>

- <span data-ttu-id="eacd2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eacd2-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="eacd2-107">Defender förr Office 365</span><span class="sxs-lookup"><span data-stu-id="eacd2-107">Defender for Office 365</span></span>

<span data-ttu-id="eacd2-108">Den här artikeln förklarar hur du dirigerar konton till Microsoft 365 Defender genom att aktivera automatisk omdirigering från det tidigare säkerhets- och efterlevnadscentret för Office 365 (protection.office.com) till Microsoft 365 Defender (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="eacd2-108">This article explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Office 365 Security and Compliance Center (protection.office.com), to Microsoft 365 Defender (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="eacd2-109">Vad du kan förvänta dig</span><span class="sxs-lookup"><span data-stu-id="eacd2-109">What to expect</span></span>
<span data-ttu-id="eacd2-110">När automatisk omdirigering har aktiverats och aktiverats dirigeras användare som har åtkomst till säkerhetsrelaterade funktioner i Office 365 Security and Compliance (protection.office.com) automatiskt till Microsoft 365 Defender ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="eacd2-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to Microsoft 365 Defender (https://security.microsoft.com).</span></span>  

<span data-ttu-id="eacd2-111">Läs mer om vad som har ändrats: [Microsoft Defender för Office 365 i Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="eacd2-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="eacd2-112">När automatisk omdirigering är aktiverad dirigeras användarna till Microsoft 365 Defender när de använder säkerhetsfunktionerna i Office 365 Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="eacd2-112">With automatic redirection turned on, users will be routed to Microsoft 365 Defender when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="eacd2-113">De omfattar funktioner i avsnittet Hothantering och instrumentpanelen och rapporterna för hantering av hot.</span><span class="sxs-lookup"><span data-stu-id="eacd2-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="eacd2-114">Objekt i säkerhets- Office 365 säkerhets- och efterlevnadscentret som inte är relaterade till säkerhet omdirigeras inte till Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="eacd2-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to Microsoft 365 Defender.</span></span>

<span data-ttu-id="eacd2-115">Efterlevnadsrelaterade objekt finns i Microsoft 365 efterlevnadscenter, och e-postflödesrelaterade objekt finns Exchange administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="eacd2-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="eacd2-116">Alla andra funktioner, oavsett om de är efterlevnadsrelaterade eller funktioner som fungerar för båda, påverkas inte av omdirigering.</span><span class="sxs-lookup"><span data-stu-id="eacd2-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="eacd2-117">Office 365 säkerhetsvarningar visas i både Defender Microsoft 365 och Säkerhets- och efterlevnadscenter för Office 365, utan omdirigering.</span><span class="sxs-lookup"><span data-stu-id="eacd2-117">Office 365 security alerts appear in both Microsoft 365 Defender and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="eacd2-118">Konfigurera portalomdirigering</span><span class="sxs-lookup"><span data-stu-id="eacd2-118">Set up portal redirection</span></span>
<span data-ttu-id="eacd2-119">Om du vill börja dirigera konton till Microsoft 365 Defender på security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="eacd2-119">To start routing accounts to Microsoft 365 Defender at security.microsoft.com:</span></span>

1. <span data-ttu-id="eacd2-120">Kontrollera att du är global administratör eller har säkerhetsadministratörsbehörigheter i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eacd2-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="eacd2-121">[Logga in](https://security.microsoft.com/) på Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="eacd2-121">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>
3. <span data-ttu-id="eacd2-122">Gå till **Inställningar**  >  **e-& omdirigering till**  >  **samarbetsportalen.**</span><span class="sxs-lookup"><span data-stu-id="eacd2-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="eacd2-123">Ändra inställningen för automatisk omdirigering till **På**.</span><span class="sxs-lookup"><span data-stu-id="eacd2-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="eacd2-124">Klicka **på Aktivera** om du vill använda automatisk omdirigering Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="eacd2-124">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

> [!NOTE]
> <span data-ttu-id="eacd2-125">När omdirigering har aktiverats matas konton i aktiva sessioner medan den här inställningen används inte från sessionen och dirigeras bara till Microsoft 365 Defender när den aktuella sessionen avslutas och loggar in igen.</span><span class="sxs-lookup"><span data-stu-id="eacd2-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="eacd2-126">Kan jag använda den tidigare portalen igen?</span><span class="sxs-lookup"><span data-stu-id="eacd2-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="eacd2-127">Om något inte fungerar för dig eller om det finns något som du inte kan slutföra via Microsoft 365 Defender vill vi höra mer om det med hjälp av feedback-alternativet för portalen.</span><span class="sxs-lookup"><span data-stu-id="eacd2-127">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="eacd2-128">Om du har stött på problem med omdirigering får du gärna meddela oss.</span><span class="sxs-lookup"><span data-stu-id="eacd2-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="eacd2-129">Så här återgår du till den tidigare portalen:</span><span class="sxs-lookup"><span data-stu-id="eacd2-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="eacd2-130">[Logga in](https://security.microsoft.com/) på Microsoft 365 Defender som global administratör eller med ett konto med säkerhetsadministratörsbehörigheter i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eacd2-130">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="eacd2-131">Gå till **Inställningar**  >  **e-& omdirigering till**  >  **samarbetsportalen.**</span><span class="sxs-lookup"><span data-stu-id="eacd2-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="eacd2-132">Ändra inställningen för automatisk omdirigering till **Av**.</span><span class="sxs-lookup"><span data-stu-id="eacd2-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="eacd2-133">Klicka **på Inaktivera** & dela feedback när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="eacd2-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="eacd2-134">Den här inställningen kan aktiveras igen när som helst.</span><span class="sxs-lookup"><span data-stu-id="eacd2-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="eacd2-135">När de har inaktiverats kommer konton inte längre att dirigeras till security.microsoft.com och du kommer återigen att ha åtkomst till den tidigare portalen – securitycenter.windows.com eller securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="eacd2-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal—securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="eacd2-136">Relaterad information</span><span class="sxs-lookup"><span data-stu-id="eacd2-136">Related information</span></span>
- [<span data-ttu-id="eacd2-137">Microsoft 365 Defender-översikt</span><span class="sxs-lookup"><span data-stu-id="eacd2-137">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="eacd2-138">Microsoft Defender för slutpunkt i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eacd2-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="eacd2-139">Microsoft levererar unified SIEM och XDR för att modernisera säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="eacd2-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="eacd2-140">Infografik av XDR kontra SIEM</span><span class="sxs-lookup"><span data-stu-id="eacd2-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="eacd2-141">Nya Defender</span><span class="sxs-lookup"><span data-stu-id="eacd2-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="eacd2-142">Om Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eacd2-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="eacd2-143">Microsofts säkerhetsportaler och administrationscenter</span><span class="sxs-lookup"><span data-stu-id="eacd2-143">Microsoft security portals and admin centers</span></span>](portals.md)
