---
title: Konfigurera Azure Rights Management för den tidigare versionen av meddelandekryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: Den tidigare versionen Meddelandekryptering i Office 365 på Microsoft Azure Rights Management (kallades tidigare för Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162046"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="90efd-103">Konfigurera Azure Rights Management för den tidigare versionen av meddelandekryptering</span><span class="sxs-lookup"><span data-stu-id="90efd-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="90efd-104">I det här avsnittet beskrivs de steg du behöver följa för att aktivera och sedan konfigurera Azure Rights Management (RMS), en del av Azure Information Protection, för användning med den tidigare versionen av Meddelandekryptering i Office 365 (OME).</span><span class="sxs-lookup"><span data-stu-id="90efd-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="90efd-105">Den här artikeln gäller endast den tidigare versionen av OME</span><span class="sxs-lookup"><span data-stu-id="90efd-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="90efd-106">Om du ännu inte har flyttat organisationen till de nya OME-funktionerna, men redan har distribuerat OME, gäller informationen i den här artikeln för din organisation.</span><span class="sxs-lookup"><span data-stu-id="90efd-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="90efd-107">Microsoft rekommenderar att du gör en plan för att flytta över till de nya OME-funktionerna så snart det är lämpligt för din organisation.</span><span class="sxs-lookup"><span data-stu-id="90efd-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="90efd-108">Instruktioner finns i [Konfigurera nya Meddelandekryptering i Office 365 funktioner.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="90efd-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="90efd-109">Om du vill veta mer om hur de nya funktionerna fungerar först kan du läsa mer [i Meddelandekryptering i Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="90efd-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="90efd-110">Resten av den här artikeln refererar till OME-beteendet innan de nya OME-funktionerna släpps.</span><span class="sxs-lookup"><span data-stu-id="90efd-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="90efd-111">Krav för att använda den tidigare versionen av Meddelandekryptering i Office 365</span><span class="sxs-lookup"><span data-stu-id="90efd-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="90efd-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="90efd-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="90efd-113">Meddelandekryptering i Office 365 (OME), inklusive IRM, är beroende av Azure Rights Management (Azure RMS).</span><span class="sxs-lookup"><span data-stu-id="90efd-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="90efd-114">Azure RMS är den skyddsteknik som används av Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="90efd-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="90efd-115">Om du vill använda OME måste organisationen ha en Exchange Online- Exchange Online Protection-prenumeration som i sin tur omfattar en Azure Rights Management-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="90efd-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="90efd-116">Om du inte är säker på vad prenumerationen innehåller kan du läsa mer Exchange Online tjänstbeskrivningar för [Meddelandeprincip, Återställning och Efterlevnad.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="90efd-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

- <span data-ttu-id="90efd-117">Om du har Azure Rights Management men det inte är inställt för Exchange Online eller Exchange Online Protection förklarar den här artikeln hur du aktiverar Azure Rights Management och beskriver sedan det bästa sättet att konfigurera OME så att det fungerar med Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="90efd-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="90efd-118">Om du redan har ställt in OME att fungera med Azure Rights Management för Exchange Online eller Exchange Online Protection, beroende på hur du har ställt in det, kanske du är redo att börja använda OME och de nya funktionerna direkt.</span><span class="sxs-lookup"><span data-stu-id="90efd-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="90efd-119">I den här artikeln förklarar vi hur du tar reda på om du har ställt in OME korrekt, vad du kan göra om du behöver ändra inställningarna och vad som händer om du väljer att inte ändra inställningarna.</span><span class="sxs-lookup"><span data-stu-id="90efd-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="90efd-120">Om du till exempel vill använda de nya funktionerna måste du använda Azure RMS med OME.</span><span class="sxs-lookup"><span data-stu-id="90efd-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="90efd-121">Du kan inte använda de nya funktionerna med en lokal Active Directory RMS.</span><span class="sxs-lookup"><span data-stu-id="90efd-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="90efd-122">Aktivera Azure Rights Management för den tidigare versionen av OME i Office 365</span><span class="sxs-lookup"><span data-stu-id="90efd-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="90efd-123">Du måste aktivera Azure Rights Management så att användarna i organisationen kan tillämpa informationsskydd på meddelanden som de skickar och öppna meddelanden och filer som har skyddats av tjänsten Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="90efd-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="90efd-124">Anvisningar finns i [Aktivera Azure Rights Management.](/azure/information-protection/activate-service)</span><span class="sxs-lookup"><span data-stu-id="90efd-124">For instructions, see [Activating Azure Rights Management](/azure/information-protection/activate-service).</span></span> <span data-ttu-id="90efd-125">När du har slutfört aktiveringen återgår du hit och fortsätter med uppgifterna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="90efd-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="90efd-126">Konfigurera den tidigare versionen av OME att använda Azure RMS genom att importera betrodda publiceringsdomäner (TPDs)</span><span class="sxs-lookup"><span data-stu-id="90efd-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="90efd-127">En TPD är en XML-fil som innehåller information om organisationens rättighetshanteringsinställningar.</span><span class="sxs-lookup"><span data-stu-id="90efd-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="90efd-128">Till exempel innehåller TPD information om serverlicensorcertifikatet (SLC) som används för att signera och kryptera certifikat och licenser, webbadresserna som används för licensiering och publicering och så vidare.</span><span class="sxs-lookup"><span data-stu-id="90efd-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="90efd-129">Du importerar TPD till organisationen med hjälp av Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90efd-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="90efd-130">Tidigare kunde du välja att importera TPD:er från AD RMS (Active Directory Rights Management service) till organisationen.</span><span class="sxs-lookup"><span data-stu-id="90efd-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="90efd-131">Om du gör det kan du dock inte använda de nya OME-funktionerna, och det rekommenderas inte.</span><span class="sxs-lookup"><span data-stu-id="90efd-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="90efd-132">Om organisationen är konfigurerad på det här sättet rekommenderar Microsoft att du skapar en plan för migrering från din lokala Active Directory RMS till molnbaserat Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="90efd-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="90efd-133">Mer information finns i [Migrera från AD RMS till Azure Information Protection.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="90efd-133">For more information, see [Migrating from AD RMS to Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="90efd-134">Du kan inte använda de nya OME-funktionerna förrän du har slutfört migreringen till Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="90efd-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="90efd-135">**Importera TPD från Azure RMS**</span><span class="sxs-lookup"><span data-stu-id="90efd-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="90efd-136">[Anslut att Exchange Online använda Remote PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="90efd-136">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="90efd-137">Välj den URL för nyckeldelning som motsvarar organisationens geografiska plats:</span><span class="sxs-lookup"><span data-stu-id="90efd-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="90efd-138">**Plats**</span><span class="sxs-lookup"><span data-stu-id="90efd-138">**Location**</span></span>|<span data-ttu-id="90efd-139">**URL för nyckeldelningsplats**</span><span class="sxs-lookup"><span data-stu-id="90efd-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="90efd-140">Nordamerika</span><span class="sxs-lookup"><span data-stu-id="90efd-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="90efd-141">EU</span><span class="sxs-lookup"><span data-stu-id="90efd-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="90efd-142">Asien</span><span class="sxs-lookup"><span data-stu-id="90efd-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="90efd-143">Sydamerika</span><span class="sxs-lookup"><span data-stu-id="90efd-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="90efd-144">Office 365 för myndigheter (Government Community Cloud)</span><span class="sxs-lookup"><span data-stu-id="90efd-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="90efd-145">Den här RMS-nyckeldelningsplatsen är reserverad för kunder som har köpt Office 365 för myndighets-SKU:er.</span><span class="sxs-lookup"><span data-stu-id="90efd-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="90efd-146">Konfigurera nyckeldelningsplatsen genom att köra [cmdleten Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) enligt följande:</span><span class="sxs-lookup"><span data-stu-id="90efd-146">Configure the key-sharing location by running the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="90efd-147">Om du till exempel vill konfigurera nyckeldelningsplatsen om organisationen finns i Nordamerika:</span><span class="sxs-lookup"><span data-stu-id="90efd-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="90efd-148">Kör [cmdleten Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) med -RMSOnline-bytet för att importera TPD från Azure Rights Management:</span><span class="sxs-lookup"><span data-stu-id="90efd-148">Run the [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="90efd-149">Där  *TPDName*  är det namn du vill använda för TPD.</span><span class="sxs-lookup"><span data-stu-id="90efd-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="90efd-150">Till exempel "Contoso north american TPD".</span><span class="sxs-lookup"><span data-stu-id="90efd-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="90efd-151">Om du vill verifiera att organisationen har konfigurerats att använda Azure Rights Management-tjänsten kör du cmdlet:en [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) med -RMSOnline-bytet på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="90efd-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="90efd-152">Den här cmdleten kontrollerar bland annat anslutningen till Azure Rights Management-tjänsten, laddar ned TPD och kontrollerar dess giltighet.</span><span class="sxs-lookup"><span data-stu-id="90efd-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="90efd-153">Kör [cmdleten Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) enligt följande för att inaktivera Azure Rights Management-mallar så att de inte blir tillgängliga i Outlook på webben och Outlook:</span><span class="sxs-lookup"><span data-stu-id="90efd-153">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="90efd-154">Kör [cmdleten Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) enligt följande för att aktivera Azure Rights Management för din molnbaserade e-postorganisation och konfigurera den för användning med Azure Rights Management för Meddelandekryptering i Office 365:</span><span class="sxs-lookup"><span data-stu-id="90efd-154">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="90efd-155">Verifiera att du har importerat TPD och aktiverat Azure Rights Management genom att använda cmdleten Test-IRMConfiguration för att testa funktionerna i Azure Rights Management.</span><span class="sxs-lookup"><span data-stu-id="90efd-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="90efd-156">Mer information finns i "Exempel 1" i [Test-IRMConfiguration.](/powershell/module/exchange/test-irmconfiguration)</span><span class="sxs-lookup"><span data-stu-id="90efd-156">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="90efd-157">Jag har den tidigare versionen av OME konfigurerad med Active Directory Rights Management och inte Azure Information Protection, vad ska jag göra?</span><span class="sxs-lookup"><span data-stu-id="90efd-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="90efd-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="90efd-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="90efd-159">Du kan fortsätta att använda dina befintliga Meddelandekryptering i Office 365-postflödesregler med Active Directory Rights Management, men du kan inte konfigurera eller använda de nya OME-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="90efd-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="90efd-160">I stället måste du migrera till Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="90efd-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="90efd-161">Mer information om migrering och vad det innebär för organisationen finns i Migrera från [AD RMS till Azure Information Protection.](/information-protection/deploy-use/prepare-environment-adrms)</span><span class="sxs-lookup"><span data-stu-id="90efd-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="90efd-162">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="90efd-162">Next steps</span></span>
<span data-ttu-id="90efd-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="90efd-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="90efd-164">När du har slutfört konfigurationen av Azure Rights Management och vill aktivera de nya OME-funktionerna kan du gå till Konfigurera nya Meddelandekryptering i Office 365-funktioner som bygger på [Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="90efd-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)</span></span>
  
<span data-ttu-id="90efd-165">När du har ställt in din organisation på att använda de nya OME-funktionerna är du redo att Definiera e-postflödesregler för att skydda e-postmeddelanden [med nya OME-funktioner.](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="90efd-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="90efd-166">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="90efd-166">Related topics</span></span>
<span data-ttu-id="90efd-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="90efd-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="90efd-168">Kryptering i Office 365</span><span class="sxs-lookup"><span data-stu-id="90efd-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="90efd-169">Teknisk referensinformation om kryptering i Office 365</span><span class="sxs-lookup"><span data-stu-id="90efd-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="90efd-170">Vad är Azure Rights Management?</span><span class="sxs-lookup"><span data-stu-id="90efd-170">What is Azure Rights Management?</span></span>](/information-protection/understand-explore/what-is-azure-rms)