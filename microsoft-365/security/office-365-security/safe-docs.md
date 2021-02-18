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
ms.openlocfilehash: a3f4ed3535c7e53774b9b567b50f7c06e99cef9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288591"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="4409a-103">Säkra dokument i Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4409a-103">Safe Documents in Microsoft 365 E5</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4409a-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="4409a-104">**Applies to**</span></span>
- [<span data-ttu-id="4409a-105">Microsoft Defender för Office 365 abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="4409a-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="4409a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4409a-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="4409a-107">Säkra dokument är en funktion i Microsoft 365 E5 eller Microsoft 365 E5-säkerhet som använder [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för Slutpunkt för att söka igenom dokument och filer som öppnas i [Skyddad vy.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)</span><span class="sxs-lookup"><span data-stu-id="4409a-107">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4409a-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="4409a-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4409a-109">Säkra dokument är endast tillgängliga för användare med Säkerhetslicenser för *Microsoft 365 E5* eller *Microsoft 365 E5.*</span><span class="sxs-lookup"><span data-stu-id="4409a-109">Safe Documents is available only to users with *Microsoft 365 E5* or *Microsoft 365 E5 Security* licenses.</span></span> <span data-ttu-id="4409a-110">Licenserna ingår inte i Microsoft Defender för Office 365-abonnemang.</span><span class="sxs-lookup"><span data-stu-id="4409a-110">These licenses are not included in Microsoft Defender for Office 365 plans.</span></span>

- <span data-ttu-id="4409a-111">Säkra dokument stöds i Microsoft 365-appar för företag (kallades tidigare Office 365 ProPlus) version 2004 eller senare.</span><span class="sxs-lookup"><span data-stu-id="4409a-111">Safe Documents is supported in Microsoft 365 Apps for enterprise (formerly known as Office 365 ProPlus) version 2004 or later.</span></span>

- <span data-ttu-id="4409a-112">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="4409a-112">You open the Security & Compliance Center at <https://protection.office.com>.</span></span> <span data-ttu-id="4409a-113">Gå direkt till **atp-sidan för säkra bifogade** filer genom att <https://protection.office.com/safeattachmentv2> öppna.</span><span class="sxs-lookup"><span data-stu-id="4409a-113">To go directly to the **ATP Safe Attachments** page, open <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="4409a-114">Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4409a-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="4409a-115">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="4409a-115">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4409a-116">Om du vill konfigurera inställningarna för säkra dokument måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="4409a-116">To configure Safe Documents settings, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4409a-117">För skrivskyddade åtkomst till inställningarna för säkra dokument måste du vara medlem i rollgrupperna **Global Reader** **eller** Säkerhetsläsare.</span><span class="sxs-lookup"><span data-stu-id="4409a-117">For read-only access to Safe Documents settings, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4409a-118">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4409a-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="4409a-119">Genom att lägga till användare i motsvarande Azure Active Directory-rollen i Administrationscentret för Microsoft 365 får användarna den behörighet som krävs i Säkerhets- och efterlevnadscentret _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4409a-119">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4409a-120">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="4409a-120">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="4409a-121">Rollgruppen **Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ger också skrivskyddad åtkomst till funktionen.</span><span class="sxs-lookup"><span data-stu-id="4409a-121">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

### <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="4409a-122">Hur hanterar Microsoft dina data?</span><span class="sxs-lookup"><span data-stu-id="4409a-122">How does Microsoft handle your data?</span></span>

<span data-ttu-id="4409a-123">Om du vill skydda dig skickas filer till Microsoft [Defender för slutpunktsmoln](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för analys.</span><span class="sxs-lookup"><span data-stu-id="4409a-123">To keep you protected, Safe Documents sends files to the [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span> <span data-ttu-id="4409a-124">Information om hur Microsoft Defender för Endpoint hanterar dina data finns här: Microsoft Defender för [slutpunktens datalagring och sekretess.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="4409a-124">Details on how Microsoft Defender for Endpoint handles your data can be found here: [Microsoft Defender for Endpoint data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>

<span data-ttu-id="4409a-125">Filer som skickas av säkra dokument sparas inte i Defender utöver den tid som krävs för analys (vanligtvis mindre än 24 timmar).</span><span class="sxs-lookup"><span data-stu-id="4409a-125">Files sent by Safe Documents are not retained in Defender beyond the time needed for analysis (typically, less than 24 hours).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="4409a-126">Använda Säkerhets- & center för att konfigurera säkra dokument</span><span class="sxs-lookup"><span data-stu-id="4409a-126">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="4409a-127">Gå till  ATP & för hanteringspolicy för säkerhet och säkerhet i Säkerhets- och efterlevnadscenter och klicka sedan \>  \> på **Globala inställningar.**</span><span class="sxs-lookup"><span data-stu-id="4409a-127">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="4409a-128">I den **globala inställningsfällan** som visas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="4409a-128">In the **Global settings** fly out that appears, configure the following settings:</span></span>

   - <span data-ttu-id="4409a-129">**Aktivera Säkra dokument för Office-klienter:** Flytta reglaget till höger för att aktivera funktionen: ![ ](../../media/scc-toggle-on.png) Aktivera.</span><span class="sxs-lookup"><span data-stu-id="4409a-129">**Turn on Safe Documents for Office clients**: Move the toggle to the right to turn on the feature: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="4409a-130">Tillåt att andra klickar i Skyddad vy även om filen identifieras som skadlig i Säkra dokument: Vi rekommenderar att du låter det här alternativet vara inaktiverat (låt **växlingsknappen** vara ![ inaktiverad ](../../media/scc-toggle-off.png) till vänster).</span><span class="sxs-lookup"><span data-stu-id="4409a-130">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you leave this option turned off (leave the toggle to the left: ![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="4409a-131">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="4409a-131">When you're finished, click **Save**.</span></span>

   ![Inställningarna för säkra dokument när du har valt Globala inställningar på sidan Säkra bifogade filer.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a><span data-ttu-id="4409a-133">Använda Exchange Online PowerShell för att konfigurera säkra dokument</span><span class="sxs-lookup"><span data-stu-id="4409a-133">Use Exchange Online PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="4409a-134">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="4409a-134">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="4409a-135">Parametern _EnableSafeDocs_ aktiverar eller inaktiverar säkra dokument för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="4409a-135">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>
- <span data-ttu-id="4409a-136">Parametern _AllowSafeDocsOpen_ tillåter eller förhindrar användare från att lämna Skyddad vy (dvs. öppna dokumentet) om dokumentet har identifierats som skadligt.</span><span class="sxs-lookup"><span data-stu-id="4409a-136">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="4409a-137">Det här exemplet aktiverar Säkra dokument för hela organisationen och hindrar användare från att öppna dokument som har identifierats som skadliga från Skyddad vy.</span><span class="sxs-lookup"><span data-stu-id="4409a-137">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="4409a-138">Detaljerad information om syntax och parametrar finns [i Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)</span><span class="sxs-lookup"><span data-stu-id="4409a-138">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="4409a-139">Hur vet jag att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="4409a-139">How do I know this worked?</span></span>

<span data-ttu-id="4409a-140">Kontrollera att du har aktiverat och konfigurerat Säkra dokument genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="4409a-140">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="4409a-141">I Säkerhets- &  \>  \> **Efterlevnadscenter** går du till **ATP**(Hanteringspolicy för hothanteringspolicy) – säkra bifogade filer, klickar på Globala inställningar och kontrollerar aktivera Säkra dokument för **Office-klienter** och tillåter användare att klicka igenom Skyddad vy även om säkra dokument identifierar filen som skadlig.</span><span class="sxs-lookup"><span data-stu-id="4409a-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, click **Global settings**, and verify the **Turn on Safe Documents for Office clients** and **Allow people to click through Protected View even if Safe Documents identifies the file as malicious** settings.</span></span>

- <span data-ttu-id="4409a-142">Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdena:</span><span class="sxs-lookup"><span data-stu-id="4409a-142">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- <span data-ttu-id="4409a-143">Följande filer är tillgängliga för att testa skyddet mot säkra dokument.</span><span class="sxs-lookup"><span data-stu-id="4409a-143">The following files are available to test Safe Documents protection.</span></span> <span data-ttu-id="4409a-144">Dessa dokument liknar filen EICAR.TXT för att testa antivirus- och antiviruslösningar.</span><span class="sxs-lookup"><span data-stu-id="4409a-144">These documents are similar to the EICAR.TXT file for testing anti-malware and anti-virus solutions.</span></span> <span data-ttu-id="4409a-145">Filerna är inte skadliga, men de utlöser skydd för säkra dokument.</span><span class="sxs-lookup"><span data-stu-id="4409a-145">The files are not harmful, but they will trigger Safe Documents protection.</span></span>

  - [<span data-ttu-id="4409a-146">SafeDocsDemo.docx</span><span class="sxs-lookup"><span data-stu-id="4409a-146">SafeDocsDemo.docx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [<span data-ttu-id="4409a-147">SafeDocsDemo.pptx</span><span class="sxs-lookup"><span data-stu-id="4409a-147">SafeDocsDemo.pptx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [<span data-ttu-id="4409a-148">SafeDocsDemo.xlsx</span><span class="sxs-lookup"><span data-stu-id="4409a-148">SafeDocsDemo.xlsx</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
