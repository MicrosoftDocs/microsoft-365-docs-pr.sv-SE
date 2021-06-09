---
title: Felsöka onboarding-problem och felmeddelanden
description: Felsöka onboarding-problem och felmeddelande när du slutför installationen av Microsoft Defender för Endpoint.
keywords: felsökning, felsökning, Azure Active Directory, registrering, felmeddelande, felmeddelanden, microsoft defender för slutpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: b8e15f27ffe4babe730870fb576980c62cb0fd59
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844044"
---
# <a name="troubleshoot-subscription-and-portal-access-issues"></a><span data-ttu-id="219ea-104">Felsöka problem med prenumerationer och portalåtkomst</span><span class="sxs-lookup"><span data-stu-id="219ea-104">Troubleshoot subscription and portal access issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="219ea-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="219ea-105">**Applies to:**</span></span>
- [<span data-ttu-id="219ea-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="219ea-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="219ea-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="219ea-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="219ea-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="219ea-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="219ea-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="219ea-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troublshootonboarding-abovefoldlink)

<span data-ttu-id="219ea-110">På den här sidan finns detaljerad information om hur du felsöker problem som kan uppstå när du skaffar Microsoft Defender för slutpunktstjänsten.</span><span class="sxs-lookup"><span data-stu-id="219ea-110">This page provides detailed steps to troubleshoot issues that might occur when setting up your Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="219ea-111">Om du får ett felmeddelande Microsoft Defender Säkerhetscenter en detaljerad förklaring av vad problemet är och relevanta länkar kommer att tillhandahållas.</span><span class="sxs-lookup"><span data-stu-id="219ea-111">If you receive an error message, Microsoft Defender Security Center will provide a detailed explanation on what the issue is and relevant links will be supplied.</span></span>

## <a name="no-subscriptions-found"></a><span data-ttu-id="219ea-112">Inga prenumerationer hittades</span><span class="sxs-lookup"><span data-stu-id="219ea-112">No subscriptions found</span></span>

<span data-ttu-id="219ea-113">Om du får meddelandet Inga prenumerationer  hittades när du använde Microsoft Defender Säkerhetscenter, innebär det att den Azure Active Directory (Azure AD) som användes för att logga in användaren på portalen inte har någon Microsoft Defender för slutpunkt-licens.</span><span class="sxs-lookup"><span data-stu-id="219ea-113">If while accessing Microsoft Defender Security Center you get a **No subscriptions found** message, it means the Azure Active Directory (Azure AD) used to log in the user to the portal, does not have a Microsoft Defender for Endpoint license.</span></span>

<span data-ttu-id="219ea-114">Möjliga orsaker:</span><span class="sxs-lookup"><span data-stu-id="219ea-114">Potential reasons:</span></span>
- <span data-ttu-id="219ea-115">Licenserna Windows E5 Office E5 är separata licenser.</span><span class="sxs-lookup"><span data-stu-id="219ea-115">The Windows E5 and Office E5 licenses are separate licenses.</span></span>
- <span data-ttu-id="219ea-116">Licensen har köpts men inte etablerats till den här Azure AD-instansen.</span><span class="sxs-lookup"><span data-stu-id="219ea-116">The license was purchased but not provisioned to this Azure AD instance.</span></span>
    - <span data-ttu-id="219ea-117">Det kan vara ett problem med licensetablering.</span><span class="sxs-lookup"><span data-stu-id="219ea-117">It could be a license provisioning issue.</span></span>
    - <span data-ttu-id="219ea-118">Det kan vara så att du oavsiktligt har etablerat licensen till ett annat Microsoft Azure AD än den som används för autentisering i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="219ea-118">It could be you inadvertently provisioned the license to a different Microsoft Azure AD than the one used for authentication into the service.</span></span>

