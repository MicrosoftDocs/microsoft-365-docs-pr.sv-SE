---
title: Konfigurera avancerade funktioner i Microsoft Defender för Slutpunkt
description: Aktivera avancerade funktioner, till exempel blockeringsfil i Microsoft Defender för Endpoint.
keywords: avancerade funktioner, inställningar, blockering av fil, automatisk undersökning, automatisk lösning, skype, microsoft defender för identitet, office 365, azure informationsskydd, intune
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c5e6edb40254ab905ef5ef3ddef9bf8bf54fc54b
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698274"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a><span data-ttu-id="c7878-104">Konfigurera avancerade funktioner i Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="c7878-104">Configure advanced features in Defender for Endpoint</span></span>

<span data-ttu-id="c7878-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c7878-105">**Applies to:**</span></span>
- [<span data-ttu-id="c7878-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c7878-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c7878-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c7878-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> <span data-ttu-id="c7878-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="c7878-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c7878-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="c7878-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="c7878-110">Beroende på vilka Microsoft-säkerhetsprodukter du använder kan vissa avancerade funktioner vara tillgängliga för dig att integrera Defender för Slutpunkt med.</span><span class="sxs-lookup"><span data-stu-id="c7878-110">Depending on the Microsoft security products that you use, some advanced features might be available for you to integrate Defender for Endpoint with.</span></span>

## <a name="enable-advanced-features"></a><span data-ttu-id="c7878-111">Aktivera avancerade funktioner</span><span class="sxs-lookup"><span data-stu-id="c7878-111">Enable advanced features</span></span>

1. <span data-ttu-id="c7878-112">I navigeringsfönstret väljer du **Inställningar inställningar Avancerade**  >  **funktioner**.</span><span class="sxs-lookup"><span data-stu-id="c7878-112">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="c7878-113">Välj den avancerade funktion du vill konfigurera och växla inställningen **mellan** På och **Av.**</span><span class="sxs-lookup"><span data-stu-id="c7878-113">Select the advanced feature you want to configure and toggle the setting between **On** and **Off**.</span></span>
3. <span data-ttu-id="c7878-114">Klicka **på Spara inställningar.**</span><span class="sxs-lookup"><span data-stu-id="c7878-114">Click **Save preferences**.</span></span>

<span data-ttu-id="c7878-115">Använd följande avancerade funktioner för att få bättre skydd från potentiellt skadliga filer och få bättre insyn under säkerhetsundersökningen.</span><span class="sxs-lookup"><span data-stu-id="c7878-115">Use the following advanced features to get better protected from potentially malicious files and gain better insight during security investigations.</span></span>

## <a name="automated-investigation"></a><span data-ttu-id="c7878-116">Automatiserad undersökning</span><span class="sxs-lookup"><span data-stu-id="c7878-116">Automated investigation</span></span>

<span data-ttu-id="c7878-117">Aktivera den här funktionen för att dra nytta av tjänstens funktioner för automatisk undersökning och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="c7878-117">Turn on this feature to take advantage of the automated investigation and remediation features of the service.</span></span> <span data-ttu-id="c7878-118">Mer information finns i [Automatiserad undersökning](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="c7878-118">For more information, see [Automated investigation](automated-investigations.md).</span></span>

## <a name="live-response"></a><span data-ttu-id="c7878-119">Livesvar</span><span class="sxs-lookup"><span data-stu-id="c7878-119">Live response</span></span>

<span data-ttu-id="c7878-120">Aktivera den här funktionen så att användare med rätt behörighet kan starta en direkt svarssession på enheter.</span><span class="sxs-lookup"><span data-stu-id="c7878-120">Turn on this feature so that users with the appropriate permissions can start a live response session on devices.</span></span>

<span data-ttu-id="c7878-121">Mer information om rolltilldelningar finns i [Skapa och hantera roller.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c7878-121">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>

## <a name="live-response-for-servers"></a><span data-ttu-id="c7878-122">Live-svar för servrar</span><span class="sxs-lookup"><span data-stu-id="c7878-122">Live response for servers</span></span>
<span data-ttu-id="c7878-123">Aktivera den här funktionen så att användare med rätt behörighet kan starta en live-svarssession på servrar.</span><span class="sxs-lookup"><span data-stu-id="c7878-123">Turn on this feature so that users with the appropriate permissions can start a live response session on servers.</span></span>

<span data-ttu-id="c7878-124">Mer information om rolltilldelningar finns i [Skapa och hantera roller.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="c7878-124">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>


## <a name="live-response-unsigned-script-execution"></a><span data-ttu-id="c7878-125">Körning av skript som inte har signerats med Live Response</span><span class="sxs-lookup"><span data-stu-id="c7878-125">Live response unsigned script execution</span></span>

<span data-ttu-id="c7878-126">Om du aktiverar den här funktionen kan du köra osignerade skript i en svarssession i direktsändning.</span><span class="sxs-lookup"><span data-stu-id="c7878-126">Enabling this feature allows you to run unsigned scripts in a live response session.</span></span>

## <a name="always-remediate-pua"></a><span data-ttu-id="c7878-127">Åtgärda alltid PUA</span><span class="sxs-lookup"><span data-stu-id="c7878-127">Always remediate PUA</span></span>
<span data-ttu-id="c7878-128">Potentiellt oönskade program (PUA) är en kategori av programvara som kan få datorn att köras långsamt, visa oväntade annonser eller i värsta fall installera annan programvara som kan vara oväntad eller oönskad.</span><span class="sxs-lookup"><span data-stu-id="c7878-128">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> 

<span data-ttu-id="c7878-129">Aktivera den här funktionen så att potentiellt oönskade program (PUA) åtgärdas på alla enheter i klientorganisationen även om PUA-skyddet inte har konfigurerats på enheterna.</span><span class="sxs-lookup"><span data-stu-id="c7878-129">Turn on this feature so that potentially unwanted applications (PUA) are remediated on all devices in your tenant even if PUA protection is not configured on the devices.</span></span> <span data-ttu-id="c7878-130">Det här hjälper till att skydda användare från att oavsiktligt installera oönskade program på enheten.</span><span class="sxs-lookup"><span data-stu-id="c7878-130">This will help protect users from inadvertently installing unwanted applications on their device.</span></span> <span data-ttu-id="c7878-131">När den är inaktiverad beror åtgärder på enhetens konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c7878-131">When turned off, remediation is dependent on the device configuration.</span></span> 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a><span data-ttu-id="c7878-132">Begränsa korrelationen till inom begränsade enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="c7878-132">Restrict correlation to within scoped device groups</span></span>
<span data-ttu-id="c7878-133">När den här inställningen är aktiverad korreleras aviseringar till separata incidenter utifrån deras begränsade enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="c7878-133">When this setting is turned on, alerts are correlated into separate incidents based on their scoped device group.</span></span> <span data-ttu-id="c7878-134">Som standard sker korrelationen mellan incidenter i hela klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="c7878-134">By default, incident correlation happens across the entire tenant scope.</span></span>

>[!NOTE]
><span data-ttu-id="c7878-135">Om du ändrar den här inställningen påverkas bara framtida korrelationer.</span><span class="sxs-lookup"><span data-stu-id="c7878-135">Changing this setting impacts future alert correlations only.</span></span>

## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="c7878-136">Aktivera EDR i blockläge</span><span class="sxs-lookup"><span data-stu-id="c7878-136">Enable EDR in block mode</span></span>
<span data-ttu-id="c7878-137">Identifiering av slutpunkt och svar (EDR) i blockeringsläge ger skydd mot skadliga artefakter, även när Microsoft Defender Antivirus körs i passiv form.</span><span class="sxs-lookup"><span data-stu-id="c7878-137">Endpoint detection and response (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="c7878-138">När EDR är aktiverat blockerar EDR i blockläge skadliga artefakter eller beteenden som identifieras på en enhet.</span><span class="sxs-lookup"><span data-stu-id="c7878-138">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="c7878-139">EDR i blockläge arbetar bakom kulisserna för att åtgärda skadliga artefakter som upptäcks efter intrånget.</span><span class="sxs-lookup"><span data-stu-id="c7878-139">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span>


## <a name="autoresolve-remediated-alerts"></a><span data-ttu-id="c7878-140">Åtgärdat autoresole-aviseringar</span><span class="sxs-lookup"><span data-stu-id="c7878-140">Autoresolve remediated alerts</span></span>

<span data-ttu-id="c7878-141">För klientprogram som skapats i eller efter Windows 10, version 1809, konfigureras automatisk undersökning och åtgärd som standard för att lösa varningar där status för automatisk analys är "Inga hot hittades" eller "Åtgärdat".</span><span class="sxs-lookup"><span data-stu-id="c7878-141">For tenants created on or after Windows 10, version 1809, the automated investigation and remediation capability is configured by default to resolve alerts where the automated analysis result status is "No threats found" or "Remediated".</span></span>  <span data-ttu-id="c7878-142">Om du inte vill att aviseringarna ska matchas automatiskt måste du inaktivera funktionen manuellt.</span><span class="sxs-lookup"><span data-stu-id="c7878-142">If you don't want to have alerts auto-resolved, you'll need to manually turn off the feature.</span></span>

> [!TIP]
> <span data-ttu-id="c7878-143">För klientorganisationen som skapats tidigare än den versionen måste du manuellt aktivera den här funktionen på sidan [Avancerade](https://securitycenter.windows.com/preferences2/integration) funktioner.</span><span class="sxs-lookup"><span data-stu-id="c7878-143">For tenants created prior to that version, you'll need to manually turn this feature on from the [Advanced features](https://securitycenter.windows.com/preferences2/integration) page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c7878-144">Resultatet av åtgärden för automatisk lösning kan påverka beräkningen av enhetrisknivå som baseras på de aktiva aviseringarna som finns på en enhet.</span><span class="sxs-lookup"><span data-stu-id="c7878-144">The result of the auto-resolve action may influence the Device risk level calculation which is based on the active alerts found on a device.</span></span>
> - <span data-ttu-id="c7878-145">Om en analytiker för säkerhetsåtgärder manuellt anger statusen för en avisering till "Pågår" eller "Löst" skriver funktionen för automatisk resolve inte över den.</span><span class="sxs-lookup"><span data-stu-id="c7878-145">If a security operations analyst manually sets the status of an alert to "In progress" or "Resolved" the auto-resolve capability will not overwrite it.</span></span>

## <a name="allow-or-block-file"></a><span data-ttu-id="c7878-146">Tillåta eller blockera fil</span><span class="sxs-lookup"><span data-stu-id="c7878-146">Allow or block file</span></span>

<span data-ttu-id="c7878-147">Blockering är bara tillgängligt om din organisation uppfyller följande krav:</span><span class="sxs-lookup"><span data-stu-id="c7878-147">Blocking is only available if your organization fulfills these requirements:</span></span>

- <span data-ttu-id="c7878-148">Använder Microsoft Defender Antivirus som den aktiva antimalwarelösningen och</span><span class="sxs-lookup"><span data-stu-id="c7878-148">Uses Microsoft Defender Antivirus as the active antimalware solution and,</span></span>
- <span data-ttu-id="c7878-149">Den molnbaserade skyddsfunktionen är aktiverad</span><span class="sxs-lookup"><span data-stu-id="c7878-149">The cloud-based protection feature is enabled</span></span>

<span data-ttu-id="c7878-150">Med den här funktionen kan du blockera potentiellt skadliga filer i nätverket.</span><span class="sxs-lookup"><span data-stu-id="c7878-150">This feature enables you to block potentially malicious files in your network.</span></span> <span data-ttu-id="c7878-151">När du blockerar en fil förhindrar du att den läses, skrivs eller körs på enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="c7878-151">Blocking a file will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="c7878-152">Aktivera Tillåt **eller blockera** filer:</span><span class="sxs-lookup"><span data-stu-id="c7878-152">To turn **Allow or block** files on:</span></span>

1. <span data-ttu-id="c7878-153">Välj Inställningar Avancerade funktioner Tillåt eller **blockera**  >    >  **fil i navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="c7878-153">In the navigation pane, select **Settings** > **Advanced features** > **Allow or block file**.</span></span>

1. <span data-ttu-id="c7878-154">Ändra inställningen mellan **På och** **Av.**</span><span class="sxs-lookup"><span data-stu-id="c7878-154">Toggle the setting between **On** and **Off**.</span></span>

    ![Bild av avancerade inställningar för filblockeringsfunktionen](images/atp-preferences-setup.png)

1. <span data-ttu-id="c7878-156">Välj **Spara inställningar** längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="c7878-156">Select **Save preferences** at the bottom of the page.</span></span>

<span data-ttu-id="c7878-157">När du har aktiverat den här funktionen kan [du blockera](respond-file-alerts.md#allow-or-block-file) filer via **fliken** Lägg till indikator på en fils profilsida.</span><span class="sxs-lookup"><span data-stu-id="c7878-157">After turning on this feature, you can [block files](respond-file-alerts.md#allow-or-block-file) via the **Add Indicator** tab on a file's profile page.</span></span>

## <a name="custom-network-indicators"></a><span data-ttu-id="c7878-158">Anpassade nätverksindikatorer</span><span class="sxs-lookup"><span data-stu-id="c7878-158">Custom network indicators</span></span>

<span data-ttu-id="c7878-159">Om du slår på den här funktionen kan du skapa indikatorer för IP-adresser, domäner och URL-adresser, som avgör om de tillåts eller blockeras baserat på en anpassad indikatorlista.</span><span class="sxs-lookup"><span data-stu-id="c7878-159">Turning on this feature allows you to create indicators for IP addresses, domains, or URLs, which determine whether they will be allowed or blocked based on your custom indicator list.</span></span>

<span data-ttu-id="c7878-160">Om du vill använda den här funktionen måste enheterna köra Windows 10 version 1709 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c7878-160">To use this feature, devices must be running Windows 10 version 1709 or later.</span></span> <span data-ttu-id="c7878-161">De bör också ha nätverksskydd i blockläge och version 4.18.1906.3 eller senare av program mot skadlig programvara, se [KB 4052623.](https://go.microsoft.com/fwlink/?linkid=2099834)</span><span class="sxs-lookup"><span data-stu-id="c7878-161">They should also have network protection in block mode and version 4.18.1906.3 or later of the antimalware platform [see KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span></span>

<span data-ttu-id="c7878-162">Mer information finns i [Hantera indikatorer](manage-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="c7878-162">For more information, see [Manage indicators](manage-indicators.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c7878-163">Nätverksskydd utnyttjar ryktestjänster som bearbetar förfrågningar på platser som kan vara utanför den plats du har valt för Defender för Slutpunktsdata.</span><span class="sxs-lookup"><span data-stu-id="c7878-163">Network protection leverages reputation services that process requests in locations that might be outside of the location you have selected for your Defender for Endpoint data.</span></span>

## <a name="tamper-protection"></a><span data-ttu-id="c7878-164">Skydd mot manipulering</span><span class="sxs-lookup"><span data-stu-id="c7878-164">Tamper protection</span></span>
<span data-ttu-id="c7878-165">Under vissa typer av cyberattacker försöker dåliga aktör att inaktivera säkerhetsfunktioner, till exempel antivirusskydd, på dina datorer.</span><span class="sxs-lookup"><span data-stu-id="c7878-165">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="c7878-166">Dåliga aktör vill inaktivera dina säkerhetsfunktioner för att få enklare åtkomst till dina data, installera skadlig programvara eller på annat sätt utnyttja dina data, din identitet och dina enheter.</span><span class="sxs-lookup"><span data-stu-id="c7878-166">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span>

<span data-ttu-id="c7878-167">Skydd mot manipulering låser i princip Microsoft Defender Antivirus och förhindrar att säkerhetsinställningarna ändras genom appar och metoder.</span><span class="sxs-lookup"><span data-stu-id="c7878-167">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods.</span></span>

<span data-ttu-id="c7878-168">Behåll skydd mot manipulering aktiverat för att förhindra oönskade ändringar i din säkerhetslösning och dess viktiga funktioner.</span><span class="sxs-lookup"><span data-stu-id="c7878-168">Keep tamper protection turned on to prevent unwanted changes to your security solution and its essential features.</span></span>


## <a name="show-user-details"></a><span data-ttu-id="c7878-169">Visa användarinformation</span><span class="sxs-lookup"><span data-stu-id="c7878-169">Show user details</span></span>

<span data-ttu-id="c7878-170">Aktivera den här funktionen så att du kan se användarinformation som lagras i Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c7878-170">Turn on this feature so that you can see user details stored in Azure Active Directory.</span></span> <span data-ttu-id="c7878-171">Informationen omfattar en användares bild, namn, titel och avdelningsinformation när du undersöker enheter med användarkonton.</span><span class="sxs-lookup"><span data-stu-id="c7878-171">Details include a user's picture, name, title, and department information  when investigating user account entities.</span></span> <span data-ttu-id="c7878-172">Användarkontoinformationen finns i följande vyer:</span><span class="sxs-lookup"><span data-stu-id="c7878-172">You can find user account information in the following views:</span></span>

- <span data-ttu-id="c7878-173">Instrumentpanel för säkerhetsåtgärder</span><span class="sxs-lookup"><span data-stu-id="c7878-173">Security operations dashboard</span></span>
- <span data-ttu-id="c7878-174">Aviseringskö</span><span class="sxs-lookup"><span data-stu-id="c7878-174">Alert queue</span></span>
- <span data-ttu-id="c7878-175">Sidan Enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="c7878-175">Device details page</span></span>

<span data-ttu-id="c7878-176">Mer information finns i [Undersöka ett användarkonto.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="c7878-176">For more information, see [Investigate a user account](investigate-user.md).</span></span>


## <a name="skype-for-business-integration"></a><span data-ttu-id="c7878-177">Skype för företag-integrering</span><span class="sxs-lookup"><span data-stu-id="c7878-177">Skype for Business integration</span></span>

<span data-ttu-id="c7878-178">Om du aktiverar Skype för företag-integreringen kan du kommunicera med användare via Skype för företag, e-post eller telefon.</span><span class="sxs-lookup"><span data-stu-id="c7878-178">Enabling the Skype for Business integration gives you the ability to communicate with users using Skype for Business, email, or phone.</span></span> <span data-ttu-id="c7878-179">Det kan vara praktiskt när du behöver kommunicera med användaren och minimera risker.</span><span class="sxs-lookup"><span data-stu-id="c7878-179">This can be handy when you need to communicate with the user and mitigate risks.</span></span>

> [!NOTE]
> <span data-ttu-id="c7878-180">När en enhet isoleras från nätverket visas ett popup-fönster där du kan välja att aktivera Outlook- och Skype-kommunikationer som tillåter kommunikation till användaren när han eller hon kopplas bort från nätverket.</span><span class="sxs-lookup"><span data-stu-id="c7878-180">When a device is being isolated from the network, there's a pop-up where you can choose to enable Outlook and Skype communications which allows communications to the user while they are disconnected from the network.</span></span> <span data-ttu-id="c7878-181">Den här inställningen gäller för Skype- och Outlook-kommunikation när enheter är i separat läge.</span><span class="sxs-lookup"><span data-stu-id="c7878-181">This setting applies to Skype and Outlook communication when devices are in isolation mode.</span></span>

## <a name="microsoft-defender-for-identity-integration"></a><span data-ttu-id="c7878-182">Microsoft Defender för identitetsintegrering</span><span class="sxs-lookup"><span data-stu-id="c7878-182">Microsoft Defender for Identity integration</span></span>

<span data-ttu-id="c7878-183">Integreringen med Azure Advanced Threat Protection gör att du kan pivotera direkt till en annan Microsoft Identity-säkerhetsprodukt.</span><span class="sxs-lookup"><span data-stu-id="c7878-183">The integration with Azure Advanced Threat Protection allows you to pivot directly into another Microsoft Identity security product.</span></span> <span data-ttu-id="c7878-184">Med Azure Avancerat skydd utökas en undersökning med ytterligare insikter om ett misstänkt komprometterat konto och relaterade resurser.</span><span class="sxs-lookup"><span data-stu-id="c7878-184">Azure Advanced Threat Protection augments an investigation with additional insights about a suspected compromised account and related resources.</span></span> <span data-ttu-id="c7878-185">Genom att aktivera den här funktionen kan du utöka den enhetsbaserade undersökningsfunktionen genom att pivotera över nätverket från en synpunkt.</span><span class="sxs-lookup"><span data-stu-id="c7878-185">By enabling this feature, you'll enrich the device-based investigation capability by pivoting across the network from an identify point of view.</span></span>

> [!NOTE]
> <span data-ttu-id="c7878-186">Du måste ha rätt licens för att aktivera den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="c7878-186">You'll need to have the appropriate license to enable this feature.</span></span>

## <a name="office-365-threat-intelligence-connection"></a><span data-ttu-id="c7878-187">Office 365 Threat Intelligence-anslutning</span><span class="sxs-lookup"><span data-stu-id="c7878-187">Office 365 Threat Intelligence connection</span></span>

<span data-ttu-id="c7878-188">Den här funktionen är endast tillgänglig om du har ett aktivt Office 365 E5- eller Threat Intelligence-tillägg.</span><span class="sxs-lookup"><span data-stu-id="c7878-188">This feature is only available if you have an active Office 365 E5 or the Threat Intelligence add-on.</span></span> <span data-ttu-id="c7878-189">Mer information finns på produktsidan för Office 365 Enterprise, E5.</span><span class="sxs-lookup"><span data-stu-id="c7878-189">For more information, see the Office 365 Enterprise E5 product page.</span></span>

<span data-ttu-id="c7878-190">När du aktiverar den här funktionen kan du införliva data från Avancerat skydd för Office 365 i Microsoft Defender Säkerhetscenter för att genomföra en omfattande säkerhetsundersökning i alla Office 365-postlådor och Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="c7878-190">When you turn this feature on, you'll be able to incorporate data from Office 365 Advanced Threat Protection into Microsoft Defender Security Center to conduct a comprehensive security investigation across Office 365 mailboxes and Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="c7878-191">Du måste ha rätt licens för att aktivera den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="c7878-191">You'll need to have the appropriate license to enable this feature.</span></span>

<span data-ttu-id="c7878-192">Om du vill få sammanhangsbaserad enhetsintegration i Office 365 Threat Intelligence måste du aktivera Defender för Slutpunktsinställningar i instrumentpanelen för & säkerhet och efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="c7878-192">To receive contextual device integration in Office 365 Threat Intelligence, you'll need to enable the Defender for Endpoint settings in the Security & Compliance dashboard.</span></span> <span data-ttu-id="c7878-193">Mer information finns i Undersökning [av hot och svar.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti)</span><span class="sxs-lookup"><span data-stu-id="c7878-193">For more information, see [Threat investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-ti).</span></span>

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a><span data-ttu-id="c7878-194">Microsoft Threat Experts – riktade attackmeddelanden</span><span class="sxs-lookup"><span data-stu-id="c7878-194">Microsoft Threat Experts - Targeted Attack Notifications</span></span>

<span data-ttu-id="c7878-195">Av de två Microsoft Threat Expert-komponenterna är riktade attackmeddelanden i allmän tillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="c7878-195">Out of the two Microsoft Threat Expert components, targeted attack notification is in general availability.</span></span> <span data-ttu-id="c7878-196">Experter på begäran är fortfarande i förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="c7878-196">Experts-on-demand capability is still in preview.</span></span> <span data-ttu-id="c7878-197">Du kan bara använda funktionen för experter på begäran om du har tillämpat en förhandsgranskning och programmet har godkänts.</span><span class="sxs-lookup"><span data-stu-id="c7878-197">You can only use the experts-on-demand capability if you have applied for preview and your application has been approved.</span></span> <span data-ttu-id="c7878-198">Du kan få riktade attackmeddelanden från Microsoft Threat Experts via din Defender för Endpoint-portalens aviseringar-instrumentpanel och via e-post om du konfigurerar den.</span><span class="sxs-lookup"><span data-stu-id="c7878-198">You can receive targeted attack notifications from Microsoft Threat Experts through your Defender for Endpoint portal's alerts dashboard and via email if you configure it.</span></span>

> [!NOTE]
> <span data-ttu-id="c7878-199">Microsoft Threat Experts-funktionen i Defender för Endpoint är tillgänglig med en E5-licens för [Enterprise Mobility + Security.](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)</span><span class="sxs-lookup"><span data-stu-id="c7878-199">The Microsoft Threat Experts capability in Defender for Endpoint is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span></span>
## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="c7878-200">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c7878-200">Microsoft Cloud App Security</span></span>

<span data-ttu-id="c7878-201">Aktivering av den här inställningen vidarebefordrar Defender för Endpoint-signaler till Microsoft Cloud App Security för att bättre kunna se användningen av molnprogram.</span><span class="sxs-lookup"><span data-stu-id="c7878-201">Enabling this setting forwards Defender for Endpoint signals to Microsoft Cloud App Security to provide deeper visibility into cloud application usage.</span></span> <span data-ttu-id="c7878-202">Vidarebefordrade data lagras och bearbetas på samma plats som dina Cloud App Security-data.</span><span class="sxs-lookup"><span data-stu-id="c7878-202">Forwarded data is stored and processed in the same location as your Cloud App Security data.</span></span>

> [!NOTE]
> <span data-ttu-id="c7878-203">Den här funktionen är tillgänglig med en E5-licens för [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) på enheter som kör Windows 10, version 1709 (OS-version 16299.1085 med [KB4493441),](https://support.microsoft.com/help/4493441)Windows 10, version 1803 (OS Version 17134.704 med [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 med [KB4489899](https://support.microsoft.com/help/4489899)) eller senare Windows 10-versioner.</span><span class="sxs-lookup"><span data-stu-id="c7878-203">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)), or later Windows 10 versions.</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="c7878-204">Microsoft Secure Score</span><span class="sxs-lookup"><span data-stu-id="c7878-204">Microsoft Secure Score</span></span>

<span data-ttu-id="c7878-205">Vidarebefordrar Microsoft Defender för Endpoint-signaler till Microsoft Secure Score i Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="c7878-205">Forwards Microsoft Defender for Endpoint signals to Microsoft Secure Score in the Microsoft 365 security center.</span></span> <span data-ttu-id="c7878-206">Om du slår på den här funktionen kan Microsoft Secure Score hålla ordning på enhetens säkerhetssystem.</span><span class="sxs-lookup"><span data-stu-id="c7878-206">Turning on this feature gives Microsoft Secure Score visibility into the device's security posture.</span></span> <span data-ttu-id="c7878-207">Vidarebefordrade data lagras och bearbetas på samma plats som dina Microsoft Secure Score-data.</span><span class="sxs-lookup"><span data-stu-id="c7878-207">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a><span data-ttu-id="c7878-208">Aktivera Microsoft Defender för slutpunktsintegrering från Microsoft Defender för identitetsportalen</span><span class="sxs-lookup"><span data-stu-id="c7878-208">Enable the Microsoft Defender for Endpoint integration from the Microsoft Defender for Identity portal</span></span>

<span data-ttu-id="c7878-209">Om du vill få en sammanhangsberoende enhetsintegration i Microsoft Defender för identitet måste du också aktivera funktionen i Microsoft Defender för identitetsportalen.</span><span class="sxs-lookup"><span data-stu-id="c7878-209">To receive contextual device integration in Microsoft Defender for Identity, you'll also need to enable the feature in the Microsoft Defender for Identity portal.</span></span>

1. <span data-ttu-id="c7878-210">Logga in på [Microsoft Defender för identitetsportalen med](https://portal.atp.azure.com/) en global administratör eller säkerhetsadministratörsroll.</span><span class="sxs-lookup"><span data-stu-id="c7878-210">Log in to the [Microsoft Defender for Identity portal](https://portal.atp.azure.com/) with a Global Administrator or Security Administrator role.</span></span>

2. <span data-ttu-id="c7878-211">Klicka **på Skapa din instans**.</span><span class="sxs-lookup"><span data-stu-id="c7878-211">Click **Create your instance**.</span></span>

3. <span data-ttu-id="c7878-212">Ändra inställningen Integration till På **och** klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c7878-212">Toggle the Integration setting to **On** and click **Save**.</span></span>

<span data-ttu-id="c7878-213">När du har slutfört integrationsstegen på båda portalerna kan du se relevanta aviseringar på sidan med enhetsinformation eller användarinformation.</span><span class="sxs-lookup"><span data-stu-id="c7878-213">After completing the integration steps on both portals, you'll be able to see relevant alerts in the device details or user details page.</span></span>

## <a name="web-content-filtering"></a><span data-ttu-id="c7878-214">Filtrering av webbinnehåll</span><span class="sxs-lookup"><span data-stu-id="c7878-214">Web content filtering</span></span>
<span data-ttu-id="c7878-215">Blockera åtkomst till webbplatser som innehåller oönskat innehåll och spåra webbaktivitet i alla domäner.</span><span class="sxs-lookup"><span data-stu-id="c7878-215">Block access to websites containing unwanted content and track web activity across all domains.</span></span> <span data-ttu-id="c7878-216">Skapa en princip för webbinnehållsfiltrering om du vill ange vilka [kategorier av webbinnehåll](https://security.microsoft.com/preferences2/web_content_filtering_policy)som du vill blockera.</span><span class="sxs-lookup"><span data-stu-id="c7878-216">To specify the web content categories you want to block, create a [web content filtering policy](https://security.microsoft.com/preferences2/web_content_filtering_policy).</span></span> <span data-ttu-id="c7878-217">Se till att du har nätverksskydd i blockeringsläge när du distribuerar [Microsoft Defender för slutpunktens säkerhetsbaslinje.](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)</span><span class="sxs-lookup"><span data-stu-id="c7878-217">Ensure you have network protection in block mode when deploying the [Microsoft Defender for Endpoint security baseline](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2).</span></span>


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a><span data-ttu-id="c7878-218">Dela slutpunktsaviseringar med Microsofts efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="c7878-218">Share endpoint alerts with Microsoft Compliance Center</span></span>
<span data-ttu-id="c7878-219">Vidarebefordrar säkerhetsvarningar för slutpunkter och deras status till Microsofts efterlevnadscenter, så att du kan förbättra principer för insiderriskhantering med varningar och åtgärda interna risker innan de kan orsaka skada.</span><span class="sxs-lookup"><span data-stu-id="c7878-219">Forwards endpoint security alerts and their triage status to Microsoft Compliance Center, allowing you to enhance insider risk management policies with alerts and remediate internal risks before they cause harm.</span></span> <span data-ttu-id="c7878-220">Vidarebefordrade data bearbetas och lagras på samma plats som dina Office 365-data.</span><span class="sxs-lookup"><span data-stu-id="c7878-220">Forwarded data is processed and stored in the same location as your Office 365 data.</span></span>

<span data-ttu-id="c7878-221">När du har [konfigurerat indikatorerna för brott](/microsoft-365/compliance/insider-risk-management-settings#indicators) mot säkerhetsprinciper i inställningarna för Insider-riskhantering delas Defender för Slutpunktsaviseringar med Insider-riskhantering för tillämpliga användare.</span><span class="sxs-lookup"><span data-stu-id="c7878-221">After configuring the [Security policy violation indicators](/microsoft-365/compliance/insider-risk-management-settings#indicators) in the insider risk management settings, Defender for Endpoint alerts will be shared with insider risk management for applicable users.</span></span>



## <a name="microsoft-intune-connection"></a><span data-ttu-id="c7878-222">Microsoft Intune-anslutning</span><span class="sxs-lookup"><span data-stu-id="c7878-222">Microsoft Intune connection</span></span>

<span data-ttu-id="c7878-223">Defender för Endpoint kan integreras med [Microsoft Intune för att aktivera](https://docs.microsoft.com/intune/what-is-intune) [enhetsriskbaserad villkorlig åtkomst.](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)</span><span class="sxs-lookup"><span data-stu-id="c7878-223">Defender for Endpoint can be integrated with [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) to [enable device risk-based conditional access](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span> <span data-ttu-id="c7878-224">När du [aktiverar den här funktionen](configure-conditional-access.md)kan du dela Information om Endpoint-enheter med Intune och förbättra tvingande policy.</span><span class="sxs-lookup"><span data-stu-id="c7878-224">When you [turn on this feature](configure-conditional-access.md), you'll be able to share Defender for Endpoint device information with Intune, enhancing policy enforcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7878-225">Du måste aktivera integreringen på både Intune och Defender för Endpoint om du vill använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="c7878-225">You'll need to enable the integration on both Intune and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="c7878-226">Mer information om specifika steg finns i Konfigurera [villkorsstyrd åtkomst i Defender för slutpunkt.](configure-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="c7878-226">For more information on specific steps, see [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).</span></span>

<span data-ttu-id="c7878-227">Den här funktionen är endast tillgänglig om du har följande:</span><span class="sxs-lookup"><span data-stu-id="c7878-227">This feature is only available if you have the following:</span></span>

- <span data-ttu-id="c7878-228">En licensierad klientorganisation för Enterprise Mobility + Security E3 och Windows E5 (eller Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="c7878-228">A licensed tenant for Enterprise Mobility + Security E3, and Windows E5 (or Microsoft 365 Enterprise E5)</span></span>
- <span data-ttu-id="c7878-229">En aktiv Microsoft Intune-miljö med Intune-hanterade Windows 10-enheter [med Azure AD-anslutna](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/).</span><span class="sxs-lookup"><span data-stu-id="c7878-229">An active Microsoft Intune environment, with Intune-managed Windows 10 devices [Azure AD-joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/).</span></span>


### <a name="conditional-access-policy"></a><span data-ttu-id="c7878-230">Princip för villkorsstyrd åtkomst</span><span class="sxs-lookup"><span data-stu-id="c7878-230">Conditional Access policy</span></span>

<span data-ttu-id="c7878-231">När du aktiverar Intune-integrering skapar Intune automatiskt en klassisk CA-princip (Conditional Access).</span><span class="sxs-lookup"><span data-stu-id="c7878-231">When you enable Intune integration, Intune will automatically create a classic Conditional Access (CA) policy.</span></span> <span data-ttu-id="c7878-232">Den här klassiska CA-principen är en förutsättning för att kunna konfigurera statusrapporter till Intune.</span><span class="sxs-lookup"><span data-stu-id="c7878-232">This classic CA policy is a prerequisite for setting up status reports to Intune.</span></span> <span data-ttu-id="c7878-233">Den ska inte tas bort.</span><span class="sxs-lookup"><span data-stu-id="c7878-233">It should not be deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="c7878-234">Den klassiska CA-principen som skapas av Intune skiljer sig från moderna [villkorsstyrda](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)åtkomstprinciper, som används för att konfigurera slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="c7878-234">The classic CA policy created by Intune is distinct from modern [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/), which are used for configuring endpoints.</span></span>


## <a name="device-discovery"></a><span data-ttu-id="c7878-235">Enhetsidentifiering</span><span class="sxs-lookup"><span data-stu-id="c7878-235">Device discovery</span></span>
<span data-ttu-id="c7878-236">Hjälper dig att hitta ohanterade enheter anslutna till företagsnätverket utan att behöva extra utrustning eller krångliga processändringar.</span><span class="sxs-lookup"><span data-stu-id="c7878-236">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="c7878-237">Med onboarded-enheter kan du hitta ohanterade enheter i nätverket och bedöma svagheter och risker.</span><span class="sxs-lookup"><span data-stu-id="c7878-237">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="c7878-238">Mer information finns i [Enhetsidentifiering](device-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="c7878-238">For more information, see [Device discovery](device-discovery.md).</span></span>

## <a name="preview-features"></a><span data-ttu-id="c7878-239">Förhandsgranskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="c7878-239">Preview features</span></span>

<span data-ttu-id="c7878-240">Lär dig mer om nya funktioner i förhandsversionen av Defender för slutpunkt och bli bland de första som kan prova kommande funktioner genom att aktivera förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="c7878-240">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="c7878-241">Du har tillgång till kommande funktioner som du kan ge feedback på för att förbättra den övergripande upplevelsen innan funktionerna blir tillgängliga i allmänhet.</span><span class="sxs-lookup"><span data-stu-id="c7878-241">You'll have access to upcoming features, which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>




## <a name="related-topics"></a><span data-ttu-id="c7878-242">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c7878-242">Related topics</span></span>

- [<span data-ttu-id="c7878-243">Uppdatera inställningar för datalagring</span><span class="sxs-lookup"><span data-stu-id="c7878-243">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="c7878-244">Konfigurera varningsaviseringar</span><span class="sxs-lookup"><span data-stu-id="c7878-244">Configure alert notifications</span></span>](configure-email-notifications.md)
