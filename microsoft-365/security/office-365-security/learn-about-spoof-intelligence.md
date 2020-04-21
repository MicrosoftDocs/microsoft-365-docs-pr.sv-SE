---
title: Konfigurera förfalskningsinformation
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du konfigurerar förfalskade avsändare så att de tillåter eller inte tillåter, och andra falska intelligensinställningar i Exchange Online och Exchange Online Protection (EOP).
ms.openlocfilehash: 958f27d190748ee12976a6b47794a23e025172cf
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630497"
---
# <a name="configure-spoof-intelligence-in-microsoft-365"></a><span data-ttu-id="0f48c-103">Konfigurera falska underrättelser i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f48c-103">Configure spoof intelligence in Microsoft 365</span></span>

<span data-ttu-id="0f48c-104">Om du är en Microsoft 365-kund med postlådor i Exchange Online eller en fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor skyddas inkommande e-postmeddelanden automatiskt mot förfalskning av EOP från och med oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="0f48c-104">If you're an Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="0f48c-105">EOP använder falska underrättelser som en del av organisationens övergripande försvar mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0f48c-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="0f48c-106">Mer information finns i [Skydd mot förfalskning i Microsoft 365](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="0f48c-106">For more information, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="0f48c-107">När en avsändare förfalskar en e-postadress verkar de vara en användare i en av organisationens domäner eller en användare i en extern domän som skickar e-post till din organisation.</span><span class="sxs-lookup"><span data-stu-id="0f48c-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="0f48c-108">Angripare som förfalskar avsändare för att skicka skräppost eller nätfiske e-post måste blockeras.</span><span class="sxs-lookup"><span data-stu-id="0f48c-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="0f48c-109">Men det finns scenarier där legitima avsändare är förfalskning.</span><span class="sxs-lookup"><span data-stu-id="0f48c-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="0f48c-110">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="0f48c-110">For example:</span></span>

