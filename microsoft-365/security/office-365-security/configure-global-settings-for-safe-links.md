---
title: Konfigurera globala inställningar för inställningar för säkra länkar i Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur du visar och konfigurerar globala inställningar (Blockera följande webb adresser lista och skydd för Office 365-appar) för säkra länkar i Office 365 Avancerat skydd (ATP).
ms.openlocfilehash: 6ca18bfb555419a8f4a61b55715f328ed7da5e88
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328567"
---
# <a name="configure-global-settings-for-safe-links-in-office-365-atp"></a><span data-ttu-id="da23a-103">Konfigurera globala inställningar för säkra länkar i Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="da23a-103">Configure global settings for Safe Links in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="da23a-104">Den här artikeln är avsedd för företagskunder som har [Office 365 Avancerat skydd](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="da23a-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="da23a-105">Om du är hem användare letar efter information om Safelinks i Outlook kan du läsa mer i [avancerad Outlook.com-säkerhet](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="da23a-105">If you are a home user looking for information about Safelinks in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="da23a-106">Säkra länkar är en funktion i [Office 365 Avancerat skydd (ATP)](office-365-atp.md) som tillhandahåller URL-genomsökning av inkommande e-postmeddelanden i e-postflöde och när du klickar på verifiering av URL-adresser och länkar i e-postmeddelanden och på andra platser.</span><span class="sxs-lookup"><span data-stu-id="da23a-106">Safe Links is a feature in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) that provides URL scanning of inbound email messages in mail flow, and time of click verification of URLs and links in email messages and in other locations.</span></span> <span data-ttu-id="da23a-107">Mer information finns i [säkra länkar i Office 365 ATP](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="da23a-107">For more information, see [Safe Links in Office 365 ATP](atp-safe-links.md).</span></span>

