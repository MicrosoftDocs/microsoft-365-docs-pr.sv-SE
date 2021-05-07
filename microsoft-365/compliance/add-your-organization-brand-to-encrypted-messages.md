---
title: Lägga till organisationens varumärke i krypterade meddelanden
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Lär Office 365 hur globala administratörer kan använda företagets varumärke i krypterade e-postmeddelanden & innehållet på krypteringsportalen.
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162547"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="6bdab-103">Lägga till organisationens varumärke i meddelandekrypteringskryptering i Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="6bdab-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="6bdab-104">Du kan använda företagets varumärke för att anpassa utseendet på din organisations e-postmeddelanden och krypteringsportalen.</span><span class="sxs-lookup"><span data-stu-id="6bdab-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="6bdab-105">Du måste tillämpa global administratörsbehörighet på ditt arbets- eller skolkonto innan du kan komma igång.</span><span class="sxs-lookup"><span data-stu-id="6bdab-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="6bdab-106">När du har de här behörigheterna kan du använda cmdletarna Get-OMEConfiguration och Set-OMEConfiguration Windows PowerShell för att anpassa de här delarna av krypterade e-postmeddelanden:</span><span class="sxs-lookup"><span data-stu-id="6bdab-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="6bdab-107">Inledande text</span><span class="sxs-lookup"><span data-stu-id="6bdab-107">Introductory text</span></span>

- <span data-ttu-id="6bdab-108">Ansvarsfriskrivningstext</span><span class="sxs-lookup"><span data-stu-id="6bdab-108">Disclaimer text</span></span>

- <span data-ttu-id="6bdab-109">URL till din organisations sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="6bdab-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="6bdab-110">Text i OME-portalen</span><span class="sxs-lookup"><span data-stu-id="6bdab-110">Text in the OME portal</span></span>

- <span data-ttu-id="6bdab-111">Logotyp som visas i e-postmeddelandet och OME-portalen, eller om du ska använda en logotyp alls</span><span class="sxs-lookup"><span data-stu-id="6bdab-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="6bdab-112">Bakgrundsfärg i e-postmeddelandet och OME-portalen</span><span class="sxs-lookup"><span data-stu-id="6bdab-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="6bdab-113">Du kan också när som helst återgå till standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="6bdab-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="6bdab-114">Om du vill ha mer kontroll kan du använda Office 365 Advanced Message Encryption skapa flera mallar för krypterade e-postmeddelanden som kommer från organisationen.</span><span class="sxs-lookup"><span data-stu-id="6bdab-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="6bdab-115">Använd de här mallarna för att styra delar av slutanvändarupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="6bdab-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="6bdab-116">Ange till exempel om mottagare kan använda Google, Yahoo och Microsoft-konton för att logga in på krypteringsportalen.</span><span class="sxs-lookup"><span data-stu-id="6bdab-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="6bdab-117">Använd mallar för att uppfylla flera användningsfall, till exempel:</span><span class="sxs-lookup"><span data-stu-id="6bdab-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="6bdab-118">Enskilda avdelningar, till exempel ekonomi, försäljning och så vidare.</span><span class="sxs-lookup"><span data-stu-id="6bdab-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="6bdab-119">Olika produkter</span><span class="sxs-lookup"><span data-stu-id="6bdab-119">Different products</span></span>

- <span data-ttu-id="6bdab-120">Olika geografiska regioner eller länder</span><span class="sxs-lookup"><span data-stu-id="6bdab-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="6bdab-121">Om du vill tillåta att e-postmeddelanden återkallas</span><span class="sxs-lookup"><span data-stu-id="6bdab-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="6bdab-122">Om du vill att e-postmeddelanden som skickas till externa mottagare ska upphöra att gälla efter ett angivet antal dagar.</span><span class="sxs-lookup"><span data-stu-id="6bdab-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="6bdab-123">När du har skapat mallarna kan du använda dem i krypterade e-postmeddelanden genom att Exchange e-postflödesregler.</span><span class="sxs-lookup"><span data-stu-id="6bdab-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="6bdab-124">Om du har Office 365 Advanced Message Encryption kan du återkalla alla e-postmeddelanden som du har profilerat med hjälp av dessa mallar.</span><span class="sxs-lookup"><span data-stu-id="6bdab-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="6bdab-125">Arbeta med varumärkesmallar för OME</span><span class="sxs-lookup"><span data-stu-id="6bdab-125">Work with OME branding templates</span></span>

