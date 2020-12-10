---
title: Angrepps Simulator i Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig att använda en angrepps Simulator för att köra simulerade nät för nätfiske och lösen ord i Microsoft 365 E5-eller Microsoft Defender för Office 365 plan 2-organisationer.
ms.openlocfilehash: b1c2ad265c4812f67aee66f0f59664480b4db229
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615210"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="54887-103">Angrepps Simulator i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="54887-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="54887-104">Om din organisation har Microsoft Defender för Office 365 abonnemang 2, som innehåller [hot undersökningar och svars funktioner](office-365-ti.md), kan du använda angrepps simulatorn i säkerhets & Compliance Center för att köra realistiska angrepp i din organisation.</span><span class="sxs-lookup"><span data-stu-id="54887-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="54887-105">Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din botten linje.</span><span class="sxs-lookup"><span data-stu-id="54887-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="54887-106">Läs den här artikeln om du vill veta mer.</span><span class="sxs-lookup"><span data-stu-id="54887-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="54887-107">Information om attack simulering och utbildning relaterade data lagras med andra kunddata för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="54887-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="54887-108">Mer information finns i [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span><span class="sxs-lookup"><span data-stu-id="54887-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

> [!TIP]
> <span data-ttu-id="54887-109">Utbildning för attack simulering är tillgängligt för offentlig för hands version i Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="54887-109">Attack simulation training is available for public preview in the Microsoft 365 security center.</span></span> <span data-ttu-id="54887-110">Ta en titt på [simulera ett nät fiske angrepp med Microsoft Defender för Office 365](attack-simulation-training.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="54887-110">Check out [Simulate a phishing attack with Microsoft Defender for Office 365](attack-simulation-training.md) to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="54887-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="54887-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="54887-112">Gå till <https://protection.office.com/> för att öppna Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="54887-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="54887-113">Angrepps simulatorn  finns i \> **angrepps** hanterings tjänsten.</span><span class="sxs-lookup"><span data-stu-id="54887-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="54887-114">Gå direkt till angrepps simulatorn, öppen <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="54887-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="54887-115">Mer information om tillgängligheten för angrepps enheter för olika Microsoft 365-prenumerationer finns i [Beskrivning av Microsoft Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="54887-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="54887-116">Du måste vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .</span><span class="sxs-lookup"><span data-stu-id="54887-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="54887-117">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="54887-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="54887-118">Ditt konto måste konfigureras för multifaktorautentisering (MFA) för att skapa och hantera kampanjer i angrepps Simulator.</span><span class="sxs-lookup"><span data-stu-id="54887-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="54887-119">Anvisningar finns i [Konfigurera multifaktorautentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="54887-119">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="54887-120">Nät fiske kampanjer samlar in och bearbetar händelser i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="54887-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="54887-121">Historiska kampanj data kommer att vara tillgängliga i upp till 90 dagar efter att du har lanserat kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="54887-122">Det finns inga motsvarande PowerShell-cmdlets för angrepps Simulator.</span><span class="sxs-lookup"><span data-stu-id="54887-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="54887-123">Spear nät fiske kampanjer</span><span class="sxs-lookup"><span data-stu-id="54887-123">Spear phishing campaigns</span></span>

<span data-ttu-id="54887-124">*Nätfiske* är en generisk term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="54887-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="54887-125">*Spear nätfiske* är ett riktat nätfiske-angrepp som använder prioriterat och anpassat innehåll som är specifikt skräddarsydda för de riktade mottagarna (vanligt vis efter Reconnaissance på mottagarna).</span><span class="sxs-lookup"><span data-stu-id="54887-125">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="54887-126">I angrepps simulatorer är två olika typer av Spear nät fiske kampanjer tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="54887-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="54887-127">**Spear nätfiske (uppgifter om skörd)**: ett försök görs att få mottagarna att klicka på en URL i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="54887-127">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="54887-128">Om de klickar på länken uppmanas de att ange sina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="54887-128">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="54887-129">Om de gör det tas de till någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="54887-129">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="54887-130">En standard sida som förklarar att detta var ett test och ger tips för att känna igen nät fiske meddelanden.</span><span class="sxs-lookup"><span data-stu-id="54887-130">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Vad användarna ser om de klickar på nätfiske-länken och anger deras autentiseringsuppgifter](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="54887-132">En anpassad sida (URL) som du anger.</span><span class="sxs-lookup"><span data-stu-id="54887-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="54887-133">**Spear nätfiske (bifogad fil)**: med angreppet försöker mottagarna att öppna en. docx-eller. pdf-bilaga i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="54887-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="54887-134">Den bifogade filen innehåller samma innehåll från den vanliga nät fiske länken, men den första meningen börjar med " \<Display Name\> , du ser det här meddelandet som ett nyligen öppnade e-postmeddelande...".</span><span class="sxs-lookup"><span data-stu-id="54887-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="54887-135">För närvarande upphör Spear nät fiske kampanjer inte att gälla.</span><span class="sxs-lookup"><span data-stu-id="54887-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="54887-136">Skapa en Spear nätfiske-kampanj</span><span class="sxs-lookup"><span data-stu-id="54887-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="54887-137">En viktig del av alla Spear nät fiske kampanjer är utseendet och känslan hos det e-postmeddelande som skickas till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="54887-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="54887-138">För att skapa och konfigurera e-postmeddelandet har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="54887-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="54887-139">**Använda en inbyggd e-postmall**: två inbyggda mallar är tillgängliga: **pris gåvo kampanjen** och **löne uppdatering**.</span><span class="sxs-lookup"><span data-stu-id="54887-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="54887-140">Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="54887-141">**Skapa en återanvändbar e-postmall**: när du har skapat och sparat e-postmallen kan du använda den igen i framtida Spear nät fiske kampanjer.</span><span class="sxs-lookup"><span data-stu-id="54887-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="54887-142">Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="54887-143">**Skapa e-postmeddelandet i guiden**: du kan skapa e-postmeddelandet direkt i guiden när du skapar och startar Spear phishing-kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="54887-144">Steg 1 (valfritt): skapa en anpassad e-postmall</span><span class="sxs-lookup"><span data-stu-id="54887-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="54887-145">Om du ska använda någon av de inbyggda mallarna eller skapa e-postmeddelandet direkt i guiden kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="54887-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="54887-146">I säkerhets & Compliance Center går du till **Threat Management** \> **attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="54887-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="54887-147">På sidan **simulera attacker** , i något av **Spear phishing-** eller **Spear phishing-** avsnitt, klickar du på **angrepps information**.</span><span class="sxs-lookup"><span data-stu-id="54887-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="54887-148">Det spelar ingen roll var du skapar mallen.</span><span class="sxs-lookup"><span data-stu-id="54887-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="54887-149">De tillgängliga alternativen i mallen är desamma för båda typerna av nät fiske attacker.</span><span class="sxs-lookup"><span data-stu-id="54887-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="54887-150">Klicka på **ny mall** **i området för** **nätfiske-mallar** på sidan **information om attack** som öppnas.</span><span class="sxs-lookup"><span data-stu-id="54887-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="54887-151">Guiden **Konfigurera nätfiske-mall** startas i en ny utfällning.</span><span class="sxs-lookup"><span data-stu-id="54887-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="54887-152">Ange ett unikt visnings namn för mallen i steget **Starta** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="54887-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="54887-153">Konfigurera följande inställningar i steget **Konfigurera e-postinformation** :</span><span class="sxs-lookup"><span data-stu-id="54887-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="54887-154">**From (namn)**: visnings namnet som används för meddelande avsändare.</span><span class="sxs-lookup"><span data-stu-id="54887-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="54887-155">**Från (e-post)**: avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="54887-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="54887-156">**URL till nätfiske-inloggnings Server**: Klicka på den nedrullningsbara List rutan och välj en av de tillgängliga URL-adresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="54887-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="54887-157">Det här är URL-adressen som användarna blir frestade att klicka på.</span><span class="sxs-lookup"><span data-stu-id="54887-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="54887-158">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="54887-158">The choices are:</span></span>

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
     > - <span data-ttu-id="54887-159">Alla URL-adresser är avsiktligt http, inte https.</span><span class="sxs-lookup"><span data-stu-id="54887-159">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="54887-160">En URL-ryktes tjänst kan identifiera en eller flera av dessa URL-adresser som osäkra.</span><span class="sxs-lookup"><span data-stu-id="54887-160">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="54887-161">Kontrol lera tillgängligheten för URL-adressen i webbläsare som stöds innan du använder URL-adressen i en nätfiske-kampanj.</span><span class="sxs-lookup"><span data-stu-id="54887-161">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="54887-162">**Anpassad URL** för start sidan: Ange en extra landnings sida där användarna ska klicka på nätfiske-länken och ange deras autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="54887-162">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="54887-163">Den här länken ersätter standard ingångs sidan.</span><span class="sxs-lookup"><span data-stu-id="54887-163">This link replaces the default landing page.</span></span> <span data-ttu-id="54887-164">Om du till exempel har intern medvetenhets kurs kan du ange den URL-adressen här.</span><span class="sxs-lookup"><span data-stu-id="54887-164">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="54887-165">**Kategori**: den här inställningen används inte (något du anger ignoreras).</span><span class="sxs-lookup"><span data-stu-id="54887-165">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="54887-166">**Ämne**: fältet **subject** i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="54887-166">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="54887-167">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="54887-167">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="54887-168">I steget Skapa **e-post** skapar du meddelande texten i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="54887-168">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="54887-169">Du kan använda fliken **e-post** (en RTF-HTML-redigerare) eller fliken **källa** (RAW HTML-kod).</span><span class="sxs-lookup"><span data-stu-id="54887-169">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="54887-170">HTML-formateringen kan vara så enkel eller komplex som du vill.</span><span class="sxs-lookup"><span data-stu-id="54887-170">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="54887-171">Du kan infoga bilder och text för att förbättra believability för meddelandet i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="54887-171">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="54887-172">`${username}` infogar mottagarens namn.</span><span class="sxs-lookup"><span data-stu-id="54887-172">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="54887-173">`${loginserverurl}` infogar URL-adressen för ett **nätfiske-inloggningsnamn** från föregående steg.</span><span class="sxs-lookup"><span data-stu-id="54887-173">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="54887-174">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="54887-174">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="54887-175">Klicka på **Slutför** i steget **Bekräfta** .</span><span class="sxs-lookup"><span data-stu-id="54887-175">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="54887-176">Steg 2: skapa och starta Spear phishing-kampanjen</span><span class="sxs-lookup"><span data-stu-id="54887-176">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="54887-177">I säkerhets & Compliance Center går du till **Threat Management** \> **attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="54887-177">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="54887-178">På sidan **simulera attacker** väljer du något av följande alternativ baserat på den typ av kampanj som du vill skapa:</span><span class="sxs-lookup"><span data-stu-id="54887-178">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="54887-179">I avsnittet **Spear phishing (identifierings skörd)** klickar du på **Starta attack** eller klicka på **angrepps information** \> .</span><span class="sxs-lookup"><span data-stu-id="54887-179">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="54887-180">I avsnittet **Spear phishing (bilaga)** klickar du på **Starta attack** eller klicka på **angrepps information** \> .</span><span class="sxs-lookup"><span data-stu-id="54887-180">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="54887-181">Guiden **Konfigurera nätfiske-attack** startas med en ny utfällning.</span><span class="sxs-lookup"><span data-stu-id="54887-181">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="54887-182">Gör något av följande i steget **Starta** :</span><span class="sxs-lookup"><span data-stu-id="54887-182">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="54887-183">I rutan **namn** anger du ett unikt visnings namn för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-183">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="54887-184">Klicka inte på **Använd mall** eftersom du kommer att skapa e-postmeddelandet senare i guiden.</span><span class="sxs-lookup"><span data-stu-id="54887-184">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="54887-185">Klicka på **Använd mall** och välj en inbyggd eller anpassad e-postmall.</span><span class="sxs-lookup"><span data-stu-id="54887-185">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="54887-186">När du har valt mallen fylls **namn** rutan i automatiskt baserat på mallen, men du kan ändra namnet.</span><span class="sxs-lookup"><span data-stu-id="54887-186">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Start sida för nätfiske](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="54887-188">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="54887-188">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="54887-189">Gör något av följande i steget **mål mottagare** :</span><span class="sxs-lookup"><span data-stu-id="54887-189">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="54887-190">Klicka på **Adress bok** för att välja mottagarna (användare eller grupper) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-190">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="54887-191">Varje riktad mottagare måste ha en Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="54887-191">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="54887-192">Om du klickar på **filter** och **använder** utan att ange ett Sök kriterium returneras alla mottagare och läggs till i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-192">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="54887-193">Klicka på **Importera** sedan importera **fil** för att importera en CSV-eller rad avgränsad fil med e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="54887-193">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="54887-194">Varje rad måste innehålla mottagarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="54887-194">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="54887-195">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="54887-195">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="54887-196">Konfigurera följande inställningar i steget **Konfigurera e-postinformation** :</span><span class="sxs-lookup"><span data-stu-id="54887-196">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="54887-197">Om du har valt en mall i **Start** steget är de flesta dessa värden redan konfigurerade, men du kan ändra dem.</span><span class="sxs-lookup"><span data-stu-id="54887-197">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="54887-198">**From (namn)**: visnings namnet som används för meddelande avsändare.</span><span class="sxs-lookup"><span data-stu-id="54887-198">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="54887-199">**Från (e-post)**: avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="54887-199">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="54887-200">Du kan ange en verklig eller falsk e-postadress från organisationens e-postdomän, eller så kan du ange en verklig eller falsk extern e-postadress.</span><span class="sxs-lookup"><span data-stu-id="54887-200">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="54887-201">En giltig avsändares e-postadress från din organisation löses faktiskt i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="54887-201">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="54887-202">**URL till nätfiske-inloggnings Server**: Klicka på den nedrullningsbara List rutan och välj en av de tillgängliga URL-adresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="54887-202">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="54887-203">Det här är URL-adressen som användarna blir frestade att klicka på.</span><span class="sxs-lookup"><span data-stu-id="54887-203">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="54887-204">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="54887-204">The choices are:</span></span>

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
     > - <span data-ttu-id="54887-205">Alla URL-adresser är avsiktligt http, inte https.</span><span class="sxs-lookup"><span data-stu-id="54887-205">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="54887-206">En URL-ryktes tjänst kan identifiera en eller flera av dessa URL-adresser som osäkra.</span><span class="sxs-lookup"><span data-stu-id="54887-206">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="54887-207">Kontrol lera tillgängligheten för URL-adressen i webbläsare som stöds innan du använder URL-adressen i en nätfiske-kampanj.</span><span class="sxs-lookup"><span data-stu-id="54887-207">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="54887-208">Du måste välja en URL-adress.</span><span class="sxs-lookup"><span data-stu-id="54887-208">You are required to select a URL.</span></span> <span data-ttu-id="54887-209">För **Spear nätfiske (Attachment)** kan du ta bort länken från meddelande texten i nästa steg (annars innehåller meddelandet både en länk **och** en bifogad fil).</span><span class="sxs-lookup"><span data-stu-id="54887-209">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="54887-210">**Typ av bifogad fil**: den här inställningen är endast tillgänglig i **Spear nätfiske (bifogade filer)** .</span><span class="sxs-lookup"><span data-stu-id="54887-210">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="54887-211">Klicka på den nedrullningsbara List rutan och välj **. DOCX** eller **. PDF** i listan.</span><span class="sxs-lookup"><span data-stu-id="54887-211">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="54887-212">**Namn på bifogad fil**: den här inställningen är endast tillgänglig i **Spear nätfiske (bifogade filer)** .</span><span class="sxs-lookup"><span data-stu-id="54887-212">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="54887-213">Ange ett fil namn för. docx-eller. pdf-bilagan.</span><span class="sxs-lookup"><span data-stu-id="54887-213">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="54887-214">**Anpassad URL** för start sidan: Ange en extra landnings sida där användarna ska klicka på nätfiske-länken och ange deras autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="54887-214">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="54887-215">Den här länken ersätter standard ingångs sidan.</span><span class="sxs-lookup"><span data-stu-id="54887-215">This link replaces the default landing page.</span></span> <span data-ttu-id="54887-216">Om du till exempel har intern medvetenhets kurs kan du ange den URL-adressen här.</span><span class="sxs-lookup"><span data-stu-id="54887-216">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="54887-217">**Ämne**: fältet **subject** i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="54887-217">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="54887-218">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="54887-218">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="54887-219">I steget Skapa **e-post** skapar du meddelande texten i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="54887-219">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="54887-220">Om du har valt en mall i **Start** steget är meddelande texten redan konfigurerad, men du kan anpassa den.</span><span class="sxs-lookup"><span data-stu-id="54887-220">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="54887-221">Du kan använda fliken **e-post** (en RTF-HTML-redigerare) eller fliken **källa** (RAW HTML-kod).</span><span class="sxs-lookup"><span data-stu-id="54887-221">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="54887-222">HTML-formateringen kan vara så enkel eller komplex som du vill.</span><span class="sxs-lookup"><span data-stu-id="54887-222">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="54887-223">Du kan infoga bilder och text för att förbättra believability för meddelandet i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="54887-223">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="54887-224">`${username}` infogar mottagarens namn.</span><span class="sxs-lookup"><span data-stu-id="54887-224">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="54887-225">`${loginserverurl}` infogar URL-värdet för **nätfiske-inloggningsnamn** .</span><span class="sxs-lookup"><span data-stu-id="54887-225">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="54887-226">För **Spear phishing-kampanjer (bifogade filer)** bör du ta bort länken från meddelande texten (annars kommer meddelandet att innehålla både en länk **och** en bifogad fil, och länkar klickar spåras inte till en bifogad fil).</span><span class="sxs-lookup"><span data-stu-id="54887-226">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Skriv e-postmeddelande](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="54887-228">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="54887-228">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="54887-229">Klicka på **Slutför** i steget **Bekräfta** för att starta kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-229">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="54887-230">Nät fiske meddelandet levereras till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="54887-230">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="54887-231">Lösen ords attacker</span><span class="sxs-lookup"><span data-stu-id="54887-231">Password attack campaigns</span></span>

<span data-ttu-id="54887-232">Ett *lösen ords angrepp* försöker gissa lösen ord för användar konton i en organisation, vanligt vis efter att angriparen har identifierat ett eller flera giltiga användar konton.</span><span class="sxs-lookup"><span data-stu-id="54887-232">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="54887-233">I angrepps simulatorer är två olika typer av lösen ords attacker tillgängliga för dig för att testa komplexiteten hos användarnas lösen ord:</span><span class="sxs-lookup"><span data-stu-id="54887-233">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="54887-234">**Råa force-lösenord (ordbok)**: en upptaget-eller *ordlisteattacker* *använder en stor* ordbok med lösen ord på ett användar konto med en fråga om att en av dem ska fungera (många lösen ord mot ett konto).</span><span class="sxs-lookup"><span data-stu-id="54887-234">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="54887-235">Felaktig låsning-gräns för lösen ord</span><span class="sxs-lookup"><span data-stu-id="54887-235">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="54887-236">För ord listor kan du ange ett eller flera lösen ord (som anges manuellt eller i en uppladdad fil) och du kan ange en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="54887-236">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="54887-237">**Attack för lösen ords besprutning**: ett *lösen* ord som används för att skydda en dator använder samma noggrant övervägda lösen ord mot en lista över användar konton (ett lösen ord mot många konton)</span><span class="sxs-lookup"><span data-stu-id="54887-237">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="54887-238">Lösen ords dusch attacker är svårare att upptäcka än problem med råa lösen ord (sannolikheten att lyckas ökar när en angripare försöker med ett lösen ord på dussin tals eller hundratals konton utan risk för att Tripping användarens felaktiga lösen ord).</span><span class="sxs-lookup"><span data-stu-id="54887-238">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="54887-239">För angrepp med lösen ord kan du bara ange ett lösen ord och du kan ange en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="54887-239">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="54887-240">Lösen ords attacker i angrepps Simulator vidarebefordrar användar namn och lösen ord för grundläggande autentisering till en slut punkt, så de fungerar även med andra autentiseringsmetoder (AD FS, lösen ords-hash-synkronisering, vidarekoppling, PingFederate, osv.).</span><span class="sxs-lookup"><span data-stu-id="54887-240">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="54887-241">För användare som har MFA aktiverat, även om lösen ords attackeret försöker nå sitt faktiska lösen ord, kommer försöket alltid att registreras som ett fel (med andra ord kommer MFA-användarna aldrig att synas i kampanjens antal **lyckade försök** .</span><span class="sxs-lookup"><span data-stu-id="54887-241">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="54887-242">Det här är det förväntade resultatet.</span><span class="sxs-lookup"><span data-stu-id="54887-242">This is the expected result.</span></span> <span data-ttu-id="54887-243">MFA är en primär metod för att skydda mot lösen ords attacker.</span><span class="sxs-lookup"><span data-stu-id="54887-243">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="54887-244">Skapa och starta en kampanj för att attackera lösen ord</span><span class="sxs-lookup"><span data-stu-id="54887-244">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="54887-245">I säkerhets & Compliance Center går du till **Threat Management** \> **attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="54887-245">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="54887-246">På sidan **simulera attacker** väljer du något av följande alternativ baserat på den typ av kampanj som du vill skapa:</span><span class="sxs-lookup"><span data-stu-id="54887-246">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="54887-247">I avsnittet **råa force-lösenord (ordbok)** klickar du på **Starta attack** eller klicka på **angrepps information** \> .</span><span class="sxs-lookup"><span data-stu-id="54887-247">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="54887-248">Klicka på **Starta** attacker eller klicka på **angrepps information** i avsnittet **lösen ords besprutnings attacker** \> .</span><span class="sxs-lookup"><span data-stu-id="54887-248">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="54887-249">Guiden **Konfigurera lösen ords attacker** startar i en ny utfällning.</span><span class="sxs-lookup"><span data-stu-id="54887-249">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="54887-250">Ange ett unikt visnings namn för kampanjen i steget **Starta** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="54887-250">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="54887-251">Gör något av följande i steget **mål användare** :</span><span class="sxs-lookup"><span data-stu-id="54887-251">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="54887-252">Klicka på **Adress bok** för att välja mottagarna (användare eller grupper) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-252">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="54887-253">Varje riktad mottagare måste ha en Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="54887-253">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="54887-254">Om du klickar på **filter** och **använder** utan att ange ett Sök kriterium returneras alla mottagare och läggs till i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-254">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="54887-255">Klicka på **Importera** sedan importera **fil** för att importera en CSV-eller rad avgränsad fil med e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="54887-255">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="54887-256">Varje rad måste innehålla mottagarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="54887-256">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="54887-257">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="54887-257">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="54887-258">Välj vad du vill göra i steget **Välj angrepps inställningar** :</span><span class="sxs-lookup"><span data-stu-id="54887-258">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="54887-259">**Råa force-lösenord (ordbok)**: gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="54887-259">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="54887-260">**Ange lösen ord manuellt**: Skriv in ett lösen ord i rutan **Tryck på RETUR för att lägga till ett** lösenord och tryck sedan på RETUR.</span><span class="sxs-lookup"><span data-stu-id="54887-260">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="54887-261">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="54887-261">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="54887-262">**Ladda upp lösen ord från en ordlistefil**: Klicka på **Ladda upp** för att importera en befintlig textfil som innehåller ett lösen ord på varje rad och en tom sista rad.</span><span class="sxs-lookup"><span data-stu-id="54887-262">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="54887-263">Text filen måste vara 10 MB eller mindre och får inte innehålla fler än 30000 lösen ord.</span><span class="sxs-lookup"><span data-stu-id="54887-263">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="54887-264">**Lösen ords besprutning**: Skriv ett lösen ord i **lösen ordet som ska användas i angrepps** rutan.</span><span class="sxs-lookup"><span data-stu-id="54887-264">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="54887-265">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="54887-265">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="54887-266">Klicka på **Slutför** i steget **Bekräfta** för att starta kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-266">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="54887-267">De angivna lösen orden är på användare som du har angett.</span><span class="sxs-lookup"><span data-stu-id="54887-267">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="54887-268">Visa kampanj resultat</span><span class="sxs-lookup"><span data-stu-id="54887-268">View campaign results</span></span>

<span data-ttu-id="54887-269">När du har lanserat en kampanj kan du kontrol lera förlopp och resultat på huvud sidan **simulera attacker** .</span><span class="sxs-lookup"><span data-stu-id="54887-269">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="54887-270">Aktiva kampanjer visar ett statusfält, ett slutfört procent värde och "(slutförda användare) av (totalt antal användare).</span><span class="sxs-lookup"><span data-stu-id="54887-270">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="54887-271">Om du klickar på knappen **Uppdatera** uppdateras alla aktiva kampanjer.</span><span class="sxs-lookup"><span data-stu-id="54887-271">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="54887-272">Du kan också klicka på **Avbryt** om du vill stoppa en aktiv kampanj.</span><span class="sxs-lookup"><span data-stu-id="54887-272">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="54887-273">När kampanjen är klar ändras status till **angreppet**.</span><span class="sxs-lookup"><span data-stu-id="54887-273">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="54887-274">Du kan visa kampanj resultaten genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="54887-274">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="54887-275">Klicka på **Visa rapport** under namnet på kampanjen på huvud sidan för **simulerade attacker** .</span><span class="sxs-lookup"><span data-stu-id="54887-275">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="54887-276">På huvud sidan **simulera attacker** klickar du på **angrepps information** i avsnittet för typen av attack.</span><span class="sxs-lookup"><span data-stu-id="54887-276">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="54887-277">På sidan **information om attack** som öppnas väljer du kampanjen i avsnittet **attack historik** .</span><span class="sxs-lookup"><span data-stu-id="54887-277">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="54887-278">En av de föregående åtgärderna tar dig till en sida med namnet **angrepps information**.</span><span class="sxs-lookup"><span data-stu-id="54887-278">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="54887-279">Informationen som är tillgänglig på den här sidan för varje typ av kampanj beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="54887-279">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="54887-280">Spear nätfiske (identitets skörd) kampanj resultat</span><span class="sxs-lookup"><span data-stu-id="54887-280">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="54887-281">Följande information finns på sidan **attack information** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="54887-281">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="54887-282">Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-282">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="54887-283">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="54887-283">**Total users targeted**</span></span>

- <span data-ttu-id="54887-284">**Lyckade försök**: antalet användare som klickade på länken **och** angett sina *autentiseringsuppgifter (användar* namn och lösen ord).</span><span class="sxs-lookup"><span data-stu-id="54887-284">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="54887-285">**Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.</span><span class="sxs-lookup"><span data-stu-id="54887-285">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="54887-286">**Snabbast Klicka** här: hur lång tid det tog för den första användaren att klicka på länken efter att du startade kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-286">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="54887-287">**Genomsnittligt Klicka** på: summan av hur lång tid det tog för alla att klicka på länken dividerat med antalet användare som klickade på länken.</span><span class="sxs-lookup"><span data-stu-id="54887-287">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="54887-288">**Klicka på framgång-frekvens**: en procents ATS som beräknas av (antal användare som klickade på länken)/ **totalt riktade användare**.</span><span class="sxs-lookup"><span data-stu-id="54887-288">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="54887-289">**Snabbaste uppgifter**: hur länge den tog den första användaren att ange sina autentiseringsuppgifter efter att du har lanserat kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-289">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="54887-290">**Genomsnittligt antal autentiseringsuppgifter**: summan av hur lång tid det tog för alla att ange sina inloggnings uppgifter dividerat med antalet användare som angav sina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="54887-290">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="54887-291">**Framgång för lyckade** uppgifter: en procents ATS som beräknas av (antal användare som angav sina uppgifter)/ **totalt riktade till användare**.</span><span class="sxs-lookup"><span data-stu-id="54887-291">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="54887-292">Ett stapeldiagram som visar numret på den **klickade** och den **angivna autentiseringsuppgiften** per dag.</span><span class="sxs-lookup"><span data-stu-id="54887-292">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="54887-293">Ett cirkel diagram som visar den **länk som klickas** på, **autentiseringsuppgifter** och **ingen** procents ATS för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-293">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="54887-294">I avsnittet **kompromissade användare** visas information om de användare som klickade på länken:</span><span class="sxs-lookup"><span data-stu-id="54887-294">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="54887-295">Användarens e-postadress</span><span class="sxs-lookup"><span data-stu-id="54887-295">The user's email address</span></span>

  - <span data-ttu-id="54887-296">Datum/tid när de klickade på länken.</span><span class="sxs-lookup"><span data-stu-id="54887-296">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="54887-297">IP-adress för klienter.</span><span class="sxs-lookup"><span data-stu-id="54887-297">The client IP address.</span></span>

  - <span data-ttu-id="54887-298">Information om användarens version av Windows och webbläsare.</span><span class="sxs-lookup"><span data-stu-id="54887-298">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="54887-299">Du kan klicka på **Exportera** för att exportera resultaten till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="54887-299">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="54887-300">Spear phishing (bilagor) kampanj resultat</span><span class="sxs-lookup"><span data-stu-id="54887-300">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="54887-301">Följande information finns på sidan **attack information** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="54887-301">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="54887-302">Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-302">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="54887-303">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="54887-303">**Total users targeted**</span></span>

- <span data-ttu-id="54887-304">**Lyckade försök**: antalet användare som öppnade eller hämtade och öppnade den bifogade filen (för hands version).</span><span class="sxs-lookup"><span data-stu-id="54887-304">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="54887-305">**Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.</span><span class="sxs-lookup"><span data-stu-id="54887-305">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="54887-306">**Snabbare öppning av bifogade filer**: hur lång tid det tog för den första användaren att öppna den bifogade filen när du startade kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-306">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="54887-307">**Genomsnittlig öppnings tid för bifogade filer**: summan av hur lång tid det tog för alla att öppna den bifogade filen dividerat med antalet användare som öppnade den bifogade filen.</span><span class="sxs-lookup"><span data-stu-id="54887-307">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="54887-308">Slut för **ande frekvens för bifogad fil**: en procents ATS som beräknas av (antal användare som öppnade bilagan)/ **totalt riktade användare**.</span><span class="sxs-lookup"><span data-stu-id="54887-308">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="54887-309">Lösen ords intrång (ord listor) kampanj resultat</span><span class="sxs-lookup"><span data-stu-id="54887-309">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="54887-310">Följande information finns på sidan **attack information** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="54887-310">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="54887-311">Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-311">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="54887-312">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="54887-312">**Total users targeted**</span></span>

- <span data-ttu-id="54887-313">**Lyckade försök**: antalet användare som har hittat ett angivet lösen ord.</span><span class="sxs-lookup"><span data-stu-id="54887-313">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="54887-314">**Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.</span><span class="sxs-lookup"><span data-stu-id="54887-314">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="54887-315">I avsnittet **kompromissade användare** visas e-postadresserna till de berörda användarna.</span><span class="sxs-lookup"><span data-stu-id="54887-315">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="54887-316">Du kan klicka på **Exportera** för att exportera resultaten till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="54887-316">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="54887-317">Lösen ords spridningen kampanj resultat</span><span class="sxs-lookup"><span data-stu-id="54887-317">Password spray attack campaign results</span></span>

<span data-ttu-id="54887-318">Följande information finns på sidan **attack information** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="54887-318">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="54887-319">Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="54887-319">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="54887-320">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="54887-320">**Total users targeted**</span></span>

- <span data-ttu-id="54887-321">**Lyckade försök**: antalet användare som har hittats med det angivna lösen ordet.</span><span class="sxs-lookup"><span data-stu-id="54887-321">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="54887-322">**Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.</span><span class="sxs-lookup"><span data-stu-id="54887-322">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