<span data-ttu-id="da23a-108">Du konfigurerar de flesta säkra länkar-inställningar i principer för säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="da23a-108">You configure most Safe Links settings in Safe Links policies.</span></span> <span data-ttu-id="da23a-109">Anvisningar finns i [Konfigurera principer för säkra länkar i Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="da23a-109">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

<span data-ttu-id="da23a-110">Men, säkra länkar använder dessutom globala inställningar som gäller för alla användare som ingår i alla aktiva principer för säker länkar.</span><span class="sxs-lookup"><span data-stu-id="da23a-110">But, Safe Links also uses global settings that apply to all users who are included in any active Safe Links policies.</span></span> <span data-ttu-id="da23a-111">Följande globala inställningar:</span><span class="sxs-lookup"><span data-stu-id="da23a-111">These global settings area:</span></span>

- <span data-ttu-id="da23a-112">Listan **Blockera följande URL: er** .</span><span class="sxs-lookup"><span data-stu-id="da23a-112">The **Block the following URLs** list.</span></span> <span data-ttu-id="da23a-113">Mer information finns i ["Blockera följande URL-adresser" för säkra länkar](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span><span class="sxs-lookup"><span data-stu-id="da23a-113">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)</span></span>
- <span data-ttu-id="da23a-114">Säkra länkar skyddar mot Office 365-appar.</span><span class="sxs-lookup"><span data-stu-id="da23a-114">Safe Links protection for Office 365 apps.</span></span> <span data-ttu-id="da23a-115">Mer information finns i [Inställningar för säkra Länkar för Office 365-appar](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="da23a-115">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

<span data-ttu-id="da23a-116">Du kan konfigurera inställningarna för global Safe Links i säkerhets & Compliance Center eller i PowerShell (Exchange Online PowerShell för kvalificerade Microsoft 365-organisationer med post lådor i Exchange Online, fristående EOP PowerShell för organisationer utan Exchange Online-postlådor, men med Office 365 ATP-tilläggs prenumerationer).</span><span class="sxs-lookup"><span data-stu-id="da23a-116">You can configure the global Safe Links settings in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Office 365 ATP add-on subscriptions).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="da23a-117">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="da23a-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="da23a-118">De funktioner som tillhandahålls av globala inställningar för säkra länkar tillämpas bara på användare som ingår i principer för aktiva säkra länkar.</span><span class="sxs-lookup"><span data-stu-id="da23a-118">The features provided by global settings for Safe Links are only applied to users who are included in active Safe Links policies.</span></span> <span data-ttu-id="da23a-119">Det finns inga inbyggda eller standard principer för säkra länkar, så du behöver skapa minst en princip för säkra Länkar för att dessa globala inställningar ska vara aktiva.</span><span class="sxs-lookup"><span data-stu-id="da23a-119">There is no built-in or default Safe Links policy, so you need to create at least one Safe Links policy in order for these global settings to be active.</span></span> <span data-ttu-id="da23a-120">Anvisningar finns i [Konfigurera principer för säkra länkar i Office 365 ATP](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="da23a-120">For instructions, see [Set up Safe Links policies in Office 365 ATP](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="da23a-121">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="da23a-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="da23a-122">Använd om du vill gå direkt till sidan **Safe Links för ATP** <https://protection.office.com/safelinksv2> .</span><span class="sxs-lookup"><span data-stu-id="da23a-122">To go directly to the **ATP Safe Links** page, use <https://protection.office.com/safelinksv2>.</span></span>

- <span data-ttu-id="da23a-123">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="da23a-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="da23a-124">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="da23a-124">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="da23a-125">Om du vill visa och konfigurera globala inställningar för säkra länkar måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="da23a-125">To view and configure the global settings for Safe Links, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="da23a-126">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="da23a-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="da23a-127">**Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="da23a-127">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="da23a-128">För våra rekommenderade värden för globala inställningar för säkra länkar, se [Inställningar för säkra anslutningar](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span><span class="sxs-lookup"><span data-stu-id="da23a-128">For our recommended values for the global settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).</span></span>

- <span data-ttu-id="da23a-129">Tillåt upp till 30 minuter för att en ny eller uppdaterad princip ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="da23a-129">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

- <span data-ttu-id="da23a-130">[Nya funktioner läggs hela tiden till för ATP](office-365-atp.md#new-features-in-office-365-atp).</span><span class="sxs-lookup"><span data-stu-id="da23a-130">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="da23a-131">När nya funktioner läggs till kan du behöva justera dina befintliga principer för säker länkar.</span><span class="sxs-lookup"><span data-stu-id="da23a-131">As new features are added, you may need to make adjustments to your existing Safe Links policies.</span></span>

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a><span data-ttu-id="da23a-132">Konfigurera listan "Blockera följande URL-adresser" i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="da23a-132">Configure the "Block the following URLs" list in the Security & Compliance Center</span></span>

<span data-ttu-id="da23a-133">I rutan **Blockera följande URL: er** visas länkar som alltid ska blockeras av sökning efter säkra länkar i program som stöds.</span><span class="sxs-lookup"><span data-stu-id="da23a-133">The **Block the following URLs** list identifies the links that should always be blocked by Safe Links scanning in supported apps.</span></span> <span data-ttu-id="da23a-134">Mer information finns i ["Blockera följande URL-adresser" för säkra länkar](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span><span class="sxs-lookup"><span data-stu-id="da23a-134">For more information, see ["Block the following URLs" list for Safe Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).</span></span>

1. <span data-ttu-id="da23a-135">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP Safe Links**och klickar sedan på **globala inställningar**.</span><span class="sxs-lookup"><span data-stu-id="da23a-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="da23a-136">I **principen Safe Links för din organisation** flyger ut som visas går du till rutan **Blockera följande URL: er** .</span><span class="sxs-lookup"><span data-stu-id="da23a-136">In the **Safe Links policy for your organization** fly out that appears, go to the **Block the following URLs** box.</span></span>

3. <span data-ttu-id="da23a-137">Konfigurera en eller flera poster enligt [syntaxen för listan Blockera följande URL: er](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="da23a-137">Configure one or more entries as described in [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

   <span data-ttu-id="da23a-138">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="da23a-138">When you're finished, click **Save**.</span></span>

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a><span data-ttu-id="da23a-139">Konfigurera listan "Blockera följande URL-adresser" i PowerShell</span><span class="sxs-lookup"><span data-stu-id="da23a-139">Configure the "Block the following URLs" list in PowerShell</span></span>

<span data-ttu-id="da23a-140">Information om syntaxen finns i [syntaxen för listan "Blockera följande URL-adresser"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span><span class="sxs-lookup"><span data-stu-id="da23a-140">For details about the entry syntax, see [Entry syntax for the "Block the following URLs" list](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).</span></span>

<span data-ttu-id="da23a-141">Du kan använda cmdleten **Get-AtpPolicyForO365** för att visa befintliga poster i egenskapen _BlockURLs_ .</span><span class="sxs-lookup"><span data-stu-id="da23a-141">You can use the **Get-AtpPolicyForO365** cmdlet to view existing entries in the _BlockURLs_ property.</span></span>

- <span data-ttu-id="da23a-142">Om du vill lägga till värden som ersätter befintliga poster kan du använda följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="da23a-142">To add values that will replace any existing entries, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  <span data-ttu-id="da23a-143">I det här exemplet läggs följande poster till i listan:</span><span class="sxs-lookup"><span data-stu-id="da23a-143">This example adds the following entries to the list:</span></span>

  - <span data-ttu-id="da23a-144">Blockera domänen, under domäner och sökvägar för fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="da23a-144">Block the domain, subdomains, and paths for fabrikam.com.</span></span>
  - <span data-ttu-id="da23a-145">Blockera under domänens Research, men inte den överordnade domänen eller andra under domäner i tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="da23a-145">Block the subdomain research, but not the parent domain or other subdomains in tailspintoys.com</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- <span data-ttu-id="da23a-146">Använd följande syntax för att lägga till eller ta bort värden utan att påverka andra befintliga poster:</span><span class="sxs-lookup"><span data-stu-id="da23a-146">To add or remove values without affecting other existing entries, use the following syntax:</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  <span data-ttu-id="da23a-147">I det här exemplet läggs en ny post för adatum.com till, och posten för fabrikam.com tas bort.</span><span class="sxs-lookup"><span data-stu-id="da23a-147">This example adds a new entry for adatum.com, and removes the entry for fabrikam.com.</span></span>

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a><span data-ttu-id="da23a-148">Konfigurera skydd för säkra Länkar för Office 365-appar i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="da23a-148">Configure Safe Links protection for Office 365 apps in the Security & Compliance Center</span></span>

<span data-ttu-id="da23a-149">Säkra länkar skydd för Office 365-appar gäller för dokument i Office-skrivbord, mobiler och webb program som stöds.</span><span class="sxs-lookup"><span data-stu-id="da23a-149">Safe Links protection for Office 365 apps applies to documents in supported Office desktop, mobile, and web apps.</span></span> <span data-ttu-id="da23a-150">Mer information finns i [Inställningar för säkra Länkar för Office 365-appar](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span><span class="sxs-lookup"><span data-stu-id="da23a-150">For more information, see [Safe Links settings for Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).</span></span>

1. <span data-ttu-id="da23a-151">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> **ATP Safe Links**och klickar sedan på **globala inställningar**.</span><span class="sxs-lookup"><span data-stu-id="da23a-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="da23a-152">I **principen Safe Links för din organisation** flyger ut som visas konfigurerar du följande inställningar i inställningarna för **innehåll utom e-post** :</span><span class="sxs-lookup"><span data-stu-id="da23a-152">In the **Safe Links policy for your organization** fly out that appears, configure the following settings in the **Settings that apply to content except email** section:</span></span>

   - <span data-ttu-id="da23a-153">**Office 365-program**: kontrol lera att växlings knappen är till höger för att aktivera säkra Länkar för Office 365-appar som stöds: ![ slå på ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="da23a-153">**Office 365 applications**: Verify the toggle is to the right to enable Safe Links for supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   - <span data-ttu-id="da23a-154">**Spåra inte när användare klickar på säkra länkar**: flytta växlings knappen till vänster för att hålla reda på användare klickar på relaterade till blockerade URL: er i Office 365-appar som stöds ![ ](../../media/scc-toggle-off.png) .</span><span class="sxs-lookup"><span data-stu-id="da23a-154">**Do not track when users click Safe Links**: Move the toggle to the left to track user clicks related to blocked URLs in supported Office 365 apps: ![Toggle off](../../media/scc-toggle-off.png).</span></span>

   - <span data-ttu-id="da23a-155">**Tillåt inte att användare klickar via säkra länkar till den ursprungliga webb adressen**: kontrol lera att växlings knappen är till höger för att förhindra användare från att klicka dig fram till den ursprungliga blockerade webb adressen i Office 365-appar som stöds och ![ aktivera ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .</span><span class="sxs-lookup"><span data-stu-id="da23a-155">**Do not let users click through Safe Links to the original URL**: Verify the toggle is to the right to prevent users from clicking through to the original blocked URL in supported Office 365 apps: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="da23a-156">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="da23a-156">When you're finished, click **Save**.</span></span>

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a><span data-ttu-id="da23a-157">Konfigurera skydd för säkra Länkar för Office 365-appar i PowerShell</span><span class="sxs-lookup"><span data-stu-id="da23a-157">Configure Safe Links protection for Office 365 apps in PowerShell</span></span>

<span data-ttu-id="da23a-158">Om du hellre vill använda PowerShell för att konfigurera skydd för säkra Länkar för Office 365-appar kan du använda följande syntax i Exchange Online PowerShell eller Exchange Online Protection PowerShell:</span><span class="sxs-lookup"><span data-stu-id="da23a-158">If you'd rather use PowerShell to configure Safe Links protection for Office 365 apps, use the following syntax in Exchange Online PowerShell or Exchange Online Protection PowerShell:</span></span>

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

<span data-ttu-id="da23a-159">I det här exemplet konfigureras följande inställningar för skydd för säkra länkar i Office 365-appar:</span><span class="sxs-lookup"><span data-stu-id="da23a-159">This example configures the following settings for Safe Links protection in Office 365 apps:</span></span>

- <span data-ttu-id="da23a-160">Säkra Länkar för Office 365-appar är aktiverade (vi använder inte parametern _EnableSafeLinksForO365Clients_ och standardvärdet är $true).</span><span class="sxs-lookup"><span data-stu-id="da23a-160">Safe Links for Office 365 apps is turned on (we aren't using the _EnableSafeLinksForO365Clients_ parameter, and the default value is $true).</span></span>
- <span data-ttu-id="da23a-161">Användaren klickar på relaterade till blockerade URL: er i Office 365-program som stöds och spåras.</span><span class="sxs-lookup"><span data-stu-id="da23a-161">User clicks related to blocked URLs in supported Office 365 apps are tracked.</span></span>
- <span data-ttu-id="da23a-162">Användare får inte klicka här via _till den ursprungliga_ blockerade webb adressen i Office 365-appar som stöds, och standardvärdet är $false).</span><span class="sxs-lookup"><span data-stu-id="da23a-162">Users are not allowed to click through to the original blocked URL in supported Office 365 apps (we aren't using the _AllowClickThrough_ parameter, and the default value is $false).</span></span>

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

<span data-ttu-id="da23a-163">Detaljerad information om syntax och parametrar finns i [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="da23a-163">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="da23a-164">Hur vet jag att de här procedurerna fungerade?</span><span class="sxs-lookup"><span data-stu-id="da23a-164">How do you know these procedures worked?</span></span>

<span data-ttu-id="da23a-165">Gör något av följande för att kontrol lera att du har konfigurerat de globala inställningarna för säkra länkar ( **Blockera följande webb adress** lista och Office 365 App Protection-inställningar):</span><span class="sxs-lookup"><span data-stu-id="da23a-165">To verify that you've successfully configured the global settings for Safe Links (the **Block the following URLs** list and the Office 365 app protection settings), do any of the following steps:</span></span>

- <span data-ttu-id="da23a-166">I säkerhets & Compliance Center går du till **Threat Management** \> **policy** \> - **säkra länkar**, klickar på **globala inställningar**och kontrollerar inställningarna i rutan Lägg på.</span><span class="sxs-lookup"><span data-stu-id="da23a-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Links**, click **Global settings**, and verify the settings in the fly out that appears.</span></span>

- <span data-ttu-id="da23a-167">Kör följande kommando i Exchange Online PowerShell eller Exchange Online Protection PowerShell och kontrol lera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="da23a-167">In Exchange Online PowerShell or Exchange Online Protection PowerShell, run the following command and verify the settings:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  <span data-ttu-id="da23a-168">Detaljerad information om syntax och parametrar finns i [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="da23a-168">For detailed syntax and parameter information, see [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).</span></span>