<span data-ttu-id="219ea-119">I båda fallen bör du kontakta Microsofts support på [Allmän Microsoft Defender för Endpoint-support eller](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) [volymlicenssupport.](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx)</span><span class="sxs-lookup"><span data-stu-id="219ea-119">For both cases, you should contact Microsoft support at [General Microsoft Defender for Endpoint Support](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636419533611396913) or [Volume license support](https://www.microsoft.com/licensing/servicecenter/Help/Contact.aspx).</span></span>

![Bild av att inga prenumerationer hittades](images/atp-no-subscriptions-found.png)

## <a name="your-subscription-has-expired"></a><span data-ttu-id="219ea-121">Din prenumeration har gått ut</span><span class="sxs-lookup"><span data-stu-id="219ea-121">Your subscription has expired</span></span>

<span data-ttu-id="219ea-122">Om ett meddelande om att din  prenumeration Microsoft Defender Säkerhetscenter du får ett meddelande om att din prenumeration har upphört att gälla när du öppnar ett e-postmeddelande har gått ut har onlinetjänstprenumerationen upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="219ea-122">If while accessing Microsoft Defender Security Center you get a **Your subscription has expired** message, your online service subscription has expired.</span></span> <span data-ttu-id="219ea-123">Microsoft Defender för Endpoint-prenumerationen har, precis som alla andra onlinetjänstprenumerationer, ett utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="219ea-123">Microsoft Defender for Endpoint subscription, like any other online service subscription, has an expiration date.</span></span> 

<span data-ttu-id="219ea-124">Du kan när som helst välja att förnya eller förlänga licensen.</span><span class="sxs-lookup"><span data-stu-id="219ea-124">You can choose to renew or extend the license at any point in time.</span></span> <span data-ttu-id="219ea-125">När du öppnar portalen efter  utgångsdatumet visas meddelandet Din prenumeration har upphört att gälla med ett alternativ för att ladda ned paketet för offboarding på enheten om du väljer att inte förnya licensen.</span><span class="sxs-lookup"><span data-stu-id="219ea-125">When accessing the portal after the expiration date a **Your subscription has expired** message will be presented with an option to download the device offboarding package, should you choose to not renew the license.</span></span>

> [!NOTE]
> <span data-ttu-id="219ea-126">Av säkerhetsskäl upphör paketet som används till Offboard-enheter 30 dagar efter det datum då det laddades ned.</span><span class="sxs-lookup"><span data-stu-id="219ea-126">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="219ea-127">Utgångna offboarding-paket som skickats till en enhet kommer att avvisas.</span><span class="sxs-lookup"><span data-stu-id="219ea-127">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="219ea-128">När du laddar ned ett offboarding-paket meddelas du om paketens utgångsdatum och det inkluderas också i paketnamnet.</span><span class="sxs-lookup"><span data-stu-id="219ea-128">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

![Bild av att prenumerationen har gått ut](images/atp-subscription-expired.png)

## <a name="you-are-not-authorized-to-access-the-portal"></a><span data-ttu-id="219ea-130">Du har inte behörighet att komma åt portalen</span><span class="sxs-lookup"><span data-stu-id="219ea-130">You are not authorized to access the portal</span></span>

<span data-ttu-id="219ea-131">Om du får ett meddelande om att du inte har behörighet att komma åt **portalen** bör du vara medveten om att Microsoft Defender för Endpoint är en säkerhetsövervakning, undersökning av incidenter och svar, och därför begränsas åtkomsten till den och kontrolleras av användaren.</span><span class="sxs-lookup"><span data-stu-id="219ea-131">If you receive a **You are not authorized to access the portal**, be aware that Microsoft Defender for Endpoint is a security monitoring, incident investigation and response product, and as such, access to it is restricted and controlled by the user.</span></span>
<span data-ttu-id="219ea-132">Mer information finns i Tilldela [**användaråtkomst till portalen.**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="219ea-132">For more information, see, [**Assign user access to the portal**](/windows/threat-protection/windows-defender-atp/assign-portal-access-windows-defender-advanced-threat-protection).</span></span>

![Bild av ej behörig att komma åt portalen](images/atp-not-authorized-to-access-portal.png)

## <a name="data-currently-isnt-available-on-some-sections-of-the-portal"></a><span data-ttu-id="219ea-134">Data är för närvarande inte tillgängliga på vissa avsnitt i portalen</span><span class="sxs-lookup"><span data-stu-id="219ea-134">Data currently isn't available on some sections of the portal</span></span>
<span data-ttu-id="219ea-135">Om instrumentpanelen på portalen och andra avsnitt visar ett felmeddelande, till exempel "Data är för närvarande inte tillgängligt":</span><span class="sxs-lookup"><span data-stu-id="219ea-135">If the portal dashboard and other sections show an error message such as "Data currently isn't available":</span></span>

![Bild på data som för närvarande inte är tillgängliga](images/atp-data-not-available.png)

<span data-ttu-id="219ea-137">Du måste tillåta alla `securitycenter.windows.com` underdomäner under den.</span><span class="sxs-lookup"><span data-stu-id="219ea-137">You'll need to allow the `securitycenter.windows.com` and all subdomains under it.</span></span> <span data-ttu-id="219ea-138">Till exempel `*.securitycenter.windows.com`.</span><span class="sxs-lookup"><span data-stu-id="219ea-138">For example, `*.securitycenter.windows.com`.</span></span>


## <a name="portal-communication-issues"></a><span data-ttu-id="219ea-139">Informationsproblem i portalen</span><span class="sxs-lookup"><span data-stu-id="219ea-139">Portal communication issues</span></span>
<span data-ttu-id="219ea-140">Om du stöter på problem med åtkomst till portalen, saknade data eller begränsad åtkomst till delar av portalen måste du kontrollera att följande URL:er är tillåtna och öppna för kommunikation.</span><span class="sxs-lookup"><span data-stu-id="219ea-140">If you encounter issues with accessing the portal, missing data, or restricted access to portions of the portal, you'll need to verify that the following URLs are allowed and open for communication.</span></span>

- `*.blob.core.windows.net`
- `crl.microsoft.com`
- `https://*.microsoftonline-p.com`
- `https://*.securitycenter.windows.com` 
- `https://automatediracs-eus-prd.securitycenter.windows.com`
- `https://login.microsoftonline.com`
- `https://login.windows.net`
- `https://onboardingpackagescusprd.blob.core.windows.net`
- `https://secure.aadcdn.microsoftonline-p.com` 
- `https://securitycenter.windows.com` 
- `https://static2.sharepointonline.com` 



