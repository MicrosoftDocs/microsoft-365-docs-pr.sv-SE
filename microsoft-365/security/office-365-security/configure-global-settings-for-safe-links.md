---
title: Konfigurera globala inställningar för Valv Länkar i Defender för Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur de visar och konfigurerar globala inställningar (listan "Blockera följande URL:er" och skydd för Office 365-appar) för Valv-länkar i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 46bafd89400dfa551641c055f6f0e208c0ecd49f
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108049"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="90d80-103">Konfigurera globala inställningar för Valv Länkar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="90d80-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="90d80-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="90d80-104">**Applies to**</span></span>
- [<span data-ttu-id="90d80-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="90d80-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="90d80-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90d80-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="90d80-107">Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="90d80-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="90d80-108">Om du är hemanvändare och vill ha information om säkra länkar i Outlook kan du läsa [Mer Outlook.com-säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="90d80-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="90d80-109">Valv Länkar är en funktion i [Microsoft Defender](defender-for-office-365.md) för Office 365 som ger URL-skanning av inkommande e-postmeddelanden i e-postflödet och tidpunkten för klickverifiering av URL:er och länkar i e-postmeddelanden och på andra platser.</span><span class="sxs-lookup"><span data-stu-id="90d80-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="90d80-110">Mer information finns i artikeln [Valv i Microsoft Defender för Office 365](safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="90d80-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="90d80-111">Du konfigurerar Valv inställningar för länkar Valv principer.</span><span class="sxs-lookup"><span data-stu-id="90d80-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="90d80-112">Instruktioner finns i Konfigurera [principer Valv länkar i Microsoft Defender för Office 365.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="90d80-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="90d80-113">Men Valv länkar använder också följande globala inställningar som du konfigurerar utanför Valv själva principerna:</span><span class="sxs-lookup"><span data-stu-id="90d80-113">But, Safe Links also uses the following global settings that you configure outside of the Safe Links policies themselves:</span></span>

- <span data-ttu-id="90d80-114">Listan **Blockera följande URL:er.**</span><span class="sxs-lookup"><span data-stu-id="90d80-114">The **Block the following URLs** list.</span></span> <span data-ttu-id="90d80-115">Den här inställningen gäller för alla användare som ingår i alla aktiva Valv-länkar.</span><span class="sxs-lookup"><span data-stu-id="90d80-115">This setting applies to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="90d80-116">Mer information finns i [listan "Blockera följande URL:er" för Valv Länkar](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="90d80-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="90d80-117">Valv Länkskydd för Office 365 appar.</span><span class="sxs-lookup"><span data-stu-id="90d80-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="90d80-118">De här inställningarna gäller för alla användare i organisationen som är licensierade för Defender för Office 365, oavsett om användarna ingår i active Valv-länkar eller inte.</span><span class="sxs-lookup"><span data-stu-id="90d80-118">These settings apply to all users in the organization who are licensed for Defender for Office 365, regardless of whether the users are included in active Safe Links policies or not.</span></span> <span data-ttu-id="90d80-119">Mer information finns i inställningar [Valv länkar för appar Office 365 .](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="90d80-119">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="90d80-120">Du kan konfigurera de globala inställningarna för Valv-länkar i Microsoft 365 Defender-portalen eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online– fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Microsoft Defender för Office 365-tilläggsprenumerationer).</span><span class="sxs-lookup"><span data-stu-id="90d80-120">You can configure the global Safe Links settings in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="90d80-121">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="90d80-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="90d80-122">Det finns ingen inbyggd eller standardprincip för Valv-länkar, så du måste skapa minst en Valv-länkprincip för att listan Blockera följande URL:er ska vara aktiv. </span><span class="sxs-lookup"><span data-stu-id="90d80-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for the **Block the following URLs** list to be active.</span></span> <span data-ttu-id="90d80-123">Instruktioner finns i Konfigurera [principer Valv länkar i Microsoft Defender för Office 365.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="90d80-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="90d80-124">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="90d80-124">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="90d80-125">Om du vill gå **direkt Valv sidan** Länkar använder du <https://security.microsoft.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="90d80-125">To go directly to the **Safe Links** page, use <https://security.microsoft.com/safelinksv2>.</span></span>

- <span data-ttu-id="90d80-126">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="90d80-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="90d80-127">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="90d80-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="90d80-128">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="90d80-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="90d80-129">För att konfigurera globala inställningar Valv länkar måste du vara medlem i rollgrupperna **Organisationshantering** **eller Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="90d80-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="90d80-130">För skrivskyddade åtkomst till globala inställningar för Valv länkar måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="90d80-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="90d80-131">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="90d80-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="90d80-132">**Anteckningar**:</span><span class="sxs-lookup"><span data-stu-id="90d80-132">**Notes**:</span></span>

  - <span data-ttu-id="90d80-133">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="90d80-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="90d80-134">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="90d80-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="90d80-135">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="90d80-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="90d80-136">Våra rekommenderade värden för de globala inställningarna för Valv finns i inställningar [Valv Länkar.](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="90d80-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="90d80-137">Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="90d80-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="90d80-138">[Nya funktioner läggs kontinuerligt till i Microsoft Defender för Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="90d80-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="90d80-139">När nya funktioner läggs till kan du behöva justera dina befintliga principer Valv Länkar.</span><span class="sxs-lookup"><span data-stu-id="90d80-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="90d80-140">Konfigurera listan "Blockera följande URL:er" i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="90d80-140">Configure the "Block the following URLs" list in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="90d80-141">I **listan Blockera följande URL:er** identifieras de länkar som alltid ska blockeras av Valv i program som stöds.</span><span class="sxs-lookup"><span data-stu-id="90d80-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="90d80-142">Mer information finns i [listan "Blockera följande URL:er" för Valv Länkar.](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="90d80-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="90d80-143">I Microsoft 365 Defender-portalen går du till Avsnittet **Principer &** e&-post och samarbete & Principer \>  \>  \>  för hot \> **Valv.**</span><span class="sxs-lookup"><span data-stu-id="90d80-143">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="90d80-144">På sidan **Valv klickar** du på **Globala inställningar**.</span><span class="sxs-lookup"><span data-stu-id="90d80-144">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="90d80-145">I den **Valv princip för** länkar för organisationen som visas går du till rutan Blockera följande **URL:er.**</span><span class="sxs-lookup"><span data-stu-id="90d80-145">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="90d80-146">Konfigurera en eller flera poster enligt beskrivningen i [Postsyntax för listan "Blockera följande URL:er".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="90d80-146">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="90d80-147">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="90d80-147">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="90d80-148">Konfigurera listan "Blockera följande URL:er" i PowerShell</span><span class="sxs-lookup"><span data-stu-id="90d80-148">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="90d80-149">Mer information om postsyntaxen finns [i Postsyntax för listan "Blockera följande URL:er".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="90d80-149">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="90d80-150">Du kan använda cmdleten **Get-AtpPolicyForO365** till att visa befintliga poster i egenskapen _BlockURLs._</span><span class="sxs-lookup"><span data-stu-id="90d80-150">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="90d80-151">Om du vill lägga till värden som ersätter befintliga poster använder du följande syntax i Exchange Online PowerShell Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="90d80-151">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="90d80-152">I det här exemplet läggs följande poster till i listan:</span><span class="sxs-lookup"><span data-stu-id="90d80-152">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="90d80-153">Blockera domän, underdomäner och sökvägar för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="90d80-153">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="90d80-154">Blockera efterforskningar för underdomäner, men inte den överordnade domänen eller andra underdomäner i tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="90d80-154">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="90d80-155">Om du vill lägga till eller ta bort värden utan att påverka andra befintliga poster använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="90d80-155">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="90d80-156">I det här exemplet läggs en ny adatum.com posten till och posten tas bort för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="90d80-156">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="90d80-157">Konfigurera Valv för länkar för Office 365-program i Microsoft 365 Defender portalen</span><span class="sxs-lookup"><span data-stu-id="90d80-157">Configure Safe Links protection for Office 365 apps in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="90d80-158">Valv Länkskydd för Office 365-appar gäller för dokument i Office-, mobil- och webbappar som stöds.</span><span class="sxs-lookup"><span data-stu-id="90d80-158">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="90d80-159">Mer information finns i inställningar [Valv länkar för appar Office 365 .](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="90d80-159">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="90d80-160">I Microsoft 365 Defender-portalen går du till Avsnittet **Principer &** e&-post och samarbete & Principer \>  \>  \>  för hot \> **Valv.**</span><span class="sxs-lookup"><span data-stu-id="90d80-160">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links**.</span></span>

2. <span data-ttu-id="90d80-161">På sidan **Valv klickar** du på **Globala inställningar**.</span><span class="sxs-lookup"><span data-stu-id="90d80-161">On the **Safe Links** page, click **Global settings**.</span></span> <span data-ttu-id="90d80-162">I den **Valv-länkprincip** för organisationen som visas konfigurerar du följande inställningar i avsnittet Inställningar som gäller för innehåll i **Office 365-appar:**</span><span class="sxs-lookup"><span data-stu-id="90d80-162">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content in supported Office 365 apps** section:</span></span>

   - <span data-ttu-id="90d80-163">**Använd Valv länkar i** Office 365-appar: Kontrollera att växlingsknappen är till höger för att aktivera Valv-länkar för Office 365-appar som stöds: ![ Aktivera ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="90d80-163">**Use Safe Links in Office 365 apps**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="90d80-164">**Spåra inte när användare** klickar på skyddade länkar i Office 365-appar : Flytta reglaget till vänster för att spåra användarklick på blockerade URL:er i Office 365-appar: Inaktivera ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="90d80-164">**Do not track when users click protected links in Office 365 apps**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="90d80-165">**Låt inte användare** klicka till den ursprungliga URL:en i Office 365-appar: Kontrollera att reglaget är till höger för att hindra användare från att klicka till den ursprungliga blockerade URL:en i Office 365-appar som stöds: Aktivera ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="90d80-165">**Do not let users click through to the original URL in Office 365 apps**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="90d80-166">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="90d80-166">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="90d80-167">Konfigurera Valv för länkar för Office 365 i PowerShell</span><span class="sxs-lookup"><span data-stu-id="90d80-167">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="90d80-168">Om du hellre vill använda PowerShell för att konfigurera Valv Links protection för Office 365-appar använder du följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="90d80-168">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="90d80-169">I det här exemplet konfigureras följande inställningar Valv skydd mot länkar i Office 365 appar:</span><span class="sxs-lookup"><span data-stu-id="90d80-169">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="90d80-170">Valv Länkar till Office 365-appar är aktiverat (vi använder inte parametern _EnableSafeLinksForO365Clients_ och standardvärdet är $true).</span><span class="sxs-lookup"><span data-stu-id="90d80-170">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="90d80-171">Användaren klickar på relaterade till blockerade URL:er i Office 365-program spåras.</span><span class="sxs-lookup"><span data-stu-id="90d80-171">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="90d80-172">Användarna får inte klicka sig fram till den ursprungliga blockerade URL:en i Office 365-appar som stöds (parametern _AllowClickThrough_ används inte och standardvärdet är $false).</span><span class="sxs-lookup"><span data-stu-id="90d80-172">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="90d80-173">Detaljerad information om syntax och parametrar finns i [Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="90d80-173">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="90d80-174">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="90d80-174">How do you know these procedures worked?</span></span>

<span data-ttu-id="90d80-175">Kontrollera att du har konfigurerat de globala inställningarna för Valv-länkar (listan Blockera följande **URL:er** och Office 365-programskyddsinställningarna) genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="90d80-175">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="90d80-176">I Microsoft 365 Defender-portalen går du till Principer för **e-&-samarbete** & principer för regler och hot Valv Länkar klickar på Globala inställningar och kontrollerar inställningarna i flyg ut som \>  \>  \>  \>  \> visas. </span><span class="sxs-lookup"><span data-stu-id="90d80-176">In the Microsoft 365 Defender portal, go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** page \> **Policies** section \> **Safe Links** \> click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="90d80-177">I Exchange Online PowerShell Exchange Online Protection PowerShell kör du följande kommando och kontrollerar inställningarna:</span><span class="sxs-lookup"><span data-stu-id="90d80-177">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="90d80-178">Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="90d80-178">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>
