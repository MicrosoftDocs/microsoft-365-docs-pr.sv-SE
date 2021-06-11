---
title: Konfigurera och hantera Microsoft Hotexperter funktioner via Microsoft 365 Defender
description: Prenumerera på Microsoft Threats Experts via Microsoft 365 Defender för att konfigurera, hantera och använda det i dina dagliga säkerhetsåtgärder och säkerhetsadministration.
keywords: Microsoft Hotexperter, hanterad säkerhetstjänst för hot, MTE, Microsoft-hanterad service för hot
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
localization_priority: normal
manager: dansimp
audience: ITPro
ms.topic: article
ms.openlocfilehash: 0ccb8482dae94de4a9f43a5ecaf7c701e6dd82a5
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844796"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a><span data-ttu-id="c1bb1-104">Konfigurera och hantera Microsoft Hotexperter funktioner via Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1bb1-104">Configure and manage Microsoft Threat Experts capabilities through Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c1bb1-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c1bb1-105">**Applies to:**</span></span>

- [<span data-ttu-id="c1bb1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1bb1-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="c1bb1-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="c1bb1-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="c1bb1-108">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="c1bb1-108">Before you begin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c1bb1-109">Innan du ansöker kontrollerar du att du tar upp behörighetskraven för den tekniska Microsoft Hotexperter – Riktad attackaviseringar med din Microsoft-leverantör och ditt kontoteam för tekniska tjänster.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-109">Before you apply, make sure to discuss the eligibility requirements for the Microsoft Threat Experts – Targeted Attack Notifications managed threat hunting service with your Microsoft Technical Service provider and account team.</span></span>

<span data-ttu-id="c1bb1-110">Om du vill ta emot riktade attackmeddelanden måste du ha Microsoft 365 Defender distribuerad med registrerade enheter.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-110">To receive targeted attack notifications, you'll need to have Microsoft 365 Defender deployed with devices enrolled.</span></span> <span data-ttu-id="c1bb1-111">Skicka sedan ett program via M365-portalen för Microsoft Hotexperter – Riktade attackmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-111">Then, submit an application through the M365 portal for Microsoft Threat Experts - Targeted Attack Notifications.</span></span>

<span data-ttu-id="c1bb1-112">Kontakta din kontogrupp eller Microsoft-representant för att prenumerera Microsoft Hotexperter - Experter på begäran.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-112">Contact your account team or Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span> <span data-ttu-id="c1bb1-113">Med experter på begäran kan du rådgöra med våra hotexperter om hur du skyddar organisationen från relevanta identifieringar och adversaries.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-113">Experts on Demand lets you consult with our threat experts on how to protect your organization from relevant detections and adversaries.</span></span>

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a><span data-ttu-id="c1bb1-114">Ansök för Microsoft Hotexperter – riktad tjänst för attackmeddelanden</span><span class="sxs-lookup"><span data-stu-id="c1bb1-114">Apply for Microsoft Threat Experts - Targeted Attack Notifications service</span></span>

<span data-ttu-id="c1bb1-115">Om du redan har Microsoft Defender för Slutpunkt och Microsoft 365 Defender kan du ansöka om Microsoft Hotexperter – riktade attackmeddelanden via deras Microsoft 365 Defender-portal.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-115">If you already have Microsoft Defender for Endpoint and Microsoft 365 Defender, you can apply for Microsoft Threat Experts – Targeted Attack Notifications through their Microsoft 365 Defender portal.</span></span>  <span data-ttu-id="c1bb1-116">Riktade attackmeddelanden ger dig särskilda insikter och analyser som hjälper dig att identifiera de viktigaste hoten för din organisation, så att du kan svara på dem snabbt.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-116">Targeted attack notifications grant you special insight and analysis to help identify the most critical threats to your organization, so you can respond to them quickly.</span></span>

1. <span data-ttu-id="c1bb1-117">I navigeringsfönstret går du till **slutpunkter Inställningar > till > Allmänt > funktioner > Microsoft Hotexperter – Riktade attackmeddelanden.**</span><span class="sxs-lookup"><span data-stu-id="c1bb1-117">From the navigation pane, go to **Settings > Endpoints > General > Advanced features > Microsoft Threat Experts - Targeted Attack Notifications**.</span></span>

2. <span data-ttu-id="c1bb1-118">Välj **Använd**.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-118">Select **Apply**.</span></span>

    ![Bild av Microsoft Hotexperter inställningar](../../media/mte/mte-collaboratewithmte.png)

3. <span data-ttu-id="c1bb1-120">Ange ditt namn och din e-postadress så att Microsoft kan kontakta dig om programmet.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-120">Enter your name and email address so that Microsoft can contact you about your application.</span></span>

    ![Bild på Microsoft Hotexperter program](../../media/mte/mte-apply.png)

4. <span data-ttu-id="c1bb1-122">Läs [sekretesspolicyn](https://privacy.microsoft.com/en-us/privacystatement)och välj sedan **Skicka** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-122">Read the [privacy statement](https://privacy.microsoft.com/en-us/privacystatement), then select **Submit** when you're done.</span></span> <span data-ttu-id="c1bb1-123">Du får ett välkomstmeddelande via e-post när din ansökan har godkänts.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-123">You'll receive a welcome email once your application is approved.</span></span>

    ![Bild på Microsoft Hotexperter programbekräftelse](../../media/mte/mte-applicationconfirmation.png)

5. <span data-ttu-id="c1bb1-125">När du får välkomstmeddelandet får du automatiskt riktade attackmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-125">After you receive your welcome email, you'll automatically start receiving targeted attack notifications.</span></span>

6. <span data-ttu-id="c1bb1-126">Du kan kontrollera din status genom att **gå Inställningar > slutpunkter > Allmänna > Avancerade funktioner.**</span><span class="sxs-lookup"><span data-stu-id="c1bb1-126">You can verify your status by visiting **Settings > Endpoints > General > Advanced features**.</span></span> <span data-ttu-id="c1bb1-127">När den godkänts **Microsoft Hotexperter - Riktad attackmeddelandeknapp** visas och är **påslagen.**</span><span class="sxs-lookup"><span data-stu-id="c1bb1-127">Once approved, the **Microsoft Threat Experts - Targeted Attack Notification** toggle will be visible and switched **On**.</span></span>

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a><span data-ttu-id="c1bb1-128">Var du ser riktade attackmeddelanden från Microsoft Hotexperter</span><span class="sxs-lookup"><span data-stu-id="c1bb1-128">Where you'll see the targeted attack notifications from Microsoft Threat Experts</span></span>

<span data-ttu-id="c1bb1-129">Du kan få riktade attackmeddelanden från Microsoft Hotexperter via följande medium:</span><span class="sxs-lookup"><span data-stu-id="c1bb1-129">You can receive targeted attack notification from Microsoft Threat Experts through the following mediums:</span></span>

- <span data-ttu-id="c1bb1-130">Sidan Microsoft 365 i **Defender-portalen**</span><span class="sxs-lookup"><span data-stu-id="c1bb1-130">The Microsoft 365 Defender portal's **Incidents** page</span></span>
- <span data-ttu-id="c1bb1-131">Instrumentpanelen Microsoft 365 Avisering på **Defender-portalen**</span><span class="sxs-lookup"><span data-stu-id="c1bb1-131">The Microsoft 365 Defender portal's **Alerts** dashboard</span></span>
- <span data-ttu-id="c1bb1-132">OData-avisering för [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) och [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span><span class="sxs-lookup"><span data-stu-id="c1bb1-132">OData alerting [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) and [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span></span>
- <span data-ttu-id="c1bb1-133">[DeviceAlertEvents-tabell](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) i Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="c1bb1-133">[DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) table in Advanced hunting</span></span>
- <span data-ttu-id="c1bb1-134">Din inkorg om du väljer att få riktade attackmeddelanden skickade till dig via e-post.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-134">Your inbox, if you choose to have targeted attack notifications sent to you via email.</span></span> <span data-ttu-id="c1bb1-135">Se Skapa [en regel för e-postavisering](#create-an-email-notification-rule) nedan.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-135">See [Create an email notification rule](#create-an-email-notification-rule) below.</span></span>

### <a name="create-an-email-notification-rule"></a><span data-ttu-id="c1bb1-136">Skapa en regel för e-postavisering</span><span class="sxs-lookup"><span data-stu-id="c1bb1-136">Create an email notification rule</span></span>

<span data-ttu-id="c1bb1-137">Du kan skapa regler för att skicka e-postaviseringar för aviseringsmottagare.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-137">You can create rules to send email notifications for notification recipients.</span></span> <span data-ttu-id="c1bb1-138">Fullständig information finns i Konfigurera  [aviseringsmeddelanden för](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) att skapa, redigera, ta bort eller felsöka e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-138">For full details, see  [Configure alert notifications](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) to create, edit, delete, or troubleshoot email notification.</span></span>

## <a name="view-targeted-attack-notifications"></a><span data-ttu-id="c1bb1-139">Visa riktade attackmeddelanden</span><span class="sxs-lookup"><span data-stu-id="c1bb1-139">View targeted attack notifications</span></span>

<span data-ttu-id="c1bb1-140">Du börjar ta emot riktade attackaviseringar från e Microsoft Hotexperter postmeddelanden när du har konfigurerat systemet för att ta emot e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-140">You'll start receiving targeted attack notification from Microsoft Threat Experts in your email after you have configured your system to receive email notification.</span></span>

1. <span data-ttu-id="c1bb1-141">Välj länken i e-postmeddelandet för att gå till motsvarande aviseringskontext i instrumentpanelen som är märkt **med hotexperter.**</span><span class="sxs-lookup"><span data-stu-id="c1bb1-141">Select the link in the email to go to the corresponding alert context in the dashboard tagged with **Threat experts**.</span></span>

2. <span data-ttu-id="c1bb1-142">Välj  samma aviseringsavsnitt på sidan Aviseringar som i e-postmeddelandet om du vill visa mer information.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-142">From the **Alerts** page, select the same alert topic as the one you received in the email, to view further details.</span></span>

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="c1bb1-143">Prenumerera på Microsoft Hotexperter – experter på begäran</span><span class="sxs-lookup"><span data-stu-id="c1bb1-143">Subscribe to Microsoft Threat Experts - Experts on Demand</span></span>

<span data-ttu-id="c1bb1-144">Om du redan är Microsoft Defender för Endpoint-kund kan du kontakta din Microsoft-representant för att prenumerera på Microsoft Hotexperter - experter på begäran.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-144">If you're already a Microsoft Defender for Endpoint customer, you can contact your Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span>

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a><span data-ttu-id="c1bb1-145">Kontakta en Microsoft-expert om misstänkt cybersäkerhet i din organisation</span><span class="sxs-lookup"><span data-stu-id="c1bb1-145">Consult a Microsoft threat expert about suspicious cybersecurity activities in your organization</span></span>

<span data-ttu-id="c1bb1-146">Du kan kontakta Microsoft Hotexperter inifrån Microsoft 365 Defender-portalen.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-146">You can contact Microsoft Threat Experts from inside the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="c1bb1-147">Experter kan hjälpa dig att förstå komplexa hot och riktade attackmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-147">Experts can help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="c1bb1-148">Samarbeta med experter för mer information om aviseringar och incidenter, eller råd om hantering av komprometteringar.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-148">Partner with experts for further details about alerts and incidents, or advice on handling compromise.</span></span> <span data-ttu-id="c1bb1-149">Få insyn i det hotinformationssammanhang som beskrivs av din portalinstrumentpanel.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-149">Gain insight into the threat intelligence context described by your portal dashboard.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c1bb1-150">Aviseringsförfrågningar som rör din organisations anpassade hotinformation stöds inte för närvarande.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-150">Alert inquiries related to your organization's customized threat intelligence data are not currently supported.</span></span> <span data-ttu-id="c1bb1-151">Kontakta din säkerhets- eller svarsgrupp för incidenter för mer information.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-151">Consult with your security operations or incident response team for details.</span></span>
> - <span data-ttu-id="c1bb1-152">Du måste ha  behörigheten Hantera säkerhetsinställningar i Säkerhetscenter i Microsoft 365 Defender-portalen för att skicka en förfrågan via formuläret Konsultera en expert **på** hot.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-152">You need to have the **Manage security settings in Security Center** permission in the Microsoft 365 Defender portal to submit an inquiry through the **Consult a threat expert** form.</span></span>

1. <span data-ttu-id="c1bb1-153">Gå till portalsidan som är relaterad till den information som du vill **undersöka:** till exempel **Enhet,** **Avisering** eller Incident.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-153">Navigate to the portal page related to the information that you'd like to investigate: for example, **Device**, **Alert**, or **Incident**.</span></span> <span data-ttu-id="c1bb1-154">Kontrollera att portalsidan som är relaterad till din förfrågan visas innan du skickar en undersökningsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-154">Make sure that the portal page related to your inquiry is in view before you send an investigation request.</span></span>

2. <span data-ttu-id="c1bb1-155">I den översta menyn väljer du **? Kontakta en hotexpert**.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-155">From the top menu, select **? Consult a threat expert**.</span></span>

    ![Bild på Microsoft Hotexperter på begäran från menyn](../../media/mte/incidents-action-mte-highlighted.png)

    <span data-ttu-id="c1bb1-157">En utfälld skärm öppnas.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-157">A flyout screen will open.</span></span>

    <span data-ttu-id="c1bb1-158">I sidhuvudet visas om du använder en utvärderingsprenumeration eller en fullständig Microsoft Hotexperter - Experter på begäran-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-158">The header will indicate if you are on a trial subscription, or a full Microsoft Threat Experts - Experts on-Demand subscription.</span></span>

    ![Bild av Microsoft Hotexperter provprenumeration på experter på begäran](../../media/mte/mte-trial.png)

    <span data-ttu-id="c1bb1-160">Fältet **Undersökningsämne** innehåller redan länken till den aktuella sidan för din begäran.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-160">The **Investigation topic** field will already be populated with the link to the relevant page for your request.</span></span>

3. <span data-ttu-id="c1bb1-161">Ange tillräckligt med information i nästa fält för att ge Microsoft Hotexperter tillräckligt med kontext för att starta undersökningen.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-161">In the next field, provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span></span>

4. <span data-ttu-id="c1bb1-162">Ange den e-postadress som du vill använda för att motsvara Microsoft Hotexperter.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-162">Enter the email address that you'd like to use to correspond with Microsoft Threat Experts.</span></span>

> [!NOTE]
> <span data-ttu-id="c1bb1-163">Om du vill spåra status för ärenden av den tekniska experten på begäran via Microsoft Services Hub kan du kontakta din tekniska kontohanterare.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-163">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your technical account manager.</span></span>

<span data-ttu-id="c1bb1-164">Titta på den här videon för en snabb överblick över Microsoft Services-hubben.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-164">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a><span data-ttu-id="c1bb1-165">Exempel på undersökningsavsnitt</span><span class="sxs-lookup"><span data-stu-id="c1bb1-165">Sample investigation topics</span></span>

### <a name="alert-information"></a><span data-ttu-id="c1bb1-166">Aviseringsinformation</span><span class="sxs-lookup"><span data-stu-id="c1bb1-166">Alert information</span></span>

- <span data-ttu-id="c1bb1-167">Vi såg en ny typ av varning för en binär bo-off-the-land binär.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-167">We saw a new type of alert for a living-off-the-land binary.</span></span> <span data-ttu-id="c1bb1-168">Vi kan ange aviserings-ID:t.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-168">We can provide the alert ID.</span></span> <span data-ttu-id="c1bb1-169">Kan du berätta mer om den här aviseringen och hur vi kan undersöka den ytterligare?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-169">Can you tell us more about this alert and how we can investigate it further?</span></span>
- <span data-ttu-id="c1bb1-170">Vi har observerat två liknande attacker som båda försöker köra skadliga PowerShell-skript men generera olika aviseringar.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-170">We've observed two similar attacks, which both try to execute malicious PowerShell scripts but generate different alerts.</span></span> <span data-ttu-id="c1bb1-171">Den ena är "Misstänkt PowerShell-kommandorad" och den andra är "En skadlig fil upptäcktes baserat på indikering från O365".</span><span class="sxs-lookup"><span data-stu-id="c1bb1-171">One is "Suspicious PowerShell command line" and the other is "A malicious file was detected based on indication provided by O365".</span></span> <span data-ttu-id="c1bb1-172">Vad är skillnaden?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-172">What is the difference?</span></span>
- <span data-ttu-id="c1bb1-173">Vi fick en udda avisering idag om ett felaktigt antal misslyckade inloggningar från en användares enhet.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-173">We received an odd alert today about an abnormal number of failed logins from a high profile user’s device.</span></span> <span data-ttu-id="c1bb1-174">Vi hittar inga ytterligare bevis för försöken.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-174">We can't find any further evidence for these attempts.</span></span> <span data-ttu-id="c1bb1-175">Hur visar Microsoft 365 Defender de här försöken?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-175">How can Microsoft 365 Defender see these attempts?</span></span> <span data-ttu-id="c1bb1-176">Vilken typ av inloggning övervakas?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-176">What type of logins are being monitored?</span></span>
- <span data-ttu-id="c1bb1-177">Kan du ge mer kontext eller information om aviseringen, "Misstänkt beteende av ett systemverktyg har observerats"?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-177">Can you give more context or insight about the alert, "Suspicious behavior by a system utility was observed"?</span></span>
- <span data-ttu-id="c1bb1-178">Jag har sett en avisering med namnet "Skapande av vidare vidarebefordran/omdirigeringsregel".</span><span class="sxs-lookup"><span data-stu-id="c1bb1-178">I observed an alert titled "Creation of forwarding/redirect rule".</span></span> <span data-ttu-id="c1bb1-179">Jag tror att aktiviteten är sann.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-179">I believe the activity is benign.</span></span> <span data-ttu-id="c1bb1-180">Kan du berätta varför jag fick en avisering?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-180">Can you tell me why I received an alert?</span></span>

### <a name="possible-machine-compromise"></a><span data-ttu-id="c1bb1-181">Möjlig datorkompromettering</span><span class="sxs-lookup"><span data-stu-id="c1bb1-181">Possible machine compromise</span></span>

- <span data-ttu-id="c1bb1-182">Kan du hjälpa dig att förklara varför vi ser ett meddelande eller en avisering om att "okänd process observeras" på många enheter i vår organisation?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-182">Can you help explain why we see a message or alert for "Unknown process observed" on many devices in our organization?</span></span> <span data-ttu-id="c1bb1-183">Vi uppskattar eventuella synpunkter för att klargöra om det här meddelandet eller aviseringen är relaterat till skadlig aktivitet.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-183">We appreciate any input to clarify whether this message or alert is related to malicious activity.</span></span>
- <span data-ttu-id="c1bb1-184">Kan du verifiera en möjlig kompromett på följande system, från förra veckan?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-184">Can you help validate a possible compromise on the following system, dating from last week?</span></span> <span data-ttu-id="c1bb1-185">Det fungerar ungefär som en tidigare identifiering av skadlig programvara på samma system för sex månader sedan.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-185">It's behaving similarly as a previous malware detection on the same system six months ago.</span></span>

### <a name="threat-intelligence-details"></a><span data-ttu-id="c1bb1-186">Information om hotinformation</span><span class="sxs-lookup"><span data-stu-id="c1bb1-186">Threat intelligence details</span></span>

- <span data-ttu-id="c1bb1-187">Vi har upptäckt ett nätfiskemeddelande som levererade ett skadligt Word-dokument till en användare.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-187">We detected a phishing email that delivered a malicious Word document to a user.</span></span> <span data-ttu-id="c1bb1-188">Dokumentet orsakade en serie misstänkta händelser, vilket utlöste flera aviseringar för en viss skadlig programvara-familj.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-188">The document caused a series of suspicious events, which triggered multiple alerts for a particular malware family.</span></span> <span data-ttu-id="c1bb1-189">Har du någon information om den här skadlig programvara?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-189">Do you have any information on this malware?</span></span> <span data-ttu-id="c1bb1-190">Om ja, kan du skicka oss en länk?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-190">If yes, can you send us a link?</span></span>
- <span data-ttu-id="c1bb1-191">Vi såg nyligen ett blogginlägg om ett hot som riktar sig till vår bransch.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-191">We recently saw a blog post about a threat that is targeting our industry.</span></span> <span data-ttu-id="c1bb1-192">Kan du hjälpa oss att förstå vilket skydd Microsoft 365 Defender ger mot den här hot aktören?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-192">Can you help us understand what protection Microsoft 365 Defender provides against this threat actor?</span></span>
- <span data-ttu-id="c1bb1-193">Vi har nyligen observerat en nätfiskekampanj som utförts mot vår organisation.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-193">We recently observed a phishing campaign conducted against our organization.</span></span> <span data-ttu-id="c1bb1-194">Kan du tala om för oss om detta var specifikt riktat till vårt företag eller lodrätt?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-194">Can you tell us if this was targeted specifically to our company or vertical?</span></span>

### <a name="microsoft-threat-experts-alert-communications"></a><span data-ttu-id="c1bb1-195">Microsoft Hotexperter aviseringsmeddelanden</span><span class="sxs-lookup"><span data-stu-id="c1bb1-195">Microsoft Threat Experts’ alert communications</span></span>

- <span data-ttu-id="c1bb1-196">Kan ditt svarsteam för incidenter hjälpa oss att hantera det riktade attackmeddelandet vi fick?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-196">Can your incident response team help us address the targeted attack notification that we got?</span></span>
- <span data-ttu-id="c1bb1-197">Vi har fått den här riktade attackmeddelandet från Microsoft Hotexperter.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-197">We received this targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="c1bb1-198">Vi har inte vårt eget svarsteam för incidenter.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-198">We don’t have our own incident response team.</span></span> <span data-ttu-id="c1bb1-199">Vad kan vi göra nu och hur kan vi begränsa händelsen?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-199">What can we do now, and how can we contain the incident?</span></span>
- <span data-ttu-id="c1bb1-200">Vi har fått ett meddelande om riktad attack från Microsoft Hotexperter.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-200">We received a targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="c1bb1-201">Vilka data kan du ge oss som vi kan skicka till vårt svarsteam för incidenter?</span><span class="sxs-lookup"><span data-stu-id="c1bb1-201">What data can you provide to us that we can pass on to our incident response team?</span></span>

> [!NOTE]
> <span data-ttu-id="c1bb1-202">Microsoft Hotexperter är en hanterad tjänst för hot efter hot och inte en svarstjänst för incidenter.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-202">Microsoft Threat Experts is a managed threat hunting service and not an incident response service.</span></span> <span data-ttu-id="c1bb1-203">Vid behov kan experterna vid behov smidigt gå över undersökningen till TJÄNSTEN Microsoft Cybersecurity Solutions Group (CSG) för tjänsten Detection and Response Team (PHOTOSHOP).</span><span class="sxs-lookup"><span data-stu-id="c1bb1-203">However, the experts can seamlessly transition the investigation to Microsoft Cybersecurity Solutions Group (CSG)'s Detection and Response Team (DART) services, when necessary.</span></span> <span data-ttu-id="c1bb1-204">Du kan också välja att kommunicera med din egen svarsgrupp för incidenter för att åtgärda problem som kräver ett incidentsvar.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-204">You can also opt to engage with your own incident response team to address issues that requires an incident response.</span></span>

## <a name="scenario"></a><span data-ttu-id="c1bb1-205">Scenario</span><span class="sxs-lookup"><span data-stu-id="c1bb1-205">Scenario</span></span>

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a><span data-ttu-id="c1bb1-206">Få en förloppsrapport om din förfrågan om hanterad förfrågan</span><span class="sxs-lookup"><span data-stu-id="c1bb1-206">Receive a progress report about your managed hunting inquiry</span></span>

<span data-ttu-id="c1bb1-207">Svaret från Microsoft Hotexperter varierar beroende på din förfrågan.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-207">The response from Microsoft Threat Experts will vary according to your inquiry.</span></span> <span data-ttu-id="c1bb1-208">I allmänhet får du något av följande svar:</span><span class="sxs-lookup"><span data-stu-id="c1bb1-208">You'll generally receive one of the following responses:</span></span>

- <span data-ttu-id="c1bb1-209">Mer information krävs för att fortsätta med undersökningen</span><span class="sxs-lookup"><span data-stu-id="c1bb1-209">More information is needed to continue with the investigation</span></span>
- <span data-ttu-id="c1bb1-210">Det krävs en eller flera filexempel för att avgöra det tekniska sammanhanget</span><span class="sxs-lookup"><span data-stu-id="c1bb1-210">A file or several file samples are needed to determine the technical context</span></span>
- <span data-ttu-id="c1bb1-211">Undersökning kräver mer tid</span><span class="sxs-lookup"><span data-stu-id="c1bb1-211">Investigation requires more time</span></span>
- <span data-ttu-id="c1bb1-212">Den inledande informationen var tillräcklig för att slutföra undersökningen</span><span class="sxs-lookup"><span data-stu-id="c1bb1-212">Initial information was enough to conclude the investigation</span></span>

<span data-ttu-id="c1bb1-213">Om en expert begär mer information eller filprov är det centralt att svara snabbt för att hålla undersökningen igång.</span><span class="sxs-lookup"><span data-stu-id="c1bb1-213">If an expert requests more information or file samples, it's crucial to respond quickly to keep the investigation moving.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1bb1-214">Se även</span><span class="sxs-lookup"><span data-stu-id="c1bb1-214">See also</span></span>

- [<span data-ttu-id="c1bb1-215">Översikt över Microsoft Hotexperter</span><span class="sxs-lookup"><span data-stu-id="c1bb1-215">Microsoft Threat Experts overview</span></span>](microsoft-threat-experts.md)