- <span data-ttu-id="0f48c-111">Legitima scenarier för förfalskning av interna domäner:</span><span class="sxs-lookup"><span data-stu-id="0f48c-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="0f48c-112">Avsändare från tredje part använder domänen för att skicka massutskick till dina egna anställda för företagsavundersökningar.</span><span class="sxs-lookup"><span data-stu-id="0f48c-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>

  - <span data-ttu-id="0f48c-113">Ett externt företag genererar och skickar reklam- eller produktuppdateringar för din räkning.</span><span class="sxs-lookup"><span data-stu-id="0f48c-113">An external company generates and sends advertising or product updates on your behalf.</span></span>

  - <span data-ttu-id="0f48c-114">En assistent måste regelbundet skicka e-post till en annan person inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="0f48c-114">An assistant regularly needs to send email for another person within your organization.</span></span>

  - <span data-ttu-id="0f48c-115">Ett internt program skickar e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="0f48c-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="0f48c-116">Legitima scenarier för förfalskning av externa domäner:</span><span class="sxs-lookup"><span data-stu-id="0f48c-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="0f48c-117">Avsändaren finns i en e-postlista (kallas även diskussionslista) och e-postlistan vidarebefordrar e-post från den ursprungliga avsändaren till alla deltagare i e-postlistan.</span><span class="sxs-lookup"><span data-stu-id="0f48c-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>

  - <span data-ttu-id="0f48c-118">Ett externt företag skickar e-post på uppdrag av ett annat företag (till exempel en automatiserad rapport eller ett program-som-en-tjänst företag).</span><span class="sxs-lookup"><span data-stu-id="0f48c-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="0f48c-119">Falska underrättelser, och särskilt standardprincipen (och endast) falska underrättelser, hjälper till att säkerställa att falska e-postmeddelanden som skickas av legitima avsändare inte fastnar i skräppostfilter i Microsoft 365 eller externa e-postsystem, samtidigt som användarna skyddas från skräppost- eller nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="0f48c-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in spam filters in Microsoft 365 or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="0f48c-120">Du kan hantera falska underrättelser i Microsoft 365 Security & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-kunder; Exchange Online Protection PowerShell för fristående EOP-kunder).</span><span class="sxs-lookup"><span data-stu-id="0f48c-120">You can manage spoof intelligence in the Microsoft 365 Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0f48c-121">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="0f48c-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0f48c-122">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0f48c-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0f48c-123">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="0f48c-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="0f48c-124">Om du vill gå direkt till <https://protection.office.com/antiphishing>sidan **Mot nätfiske** använder du .</span><span class="sxs-lookup"><span data-stu-id="0f48c-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="0f48c-125">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0f48c-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0f48c-126">Information om hur du använder Windows PowerShell för att ansluta till fristående Exchange Online Protection PowerShell finns i artikeln om att [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="0f48c-126">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0f48c-127">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="0f48c-127">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="0f48c-128">Om du vill ändra informationsprincipen eller aktivera eller inaktivera falska underrättelser måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="0f48c-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="0f48c-129">För skrivskyddad åtkomst till den falska underrättelsepolicyn måste du vara medlem i rollgruppen **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="0f48c-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="0f48c-130">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter för Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0f48c-130">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="0f48c-131">För våra rekommenderade inställningar för falska underrättelser, [EOP standard anti-phishing-principinställningar](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="0f48c-131">For our recommended settings for spoof intelligence, [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="0f48c-132">Använd Security & Compliance Center för att hantera förfalskade avsändare</span><span class="sxs-lookup"><span data-stu-id="0f48c-132">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="0f48c-133">Om du har en Office 365 Enterprise E5-prenumeration eller har köpt och ATP-tillägg (Advanced Threat Protection) separat kan du även hantera avsändare som förfalskar din domän via [Spoof Intelligence-insikten](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="0f48c-133">If you have an Office 365 Enterprise E5 subscription or have separately purchased and Advanced Threat Protection (ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="0f48c-134">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="0f48c-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="0f48c-135">På sidan **Inställningar för** skräppost ![klickar](../../media/scc-expand-icon.png) du på Ikonen Expandera för att expandera **Spoof intelligence policy**.</span><span class="sxs-lookup"><span data-stu-id="0f48c-135">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Välj informationspolicy för falska underrättelser](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="0f48c-137">Gör något av följande val:</span><span class="sxs-lookup"><span data-stu-id="0f48c-137">Make one of the following selections:</span></span>

   - <span data-ttu-id="0f48c-138">**Granska nya avsändare**</span><span class="sxs-lookup"><span data-stu-id="0f48c-138">**Review new senders**</span></span>
   - <span data-ttu-id="0f48c-139">**Visa mig avsändare som jag redan har granskat**</span><span class="sxs-lookup"><span data-stu-id="0f48c-139">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="0f48c-140">I **Bestäm om dessa avsändare tillåts förfalska användarnas** utfällbara alternativ som visas väljer du en av följande flikar:</span><span class="sxs-lookup"><span data-stu-id="0f48c-140">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="0f48c-141">**Dina domäner:** Avsändare som förfalskar användare i dina interna domäner.</span><span class="sxs-lookup"><span data-stu-id="0f48c-141">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="0f48c-142">**Externa domäner**: Avsändare som förfalskar användare i externa domäner.</span><span class="sxs-lookup"><span data-stu-id="0f48c-142">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="0f48c-143">Klicka ![på](../../media/scc-expand-icon.png) Ikonen Expandera i kolumnen **Tillåtet att förfalska?**</span><span class="sxs-lookup"><span data-stu-id="0f48c-143">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="0f48c-144">Välj **Ja** om du vill tillåta förfalskad avsändare eller välj **Nej** för att markera meddelandet som förfalskat.</span><span class="sxs-lookup"><span data-stu-id="0f48c-144">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="0f48c-145">Åtgärden styrs av standardpolicyn mot nätfiske eller anpassade ATP-principer för nätfiske (standardvärdet är **Flytta meddelande till mappen Skräppost**).</span><span class="sxs-lookup"><span data-stu-id="0f48c-145">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="0f48c-146">Mer information finns [i Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="0f48c-146">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Skärmbild som visar de utfällda utfällbara avsändare som spoofed och om avsändaren tillåts förfalska](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="0f48c-148">Kolumnerna och värdena som visas förklaras i följande lista:</span><span class="sxs-lookup"><span data-stu-id="0f48c-148">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="0f48c-149">**Förfalskad användare**: Användarkontot som förfalskas.</span><span class="sxs-lookup"><span data-stu-id="0f48c-149">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="0f48c-150">Det här är meddelandeavsändaren i från-adressen (kallas även `5322.From` adressen) som visas i e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="0f48c-150">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="0f48c-151">Adressens giltighet kontrolleras inte av SPF.</span><span class="sxs-lookup"><span data-stu-id="0f48c-151">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="0f48c-152">På fliken **Dina domäner** innehåller värdet en enda e-postadress, eller om käll-e-postservern förfalskar flera användarkonton innehåller det **mer än en**.</span><span class="sxs-lookup"><span data-stu-id="0f48c-152">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="0f48c-153">På fliken **Externa domäner** innehåller värdet domänen för den förfalskade användaren, inte den fullständiga e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="0f48c-153">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="0f48c-154">**Skicka infrastruktur:** Domänen som hittades i en omvänd DNS-sökning (PTR-post) av käll-e-postserverns IP-adress, eller IP-adressen om källan inte har någon PTR-post.</span><span class="sxs-lookup"><span data-stu-id="0f48c-154">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="0f48c-155">Mer information om meddelandekällor och meddelandeavsändare finns i [En översikt över e-postmeddelandenstandarder](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="0f48c-155">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="0f48c-156">**Antal meddelanden**: Antalet meddelanden från den sändande infrastrukturen till din organisation som innehåller den angivna förfalskade avsändaren eller avsändare inom de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="0f48c-156">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="0f48c-157">**Antal klagomål från användare:** Klagomål som lämnats in av dina användare mot denna avsändare inom de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="0f48c-157">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="0f48c-158">Klagomål är vanligtvis i form av skräp inlagor till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0f48c-158">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="0f48c-159">**Autentiseringsresultat**: Ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="0f48c-159">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="0f48c-160">**Godkänd**: Avsändaren skickade avsändare e-postautentiseringskontroller (SPF eller DKIM).</span><span class="sxs-lookup"><span data-stu-id="0f48c-160">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="0f48c-161">**Misslyckades**: Avsändaren misslyckades EOP-avsänaren autentiseringskontroller.</span><span class="sxs-lookup"><span data-stu-id="0f48c-161">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="0f48c-162">**Okänd**: Resultatet av dessa kontroller är inte känt.</span><span class="sxs-lookup"><span data-stu-id="0f48c-162">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="0f48c-163">**Beslut som fastställts av**: Visar vem som fastställt om den sändande infrastrukturen tillåts förfalska användaren:</span><span class="sxs-lookup"><span data-stu-id="0f48c-163">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="0f48c-164">**Spoof intelligens politik** (automatisk)</span><span class="sxs-lookup"><span data-stu-id="0f48c-164">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="0f48c-165">**Admin** (manuell)</span><span class="sxs-lookup"><span data-stu-id="0f48c-165">**Admin** (manual)</span></span>

   - <span data-ttu-id="0f48c-166">**Senast sedd**: Det sista datumet då ett meddelande togs emot från den sändande infrastrukturen som innehåller den falska användaren.</span><span class="sxs-lookup"><span data-stu-id="0f48c-166">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="0f48c-167">**Tillåtet att förfalska?**: De värden som du ser här är:</span><span class="sxs-lookup"><span data-stu-id="0f48c-167">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="0f48c-168">**Ja**: Meddelanden från kombinationen av förfalskad användare och skicka infrastruktur är tillåtna och behandlas inte som förfalskad e-post.</span><span class="sxs-lookup"><span data-stu-id="0f48c-168">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="0f48c-169">**Nej**: Meddelanden från kombinationen av förfalskad användare och skickad infrastruktur markeras som förfalskade.</span><span class="sxs-lookup"><span data-stu-id="0f48c-169">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="0f48c-170">Åtgärden styrs av standardpolicyn mot nätfiske eller anpassade ATP-principer för nätfiske (standardvärdet är **Flytta meddelande till mappen Skräppost**).</span><span class="sxs-lookup"><span data-stu-id="0f48c-170">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="0f48c-171">Mer information finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="0f48c-171">See the next section for more information.</span></span>

     - <span data-ttu-id="0f48c-172">**Vissa användare** ( fliken**Domäner** endast): En skickande infrastruktur förfalskar flera användare, där vissa falska användare är tillåtna och andra inte är det.</span><span class="sxs-lookup"><span data-stu-id="0f48c-172">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="0f48c-173">Använd fliken **Detaljerad** om du vill visa de specifika adresserna.</span><span class="sxs-lookup"><span data-stu-id="0f48c-173">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="0f48c-174">Klicka på **Spara**längst ned på sidan .</span><span class="sxs-lookup"><span data-stu-id="0f48c-174">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="0f48c-175">Använda PowerShell för att hantera förfalskade avsändare</span><span class="sxs-lookup"><span data-stu-id="0f48c-175">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="0f48c-176">Om du vill visa tillåtna och blockerade avsändare i falska underrättelser använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="0f48c-176">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="0f48c-177">I det här exemplet returneras detaljerad information om alla avsändare som tillåts förfalska användare i dina domäner.</span><span class="sxs-lookup"><span data-stu-id="0f48c-177">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilter -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="0f48c-178">Detaljerad syntax- och parameterinformation finns i [Hämta-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="0f48c-178">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).</span></span>

<span data-ttu-id="0f48c-179">Så här konfigurerar du tillåtna och blockerade avsändare i falska underrättelser:</span><span class="sxs-lookup"><span data-stu-id="0f48c-179">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="0f48c-180">Fånga den aktuella listan över upptäckta förfalskade avsändare genom att skriva utdata från cmdleten **Get-PhishFilterPolicy** till en CSV-fil:</span><span class="sxs-lookup"><span data-stu-id="0f48c-180">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="0f48c-181">Redigera CSV-filen för att lägga till eller ändra värdena **SpoofedUser** (e-postadress) och **AllowedToSpoof** (Ja eller Nej).</span><span class="sxs-lookup"><span data-stu-id="0f48c-181">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="0f48c-182">Spara filen, läs filen och lagra innehållet som `$UpdateSpoofedSenders`en variabel med namnet :</span><span class="sxs-lookup"><span data-stu-id="0f48c-182">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="0f48c-183">Använd `$UpdateSpoofedSenders` variabeln för att konfigurera principen för falska underrättelser:</span><span class="sxs-lookup"><span data-stu-id="0f48c-183">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="0f48c-184">Detaljerad syntax- och parameterinformation finns i [Ange-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="0f48c-184">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="0f48c-185">Använd Security & Compliance Center för att konfigurera falska underrättelser</span><span class="sxs-lookup"><span data-stu-id="0f48c-185">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="0f48c-186">Konfigurationsalternativen för falska underrättelser beskrivs i [Spoof-inställningar i anti-phishing-principer](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="0f48c-186">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="0f48c-187">Vilka alternativ du har tillgång till beror på din prenumeration:</span><span class="sxs-lookup"><span data-stu-id="0f48c-187">Your available options depend on your subscription:</span></span>

- <span data-ttu-id="0f48c-188">Fristående EOP-organisationer utan Exchange Online-postlådor kan inte konfigurera falska intelligensinställningar.</span><span class="sxs-lookup"><span data-stu-id="0f48c-188">Standalone EOP organizations without Exchange Online mailboxes can't configure spoof intelligence settings.</span></span>

- <span data-ttu-id="0f48c-189">Microsoft 365-organisationer med Exchange Online-postlådor kan konfigurera falska intelligensinställningar i standardprincipen mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0f48c-189">Microsoft 365 organizations with Exchange Online mailboxes can configure spoof intelligence settings in the default (and only) anti-phishing policy.</span></span> <span data-ttu-id="0f48c-190">Instruktioner finns [i Konfigurera standardprincipen mot nätfiske i EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="0f48c-190">For instructions, see [Configure the default anti-phishing policy in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="0f48c-191">Microsoft 365-organisationer med ATP kan konfigurera falska intelligensinställningar i atp-principen mot nätfiske för standardtjänster och även i anpassade ATP-principer mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="0f48c-191">Microsoft 365 organizations with ATP can configure spoof intelligence settings in the default ATP anti-phishing policy, and also in custom ATP anti-phishing policies.</span></span> <span data-ttu-id="0f48c-192">Instruktioner finns [i Konfigurera ATP-principer för nätfiske i Microsoft 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0f48c-192">For instructions, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0f48c-193">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="0f48c-193">How do you know these procedures worked?</span></span>

<span data-ttu-id="0f48c-194">Om du vill kontrollera att du har konfigurerat falska underrättelser med avsändare som är tillåtna och inte får förfalska och att du har konfigurerat falska intelligensinställningar använder du något av följande steg:</span><span class="sxs-lookup"><span data-stu-id="0f48c-194">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="0f48c-195">Gå till **Policy** \> **Policy** \> för skräppostutredning av **skräppost** \> för **Spoof intelligence policy** \> & som du redan **har granskat** \> fliken Säkerhet **Your Domains** & **efterlevnadscenter** och verifiera värdet **tillåten att förfalska?**</span><span class="sxs-lookup"><span data-stu-id="0f48c-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="0f48c-196">I PowerShell kör du följande kommandon för att visa de avsändare som är tillåtna och inte får förfalska:</span><span class="sxs-lookup"><span data-stu-id="0f48c-196">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilter -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="0f48c-197">I PowerShell kör du följande kommando för att exportera listan över alla falska avsändare till en CSV-fil:</span><span class="sxs-lookup"><span data-stu-id="0f48c-197">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="0f48c-198">I Microsoft 365-organisationer med Exchange Online-postlådor gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="0f48c-198">In Microsoft 365 organizations with Exchange Online mailboxes, do either of the following steps:</span></span>

  - <span data-ttu-id="0f48c-199">Gå till **Policy** \> **Anti-phishing-principen** \> mot **nätfiske** \> **i** Security & Compliance Center och visa information i det utfällbara utfällbara energiläget.</span><span class="sxs-lookup"><span data-stu-id="0f48c-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

  - <span data-ttu-id="0f48c-200">I Exchange Online PowerShell kör du följande kommando och verifierar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="0f48c-200">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
    ```

- <span data-ttu-id="0f48c-201">I Microsoft 365 ATP-organisationer gör du något av följande:</span><span class="sxs-lookup"><span data-stu-id="0f48c-201">In Microsoft 365 ATP organizations, do either of the following steps:</span></span>

  - <span data-ttu-id="0f48c-202">I Security & Compliance Center går du till **ATP-principen** **mot hothanteringspolicy** \> **Policy** \> och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="0f48c-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** and do either of the following steps:</span></span>

    - <span data-ttu-id="0f48c-203">Välj en princip i listan.</span><span class="sxs-lookup"><span data-stu-id="0f48c-203">Select a policy from the list.</span></span> <span data-ttu-id="0f48c-204">I det utfällbara resultatet som visas kontrollerar du värdena i avsnittet **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="0f48c-204">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
    - <span data-ttu-id="0f48c-205">Klicka på **Standardprincip**.</span><span class="sxs-lookup"><span data-stu-id="0f48c-205">Click **Default policy**.</span></span> <span data-ttu-id="0f48c-206">I det utfällbara resultatet som visas kontrollerar du värdena i avsnittet **Spoof.**</span><span class="sxs-lookup"><span data-stu-id="0f48c-206">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

  - <span data-ttu-id="0f48c-207">I Exchange Online PowerShell ersätter du \<Namn\> med Office365 AntiPhish Standard eller namnet på en anpassad ATP-anti-phishing-princip och kör följande kommando och verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="0f48c-207">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom ATP anti-phishing policy, and run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "<Name>"
    ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="0f48c-208">Andra sätt att hantera förfalskning och nätfiske</span><span class="sxs-lookup"><span data-stu-id="0f48c-208">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="0f48c-209">Var flitig om förfalskning och nätfiske skydd.</span><span class="sxs-lookup"><span data-stu-id="0f48c-209">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="0f48c-210">Här är relaterade sätt att kontrollera avsändare som förfalskar din domän och hjälper till att förhindra att de skadar din organisation:</span><span class="sxs-lookup"><span data-stu-id="0f48c-210">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="0f48c-211">Kontrollera **spoof-e-postrapporten**.</span><span class="sxs-lookup"><span data-stu-id="0f48c-211">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="0f48c-212">Du kan ofta använda den här rapporten för att visa och hantera förfalskade avsändare.</span><span class="sxs-lookup"><span data-stu-id="0f48c-212">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="0f48c-213">Information finns i [rapporten Spoof Detections](view-email-security-reports.md#spoof-detections-report).</span><span class="sxs-lookup"><span data-stu-id="0f48c-213">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="0f48c-214">Granska konfigurationen av avsändbara principramar (SPF).</span><span class="sxs-lookup"><span data-stu-id="0f48c-214">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="0f48c-215">En snabb introduktion till SPF och snabbt konfigurera den finns [i Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="0f48c-215">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="0f48c-216">För att få en djupare förståelse av hur Office 365 använder SPF, eller om du vill veta hur du felsöker eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing (Så här använder Office 365 SPF för att förhindra förfalskning)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="0f48c-216">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="0f48c-217">Granska konfigurationen av identifierade e-postmeddelanden (DomainKeys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="0f48c-217">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="0f48c-218">Du bör använda DKIM utöver SPF och DMARC för att förhindra att angripare skickar meddelanden som ser ut som om de kommer från domänen.</span><span class="sxs-lookup"><span data-stu-id="0f48c-218">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="0f48c-219">Med DKIM kan du lägga till en digital signatur i e-postmeddelanden i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="0f48c-219">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="0f48c-220">Information finns i [Använda DKIM för att validera utgående e-post som skickas från din anpassade domän i Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="0f48c-220">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="0f48c-221">Granska konfigurationen för domänbaserad meddelandeautentisering, rapportering och överensstämmelse (DMARC).</span><span class="sxs-lookup"><span data-stu-id="0f48c-221">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="0f48c-222">Implementering av DMARC med SPF och DKIM ger ytterligare skydd mot förfalsknings- och nätfiske-e-post.</span><span class="sxs-lookup"><span data-stu-id="0f48c-222">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="0f48c-223">DMARC gör så att mottagande e-postsystem kan bestämma vad som ska göras med meddelanden som skickats från din domän som misslyckas i SPF- eller DKIM-kontroller.</span><span class="sxs-lookup"><span data-stu-id="0f48c-223">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="0f48c-224">Information finns i [Använda DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="0f48c-224">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>