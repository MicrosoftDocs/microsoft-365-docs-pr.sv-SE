---
title: AttackTat In Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig hur de kan använda Attack Program för att köra simulerade nätfiske- och lösenordsattacker i sina organisationer med Microsoft 365 E5 eller Microsoft Defender för Office 365 Abonnemang 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7c88a5df6fae61e1ffe70214ad4a73deef4b380e
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717614"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="30a9b-103">AttackTat In Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="30a9b-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="30a9b-104">**Gäller Microsoft** [Defender för Office 365 abonnemang 2](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="30a9b-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="30a9b-105">Om din organisation har Microsoft Defender för Office 365 abonnemang 2, som omfattar funktioner för hotundersökning och [svar,](office-365-ti.md)kan du använda Attack i Säkerhets- & Efterlevnadscenter för att köra realistiska attackscenarier i organisationen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="30a9b-106">Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din nederkant.</span><span class="sxs-lookup"><span data-stu-id="30a9b-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="30a9b-107">Läs den här artikeln om du vill veta mer.</span><span class="sxs-lookup"><span data-stu-id="30a9b-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="30a9b-108">AttackAnvisningarna som beskrivs i den här artikeln är  nu skrivskyddad och har ersatts av utbildning för attacksimulering i noden **E-post &** samarbete i [Säkerhetscenter för Microsoft 365.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="30a9b-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="30a9b-109">Mer information finns i Komma igång [med att använda attacksimuleringsutbildning.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="30a9b-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="30a9b-110">Möjligheten att starta nya simuleringar från den här versionen av attackattacken har inaktiverats.</span><span class="sxs-lookup"><span data-stu-id="30a9b-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="30a9b-111">Du kan dock fortfarande komma åt rapporter i upp till 90 dagar från den 24 januari 2021.</span><span class="sxs-lookup"><span data-stu-id="30a9b-111">However, you can still access reports for up to 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="30a9b-112">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="30a9b-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="30a9b-113">Gå till <https://protection.office.com/> för att öppna Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="30a9b-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="30a9b-114">Attackattack är tillgänglig vid **hothanteringsattack.** \> </span><span class="sxs-lookup"><span data-stu-id="30a9b-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="30a9b-115">Gå direkt till attack nu, <https://protection.office.com/attacksimulator> öppna.</span><span class="sxs-lookup"><span data-stu-id="30a9b-115">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="30a9b-116">Mer information om tillgängligheten för AttackTrafik för olika Microsoft 365-prenumerationer finns i [tjänstbeskrivningen för Microsoft Defender för Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="30a9b-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="30a9b-117">Du måste vara medlem i rollgrupperna **Organisationshantering** **eller Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="30a9b-118">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="30a9b-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="30a9b-119">Ditt konto måste konfigureras för multifaktorautentisering (MFA) för att skapa och hantera kampanjer i Attack Den här enheten.</span><span class="sxs-lookup"><span data-stu-id="30a9b-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="30a9b-120">Instruktioner finns i Konfigurera [multifaktorautentisering.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="30a9b-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="30a9b-121">Attack Det fungerar bara för molnbaserade postlådor.</span><span class="sxs-lookup"><span data-stu-id="30a9b-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="30a9b-122">Nätfiskekampanjer samlar in och bearbetar händelser i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="30a9b-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="30a9b-123">Historiska kampanjdata är tillgängliga i upp till 90 dagar efter att du startade kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="30a9b-124">Attackattack och utbildningsrelaterade data lagras med andra kunddata för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="30a9b-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="30a9b-125">Mer information finns i [Microsoft 365-dataplatser.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="30a9b-125">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="30a9b-126">Det finns inga Motsvarande PowerShell-cmdlets för Attack Attack Attack.</span><span class="sxs-lookup"><span data-stu-id="30a9b-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="30a9b-127">Nätfiskekampanjer</span><span class="sxs-lookup"><span data-stu-id="30a9b-127">Spear phishing campaigns</span></span>

<span data-ttu-id="30a9b-128">*Nätfiske* är en vanlig term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar komma från legitima eller betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="30a9b-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="30a9b-129">*Nätfiske* är en riktad nätfiskeattack som använder fokuserat och anpassat innehåll som är specifikt anpassat efter de riktade mottagarna (vanligtvis efterkontroll på mottagarna av attacken).</span><span class="sxs-lookup"><span data-stu-id="30a9b-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="30a9b-130">Två olika typer av nätfiskekampanjer är tillgängliga i Attack Det finns två olika typer av nätfiskekampanjer:</span><span class="sxs-lookup"><span data-stu-id="30a9b-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="30a9b-131">**Nätfiske (autentiseringsuppgifter)**: Attacken försöker övertyga mottagarna att klicka på en URL i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="30a9b-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="30a9b-132">Om de klickar på länken uppmanas de att ange sina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="30a9b-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="30a9b-133">I så fall tas de till någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="30a9b-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="30a9b-134">En standardsida som förklarar att det var ett test och ger tips om hur du känner igen nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="30a9b-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Vad användarna ser om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="30a9b-136">En anpassad sida (URL) som du anger.</span><span class="sxs-lookup"><span data-stu-id="30a9b-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="30a9b-137">**Nätfiske (bifogad fil)**: Attacken försöker övertyga mottagarna att öppna en bifogad DOCX- eller .PDF-fil i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="30a9b-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="30a9b-138">Den bifogade filen innehåller samma innehåll från standardlänken för nätfiske, men den första meningen börjar med ", du ser det här meddelandet som ett nyligen öppnat \<Display Name\> e-postmeddelande...".</span><span class="sxs-lookup"><span data-stu-id="30a9b-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="30a9b-139">För närvarande upphör inte nätfiskekampanjer i Attack Det här gäller inte längre.</span><span class="sxs-lookup"><span data-stu-id="30a9b-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="30a9b-140">Skapa en nätfiskekampanj</span><span class="sxs-lookup"><span data-stu-id="30a9b-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="30a9b-141">En viktig del av alla nätfiskekampanjer är utseendet och känslan i e-postmeddelandet som skickas till de riktade mottagarna.</span><span class="sxs-lookup"><span data-stu-id="30a9b-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="30a9b-142">Om du vill skapa och konfigurera e-postmeddelandet har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="30a9b-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="30a9b-143">**Använd en inbyggd e-postmall:** Två inbyggda mallar är tillgängliga: Gåkampanj **och** **löneuppdatering.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="30a9b-144">Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="30a9b-145">**Skapa en återanvändningsbar e-postmall:** När du har skapat och sparat e-postmallen kan du använda den igen i kommande nätfiskekampanjer.</span><span class="sxs-lookup"><span data-stu-id="30a9b-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="30a9b-146">Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="30a9b-147">**Skapa e-postmeddelandet i guiden:** Du kan skapa e-postmeddelandet direkt i guiden när du skapar och startar nätfiskekampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="30a9b-148">Steg 1 (valfritt): Skapa en anpassad e-postmall</span><span class="sxs-lookup"><span data-stu-id="30a9b-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="30a9b-149">Om du ska använda någon av de inbyggda mallarna eller skapa e-postmeddelandet direkt i guiden kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="30a9b-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="30a9b-150">I Säkerhets- & Säkerhets- och efterlevnadscenter går du **till Attack** för \> **hothantering.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="30a9b-151">På sidan **Simulera attacker,** i antingen avsnitten **Nätfiske (autentiseringsinloggning)** eller **Nätfiske (bifogad fil),** klickar du **på Attackinformation.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="30a9b-152">Det spelar ingen roll var du skapar mallen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="30a9b-153">De tillgängliga alternativen i mallen är desamma för båda typerna av nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="30a9b-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="30a9b-154">Klicka på **Ny** mall i  området Skapa mallar  på sidan Attackinformation som öppnas i avsnittet **Nätfiskemallar.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="30a9b-155">Guiden **Konfigurera nätfiskemall** startar i en ny utfällningsguide.</span><span class="sxs-lookup"><span data-stu-id="30a9b-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="30a9b-156">Ange ett unikt visningsnamn för mallen i steget **Start** och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="30a9b-157">I steget **Konfigurera e-postinformation** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="30a9b-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="30a9b-158">**Från (Namn)**: Visningsnamnet som används för meddelandets avsändare.</span><span class="sxs-lookup"><span data-stu-id="30a9b-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="30a9b-159">**Från (E-post)**: Avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="30a9b-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="30a9b-160">**URL till nätfiskeinloggningsserver:** Klicka på listrutan och välj en av de tillgängliga webbadresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="30a9b-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="30a9b-161">Det här är URL-adressen som användarna frestas att klicka på.</span><span class="sxs-lookup"><span data-stu-id="30a9b-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="30a9b-162">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="30a9b-162">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > <span data-ttu-id="30a9b-163">Ett rykte på en URL-tjänst kan identifiera en eller flera av dessa URL:er som osäkra.</span><span class="sxs-lookup"><span data-stu-id="30a9b-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="30a9b-164">Kontrollera om URL:en är tillgänglig i dina webbläsare som stöds innan du använder URL:en i en nätfiskekampanj.</span><span class="sxs-lookup"><span data-stu-id="30a9b-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="30a9b-165">**Anpassad webbadress till startsidan:** Ange en valfri landningssida dit användarna tas om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="30a9b-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="30a9b-166">Den här länken ersätter standardlandningssidan.</span><span class="sxs-lookup"><span data-stu-id="30a9b-166">This link replaces the default landing page.</span></span> <span data-ttu-id="30a9b-167">Om du till exempel har intern informationsutbildning kan du ange url:en här.</span><span class="sxs-lookup"><span data-stu-id="30a9b-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="30a9b-168">**Kategori:** Den här inställningen används inte för närvarande (allt du anger ignoreras).</span><span class="sxs-lookup"><span data-stu-id="30a9b-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="30a9b-169">**Ämne:** **Ämnesfältet** i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="30a9b-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="30a9b-170">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="30a9b-171">Skapa **meddelandetexten i e-postmeddelandet** i steget Skriv e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="30a9b-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="30a9b-172">Du kan använda fliken **E-post** (en RTF-redigerare) eller **fliken** Källa (raw HTML-kod).</span><span class="sxs-lookup"><span data-stu-id="30a9b-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="30a9b-173">HTML-formateringen kan vara så enkel eller komplex som du vill ha den.</span><span class="sxs-lookup"><span data-stu-id="30a9b-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="30a9b-174">Du kan infoga bilder och text för att göra meddelandet bättre i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="30a9b-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="30a9b-175">`${username}` infogar mottagarens namn.</span><span class="sxs-lookup"><span data-stu-id="30a9b-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="30a9b-176">`${loginserverurl}` infogar **URL-adressen för nätfiskeinloggningsservern** från föregående steg.</span><span class="sxs-lookup"><span data-stu-id="30a9b-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="30a9b-177">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="30a9b-178">Klicka på **Slutför** i steget **Bekräfta.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="30a9b-179">Steg 2: Skapa och starta nätfiskekampanjen</span><span class="sxs-lookup"><span data-stu-id="30a9b-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="30a9b-180">I Säkerhets- & Säkerhets- och efterlevnadscenter går du **till Attack** för \> **hothantering.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="30a9b-181">Gör något **av följande** val på sidan Simulera attacker baserat på vilken typ av kampanj du vill skapa:</span><span class="sxs-lookup"><span data-stu-id="30a9b-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="30a9b-182">Klicka på Starta attack eller klicka  på Starta attack med information om nätfiske (autentiseringsuppgifter) **i** avsnittet Om  \> **nätfiske**(autentiseringsstart).</span><span class="sxs-lookup"><span data-stu-id="30a9b-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="30a9b-183">Klicka på Starta attack eller  klicka på Attack **Details** Launch Attack i avsnittet Nätfiske **(bifogad** \> **fil).**</span><span class="sxs-lookup"><span data-stu-id="30a9b-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="30a9b-184">Guiden **Konfigurera nätfiskeattack** startar i en ny utfällning.</span><span class="sxs-lookup"><span data-stu-id="30a9b-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="30a9b-185">Gör något **av** följande i startsteget:</span><span class="sxs-lookup"><span data-stu-id="30a9b-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="30a9b-186">Ange **ett** unikt visningsnamn för kampanjen i rutan Namn.</span><span class="sxs-lookup"><span data-stu-id="30a9b-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="30a9b-187">Klicka inte på **Använd mall** eftersom du skapar e-postmeddelandet senare i guiden.</span><span class="sxs-lookup"><span data-stu-id="30a9b-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="30a9b-188">Klicka **på Använd mall** och välj en inbyggd eller anpassad e-postmall.</span><span class="sxs-lookup"><span data-stu-id="30a9b-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="30a9b-189">När du har valt mallen **fylls** rutan Namn automatiskt i baserat på mallen, men du kan ändra namnet.</span><span class="sxs-lookup"><span data-stu-id="30a9b-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30a9b-190">![Startsida för nätfiske](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="30a9b-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="30a9b-191">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="30a9b-192">Gör något **av följande** i steget Målmottagare:</span><span class="sxs-lookup"><span data-stu-id="30a9b-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="30a9b-193">Klicka **på Adressbok** för att välja mottagare (användare eller grupper) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="30a9b-194">Varje mottagare måste ha en Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="30a9b-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="30a9b-195">Om du klickar **på Filtrera** **och använd** utan att ange sökvillkor returneras alla mottagare och läggs till i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="30a9b-196">Klicka **på** Importera **och sedan på Importera** fil för att importera en fil med kommaavgränsade värden (CSV) eller en radavgränsad fil med e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="30a9b-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="30a9b-197">Varje rad måste innehålla mottagarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="30a9b-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="30a9b-198">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="30a9b-199">I steget **Konfigurera e-postinformation** konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="30a9b-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="30a9b-200">Om du valde en mall i **Start-steget** är de flesta av dessa värden redan konfigurerade, men du kan ändra dem.</span><span class="sxs-lookup"><span data-stu-id="30a9b-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="30a9b-201">**Från (Namn)**: Visningsnamnet som används för meddelandets avsändare.</span><span class="sxs-lookup"><span data-stu-id="30a9b-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="30a9b-202">**Från (E-post)**: Avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="30a9b-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="30a9b-203">Du kan ange en verklig eller falsk e-postadress från organisationens e-postdomän eller ange en verklig eller falsk extern e-postadress.</span><span class="sxs-lookup"><span data-stu-id="30a9b-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="30a9b-204">En giltig avsändares e-postadress från organisationen fungerar faktiskt i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="30a9b-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="30a9b-205">**URL till nätfiskeinloggningsserver:** Klicka på listrutan och välj en av de tillgängliga webbadresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="30a9b-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="30a9b-206">Det här är URL-adressen som användarna frestas att klicka på.</span><span class="sxs-lookup"><span data-stu-id="30a9b-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="30a9b-207">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="30a9b-207">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - <span data-ttu-id="30a9b-208">Alla URL:er är avsiktligt http, inte https.</span><span class="sxs-lookup"><span data-stu-id="30a9b-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="30a9b-209">Ett rykte på en URL-tjänst kan identifiera en eller flera av dessa URL:er som osäkra.</span><span class="sxs-lookup"><span data-stu-id="30a9b-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="30a9b-210">Kontrollera om URL:en är tillgänglig i dina webbläsare som stöds innan du använder URL:en i en nätfiskekampanj.</span><span class="sxs-lookup"><span data-stu-id="30a9b-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="30a9b-211">Du måste välja en URL-adress.</span><span class="sxs-lookup"><span data-stu-id="30a9b-211">You are required to select a URL.</span></span> <span data-ttu-id="30a9b-212">Vid kampanjer mot nätfiske **(bifogad fil)** kan du ta bort länken från brödtexten i  meddelandet i nästa steg (annars innehåller meddelandet både en länk och en bifogad fil).</span><span class="sxs-lookup"><span data-stu-id="30a9b-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="30a9b-213">**Typ av** bifogad fil: Den här inställningen är endast tillgänglig i kampanjer för **nätfiske (bifogad** fil).</span><span class="sxs-lookup"><span data-stu-id="30a9b-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="30a9b-214">Klicka på listrutan och **välj. DOCX** eller **. PDF** från listan.</span><span class="sxs-lookup"><span data-stu-id="30a9b-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="30a9b-215">**Namn på** bifogad fil: Den här inställningen är endast tillgänglig i kampanjer för **nätfiske (bifogad** fil).</span><span class="sxs-lookup"><span data-stu-id="30a9b-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="30a9b-216">Ange ett filnamn för den bifogade filen .docx eller .pdf.</span><span class="sxs-lookup"><span data-stu-id="30a9b-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="30a9b-217">**Anpassad webbadress till startsidan:** Ange en valfri landningssida dit användarna tas om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="30a9b-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="30a9b-218">Den här länken ersätter standardlandningssidan.</span><span class="sxs-lookup"><span data-stu-id="30a9b-218">This link replaces the default landing page.</span></span> <span data-ttu-id="30a9b-219">Om du till exempel har intern informationsutbildning kan du ange url:en här.</span><span class="sxs-lookup"><span data-stu-id="30a9b-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="30a9b-220">**Ämne:** **Ämnesfältet** i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="30a9b-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="30a9b-221">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="30a9b-222">Skapa **meddelandetexten i e-postmeddelandet** i steget Skriv e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="30a9b-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="30a9b-223">Om du valde en mall i **Start-steget** är meddelandetexten redan konfigurerad, men du kan anpassa den.</span><span class="sxs-lookup"><span data-stu-id="30a9b-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="30a9b-224">Du kan använda fliken **E-post** (en RTF-redigerare) eller **fliken** Källa (raw HTML-kod).</span><span class="sxs-lookup"><span data-stu-id="30a9b-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="30a9b-225">HTML-formateringen kan vara så enkel eller komplex som du vill ha den.</span><span class="sxs-lookup"><span data-stu-id="30a9b-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="30a9b-226">Du kan infoga bilder och text för att göra meddelandet bättre i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="30a9b-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="30a9b-227">`${username}` infogar mottagarens namn.</span><span class="sxs-lookup"><span data-stu-id="30a9b-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="30a9b-228">`${loginserverurl}`infogar **URL-värdet för nätfiskeinloggningsservern.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="30a9b-229">Vid kampanjer mot nätfiske **(bifogad fil)** bör du ta bort länken från brödtexten i meddelandet (annars innehåller meddelandet både en länk och en bifogad fil och länkklick spåras inte i en kampanj för bifogade filer). </span><span class="sxs-lookup"><span data-stu-id="30a9b-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="30a9b-230">![Skriv e-posttext](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="30a9b-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="30a9b-231">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="30a9b-232">Klicka på **Slutför** i steget **Bekräfta för** att starta kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="30a9b-233">Nätfiskemeddelandet levereras till de riktade mottagarna.</span><span class="sxs-lookup"><span data-stu-id="30a9b-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="30a9b-234">Lösenordsattackkampanjer</span><span class="sxs-lookup"><span data-stu-id="30a9b-234">Password attack campaigns</span></span>

<span data-ttu-id="30a9b-235">En *lösenordsattack* försöker gissa lösenord för användarkonton i en organisation, vanligtvis efter att attackeraren har identifierat ett eller flera giltiga användarkonton.</span><span class="sxs-lookup"><span data-stu-id="30a9b-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="30a9b-236">I Attack Complex finns det två olika typer av lösenordsattackkampanjer som du kan använda för att testa användarnas lösenords komplexitet:</span><span class="sxs-lookup"><span data-stu-id="30a9b-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="30a9b-237">**Råstyrt** lösenord (ordlisteattack)  : En rå kraft- eller ordlisteattack använder en stor ordlistefil med lösenord för ett användarkonto och hoppas att ett av dem fungerar (många lösenord mot ett konto). </span><span class="sxs-lookup"><span data-stu-id="30a9b-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="30a9b-238">Felaktiga lösenordslåsningar hjälper till att avstyra råstyra lösenordsattacker.</span><span class="sxs-lookup"><span data-stu-id="30a9b-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="30a9b-239">För ordlisteattacken kan du ange ett eller flera lösenord att prova (manuellt anges eller i en uppladdad fil) och du kan ange en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="30a9b-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="30a9b-240">**Lösenordsattack:** En *lösenordsattack* använder samma noggrant övervägde lösenord mot en lista med användarkonton (ett lösenord mot många konton).</span><span class="sxs-lookup"><span data-stu-id="30a9b-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="30a9b-241">Lösenordsattacker är svårare att identifiera än råstyra lösenordsattacker (sannolikheten för att en attack lyckas ökar när en attacker försöker ett lösenord med dussintals eller hundratals konton utan risk för att utlåsa användarens felaktiga lösenord).</span><span class="sxs-lookup"><span data-stu-id="30a9b-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="30a9b-242">För lösenordsattacken kan du bara ange ett lösenord att prova och du kan ange en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="30a9b-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="30a9b-243">Lösenordsattackerna i Attack Pass användarnamn och lösenord Basic begär till en slutpunkt, så de fungerar även med andra autentiseringsmetoder (AD FS, synkronisering av lösenordshashar, direktuppspelning, PingFederate osv.).</span><span class="sxs-lookup"><span data-stu-id="30a9b-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="30a9b-244">För användare som har MFA aktiverat, även om lösenordsattacken försöker med sitt faktiska lösenord, registreras försöket alltid  som ett fel (MFA-användare visas alltså aldrig i antalet lyckade försök för kampanjen).</span><span class="sxs-lookup"><span data-stu-id="30a9b-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="30a9b-245">Det här är det förväntade resultatet.</span><span class="sxs-lookup"><span data-stu-id="30a9b-245">This is the expected result.</span></span> <span data-ttu-id="30a9b-246">MFA är en primär metod för att skydda mot lösenordsattacker.</span><span class="sxs-lookup"><span data-stu-id="30a9b-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="30a9b-247">Skapa och starta en kampanj för lösenordsattack</span><span class="sxs-lookup"><span data-stu-id="30a9b-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="30a9b-248">I Säkerhets- & Säkerhets- och efterlevnadscenter går du **till Attack** för \> **hothantering.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="30a9b-249">Gör något **av följande** val på sidan Simulera attacker baserat på vilken typ av kampanj du vill skapa:</span><span class="sxs-lookup"><span data-stu-id="30a9b-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="30a9b-250">Klicka på Starta attack eller klicka på  Starta attackinformation i avsnittet Råstyrt tvinga lösenord  (Ordlisteattack).  \> </span><span class="sxs-lookup"><span data-stu-id="30a9b-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="30a9b-251">i avsnittet **Lösenordsattack klickar** du på **Starta** attack eller klickar på Starta **attackinformation.** \> </span><span class="sxs-lookup"><span data-stu-id="30a9b-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="30a9b-252">Guiden **Konfigurera lösenordsattack** startar i en ny utfäll kant.</span><span class="sxs-lookup"><span data-stu-id="30a9b-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="30a9b-253">Ange ett **unikt** visningsnamn för kampanjen i steget Start och klicka sedan på **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="30a9b-254">Gör något **av följande** i steget Målanvändare:</span><span class="sxs-lookup"><span data-stu-id="30a9b-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="30a9b-255">Klicka **på Adressbok** för att välja mottagare (användare eller grupper) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="30a9b-256">Varje mottagare måste ha en Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="30a9b-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="30a9b-257">Om du klickar **på Filtrera** **och använd** utan att ange sökvillkor returneras alla mottagare och läggs till i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="30a9b-258">Klicka **på** Importera **och sedan på Importera** fil för att importera en fil med kommaavgränsade värden (CSV) eller en radavgränsad fil med e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="30a9b-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="30a9b-259">Varje rad måste innehålla mottagarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="30a9b-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="30a9b-260">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="30a9b-261">I steget **Välj attackinställningar** väljer du vad du vill göra baserat på kampanjtypen:</span><span class="sxs-lookup"><span data-stu-id="30a9b-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="30a9b-262">**Råstyrt lösenord (ordlisteattack)**: Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="30a9b-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="30a9b-263">**Ange lösenord manuellt:** Skriv ett lösenord **i rutan** Tryck på Retur för att lägga till ett lösenord och tryck sedan på RETUR.</span><span class="sxs-lookup"><span data-stu-id="30a9b-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="30a9b-264">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="30a9b-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="30a9b-265">**Ladda upp lösenord från en ordlistefil:** Klicka på Ladda upp om du vill importera en befintlig textfil som innehåller ett lösenord på varje rad och en tom sista rad. </span><span class="sxs-lookup"><span data-stu-id="30a9b-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="30a9b-266">Textfilen måste vara 10 MB eller mindre och får inte innehålla fler än 3 0000 lösenord.</span><span class="sxs-lookup"><span data-stu-id="30a9b-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="30a9b-267">**Lösenordsattack:** **Ange ett lösenord i** lösenordsrutan som ska användas i attackrutan.</span><span class="sxs-lookup"><span data-stu-id="30a9b-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="30a9b-268">Klicka på Nästa när du är **klar.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="30a9b-269">Klicka på **Slutför** i steget **Bekräfta för** att starta kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="30a9b-270">De angivna lösenorden används av användare som du angett.</span><span class="sxs-lookup"><span data-stu-id="30a9b-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="30a9b-271">Visa kampanjresultat</span><span class="sxs-lookup"><span data-stu-id="30a9b-271">View campaign results</span></span>

<span data-ttu-id="30a9b-272">När du har lanserat en kampanj kan du kontrollera förloppet och resultaten på **huvudsidan För simulera attacker.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="30a9b-273">Aktiva kampanjer visar ett statusfält, ett slutfört procentvärde och antalet "(slutförda användare) (totalt antal användare)".</span><span class="sxs-lookup"><span data-stu-id="30a9b-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="30a9b-274">Om du **klickar på** knappen Uppdatera uppdateras förloppet för alla aktiva kampanjer.</span><span class="sxs-lookup"><span data-stu-id="30a9b-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="30a9b-275">Du kan också klicka på **Avbryt** om du vill stoppa en aktiv kampanj.</span><span class="sxs-lookup"><span data-stu-id="30a9b-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="30a9b-276">När kampanjen är klar har statusen ändras till **Attack.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="30a9b-277">Du kan visa resultatet av kampanjen genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="30a9b-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="30a9b-278">På huvudsidan **För simulera** attacker klickar **du på Visa** rapport under namnet på kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="30a9b-279">På huvudsidan **Simulera attacker** klickar du **på Attackinformation** i avsnittet för typen av attack.</span><span class="sxs-lookup"><span data-stu-id="30a9b-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="30a9b-280">Välj **kampanjen i** avsnittet Attackhistorik på sidan Attackinformation **som** öppnas.</span><span class="sxs-lookup"><span data-stu-id="30a9b-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="30a9b-281">Någon av de föregående åtgärderna tar dig till en sida som heter **Attack details.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="30a9b-282">Informationen som är tillgänglig på den här sidan för varje typ av kampanj beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="30a9b-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="30a9b-283">Kampanjresultat för nätfiske (autentiseringsuppgifter)</span><span class="sxs-lookup"><span data-stu-id="30a9b-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="30a9b-284">Följande information finns på sidan **Attackinformation** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="30a9b-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="30a9b-285">Kampanjens varaktighet (startdatum/tid och slutdatum/tid).</span><span class="sxs-lookup"><span data-stu-id="30a9b-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="30a9b-286">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="30a9b-286">**Total users targeted**</span></span>

- <span data-ttu-id="30a9b-287">**Lyckade försök:** Antalet användare som klickade på länken **och** angav sina autentiseringsuppgifter *(val av* användarnamn och lösenord).</span><span class="sxs-lookup"><span data-stu-id="30a9b-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="30a9b-288">**Övergripande framgångsfrekvens**: En procentandel som beräknas med Lyckades försök **Totalt antal**  /  **användare riktad.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="30a9b-289">**Snabbast klicka:** Hur lång tid det tog den första användaren att klicka på länken efter att du startat kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="30a9b-290">**Genomsnittligt** klick: Summan av hur lång tid det tog att klicka på länken dividerat med antalet användare som klickade på länken.</span><span class="sxs-lookup"><span data-stu-id="30a9b-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="30a9b-291">**Klicka på Framgång:** En procentandel som beräknas utifrån (antalet användare som klickade på länken) **/Totalt antal riktade användare.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="30a9b-292">**Snabbast:** Hur lång tid det tog för den första användaren att ange sina autentiseringsuppgifter efter att du startat kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="30a9b-293">**Genomsnittligt** antal autentiseringsuppgifter: Summan av hur lång tid det tog för alla att ange sina autentiseringsuppgifter dividerat med antalet användare som angav deras autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="30a9b-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="30a9b-294">**Lyckade autentiseringsuppgifter: En** procentandel som beräknas av (antalet användare som angett sina autentiseringsuppgifter) **/Totalt antal riktade användare.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="30a9b-295">Ett stapeldiagram som visar **den länk som klickas** och **de autentiseringsuppgifter som anges** för varje dag.</span><span class="sxs-lookup"><span data-stu-id="30a9b-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="30a9b-296">Ett cirkeldiagram som visar **klickad länk,** de **autentiseringsuppgifter som anges** **och inga** procenttal för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="30a9b-297">I **avsnittet Komprometterade** användare visas information om de användare som klickade på länken:</span><span class="sxs-lookup"><span data-stu-id="30a9b-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="30a9b-298">Användarens e-postadress</span><span class="sxs-lookup"><span data-stu-id="30a9b-298">The user's email address</span></span>

  - <span data-ttu-id="30a9b-299">Datum/tid då de klickade på länken.</span><span class="sxs-lookup"><span data-stu-id="30a9b-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="30a9b-300">Klientens IP-adress.</span><span class="sxs-lookup"><span data-stu-id="30a9b-300">The client IP address.</span></span>

  - <span data-ttu-id="30a9b-301">Information om användarens version av Windows och webbläsare.</span><span class="sxs-lookup"><span data-stu-id="30a9b-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="30a9b-302">Du kan klicka på **Exportera** om du vill exportera resultaten till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="30a9b-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="30a9b-303">Kampanjresultat för nätfiske (bifogad fil)</span><span class="sxs-lookup"><span data-stu-id="30a9b-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="30a9b-304">Följande information finns på sidan **Attackinformation** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="30a9b-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="30a9b-305">Kampanjens varaktighet (startdatum/tid och slutdatum/tid).</span><span class="sxs-lookup"><span data-stu-id="30a9b-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="30a9b-306">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="30a9b-306">**Total users targeted**</span></span>

- <span data-ttu-id="30a9b-307">**Lyckade försök:** Antalet användare som öppnade eller hämtade och öppnade den bifogade filen (förhandsgranskningen räknas inte).</span><span class="sxs-lookup"><span data-stu-id="30a9b-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="30a9b-308">**Övergripande framgångsfrekvens**: En procentandel som beräknas med Lyckades försök **Totalt antal**  /  **användare riktad.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="30a9b-309">**Snabbast öppningstid för** bifogade filer: Hur lång tid det tog den första användaren att öppna den bifogade filen efter att du startade kampanjen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="30a9b-310">**Genomsnittlig öppen tid för bifogade** filer: Summan av hur lång tid det tog att öppna den bifogade filen dividerat med antalet användare som öppnade den bifogade filen.</span><span class="sxs-lookup"><span data-stu-id="30a9b-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="30a9b-311">**Antal användare som öppnat den** bifogade filen som lyckades: En procentandel som beräknas av (antalet användare som öppnade den bifogade filen) **/Totalt antal riktade användare.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="30a9b-312">Kampanjresultat för råstyrt lösenord (ordlisteattack)</span><span class="sxs-lookup"><span data-stu-id="30a9b-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="30a9b-313">Följande information finns på sidan **Attackinformation** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="30a9b-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="30a9b-314">Kampanjens varaktighet (startdatum/tid och slutdatum/tid).</span><span class="sxs-lookup"><span data-stu-id="30a9b-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="30a9b-315">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="30a9b-315">**Total users targeted**</span></span>

- <span data-ttu-id="30a9b-316">**Lyckade försök:** Antalet användare som hittades använda ett av de angivna lösenorden.</span><span class="sxs-lookup"><span data-stu-id="30a9b-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="30a9b-317">**Övergripande framgångsfrekvens**: En procentandel som beräknas med Lyckades försök **Totalt antal**  /  **användare riktad.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="30a9b-318">I **avsnittet Komprometterade** användare visas e-postadresserna till de berörda användarna.</span><span class="sxs-lookup"><span data-stu-id="30a9b-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="30a9b-319">Du kan klicka på **Exportera** om du vill exportera resultaten till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="30a9b-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="30a9b-320">Kampanjresultat för lösenordsattack</span><span class="sxs-lookup"><span data-stu-id="30a9b-320">Password spray attack campaign results</span></span>

<span data-ttu-id="30a9b-321">Följande information finns på sidan **Attackinformation** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="30a9b-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="30a9b-322">Kampanjens varaktighet (startdatum/tid och slutdatum/tid).</span><span class="sxs-lookup"><span data-stu-id="30a9b-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="30a9b-323">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="30a9b-323">**Total users targeted**</span></span>

- <span data-ttu-id="30a9b-324">**Lyckade försök:** Antalet användare som hittades använda det angivna lösenordet.</span><span class="sxs-lookup"><span data-stu-id="30a9b-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="30a9b-325">**Övergripande framgångsfrekvens**: En procentandel som beräknas med Lyckades försök **Totalt antal**  /  **användare riktad.**</span><span class="sxs-lookup"><span data-stu-id="30a9b-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
