---
title: Konfigurera globala inställningar för inställningarna för säkra länkar i Defender för Office 365
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
description: Administratörer kan lära sig hur de visar och konfigurerar globala inställningar (listan "Blockera följande URL:er" och skydd för Office 365-appar) för säkra länkar i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 390177a24648cf860a78ab831d5dfe334b2c9590
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207004"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="15f66-103">Konfigurera globala inställningar för säkra länkar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="15f66-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="15f66-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="15f66-104">**Applies to**</span></span>
- [<span data-ttu-id="15f66-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="15f66-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="15f66-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15f66-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> <span data-ttu-id="15f66-107">Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](defender-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="15f66-107">This article is intended for business customers who have [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span> <span data-ttu-id="15f66-108">Om du är hemanvändare och vill ha information om säkra länkar i Outlook kan du läsa Mer [Outlook.com säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="15f66-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="15f66-109">Säkra länkar är en funktion i Microsoft Defender för [Office 365](defender-for-office-365.md) som ger URL-skanning av inkommande e-postmeddelanden i e-postflödet och tidpunkten för klickverifiering av URL:er och länkar i e-postmeddelanden och på andra platser.</span><span class="sxs-lookup"><span data-stu-id="15f66-109">Safe Links is a feature in [Microsoft Defender for Office 365](defender-for-office-365.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="15f66-110">Mer information finns i [Säkra länkar i Microsoft Defender för Office 365.](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="15f66-110">For more information, see [Safe Links in Microsoft Defender for Office 365](safe-links.md).</span></span>

<span data-ttu-id="15f66-111">Du konfigurerar de flesta inställningarna för Säkra länkar i Principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="15f66-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="15f66-112">Anvisningar finns i Konfigurera [principer för säkra länkar i Microsoft Defender för Office 365.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="15f66-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

<span data-ttu-id="15f66-113">Men i Safe Links används även globala inställningar som gäller för alla användare som finns med i aktiva principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="15f66-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="15f66-114">Följande globala inställningsområde:</span><span class="sxs-lookup"><span data-stu-id="15f66-114">These global settings area:</span></span>

- <span data-ttu-id="15f66-115">Listan **Blockera följande URL:er.**</span><span class="sxs-lookup"><span data-stu-id="15f66-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="15f66-116">Mer information finns i [listan "Blockera följande URL:er" för Säkra länkar](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="15f66-116">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="15f66-117">Skydd mot säkra länkar för Office 365-appar.</span><span class="sxs-lookup"><span data-stu-id="15f66-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="15f66-118">Mer information finns i Inställningar [för säkra länkar för Office 365-appar.](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="15f66-118">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="15f66-119">Du kan konfigurera de globala inställningarna för säkra länkar i Säkerhets- och efterlevnadscenter för & eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor men med Microsoft Defender för Office 365-tilläggsprenumerationer).</span><span class="sxs-lookup"><span data-stu-id="15f66-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="15f66-120">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="15f66-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="15f66-121">De funktioner som tillhandahålls av globala inställningar för säkra länkar tillämpas endast på användare som ingår i aktiva principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="15f66-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="15f66-122">Det finns ingen inbyggd eller standardprincip för säkra länkar, så du måste skapa minst en princip för säkra länkar för att de globala inställningarna ska vara aktiva.</span><span class="sxs-lookup"><span data-stu-id="15f66-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="15f66-123">Anvisningar finns i Konfigurera [principer för säkra länkar i Microsoft Defender för Office 365.](set-up-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="15f66-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-safe-links-policies.md).</span></span>

- <span data-ttu-id="15f66-124">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="15f66-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="15f66-125">Om du vill gå direkt **till sidan Säkra** länkar använder du <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="15f66-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="15f66-126">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="15f66-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="15f66-127">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="15f66-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="15f66-128">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="15f66-128">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="15f66-129">Om du vill konfigurera globala inställningar för Säkra länkar måste du vara medlem i rollgrupperna **Organisationshantering** **eller Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="15f66-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="15f66-130">För skrivskyddade åtkomst till globala inställningar för säkra länkar måste du vara medlem i **rollgrupperna Global Reader** **eller Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="15f66-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="15f66-131">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="15f66-131">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="15f66-132">**Anteckningar**:</span><span class="sxs-lookup"><span data-stu-id="15f66-132">**Notes**:</span></span>

  - <span data-ttu-id="15f66-133">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15f66-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="15f66-134">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="15f66-134">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="15f66-135">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="15f66-135">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="15f66-136">Vi rekommenderar värden för globala inställningar för säkra länkar i Inställningarna [för säkra länkar.](recommended-settings-for-eop-and-office365.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="15f66-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

- <span data-ttu-id="15f66-137">Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="15f66-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="15f66-138">[Nya funktioner läggs kontinuerligt till i Microsoft Defender för Office 365.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="15f66-138">[New features are continually being added to Microsoft Defender for Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="15f66-139">När nya funktioner läggs till kan du behöva justera dina befintliga principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="15f66-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="15f66-140">Konfigurera listan Blockera följande URL:er i Säkerhets- och & Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="15f66-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="15f66-141">I **listan Blockera följande URL:er** identifieras de länkar som alltid ska blockeras av genomsökning av säkra länkar i program som stöds.</span><span class="sxs-lookup"><span data-stu-id="15f66-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="15f66-142">Mer information finns i [listan "Blockera följande URL:er" för Säkra länkar.](safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="15f66-142">For more information, see ["Block the following URLs" list for Safe Links](safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="15f66-143">I Säkerhets- & säkerhets- och  efterlevnadscenter går du till ATP för hothanteringspolicyn ATP – säkra \>  \> länkar och klickar sedan **på Globala inställningar.**</span><span class="sxs-lookup"><span data-stu-id="15f66-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="15f66-144">I principen **för säkra länkar för organisationen** som visas går du till rutan Blockera följande **URL:er.**</span><span class="sxs-lookup"><span data-stu-id="15f66-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="15f66-145">Konfigurera en eller flera poster enligt beskrivningen i [Postsyntax för listan "Blockera följande URL:er".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="15f66-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="15f66-146">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="15f66-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="15f66-147">Konfigurera listan "Blockera följande URL:er" i PowerShell</span><span class="sxs-lookup"><span data-stu-id="15f66-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="15f66-148">Mer information om postsyntaxen finns [i Postsyntax för listan "Blockera följande URL:er".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="15f66-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="15f66-149">Du kan använda cmdleten **Get-AtpPolicyForO365** till att visa befintliga poster i egenskapen _BlockURLs._</span><span class="sxs-lookup"><span data-stu-id="15f66-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="15f66-150">Om du vill lägga till värden som ersätter befintliga poster ska du använda följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="15f66-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="15f66-151">I det här exemplet läggs följande poster till i listan:</span><span class="sxs-lookup"><span data-stu-id="15f66-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="15f66-152">Blockera domän, underdomäner och sökvägar för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="15f66-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="15f66-153">Blockera efterforskningar för underdomäner, men inte den överordnade domänen eller andra underdomäner i tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="15f66-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="15f66-154">Om du vill lägga till eller ta bort värden utan att påverka andra befintliga poster använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="15f66-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="15f66-155">I det här exemplet läggs en ny adatum.com posten till och posten tas bort för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="15f66-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="15f66-156">Konfigurera skydd mot säkra länkar för Office 365-appar i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="15f66-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="15f66-157">Skydd mot säkra länkar för Office 365-program gäller dokument i Office-skrivbords-, mobil- och webbprogram som stöds.</span><span class="sxs-lookup"><span data-stu-id="15f66-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="15f66-158">Mer information finns i Inställningar [för säkra länkar för Office 365-appar.](safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="15f66-158">For more information, see [Safe Links settings for Office 365 apps](safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="15f66-159">I Säkerhets- & säkerhets- och  efterlevnadscenter går du till ATP för hothanteringspolicyn ATP – säkra \>  \> länkar och klickar sedan **på Globala inställningar.**</span><span class="sxs-lookup"><span data-stu-id="15f66-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="15f66-160">I principen **för säkra länkar för organisationen som** visas konfigurerar du följande inställningar i avsnittet Inställningar som gäller för innehåll utom **e-post:**</span><span class="sxs-lookup"><span data-stu-id="15f66-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="15f66-161">**Office 365-program:** Kontrollera att reglaget är till höger för att aktivera Säkra länkar för Office 365-appar som stöds: ![ Aktivera ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="15f66-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="15f66-162">**Spåra inte när användare** klickar på Säkra länkar: Flytta växlingsknappen åt vänster för att spåra användarklick som är relaterade till blockerade URL-adresser i Office 365-appar som stöds: Inaktivera ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="15f66-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="15f66-163">**Låt inte användare** klicka genom Säkra länkar till den ursprungliga URL:en: Kontrollera att växlingsknappen är till höger för att hindra användare från att klicka till den ursprungliga blockerade URL:en i Office 365-appar som stöds: Aktivera ![ ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="15f66-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="15f66-164">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="15f66-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="15f66-165">Konfigurera skydd mot säkra länkar för Office 365-appar i PowerShell</span><span class="sxs-lookup"><span data-stu-id="15f66-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="15f66-166">Om du hellre vill använda PowerShell för att konfigurera skydd mot säkra länkar för Office 365-program använder du följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="15f66-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="15f66-167">I det här exemplet konfigureras följande inställningar för skydd mot säkra länkar i Office 365-appar:</span><span class="sxs-lookup"><span data-stu-id="15f66-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="15f66-168">Säkra länkar för Office 365-appar är aktiverat (vi använder inte parametern _EnableSafeLinksForO365Clients_ och standardvärdet är $true).</span><span class="sxs-lookup"><span data-stu-id="15f66-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="15f66-169">Användaren klickar på blockerade URL:er i Office 365-appar som stöds spåras.</span><span class="sxs-lookup"><span data-stu-id="15f66-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="15f66-170">Användarna får inte klicka sig fram till den ursprungliga blockerade URL:en i Office 365-appar som stöds (parametern _AllowClickThrough_ används inte och standardvärdet är $false).</span><span class="sxs-lookup"><span data-stu-id="15f66-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="15f66-171">Detaljerad information om syntax och parametrar finns i [Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="15f66-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="15f66-172">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="15f66-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="15f66-173">Verifiera att du har konfigurerat de globala inställningarna för säkra länkar (listan Blockera följande **URL:er** och programskyddsinställningarna för Office 365) genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="15f66-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="15f66-174">I Säkerhets- & säkerhets- och  efterlevnadscenter går du till ATP för hothanteringspolicyn – säkra länkar , klickar på Globala inställningar och kontrollerar inställningarna i utfällpunkten \>  \> som visas. </span><span class="sxs-lookup"><span data-stu-id="15f66-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="15f66-175">Kör följande kommando och verifiera inställningarna i Exchange Online PowerShell eller Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="15f66-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="15f66-176">Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365.](/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="15f66-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).</span></span>