---
title: Omdirigera konton från Microsoft Defender för Slutpunkt till Microsoft 365 Defender
description: Hur du omdirigerar konton och sessioner från Defender för Slutpunkt till Microsoft 365 Defender.
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
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842572"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a><span data-ttu-id="9bcc2-104">Omdirigera konton från Microsoft Defender för Slutpunkt till Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bcc2-104">Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9bcc2-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9bcc2-105">**Applies to:**</span></span>
- <span data-ttu-id="9bcc2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bcc2-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="9bcc2-107">Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9bcc2-107">Defender for Endpoint</span></span>

<span data-ttu-id="9bcc2-108">I enlighet med Microsofts metod för olika domäner för skydd mot hot med SIEM och XDR (Extended detection and response) har vi bytte namn till Microsoft Defender Avancerat skydd som Microsoft Defender för Endpoint och enhetligt det till en enda integrerad portal – Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - Microsoft 365 Defender.</span></span>

<span data-ttu-id="9bcc2-109">I den här guiden förklaras hur du dirigerar konton till Microsoft 365 Defender genom att aktivera automatisk omdirigering från den tidigare Microsoft Defender för Slutpunktsportalen (securitycenter.windows.com eller securitycenter.microsoft.com) till Microsoft 365 Defender-portalen (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="9bcc2-109">This guide explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to Microsoft 365 Defender portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="9bcc2-110">Microsoft Defender för slutpunkt i Microsoft 365 Defender har stöd för att bevilja åtkomst till hanterade säkerhetstjänstleverantörer [(MSSP: er)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) på samma sätt som åtkomst beviljas i [Microsoft Defender säkerhetscenter.](./mssp-access.md)</span><span class="sxs-lookup"><span data-stu-id="9bcc2-110">Microsoft Defender for Endpoint in Microsoft 365 Defender supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="9bcc2-111">Vad du kan förvänta dig</span><span class="sxs-lookup"><span data-stu-id="9bcc2-111">What to expect</span></span>
<span data-ttu-id="9bcc2-112">När automatisk omdirigering har aktiverats dirigeras konton med åtkomst till den tidigare Microsoft Defender för Slutpunktsportalen i securitycenter.windows.com eller securitycenter.microsoft.com automatiskt till Microsoft 365 Defender-portalen på security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to Microsoft 365 Defender portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="9bcc2-113">Läs mer om vad som har ändrats: [Microsoft Defender för slutpunkt i Microsoft 365 Defender](microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="9bcc2-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="9bcc2-114">Det inkluderar omdirigering för direkt åtkomst till den tidigare portalen via webbläsare, inklusive länkar som pekar mot den tidigare securitycenter.windows.com-portalen – till exempel länkar i e-postmeddelanden och länkar som returneras av SIEM API-anrop.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="9bcc2-115">Externa länkar från e-postaviseringar eller SIEM-API:er innehåller för närvarande länkar till båda portalerna.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="9bcc2-116">När omdirigeringen är aktiverad pekar båda länkarna på Microsoft 365 Defender tills den gamla länken tas bort så småningom.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-116">Once redirection is enabled, both links will point to Microsoft 365 Defender until the old link is eventually removed.</span></span> <span data-ttu-id="9bcc2-117">Vi rekommenderar att du använder den nya länken som pekar på Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-117">We encourage you to adopt the new link pointing to Microsoft 365 Defender.</span></span>

<span data-ttu-id="9bcc2-118">Se tabellen nedan för mer information om länkar och routning.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="9bcc2-119">SIEM API-routning</span><span class="sxs-lookup"><span data-stu-id="9bcc2-119">SIEM API routing</span></span>

|<span data-ttu-id="9bcc2-120">**Egenskap**</span><span class="sxs-lookup"><span data-stu-id="9bcc2-120">**Property**</span></span>  |<span data-ttu-id="9bcc2-121">**Mål när omdirigering är AV**</span><span class="sxs-lookup"><span data-stu-id="9bcc2-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="9bcc2-122">**Mål när omdirigering är PÅ**</span><span class="sxs-lookup"><span data-stu-id="9bcc2-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="9bcc2-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="9bcc2-123">LinkToWDATP</span></span> | <span data-ttu-id="9bcc2-124">Aviseringssida i securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="9bcc2-125">Aviseringssida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="9bcc2-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="9bcc2-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="9bcc2-127">Incidentsida i securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="9bcc2-128">Incidentsida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="9bcc2-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="9bcc2-129">LinkToMTP</span></span> | <span data-ttu-id="9bcc2-130">Aviseringssida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="9bcc2-131">Aviseringssida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="9bcc2-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="9bcc2-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="9bcc2-133">Incidentsida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="9bcc2-134">Incidentsida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="9bcc2-135">E-postaviseringar</span><span class="sxs-lookup"><span data-stu-id="9bcc2-135">Email alert notifications</span></span>

|<span data-ttu-id="9bcc2-136">**Egenskap**</span><span class="sxs-lookup"><span data-stu-id="9bcc2-136">**Property**</span></span>  |<span data-ttu-id="9bcc2-137">**Mål när omdirigering är AV**</span><span class="sxs-lookup"><span data-stu-id="9bcc2-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="9bcc2-138">**Mål när omdirigering är PÅ**</span><span class="sxs-lookup"><span data-stu-id="9bcc2-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="9bcc2-139">Aviseringssida</span><span class="sxs-lookup"><span data-stu-id="9bcc2-139">Alert page</span></span>  | <span data-ttu-id="9bcc2-140">Aviseringssida i securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="9bcc2-141">Aviseringssida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="9bcc2-142">Incidentsida</span><span class="sxs-lookup"><span data-stu-id="9bcc2-142">Incident page</span></span>  |<span data-ttu-id="9bcc2-143">Incidentsida i securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="9bcc2-144">Incidentsida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="9bcc2-145">Aviseringssida i säkerhetscenterportalen</span><span class="sxs-lookup"><span data-stu-id="9bcc2-145">Alert page in security center portal</span></span> | <span data-ttu-id="9bcc2-146">Aviseringssida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="9bcc2-147">Aviseringssida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="9bcc2-148">Incidentsida i säkerhetscenterportalen</span><span class="sxs-lookup"><span data-stu-id="9bcc2-148">Incident page in security center portal</span></span> | <span data-ttu-id="9bcc2-149">Incidentsida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="9bcc2-150">Incidentsida i security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9bcc2-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="9bcc2-151">När får detta effekt?</span><span class="sxs-lookup"><span data-stu-id="9bcc2-151">When does this take effect?</span></span> 
<span data-ttu-id="9bcc2-152">När den är aktiverad kan uppdateringen börja gälla nästan omedelbart för vissa konton.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="9bcc2-153">Men omdirigeringen kan ta längre tid att sprida till alla konton i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="9bcc2-154">Konton i aktiva sessioner medan den här inställningen används matas inte ut från deras session och kommer bara att dirigeras till Microsoft 365 Defender när den aktuella sessionen avslutas och loggar in igen.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="9bcc2-155">Konfigurera portalomdirigering</span><span class="sxs-lookup"><span data-stu-id="9bcc2-155">Set up portal redirection</span></span>
<span data-ttu-id="9bcc2-156">Så här börjar du dirigera konton Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="9bcc2-156">To start routing accounts to Microsoft 365 Defender:</span></span>
1. <span data-ttu-id="9bcc2-157">Kontrollera att du är global administratör eller har säkerhetsadministratörsbehörigheter i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9bcc2-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="9bcc2-158">[Logga in](https://security.microsoft.com/) på Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-158">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>

3. <span data-ttu-id="9bcc2-159">Gå till **Inställningar**  >  **Endpoints**  >  **General**  >  **Portal-omdirigering eller** klicka [här](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="9bcc2-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="9bcc2-160">Ändra inställningen för automatisk omdirigering till **På**.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="9bcc2-161">Klicka **på Aktivera** om du vill använda automatisk omdirigering Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-161">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

>[!IMPORTANT]
><span data-ttu-id="9bcc2-162">Aktivering av den här inställningen avbryts inte aktiva användarsessioner.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="9bcc2-163">Konton som befinner sig i en aktiv session medan den här inställningen används dirigeras endast till Microsoft 365 Defender efter att den aktuella sessionen avslutas och loggar in igen.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-163">Accounts who are in an active session while this setting is applied will only be directed to Microsoft 365 Defender after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="9bcc2-164">Du måste vara global administratör eller ha säkerhetsadministratörsbehörighet i Azure Active Directory aktivera eller inaktivera den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="9bcc2-165">Kan jag använda den tidigare portalen igen?</span><span class="sxs-lookup"><span data-stu-id="9bcc2-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="9bcc2-166">Om något inte fungerar för dig eller om det finns något som du inte kan slutföra via Microsoft 365 Defender vill vi höra om det.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-166">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it.</span></span> <span data-ttu-id="9bcc2-167">Om du har stött på problem med omdirigering rekommenderar vi att du berättar det för oss med hjälp av formuläret för att skicka feedback.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="9bcc2-168">Så här återgår du till den tidigare Microsoft Defender för Endpoint-portalen:</span><span class="sxs-lookup"><span data-stu-id="9bcc2-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="9bcc2-169">[Logga in](https://security.microsoft.com/) på Microsoft 365 Defender som global administratör eller med ett konto med säkerhetsadministratörsbehörigheter i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-169">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="9bcc2-170">Gå till **Inställningar**  >  **Huvudportalens**  >    >  **omdirigering eller** [öppna sidan här](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="9bcc2-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="9bcc2-171">Ändra inställningen för automatisk omdirigering till **Av**.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="9bcc2-172">Klicka **på Inaktivera** & dela feedback när du uppmanas att göra det.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="9bcc2-173">Den här inställningen kan aktiveras igen när som helst.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="9bcc2-174">När de har inaktiverats kommer konton inte längre att dirigeras till security.microsoft.com och du kommer återigen att ha åtkomst till den tidigare portalen – securitycenter.windows.com eller securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9bcc2-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="9bcc2-175">Relaterad information</span><span class="sxs-lookup"><span data-stu-id="9bcc2-175">Related information</span></span>
- [<span data-ttu-id="9bcc2-176">Microsoft 365 Defender-översikt</span><span class="sxs-lookup"><span data-stu-id="9bcc2-176">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="9bcc2-177">Microsoft Defender för slutpunkt i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bcc2-177">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="9bcc2-178">Microsoft levererar unified SIEM och XDR för att modernisera säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="9bcc2-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="9bcc2-179">Infografik av XDR kontra SIEM</span><span class="sxs-lookup"><span data-stu-id="9bcc2-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="9bcc2-180">Nya Defender</span><span class="sxs-lookup"><span data-stu-id="9bcc2-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="9bcc2-181">Om Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bcc2-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="9bcc2-182">Microsofts säkerhetsportaler och administrationscenter</span><span class="sxs-lookup"><span data-stu-id="9bcc2-182">Microsoft security portals and admin centers</span></span>](portals.md)