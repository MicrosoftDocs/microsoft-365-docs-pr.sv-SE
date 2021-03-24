---
title: Omdirigera konton från Microsoft Defender för Office 365 till det nya säkerhetscentret för Microsoft 365
description: Omdirigera från Defender för Office 365 till Microsoft 365 Säkerhetscenter.
keywords: Microsoft 365 Säkerhetscenter, Komma igång med Microsoft 365 säkerhetscenter, omdirigering av säkerhetscenter
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072681"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="52771-104">Omdirigera konton från Microsoft Defender för Office 365 till Säkerhetscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="52771-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="52771-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="52771-105">**Applies to:**</span></span>

- <span data-ttu-id="52771-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52771-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="52771-107">Defender förr Office 365</span><span class="sxs-lookup"><span data-stu-id="52771-107">Defender for Office 365</span></span>

<span data-ttu-id="52771-108">I den här artikeln förklaras hur du dirigerar konton till Microsoft 365 säkerhetscenter genom att aktivera automatisk omdirigering från Microsofts tidigare säkerhets- och efterlevnadscenter (protection.office.com eller securitycenter.microsoft.com) till Microsoft 365 säkerhetscenter (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="52771-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

>[!NOTE]
> <span data-ttu-id="52771-109">Funktionen för portalomdirigering är endast tillgänglig för Office 365 E5 och Microsoft Defender för Office P2-kunder</span><span class="sxs-lookup"><span data-stu-id="52771-109">Portal redirection capability is available for Office 365 E5 and Microsoft Defender for Office P2 customers only</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="52771-110">Vad du kan förvänta dig</span><span class="sxs-lookup"><span data-stu-id="52771-110">What to expect</span></span>
<span data-ttu-id="52771-111">När automatisk omdirigering har aktiverats och aktiverats dirigeras användare som har åtkomst till säkerhetsrelaterade funktioner i Office 365 säkerhet och efterlevnad (protection.office.com) automatiskt till Säkerhetscenter för Microsoft 365 https://security.microsoft.com) (.</span><span class="sxs-lookup"><span data-stu-id="52771-111">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="52771-112">Läs mer om vad som har ändrats: [Microsoft Defender för Office 365 i Säkerhetscenter för Microsoft 365.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="52771-112">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="52771-113">När automatisk omdirigering är aktiverat dirigeras användarna till Säkerhetscenter för Microsoft 365 när de använder säkerhetsfunktioner i Säkerhets- och efterlevnadscenter för Office 365.</span><span class="sxs-lookup"><span data-stu-id="52771-113">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="52771-114">De omfattar funktioner i avsnittet Hothantering och instrumentpanelen och rapporterna för hantering av hot.</span><span class="sxs-lookup"><span data-stu-id="52771-114">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="52771-115">Objekt i Säkerhets- och efterlevnadscenter för Office 365 som inte är relaterade till säkerhet omdirigeras inte till Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="52771-115">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="52771-116">Efterlevnadsrelaterade objekt finns i Efterlevnadscenter för Microsoft 365, och e-postflödesrelaterade objekt finns i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="52771-116">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="52771-117">Alla andra funktioner, oavsett om de är efterlevnadsrelaterade eller funktioner som fungerar för båda, påverkas inte av omdirigering.</span><span class="sxs-lookup"><span data-stu-id="52771-117">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="52771-118">Office 365-säkerhetsvarningar visas i både Microsoft 365 säkerhetscenter och Office 365 Säkerhets- och efterlevnadscenter, utan omdirigering.</span><span class="sxs-lookup"><span data-stu-id="52771-118">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="52771-119">Konfigurera portalomdirigering</span><span class="sxs-lookup"><span data-stu-id="52771-119">Set up portal redirection</span></span>
<span data-ttu-id="52771-120">Så här börjar du dirigera konton till Säkerhetscenter för Microsoft 365 security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="52771-120">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="52771-121">Kontrollera att du är global administratör eller har säkerhetsadministratörsbehörigheter i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="52771-121">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="52771-122">[Logga in](https://security.microsoft.com/) på Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="52771-122">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="52771-123">Gå till **Inställningar**  >  **E-& omdirigering till**  >  **samarbetsportalen.**</span><span class="sxs-lookup"><span data-stu-id="52771-123">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="52771-124">Ändra inställningen för automatisk omdirigering till **På**.</span><span class="sxs-lookup"><span data-stu-id="52771-124">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="52771-125">Klicka **på Aktivera** om du vill använda automatisk omdirigering på Microsoft 365 Säkerhetscenter-portalen.</span><span class="sxs-lookup"><span data-stu-id="52771-125">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="52771-126">När omdirigering har aktiverats matas konton i aktiva sessioner medan den här inställningen används inte från sessionen och dirigeras bara till Säkerhetscenter för Microsoft 365 när den aktuella sessionen avslutas och loggar in igen.</span><span class="sxs-lookup"><span data-stu-id="52771-126">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="52771-127">Kan jag använda den tidigare portalen igen?</span><span class="sxs-lookup"><span data-stu-id="52771-127">Can I go back to using the former portal?</span></span>
<span data-ttu-id="52771-128">Om något inte fungerar för dig eller om det finns något som du inte kan slutföra via Microsoft 365 Säkerhetscenter-portalen vill vi höra om det med hjälp av alternativet för portalfeedback.</span><span class="sxs-lookup"><span data-stu-id="52771-128">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="52771-129">Om du har stött på problem med omdirigering rekommenderar vi att du når ut till din PM-kompis direkt via privat förhandsgranskning eller berättar det via formuläret för att skicka feedback.</span><span class="sxs-lookup"><span data-stu-id="52771-129">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="52771-130">Så här återgår du till den tidigare portalen:</span><span class="sxs-lookup"><span data-stu-id="52771-130">To revert to the former portal:</span></span>

1. <span data-ttu-id="52771-131">[Logga in](https://security.microsoft.com/) på Microsoft 365 Säkerhetscenter som global administratör eller använd och konto med säkerhetsadministratörsbehörigheter i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="52771-131">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="52771-132">Gå till **Inställningar**  >  **Slutpunkter**  >  **allmän**  >  **portalomdirigering**.</span><span class="sxs-lookup"><span data-stu-id="52771-132">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="52771-133">Ändra inställningen för automatisk omdirigering till **Av**.</span><span class="sxs-lookup"><span data-stu-id="52771-133">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="52771-134">Klicka **på Inaktivera** & dela feedback när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="52771-134">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="52771-135">Den här inställningen kan aktiveras igen när som helst.</span><span class="sxs-lookup"><span data-stu-id="52771-135">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="52771-136">När de har inaktiverats kommer konton inte längre att dirigeras till security.microsoft.com och du kommer återigen att ha åtkomst till den tidigare portalen – securitycenter.windows.com eller securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="52771-136">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="52771-137">Relaterad information</span><span class="sxs-lookup"><span data-stu-id="52771-137">Related information</span></span>
- [<span data-ttu-id="52771-138">Microsoft 365 Säkerhetscenter översikt</span><span class="sxs-lookup"><span data-stu-id="52771-138">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="52771-139">Microsoft Defender för Slutpunkt i Säkerhetscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="52771-139">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="52771-140">Microsoft levererar unified SIEM och XDR för att modernisera säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="52771-140">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="52771-141">Infografik av XDR kontra SIEM</span><span class="sxs-lookup"><span data-stu-id="52771-141">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="52771-142">Nya Defender</span><span class="sxs-lookup"><span data-stu-id="52771-142">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="52771-143">Om Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52771-143">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="52771-144">Microsofts säkerhetsportaler och administrationscenter</span><span class="sxs-lookup"><span data-stu-id="52771-144">Microsoft security portals and admin centers</span></span>](portals.md)