<span data-ttu-id="6bdab-126">Du kan ändra flera funktioner i en varumärkesmall.</span><span class="sxs-lookup"><span data-stu-id="6bdab-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="6bdab-127">Du kan ändra, men inte ta bort, standardmallen.</span><span class="sxs-lookup"><span data-stu-id="6bdab-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="6bdab-128">Om du har Avancerad meddelandekryptering kan du också skapa, ändra och ta bort anpassade mallar.</span><span class="sxs-lookup"><span data-stu-id="6bdab-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="6bdab-129">Använd Windows PowerShell att arbeta med en varumärkesmall i taget.</span><span class="sxs-lookup"><span data-stu-id="6bdab-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="6bdab-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) – Ändra standardmallen för profilering eller en anpassad varumärkesmall som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="6bdab-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="6bdab-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) – Skapa en ny varumärkesmall, endast avancerad meddelandekryptering.</span><span class="sxs-lookup"><span data-stu-id="6bdab-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="6bdab-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) – Ta bort en anpassad varumärkesmall, endast avancerad meddelandekryptering.</span><span class="sxs-lookup"><span data-stu-id="6bdab-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="6bdab-133">Du kan inte ta bort standardmallen för profilering.</span><span class="sxs-lookup"><span data-stu-id="6bdab-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="6bdab-134">Ändra en OME-varumärkesmall</span><span class="sxs-lookup"><span data-stu-id="6bdab-134">Modify an OME branding template</span></span>

