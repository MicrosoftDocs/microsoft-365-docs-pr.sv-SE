---
title: Angrepps Simulator i Microsoft Defender för Office 365
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
description: Administratörer kan lära sig att använda en angrepps Simulator för att köra simulerade nät för nätfiske och lösen ord i Microsoft 365 E5-eller Microsoft Defender för Office 365 plan 2-organisationer.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a9abca803c21baa7fcb5f0ab7b3d4c497c4473b8
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939326"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="97bc4-103">Angrepps Simulator i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="97bc4-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="97bc4-104">Om din organisation har Microsoft Defender för Office 365 abonnemang 2, som innehåller [hot undersökningar och svars funktioner](office-365-ti.md), kan du använda angrepps simulatorn i säkerhets & Compliance Center för att köra realistiska angrepp i din organisation.</span><span class="sxs-lookup"><span data-stu-id="97bc4-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="97bc4-105">Dessa simulerade attacker kan hjälpa dig att identifiera och hitta sårbara användare innan en verklig attack påverkar din botten linje.</span><span class="sxs-lookup"><span data-stu-id="97bc4-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="97bc4-106">Läs den här artikeln om du vill veta mer.</span><span class="sxs-lookup"><span data-stu-id="97bc4-106">Read this article to learn more.</span></span>

