---
title: Säkra dokument i Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Lär dig mer om Safe-dokument i Microsoft 365 E5 eller Microsoft 365 E5 Security.
ms.openlocfilehash: 8918c7da26a60c7cfd64b7148d0added82cc6642
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949460"
---
# <a name="safe-documents-in-microsoft-365-e5"></a><span data-ttu-id="755ed-103">Säkra dokument i Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="755ed-103">Safe Documents in Microsoft 365 E5</span></span>

<span data-ttu-id="755ed-104">Säkra dokument är en funktion i Microsoft 365 E5-eller Microsoft 365 E5-säkerhet som använder [Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för att söka igenom dokument och filer som öppnas i [skyddad vy](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="755ed-104">Safe Documents is a feature in Microsoft 365 E5 or Microsoft 365 E5 Security that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="755ed-105">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="755ed-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="755ed-106">Säkra dokument är nu i allmänhet tillgängliga för användare med Office version 2004 (12730. x) eller senare.</span><span class="sxs-lookup"><span data-stu-id="755ed-106">Safe Documents is now generally available to users with Office Version 2004 (12730.x) or greater!</span></span> <span data-ttu-id="755ed-107">Den här funktionen är inaktive rad som standard och måste aktive ras av säkerhets administratören.</span><span class="sxs-lookup"><span data-stu-id="755ed-107">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="755ed-108">Den här funktionen är endast tillgänglig för användare med *microsoft 365 E5* -eller *Microsoft 365 E5-säkerhets* licens (ingår inte i Office 365 ATP-abonnemang).</span><span class="sxs-lookup"><span data-stu-id="755ed-108">This feature is only available to users with the *Microsoft 365 E5* or *Microsoft 365 E5 Security* license (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="755ed-109">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="755ed-109">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="755ed-110">Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="755ed-110">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="755ed-111">Mer information om</span><span class="sxs-lookup"><span data-stu-id="755ed-111">For more information about</span></span> 

- <span data-ttu-id="755ed-112">Du måste tilldelas behörigheter innan du kan utföra procedurerna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="755ed-112">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="755ed-113">För att aktivera och konfigurera säkra dokument måste du vara medlem i roll grupperna **organisations hantering** eller **säkerhets administratör** .</span><span class="sxs-lookup"><span data-stu-id="755ed-113">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="755ed-114">Mer information om rollgrupper i Säkerhets- och efterlevnadscenter finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="755ed-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="how-does-microsoft-handle-your-data"></a><span data-ttu-id="755ed-115">Hur hanterar Microsoft dina data?</span><span class="sxs-lookup"><span data-stu-id="755ed-115">How does Microsoft handle your data?</span></span>

<span data-ttu-id="755ed-116">För att skydda dig skickar säkra dokument filer till [Microsoft Defender Avancerat skydd för hotet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för analys.</span><span class="sxs-lookup"><span data-stu-id="755ed-116">To keep you protected, Safe Documents sends files to the [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) cloud for analysis.</span></span>

- <span data-ttu-id="755ed-117">Information om hur Microsoft Defender Avancerat skydd hanterar dina data finns [här](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span><span class="sxs-lookup"><span data-stu-id="755ed-117">Details on how Microsoft Defender Advanced Threat Protection handles your data can be found [here](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).</span></span>
- <span data-ttu-id="755ed-118">Utöver rikt linjerna ovan behålls inte filer som skickats av säkra dokument i Defender efter den tid som krävs för analys, vilket normalt är mindre än 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="755ed-118">In addition to the guidelines above, files sent by Safe Documents are not retained in Defender beyond the time needed for analysis, which is typically less than 24 hours.</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="755ed-119">Använda säkerhets & Compliance Center för att konfigurera betrodda dokument</span><span class="sxs-lookup"><span data-stu-id="755ed-119">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="755ed-120">Öppna säkerhets & Compliance Center på <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="755ed-120">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="755ed-121">Gå till policyn för **Threat Management** - \> **Policy** \> **säkerhets**meddelanden.</span><span class="sxs-lookup"><span data-stu-id="755ed-121">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="755ed-122">Konfigurera någon av följande inställningar i avsnittet **Hjälp personer att skydda utanför skyddad vy i Office-program** .</span><span class="sxs-lookup"><span data-stu-id="755ed-122">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="755ed-123">**Aktivera säkra dokument för Office-klienter**</span><span class="sxs-lookup"><span data-stu-id="755ed-123">**Turn on Safe Documents for Office clients**</span></span>

   - <span data-ttu-id="755ed-124">**Tillåt att personer klickar via skyddad vy även om säkra dokument identifierar filen som skadlig**: Vi rekommenderar att du inte aktiverar det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="755ed-124">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="755ed-125">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="755ed-125">When you're finished, click **Save**.</span></span>

![Sida med säkra filer för ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a><span data-ttu-id="755ed-127">Använda Exchange Online PowerShell eller fristående EOP PowerShell för att konfigurera betrodda dokument</span><span class="sxs-lookup"><span data-stu-id="755ed-127">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="755ed-128">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="755ed-128">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- <span data-ttu-id="755ed-129">Med parametern _EnableSafeDocs_ aktive ras eller inaktive ras säkra dokument för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="755ed-129">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="755ed-130">Med _AllowSafeDocsOpen_ -parametern kan du hindra användare från att lämna skyddad vy (det innebär att dokumentet öppnas) om dokumentet har identifierats som skadligt.</span><span class="sxs-lookup"><span data-stu-id="755ed-130">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="755ed-131">Det här exemplet aktiverar säkra dokument för hela organisationen och hindrar användarna från att öppna dokument som har identifierats som skadliga från skyddad vy.</span><span class="sxs-lookup"><span data-stu-id="755ed-131">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="755ed-132">Detaljerad information om syntax och parametrar finns i [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="755ed-132">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="755ed-133">Hur vet jag att det här fungerade?</span><span class="sxs-lookup"><span data-stu-id="755ed-133">How do I know this worked?</span></span>

<span data-ttu-id="755ed-134">Gör något av följande om du vill kontrol lera att du har aktiverat och konfigurerat säkra dokument:</span><span class="sxs-lookup"><span data-stu-id="755ed-134">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="755ed-135">I säkerhets & Compliance Center går du till **Threat Management** \> **policys** för inkommande \> **bifogade filer**och verifierar att de val du **gör för att skydda en fil som öppnas utanför skyddad vy i Office-program** .</span><span class="sxs-lookup"><span data-stu-id="755ed-135">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="755ed-136">Kör följande kommando i Exchange Online PowerShell och kontrol lera egenskapsvärdena:</span><span class="sxs-lookup"><span data-stu-id="755ed-136">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