<span data-ttu-id="6bdab-135">Använd Windows PowerShell att ändra en varumärkesmall i taget.</span><span class="sxs-lookup"><span data-stu-id="6bdab-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="6bdab-136">Om du har Avancerad meddelandekryptering kan du också skapa, ändra och ta bort anpassade mallar.</span><span class="sxs-lookup"><span data-stu-id="6bdab-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="6bdab-137">Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6bdab-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="6bdab-138">Instruktioner finns i [Anslut för Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="6bdab-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="6bdab-139">Använd Set-OMEConfiguration cmdlet enligt beskrivningen i [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) eller använd följande grafik och tabell för vägledning.</span><span class="sxs-lookup"><span data-stu-id="6bdab-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![Anpassningsbara e-postdelar](../media/ome-template-breakout.png)

|<span data-ttu-id="6bdab-141">**Så här anpassar du den här funktionen i krypteringsupplevelsen**</span><span class="sxs-lookup"><span data-stu-id="6bdab-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="6bdab-142">**Använd de här kommandona**</span><span class="sxs-lookup"><span data-stu-id="6bdab-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6bdab-143">Bakgrundsfärg</span><span class="sxs-lookup"><span data-stu-id="6bdab-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="6bdab-144">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="6bdab-145">Mer information om bakgrundsfärger finns i avsnittet [Bakgrundsfärger längre](#background-color-reference) fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6bdab-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="6bdab-146">Logotyp</span><span class="sxs-lookup"><span data-stu-id="6bdab-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="6bdab-147">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="6bdab-148">Filformat som stöds: .png, .jpg, .bmp eller .tiff</span><span class="sxs-lookup"><span data-stu-id="6bdab-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="6bdab-149">Optimal storlek på logotypfilen: mindre än 40 kB</span><span class="sxs-lookup"><span data-stu-id="6bdab-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="6bdab-150">Optimal storlek på logotypbild: 170 x 70 bildpunkter.</span><span class="sxs-lookup"><span data-stu-id="6bdab-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="6bdab-151">Om bilden överskrider de här måtten ändrar tjänsten storlek på din logotyp för visning i portalen.</span><span class="sxs-lookup"><span data-stu-id="6bdab-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="6bdab-152">Tjänsten ändrar inte själva grafikfilen.</span><span class="sxs-lookup"><span data-stu-id="6bdab-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="6bdab-153">För bästa resultat bör du använda optimal storlek.</span><span class="sxs-lookup"><span data-stu-id="6bdab-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="6bdab-154">Text bredvid avsändarens namn och e-postadress</span><span class="sxs-lookup"><span data-stu-id="6bdab-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="6bdab-155">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="6bdab-156">Text som visas på knappen "Läs upp meddelande"</span><span class="sxs-lookup"><span data-stu-id="6bdab-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="6bdab-157">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="6bdab-158">Text som visas under knappen "Läs meddelande"</span><span class="sxs-lookup"><span data-stu-id="6bdab-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="6bdab-159">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="6bdab-160">URL för länken Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="6bdab-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="6bdab-161">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="6bdab-162">Ansvarsfriskrivningsutdrag i e-postmeddelandet som innehåller det krypterade meddelandet</span><span class="sxs-lookup"><span data-stu-id="6bdab-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="6bdab-163">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="6bdab-164">Text som visas högst upp i visningsportalen för krypterade e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="6bdab-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="6bdab-165">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="6bdab-166">Aktivera eller inaktivera autentisering med ett lösenord för den här anpassade mallen</span><span class="sxs-lookup"><span data-stu-id="6bdab-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="6bdab-167">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-167">**Examples:**</span></span> <br/><span data-ttu-id="6bdab-168">Så här aktiverar du lösenord för en gång för den här anpassade mallen</span><span class="sxs-lookup"><span data-stu-id="6bdab-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="6bdab-169">Inaktivera lösenord för en gång för den här anpassade mallen</span><span class="sxs-lookup"><span data-stu-id="6bdab-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="6bdab-170">Aktivera eller inaktivera autentisering med Microsoft-, Google- eller Yahoo-identiteter för den här anpassade mallen</span><span class="sxs-lookup"><span data-stu-id="6bdab-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="6bdab-171">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-171">**Examples:**</span></span> <br/><span data-ttu-id="6bdab-172">Så här aktiverar du sociala ID för den här anpassade mallen</span><span class="sxs-lookup"><span data-stu-id="6bdab-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="6bdab-173">Så här inaktiverar du sociala ID för den här anpassade mallen</span><span class="sxs-lookup"><span data-stu-id="6bdab-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="6bdab-174">Skapa en OME-varumärkesmall (avancerad meddelandekryptering)</span><span class="sxs-lookup"><span data-stu-id="6bdab-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="6bdab-175">Om du har Office 365 Advanced Message Encryption kan du skapa anpassade varumärkesmallar för din organisation med hjälp av cmdleten [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="6bdab-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="6bdab-176">När du har skapat mallen kan du ändra mallen med hjälp av cmdleten Set-OMEConfiguration som beskrivs i Ändra en [OME-varumärkesmall.](#modify-an-ome-branding-template)</span><span class="sxs-lookup"><span data-stu-id="6bdab-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="6bdab-177">Du kan skapa flera mallar.</span><span class="sxs-lookup"><span data-stu-id="6bdab-177">You can create multiple templates.</span></span>

<span data-ttu-id="6bdab-178">Så här skapar du en ny anpassad varumärkesmall:</span><span class="sxs-lookup"><span data-stu-id="6bdab-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="6bdab-179">Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6bdab-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="6bdab-180">Instruktioner finns i [Anslut för Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="6bdab-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="6bdab-181">Använd [cmdleten New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) för att skapa en ny mall.</span><span class="sxs-lookup"><span data-stu-id="6bdab-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="6bdab-182">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="6bdab-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="6bdab-183">Returnera standardmallen för varumärkesmall till dess ursprungliga värden</span><span class="sxs-lookup"><span data-stu-id="6bdab-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="6bdab-184">Om du vill ta bort alla ändringar från standardmallen, inklusive varumärkesanpassningar och så vidare, slutför du de här stegen:</span><span class="sxs-lookup"><span data-stu-id="6bdab-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="6bdab-185">Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6bdab-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="6bdab-186">Instruktioner finns i [Anslut för Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="6bdab-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="6bdab-187">Använd **cmdleten Set-OMEConfiguration** enligt beskrivningen i [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="6bdab-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="6bdab-188">Om du vill ta bort organisationens anpassningar av ansvarsfriskrivningstext, e-posttext och portaltext anger du värdet som en tom `""` sträng.</span><span class="sxs-lookup"><span data-stu-id="6bdab-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="6bdab-189">För alla bildvärden, till exempel Logotyp, ställer du in värdet på  `"$null"` .</span><span class="sxs-lookup"><span data-stu-id="6bdab-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="6bdab-190">I följande tabell beskrivs standardinställningen för krypteringsalternativ.</span><span class="sxs-lookup"><span data-stu-id="6bdab-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="6bdab-191">Om du vill återställa den här funktionen i krypteringen till standardtexten och standardbilden</span><span class="sxs-lookup"><span data-stu-id="6bdab-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="6bdab-192">Använd de här kommandona</span><span class="sxs-lookup"><span data-stu-id="6bdab-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="6bdab-193">Standardtext som medföljer krypterade e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="6bdab-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="6bdab-194">Standardtexten visas ovanför instruktionerna för att visa krypterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="6bdab-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="6bdab-195">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="6bdab-196">Ansvarsfriskrivningsutdrag i e-postmeddelandet som innehåller det krypterade meddelandet</span><span class="sxs-lookup"><span data-stu-id="6bdab-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="6bdab-197">**Exempel:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="6bdab-198">Text som visas högst upp i visningsportalen för krypterade e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="6bdab-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="6bdab-199">**Exempel som återställer till standard:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="6bdab-200">Logotyp</span><span class="sxs-lookup"><span data-stu-id="6bdab-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="6bdab-201">**Exempel som återställer till standard:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="6bdab-202">Bakgrundsfärg</span><span class="sxs-lookup"><span data-stu-id="6bdab-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="6bdab-203">**Exempel som återställer till standard:**</span><span class="sxs-lookup"><span data-stu-id="6bdab-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="6bdab-204">Ta bort en anpassad varumärkesmall (Avancerad meddelandekryptering)</span><span class="sxs-lookup"><span data-stu-id="6bdab-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="6bdab-205">Du kan bara ta bort anpassade mallar som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="6bdab-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="6bdab-206">Du kan inte ta bort standardmallen för profilering.</span><span class="sxs-lookup"><span data-stu-id="6bdab-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="6bdab-207">Så här tar du bort en anpassad varumärkesmall:</span><span class="sxs-lookup"><span data-stu-id="6bdab-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="6bdab-208">Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6bdab-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="6bdab-209">Instruktioner finns i [Anslut för Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="6bdab-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="6bdab-210">Använd **cmdleten Remove-OMEConfiguration** enligt följande:</span><span class="sxs-lookup"><span data-stu-id="6bdab-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="6bdab-211">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="6bdab-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="6bdab-212">Mer information finns i [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span><span class="sxs-lookup"><span data-stu-id="6bdab-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="6bdab-213">Skapa en Exchange e-postflödesregel som tillämpar din anpassade profilering på krypterade e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="6bdab-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="6bdab-214">När du antingen har ändrat standardmallen eller skapat nya varumärkesmallar kan du skapa Exchange-postflödesregler för att tillämpa din anpassade profilering utifrån vissa villkor.</span><span class="sxs-lookup"><span data-stu-id="6bdab-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="6bdab-215">En sådan regel kommer att tillämpa anpassad profilering i följande scenarier:</span><span class="sxs-lookup"><span data-stu-id="6bdab-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="6bdab-216">Om e-postmeddelandet krypterades manuellt av slutanvändaren med hjälp Outlook eller Outlook på webben, tidigare Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="6bdab-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="6bdab-217">Om e-postmeddelandet automatiskt krypterades av Exchange e-postflödesregel eller princip för dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="6bdab-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="6bdab-218">Mer information om hur du skapar en Exchange-postflödesregel som tillämpar kryptering finns i Definiera e-postflödesregler för att [kryptera e-postmeddelanden i Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="6bdab-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="6bdab-219">Använd ett arbets- eller skolkonto som har beviljats global administratörsbehörighet i en webbläsare och logga [in på Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span><span class="sxs-lookup"><span data-stu-id="6bdab-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="6bdab-220">Välj **panelen** Admin.</span><span class="sxs-lookup"><span data-stu-id="6bdab-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="6bdab-221">Välj Microsoft 365 administrationscenter i **administrationscentret** \> **för Exchange**.</span><span class="sxs-lookup"><span data-stu-id="6bdab-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="6bdab-222">I EAC går du till **E-postflödesregler** \>  och väljer **Ny** ny ikon Skapa en ![ ny ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regel.**</span><span class="sxs-lookup"><span data-stu-id="6bdab-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="6bdab-223">Mer information om hur du använder EAC finns Exchange [administrationscenter i Exchange Online](/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="6bdab-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="6bdab-224">I **Namn** anger du ett namn på regeln, till exempel Profilering för säljavdelningen.</span><span class="sxs-lookup"><span data-stu-id="6bdab-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="6bdab-225">I **Använd den här regeln** om väljer du villkoret **Avsändaren** finns i organisationen och andra villkor som du vill använda i listan med tillgängliga villkor.</span><span class="sxs-lookup"><span data-stu-id="6bdab-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="6bdab-226">Du kanske till exempel vill använda en viss varumärkesmall för:</span><span class="sxs-lookup"><span data-stu-id="6bdab-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="6bdab-227">Alla krypterade e-postmeddelanden som skickas från medlemmar på ekonomiavdelningen</span><span class="sxs-lookup"><span data-stu-id="6bdab-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="6bdab-228">Krypterade e-postmeddelanden som skickas med ett visst nyckelord, till exempel "Extern" eller "Partner"</span><span class="sxs-lookup"><span data-stu-id="6bdab-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="6bdab-229">Krypterade e-postmeddelanden som skickas till en viss domän</span><span class="sxs-lookup"><span data-stu-id="6bdab-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="6bdab-230">Från **Gör följande väljer du** Ändra **meddelandets säkerhet Tillämpa** anpassad anpassning på \> **OME-meddelanden.**</span><span class="sxs-lookup"><span data-stu-id="6bdab-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="6bdab-231">Välj sedan en varumärkesmall i listrutan.</span><span class="sxs-lookup"><span data-stu-id="6bdab-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="6bdab-232">(Valfritt) Du kan konfigurera e-postflödesregeln så att kryptering och anpassad profilering tillämpas.</span><span class="sxs-lookup"><span data-stu-id="6bdab-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="6bdab-233">Från **Gör följande väljer** du Ändra **meddelandets säkerhet** och sedan Apply Meddelandekryptering i Office 365 and rights **protection**.</span><span class="sxs-lookup"><span data-stu-id="6bdab-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="6bdab-234">Välj en RMS-mall i listan, **välj Spara** och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="6bdab-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="6bdab-235">Listan med mallar innehåller standardmallar och alternativ samt eventuella anpassade mallar som du skapar.</span><span class="sxs-lookup"><span data-stu-id="6bdab-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="6bdab-236">Om listan är tom, kontrollera att du har Meddelandekryptering i Office 365 med de nya funktionerna.</span><span class="sxs-lookup"><span data-stu-id="6bdab-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="6bdab-237">Instruktioner finns i [Konfigurera nya Meddelandekryptering i Office 365 funktioner.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="6bdab-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="6bdab-238">Mer information om standardmallar finns i Konfigurera [och hantera mallar för Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates)</span><span class="sxs-lookup"><span data-stu-id="6bdab-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="6bdab-239">Mer information om alternativet **Vidarebefordra inte finns i** alternativet Vidarebefordra inte för [e-postmeddelanden.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="6bdab-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="6bdab-240">Mer information om det enda **alternativet för kryptering finns** i Alternativet Kryptera endast för [e-postmeddelanden.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="6bdab-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="6bdab-241">Välj **Lägg till åtgärd** om du vill ange en annan åtgärd.</span><span class="sxs-lookup"><span data-stu-id="6bdab-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="6bdab-242">Bakgrundsfärgreferens</span><span class="sxs-lookup"><span data-stu-id="6bdab-242">Background color reference</span></span>

<span data-ttu-id="6bdab-243">Färgnamnen som du kan använda för bakgrundsfärgen är begränsade.</span><span class="sxs-lookup"><span data-stu-id="6bdab-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="6bdab-244">I stället för ett färgnamn kan du använda ett hexkodsvärde (#RRGGBB).</span><span class="sxs-lookup"><span data-stu-id="6bdab-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="6bdab-245">Du kan använda ett hexkodvärde som motsvarar ett färgnamn eller så kan du använda ett anpassat hexkodsvärde.</span><span class="sxs-lookup"><span data-stu-id="6bdab-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="6bdab-246">Se till att omge det hexadecigrafiska kodvärdet med citattecken (till exempel `"#f0f8ff"` ).</span><span class="sxs-lookup"><span data-stu-id="6bdab-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="6bdab-247">De tillgängliga namnen på bakgrundsfärgerna och deras motsvarande hexadexkodvärden beskrivs i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6bdab-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="6bdab-248">**Färgnamn**</span><span class="sxs-lookup"><span data-stu-id="6bdab-248">**Color name**</span></span>|<span data-ttu-id="6bdab-249">**Färgkod**</span><span class="sxs-lookup"><span data-stu-id="6bdab-249">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="6bdab-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="6bdab-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="6bdab-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="6bdab-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="6bdab-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="6bdab-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="6bdab-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="6bdab-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="6bdab-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="6bdab-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="6bdab-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="6bdab-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="6bdab-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="6bdab-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="6bdab-257">#000000</span><span class="sxs-lookup"><span data-stu-id="6bdab-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="6bdab-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="6bdab-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="6bdab-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="6bdab-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="6bdab-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="6bdab-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="6bdab-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="6bdab-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="6bdab-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="6bdab-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="6bdab-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="6bdab-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="6bdab-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="6bdab-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="6bdab-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="6bdab-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="6bdab-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="6bdab-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="6bdab-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="6bdab-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="6bdab-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="6bdab-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="6bdab-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="6bdab-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="6bdab-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="6bdab-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="6bdab-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="6bdab-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="6bdab-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="6bdab-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="6bdab-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="6bdab-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="6bdab-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="6bdab-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="6bdab-275">#006400</span><span class="sxs-lookup"><span data-stu-id="6bdab-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="6bdab-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="6bdab-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="6bdab-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="6bdab-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="6bdab-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="6bdab-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="6bdab-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="6bdab-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="6bdab-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="6bdab-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="6bdab-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="6bdab-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="6bdab-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="6bdab-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="6bdab-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="6bdab-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="6bdab-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="6bdab-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="6bdab-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="6bdab-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="6bdab-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="6bdab-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="6bdab-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="6bdab-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="6bdab-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="6bdab-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="6bdab-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="6bdab-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="6bdab-290">#696969</span><span class="sxs-lookup"><span data-stu-id="6bdab-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="6bdab-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="6bdab-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="6bdab-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="6bdab-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="6bdab-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="6bdab-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="6bdab-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="6bdab-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="6bdab-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="6bdab-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="6bdab-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="6bdab-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="6bdab-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="6bdab-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="6bdab-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="6bdab-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="6bdab-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="6bdab-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="6bdab-300">#808080</span><span class="sxs-lookup"><span data-stu-id="6bdab-300">#808080</span></span>|
|`green`|<span data-ttu-id="6bdab-301">#008000</span><span class="sxs-lookup"><span data-stu-id="6bdab-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="6bdab-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="6bdab-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="6bdab-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="6bdab-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="6bdab-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="6bdab-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="6bdab-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="6bdab-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="6bdab-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="6bdab-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="6bdab-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="6bdab-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="6bdab-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="6bdab-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="6bdab-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="6bdab-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="6bdab-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="6bdab-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="6bdab-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="6bdab-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="6bdab-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="6bdab-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="6bdab-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="6bdab-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="6bdab-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="6bdab-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="6bdab-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="6bdab-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="6bdab-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="6bdab-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="6bdab-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="6bdab-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="6bdab-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="6bdab-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="6bdab-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="6bdab-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="6bdab-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="6bdab-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="6bdab-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="6bdab-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="6bdab-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="6bdab-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="6bdab-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="6bdab-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="6bdab-324">#778899</span><span class="sxs-lookup"><span data-stu-id="6bdab-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="6bdab-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="6bdab-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="6bdab-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="6bdab-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="6bdab-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="6bdab-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="6bdab-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="6bdab-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="6bdab-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="6bdab-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="6bdab-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="6bdab-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="6bdab-331">#800000</span><span class="sxs-lookup"><span data-stu-id="6bdab-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="6bdab-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="6bdab-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="6bdab-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="6bdab-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="6bdab-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="6bdab-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="6bdab-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="6bdab-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="6bdab-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="6bdab-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="6bdab-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="6bdab-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="6bdab-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="6bdab-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="6bdab-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="6bdab-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="6bdab-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="6bdab-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="6bdab-341">#191970</span><span class="sxs-lookup"><span data-stu-id="6bdab-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="6bdab-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="6bdab-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="6bdab-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="6bdab-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="6bdab-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="6bdab-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="6bdab-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="6bdab-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="6bdab-346">#000080</span><span class="sxs-lookup"><span data-stu-id="6bdab-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="6bdab-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="6bdab-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="6bdab-348">#808000</span><span class="sxs-lookup"><span data-stu-id="6bdab-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="6bdab-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="6bdab-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="6bdab-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="6bdab-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="6bdab-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="6bdab-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="6bdab-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="6bdab-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="6bdab-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="6bdab-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="6bdab-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="6bdab-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="6bdab-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="6bdab-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="6bdab-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="6bdab-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="6bdab-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="6bdab-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="6bdab-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="6bdab-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="6bdab-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="6bdab-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="6bdab-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="6bdab-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="6bdab-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="6bdab-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="6bdab-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="6bdab-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="6bdab-363">#800080</span><span class="sxs-lookup"><span data-stu-id="6bdab-363">#800080</span></span>|
|`red`|<span data-ttu-id="6bdab-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="6bdab-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="6bdab-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="6bdab-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="6bdab-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="6bdab-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="6bdab-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="6bdab-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="6bdab-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="6bdab-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="6bdab-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="6bdab-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="6bdab-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="6bdab-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="6bdab-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="6bdab-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="6bdab-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="6bdab-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="6bdab-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="6bdab-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="6bdab-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="6bdab-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="6bdab-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="6bdab-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="6bdab-376">#708090</span><span class="sxs-lookup"><span data-stu-id="6bdab-376">#708090</span></span>|
|`snow`|<span data-ttu-id="6bdab-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="6bdab-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="6bdab-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="6bdab-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="6bdab-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="6bdab-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="6bdab-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="6bdab-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="6bdab-381">#008080</span><span class="sxs-lookup"><span data-stu-id="6bdab-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="6bdab-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="6bdab-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="6bdab-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="6bdab-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="6bdab-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="6bdab-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="6bdab-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="6bdab-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="6bdab-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="6bdab-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="6bdab-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="6bdab-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="6bdab-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="6bdab-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="6bdab-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="6bdab-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="6bdab-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="6bdab-390">#9acd32</span></span>|