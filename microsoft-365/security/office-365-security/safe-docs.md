---
title: Säkra dokument i Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Lär dig mer om säkra dokument i Microsoft 365 E5 eller Microsoft 365 E5 Security.
ms.openlocfilehash: c574e28a01dc961d898638184afe9ece90e31133
ms.sourcegitcommit: aa7f7350d1342ff9713bb840b2cc96d1a4234ef4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2020
ms.locfileid: "44835357"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="b7ea1-103">Säkra dokument i Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b7ea1-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="b7ea1-104">Säkra dokument är en funktion i Microsoft 365 E5 eller Microsoft 365 E5 Security som använder [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för att skanna dokument och filer som öppnas i [skyddad vy](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="b7ea1-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b7ea1-105">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="b7ea1-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b7ea1-106">Säkra dokument är nu allmänt tillgängliga för användare med Office Version 2004 (12730.x) eller mer!</span><span class="sxs-lookup"><span data-stu-id="b7ea1-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="b7ea1-107">Den här funktionen är inaktiverad som standard och måste aktiveras av säkerhetsadministratören.</span><span class="sxs-lookup"><span data-stu-id="b7ea1-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="b7ea1-108">Den här funktionen är endast tillgänglig för användare med *Microsoft 365 E5-* eller *Microsoft 365 E5 Security-licensen* (ingår inte i Office 365 ATP-abonnemang).</span><span class="sxs-lookup"><span data-stu-id="b7ea1-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="b7ea1-109">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b7ea1-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="b7ea1-110">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="b7ea1-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="b7ea1-111">Du måste tilldelas behörigheter innan du kan utföra procedurerna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b7ea1-111">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="b7ea1-112">Om du vill aktivera och konfigurera säkra dokument måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="b7ea1-112">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="b7ea1-113">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b7ea1-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="b7ea1-114">Hur hanterar Microsoft dina data?</span><span class="sxs-lookup"><span data-stu-id="b7ea1-114">How does Microsoft handle your data?</span></span>

<span data-ttu-id="b7ea1-115">För att skydda dig skickar säkra dokument filer till [Microsoft Defender Advanced Threat Protection-molnet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för analys.</span><span class="sxs-lookup"><span data-stu-id="b7ea1-115">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="b7ea1-116">Information om hur Microsoft Defender Advanced Threat Protection hanterar dina data finns [här](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span><span class="sxs-lookup"><span data-stu-id="b7ea1-116">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)</span></span>
- <span data-ttu-id="b7ea1-117">Utöver riktlinjerna ovan behålls inte filer som skickas av säkra dokument i Defender efter den tid som behövs för analys, vilket vanligtvis är mindre än 24 timmar</span><span class="sxs-lookup"><span data-stu-id="b7ea1-117">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="b7ea1-118">Använda Security & Compliance Center för att konfigurera säkra dokument</span><span class="sxs-lookup"><span data-stu-id="b7ea1-118">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="b7ea1-119">Öppna Säkerhets- & Compliance Center på <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="b7ea1-119">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="b7ea1-120">Gå **Threat management** till \> **Policy** \> **ATP-säkra bilagor för**hothanteringspolicy .</span><span class="sxs-lookup"><span data-stu-id="b7ea1-120">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="b7ea1-121">Konfigurera någon av följande inställningar när du litar på en fil för att öppna utanför skyddad vy i Office-program i hjälpen när de **litar på en fil för att öppna utanför Skyddad vy i Office-program:**</span><span class="sxs-lookup"><span data-stu-id="b7ea1-121">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="b7ea1-122">**Aktivera säkra dokument för Office-klienter**</span><span class="sxs-lookup"><span data-stu-id="b7ea1-122">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="b7ea1-123">**Tillåt personer att klicka sig igenom Skyddad vy även om säkra dokument identifierar filen som skadlig:** Vi rekommenderar att du inte aktiverar det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="b7ea1-123">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="b7ea1-124">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="b7ea1-124">When you're finished, click **Save**.</span></span>

![ATP Säkra bilagor sida](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="b7ea1-126">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera säkra dokument</span><span class="sxs-lookup"><span data-stu-id="b7ea1-126">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="b7ea1-127">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="b7ea1-127">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="b7ea1-128">Parametern _EnableSafeDocs_ aktiverar eller inaktiverar säkra dokument för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="b7ea1-128">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="b7ea1-129">Parametern _AllowSafeDocsOpen_ gör det möjligt eller hindrar användare från att lämna skyddad vy (det vill än att öppna dokumentet) om dokumentet har identifierats som skadligt.</span><span class="sxs-lookup"><span data-stu-id="b7ea1-129">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="b7ea1-130">Det här exemplet aktiverar säkra dokument för hela organisationen och hindrar användare från att öppna dokument som har identifierats som skadliga från skyddad vy.</span><span class="sxs-lookup"><span data-stu-id="b7ea1-130">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="b7ea1-131">Detaljerad syntax- och parameterinformation finns i [Ange-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="b7ea1-131">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="b7ea1-132">Hur vet jag att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="b7ea1-132">How do I know this worked?</span></span>

<span data-ttu-id="b7ea1-133">Så här kontrollerar du att du har aktiverat och konfigurerat säkra dokument:</span><span class="sxs-lookup"><span data-stu-id="b7ea1-133">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="b7ea1-134">I Security & Compliance Center **Threat management** går du till \> **Policy** \> **ATP-betrodda bilagor**för hothanteringsprincip och verifierar valen i **hjälppersonerna att vara säkra när de litar på en fil för att öppna utanför skyddad vy i Office-program.**</span><span class="sxs-lookup"><span data-stu-id="b7ea1-134">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="b7ea1-135">Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdena:</span><span class="sxs-lookup"><span data-stu-id="b7ea1-135">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
