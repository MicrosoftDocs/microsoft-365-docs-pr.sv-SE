---
title: Konfigurera globala inställningar för inställningarna för Säkra länkar i Defender för Office 365
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
description: Administratörer kan ta reda på hur de visar och konfigurerar globala inställningar (listan Blockera följande URL:er och skydd för Office 365-program) för säkra länkar i Microsoft Defender för Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 885fe6a06cce054bea6d6f20c24c5c1f2a159c07
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165733"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a><span data-ttu-id="49de6-103">Konfigurera globala inställningar för Säkra länkar i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="49de6-103">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="49de6-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="49de6-104">**Applies to**</span></span>
- [<span data-ttu-id="49de6-105">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="49de6-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="49de6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49de6-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="49de6-107">Den här artikeln är avsedd för företagskunder som har [Microsoft Defender för Office 365](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="49de6-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="49de6-108">Om du är hemanvändare och vill ha information om säkra länkar i Outlook kan du [läsa Mer Outlook.com säkerhet.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)</span><span class="sxs-lookup"><span data-stu-id="49de6-108">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="49de6-109">Säkra länkar är en funktion i Microsoft Defender för [Office 365](office-365-atp.md) som ger URL-genomsökning av inkommande e-postmeddelanden i e-postflödet och tidpunkten för klickverifiering av URL:er och länkar i e-postmeddelanden och på andra platser.</span><span class="sxs-lookup"><span data-stu-id="49de6-109">Safe Links is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="49de6-110">Mer information finns i [Säkra länkar i Microsoft Defender för Office 365.](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="49de6-110">For more information, see [Safe Links in Microsoft Defender for Office 365](atp-safe-links.md).</span></span>

<span data-ttu-id="49de6-111">Du konfigurerar de flesta inställningarna för Säkra länkar i principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="49de6-111">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="49de6-112">Instruktioner finns i Konfigurera [principer för säkra länkar i Microsoft Defender för Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="49de6-112">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="49de6-113">Men Säkra länkar använder även globala inställningar som gäller för alla användare som ingår i aktiva principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="49de6-113">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="49de6-114">Följande globala inställningsområde:</span><span class="sxs-lookup"><span data-stu-id="49de6-114">These global settings area:</span></span>

- <span data-ttu-id="49de6-115">Listan **Blockera följande URL-adresser.**</span><span class="sxs-lookup"><span data-stu-id="49de6-115">The **Block the following URLs** list.</span></span> <span data-ttu-id="49de6-116">Mer information finns i [listan "Blockera följande URL:er" för Säkra länkar](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="49de6-116">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="49de6-117">Skydd mot säkra länkar för Office 365-appar.</span><span class="sxs-lookup"><span data-stu-id="49de6-117">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="49de6-118">Mer information finns i inställningarna [för Säkra länkar för Office 365-appar.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="49de6-118">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="49de6-119">Du kan konfigurera globala inställningar för säkra länkar i Säkerhets- & och efterlevnadscenter eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med postlådor i Exchange Online; fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Microsoft Defender för Office 365-tilläggsprenumerationer).</span><span class="sxs-lookup"><span data-stu-id="49de6-119">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Microsoft Defender for Office 365 add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="49de6-120">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="49de6-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="49de6-121">De funktioner som tillhandahålls av globala inställningar för säkra länkar tillämpas endast på användare som ingår i aktiva principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="49de6-121">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="49de6-122">Det finns ingen inbyggd eller standardprincip för säkra länkar, så du måste skapa minst en princip för säkra länkar för att dessa globala inställningar ska vara aktiva.</span><span class="sxs-lookup"><span data-stu-id="49de6-122">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="49de6-123">Instruktioner finns i Konfigurera [principer för säkra länkar i Microsoft Defender för Office 365.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="49de6-123">For instructions, see [Set up Safe Links policies in Microsoft Defender for Office 365](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="49de6-124">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="49de6-124">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="49de6-125">Om du vill gå direkt **till sidan Säkra** länkar använder du <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="49de6-125">To go directly to the **Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="49de6-126">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="49de6-126">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="49de6-127">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="49de6-127">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="49de6-128">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="49de6-128">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="49de6-129">Om du vill konfigurera globala inställningar för Säkra länkar måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="49de6-129">To configure the global settings for Safe Links, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="49de6-130">För skrivskyddade åtkomst till globala inställningar för säkra länkar måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="49de6-130">For read-only access to the global settings for Safe Links, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="49de6-131">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="49de6-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="49de6-132">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="49de6-132">**Notes**:</span></span>

  - <span data-ttu-id="49de6-133">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="49de6-133">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="49de6-134">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="49de6-134">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="49de6-135">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="49de6-135">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="49de6-136">Våra rekommenderade värden för de globala inställningarna för Säkra länkar finns i [inställningarna för Säkra länkar.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)</span><span class="sxs-lookup"><span data-stu-id="49de6-136">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="49de6-137">Det kan ta upp till 30 minuter innan en ny eller uppdaterad princip tillämpas.</span><span class="sxs-lookup"><span data-stu-id="49de6-137">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="49de6-138">[Nya funktioner läggs kontinuerligt till i Microsoft Defender för Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="49de6-138">[New features are continually being added to Microsoft Defender for Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="49de6-139">När nya funktioner läggs till kan du behöva justera dina befintliga principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="49de6-139">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="49de6-140">Konfigurera listan "Blockera följande URL:er" i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="49de6-140">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="49de6-141">I **listan Blockera följande URL:er** identifieras de länkar som alltid ska blockeras genom genomsökning av Säkra länkar i appar som stöds.</span><span class="sxs-lookup"><span data-stu-id="49de6-141">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="49de6-142">Mer information finns i [listan "Blockera följande URL:er" för Säkra länkar.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="49de6-142">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="49de6-143">I Säkerhets- & Säkerhets- och  efterlevnadscenter går du till ATP – säkra länkar för hanteringspolicy och \>  \> klickar sedan **på Globala inställningar.**</span><span class="sxs-lookup"><span data-stu-id="49de6-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="49de6-144">I principen **för säkra länkar i organisationen** som visas går du till rutan Blockera följande **URL:er.**</span><span class="sxs-lookup"><span data-stu-id="49de6-144">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="49de6-145">Konfigurera en eller flera poster enligt beskrivningen i [Postsyntax för listan "Blockera följande URL:er".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="49de6-145">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="49de6-146">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="49de6-146">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="49de6-147">Konfigurera listan "Blockera följande URL:er" i PowerShell</span><span class="sxs-lookup"><span data-stu-id="49de6-147">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="49de6-148">Mer information om postsyntaxen [finns i Postsyntax för listan Blockera följande URL:er.](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)</span><span class="sxs-lookup"><span data-stu-id="49de6-148">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="49de6-149">Du kan använda cmdleten **Get-AtpPolicyForO365** till att visa befintliga poster i egenskapen _BlockURLs._</span><span class="sxs-lookup"><span data-stu-id="49de6-149">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="49de6-150">Om du vill lägga till värden som ersätter befintliga poster ska du använda följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="49de6-150">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="49de6-151">I det här exemplet läggs följande poster till i listan:</span><span class="sxs-lookup"><span data-stu-id="49de6-151">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="49de6-152">Blockera domän, underdomäner och sökvägar för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="49de6-152">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="49de6-153">Blockera underdomänsforskningen, men inte den överordnade domänen eller andra underdomäner i tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="49de6-153">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="49de6-154">Om du vill lägga till eller ta bort värden utan att påverka andra befintliga poster använder du följande syntax:</span><span class="sxs-lookup"><span data-stu-id="49de6-154">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="49de6-155">Det här exemplet lägger till en adatum.com post och tar bort posten för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="49de6-155">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="49de6-156">Konfigurera skydd mot säkra länkar för Office 365-appar i Säkerhets- & Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="49de6-156">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="49de6-157">Skydd mot säkra länkar för Office 365-program gäller dokument i Office-skrivbords-, mobil- och webbprogram som stöds.</span><span class="sxs-lookup"><span data-stu-id="49de6-157">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="49de6-158">Mer information finns i inställningarna [för Säkra länkar för Office 365-appar.](atp-safe-links.md#safe-links-settings-for-office-365-apps)</span><span class="sxs-lookup"><span data-stu-id="49de6-158">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="49de6-159">I Säkerhets- & Säkerhets- och  efterlevnadscenter går du till ATP – säkra länkar för hanteringspolicy och \>  \> klickar sedan **på Globala inställningar.**</span><span class="sxs-lookup"><span data-stu-id="49de6-159">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="49de6-160">I principen **För säkra länkar i organisationen** som visas konfigurerar du följande inställningar i inställningarna som gäller för innehåll utom **e-postavsnittet:**</span><span class="sxs-lookup"><span data-stu-id="49de6-160">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="49de6-161">**Office 365-program:** Kontrollera att reglaget är till höger för att aktivera Säkra länkar för Office 365-program som stöds: ![ Aktivera ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="49de6-161">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="49de6-162">**Spåra inte när användare** klickar på Säkra länkar: Flytta växlingsknappen åt vänster för att spåra användarklick som är relaterade till blockerade URL:er i Office 365-appar som stöds: ![ ](../../media/scc-toggle-off.png) Inaktivera.</span><span class="sxs-lookup"><span data-stu-id="49de6-162">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="49de6-163">**Låt inte användare** klicka genom Säkra länkar till den ursprungliga URL:en: Kontrollera att reglaget är till höger för att hindra användare från att klicka till den ursprungliga blockerade URL:en i Office 365-appar som stöds: Slå ![ ](../../media/scc-toggle-on.png) på.</span><span class="sxs-lookup"><span data-stu-id="49de6-163">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   <span data-ttu-id="49de6-164">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="49de6-164">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="49de6-165">Konfigurera skydd mot säkra länkar för Office 365-appar i PowerShell</span><span class="sxs-lookup"><span data-stu-id="49de6-165">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="49de6-166">Om du hellre vill använda PowerShell för att konfigurera skydd mot säkra länkar för Office 365-program använder du följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="49de6-166">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="49de6-167">Det här exemplet konfigurerar följande inställningar för skydd mot säkra länkar i Office 365-program:</span><span class="sxs-lookup"><span data-stu-id="49de6-167">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="49de6-168">Säkra länkar för Office 365-appar är aktiverat (vi använder inte parametern _EnableSafeLinksForO365Clients_ och standardvärdet är $true).</span><span class="sxs-lookup"><span data-stu-id="49de6-168">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="49de6-169">Användarklick som är relaterade till blockerade URL:er i Office 365-program spåras.</span><span class="sxs-lookup"><span data-stu-id="49de6-169">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="49de6-170">Användare får inte klicka till den ursprungliga blockerade URL:en i Office 365-program som stöds (parametern _AllowClickThrough_ används inte och standardvärdet är $false).</span><span class="sxs-lookup"><span data-stu-id="49de6-170">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="49de6-171">Detaljerad information om syntax och parametrar finns [i Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="49de6-171">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="49de6-172">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="49de6-172">How do you know these procedures worked?</span></span>

<span data-ttu-id="49de6-173">Kontrollera att du har konfigurerat de globala inställningarna för  säkra länkar (listan Blockera följande URL-adresser och skyddsinställningarna för Office 365-appen) genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="49de6-173">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="49de6-174">I Säkerhets- & Efterlevnadscenter går  du till ATP – säkra länkar för hanteringspolicy, klickar på Globala inställningar och kontrollerar inställningarna i flyg \>  \> ut som visas. </span><span class="sxs-lookup"><span data-stu-id="49de6-174">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="49de6-175">Kör följande kommando i Exchange Online PowerShell eller Exchange Online Protection PowerShell och kontrollera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="49de6-175">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="49de6-176">Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="49de6-176">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
