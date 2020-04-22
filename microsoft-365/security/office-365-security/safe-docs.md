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
description: Lär dig mer om säkra dokument i Office 365 ATP.
ms.openlocfilehash: b70c7013ce038a3934b7ea5e62d1d0530f12e4e6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634322"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a><span data-ttu-id="91173-103">Säkra dokument i avancerat hotskydd i Office 365</span><span class="sxs-lookup"><span data-stu-id="91173-103">Safe Documents in Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="91173-104">Säkra dokument är en funktion i Office 365 Advanced Threat Protection (ATP) som använder [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) för att skanna dokument och filer som öppnas i [skyddad vy](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span><span class="sxs-lookup"><span data-stu-id="91173-104">Safe Documents is a feature in Office 365 Advanced Threat Protection (ATP) that uses [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) to scan documents and files that are opened in [Protected View](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="91173-105">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="91173-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="91173-106">Den här funktionen är endast tillgänglig för användare med Microsoft 365 E5- eller Microsoft 365 E5 Security-licensen.</span><span class="sxs-lookup"><span data-stu-id="91173-106">This feature is only available to users with the Microsoft 365 E5 or Microsoft 365 E5 Security license.</span></span>

- <span data-ttu-id="91173-107">Säkra dokument är för närvarande tillgängliga för offentlig förhandsversion, som är tillgängliga för användare som ingår i [Office Insider-programmet](https://insider.office.com/en-us/join) på månadskanalen (Targeted)' med Office Version 2002 (12527.20092) eller mer.</span><span class="sxs-lookup"><span data-stu-id="91173-107">Safe Documents is currently available for public preview, available to users that are part of the [Office Insider Program](https://insider.office.com/en-us/join) on the 'Monthly Channel (Targeted)' with Office Version 2002 (12527.20092) or greater.</span></span> <span data-ttu-id="91173-108">Den här funktionen är inaktiverad som standard och måste aktiveras av säkerhetsadministratören.</span><span class="sxs-lookup"><span data-stu-id="91173-108">This feature is off by default and will need to be enabled by the Security Administrator.</span></span>

- <span data-ttu-id="91173-109">Endast usa-region som för närvarande stöds för kompatibel filbearbetning (Alla filer kommer att resa till den amerikanska regionen för skanning).</span><span class="sxs-lookup"><span data-stu-id="91173-109">Only US Region currently supported for compliant file processing (All files will travel to the US Region for scanning).</span></span> <span data-ttu-id="91173-110">Stöd till Storbritannien/EU-regionen planeras i en framtida uppdatering.</span><span class="sxs-lookup"><span data-stu-id="91173-110">Support for UK/EU region is planned in a future update.</span></span>

- <span data-ttu-id="91173-111">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="91173-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="91173-112">Information om hur du ansluter till Exchange Online Protection PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="91173-112">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="91173-113">Du måste tilldelas behörigheter innan du kan utföra procedurerna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="91173-113">You need to be assigned permissions before you can perform the procedures in this topic.</span></span> <span data-ttu-id="91173-114">Om du vill aktivera och konfigurera säkra dokument måste du vara medlem i rollgrupperna **Organisationshantering** eller **Säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="91173-114">To enable and configure Safe Documents, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="91173-115">Mer information om rollgrupper i Security & Compliance Center finns [i Behörigheter i Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="91173-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a><span data-ttu-id="91173-116">Använda Security & Compliance Center för att konfigurera säkra dokument</span><span class="sxs-lookup"><span data-stu-id="91173-116">Use the Security & Compliance Center to configure Safe Documents</span></span>

1. <span data-ttu-id="91173-117">Öppna Säkerhets- & Compliance Center <https://protection.office.com>på .</span><span class="sxs-lookup"><span data-stu-id="91173-117">Open the Security & Compliance Center at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="91173-118">Gå till **ATP-säkra bilagor för** **hothanteringsprincip** \> **Policy** \> .</span><span class="sxs-lookup"><span data-stu-id="91173-118">Go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

3. <span data-ttu-id="91173-119">Konfigurera någon av följande inställningar när du litar på en fil för att öppna utanför skyddad vy i Office-program i hjälpen för personer som är säkra när de **litar på en fil för att öppna utanför skyddad vy i Office-program:**</span><span class="sxs-lookup"><span data-stu-id="91173-119">In the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section, configure either of the following settings:</span></span>

   - <span data-ttu-id="91173-120">**Aktivera säkra dokument för Office-klienter (Filer skickas också till Microsoft Cloud för djupgående analyser)**</span><span class="sxs-lookup"><span data-stu-id="91173-120">**Turn on Safe Documents for Office clients (Files will also be sent to Microsoft Cloud for deep analyses)**</span></span>

   - <span data-ttu-id="91173-121">**Tillåt personer att klicka sig igenom Skyddad vy även om säkra dokument identifierar filen som skadlig:** Vi rekommenderar att du inte aktiverar det här alternativet.</span><span class="sxs-lookup"><span data-stu-id="91173-121">**Allow people to click through Protected View even if Safe Documents identifies the file as malicious**: We recommend that you don't enable this option.</span></span>

4. <span data-ttu-id="91173-122">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="91173-122">When you're finished, click **Save**.</span></span>

![ATP Säkra bilagor sida](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a><span data-ttu-id="91173-124">Använda Exchange Online PowerShell eller Exchange Online Protection PowerShell för att konfigurera säkra dokument</span><span class="sxs-lookup"><span data-stu-id="91173-124">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure Safe Documents</span></span>

<span data-ttu-id="91173-125">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="91173-125">Use the following syntax:</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- <span data-ttu-id="91173-126">Parametern _EnableSafeDocs_ aktiverar eller inaktiverar säkra dokument för hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="91173-126">The _EnableSafeDocs_ parameter enables or disables Safe Documents for the entire organization.</span></span>

- <span data-ttu-id="91173-127">Parametern _AllowSafeDocsOpen_ gör det möjligt eller hindrar användare från att lämna skyddad vy (det vill än att öppna dokumentet) om dokumentet har identifierats som skadligt.</span><span class="sxs-lookup"><span data-stu-id="91173-127">The _AllowSafeDocsOpen_ parameter allows or prevents users from leaving Protected View (that is, opening the document) if the document has been identified as malicious.</span></span>

<span data-ttu-id="91173-128">Det här exemplet aktiverar säkra dokument för hela organisationen och hindrar användare från att öppna dokument som har identifierats som skadliga från skyddad vy.</span><span class="sxs-lookup"><span data-stu-id="91173-128">This example enables Safe Documents for the entire organization, and prevents users from opening documents that have been identified as malicious from Protected View.</span></span>

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

<span data-ttu-id="91173-129">Detaljerad syntax- och parameterinformation finns i [Ange-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span><span class="sxs-lookup"><span data-stu-id="91173-129">For detailed syntax and parameter information, see [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).</span></span>

### <a name="how-do-i-know-this-worked"></a><span data-ttu-id="91173-130">Hur vet jag att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="91173-130">How do I know this worked?</span></span>

<span data-ttu-id="91173-131">Så här kontrollerar du att du har aktiverat och konfigurerat säkra dokument:</span><span class="sxs-lookup"><span data-stu-id="91173-131">To verify that you've enabled and configured Safe Documents, do any of the following steps:</span></span>

- <span data-ttu-id="91173-132">I Security & Compliance Center går du till **ATP-betrodda bilagor**för **hothanteringsprincip** \> **Policy** \> och verifierar valen i **hjälppersonerna att vara säkra när de litar på en fil för att öppna utanför skyddad vy i Office-program.**</span><span class="sxs-lookup"><span data-stu-id="91173-132">In the Security & Compliance Center go to **Threat management** \> **Policy** \> **ATP Safe Attachments**, and verify the selections in the **Help people stay safe when trusting a file to open outside Protected View in Office applications** section.</span></span>

- <span data-ttu-id="91173-133">Kör följande kommando i Exchange Online PowerShell och verifiera egenskapsvärdena:</span><span class="sxs-lookup"><span data-stu-id="91173-133">Run the following command in Exchange Online PowerShell and verify the property values:</span></span>

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
