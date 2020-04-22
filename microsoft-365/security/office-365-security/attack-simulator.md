---
title: Attack Simulator i ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Som global administratör kan du använda Attack Simulator för att köra realistiska attackscenarier i din organisation. Detta kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack träffar ditt företag.
ms.openlocfilehash: cac09ed48a46531ea2246f9c3ef798649dc73196
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638578"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="81880-104">Attack Simulator i ATP</span><span class="sxs-lookup"><span data-stu-id="81880-104">Attack Simulator in ATP</span></span>

<span data-ttu-id="81880-105">**Sammanfattning** Om du är en global administratör eller en säkerhetsadministratör och din organisation har Office 365 Advanced Threat Protection Plan 2, som innehåller [hotutrednings- och svarsfunktioner,](office-365-ti.md)kan du använda Attack Simulator för att köra realistiska attackscenarier i organisationen.</span><span class="sxs-lookup"><span data-stu-id="81880-105">**Summary** If you are a global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="81880-106">Detta kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din vinst.</span><span class="sxs-lookup"><span data-stu-id="81880-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="81880-107">Läs den här artikeln om du vill veta mer.</span><span class="sxs-lookup"><span data-stu-id="81880-107">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="81880-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="81880-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="81880-109">Öppna säkerhets- & Compliance Center genom <https://protection.office.com/>att gå till .</span><span class="sxs-lookup"><span data-stu-id="81880-109">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="81880-110">Attack simulator finns på **Threat management** \> **Attack simulator**.</span><span class="sxs-lookup"><span data-stu-id="81880-110">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![Hothantering - Attack Simulator](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="81880-112">Mer information om tillgängligheten för Attack Simulator för olika Microsoft 365-prenumerationer finns i [office 365-tjänstbeskrivning för avancerat skydd mot hot](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="81880-112">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="81880-113">Du måste vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="81880-113">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="81880-114">Mer information om rollgrupper i Security & Compliance Center finns [i Behörigheter i Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="81880-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="81880-115">Ditt konto måste konfigureras för MFA (Multi Factor Authentication) för att skapa och hantera kampanjer i Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="81880-115">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="81880-116">Instruktioner finns i [Konfigurera multifaktorautentisering](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="81880-116">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

<span data-ttu-id="81880-117">För att en attack ska kunna startas kontrollerar du att kontot du använder för att köra simulerade attacker använder multifaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="81880-117">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="81880-118">Dessutom måste du vara global administratör eller säkerhetsadministratör.</span><span class="sxs-lookup"><span data-stu-id="81880-118">In addition, you must be a global administrator or a security administrator.</span></span> <span data-ttu-id="81880-119">(Mer information om roller och behörigheter finns [i Behörigheter i Säkerhets- & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="81880-119">(To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

- <span data-ttu-id="81880-120">Nätfiskekampanjer samlar in och behandlar händelser i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="81880-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="81880-121">Historiska kampanjdata kommer att vara tillgängliga i upp till 90 dagar efter att du har startat kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="81880-122">Det finns inga motsvarande PowerShell-cmdlets för Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="81880-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="81880-123">Nätfiskekampanjer för spjut</span><span class="sxs-lookup"><span data-stu-id="81880-123">Spear phishing campaigns</span></span>

<span data-ttu-id="81880-124">*Nätfiske* är en allmän term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar komma från legitima eller betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="81880-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="81880-125">*Spear phishing* är en riktad nätfiskeattack som använder mycket fokuserat och anpassat innehåll som är särskilt anpassat till de riktade mottagarna (vanligtvis efter spaning på mottagarna av angriparen).</span><span class="sxs-lookup"><span data-stu-id="81880-125">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="81880-126">Du är global administratör eller säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="81880-126">You are a global administrator or security administrator</span></span>

<span data-ttu-id="81880-127">I Attack Simulator finns två olika typer av nätfiskekampanjer för spjut:</span><span class="sxs-lookup"><span data-stu-id="81880-127">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="81880-128">[Multifaktorautentisering/villkorlig åtkomst](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) är aktiverat för åtminstone det globala administratörskontot och säkerhetsadministratörerna som ska använda Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="81880-128">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="81880-129">(Helst är multifaktorautentisering/villkorlig åtkomst aktiverad för alla användare i organisationen.)</span><span class="sxs-lookup"><span data-stu-id="81880-129">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

  - <span data-ttu-id="81880-130">En standardsida som förklarar detta var bara ett test och ger tips om hur du känner igen nätfiskemeddelanden.</span><span class="sxs-lookup"><span data-stu-id="81880-130">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Vad användarna ser om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="81880-132">En anpassad sida (URL) som du anger.</span><span class="sxs-lookup"><span data-stu-id="81880-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="81880-133">**Spear phishing (bilaga)**: Attacken försöker övertyga mottagarna att öppna en .docx eller .pdf-bilaga i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="81880-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="81880-134">Den bifogade filen innehåller samma innehåll från standardlänken för\<nätfiske, men den första meningen börjar med "Visningsnamn\>visas det här meddelandet som ett nytt e-postmeddelande som du öppnade...".</span><span class="sxs-lookup"><span data-stu-id="81880-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="81880-135">För närvarande upphör inte spjutfiskekampanjer i Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="81880-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="81880-136">Skapa en nätfiskekampanj för spjut</span><span class="sxs-lookup"><span data-stu-id="81880-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="81880-137">En viktig del av en spjutfiskekampanj är utseendet på det e-postmeddelande som skickas till de riktade mottagarna.</span><span class="sxs-lookup"><span data-stu-id="81880-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="81880-138">Om du vill skapa och konfigurera e-postmeddelandet har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="81880-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="81880-139">**Använd en inbyggd e-postmall:** Två inbyggda mallar finns tillgängliga: **Pris giveaway** och **lön Uppdatering**.</span><span class="sxs-lookup"><span data-stu-id="81880-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="81880-140">Du kan ytterligare anpassa vissa, alla eller ingen av e-postegenskaperna från mallen när du skapar och startar kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="81880-141">**Skapa en återanvändningsbar e-postmall**: När du har skapat och sparat e-postmallen kan du använda den igen i framtida nätfiskekampanjer.</span><span class="sxs-lookup"><span data-stu-id="81880-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="81880-142">Du kan ytterligare anpassa vissa, alla eller ingen av e-postegenskaperna från mallen när du skapar och startar kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="81880-143">**Skapa e-postmeddelandet i guiden**: Du kan skapa e-postmeddelandet direkt i guiden när du skapar och startar nätfiskekampanjen för spjutet.</span><span class="sxs-lookup"><span data-stu-id="81880-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="81880-144">Steg 1 (valfritt): Skapa en anpassad e-postmall</span><span class="sxs-lookup"><span data-stu-id="81880-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="81880-145">Om du ska använda någon av de inbyggda mallarna eller skapa e-postmeddelandet direkt i guiden kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="81880-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="81880-146">Gå till simulator för \> **angreppshantering** **Threat management** för & säkerhet i säkerhetsorganisationscenter .</span><span class="sxs-lookup"><span data-stu-id="81880-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="81880-147">Klicka på **Attackinformation**i avsnitten **Spear Phishing (Credentials Harvest)** eller **Spear Phishing (Attachment)** på sidan **Simulera attacker.**</span><span class="sxs-lookup"><span data-stu-id="81880-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="81880-148">Det spelar ingen roll var du skapar mallen.</span><span class="sxs-lookup"><span data-stu-id="81880-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="81880-149">De tillgängliga alternativen i mallen är desamma för båda typerna av nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="81880-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="81880-150">Klicka på **Ny mall**i avsnittet Skapa mallar i avsnittet **Skapa mallar** på sidan **Attackinformation** som öppnas. **Create Templates**</span><span class="sxs-lookup"><span data-stu-id="81880-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="81880-151">Guiden **Konfigurera nätfiskemall** börjar i ett nytt utfällbart utfällbart.</span><span class="sxs-lookup"><span data-stu-id="81880-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="81880-152">I steget **Start** anger du ett unikt visningsnamn för mallen och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81880-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="81880-153">Konfigurera följande inställningar i steget **Konfigurera e-postinformation:**</span><span class="sxs-lookup"><span data-stu-id="81880-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="81880-154">**Från (Namn)**: Visningsnamnet som används för meddelandeavsändaren.</span><span class="sxs-lookup"><span data-stu-id="81880-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="81880-155">**Från (E-post)**: Avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="81880-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="81880-156">**Url till nätloggningsserver:** Klicka på listrutan och välj en av de tillgängliga webbadresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="81880-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="81880-157">Detta är webbadressen som användarna kommer att frestas att klicka.</span><span class="sxs-lookup"><span data-stu-id="81880-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="81880-158">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="81880-158">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="81880-159">Alla webbadresser är avsiktligt http, inte https.</span><span class="sxs-lookup"><span data-stu-id="81880-159">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="81880-160">En URL-ryktestjänst kan identifiera en eller flera av dessa webbadresser som osäkra.</span><span class="sxs-lookup"><span data-stu-id="81880-160">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="81880-161">Kontrollera tillgängligheten för webbadressen i webbläsare som stöds innan du använder webbadressen i en nätfiskekampanj.</span><span class="sxs-lookup"><span data-stu-id="81880-161">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="81880-162">**Url till anpassad målsida**: Ange en valfri målsida där användarna tas om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="81880-162">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="81880-163">Den här länken ersätter standardmålsidan.</span><span class="sxs-lookup"><span data-stu-id="81880-163">This link replaces the default landing page.</span></span> <span data-ttu-id="81880-164">Om du till exempel har intern medvetenhetsutbildning kan du ange webbadressen här.</span><span class="sxs-lookup"><span data-stu-id="81880-164">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="81880-165">**Kategori**: För närvarande används inte den här inställningen (allt du anger ignoreras).</span><span class="sxs-lookup"><span data-stu-id="81880-165">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="81880-166">**Ämne**: **Fältet Ämne** i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="81880-166">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="81880-167">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81880-167">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="81880-168">Skapa meddelandetexten för e-postmeddelandet i steget **Skriv e-post.**</span><span class="sxs-lookup"><span data-stu-id="81880-168">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="81880-169">Du kan använda fliken **E-post** (en rtf-redigerare) eller fliken **Källa** (rå HTML-kod).</span><span class="sxs-lookup"><span data-stu-id="81880-169">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="81880-170">HTML-formateringen kan vara så enkel eller komplex som du behöver den för att vara.</span><span class="sxs-lookup"><span data-stu-id="81880-170">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="81880-171">Du kan infoga bilder och text för att förbättra meddelandets trovärdighet i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="81880-171">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="81880-172">`${username}`infogar mottagarens namn.</span><span class="sxs-lookup"><span data-stu-id="81880-172">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="81880-173">`${loginserverurl}`**Url-värdet för nätfiske inloggningsservern** infogas från föregående steg.</span><span class="sxs-lookup"><span data-stu-id="81880-173">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="81880-174">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81880-174">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="81880-175">Klicka på **Slutför**i steget **Bekräfta.**</span><span class="sxs-lookup"><span data-stu-id="81880-175">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="81880-176">Steg 2: Skapa och starta nätfiskekampanjen för spjut</span><span class="sxs-lookup"><span data-stu-id="81880-176">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="81880-177">Gå till simulator för \> **angreppshantering** **Threat management** för & säkerhet i säkerhetsorganisationscenter .</span><span class="sxs-lookup"><span data-stu-id="81880-177">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="81880-178">På sidan **Simulera attacker** gör du något av följande val baserat på vilken typ av kampanj du vill skapa:</span><span class="sxs-lookup"><span data-stu-id="81880-178">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="81880-179">Klicka på **Starta attack** i avsnittet **Spear Phishing (Credentials Harvest)** eller klicka på **Attackinformation** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="81880-179">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="81880-180">Klicka på **Attack Details** \> **Launch Attack** **Starta attack** i avsnittet **Spear Phishing (Attachment).**</span><span class="sxs-lookup"><span data-stu-id="81880-180">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="81880-181">Guiden **Konfigurera nätfiskeattack** startar i ett nytt utfällbart utfällbart.</span><span class="sxs-lookup"><span data-stu-id="81880-181">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="81880-182">Gör **Start** något av följande i startsteget:</span><span class="sxs-lookup"><span data-stu-id="81880-182">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="81880-183">Ange ett unikt visningsnamn för kampanjen i rutan **Namn.**</span><span class="sxs-lookup"><span data-stu-id="81880-183">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="81880-184">Klicka inte på **Använd mall**eftersom du skapar e-postmeddelandet senare i guiden.</span><span class="sxs-lookup"><span data-stu-id="81880-184">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="81880-185">Klicka på **Använd mall** och välj en inbyggd eller anpassad e-postmall.</span><span class="sxs-lookup"><span data-stu-id="81880-185">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="81880-186">När du har valt mallen fylls rutan **Namn** automatiskt baserat på mallen, men du kan ändra namnet.</span><span class="sxs-lookup"><span data-stu-id="81880-186">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Startsida för nätfiske](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="81880-188">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81880-188">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="81880-189">Gör något av följande i steget **Målmottagare:**</span><span class="sxs-lookup"><span data-stu-id="81880-189">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="81880-190">Klicka på **Adressbok** om du vill välja mottagare (användare eller grupper) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-190">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="81880-191">Varje riktad mottagare måste ha en Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="81880-191">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="81880-192">Om du klickar på **Filtrera** och **tillämpa** utan att ange några sökvillkor returneras alla mottagare och läggs till i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-192">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="81880-193">Klicka på **Importera** och sedan **Filimport** om du vill importera ett kommaavgränsat värde (CSV) eller radavgränsad fil med e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="81880-193">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="81880-194">Varje rad måste innehålla mottagarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="81880-194">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="81880-195">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81880-195">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="81880-196">Konfigurera följande inställningar i steget **Konfigurera e-postinformation:**</span><span class="sxs-lookup"><span data-stu-id="81880-196">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="81880-197">Om du har valt en mall i **startsteget** är de flesta av dessa värden redan konfigurerade, men du kan ändra dem.</span><span class="sxs-lookup"><span data-stu-id="81880-197">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="81880-198">**Från (Namn)**: Visningsnamnet som används för meddelandeavsändaren.</span><span class="sxs-lookup"><span data-stu-id="81880-198">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="81880-199">**Från (E-post)**: Avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="81880-199">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="81880-200">Du kan ange en verklig eller falsk e-postadress från organisationens e-postdomän, eller så kan du ange en verklig eller falsk extern e-postadress.</span><span class="sxs-lookup"><span data-stu-id="81880-200">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="81880-201">En giltig e-postadress för avsändaren från organisationen kommer faktiskt att matchas i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="81880-201">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="81880-202">**Url till nätloggningsserver:** Klicka på listrutan och välj en av de tillgängliga webbadresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="81880-202">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="81880-203">Detta är webbadressen som användarna kommer att frestas att klicka.</span><span class="sxs-lookup"><span data-stu-id="81880-203">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="81880-204">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="81880-204">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="81880-205">Alla webbadresser är avsiktligt http, inte https.</span><span class="sxs-lookup"><span data-stu-id="81880-205">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="81880-206">En URL-ryktestjänst kan identifiera en eller flera av dessa webbadresser som osäkra.</span><span class="sxs-lookup"><span data-stu-id="81880-206">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="81880-207">Kontrollera tillgängligheten för webbadressen i webbläsare som stöds innan du använder webbadressen i en nätfiskekampanj.</span><span class="sxs-lookup"><span data-stu-id="81880-207">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="81880-208">Du måste välja en webbadress.</span><span class="sxs-lookup"><span data-stu-id="81880-208">You are required to select a URL.</span></span> <span data-ttu-id="81880-209">För kampanjer <b>med spearfiske (bifogad fil)</b> kan du ta bort länken från meddelandets brödtext i nästa steg (annars innehåller meddelandet både en länk <b>och</b> en bifogad fil).</span><span class="sxs-lookup"><span data-stu-id="81880-209">For <b>Spear Phishing (Attachment)</b> campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link <b>and</b> an attachment).</span></span></li></ul>

   - <span data-ttu-id="81880-210">**Typ av bifogade filer**: Den här inställningen är endast tillgänglig i **spearfiskekampanjer (bifogad fil).**</span><span class="sxs-lookup"><span data-stu-id="81880-210">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="81880-211">Klicka på listrutan och välj **. DOCX** eller **. PDF** från listan.</span><span class="sxs-lookup"><span data-stu-id="81880-211">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="81880-212">**Namn på bifogade filer**: Den här inställningen är endast tillgänglig i **spearfiskekampanjer (bifogad fil).**</span><span class="sxs-lookup"><span data-stu-id="81880-212">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="81880-213">Ange ett filnamn för bifogad fil i .docx eller .pdf.</span><span class="sxs-lookup"><span data-stu-id="81880-213">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="81880-214">**Url till anpassad målsida**: Ange en valfri målsida där användarna tas om de klickar på nätfiskelänken och anger sina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="81880-214">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="81880-215">Den här länken ersätter standardmålsidan.</span><span class="sxs-lookup"><span data-stu-id="81880-215">This link replaces the default landing page.</span></span> <span data-ttu-id="81880-216">Om du till exempel har intern medvetenhetsutbildning kan du ange webbadressen här.</span><span class="sxs-lookup"><span data-stu-id="81880-216">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="81880-217">**Ämne**: **Fältet Ämne** i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="81880-217">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="81880-218">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81880-218">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="81880-219">Skapa meddelandetexten för e-postmeddelandet i steget **Skriv e-post.**</span><span class="sxs-lookup"><span data-stu-id="81880-219">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="81880-220">Om du har valt en mall i **startsteget** är meddelandetexten redan konfigurerad, men du kan anpassa den.</span><span class="sxs-lookup"><span data-stu-id="81880-220">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="81880-221">Du kan använda fliken **E-post** (en rtf-redigerare) eller fliken **Källa** (rå HTML-kod).</span><span class="sxs-lookup"><span data-stu-id="81880-221">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="81880-222">HTML-formateringen kan vara så enkel eller komplex som du behöver den för att vara.</span><span class="sxs-lookup"><span data-stu-id="81880-222">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="81880-223">Du kan infoga bilder och text för att förbättra meddelandets trovärdighet i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="81880-223">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="81880-224">`${username}`infogar mottagarens namn.</span><span class="sxs-lookup"><span data-stu-id="81880-224">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="81880-225">`${loginserverurl}`Url-värdet för **nätfiske inloggningsservern** infogas.</span><span class="sxs-lookup"><span data-stu-id="81880-225">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="81880-226">För kampanjer **med nätfiske (bifogad fil)** bör du ta bort länken från meddelandets brödtext (annars innehåller meddelandet både en länk **och** en bifogad fil och länkklick spåras inte i en kampanj för bifogade filer).</span><span class="sxs-lookup"><span data-stu-id="81880-226">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Skriv e-postkropp](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="81880-228">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81880-228">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="81880-229">Klicka på **Slutför** i steget **Bekräfta** för att starta kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-229">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="81880-230">Nätfiskemeddelandet levereras till de riktade mottagarna.</span><span class="sxs-lookup"><span data-stu-id="81880-230">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="81880-231">Kampanjer för lösenordsattacker</span><span class="sxs-lookup"><span data-stu-id="81880-231">Password attack campaigns</span></span>

<span data-ttu-id="81880-232">En *lösenordsattack* försöker gissa lösenord för användarkonton i en organisation, vanligtvis efter att angriparen har identifierat ett eller flera giltiga användarkonton.</span><span class="sxs-lookup"><span data-stu-id="81880-232">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="81880-233">I Attack Simulator är två olika typer av lösenordsattackkampanjer tillgängliga för dig att testa komplexiteten i användarnas lösenord:</span><span class="sxs-lookup"><span data-stu-id="81880-233">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="81880-234">**Brute force lösenord (ordbok attack)**: En *brute force* eller *ordbok* attack använder en stor ordbok fil av lösenord på ett användarkonto med hopp om att en av dem kommer att fungera (många lösenord mot ett konto).</span><span class="sxs-lookup"><span data-stu-id="81880-234">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="81880-235">Felaktiga lösenordsspärrar hjälper till att avskräcka attacker mot brute force-lösenord.</span><span class="sxs-lookup"><span data-stu-id="81880-235">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="81880-236">För ordlisteattacken kan du ange ett eller flera lösenord som ska provas (manuellt inmatat eller i en uppladdad fil) och du kan ange en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="81880-236">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="81880-237">**Lösenord spray attack:** Ett *lösenord spray* attack använder samma noggrant genomtänkta lösenord mot en lista över användarkonton (ett lösenord mot många konton).</span><span class="sxs-lookup"><span data-stu-id="81880-237">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="81880-238">Lösenord spray attacker är svårare att upptäcka än brute force lösenord attacker (sannolikheten för framgång ökar när en angripare försöker ett lösenord över dussintals eller hundratals konton utan risk för att snubbla användarens felaktiga lösenord lock-out).</span><span class="sxs-lookup"><span data-stu-id="81880-238">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="81880-239">För lösenordssprayattacken kan du bara ange ett lösenord att prova, och du kan ange en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="81880-239">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="81880-240">Lösenordsattackerna i Attack Simulator skickar användarnamn och lösenord Grundläggande auth-begäranden till en slutpunkt, så de fungerar också med andra autentiseringsmetoder (AD FS, lösenordshösksynkronisering, vidaregång, PingFederate, etc.).</span><span class="sxs-lookup"><span data-stu-id="81880-240">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="81880-241">För användare som har MFA aktiverat, även om **lösenordsattacken** försöker sitt faktiska lösenord, kommer försöket alltid att registrera sig som ett fel (med andra ord kommer MFA-användare aldrig att visas i antalet lyckade försök för kampanjen).</span><span class="sxs-lookup"><span data-stu-id="81880-241">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="81880-242">Detta är det förväntade resultatet.</span><span class="sxs-lookup"><span data-stu-id="81880-242">This is the expected result.</span></span> <span data-ttu-id="81880-243">MFA är en primär metod för att skydda mot lösenordsattacker.</span><span class="sxs-lookup"><span data-stu-id="81880-243">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="81880-244">Skapa och starta en kampanj för lösenordsattack</span><span class="sxs-lookup"><span data-stu-id="81880-244">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="81880-245">Gå till simulator för \> **angreppshantering** **Threat management** för & säkerhet i säkerhetsorganisationscenter .</span><span class="sxs-lookup"><span data-stu-id="81880-245">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="81880-246">På sidan **Simulera attacker** gör du något av följande val baserat på vilken typ av kampanj du vill skapa:</span><span class="sxs-lookup"><span data-stu-id="81880-246">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="81880-247">Klicka på **Starta attack** i avsnittet Brute Force **Password (Dictionary Attack)** eller klicka på **Attackinformation** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="81880-247">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="81880-248">I avsnittet **Lösenord spray attack,** klicka **på Starta attack** eller klicka på Attack **Detaljer** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="81880-248">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="81880-249">Guiden **Konfigurera lösenordsattack** startar i ett nytt utfällbart alternativ.</span><span class="sxs-lookup"><span data-stu-id="81880-249">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="81880-250">I steget **Start** anger du ett unikt visningsnamn för kampanjen och klickar sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81880-250">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="81880-251">Gör något av följande i steget **Rikta användare:**</span><span class="sxs-lookup"><span data-stu-id="81880-251">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="81880-252">Klicka på **Adressbok** om du vill välja mottagare (användare eller grupper) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-252">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="81880-253">Varje riktad mottagare måste ha en Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="81880-253">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="81880-254">Om du klickar på **Filtrera** och **tillämpa** utan att ange några sökvillkor returneras alla mottagare och läggs till i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-254">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="81880-255">Klicka på **Importera** och sedan **Filimport** om du vill importera ett kommaavgränsat värde (CSV) eller radavgränsad fil med e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="81880-255">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="81880-256">Varje rad måste innehålla mottagarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="81880-256">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="81880-257">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81880-257">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="81880-258">I steget **Välj attackinställningar** väljer du vad du ska göra baserat på kampanjtypen:</span><span class="sxs-lookup"><span data-stu-id="81880-258">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="81880-259">**Brute Force Password (Dictionary Attack)**: Gör något av följande steg:</span><span class="sxs-lookup"><span data-stu-id="81880-259">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="81880-260">**Ange lösenord manuellt**: Skriv ett lösenord i rutan **Tryck på retur för att lägga till ett lösenord** och tryck sedan på RETUR.</span><span class="sxs-lookup"><span data-stu-id="81880-260">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="81880-261">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="81880-261">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="81880-262">**Ladda upp lösenord från en ordlistefil:** Klicka på **Ladda upp** om du vill importera en befintlig textfil som innehåller ett lösenord på varje rad och en tom sista rad.</span><span class="sxs-lookup"><span data-stu-id="81880-262">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="81880-263">Textfilen måste vara 10 MB eller mindre stor och får inte innehålla fler än 3 0000 lösenord.</span><span class="sxs-lookup"><span data-stu-id="81880-263">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="81880-264">**Lösenord spray attack:** I **det lösenord (er) att använda i attackrutan,** ange ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="81880-264">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="81880-265">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="81880-265">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="81880-266">Klicka på **Slutför** i steget **Bekräfta** för att starta kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-266">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="81880-267">De angivna lösenorden provas på användare som du har angett.</span><span class="sxs-lookup"><span data-stu-id="81880-267">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="81880-268">Visa kampanjresultat</span><span class="sxs-lookup"><span data-stu-id="81880-268">View campaign results</span></span>

<span data-ttu-id="81880-269">När du har startat en kampanj kan du kontrollera förloppet och resultaten på huvudsidan **för simulera attacker.**</span><span class="sxs-lookup"><span data-stu-id="81880-269">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="81880-270">Aktiva kampanjer visar ett statusfält, ett slutfört procentvärde och antalet "(slutförda användare) (totalt antal användare).Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span><span class="sxs-lookup"><span data-stu-id="81880-270">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="81880-271">Om du klickar på knappen **Uppdatera** uppdatera uppdateras förloppet för alla aktiva kampanjer.</span><span class="sxs-lookup"><span data-stu-id="81880-271">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="81880-272">Du kan också klicka på **Avsluta** för att stoppa en aktiv kampanj.</span><span class="sxs-lookup"><span data-stu-id="81880-272">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="81880-273">När kampanjen är klar ändras statusen till **Attack slutförd**.</span><span class="sxs-lookup"><span data-stu-id="81880-273">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="81880-274">Du kan visa resultatet av kampanjen genom att utföra någon av följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="81880-274">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="81880-275">Klicka på **Visa rapport** under namnet på kampanjen på sidan **Simulera attacker.**</span><span class="sxs-lookup"><span data-stu-id="81880-275">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="81880-276">På sidan Simulera **attacker** för huvudformat klickar du på **Attackinformation** i avsnittet för typen av attack.</span><span class="sxs-lookup"><span data-stu-id="81880-276">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="81880-277">På sidan **Attackinformation** som öppnas väljer du kampanjen i avsnittet **Attackhistorik.**</span><span class="sxs-lookup"><span data-stu-id="81880-277">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="81880-278">Någon av de tidigare åtgärderna tar dig till en sida med namnet **Attackinformation**.</span><span class="sxs-lookup"><span data-stu-id="81880-278">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="81880-279">Den information som är tillgänglig på den här sidan för varje typ av kampanj beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="81880-279">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="81880-280">Kampanjresultat för Spear Phishing (Credentials Harvest)</span><span class="sxs-lookup"><span data-stu-id="81880-280">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="81880-281">Följande information finns på sidan **Attackinformation** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="81880-281">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="81880-282">Kampanjens varaktighet (startdatum/startdatum och slutdatum/sluttid).</span><span class="sxs-lookup"><span data-stu-id="81880-282">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="81880-283">**Totalt antal användare riktade**</span><span class="sxs-lookup"><span data-stu-id="81880-283">**Total users targeted**</span></span>

- <span data-ttu-id="81880-284">**Lyckade försök**: Antalet användare som klickade på länken **och** angav sina autentiseringsuppgifter *(alla* användarnamn och lösenordsvärde).</span><span class="sxs-lookup"><span data-stu-id="81880-284">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="81880-285">**Total framgång:** En procentsats som beräknas av **Lyckade försök** / **Totalt antal användare som är inriktade på**.</span><span class="sxs-lookup"><span data-stu-id="81880-285">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="81880-286">**Snabbaste klick:** Hur lång tid det tog den första användaren att klicka på länken efter att du startat kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-286">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="81880-287">**Genomsnittligt klick:** Summan av hur lång tid det tog för alla att klicka på länken dividerat med antalet användare som klickade på länken.</span><span class="sxs-lookup"><span data-stu-id="81880-287">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="81880-288">**Klicka på Framgång:** En procentsats som beräknas av (antal användare som klickade på länken) / **Totalt antal användare riktade**.</span><span class="sxs-lookup"><span data-stu-id="81880-288">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="81880-289">**Snabbaste autentiseringsuppgifter:** Hur lång tid det tog för den första användaren att ange sina autentiseringsuppgifter efter att du startat kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-289">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="81880-290">**Genomsnittlig autentiseringsuppgifter:** Summan av hur lång tid det tog för alla att ange sina autentiseringsuppgifter dividerat med antalet användare som angett sina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="81880-290">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="81880-291">**Autentiseringsuppgifter Framgång:** En procentsats som beräknas av (antal användare som angett sina autentiseringsuppgifter) / **Totalt antal användare riktade**.</span><span class="sxs-lookup"><span data-stu-id="81880-291">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="81880-292">Ett stapeldiagram som visar **länken klickade** på och **Autentiseringsuppgifter som anges** nummer per dag.</span><span class="sxs-lookup"><span data-stu-id="81880-292">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="81880-293">Ett cirkeldiagram som visar **länken klickade på**, **Autentiseringsuppgifter som angetts**och **Inga** procentsatser för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-293">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="81880-294">Avsnittet **Komprometterade användare** visar information om de användare som klickade på länken:</span><span class="sxs-lookup"><span data-stu-id="81880-294">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="81880-295">Användarens e-postadress</span><span class="sxs-lookup"><span data-stu-id="81880-295">The user's email address</span></span>

  - <span data-ttu-id="81880-296">Datum/tid då de klickade på länken.</span><span class="sxs-lookup"><span data-stu-id="81880-296">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="81880-297">Klientens IP-adress.</span><span class="sxs-lookup"><span data-stu-id="81880-297">The client IP address.</span></span>

  - <span data-ttu-id="81880-298">Information om användarens version av Windows och webbläsare.</span><span class="sxs-lookup"><span data-stu-id="81880-298">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="81880-299">Du kan klicka på **Exportera** om du vill exportera resultaten till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="81880-299">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="81880-300">Kampanjresultat för Spear Phishing (Attachment)</span><span class="sxs-lookup"><span data-stu-id="81880-300">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="81880-301">Följande information finns på sidan **Attackinformation** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="81880-301">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="81880-302">Kampanjens varaktighet (startdatum/startdatum och slutdatum/sluttid).</span><span class="sxs-lookup"><span data-stu-id="81880-302">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="81880-303">**Totalt antal användare riktade**</span><span class="sxs-lookup"><span data-stu-id="81880-303">**Total users targeted**</span></span>

- <span data-ttu-id="81880-304">**Lyckade försök**: Antalet användare som öppnade eller hämtade och öppnade den bifogade filen (förhandsgranskning räknas inte).</span><span class="sxs-lookup"><span data-stu-id="81880-304">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="81880-305">**Total framgång:** En procentsats som beräknas av **Lyckade försök** / **Totalt antal användare som är inriktade på**.</span><span class="sxs-lookup"><span data-stu-id="81880-305">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="81880-306">**Snabbaste öppen tid för bifogade filer**: Hur lång tid det tog för den första användaren att öppna den bifogade filen när du startade kampanjen.</span><span class="sxs-lookup"><span data-stu-id="81880-306">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="81880-307">**Genomsnittlig öppen tid för bifogade filer**: Summan av hur lång tid det tog för alla att öppna den bifogade filen dividerat med antalet användare som öppnade bilagan.</span><span class="sxs-lookup"><span data-stu-id="81880-307">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="81880-308">**Bifogad fil öppen framgång:** En procentsats som beräknas av (antal användare som öppnade bilagan) / **Totalt antal användare riktade**.</span><span class="sxs-lookup"><span data-stu-id="81880-308">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="81880-309">Kampanjresultat för Brute Force Password (Dictionary Attack)</span><span class="sxs-lookup"><span data-stu-id="81880-309">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="81880-310">Följande information finns på sidan **Attackinformation** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="81880-310">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="81880-311">Kampanjens varaktighet (startdatum/startdatum och slutdatum/sluttid).</span><span class="sxs-lookup"><span data-stu-id="81880-311">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="81880-312">**Totalt antal användare riktade**</span><span class="sxs-lookup"><span data-stu-id="81880-312">**Total users targeted**</span></span>

- <span data-ttu-id="81880-313">**Lyckade försök**: Antalet användare som visade sig använda ett av de angivna lösenorden.</span><span class="sxs-lookup"><span data-stu-id="81880-313">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="81880-314">**Total framgång:** En procentsats som beräknas av **Lyckade försök** / **Totalt antal användare som är inriktade på**.</span><span class="sxs-lookup"><span data-stu-id="81880-314">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="81880-315">I avsnittet **Komprometterade användare** visas de berörda användarnas e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="81880-315">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="81880-316">Du kan klicka på **Exportera** om du vill exportera resultaten till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="81880-316">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="81880-317">Kampanjresultat för lösenordssprayattack</span><span class="sxs-lookup"><span data-stu-id="81880-317">Password spray attack campaign results</span></span>

<span data-ttu-id="81880-318">Följande information finns på sidan **Attackinformation** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="81880-318">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="81880-319">Kampanjens varaktighet (startdatum/startdatum och slutdatum/sluttid).</span><span class="sxs-lookup"><span data-stu-id="81880-319">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="81880-320">**Totalt antal användare riktade**</span><span class="sxs-lookup"><span data-stu-id="81880-320">**Total users targeted**</span></span>

- <span data-ttu-id="81880-321">**Lyckade försök**: Antalet användare som visade sig använda det angivna lösenordet.</span><span class="sxs-lookup"><span data-stu-id="81880-321">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="81880-322">**Total framgång:** En procentsats som beräknas av **Lyckade försök** / **Totalt antal användare som är inriktade på**.</span><span class="sxs-lookup"><span data-stu-id="81880-322">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
