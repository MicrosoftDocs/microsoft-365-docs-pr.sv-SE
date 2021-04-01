---
title: Konfigurera och hantera Microsoft Threat Experts-funktioner via Microsoft 365 Defender
description: Prenumerera på Microsoft Threats Experts via Microsoft 365 Defender för att konfigurera, hantera och använda det i dina dagliga säkerhetsåtgärder och säkerhetsadministration.
keywords: Microsoft Threat Experts, hanterad hot-service, MTE, Microsoft hanterad service för fiske
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.openlocfilehash: e1ccd4404eb94193695239def7f26ba64e70d51d
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476575"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a><span data-ttu-id="be8f7-104">Konfigurera och hantera Microsoft Threat Experts-funktioner via Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be8f7-104">Configure and manage Microsoft Threat Experts capabilities through Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="be8f7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="be8f7-105">**Applies to:**</span></span>

- [<span data-ttu-id="be8f7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be8f7-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="be8f7-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="be8f7-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="be8f7-108">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="be8f7-108">Before you begin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be8f7-109">Innan du ansöker kontrollerar du att du tar upp behörighetskraven för Microsoft Threat Experts – Targeted Attack Notifications som hanteras av din Microsoft Technical Service-leverantör och ditt kontoteam.</span><span class="sxs-lookup"><span data-stu-id="be8f7-109">Before you apply, make sure to discuss the eligibility requirements for the Microsoft Threat Experts – Targeted Attack Notifications managed threat hunting service with your Microsoft Technical Service provider and account team.</span></span>

<span data-ttu-id="be8f7-110">Om du vill ta emot riktade attackmeddelanden måste du ha Microsoft 365 Defender distribuerat med registrerade enheter.</span><span class="sxs-lookup"><span data-stu-id="be8f7-110">To receive targeted attack notifications, you'll need to have Microsoft 365 Defender deployed with devices enrolled.</span></span> <span data-ttu-id="be8f7-111">Skicka sedan ett program via M365-portalen för Microsoft Threat Experts – Riktade attackmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="be8f7-111">Then, submit an application through the M365 portal for Microsoft Threat Experts - Targeted Attack Notifications.</span></span>

<span data-ttu-id="be8f7-112">Kontakta ditt kontoteam eller din Microsoft-representant för att prenumerera på Microsoft Threat Experts – Experts on Demand.</span><span class="sxs-lookup"><span data-stu-id="be8f7-112">Contact your account team or Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span> <span data-ttu-id="be8f7-113">Med experter på begäran kan du rådgöra med våra hotexperter om hur du skyddar organisationen från relevanta identifieringar och adversaries.</span><span class="sxs-lookup"><span data-stu-id="be8f7-113">Experts on Demand lets you consult with our threat experts on how to protect your organization from relevant detections and adversaries.</span></span>

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a><span data-ttu-id="be8f7-114">Sök efter Microsoft Threat Experts – riktad tjänst för attackmeddelanden</span><span class="sxs-lookup"><span data-stu-id="be8f7-114">Apply for Microsoft Threat Experts - Targeted Attack Notifications service</span></span>

<span data-ttu-id="be8f7-115">Om du redan har Microsoft Defender för Endpoint och Microsoft 365 Defender kan du ansöka om Microsoft Threat Experts – Targeted Attack Notifications via Microsoft 365 Defender-portalen.</span><span class="sxs-lookup"><span data-stu-id="be8f7-115">If you already have Microsoft Defender for Endpoint and Microsoft 365 Defender, you can apply for Microsoft Threat Experts – Targeted Attack Notifications through their Microsoft 365 Defender portal.</span></span>  <span data-ttu-id="be8f7-116">Riktade attackmeddelanden ger dig särskilda insikter och analyser som hjälper dig att identifiera de viktigaste hoten för din organisation, så att du kan svara på dem snabbt.</span><span class="sxs-lookup"><span data-stu-id="be8f7-116">Targeted attack notifications grant you special insight and analysis to help identify the most critical threats to your organization, so you can respond to them quickly.</span></span>

1. <span data-ttu-id="be8f7-117">I navigeringsfönstret går du till Inställningar **> slutpunkter > Allmänna > avancerade > Microsoft Threat Experts – Riktade attackmeddelanden.**</span><span class="sxs-lookup"><span data-stu-id="be8f7-117">From the navigation pane, go to **Settings > Endpoints > General > Advanced features > Microsoft Threat Experts - Targeted Attack Notifications**.</span></span>

2. <span data-ttu-id="be8f7-118">Välj **Använd**.</span><span class="sxs-lookup"><span data-stu-id="be8f7-118">Select **Apply**.</span></span>

    ![Bild av inställningar för Microsoft Threat Experts](../../media/mte/mte-collaboratewithmte.png)

3. <span data-ttu-id="be8f7-120">Ange ditt namn och din e-postadress så att Microsoft kan kontakta dig om programmet.</span><span class="sxs-lookup"><span data-stu-id="be8f7-120">Enter your name and email address so that Microsoft can contact you about your application.</span></span>

    ![Bild på programmet Microsoft Threat Experts](../../media/mte/mte-apply.png)

4. <span data-ttu-id="be8f7-122">Läs [sekretesspolicyn](https://privacy.microsoft.com/en-us/privacystatement)och välj sedan **Skicka** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="be8f7-122">Read the [privacy statement](https://privacy.microsoft.com/en-us/privacystatement), then select **Submit** when you're done.</span></span> <span data-ttu-id="be8f7-123">Du får ett välkomstmeddelande via e-post när din ansökan har godkänts.</span><span class="sxs-lookup"><span data-stu-id="be8f7-123">You'll receive a welcome email once your application is approved.</span></span>

    ![Bild på programbekräftelse från Microsoft Threat Experts](../../media/mte/mte-applicationconfirmation.png)

5. <span data-ttu-id="be8f7-125">När du får välkomstmeddelandet får du automatiskt riktade attackmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="be8f7-125">After you receive your welcome email, you'll automatically start receiving targeted attack notifications.</span></span>

6. <span data-ttu-id="be8f7-126">Du kan kontrollera din status genom att gå **till Inställningar > Slutpunkter > Allmänt > Avancerade funktioner.**</span><span class="sxs-lookup"><span data-stu-id="be8f7-126">You can verify your status by visiting **Settings > Endpoints > General > Advanced features**.</span></span> <span data-ttu-id="be8f7-127">När den godkänts **kommer Microsoft Threat Experts – Targeted Attack Notification-knappen** att visas och vara **påslagen.**</span><span class="sxs-lookup"><span data-stu-id="be8f7-127">Once approved, the **Microsoft Threat Experts - Targeted Attack Notification** toggle will be visible and switched **On**.</span></span>

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a><span data-ttu-id="be8f7-128">Var du ser riktade attackmeddelanden från Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="be8f7-128">Where you'll see the targeted attack notifications from Microsoft Threat Experts</span></span>

<span data-ttu-id="be8f7-129">Du kan få riktade attackmeddelanden från Microsoft Threat Experts via följande medium:</span><span class="sxs-lookup"><span data-stu-id="be8f7-129">You can receive targeted attack notification from Microsoft Threat Experts through the following mediums:</span></span>

- <span data-ttu-id="be8f7-130">Sidan Incidenter på Microsoft 365 **Defender-portalen**</span><span class="sxs-lookup"><span data-stu-id="be8f7-130">The Microsoft 365 Defender portal's **Incidents** page</span></span>
- <span data-ttu-id="be8f7-131">Instrumentpanelen Aviseringar på Microsoft 365 **Defender-portalen**</span><span class="sxs-lookup"><span data-stu-id="be8f7-131">The Microsoft 365 Defender portal's **Alerts** dashboard</span></span>
- <span data-ttu-id="be8f7-132">OData-avisering för [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) och [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span><span class="sxs-lookup"><span data-stu-id="be8f7-132">OData alerting [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) and [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span></span>
- <span data-ttu-id="be8f7-133">[DeviceAlertEvents-tabell](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) i Avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="be8f7-133">[DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) table in Advanced hunting</span></span>
- <span data-ttu-id="be8f7-134">Din inkorg om du väljer att få riktade attackmeddelanden skickade till dig via e-post.</span><span class="sxs-lookup"><span data-stu-id="be8f7-134">Your inbox, if you choose to have targeted attack notifications sent to you via email.</span></span> <span data-ttu-id="be8f7-135">Se Skapa [en regel för e-postavisering](#create-an-email-notification-rule) nedan.</span><span class="sxs-lookup"><span data-stu-id="be8f7-135">See [Create an email notification rule](#create-an-email-notification-rule) below.</span></span>

### <a name="create-an-email-notification-rule"></a><span data-ttu-id="be8f7-136">Skapa en regel för e-postavisering</span><span class="sxs-lookup"><span data-stu-id="be8f7-136">Create an email notification rule</span></span>

<span data-ttu-id="be8f7-137">Du kan skapa regler för att skicka e-postaviseringar för aviseringsmottagare.</span><span class="sxs-lookup"><span data-stu-id="be8f7-137">You can create rules to send email notifications for notification recipients.</span></span> <span data-ttu-id="be8f7-138">Fullständig information finns i Konfigurera  [aviseringsmeddelanden för](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) att skapa, redigera, ta bort eller felsöka e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="be8f7-138">For full details, see  [Configure alert notifications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) to create, edit, delete, or troubleshoot email notification.</span></span>

## <a name="view-targeted-attack-notifications"></a><span data-ttu-id="be8f7-139">Visa riktade attackmeddelanden</span><span class="sxs-lookup"><span data-stu-id="be8f7-139">View targeted attack notifications</span></span>

<span data-ttu-id="be8f7-140">Du kommer att få riktade attackmeddelanden från Microsoft Threat Experts i e-postmeddelandet när du har konfigurerat ditt system för att ta emot e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="be8f7-140">You'll start receiving targeted attack notification from Microsoft Threat Experts in your email after you have configured your system to receive email notification.</span></span>

1. <span data-ttu-id="be8f7-141">Välj länken i e-postmeddelandet för att gå till motsvarande aviseringskontext i instrumentpanelen som är märkt **med hotexperter.**</span><span class="sxs-lookup"><span data-stu-id="be8f7-141">Select the link in the email to go to the corresponding alert context in the dashboard tagged with **Threat experts**.</span></span>

2. <span data-ttu-id="be8f7-142">Välj  samma aviseringsavsnitt på sidan Aviseringar som i e-postmeddelandet om du vill visa mer information.</span><span class="sxs-lookup"><span data-stu-id="be8f7-142">From the **Alerts** page, select the same alert topic as the one you received in the email, to view further details.</span></span>

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="be8f7-143">Prenumerera på Microsoft Threat Experts – experter på begäran</span><span class="sxs-lookup"><span data-stu-id="be8f7-143">Subscribe to Microsoft Threat Experts - Experts on Demand</span></span>

<span data-ttu-id="be8f7-144">Om du redan är Microsoft Defender för Endpoint-kund kan du kontakta din Microsoft-representant för att prenumerera på Microsoft Threat Experts – Experts on Demand.</span><span class="sxs-lookup"><span data-stu-id="be8f7-144">If you're already a Microsoft Defender for Endpoint customer, you can contact your Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span>

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a><span data-ttu-id="be8f7-145">Kontakta en Microsoft-expert om misstänkt cybersäkerhet i din organisation</span><span class="sxs-lookup"><span data-stu-id="be8f7-145">Consult a Microsoft threat expert about suspicious cybersecurity activities in your organization</span></span>

<span data-ttu-id="be8f7-146">Du kan kontakta Microsoft Threat Experts inifrån Microsoft 365 Defender-portalen.</span><span class="sxs-lookup"><span data-stu-id="be8f7-146">You can contact Microsoft Threat Experts from inside the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="be8f7-147">Experter kan hjälpa dig att förstå komplexa hot och riktade attackmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="be8f7-147">Experts can help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="be8f7-148">Samarbeta med experter för mer information om aviseringar och incidenter, eller råd om hantering av komprometteringar.</span><span class="sxs-lookup"><span data-stu-id="be8f7-148">Partner with experts for further details about alerts and incidents, or advice on handling compromise.</span></span> <span data-ttu-id="be8f7-149">Få insyn i det hotinformationssammanhang som beskrivs av din portalinstrumentpanel.</span><span class="sxs-lookup"><span data-stu-id="be8f7-149">Gain insight into the threat intelligence context described by your portal dashboard.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="be8f7-150">Aviseringsförfrågningar som rör din organisations anpassade hotinformation stöds inte för närvarande.</span><span class="sxs-lookup"><span data-stu-id="be8f7-150">Alert inquiries related to your organization's customized threat intelligence data are not currently supported.</span></span> <span data-ttu-id="be8f7-151">Kontakta din säkerhets- eller svarsgrupp för incidenter för mer information.</span><span class="sxs-lookup"><span data-stu-id="be8f7-151">Consult with your security operations or incident response team for details.</span></span>
> - <span data-ttu-id="be8f7-152">Du måste ha  behörigheten Hantera säkerhetsinställningar i Säkerhetscenter i Microsoft 365 Defender-portalen för att skicka en förfrågan via Formuläret Konsultera en expert **på** hot.</span><span class="sxs-lookup"><span data-stu-id="be8f7-152">You need to have the **Manage security settings in Security Center** permission in the Microsoft 365 Defender portal to submit an inquiry through the **Consult a threat expert** form.</span></span>

1. <span data-ttu-id="be8f7-153">Gå till portalsidan som är relaterad till den information som du vill **undersöka:** till exempel **Enhet,** **Avisering** eller Incident.</span><span class="sxs-lookup"><span data-stu-id="be8f7-153">Navigate to the portal page related to the information that you'd like to investigate: for example, **Device**, **Alert**, or **Incident**.</span></span> <span data-ttu-id="be8f7-154">Kontrollera att portalsidan som är relaterad till din förfrågan visas innan du skickar en undersökningsförfrågan.</span><span class="sxs-lookup"><span data-stu-id="be8f7-154">Make sure that the portal page related to your inquiry is in view before you send an investigation request.</span></span>

2. <span data-ttu-id="be8f7-155">I den översta menyn väljer du **? Kontakta en hotexpert**.</span><span class="sxs-lookup"><span data-stu-id="be8f7-155">From the top menu, select **? Consult a threat expert**.</span></span>

    ![Bild på Microsoft Threat Experts Experts på begäran från menyn](../../media/mte/incidents-action-mte-highlighted.png)

    <span data-ttu-id="be8f7-157">En utfälld skärm öppnas.</span><span class="sxs-lookup"><span data-stu-id="be8f7-157">A flyout screen will open.</span></span>

    <span data-ttu-id="be8f7-158">Sidhuvudet anger om du använder en utvärderingsprenumeration eller en komplett Microsoft Threat Experts – Experts on-Demand-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="be8f7-158">The header will indicate if you are on a trial subscription, or a full Microsoft Threat Experts - Experts on-Demand subscription.</span></span>

    ![Bild på utvärderingsprenumerationsskärmen med Microsoft Threat Experts on Demand](../../media/mte/mte-trial.png)

    <span data-ttu-id="be8f7-160">Fältet **Undersökningsämne** innehåller redan länken till den aktuella sidan för din begäran.</span><span class="sxs-lookup"><span data-stu-id="be8f7-160">The **Investigation topic** field will already be populated with the link to the relevant page for your request.</span></span>

3. <span data-ttu-id="be8f7-161">I nästa fält bör du ge Microsoft Threat Experts tillräckligt med information för att starta undersökningen.</span><span class="sxs-lookup"><span data-stu-id="be8f7-161">In the next field, provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span></span>

4. <span data-ttu-id="be8f7-162">Ange den e-postadress som du vill använda för att stämma av med Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="be8f7-162">Enter the email address that you'd like to use to correspond with Microsoft Threat Experts.</span></span>

> [!NOTE]
> <span data-ttu-id="be8f7-163">Om du vill spåra status för ärenden av den tekniska experten på begäran via Microsoft Services Hub kan du kontakta din tekniska kontohanterare.</span><span class="sxs-lookup"><span data-stu-id="be8f7-163">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your technical account manager.</span></span>

<span data-ttu-id="be8f7-164">Titta på den här videon för en snabb överblick över Microsoft Services-hubben.</span><span class="sxs-lookup"><span data-stu-id="be8f7-164">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a><span data-ttu-id="be8f7-165">Exempel på undersökningsavsnitt</span><span class="sxs-lookup"><span data-stu-id="be8f7-165">Sample investigation topics</span></span>

### <a name="alert-information"></a><span data-ttu-id="be8f7-166">Aviseringsinformation</span><span class="sxs-lookup"><span data-stu-id="be8f7-166">Alert information</span></span>

- <span data-ttu-id="be8f7-167">Vi såg en ny typ av varning för en binär bo-off-the-land binär.</span><span class="sxs-lookup"><span data-stu-id="be8f7-167">We saw a new type of alert for a living-off-the-land binary.</span></span> <span data-ttu-id="be8f7-168">Vi kan ange aviserings-ID:t.</span><span class="sxs-lookup"><span data-stu-id="be8f7-168">We can provide the alert ID.</span></span> <span data-ttu-id="be8f7-169">Kan du berätta mer om den här aviseringen och hur vi kan undersöka den ytterligare?</span><span class="sxs-lookup"><span data-stu-id="be8f7-169">Can you tell us more about this alert and how we can investigate it further?</span></span>
- <span data-ttu-id="be8f7-170">Vi har observerat två liknande attacker som båda försöker köra skadliga PowerShell-skript men generera olika aviseringar.</span><span class="sxs-lookup"><span data-stu-id="be8f7-170">We've observed two similar attacks, which both try to execute malicious PowerShell scripts but generate different alerts.</span></span> <span data-ttu-id="be8f7-171">Den ena är "Misstänkt PowerShell-kommandorad" och den andra är "En skadlig fil upptäcktes baserat på indikering från O365".</span><span class="sxs-lookup"><span data-stu-id="be8f7-171">One is "Suspicious PowerShell command line" and the other is "A malicious file was detected based on indication provided by O365".</span></span> <span data-ttu-id="be8f7-172">Vad är skillnaden?</span><span class="sxs-lookup"><span data-stu-id="be8f7-172">What is the difference?</span></span>
- <span data-ttu-id="be8f7-173">Vi fick en udda avisering idag om ett felaktigt antal misslyckade inloggningar från en användares enhet.</span><span class="sxs-lookup"><span data-stu-id="be8f7-173">We received an odd alert today about an abnormal number of failed logins from a high profile user’s device.</span></span> <span data-ttu-id="be8f7-174">Vi hittar inga ytterligare bevis för försöken.</span><span class="sxs-lookup"><span data-stu-id="be8f7-174">We can't find any further evidence for these attempts.</span></span> <span data-ttu-id="be8f7-175">Hur kan Microsoft 365 Defender se de här försöken?</span><span class="sxs-lookup"><span data-stu-id="be8f7-175">How can Microsoft 365 Defender see these attempts?</span></span> <span data-ttu-id="be8f7-176">Vilken typ av inloggning övervakas?</span><span class="sxs-lookup"><span data-stu-id="be8f7-176">What type of logins are being monitored?</span></span>
- <span data-ttu-id="be8f7-177">Kan du ge mer kontext eller information om aviseringen, "Misstänkt beteende av ett systemverktyg har observerats"?</span><span class="sxs-lookup"><span data-stu-id="be8f7-177">Can you give more context or insight about the alert, "Suspicious behavior by a system utility was observed"?</span></span>
- <span data-ttu-id="be8f7-178">Jag har sett en avisering med namnet "Skapande av vidare vidarebefordran/omdirigeringsregel".</span><span class="sxs-lookup"><span data-stu-id="be8f7-178">I observed an alert titled "Creation of forwarding/redirect rule".</span></span> <span data-ttu-id="be8f7-179">Jag tror att aktiviteten är sann.</span><span class="sxs-lookup"><span data-stu-id="be8f7-179">I believe the activity is benign.</span></span> <span data-ttu-id="be8f7-180">Kan du berätta varför jag fick en avisering?</span><span class="sxs-lookup"><span data-stu-id="be8f7-180">Can you tell me why I received an alert?</span></span>

### <a name="possible-machine-compromise"></a><span data-ttu-id="be8f7-181">Möjlig datorkompromettering</span><span class="sxs-lookup"><span data-stu-id="be8f7-181">Possible machine compromise</span></span>

- <span data-ttu-id="be8f7-182">Kan du hjälpa dig att förklara varför vi ser ett meddelande eller en avisering om att "okänd process observeras" på många enheter i vår organisation?</span><span class="sxs-lookup"><span data-stu-id="be8f7-182">Can you help explain why we see a message or alert for "Unknown process observed" on many devices in our organization?</span></span> <span data-ttu-id="be8f7-183">Vi uppskattar eventuella synpunkter för att klargöra om det här meddelandet eller aviseringen är relaterat till skadlig aktivitet.</span><span class="sxs-lookup"><span data-stu-id="be8f7-183">We appreciate any input to clarify whether this message or alert is related to malicious activity.</span></span>
- <span data-ttu-id="be8f7-184">Kan du verifiera en möjlig kompromett på följande system, från förra veckan?</span><span class="sxs-lookup"><span data-stu-id="be8f7-184">Can you help validate a possible compromise on the following system, dating from last week?</span></span> <span data-ttu-id="be8f7-185">Det fungerar ungefär som en tidigare identifiering av skadlig programvara på samma system för sex månader sedan.</span><span class="sxs-lookup"><span data-stu-id="be8f7-185">It's behaving similarly as a previous malware detection on the same system six months ago.</span></span>

### <a name="threat-intelligence-details"></a><span data-ttu-id="be8f7-186">Information om hotinformation</span><span class="sxs-lookup"><span data-stu-id="be8f7-186">Threat intelligence details</span></span>

- <span data-ttu-id="be8f7-187">Vi har upptäckt ett nätfiskemeddelande som levererade ett skadligt Word-dokument till en användare.</span><span class="sxs-lookup"><span data-stu-id="be8f7-187">We detected a phishing email that delivered a malicious Word document to a user.</span></span> <span data-ttu-id="be8f7-188">Dokumentet orsakade en serie misstänkta händelser, vilket utlöste flera aviseringar för en viss skadlig programvara-familj.</span><span class="sxs-lookup"><span data-stu-id="be8f7-188">The document caused a series of suspicious events, which triggered multiple alerts for a particular malware family.</span></span> <span data-ttu-id="be8f7-189">Har du någon information om den här skadlig programvara?</span><span class="sxs-lookup"><span data-stu-id="be8f7-189">Do you have any information on this malware?</span></span> <span data-ttu-id="be8f7-190">Om ja, kan du skicka oss en länk?</span><span class="sxs-lookup"><span data-stu-id="be8f7-190">If yes, can you send us a link?</span></span>
- <span data-ttu-id="be8f7-191">Vi såg nyligen ett blogginlägg om ett hot som riktar sig till vår bransch.</span><span class="sxs-lookup"><span data-stu-id="be8f7-191">We recently saw a blog post about a threat that is targeting our industry.</span></span> <span data-ttu-id="be8f7-192">Kan du hjälpa oss att förstå vilket skydd Microsoft 365 Defender ger mot den här hot aktören?</span><span class="sxs-lookup"><span data-stu-id="be8f7-192">Can you help us understand what protection Microsoft 365 Defender provides against this threat actor?</span></span>
- <span data-ttu-id="be8f7-193">Vi har nyligen observerat en nätfiskekampanj som utförts mot vår organisation.</span><span class="sxs-lookup"><span data-stu-id="be8f7-193">We recently observed a phishing campaign conducted against our organization.</span></span> <span data-ttu-id="be8f7-194">Kan du tala om för oss om detta var specifikt riktat till vårt företag eller lodrätt?</span><span class="sxs-lookup"><span data-stu-id="be8f7-194">Can you tell us if this was targeted specifically to our company or vertical?</span></span>

### <a name="microsoft-threat-experts-alert-communications"></a><span data-ttu-id="be8f7-195">Aviseringsmeddelanden från Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="be8f7-195">Microsoft Threat Experts’ alert communications</span></span>

- <span data-ttu-id="be8f7-196">Kan ditt svarsteam för incidenter hjälpa oss att hantera det riktade attackmeddelandet vi fick?</span><span class="sxs-lookup"><span data-stu-id="be8f7-196">Can your incident response team help us address the targeted attack notification that we got?</span></span>
- <span data-ttu-id="be8f7-197">Vi har fått den här riktade attackmeddelandet från Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="be8f7-197">We received this targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="be8f7-198">Vi har inte vårt eget svarsteam för incidenter.</span><span class="sxs-lookup"><span data-stu-id="be8f7-198">We don’t have our own incident response team.</span></span> <span data-ttu-id="be8f7-199">Vad kan vi göra nu och hur kan vi begränsa händelsen?</span><span class="sxs-lookup"><span data-stu-id="be8f7-199">What can we do now, and how can we contain the incident?</span></span>
- <span data-ttu-id="be8f7-200">Vi har fått en riktad attackavisering från Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="be8f7-200">We received a targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="be8f7-201">Vilka data kan du ge oss som vi kan skicka till vårt svarsteam för incidenter?</span><span class="sxs-lookup"><span data-stu-id="be8f7-201">What data can you provide to us that we can pass on to our incident response team?</span></span>

> [!NOTE]
> <span data-ttu-id="be8f7-202">Microsoft Threat Experts är en hanterad tjänst för hot efter hot och inte en svarstjänst för incidenter.</span><span class="sxs-lookup"><span data-stu-id="be8f7-202">Microsoft Threat Experts is a managed threat hunting service and not an incident response service.</span></span> <span data-ttu-id="be8f7-203">Vid behov kan experterna vid behov smidigt gå över undersökningen till TJÄNSTEN Microsoft Cybersecurity Solutions Group (CSG) för tjänsten Detection and Response Team (PHOTOSHOP).</span><span class="sxs-lookup"><span data-stu-id="be8f7-203">However, the experts can seamlessly transition the investigation to Microsoft Cybersecurity Solutions Group (CSG)'s Detection and Response Team (DART) services, when necessary.</span></span> <span data-ttu-id="be8f7-204">Du kan också välja att kommunicera med din egen svarsgrupp för incidenter för att åtgärda problem som kräver ett incidentsvar.</span><span class="sxs-lookup"><span data-stu-id="be8f7-204">You can also opt to engage with your own incident response team to address issues that requires an incident response.</span></span>

## <a name="scenario"></a><span data-ttu-id="be8f7-205">Scenario</span><span class="sxs-lookup"><span data-stu-id="be8f7-205">Scenario</span></span>

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a><span data-ttu-id="be8f7-206">Få en förloppsrapport om din förfrågan om hanterad förfrågan</span><span class="sxs-lookup"><span data-stu-id="be8f7-206">Receive a progress report about your managed hunting inquiry</span></span>

<span data-ttu-id="be8f7-207">Svaret från Microsoft Threat Experts varierar beroende på din förfrågan.</span><span class="sxs-lookup"><span data-stu-id="be8f7-207">The response from Microsoft Threat Experts will vary according to your inquiry.</span></span> <span data-ttu-id="be8f7-208">I allmänhet får du något av följande svar:</span><span class="sxs-lookup"><span data-stu-id="be8f7-208">You'll generally receive one of the following responses:</span></span>

- <span data-ttu-id="be8f7-209">Mer information krävs för att fortsätta med undersökningen</span><span class="sxs-lookup"><span data-stu-id="be8f7-209">More information is needed to continue with the investigation</span></span>
- <span data-ttu-id="be8f7-210">Det krävs en eller flera filexempel för att avgöra det tekniska sammanhanget</span><span class="sxs-lookup"><span data-stu-id="be8f7-210">A file or several file samples are needed to determine the technical context</span></span>
- <span data-ttu-id="be8f7-211">Undersökning kräver mer tid</span><span class="sxs-lookup"><span data-stu-id="be8f7-211">Investigation requires more time</span></span>
- <span data-ttu-id="be8f7-212">Den inledande informationen var tillräcklig för att slutföra undersökningen</span><span class="sxs-lookup"><span data-stu-id="be8f7-212">Initial information was enough to conclude the investigation</span></span>

<span data-ttu-id="be8f7-213">Om en expert begär mer information eller filprov är det centralt att svara snabbt för att hålla undersökningen igång.</span><span class="sxs-lookup"><span data-stu-id="be8f7-213">If an expert requests more information or file samples, it's crucial to respond quickly to keep the investigation moving.</span></span>

## <a name="see-also"></a><span data-ttu-id="be8f7-214">Se även</span><span class="sxs-lookup"><span data-stu-id="be8f7-214">See also</span></span>

- [<span data-ttu-id="be8f7-215">Översikt över Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="be8f7-215">Microsoft Threat Experts overview</span></span>](microsoft-threat-experts.md)
