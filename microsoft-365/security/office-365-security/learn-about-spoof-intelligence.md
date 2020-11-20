---
title: Konfigurera förfalskningsinformation
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om förfalsknings intelligens i Exchange Online Protection (EOP), där du kan tillåta eller blockera specifika avsändare.
ms.openlocfilehash: 62964550be161b16767595890872055b56586f1d
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367137"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="f25a8-103">Konfigurera förfalsknings information i EOP</span><span class="sxs-lookup"><span data-stu-id="f25a8-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f25a8-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor skyddas inkommande e-postmeddelanden automatiskt mot förfalskning genom EOP som i oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="f25a8-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="f25a8-105">EOP använder förfalsknings intelligens som en del av organisationens allmänna försvar mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f25a8-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="f25a8-106">Mer information finns i [skydd mot förfalskning i EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="f25a8-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="f25a8-107">När en avsändare får en e-postadress ser de ut som en användare i en av organisationens domäner eller en användare i en extern domän som skickar e-post till din organisation.</span><span class="sxs-lookup"><span data-stu-id="f25a8-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="f25a8-108">Angripare som är falska att skicka skräp post eller nätfiske måste blockeras.</span><span class="sxs-lookup"><span data-stu-id="f25a8-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="f25a8-109">Men det finns tillfällen då legitima avsändare är falska.</span><span class="sxs-lookup"><span data-stu-id="f25a8-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="f25a8-110">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f25a8-110">For example:</span></span>