> [!TIP]
> <span data-ttu-id="97bc4-107">Utbildning för attack simulering är tillgängligt för offentlig för hands version i Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="97bc4-107">Attack simulation training is available for Public Preview in the Microsoft 365 security center.</span></span> <span data-ttu-id="97bc4-108">Ta en titt på [simulera ett nät fiske angrepp med Microsoft Defender för Office 365](attack-simulation-training.md) för mer information.</span><span class="sxs-lookup"><span data-stu-id="97bc4-108">Check out [Simulate a phishing attack with Microsoft Defender for Office 365](attack-simulation-training.md) to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="97bc4-109">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="97bc4-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="97bc4-110">Gå till <https://protection.office.com/> för att öppna Säkerhets- och efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="97bc4-110">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="97bc4-111">Angrepps simulatorn  finns i \> **angrepps** hanterings tjänsten.</span><span class="sxs-lookup"><span data-stu-id="97bc4-111">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="97bc4-112">Gå direkt till angrepps simulatorn, öppen <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="97bc4-112">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="97bc4-113">Mer information om tillgängligheten för angrepps enheter för olika Microsoft 365-prenumerationer finns i [Beskrivning av Microsoft Defender för Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="97bc4-113">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="97bc4-114">Du måste vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-114">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="97bc4-115">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="97bc4-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="97bc4-116">Ditt konto måste konfigureras för multifaktorautentisering (MFA) för att skapa och hantera kampanjer i angrepps Simulator.</span><span class="sxs-lookup"><span data-stu-id="97bc4-116">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="97bc4-117">Anvisningar finns i [Konfigurera multifaktorautentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="97bc4-117">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="97bc4-118">Nät fiske kampanjer samlar in och bearbetar händelser i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="97bc4-118">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="97bc4-119">Historiska kampanj data kommer att vara tillgängliga i upp till 90 dagar efter att du har lanserat kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-119">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="97bc4-120">Information om attack simulering och utbildning relaterade data lagras med andra kunddata för Microsoft 365-tjänster.</span><span class="sxs-lookup"><span data-stu-id="97bc4-120">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="97bc4-121">Mer information finns i [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span><span class="sxs-lookup"><span data-stu-id="97bc4-121">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="97bc4-122">Det finns inga motsvarande PowerShell-cmdlets för angrepps Simulator.</span><span class="sxs-lookup"><span data-stu-id="97bc4-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="97bc4-123">Spear nät fiske kampanjer</span><span class="sxs-lookup"><span data-stu-id="97bc4-123">Spear phishing campaigns</span></span>

<span data-ttu-id="97bc4-124">*Nätfiske* är en generisk term för e-postattacker som försöker stjäla känslig information i meddelanden som verkar vara från legitima eller betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="97bc4-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="97bc4-125">*Spear nätfiske* är ett riktat nätfiske-angrepp som använder prioriterat och anpassat innehåll som är specifikt skräddarsydda för de riktade mottagarna (vanligt vis efter Reconnaissance på mottagarna).</span><span class="sxs-lookup"><span data-stu-id="97bc4-125">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="97bc4-126">I angrepps simulatorer är två olika typer av Spear nät fiske kampanjer tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="97bc4-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="97bc4-127">**Spear nätfiske (uppgifter om skörd)**: ett försök görs att få mottagarna att klicka på en URL i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="97bc4-127">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="97bc4-128">Om de klickar på länken uppmanas de att ange sina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="97bc4-128">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="97bc4-129">Om de gör det tas de till någon av följande platser:</span><span class="sxs-lookup"><span data-stu-id="97bc4-129">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="97bc4-130">En standard sida som förklarar att detta var ett test och ger tips för att känna igen nät fiske meddelanden.</span><span class="sxs-lookup"><span data-stu-id="97bc4-130">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Vad användarna ser om de klickar på nätfiske-länken och anger deras autentiseringsuppgifter](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="97bc4-132">En anpassad sida (URL) som du anger.</span><span class="sxs-lookup"><span data-stu-id="97bc4-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="97bc4-133">**Spear nätfiske (bifogad fil)**: med angreppet försöker mottagarna att öppna en. docx-eller. pdf-bilaga i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="97bc4-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="97bc4-134">Den bifogade filen innehåller samma innehåll från den vanliga nät fiske länken, men den första meningen börjar med " \<Display Name\> , du ser det här meddelandet som ett nyligen öppnade e-postmeddelande...".</span><span class="sxs-lookup"><span data-stu-id="97bc4-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="97bc4-135">För närvarande upphör Spear nät fiske kampanjer inte att gälla.</span><span class="sxs-lookup"><span data-stu-id="97bc4-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="97bc4-136">Skapa en Spear nätfiske-kampanj</span><span class="sxs-lookup"><span data-stu-id="97bc4-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="97bc4-137">En viktig del av alla Spear nät fiske kampanjer är utseendet och känslan hos det e-postmeddelande som skickas till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="97bc4-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="97bc4-138">För att skapa och konfigurera e-postmeddelandet har du följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="97bc4-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="97bc4-139">**Använda en inbyggd e-postmall**: två inbyggda mallar är tillgängliga: **pris gåvo kampanjen** och **löne uppdatering**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="97bc4-140">Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="97bc4-141">**Skapa en återanvändbar e-postmall**: när du har skapat och sparat e-postmallen kan du använda den igen i framtida Spear nät fiske kampanjer.</span><span class="sxs-lookup"><span data-stu-id="97bc4-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="97bc4-142">Du kan ytterligare anpassa vissa, alla eller inga av e-postegenskaperna från mallen när du skapar och startar kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="97bc4-143">**Skapa e-postmeddelandet i guiden**: du kan skapa e-postmeddelandet direkt i guiden när du skapar och startar Spear phishing-kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="97bc4-144">Steg 1 (valfritt): skapa en anpassad e-postmall</span><span class="sxs-lookup"><span data-stu-id="97bc4-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="97bc4-145">Om du ska använda någon av de inbyggda mallarna eller skapa e-postmeddelandet direkt i guiden kan du hoppa över det här steget.</span><span class="sxs-lookup"><span data-stu-id="97bc4-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="97bc4-146">I säkerhets & Compliance Center går du till **Threat Management** \> **attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="97bc4-147">På sidan **simulera attacker** , i något av **Spear phishing-** eller **Spear phishing-** avsnitt, klickar du på **angrepps information**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="97bc4-148">Det spelar ingen roll var du skapar mallen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="97bc4-149">De tillgängliga alternativen i mallen är desamma för båda typerna av nät fiske attacker.</span><span class="sxs-lookup"><span data-stu-id="97bc4-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="97bc4-150">Klicka på **ny mall** **i området för** **nätfiske-mallar** på sidan **information om attack** som öppnas.</span><span class="sxs-lookup"><span data-stu-id="97bc4-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="97bc4-151">Guiden **Konfigurera nätfiske-mall** startas i en ny utfällning.</span><span class="sxs-lookup"><span data-stu-id="97bc4-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="97bc4-152">Ange ett unikt visnings namn för mallen i steget **Starta** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="97bc4-153">Konfigurera följande inställningar i steget **Konfigurera e-postinformation** :</span><span class="sxs-lookup"><span data-stu-id="97bc4-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="97bc4-154">**From (namn)**: visnings namnet som används för meddelande avsändare.</span><span class="sxs-lookup"><span data-stu-id="97bc4-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="97bc4-155">**Från (e-post)**: avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="97bc4-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="97bc4-156">**URL till nätfiske-inloggnings Server**: Klicka på den nedrullningsbara List rutan och välj en av de tillgängliga URL-adresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="97bc4-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="97bc4-157">Det här är URL-adressen som användarna blir frestade att klicka på.</span><span class="sxs-lookup"><span data-stu-id="97bc4-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="97bc4-158">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="97bc4-158">The choices are:</span></span>

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
     > <span data-ttu-id="97bc4-159">En URL-ryktes tjänst kan identifiera en eller flera av dessa URL-adresser som osäkra.</span><span class="sxs-lookup"><span data-stu-id="97bc4-159">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="97bc4-160">Kontrol lera tillgängligheten för URL-adressen i webbläsare som stöds innan du använder URL-adressen i en nätfiske-kampanj.</span><span class="sxs-lookup"><span data-stu-id="97bc4-160">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="97bc4-161">**Anpassad URL** för start sidan: Ange en extra landnings sida där användarna ska klicka på nätfiske-länken och ange deras autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="97bc4-161">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="97bc4-162">Den här länken ersätter standard ingångs sidan.</span><span class="sxs-lookup"><span data-stu-id="97bc4-162">This link replaces the default landing page.</span></span> <span data-ttu-id="97bc4-163">Om du till exempel har intern medvetenhets kurs kan du ange den URL-adressen här.</span><span class="sxs-lookup"><span data-stu-id="97bc4-163">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="97bc4-164">**Kategori**: den här inställningen används inte (något du anger ignoreras).</span><span class="sxs-lookup"><span data-stu-id="97bc4-164">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="97bc4-165">**Ämne**: fältet **subject** i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="97bc4-165">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="97bc4-166">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-166">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="97bc4-167">I steget Skapa **e-post** skapar du meddelande texten i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="97bc4-167">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="97bc4-168">Du kan använda fliken **e-post** (en RTF-HTML-redigerare) eller fliken **källa** (RAW HTML-kod).</span><span class="sxs-lookup"><span data-stu-id="97bc4-168">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="97bc4-169">HTML-formateringen kan vara så enkel eller komplex som du vill.</span><span class="sxs-lookup"><span data-stu-id="97bc4-169">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="97bc4-170">Du kan infoga bilder och text för att förbättra believability för meddelandet i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="97bc4-170">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="97bc4-171">`${username}` infogar mottagarens namn.</span><span class="sxs-lookup"><span data-stu-id="97bc4-171">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="97bc4-172">`${loginserverurl}` infogar URL-adressen för ett **nätfiske-inloggningsnamn** från föregående steg.</span><span class="sxs-lookup"><span data-stu-id="97bc4-172">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="97bc4-173">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-173">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="97bc4-174">Klicka på **Slutför** i steget **Bekräfta** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-174">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="97bc4-175">Steg 2: skapa och starta Spear phishing-kampanjen</span><span class="sxs-lookup"><span data-stu-id="97bc4-175">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="97bc4-176">I säkerhets & Compliance Center går du till **Threat Management** \> **attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-176">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="97bc4-177">På sidan **simulera attacker** väljer du något av följande alternativ baserat på den typ av kampanj som du vill skapa:</span><span class="sxs-lookup"><span data-stu-id="97bc4-177">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="97bc4-178">I avsnittet **Spear phishing (identifierings skörd)** klickar du på **Starta attack** eller klicka på **angrepps information** \> .</span><span class="sxs-lookup"><span data-stu-id="97bc4-178">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="97bc4-179">I avsnittet **Spear phishing (bilaga)** klickar du på **Starta attack** eller klicka på **angrepps information** \> .</span><span class="sxs-lookup"><span data-stu-id="97bc4-179">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="97bc4-180">Guiden **Konfigurera nätfiske-attack** startas med en ny utfällning.</span><span class="sxs-lookup"><span data-stu-id="97bc4-180">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="97bc4-181">Gör något av följande i steget **Starta** :</span><span class="sxs-lookup"><span data-stu-id="97bc4-181">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="97bc4-182">I rutan **namn** anger du ett unikt visnings namn för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-182">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="97bc4-183">Klicka inte på **Använd mall** eftersom du kommer att skapa e-postmeddelandet senare i guiden.</span><span class="sxs-lookup"><span data-stu-id="97bc4-183">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="97bc4-184">Klicka på **Använd mall** och välj en inbyggd eller anpassad e-postmall.</span><span class="sxs-lookup"><span data-stu-id="97bc4-184">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="97bc4-185">När du har valt mallen fylls **namn** rutan i automatiskt baserat på mallen, men du kan ändra namnet.</span><span class="sxs-lookup"><span data-stu-id="97bc4-185">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="97bc4-186">![Start sida för nätfiske](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="97bc4-186">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="97bc4-187">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="97bc4-188">Gör något av följande i steget **mål mottagare** :</span><span class="sxs-lookup"><span data-stu-id="97bc4-188">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="97bc4-189">Klicka på **Adress bok** för att välja mottagarna (användare eller grupper) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-189">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="97bc4-190">Varje riktad mottagare måste ha en Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="97bc4-190">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="97bc4-191">Om du klickar på **filter** och **använder** utan att ange ett Sök kriterium returneras alla mottagare och läggs till i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-191">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="97bc4-192">Klicka på **Importera** sedan importera **fil** för att importera en CSV-eller rad avgränsad fil med e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="97bc4-192">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="97bc4-193">Varje rad måste innehålla mottagarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="97bc4-193">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="97bc4-194">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-194">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="97bc4-195">Konfigurera följande inställningar i steget **Konfigurera e-postinformation** :</span><span class="sxs-lookup"><span data-stu-id="97bc4-195">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="97bc4-196">Om du har valt en mall i **Start** steget är de flesta dessa värden redan konfigurerade, men du kan ändra dem.</span><span class="sxs-lookup"><span data-stu-id="97bc4-196">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="97bc4-197">**From (namn)**: visnings namnet som används för meddelande avsändare.</span><span class="sxs-lookup"><span data-stu-id="97bc4-197">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="97bc4-198">**Från (e-post)**: avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="97bc4-198">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="97bc4-199">Du kan ange en verklig eller falsk e-postadress från organisationens e-postdomän, eller så kan du ange en verklig eller falsk extern e-postadress.</span><span class="sxs-lookup"><span data-stu-id="97bc4-199">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="97bc4-200">En giltig avsändares e-postadress från din organisation löses faktiskt i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="97bc4-200">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="97bc4-201">**URL till nätfiske-inloggnings Server**: Klicka på den nedrullningsbara List rutan och välj en av de tillgängliga URL-adresserna i listan.</span><span class="sxs-lookup"><span data-stu-id="97bc4-201">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="97bc4-202">Det här är URL-adressen som användarna blir frestade att klicka på.</span><span class="sxs-lookup"><span data-stu-id="97bc4-202">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="97bc4-203">Alternativen är:</span><span class="sxs-lookup"><span data-stu-id="97bc4-203">The choices are:</span></span>

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
     > - <span data-ttu-id="97bc4-204">Alla URL-adresser är avsiktligt http, inte https.</span><span class="sxs-lookup"><span data-stu-id="97bc4-204">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="97bc4-205">En URL-ryktes tjänst kan identifiera en eller flera av dessa URL-adresser som osäkra.</span><span class="sxs-lookup"><span data-stu-id="97bc4-205">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="97bc4-206">Kontrol lera tillgängligheten för URL-adressen i webbläsare som stöds innan du använder URL-adressen i en nätfiske-kampanj.</span><span class="sxs-lookup"><span data-stu-id="97bc4-206">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="97bc4-207">Du måste välja en URL-adress.</span><span class="sxs-lookup"><span data-stu-id="97bc4-207">You are required to select a URL.</span></span> <span data-ttu-id="97bc4-208">För **Spear nätfiske (Attachment)** kan du ta bort länken från meddelande texten i nästa steg (annars innehåller meddelandet både en länk **och** en bifogad fil).</span><span class="sxs-lookup"><span data-stu-id="97bc4-208">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="97bc4-209">**Typ av bifogad fil**: den här inställningen är endast tillgänglig i **Spear nätfiske (bifogade filer)** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-209">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="97bc4-210">Klicka på den nedrullningsbara List rutan och välj **. DOCX** eller **. PDF** i listan.</span><span class="sxs-lookup"><span data-stu-id="97bc4-210">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="97bc4-211">**Namn på bifogad fil**: den här inställningen är endast tillgänglig i **Spear nätfiske (bifogade filer)** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-211">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="97bc4-212">Ange ett fil namn för. docx-eller. pdf-bilagan.</span><span class="sxs-lookup"><span data-stu-id="97bc4-212">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="97bc4-213">**Anpassad URL** för start sidan: Ange en extra landnings sida där användarna ska klicka på nätfiske-länken och ange deras autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="97bc4-213">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="97bc4-214">Den här länken ersätter standard ingångs sidan.</span><span class="sxs-lookup"><span data-stu-id="97bc4-214">This link replaces the default landing page.</span></span> <span data-ttu-id="97bc4-215">Om du till exempel har intern medvetenhets kurs kan du ange den URL-adressen här.</span><span class="sxs-lookup"><span data-stu-id="97bc4-215">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="97bc4-216">**Ämne**: fältet **subject** i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="97bc4-216">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="97bc4-217">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-217">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="97bc4-218">I steget Skapa **e-post** skapar du meddelande texten i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="97bc4-218">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="97bc4-219">Om du har valt en mall i **Start** steget är meddelande texten redan konfigurerad, men du kan anpassa den.</span><span class="sxs-lookup"><span data-stu-id="97bc4-219">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="97bc4-220">Du kan använda fliken **e-post** (en RTF-HTML-redigerare) eller fliken **källa** (RAW HTML-kod).</span><span class="sxs-lookup"><span data-stu-id="97bc4-220">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="97bc4-221">HTML-formateringen kan vara så enkel eller komplex som du vill.</span><span class="sxs-lookup"><span data-stu-id="97bc4-221">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="97bc4-222">Du kan infoga bilder och text för att förbättra believability för meddelandet i mottagarens e-postklient.</span><span class="sxs-lookup"><span data-stu-id="97bc4-222">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="97bc4-223">`${username}` infogar mottagarens namn.</span><span class="sxs-lookup"><span data-stu-id="97bc4-223">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="97bc4-224">`${loginserverurl}` infogar URL-värdet för **nätfiske-inloggningsnamn** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-224">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="97bc4-225">För **Spear phishing-kampanjer (bifogade filer)** bör du ta bort länken från meddelande texten (annars kommer meddelandet att innehålla både en länk **och** en bifogad fil, och länkar klickar spåras inte till en bifogad fil).</span><span class="sxs-lookup"><span data-stu-id="97bc4-225">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="97bc4-226">![Skriv e-postmeddelande](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="97bc4-226">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="97bc4-227">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-227">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="97bc4-228">Klicka på **Slutför** i steget **Bekräfta** för att starta kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-228">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="97bc4-229">Nät fiske meddelandet levereras till mottagarna.</span><span class="sxs-lookup"><span data-stu-id="97bc4-229">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="97bc4-230">Lösen ords attacker</span><span class="sxs-lookup"><span data-stu-id="97bc4-230">Password attack campaigns</span></span>

<span data-ttu-id="97bc4-231">Ett *lösen ords angrepp* försöker gissa lösen ord för användar konton i en organisation, vanligt vis efter att angriparen har identifierat ett eller flera giltiga användar konton.</span><span class="sxs-lookup"><span data-stu-id="97bc4-231">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="97bc4-232">I angrepps simulatorer är två olika typer av lösen ords attacker tillgängliga för dig för att testa komplexiteten hos användarnas lösen ord:</span><span class="sxs-lookup"><span data-stu-id="97bc4-232">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="97bc4-233">**Råa force-lösenord (ordbok)**: en upptaget-eller *ordlisteattacker* *använder en stor* ordbok med lösen ord på ett användar konto med en fråga om att en av dem ska fungera (många lösen ord mot ett konto).</span><span class="sxs-lookup"><span data-stu-id="97bc4-233">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="97bc4-234">Felaktig låsning-gräns för lösen ord</span><span class="sxs-lookup"><span data-stu-id="97bc4-234">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="97bc4-235">För ord listor kan du ange ett eller flera lösen ord (som anges manuellt eller i en uppladdad fil) och du kan ange en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="97bc4-235">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="97bc4-236">**Attack för lösen ords besprutning**: ett *lösen* ord som används för att skydda en dator använder samma noggrant övervägda lösen ord mot en lista över användar konton (ett lösen ord mot många konton)</span><span class="sxs-lookup"><span data-stu-id="97bc4-236">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="97bc4-237">Lösen ords dusch attacker är svårare att upptäcka än problem med råa lösen ord (sannolikheten att lyckas ökar när en angripare försöker med ett lösen ord på dussin tals eller hundratals konton utan risk för att Tripping användarens felaktiga lösen ord).</span><span class="sxs-lookup"><span data-stu-id="97bc4-237">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="97bc4-238">För angrepp med lösen ord kan du bara ange ett lösen ord och du kan ange en eller flera användare.</span><span class="sxs-lookup"><span data-stu-id="97bc4-238">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="97bc4-239">Lösen ords attacker i angrepps Simulator vidarebefordrar användar namn och lösen ord för grundläggande autentisering till en slut punkt, så de fungerar även med andra autentiseringsmetoder (AD FS, lösen ords-hash-synkronisering, vidarekoppling, PingFederate, osv.).</span><span class="sxs-lookup"><span data-stu-id="97bc4-239">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="97bc4-240">För användare som har MFA aktiverat, även om lösen ords attackeret försöker nå sitt faktiska lösen ord, kommer försöket alltid att registreras som ett fel (med andra ord kommer MFA-användarna aldrig att synas i kampanjens antal **lyckade försök** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-240">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="97bc4-241">Det här är det förväntade resultatet.</span><span class="sxs-lookup"><span data-stu-id="97bc4-241">This is the expected result.</span></span> <span data-ttu-id="97bc4-242">MFA är en primär metod för att skydda mot lösen ords attacker.</span><span class="sxs-lookup"><span data-stu-id="97bc4-242">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="97bc4-243">Skapa och starta en kampanj för att attackera lösen ord</span><span class="sxs-lookup"><span data-stu-id="97bc4-243">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="97bc4-244">I säkerhets & Compliance Center går du till **Threat Management** \> **attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-244">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="97bc4-245">På sidan **simulera attacker** väljer du något av följande alternativ baserat på den typ av kampanj som du vill skapa:</span><span class="sxs-lookup"><span data-stu-id="97bc4-245">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="97bc4-246">I avsnittet **råa force-lösenord (ordbok)** klickar du på **Starta attack** eller klicka på **angrepps information** \> .</span><span class="sxs-lookup"><span data-stu-id="97bc4-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="97bc4-247">Klicka på **Starta** attacker eller klicka på **angrepps information** i avsnittet **lösen ords besprutnings attacker** \> .</span><span class="sxs-lookup"><span data-stu-id="97bc4-247">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="97bc4-248">Guiden **Konfigurera lösen ords attacker** startar i en ny utfällning.</span><span class="sxs-lookup"><span data-stu-id="97bc4-248">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="97bc4-249">Ange ett unikt visnings namn för kampanjen i steget **Starta** och klicka sedan på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-249">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="97bc4-250">Gör något av följande i steget **mål användare** :</span><span class="sxs-lookup"><span data-stu-id="97bc4-250">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="97bc4-251">Klicka på **Adress bok** för att välja mottagarna (användare eller grupper) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-251">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="97bc4-252">Varje riktad mottagare måste ha en Exchange Online-postlåda.</span><span class="sxs-lookup"><span data-stu-id="97bc4-252">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="97bc4-253">Om du klickar på **filter** och **använder** utan att ange ett Sök kriterium returneras alla mottagare och läggs till i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-253">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="97bc4-254">Klicka på **Importera** sedan importera **fil** för att importera en CSV-eller rad avgränsad fil med e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="97bc4-254">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="97bc4-255">Varje rad måste innehålla mottagarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="97bc4-255">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="97bc4-256">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-256">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="97bc4-257">Välj vad du vill göra i steget **Välj angrepps inställningar** :</span><span class="sxs-lookup"><span data-stu-id="97bc4-257">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="97bc4-258">**Råa force-lösenord (ordbok)**: gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="97bc4-258">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="97bc4-259">**Ange lösen ord manuellt**: Skriv in ett lösen ord i rutan **Tryck på RETUR för att lägga till ett** lösenord och tryck sedan på RETUR.</span><span class="sxs-lookup"><span data-stu-id="97bc4-259">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="97bc4-260">Upprepa det här steget så många gånger det behövs.</span><span class="sxs-lookup"><span data-stu-id="97bc4-260">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="97bc4-261">**Ladda upp lösen ord från en ordlistefil**: Klicka på **Ladda upp** för att importera en befintlig textfil som innehåller ett lösen ord på varje rad och en tom sista rad.</span><span class="sxs-lookup"><span data-stu-id="97bc4-261">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="97bc4-262">Text filen måste vara 10 MB eller mindre och får inte innehålla fler än 30000 lösen ord.</span><span class="sxs-lookup"><span data-stu-id="97bc4-262">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="97bc4-263">**Lösen ords besprutning**: Skriv ett lösen ord i **lösen ordet som ska användas i angrepps** rutan.</span><span class="sxs-lookup"><span data-stu-id="97bc4-263">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="97bc4-264">När du är klar klickar du på **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-264">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="97bc4-265">Klicka på **Slutför** i steget **Bekräfta** för att starta kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-265">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="97bc4-266">De angivna lösen orden är på användare som du har angett.</span><span class="sxs-lookup"><span data-stu-id="97bc4-266">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="97bc4-267">Visa kampanj resultat</span><span class="sxs-lookup"><span data-stu-id="97bc4-267">View campaign results</span></span>

<span data-ttu-id="97bc4-268">När du har lanserat en kampanj kan du kontrol lera förlopp och resultat på huvud sidan **simulera attacker** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-268">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="97bc4-269">Aktiva kampanjer visar ett statusfält, ett slutfört procent värde och "(slutförda användare) av (totalt antal användare).</span><span class="sxs-lookup"><span data-stu-id="97bc4-269">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="97bc4-270">Om du klickar på knappen **Uppdatera** uppdateras alla aktiva kampanjer.</span><span class="sxs-lookup"><span data-stu-id="97bc4-270">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="97bc4-271">Du kan också klicka på **Avbryt** om du vill stoppa en aktiv kampanj.</span><span class="sxs-lookup"><span data-stu-id="97bc4-271">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="97bc4-272">När kampanjen är klar ändras status till **angreppet**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-272">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="97bc4-273">Du kan visa kampanj resultaten genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="97bc4-273">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="97bc4-274">Klicka på **Visa rapport** under namnet på kampanjen på huvud sidan för **simulerade attacker** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-274">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="97bc4-275">På huvud sidan **simulera attacker** klickar du på **angrepps information** i avsnittet för typen av attack.</span><span class="sxs-lookup"><span data-stu-id="97bc4-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="97bc4-276">På sidan **information om attack** som öppnas väljer du kampanjen i avsnittet **attack historik** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-276">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="97bc4-277">En av de föregående åtgärderna tar dig till en sida med namnet **angrepps information**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-277">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="97bc4-278">Informationen som är tillgänglig på den här sidan för varje typ av kampanj beskrivs i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="97bc4-278">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="97bc4-279">Spear nätfiske (identitets skörd) kampanj resultat</span><span class="sxs-lookup"><span data-stu-id="97bc4-279">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="97bc4-280">Följande information finns på sidan **attack information** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="97bc4-280">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="97bc4-281">Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-281">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="97bc4-282">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="97bc4-282">**Total users targeted**</span></span>

- <span data-ttu-id="97bc4-283">**Lyckade försök**: antalet användare som klickade på länken **och** angett sina *autentiseringsuppgifter (användar* namn och lösen ord).</span><span class="sxs-lookup"><span data-stu-id="97bc4-283">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="97bc4-284">**Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.</span><span class="sxs-lookup"><span data-stu-id="97bc4-284">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="97bc4-285">**Snabbast Klicka** här: hur lång tid det tog för den första användaren att klicka på länken efter att du startade kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-285">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="97bc4-286">**Genomsnittligt Klicka** på: summan av hur lång tid det tog för alla att klicka på länken dividerat med antalet användare som klickade på länken.</span><span class="sxs-lookup"><span data-stu-id="97bc4-286">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="97bc4-287">**Klicka på framgång-frekvens**: en procents ATS som beräknas av (antal användare som klickade på länken)/ **totalt riktade användare**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="97bc4-288">**Snabbaste uppgifter**: hur länge den tog den första användaren att ange sina autentiseringsuppgifter efter att du har lanserat kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-288">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="97bc4-289">**Genomsnittligt antal autentiseringsuppgifter**: summan av hur lång tid det tog för alla att ange sina inloggnings uppgifter dividerat med antalet användare som angav sina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="97bc4-289">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="97bc4-290">**Framgång för lyckade** uppgifter: en procents ATS som beräknas av (antal användare som angav sina uppgifter)/ **totalt riktade till användare**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="97bc4-291">Ett stapeldiagram som visar numret på den **klickade** och den **angivna autentiseringsuppgiften** per dag.</span><span class="sxs-lookup"><span data-stu-id="97bc4-291">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="97bc4-292">Ett cirkel diagram som visar den **länk som klickas** på, **autentiseringsuppgifter** och **ingen** procents ATS för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-292">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="97bc4-293">I avsnittet **kompromissade användare** visas information om de användare som klickade på länken:</span><span class="sxs-lookup"><span data-stu-id="97bc4-293">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="97bc4-294">Användarens e-postadress</span><span class="sxs-lookup"><span data-stu-id="97bc4-294">The user's email address</span></span>

  - <span data-ttu-id="97bc4-295">Datum/tid när de klickade på länken.</span><span class="sxs-lookup"><span data-stu-id="97bc4-295">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="97bc4-296">IP-adress för klienter.</span><span class="sxs-lookup"><span data-stu-id="97bc4-296">The client IP address.</span></span>

  - <span data-ttu-id="97bc4-297">Information om användarens version av Windows och webbläsare.</span><span class="sxs-lookup"><span data-stu-id="97bc4-297">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="97bc4-298">Du kan klicka på **Exportera** för att exportera resultaten till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="97bc4-298">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="97bc4-299">Spear phishing (bilagor) kampanj resultat</span><span class="sxs-lookup"><span data-stu-id="97bc4-299">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="97bc4-300">Följande information finns på sidan **attack information** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="97bc4-300">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="97bc4-301">Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-301">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="97bc4-302">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="97bc4-302">**Total users targeted**</span></span>

- <span data-ttu-id="97bc4-303">**Lyckade försök**: antalet användare som öppnade eller hämtade och öppnade den bifogade filen (för hands version).</span><span class="sxs-lookup"><span data-stu-id="97bc4-303">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="97bc4-304">**Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.</span><span class="sxs-lookup"><span data-stu-id="97bc4-304">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="97bc4-305">**Snabbare öppning av bifogade filer**: hur lång tid det tog för den första användaren att öppna den bifogade filen när du startade kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-305">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="97bc4-306">**Genomsnittlig öppnings tid för bifogade filer**: summan av hur lång tid det tog för alla att öppna den bifogade filen dividerat med antalet användare som öppnade den bifogade filen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-306">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="97bc4-307">Slut för **ande frekvens för bifogad fil**: en procents ATS som beräknas av (antal användare som öppnade bilagan)/ **totalt riktade användare**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-307">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="97bc4-308">Lösen ords intrång (ord listor) kampanj resultat</span><span class="sxs-lookup"><span data-stu-id="97bc4-308">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="97bc4-309">Följande information finns på sidan **attack information** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="97bc4-309">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="97bc4-310">Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-310">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="97bc4-311">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="97bc4-311">**Total users targeted**</span></span>

- <span data-ttu-id="97bc4-312">**Lyckade försök**: antalet användare som har hittat ett angivet lösen ord.</span><span class="sxs-lookup"><span data-stu-id="97bc4-312">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="97bc4-313">**Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.</span><span class="sxs-lookup"><span data-stu-id="97bc4-313">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="97bc4-314">I avsnittet **kompromissade användare** visas e-postadresserna till de berörda användarna.</span><span class="sxs-lookup"><span data-stu-id="97bc4-314">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="97bc4-315">Du kan klicka på **Exportera** för att exportera resultaten till en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="97bc4-315">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="97bc4-316">Lösen ords spridningen kampanj resultat</span><span class="sxs-lookup"><span data-stu-id="97bc4-316">Password spray attack campaign results</span></span>

<span data-ttu-id="97bc4-317">Följande information finns på sidan **attack information** för varje kampanj:</span><span class="sxs-lookup"><span data-stu-id="97bc4-317">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="97bc4-318">Varaktigheten (start datum/tid och Slutdatum/tid) för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="97bc4-318">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="97bc4-319">**Totalt antal riktade användare**</span><span class="sxs-lookup"><span data-stu-id="97bc4-319">**Total users targeted**</span></span>

- <span data-ttu-id="97bc4-320">**Lyckade försök**: antalet användare som har hittats med det angivna lösen ordet.</span><span class="sxs-lookup"><span data-stu-id="97bc4-320">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="97bc4-321">**Total framgång-frekvens**: en procents ATS som beräknas vid **lyckade försök**  /  **totalt för användare riktade** sig.</span><span class="sxs-lookup"><span data-stu-id="97bc4-321">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
