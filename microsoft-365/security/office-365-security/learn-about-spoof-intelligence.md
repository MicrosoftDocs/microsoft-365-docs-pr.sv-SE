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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om förfalskningsinformation i Exchange Online Protection (EOP), där du kan tillåta eller blockera specifika förfalskningsavsändare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 55a744cf2d226e72e8d84f6eb125f2baf9b9d3a0
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167269"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="f9c90-103">Konfigurera förfalskningsinformation i EOP</span><span class="sxs-lookup"><span data-stu-id="f9c90-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f9c90-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="f9c90-104">**Applies to**</span></span>
- [<span data-ttu-id="f9c90-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f9c90-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="f9c90-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="f9c90-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="f9c90-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9c90-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f9c90-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående Exchange Online Protection (EOP) utan Exchange Online-postlådor skyddas inkommande e-postmeddelanden automatiskt mot förfalskning av EOP från och med oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="f9c90-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="f9c90-109">EOP använder förfalskningsinformation som en del av organisationens totala skydd mot nätfiske.</span><span class="sxs-lookup"><span data-stu-id="f9c90-109">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="f9c90-110">Mer information finns i [Förfalskningsskydd i EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f9c90-110">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="f9c90-111">När en avsändare förfalskning en e-postadress, de verkar vara en användare i en av organisationens domäner eller en användare i en extern domän som skickar e-post till din organisation.</span><span class="sxs-lookup"><span data-stu-id="f9c90-111">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="f9c90-112">Attacker som kapar avsändare för att skicka skräppost eller nätfiske måste blockeras.</span><span class="sxs-lookup"><span data-stu-id="f9c90-112">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="f9c90-113">Men det finns situationer där legitima avsändare förfalskning.</span><span class="sxs-lookup"><span data-stu-id="f9c90-113">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="f9c90-114">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f9c90-114">For example:</span></span>

- <span data-ttu-id="f9c90-115">Legitima scenarier för förfalskning av interna domäner:</span><span class="sxs-lookup"><span data-stu-id="f9c90-115">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="f9c90-116">Avsändare från tredje part använder din domän för att skicka massutskick till dina egna anställda för företags omröstningar.</span><span class="sxs-lookup"><span data-stu-id="f9c90-116">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="f9c90-117">Ett externt företag genererar och skickar reklam- eller produktuppdateringar åt dig.</span><span class="sxs-lookup"><span data-stu-id="f9c90-117">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="f9c90-118">En assistent behöver regelbundet skicka e-post till en annan person i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f9c90-118">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="f9c90-119">Ett internt program skickar e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="f9c90-119">An internal application sends email notifications.</span></span>

- <span data-ttu-id="f9c90-120">Legitima scenarier för förfalskning av externa domäner:</span><span class="sxs-lookup"><span data-stu-id="f9c90-120">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="f9c90-121">Avsändaren finns på en distributionslista (kallas även diskussionslista) och distributionslistan vidarebefordrar e-post från den ursprungliga avsändaren till alla deltagare på distributionslistan.</span><span class="sxs-lookup"><span data-stu-id="f9c90-121">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="f9c90-122">Ett externt företag skickar e-post åt ett annat företag (till exempel en automatiserad rapport eller ett företag med programvara som tjänst).</span><span class="sxs-lookup"><span data-stu-id="f9c90-122">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="f9c90-123">Med standardprincipen för förfalskningsinformation, och specifikt standardprincipen för förfalskning, ser du till att förfalskning som skickas av legitima avsändare inte håller sig i EOP-skräppostfilter eller externa e-postsystem, samtidigt som dina användare skyddas mot skräppost- eller nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="f9c90-123">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="f9c90-124">Du kan hantera förfalskningsinformation i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="f9c90-124">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f9c90-125">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="f9c90-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f9c90-126">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f9c90-126">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f9c90-127">Om du vill gå direkt till **Inställningar för skräppostskydd** använder du <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="f9c90-127">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="f9c90-128">Om du vill gå direkt **till sidan mot nätfiske** använder du <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="f9c90-128">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="f9c90-129">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f9c90-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f9c90-130">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f9c90-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f9c90-131">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="f9c90-131">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f9c90-132">Om du vill ändra förfalskningsprincipen eller aktivera eller inaktivera förfalskningsinformation  måste du vara medlem i rollgrupperna Organisationshantering eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="f9c90-132">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f9c90-133">För skrivskyddade åtkomst till förfalskningsinformationsprincipen måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="f9c90-133">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f9c90-134">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f9c90-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="f9c90-135">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="f9c90-135">**Notes**:</span></span>

  - <span data-ttu-id="f9c90-136">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9c90-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f9c90-137">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="f9c90-137">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="f9c90-138">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="f9c90-138">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="f9c90-139">Vi rekommenderar inställningar för förfalskningsinformation i EOP:s standardinställningar [för skydd mot nätfiske.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="f9c90-139">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="f9c90-140">Använd Säkerhets- & Efterlevnadscenter för att hantera förfalskningsavsändare</span><span class="sxs-lookup"><span data-stu-id="f9c90-140">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="f9c90-141">Om du har en Microsoft 365 Enterprise, E5-prenumeration eller har köpt ett tillägg till Microsoft Defender för Office 365 separat kan du också hantera avsändare som förfalskning av din domän via [Spoof](walkthrough-spoof-intelligence-insight.md)Intelligence-insikten.</span><span class="sxs-lookup"><span data-stu-id="f9c90-141">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="f9c90-142">I Säkerhets- och efterlevnadscenter går du till **Hothantering** \> **Princip** \> **Skräppostskydd**.</span><span class="sxs-lookup"><span data-stu-id="f9c90-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="f9c90-143">På **inställningssidan Skydd mot skräppost klickar** du på ikonen Expandera för att expandera ![ ](../../media/scc-expand-icon.png) **Spoof Intelligence-principen.**</span><span class="sxs-lookup"><span data-stu-id="f9c90-143">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Välj förfalskningsinformationsprincipen](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="f9c90-145">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="f9c90-145">Make one of the following selections:</span></span>

   - <span data-ttu-id="f9c90-146">**Granska nya avsändare**</span><span class="sxs-lookup"><span data-stu-id="f9c90-146">**Review new senders**</span></span>
   - <span data-ttu-id="f9c90-147">**Visa avsändare som jag redan har granskat**</span><span class="sxs-lookup"><span data-stu-id="f9c90-147">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="f9c90-148">I **Bestäm om dessa avsändare får** kapa användarnas utfällbar lista som visas väljer du någon av följande flikar:</span><span class="sxs-lookup"><span data-stu-id="f9c90-148">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="f9c90-149">**Dina domäner:** Avsändarna förfalskning av användare i dina interna domäner.</span><span class="sxs-lookup"><span data-stu-id="f9c90-149">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="f9c90-150">**Externa domäner:** Avsändarna förfalskning av användare i externa domäner.</span><span class="sxs-lookup"><span data-stu-id="f9c90-150">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="f9c90-151">Klicka ![ på ikonen Expandera i kolumnen ](../../media/scc-expand-icon.png) **Tillåts som förfalskning?**</span><span class="sxs-lookup"><span data-stu-id="f9c90-151">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="f9c90-152">Välj **Ja** om du vill tillåta en förfalskning, eller välj **Nej** för att markera meddelandet som kapat.</span><span class="sxs-lookup"><span data-stu-id="f9c90-152">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="f9c90-153">Åtgärden styrs av standardprincipen för skydd mot nätfiske eller anpassade principer för nätfiske (standardvärdet är Flytta meddelandet till mappen **Skräppost).**</span><span class="sxs-lookup"><span data-stu-id="f9c90-153">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="f9c90-154">Mer information finns i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="f9c90-154">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Skärmbild som visar de utfällda avsändarna och om avsändaren tillåts att kapa](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="f9c90-156">Kolumnerna och värdena som visas förklaras i följande lista:</span><span class="sxs-lookup"><span data-stu-id="f9c90-156">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="f9c90-157">**Förfalskningsanvändare**: Användarkontot som kapas.</span><span class="sxs-lookup"><span data-stu-id="f9c90-157">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="f9c90-158">Det här är meddelandets avsändare i från-adressen (kallas även adressen) som `5322.From` visas i e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="f9c90-158">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="f9c90-159">Adressens giltighet kontrolleras inte av SPF.</span><span class="sxs-lookup"><span data-stu-id="f9c90-159">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="f9c90-160">På fliken **Dina domäner** innehåller värdet en enda e-postadress, eller om käll-e-postservern förfalskning av flera användarkonton, innehåller den Fler **än en.**</span><span class="sxs-lookup"><span data-stu-id="f9c90-160">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="f9c90-161">På fliken **Externa domäner** innehåller värdet domänen för den förfalskningsanvändaren, inte den fullständiga e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="f9c90-161">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="f9c90-162">**Skicka infrastruktur:** Den domän som finns i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress.</span><span class="sxs-lookup"><span data-stu-id="f9c90-162">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="f9c90-163">Om käll-IP-adressen inte har någon PTR-post identifieras den avsändande infrastrukturen som \<source IP\> /24 (t.ex. 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="f9c90-163">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="f9c90-164">Mer information om meddelandekällor och meddelandeavsändare finns i en översikt över standarder för [e-postmeddelanden.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="f9c90-164">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="f9c90-165">**# av meddelanden:** Antalet meddelanden från den avsändande infrastrukturen till organisationen som innehåller angivna förfalskningsavsändare eller avsändare inom de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f9c90-165">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="f9c90-166">**# av klagomål från användare:** Klagomål från användare mot denna avsändare inom de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="f9c90-166">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="f9c90-167">Klagomål är vanligtvis i form av skräppost som skickas till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f9c90-167">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="f9c90-168">**Autentiseringsresultat:** Ett av följande värden:</span><span class="sxs-lookup"><span data-stu-id="f9c90-168">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="f9c90-169">**Godkänd:** Avsändaren har skickat e-postautentiseringskontroller (SPF eller DKIM).</span><span class="sxs-lookup"><span data-stu-id="f9c90-169">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="f9c90-170">**Misslyckades:** Det gick inte att autentisera EOP-avsändare med avsändaren.</span><span class="sxs-lookup"><span data-stu-id="f9c90-170">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="f9c90-171">**Okänt:** Resultatet av de här kontrollerna är inte känt.</span><span class="sxs-lookup"><span data-stu-id="f9c90-171">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="f9c90-172">**Beslut som angetts** av : Visar vem som fastställt om den avsändande infrastrukturen tillåts förfalskning av användaren:</span><span class="sxs-lookup"><span data-stu-id="f9c90-172">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="f9c90-173">**Spoof Intelligence-princip** (automatisk)</span><span class="sxs-lookup"><span data-stu-id="f9c90-173">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="f9c90-174">**Administratör** (manuellt)</span><span class="sxs-lookup"><span data-stu-id="f9c90-174">**Admin** (manual)</span></span>

   - <span data-ttu-id="f9c90-175">**Sågs** senast: Det senaste datumet när ett meddelande togs emot från den avsändande infrastrukturen som innehåller den kapade användaren.</span><span class="sxs-lookup"><span data-stu-id="f9c90-175">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="f9c90-176">**Tillåtet att kapa?**: Värdena som visas här är:</span><span class="sxs-lookup"><span data-stu-id="f9c90-176">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="f9c90-177">**Ja:** Meddelanden från kombination av förfalskningsanvändare och infrastruktur för att skicka meddelanden tillåts och hanteras inte som falska e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="f9c90-177">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="f9c90-178">**Nej:** Meddelanden från en kombination av kapad användare och infrastruktur som skickas markeras som falska.</span><span class="sxs-lookup"><span data-stu-id="f9c90-178">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="f9c90-179">Åtgärden styrs av standardprincipen för skydd mot nätfiske eller anpassade principer för nätfiske (standardvärdet är Flytta meddelandet till mappen **Skräppost).**</span><span class="sxs-lookup"><span data-stu-id="f9c90-179">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="f9c90-180">Mer information finns i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f9c90-180">See the next section for more information.</span></span>

     - <span data-ttu-id="f9c90-181">**Vissa användare** **(endast fliken** Dina domäner): En avsändande infrastruktur förfalskning av flera användare, där vissa förfalskningsanvändare tillåts och andra inte.</span><span class="sxs-lookup"><span data-stu-id="f9c90-181">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="f9c90-182">Använd fliken **Detaljerad** för att se de specifika adresserna.</span><span class="sxs-lookup"><span data-stu-id="f9c90-182">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="f9c90-183">Klicka på Spara längst ned på **sidan.**</span><span class="sxs-lookup"><span data-stu-id="f9c90-183">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="f9c90-184">Använda PowerShell för att hantera falska avsändare</span><span class="sxs-lookup"><span data-stu-id="f9c90-184">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="f9c90-185">Använd följande syntax för att visa tillåtna och blockerade avsändare i förfalskningsinformation:</span><span class="sxs-lookup"><span data-stu-id="f9c90-185">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="f9c90-186">Det här exemplet returnerar detaljerad information om alla avsändare som är tillåtna att kapa användare i domänerna.</span><span class="sxs-lookup"><span data-stu-id="f9c90-186">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="f9c90-187">Detaljerad information om syntax och parametrar finns i [Hämta-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="f9c90-187">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="f9c90-188">Så här konfigurerar du tillåtna och blockerade avsändare i förfalskningsinformation:</span><span class="sxs-lookup"><span data-stu-id="f9c90-188">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="f9c90-189">Spara den aktuella listan med identifierade förfalskningsavsändare genom att skriva utdata från cmdleten **Get-PhishFilterPolicy** till en CSV-fil:</span><span class="sxs-lookup"><span data-stu-id="f9c90-189">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="f9c90-190">Redigera CSV-filen för att lägga till eller ändra värdena **för förfalskning** (e-postadress) och **AllowedToSpoof** (Ja eller No).</span><span class="sxs-lookup"><span data-stu-id="f9c90-190">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="f9c90-191">Spara filen, läs filen och lagra innehållet som en variabel med `$UpdateSpoofedSenders` namnet:</span><span class="sxs-lookup"><span data-stu-id="f9c90-191">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="f9c90-192">Använd `$UpdateSpoofedSenders` variabeln för att konfigurera förfalskningsinformationsprincipen:</span><span class="sxs-lookup"><span data-stu-id="f9c90-192">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="f9c90-193">Detaljerad information om syntax och parametrar finns [i Set-PhishFilterPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)</span><span class="sxs-lookup"><span data-stu-id="f9c90-193">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="f9c90-194">Använda Säkerhets- & Center för att konfigurera förfalskningsinformation</span><span class="sxs-lookup"><span data-stu-id="f9c90-194">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="f9c90-195">Konfigurationsalternativen för förfalskningsinformation beskrivs i inställningarna [för förfalskning i principer för skydd mot nätfiske.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="f9c90-195">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="f9c90-196">Du kan konfigurera inställningar för förfalskningsinformation i standardprincipen för skydd mot nätfiske och även i anpassade principer.</span><span class="sxs-lookup"><span data-stu-id="f9c90-196">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="f9c90-197">Anvisningar baserade på din prenumeration finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="f9c90-197">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="f9c90-198">[Konfigurera principer för skydd mot nätfiske i EOP.](configure-anti-phishing-policies-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f9c90-198">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="f9c90-199">[Konfigurera principer för skydd mot nätfiske i Microsoft Defender för Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f9c90-199">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="f9c90-200">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="f9c90-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="f9c90-201">Använd något av följande steg för att verifiera att du har konfigurerat förfalskningsinformation med avsändare som tillåts och inte får kapa, och att du har konfigurerat inställningarna för förfalskningsinformation:</span><span class="sxs-lookup"><span data-stu-id="f9c90-201">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="f9c90-202">I Säkerhets- &  Efterlevnadscenter går du till Policy för skydd mot skräppost och expanderar \>  \> Spoof **Intelligence-principen.** Välj Visa avsändare som jag redan har granskat genom att välja fliken Dina domäner eller externa domäner och verifiera värdet Förfalskning? för \>  \>  \> avsändaren.   </span><span class="sxs-lookup"><span data-stu-id="f9c90-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="f9c90-203">I PowerShell kör du följande kommandon för att visa avsändare som tillåts och inte får kapa:</span><span class="sxs-lookup"><span data-stu-id="f9c90-203">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="f9c90-204">Kör följande kommando i PowerShell för att exportera listan över alla falska avsändare till en CSV-fil:</span><span class="sxs-lookup"><span data-stu-id="f9c90-204">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="f9c90-205">I Säkerhets- & Efterlevnadscenter  går du till Policy för hantering av hot mot nätfiske eller ATP – skydd mot nätfiske och \>  \>  gör något av följande:  </span><span class="sxs-lookup"><span data-stu-id="f9c90-205">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="f9c90-206">Välj en princip i listan.</span><span class="sxs-lookup"><span data-stu-id="f9c90-206">Select a policy from the list.</span></span> <span data-ttu-id="f9c90-207">Kontrollera värdena i förfalskningsavsnittet i den **utfällo som** visas.</span><span class="sxs-lookup"><span data-stu-id="f9c90-207">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="f9c90-208">Klicka **på Standardprincip.**</span><span class="sxs-lookup"><span data-stu-id="f9c90-208">Click **Default policy**.</span></span> <span data-ttu-id="f9c90-209">Kontrollera värdena i förfalskningsavsnittet i den **utfällo som** visas.</span><span class="sxs-lookup"><span data-stu-id="f9c90-209">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="f9c90-210">I Exchange Online PowerShell ersätter du med Office365 AntiPhish Default eller namnet på en anpassad princip och kör följande kommando för \<Name\> att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="f9c90-210">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="f9c90-211">Andra sätt att hantera förfalskning och nätfiske</span><span class="sxs-lookup"><span data-stu-id="f9c90-211">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="f9c90-212">Var flitig om förfalskning och nätfiskeskydd.</span><span class="sxs-lookup"><span data-stu-id="f9c90-212">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="f9c90-213">Här är relaterade sätt att kontrollera avsändare som förfalskning av din domän och förhindra att de skadar organisationen:</span><span class="sxs-lookup"><span data-stu-id="f9c90-213">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="f9c90-214">Kontrollera **förfalskningsrapporten.**</span><span class="sxs-lookup"><span data-stu-id="f9c90-214">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="f9c90-215">Du kan använda den här rapporten ofta för att visa och hjälpa till att hantera falska avsändare.</span><span class="sxs-lookup"><span data-stu-id="f9c90-215">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="f9c90-216">Mer information finns i [rapporten Identifiering av förfalskning.](view-email-security-reports.md#spoof-detections-report)</span><span class="sxs-lookup"><span data-stu-id="f9c90-216">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="f9c90-217">Granska SPF-konfigurationen (Sender Policy Framework).</span><span class="sxs-lookup"><span data-stu-id="f9c90-217">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="f9c90-218">En introduktion till SPF finns i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt.</span><span class="sxs-lookup"><span data-stu-id="f9c90-218">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="f9c90-219">För att få en djupare förståelse av hur Office 365 använder SPF, eller om du vill veta hur du felsöker eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing (Så här använder Office 365 SPF för att förhindra förfalskning)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="f9c90-219">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="f9c90-220">Granska konfigurationen av DKIM (DomainKeys Identified Mail).</span><span class="sxs-lookup"><span data-stu-id="f9c90-220">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="f9c90-221">Du bör använda DKIM utöver SPF och DMARC för att förhindra attacker från att skicka meddelanden som ser ut som de kommer från din domän.</span><span class="sxs-lookup"><span data-stu-id="f9c90-221">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="f9c90-222">Med DKIM kan du lägga till en digital signatur i e-postmeddelanden i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="f9c90-222">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="f9c90-223">Mer information finns i Använda [DKIM för att verifiera utgående e-post som skickas från din anpassade domän i Office 365.](use-dkim-to-validate-outbound-email.md)</span><span class="sxs-lookup"><span data-stu-id="f9c90-223">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="f9c90-224">Granska din domänbaserade konfiguration av meddelandeautentisering, rapportering och överensstämmelse (DMARC).</span><span class="sxs-lookup"><span data-stu-id="f9c90-224">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="f9c90-225">Implementering av DMARC med SPF och DKIM ger ytterligare skydd mot förfalsknings- och nätfiske-e-post.</span><span class="sxs-lookup"><span data-stu-id="f9c90-225">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="f9c90-226">DMARC gör så att mottagande e-postsystem kan bestämma vad som ska göras med meddelanden som skickats från din domän som misslyckas i SPF- eller DKIM-kontroller.</span><span class="sxs-lookup"><span data-stu-id="f9c90-226">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="f9c90-227">Mer information finns i Använda [DMARC för att verifiera e-post i Office 365.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="f9c90-227">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
