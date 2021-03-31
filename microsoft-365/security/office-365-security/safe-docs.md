---
title: Säkra dokument i Microsoft Defender för Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Läs mer om säkra dokument i Microsoft 365 E5 eller Microsoft 365 E5 Säkerhet.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 78ae99158e30046923d24897e7ab9b45adff31d0
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445402"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="e9b96-103">Säkra dokument i Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e9b96-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e9b96-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="e9b96-104">**Applies to**</span></span>
- [<span data-ttu-id="e9b96-105">Microsoft Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="e9b96-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e9b96-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9b96-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e9b96-107">Säkra dokument är en funktion i Microsoft 365 E5 eller Microsoft 365 E5-säkerhet som använder [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för Endpoint för att söka igenom dokument och filer som öppnas i [Skyddad](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) vy eller Application Guard [för Office.](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)</span><span class="sxs-lookup"><span data-stu-id="e9b96-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) or [Application Guard for Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e9b96-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="e9b96-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e9b96-109">Säkra dokument är endast tillgängligt för användare med *Säkerhetslicenser för Microsoft 365 E5* eller *Microsoft 365 E5.*</span><span class="sxs-lookup"><span data-stu-id="e9b96-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="e9b96-110">Dessa licenser ingår inte i Microsoft Defender för Office 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="e9b96-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="e9b96-111">Säkra dokument stöds i Microsoft 365-appar för företag (kallades tidigare Office 365 ProPlus) version 2004 eller senare.</span><span class="sxs-lookup"><span data-stu-id="e9b96-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="e9b96-112">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="e9b96-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="e9b96-113">Gå direkt till sidan **ATP – säkra bifogade** filer genom att öppna <https://protection.office.com/safeattachmentv2> .</span><span class="sxs-lookup"><span data-stu-id="e9b96-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="e9b96-114">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e9b96-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e9b96-115">Du måste ha tilldelats behörigheter i **Exchange Online** innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="e9b96-115">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e9b96-116">För att konfigurera inställningarna för säkra dokument måste du vara medlem i rollgrupperna **Organisationshantering** **eller Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="e9b96-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e9b96-117">För skrivskyddade åtkomst till inställningarna för säkra dokument måste du vara medlem i rollgrupperna **Global Reader** eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="e9b96-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e9b96-118">Mer information finns under [Behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="e9b96-118">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="e9b96-119">Genom att lägga till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna den nödvändiga behörigheten _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9b96-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e9b96-120">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e9b96-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="e9b96-121">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="e9b96-121">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="e9b96-122">Hur hanterar Microsoft dina data?</span><span class="sxs-lookup"><span data-stu-id="e9b96-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="e9b96-123">För att skydda dig skickar Säkra dokument filer till [Microsoft Defender för Endpoint-molnet](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för analys.</span><span class="sxs-lookup"><span data-stu-id="e9b96-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="e9b96-124">Information om hur Microsoft Defender för Endpoint hanterar dina data finns här: Microsoft Defender för [endpoint-datalagring och sekretess](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="e9b96-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="e9b96-125">Filer som skickas av säkra dokument sparas inte i Defender utöver den tid som krävs för analys (normalt mindre än 24 timmar).</span><span class="sxs-lookup"><span data-stu-id="e9b96-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="e9b96-126">Använd Säkerhets- och & för att konfigurera säkra dokument</span><span class="sxs-lookup"><span data-stu-id="e9b96-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="e9b96-127">I Säkerhets- & säkerhets- och efterlevnadscenter går **du** till ATP för hothanteringspolicy för säkra \>  \> **bifogade** filer och klickar sedan **på Globala inställningar.**</span><span class="sxs-lookup"><span data-stu-id="e9b96-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="e9b96-128">I den **globala inställningsfällan** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="e9b96-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e9b96-129">**Aktivera Säkra dokument för Office-klienter**: Flytta växlingsknappen åt höger för att aktivera funktionen: ![ Aktivera ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="e9b96-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="e9b96-130">Tillåt att andra klickar i Skyddad vy även om säkra dokument identifierar filen som skadlig: Vi rekommenderar att du låter det här alternativet vara inaktiverat (låt **växlingsknappen** vara till vänster: ![ ](../../media/scc-toggle-off.png) inaktivera).</span><span class="sxs-lookup"><span data-stu-id="e9b96-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="e9b96-131">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="e9b96-131">When you're finished, click **Save**.</span></span>

   ![Inställningarna för Säkra dokument när du har valt Globala inställningar på sidan Säkra bifogade filer.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="e9b96-133">Använda Exchange Online PowerShell för att konfigurera säkra dokument</span><span class="sxs-lookup"><span data-stu-id="e9b96-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="e9b96-134">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="e9b96-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="e9b96-135">Parametern _EnableSafeDocs_ aktiverar eller inaktiverar Säkra dokument för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="e9b96-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="e9b96-136">Parametern _AllowSafeDocsOpen_ tillåter eller hindrar användare från att lämna Skyddad vy (dvs. öppna dokumentet) om dokumentet har identifierats som skadligt.</span><span class="sxs-lookup"><span data-stu-id="e9b96-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="e9b96-137">Det här exemplet aktiverar Säkra dokument för hela organisationen och hindrar användare från att öppna dokument som har identifierats som skadliga från Skyddad vy.</span><span class="sxs-lookup"><span data-stu-id="e9b96-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="e9b96-138">Detaljerad information om syntax och parametrar finns i [Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="e9b96-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a><span data-ttu-id="e9b96-139">Gå till Microsoft Defender för slutpunktstjänsten för att aktivera granskningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="e9b96-139">Onboard to the Microsoft Defender for Endpoint Service to enable auditing capabilities</span></span>

<span data-ttu-id="e9b96-140">Om du vill distribuera Microsoft Defender för Endpoint måste du gå igenom de olika faserna i distributionen.</span><span class="sxs-lookup"><span data-stu-id="e9b96-140">To deploy Microsoft Defender for Endpoint, you need to go through the various phases of deployment.</span></span> <span data-ttu-id="e9b96-141">Efter introduktionen kan du konfigurera granskningsfunktionerna i Säkerhets- & efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="e9b96-141">After onboarding, you can configure auditing capabilities in the Security & Compliance Center.</span></span>

<span data-ttu-id="e9b96-142">Mer information finns i [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span><span class="sxs-lookup"><span data-stu-id="e9b96-142">To learn more, see [Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding).</span></span> <span data-ttu-id="e9b96-143">Om du behöver mer hjälp går du till Felsöka problem med [Microsoft Defender för slutpunkts onboarding.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)</span><span class="sxs-lookup"><span data-stu-id="e9b96-143">If you need additional help, please refer to [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="e9b96-144">Hur vet jag att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="e9b96-144">How do I know this worked?</span></span>

<span data-ttu-id="e9b96-145">Verifiera att du har aktiverat och konfigurerat säkra dokument genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="e9b96-145">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="e9b96-146">I Säkerhets- & och  \>  \> **efterlevnadscenter** går du till **ATP** för hothanteringspolicyn ATP – säkra bifogade filer , klickar på Globala inställningar och verifierar Aktivera säkra dokument för **Office-klienter** och Tillåt användare att klicka igenom Skyddad vy även om säkra dokument identifierar filen som skadlig.</span><span class="sxs-lookup"><span data-stu-id="e9b96-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="e9b96-147">Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdena:</span><span class="sxs-lookup"><span data-stu-id="e9b96-147">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="e9b96-148">Följande filer är tillgängliga för att testa skydd mot säkra dokument.</span><span class="sxs-lookup"><span data-stu-id="e9b96-148">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="e9b96-149">Dessa dokument liknar den EICAR.TXT filen för att testa skadlig programvara och antivirusprogram.</span><span class="sxs-lookup"><span data-stu-id="e9b96-149">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="e9b96-150">Filerna är inte skadliga, men de utlöser skydd för säkra dokument.</span><span class="sxs-lookup"><span data-stu-id="e9b96-150">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="e9b96-151">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="e9b96-151">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="e9b96-152">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="e9b96-152">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="e9b96-153">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="e9b96-153">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