- <span data-ttu-id="f25a8-111">Legitima scenarier för falska interna domäner:</span><span class="sxs-lookup"><span data-stu-id="f25a8-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="f25a8-112">Avsändare från tredje part använder din domän för att skicka mass utskick till dina egna anställda för företags omröstningar.</span><span class="sxs-lookup"><span data-stu-id="f25a8-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="f25a8-113">Ett externt företag genererar och skickar reklam-eller produkt uppdateringar för din räkning.</span><span class="sxs-lookup"><span data-stu-id="f25a8-113">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="f25a8-114">En assistent måste regelbundet skicka e-post till en annan person inom din organisation.</span><span class="sxs-lookup"><span data-stu-id="f25a8-114">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="f25a8-115">Ett internt program skickar e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="f25a8-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="f25a8-116">Legitima scenarier för falska externa domäner:</span><span class="sxs-lookup"><span data-stu-id="f25a8-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="f25a8-117">Avsändaren är på en distributions lista (kallas även en diskussions lista) och skickar e-post från den ursprungliga avsändaren till alla deltagare i distributions listan.</span><span class="sxs-lookup"><span data-stu-id="f25a8-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="f25a8-118">Ett externt företag skickar e-post på uppdrag av ett annat företag (till exempel en automatiserad rapport eller ett företag med program varu namn).</span><span class="sxs-lookup"><span data-stu-id="f25a8-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="f25a8-119">Förfalsknings intelligens och specifikt standard-(och endast) policy för förfalsknings intelligens säkerställer att det falska e-postmeddelandet som skickas av legitima avsändare inte kan upptäckas i EOP spam filter eller externa e-postsystem, samtidigt som användarna skyddas från skräp post eller nätfiske-attacker.</span><span class="sxs-lookup"><span data-stu-id="f25a8-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="f25a8-120">Du kan hantera förfalsknings intelligens i säkerhets & Compliance Center eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med post lådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="f25a8-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f25a8-121">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="f25a8-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f25a8-122">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f25a8-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f25a8-123">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="f25a8-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="f25a8-124">För att gå direkt till **nätfiske-** sidan, Använd <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="f25a8-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="f25a8-125">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f25a8-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f25a8-126">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f25a8-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f25a8-127">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="f25a8-127">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="f25a8-128">Om du vill ändra policyn för förfalsknings information eller aktivera förfalsknings intelligens måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="f25a8-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f25a8-129">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f25a8-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f25a8-130">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f25a8-130">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="f25a8-131">Om du vill ha skrivskyddad åtkomst till policyn för förfalsknings intelligens måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="f25a8-131">For read-only access to the spoof intelligence policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="f25a8-132">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f25a8-132">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="f25a8-133">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="f25a8-133">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="f25a8-134">För våra rekommenderade inställningar för Spoof-intelligens, se [EOP standardinställningar för skydd mot nätfiske](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="f25a8-134">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="f25a8-135">Hantera falska avsändare genom att använda säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f25a8-135">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="f25a8-136">Om du har ett Microsoft 365 Enterprise, E5-abonnemang eller har separat inköpt ett tillägg för Microsoft Defender för Office 365 kan du även hantera avsändare som har falska din domän via [förfalsknings information](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="f25a8-136">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="f25a8-137">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f25a8-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f25a8-138">På sidan **Inställningar för skräp post** klickar du på ![ ikonen Expandera ](../../media/scc-expand-icon.png) för att utöka **policyn för förfalsknings information**.</span><span class="sxs-lookup"><span data-stu-id="f25a8-138">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Välj policy för förfalsknings intelligens](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="f25a8-140">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="f25a8-140">Make one of the following selections:</span></span>

   - <span data-ttu-id="f25a8-141">**Granska nya avsändare**</span><span class="sxs-lookup"><span data-stu-id="f25a8-141">**Review new senders**</span></span>
   - <span data-ttu-id="f25a8-142">**Visa mig-avsändare som jag redan har granskat**</span><span class="sxs-lookup"><span data-stu-id="f25a8-142">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="f25a8-143">I **Bestäm om dessa avsändare får använda falska användare** som visas, väljer du någon av följande flikar:</span><span class="sxs-lookup"><span data-stu-id="f25a8-143">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="f25a8-144">**Domänerna**: avsändare förfalskningar användare i de interna domänerna.</span><span class="sxs-lookup"><span data-stu-id="f25a8-144">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="f25a8-145">**Externa domäner**: avsändare falska användare i externa domäner.</span><span class="sxs-lookup"><span data-stu-id="f25a8-145">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="f25a8-146">Klicka på ![ ikonen Expandera ](../../media/scc-expand-icon.png) i kolumnen **tillåts till förfalskning?** .</span><span class="sxs-lookup"><span data-stu-id="f25a8-146">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="f25a8-147">Välj **Ja** om du vill tillåta falska avsändare eller Välj **Nej** om du vill markera meddelandet som falsk.</span><span class="sxs-lookup"><span data-stu-id="f25a8-147">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="f25a8-148">Åtgärden styrs av standard policyn för skydd mot nätfiske eller anpassade anti-phishing-principer (Standardvärdet är **Flytta meddelandet till mappen skräp post**).</span><span class="sxs-lookup"><span data-stu-id="f25a8-148">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="f25a8-149">Mer information finns i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f25a8-149">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Skärm bild som visar utfällda falska avsändare och om avsändaren är tillåten för förfalskning](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="f25a8-151">Kolumnerna och värdena som visas förklaras i följande lista:</span><span class="sxs-lookup"><span data-stu-id="f25a8-151">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="f25a8-152">**Falsk användare**: det användar konto som används för falskas.</span><span class="sxs-lookup"><span data-stu-id="f25a8-152">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="f25a8-153">Det här är meddelandets avsändare i den från-adress (kallas även `5322.From` adress) som visas i e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="f25a8-153">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="f25a8-154">Giltigheten för denna adress kontrol leras inte av SPF.</span><span class="sxs-lookup"><span data-stu-id="f25a8-154">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="f25a8-155">På fliken **dina domäner** innehåller värdet en enda e-postadress, eller om käll-e-postservern är falsk för flera användar konton innehåller den **fler än en**.</span><span class="sxs-lookup"><span data-stu-id="f25a8-155">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="f25a8-156">På fliken **externa domäner** innehåller värdet för domänen med falsk användare, inte den fullständiga e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="f25a8-156">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="f25a8-157">**Skicka infrastruktur**: domänen hittades i en omvänd DNS-sökning (PTR-post) av käll-e-postserverns IP-adress, eller IP-adressen om källan inte har någon PTR-post.</span><span class="sxs-lookup"><span data-stu-id="f25a8-157">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="f25a8-158">Mer information om meddelande källor och meddelande avsändare finns i [Översikt över e-poststandarder](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="f25a8-158">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="f25a8-159">antal **meddelanden**: antalet meddelanden från infrastrukturen för sändning till din organisation som innehåller angivna avsändare eller avsändare inom de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f25a8-159">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="f25a8-160">**antal användare klagomål**: klagomål som lämnats av användarna mot denna avsändare inom de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f25a8-160">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="f25a8-161">Klagomål är vanligt vis i form av skräp post försändelser till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f25a8-161">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="f25a8-162">**Resultat**: ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="f25a8-162">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="f25a8-163">**Lyckades**: avsändaren skickade e-postkontroller (SPF eller DKIM).</span><span class="sxs-lookup"><span data-stu-id="f25a8-163">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="f25a8-164">**Misslyckades**: avsändaren misslyckades EOP.</span><span class="sxs-lookup"><span data-stu-id="f25a8-164">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="f25a8-165">**Okänt**: resultatet av dessa kontroller är inte känt.</span><span class="sxs-lookup"><span data-stu-id="f25a8-165">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="f25a8-166">**Beslut inställt av**: visar vilka som har fastställt om den sändande infrastrukturen har tillstånd att skicka falska användare:</span><span class="sxs-lookup"><span data-stu-id="f25a8-166">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="f25a8-167">**Policy för förfalsknings information** (automatiskt)</span><span class="sxs-lookup"><span data-stu-id="f25a8-167">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="f25a8-168">**Administratör** (manuell)</span><span class="sxs-lookup"><span data-stu-id="f25a8-168">**Admin** (manual)</span></span>

   - <span data-ttu-id="f25a8-169">**Senast sedd**: det sista datum då ett meddelande togs emot från den sändande infrastrukturen som innehåller den falskade användaren.</span><span class="sxs-lookup"><span data-stu-id="f25a8-169">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="f25a8-170">Har du **tillstånd för falska identiteter?**: de värden som visas här är:</span><span class="sxs-lookup"><span data-stu-id="f25a8-170">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="f25a8-171">**Ja**: meddelanden från en kombination av falsk användare och överföring av infrastrukturen tillåts och behandlas inte som falsk e-post.</span><span class="sxs-lookup"><span data-stu-id="f25a8-171">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="f25a8-172">**Nej**: meddelanden från en kombination av falsk användare och överföring av infrastrukturen markeras som falska.</span><span class="sxs-lookup"><span data-stu-id="f25a8-172">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="f25a8-173">Åtgärden styrs av standard policyn för skydd mot nätfiske eller anpassade anti-phishing-principer (Standardvärdet är **Flytta meddelandet till mappen skräp post**).</span><span class="sxs-lookup"><span data-stu-id="f25a8-173">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="f25a8-174">Se nästa avsnitt för mer information.</span><span class="sxs-lookup"><span data-stu-id="f25a8-174">See the next section for more information.</span></span>

     - <span data-ttu-id="f25a8-175">**Vissa användare** (endast **din domän** -flik): en annan infrastruktur är falsk för flera användare, där vissa falska användare är tillåtna och andra inte är det.</span><span class="sxs-lookup"><span data-stu-id="f25a8-175">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="f25a8-176">Använd den **detaljerade** fliken för att visa specifika adresser.</span><span class="sxs-lookup"><span data-stu-id="f25a8-176">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="f25a8-177">Klicka på **Spara** längst ned på sidan.</span><span class="sxs-lookup"><span data-stu-id="f25a8-177">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="f25a8-178">Använda PowerShell för att hantera falska avsändare</span><span class="sxs-lookup"><span data-stu-id="f25a8-178">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="f25a8-179">Använd följande syntax för att Visa tillåtna och spärrade avsändare i Spoof-intelligens:</span><span class="sxs-lookup"><span data-stu-id="f25a8-179">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="f25a8-180">I det här exemplet returneras detaljerad information om alla avsändare som får falska användare i dina domäner.</span><span class="sxs-lookup"><span data-stu-id="f25a8-180">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="f25a8-181">Detaljerad information om syntax och parametrar finns i [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f25a8-181">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="f25a8-182">Följ de här stegen om du vill konfigurera tillåtna och spärrade avsändare i Spoof-intelligens:</span><span class="sxs-lookup"><span data-stu-id="f25a8-182">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="f25a8-183">Avbilda den aktuella listan med identifierade avsändare genom att skriva utdata från cmdleten **Get-PhishFilterPolicy** till en CSV-fil:</span><span class="sxs-lookup"><span data-stu-id="f25a8-183">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="f25a8-184">Redigera CSV-filen för att lägga till eller ändra värdena för **SpoofedUser** (e-postadress) och **AllowedToSpoof** (Ja eller Nej).</span><span class="sxs-lookup"><span data-stu-id="f25a8-184">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="f25a8-185">Spara filen, Läs filen och lagra innehållet som en variabel som heter `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="f25a8-185">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="f25a8-186">Använd `$UpdateSpoofedSenders` variabeln för att konfigurera policyn för förfalsknings intelligens:</span><span class="sxs-lookup"><span data-stu-id="f25a8-186">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="f25a8-187">Detaljerad information om syntax och parametrar finns i [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="f25a8-187">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="f25a8-188">Använda säkerhets & Compliance Center för att konfigurera förfalsknings intelligens</span><span class="sxs-lookup"><span data-stu-id="f25a8-188">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="f25a8-189">Konfigurations alternativen för förfalsknings intelligens beskrivs i [Inställningar för förfalskningar i principer för nätfiske](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f25a8-189">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="f25a8-190">Du kan konfigurera inställningar för förfalsknings information i standard principen för Antinätfiske och även i anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="f25a8-190">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="f25a8-191">Anvisningar som baseras på ditt abonnemang finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="f25a8-191">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="f25a8-192">[Konfigurera AntiPhishing-principer i EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="f25a8-192">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="f25a8-193">[Konfigurera AntiPhishing-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f25a8-193">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f25a8-194">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="f25a8-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="f25a8-195">Gör så här för att kontrol lera att du har konfigurerat falsk intelligens med avsändare som är tillåtna och inte har tillåtelse att få åtkomst till falska inställningar:</span><span class="sxs-lookup"><span data-stu-id="f25a8-195">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="f25a8-196">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **anti-spam** \> expandera **policy för förfalsknings information** \> Markera **Visa mig avsändare som jag redan har granskat** \> Välj fliken **dina domäner** eller **externa domäner** och kontrol lera om det är **tillåtet att falska** för avsändaren.</span><span class="sxs-lookup"><span data-stu-id="f25a8-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="f25a8-197">I PowerShell kör du följande kommandon för att Visa avsändare som är tillåtna och inte tillåtna för falska användare:</span><span class="sxs-lookup"><span data-stu-id="f25a8-197">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="f25a8-198">I PowerShell kör du följande kommando för att exportera listan med alla falska avsändare till en CSV-fil:</span><span class="sxs-lookup"><span data-stu-id="f25a8-198">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="f25a8-199">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **mot nätfiske** eller **ATP-nätfiske** och gör något av följande:  </span><span class="sxs-lookup"><span data-stu-id="f25a8-199">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="f25a8-200">Välj en princip i listan.</span><span class="sxs-lookup"><span data-stu-id="f25a8-200">Select a policy from the list.</span></span> <span data-ttu-id="f25a8-201">I den utfällbara filen som visas kontrollerar du värdena i avsnittet **Spoof** .</span><span class="sxs-lookup"><span data-stu-id="f25a8-201">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="f25a8-202">Klicka på **standard policy**.</span><span class="sxs-lookup"><span data-stu-id="f25a8-202">Click **Default policy**.</span></span> <span data-ttu-id="f25a8-203">I den utfällbara filen som visas kontrollerar du värdena i avsnittet **Spoof** .</span><span class="sxs-lookup"><span data-stu-id="f25a8-203">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="f25a8-204">I Exchange Online PowerShell ersätter \<Name\> du med Office365 AntiPhish default eller namnet på en anpassad princip och kör följande kommando för att kontrol lera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="f25a8-204">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="f25a8-205">Andra sätt att hantera förfalskningar och nätfiske</span><span class="sxs-lookup"><span data-stu-id="f25a8-205">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="f25a8-206">Var noggrann om förfalskning och nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f25a8-206">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="f25a8-207">Här är relaterade sätt att kontrol lera avsändare som falsk din domän och hjälpa till att förhindra att den inte skadar organisationen:</span><span class="sxs-lookup"><span data-stu-id="f25a8-207">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="f25a8-208">Kontrol lera **rapporten med falsk e-post**.</span><span class="sxs-lookup"><span data-stu-id="f25a8-208">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="f25a8-209">Du kan använda den här rapporten ofta för att visa och hjälpa till att hantera falska avsändare.</span><span class="sxs-lookup"><span data-stu-id="f25a8-209">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="f25a8-210">Mer information finns i [rapporten om identifieringar av förfalskningar](view-email-security-reports.md#spoof-detections-report).</span><span class="sxs-lookup"><span data-stu-id="f25a8-210">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="f25a8-211">Granska din SPF-konfiguration (avsändare Policy Framework).</span><span class="sxs-lookup"><span data-stu-id="f25a8-211">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="f25a8-212">En introduktion till SPF finns i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt.</span><span class="sxs-lookup"><span data-stu-id="f25a8-212">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="f25a8-213">För att få en djupare förståelse av hur Office 365 använder SPF, eller om du vill veta hur du felsöker eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing (Så här använder Office 365 SPF för att förhindra förfalskning)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="f25a8-213">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="f25a8-214">Granska din DomainKeys identifieras-konfiguration (DKIM).</span><span class="sxs-lookup"><span data-stu-id="f25a8-214">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="f25a8-215">Du bör använda DKIM utöver SPF och DMARC för att förhindra att angripare skickar meddelanden som ser ut som om de kommer från din domän.</span><span class="sxs-lookup"><span data-stu-id="f25a8-215">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="f25a8-216">Med DKIM kan du lägga till en digital signatur i e-postmeddelanden i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="f25a8-216">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="f25a8-217">Mer information finns i [använda DKIM för att verifiera utgående e-post som skickas från din egen domän i Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="f25a8-217">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="f25a8-218">Granska din domänbaserade meddelande identifiering, rapportering och konfiguration av ändringar (DMARC).</span><span class="sxs-lookup"><span data-stu-id="f25a8-218">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="f25a8-219">Implementering av DMARC med SPF och DKIM ger ytterligare skydd mot förfalsknings- och nätfiske-e-post.</span><span class="sxs-lookup"><span data-stu-id="f25a8-219">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="f25a8-220">DMARC gör så att mottagande e-postsystem kan bestämma vad som ska göras med meddelanden som skickats från din domän som misslyckas i SPF- eller DKIM-kontroller.</span><span class="sxs-lookup"><span data-stu-id="f25a8-220">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="f25a8-221">Mer information finns i [använda DMARC för att verifiera e-post i Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="f25a8-221">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
