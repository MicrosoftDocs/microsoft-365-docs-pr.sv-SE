---
title: Konfigurera IRM att använda en lokal AD RMS-server
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Läs om hur du konfigurerar IRM (Information Rights Management) i Exchange Online att använda en AD RMS-server (Active Directory Rights Management Service).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c42d793639a9efaf94e3222a172ea192d1e03d3
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227241"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="11cfd-103">Konfigurera IRM att använda en lokal AD RMS-server</span><span class="sxs-lookup"><span data-stu-id="11cfd-103">Configure IRM to use an on-premises AD RMS server</span></span>

<span data-ttu-id="11cfd-104">För användning med lokala distributioner använder IRM (Information Rights Management) i Exchange Online Active Directory Rights Management Services (AD RMS), en teknik för informationsskydd i Windows Server 2008 och senare.</span><span class="sxs-lookup"><span data-stu-id="11cfd-104">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later.</span></span> <span data-ttu-id="11cfd-105">IRM-skydd tillämpas på e-post genom att använda en principmall för AD RMS-rättigheter i ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="11cfd-105">IRM protection is applied to email by applying an AD RMS rights policy template to an email message.</span></span> <span data-ttu-id="11cfd-106">Rättigheter bifogas själva meddelandet så att skydd sker online och offline och inom och utanför organisationens brandvägg.</span><span class="sxs-lookup"><span data-stu-id="11cfd-106">Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>

<span data-ttu-id="11cfd-107">I det här avsnittet finns information om hur du konfigurerar IRM för användning av en AD RMS-server.</span><span class="sxs-lookup"><span data-stu-id="11cfd-107">This topic shows you how to configure IRM to use an AD RMS server.</span></span> <span data-ttu-id="11cfd-108">Information om hur du använder de nya funktionerna för Meddelandekryptering i Office 365 med Azure Active Directory och Azure Rights Management finns i Vanliga [frågor Meddelandekryptering i Office 365 Azure Rights Management.](./ome-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="11cfd-108">For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](./ome-faq.yml).</span></span>

<span data-ttu-id="11cfd-109">Mer information om IRM i Exchange Online finns [i Information Rights Management i Exchange Online.](information-rights-management-in-exchange-online.md)</span><span class="sxs-lookup"><span data-stu-id="11cfd-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="11cfd-110">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="11cfd-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="11cfd-111">Beräknad tid för att slutföra aktiviteten: 30 minuter</span><span class="sxs-lookup"><span data-stu-id="11cfd-111">Estimated time to complete this task: 30 minutes</span></span>

- <span data-ttu-id="11cfd-112">Du måste ha tilldelats behörigheter för att kunna utföra den här proceduren eller procedurerna.</span><span class="sxs-lookup"><span data-stu-id="11cfd-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="11cfd-113">Du kan se vilka behörigheter du behöver i "Information Rights Management" i avsnittet behörigheter för [meddelandepolicyer och efterlevnad (PÅ).](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions)</span><span class="sxs-lookup"><span data-stu-id="11cfd-113">To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) topic.</span></span>

- <span data-ttu-id="11cfd-114">AD RMS-servern måste köra Windows Server 2008 eller senare.</span><span class="sxs-lookup"><span data-stu-id="11cfd-114">The AD RMS server must be running Windows Server 2008 or later.</span></span> <span data-ttu-id="11cfd-115">Mer information om hur du distribuerar AD RMS finns i [Installera ett AD RMS-kluster.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="11cfd-115">For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).</span></span>

- <span data-ttu-id="11cfd-116">Mer information om hur du installerar och konfigurerar Windows PowerShell och ansluter till tjänsten finns i konfigurera [Anslut att Exchange Online med Remote PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="11cfd-116">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="11cfd-117">Mer information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i Kortkommandon för administrationscentret [Exchange i Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)</span><span class="sxs-lookup"><span data-stu-id="11cfd-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="11cfd-118">Har du problem?</span><span class="sxs-lookup"><span data-stu-id="11cfd-118">Having problems?</span></span> <span data-ttu-id="11cfd-119">Be om hjälp i Exchange forum.</span><span class="sxs-lookup"><span data-stu-id="11cfd-119">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="11cfd-120">Besök forumen på [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)eller [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="11cfd-120">Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span>

## <a name="how-do-you-do-this"></a><span data-ttu-id="11cfd-121">Hur gör du det?</span><span class="sxs-lookup"><span data-stu-id="11cfd-121">How do you do this?</span></span>
<span data-ttu-id="11cfd-122"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="11cfd-122"><a name="sectionSection1"> </a></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="11cfd-123">Steg 1: Använd AD RMS-konsolen för att exportera en betrodd publiceringsdomän (TPD) från en AD RMS-server</span><span class="sxs-lookup"><span data-stu-id="11cfd-123">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="11cfd-124">Det första steget är att exportera en betrodd publiceringsdomän (TPD) från den lokala AD RMS-servern till en XML-fil.</span><span class="sxs-lookup"><span data-stu-id="11cfd-124">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file.</span></span> <span data-ttu-id="11cfd-125">TPD innehåller följande inställningar för att använda RMS-funktioner:</span><span class="sxs-lookup"><span data-stu-id="11cfd-125">The TPD contains the following settings needed to use RMS features:</span></span>

- <span data-ttu-id="11cfd-126">Serverlicensorcertifikatet (SLC) som används för att signera och kryptera certifikat och licenser</span><span class="sxs-lookup"><span data-stu-id="11cfd-126">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>

- <span data-ttu-id="11cfd-127">URL:er som används för licensiering och publicering</span><span class="sxs-lookup"><span data-stu-id="11cfd-127">The URLs used for licensing and publishing</span></span>

- <span data-ttu-id="11cfd-128">Principmallarna för AD RMS-rättigheter som skapades med det specifika SLC för den TPD</span><span class="sxs-lookup"><span data-stu-id="11cfd-128">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>

<span data-ttu-id="11cfd-129">När du importerar TPD lagras och skyddas den i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="11cfd-129">When you import the TPD, it's stored and protected in Exchange Online.</span></span>

1. <span data-ttu-id="11cfd-130">Öppna Active Directory Rights Management Services och expandera AD RMS-klustret.</span><span class="sxs-lookup"><span data-stu-id="11cfd-130">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>

2. <span data-ttu-id="11cfd-131">Expandera Förtroendeprinciper i **konsolträdet och** klicka sedan på **Betrodda publiceringsdomäner.**</span><span class="sxs-lookup"><span data-stu-id="11cfd-131">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>

3. <span data-ttu-id="11cfd-132">I resultatfönstret väljer du certifikatet för den domän som du vill exportera.</span><span class="sxs-lookup"><span data-stu-id="11cfd-132">In the results pane, select the certificate for the domain you want to export.</span></span>

4. <span data-ttu-id="11cfd-133">Klicka på **Exportera** betrodd publiceringsdomän **i fönstret Åtgärder.**</span><span class="sxs-lookup"><span data-stu-id="11cfd-133">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>

5. <span data-ttu-id="11cfd-134">Klicka på **Spara som i** rutan Publiceringsdomänfil för att spara filen på en viss plats på den lokala datorn. </span><span class="sxs-lookup"><span data-stu-id="11cfd-134">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer.</span></span> <span data-ttu-id="11cfd-135">Skriv ett filnamn, se till att ange  `.xml` filnamnstillägget och klicka sedan på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="11cfd-135">Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>

6. <span data-ttu-id="11cfd-136">I **rutorna** Lösenord **och Bekräfta** lösenord anger du ett starkt lösenord som ska användas för att kryptera den betrodda publiceringsdomänfilen.</span><span class="sxs-lookup"><span data-stu-id="11cfd-136">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file.</span></span> <span data-ttu-id="11cfd-137">Du måste ange det här lösenordet när du importerar TPD till din molnbaserade e-postorganisation.</span><span class="sxs-lookup"><span data-stu-id="11cfd-137">You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span>

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="11cfd-138">Steg 2: Använd Exchange Management Shell för att importera TPD-Exchange Online</span><span class="sxs-lookup"><span data-stu-id="11cfd-138">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="11cfd-139">När TPD har exporterats till en XML-fil måste du importera den till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="11cfd-139">After the TPD is exported to an XML file, you have to import it to Exchange Online.</span></span> <span data-ttu-id="11cfd-140">När en TPD importeras importeras även organisationens AD RMS-mallar.</span><span class="sxs-lookup"><span data-stu-id="11cfd-140">When a TPD is imported, your organization's AD RMS templates are also imported.</span></span> <span data-ttu-id="11cfd-141">När den första TPD har importerats blir den standard-TPD för den molnbaserade organisationen.</span><span class="sxs-lookup"><span data-stu-id="11cfd-141">When the first TPD is imported, it becomes the default TPD for your cloud-based organization.</span></span> <span data-ttu-id="11cfd-142">Om du importerar en annan TPD kan du använda standardväxeln för att göra den till den standard-TPD som är tillgänglig för användare. </span><span class="sxs-lookup"><span data-stu-id="11cfd-142">If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span>

<span data-ttu-id="11cfd-143">Du importerar TPD genom att köra följande kommando i Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="11cfd-143">To import the TPD, run the following command in Windows PowerShell:</span></span>

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="11cfd-144">Du kan hämta värdena för parametrarna _ExtranetLicensingUrl_ och _IntranetLicensingUrl_ i Active Directory Rights Management Services konsolen.</span><span class="sxs-lookup"><span data-stu-id="11cfd-144">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console.</span></span> <span data-ttu-id="11cfd-145">Välj AD RMS-klustret i konsolträdet.</span><span class="sxs-lookup"><span data-stu-id="11cfd-145">Select the AD RMS cluster in the console tree.</span></span> <span data-ttu-id="11cfd-146">Url-adresser för licensiering visas i resultatfönstret.</span><span class="sxs-lookup"><span data-stu-id="11cfd-146">The licensing URLs are displayed in the results pane.</span></span> <span data-ttu-id="11cfd-147">Dessa URL:er används av e-postklienter när innehållet måste dekrypteras och när Exchange Online behöver avgöra vilken TPD som ska användas.</span><span class="sxs-lookup"><span data-stu-id="11cfd-147">These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span>

<span data-ttu-id="11cfd-148">När du kör det här kommandot uppmanas du att ange ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="11cfd-148">When you run this command, you'll be prompted for a password.</span></span> <span data-ttu-id="11cfd-149">Ange det lösenord som du angav när du exporterade TPD från AD RMS-servern.</span><span class="sxs-lookup"><span data-stu-id="11cfd-149">Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>

<span data-ttu-id="11cfd-150">Med följande kommando importeras till exempel TPD med namnet Exporterad TPD med den XML-fil du exporterade från AD RMS-servern och sparades på skrivbordet i administratörskontot.</span><span class="sxs-lookup"><span data-stu-id="11cfd-150">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account.</span></span> <span data-ttu-id="11cfd-151">Parametern Name används för att ange ett namn på TPD.</span><span class="sxs-lookup"><span data-stu-id="11cfd-151">The Name parameter is used to specify a name to the TPD.</span></span>

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="11cfd-152">Detaljerad information om syntax och parametrar finns i [Import-RMSTrustedPublishingDomain.](/powershell/module/exchange/import-rmstrustedpublishingdomain)</span><span class="sxs-lookup"><span data-stu-id="11cfd-152">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).</span></span>

#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="11cfd-153">Hur vet du att det här steget fungerade?</span><span class="sxs-lookup"><span data-stu-id="11cfd-153">How do you know this step worked?</span></span>

<span data-ttu-id="11cfd-154">Kontrollera att du har importerat TPD genom att köra cmdleten **Get-RMSTrustedPublishingDomain** för att hämta TPD:er i Exchange Online organisationen.</span><span class="sxs-lookup"><span data-stu-id="11cfd-154">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization.</span></span> <span data-ttu-id="11cfd-155">Mer information finns i exemplen i [Get-RMSTrustedPublishingDomain.](/powershell/module/exchange/get-rmstrustedpublishingdomain)</span><span class="sxs-lookup"><span data-stu-id="11cfd-155">For details, see the examples in [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).</span></span>

### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="11cfd-156">Steg 3: Använda Exchange Management Shell för att distribuera en PRINCIPmall för AD RMS-rättigheter</span><span class="sxs-lookup"><span data-stu-id="11cfd-156">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="11cfd-157">När du har importerat TPD måste du se till att en principmall för AD RMS-rättigheter distribueras.</span><span class="sxs-lookup"><span data-stu-id="11cfd-157">After you import the TPD, you must make sure an AD RMS rights policy template is distributed.</span></span> <span data-ttu-id="11cfd-158">En distribuerad mall visas för Outlook på webben (tidigare kallat Outlook Web App), som sedan kan använda mallarna i ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="11cfd-158">A distributed template is visible to Outlook on the web (formerly known as Outlook Web App) users, who can then apply the templates to an email message.</span></span>

<span data-ttu-id="11cfd-159">Om du vill returnera en lista över alla mallar som finns i standard-TPD kör du följande kommando:</span><span class="sxs-lookup"><span data-stu-id="11cfd-159">To return a list of all templates contained in the default TPD, run the following command:</span></span>

```powershell
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="11cfd-160">Om parameterns  _värde_ är  `Archived` , visas inte mallen för användarna.</span><span class="sxs-lookup"><span data-stu-id="11cfd-160">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users.</span></span> <span data-ttu-id="11cfd-161">Endast distribuerade mallar i standard-TPD är tillgängliga i Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="11cfd-161">Only distributed templates in the default TPD are available in Outlook on the web.</span></span>

<span data-ttu-id="11cfd-162">Kör följande kommando för att distribuera en mall:</span><span class="sxs-lookup"><span data-stu-id="11cfd-162">To distribute a template, run the following command:</span></span>

```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="11cfd-163">Följande kommando importerar till exempel mallen Konfidentiellt.</span><span class="sxs-lookup"><span data-stu-id="11cfd-163">For example, the following command imports the Company Confidential template.</span></span>

```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="11cfd-164">Detaljerad information om syntax och parametrar finns i [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) och [Set-RMSTemplate.](/powershell/module/exchange/set-rmstemplate)</span><span class="sxs-lookup"><span data-stu-id="11cfd-164">For detailed syntax and parameter information, see [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) and [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).</span></span>

<span data-ttu-id="11cfd-165">**Mallen Vidarebefordra inte**</span><span class="sxs-lookup"><span data-stu-id="11cfd-165">**The Do Not Forward template**</span></span>

<span data-ttu-id="11cfd-166">När du importerar standard-TPD från den lokala organisationen till Exchange Online importeras en AD RMS-rättighetsprincipmall med namnet Vidarebefordra **inte.**</span><span class="sxs-lookup"><span data-stu-id="11cfd-166">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported.</span></span> <span data-ttu-id="11cfd-167">Som standard distribueras den här mallen när du importerar standard-TPD.</span><span class="sxs-lookup"><span data-stu-id="11cfd-167">By default, this template is distributed when you import the default TPD.</span></span> <span data-ttu-id="11cfd-168">Du kan inte använda **cmdleten Set-RMSTemplate** till att ändra mallen **Vidarebefordra inte.**</span><span class="sxs-lookup"><span data-stu-id="11cfd-168">You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span>

<span data-ttu-id="11cfd-169">När mallen **Vidarebefordra inte används** för ett meddelande kan bara meddelandets mottagare läsa det.</span><span class="sxs-lookup"><span data-stu-id="11cfd-169">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message.</span></span> <span data-ttu-id="11cfd-170">Dessutom kan mottagarna inte göra följande:</span><span class="sxs-lookup"><span data-stu-id="11cfd-170">Additionally, recipients can't do the following:</span></span>

- <span data-ttu-id="11cfd-171">Vidarebefordra meddelandet till en annan person.</span><span class="sxs-lookup"><span data-stu-id="11cfd-171">Forward the message to another person.</span></span>

- <span data-ttu-id="11cfd-172">Kopiera innehåll från meddelandet.</span><span class="sxs-lookup"><span data-stu-id="11cfd-172">Copy content from the message.</span></span>

- <span data-ttu-id="11cfd-173">Skriv ut meddelandet.</span><span class="sxs-lookup"><span data-stu-id="11cfd-173">Print the message.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11cfd-174">Mallen **Vidarebefordra inte kan** inte förhindra att information i ett meddelande kopieras med skärmbilder från tredje part, kameror eller användare som manuellt transkriberar informationen</span><span class="sxs-lookup"><span data-stu-id="11cfd-174">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span>

<span data-ttu-id="11cfd-175">Du kan skapa ytterligare principmallar för AD RMS-rättigheter på AD RMS-servern i den lokala organisationen för att uppfylla dina IRM-krav.</span><span class="sxs-lookup"><span data-stu-id="11cfd-175">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements.</span></span> <span data-ttu-id="11cfd-176">Om du skapar ytterligare principmallar för AD RMS-rättigheter måste du exportera TPD från den lokala AD RMS-servern igen och uppdatera TPD:t i den molnbaserade e-postorganisationen.</span><span class="sxs-lookup"><span data-stu-id="11cfd-176">If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span>

#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="11cfd-177">Hur vet du att det här steget fungerade?</span><span class="sxs-lookup"><span data-stu-id="11cfd-177">How do you know this step worked?</span></span>

<span data-ttu-id="11cfd-178">Kontrollera att du har distribuerat principen för och AD RMS-rättighetsprincipen genom att köra cmdlet:en **Get-RMSTemplate** för att kontrollera mallens egenskaper.</span><span class="sxs-lookup"><span data-stu-id="11cfd-178">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties.</span></span> <span data-ttu-id="11cfd-179">Mer information finns i exemplen i [Get-RMSTemplate.](/powershell/module/exchange/get-rmstemplate)</span><span class="sxs-lookup"><span data-stu-id="11cfd-179">For details, see the examples in [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).</span></span>

### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="11cfd-180">Steg 4: Aktivera IRM med Exchange Management Shell</span><span class="sxs-lookup"><span data-stu-id="11cfd-180">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="11cfd-181">När du har importerat och distribuerat en principmall för AD RMS-rättigheter kör du följande kommando för att aktivera IRM för din molnbaserade e-postorganisation.</span><span class="sxs-lookup"><span data-stu-id="11cfd-181">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>

```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="11cfd-182">Detaljerad information om syntax och parametrar finns i [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).</span><span class="sxs-lookup"><span data-stu-id="11cfd-182">For detailed syntax and parameter information, see [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).</span></span>

#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="11cfd-183">Hur vet du att det här steget fungerade?</span><span class="sxs-lookup"><span data-stu-id="11cfd-183">How do you know this step worked?</span></span>

<span data-ttu-id="11cfd-184">Kontrollera att du har aktiverat IRM genom att köra cmdleten [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) för att kontrollera IRM-konfigurationen i Exchange Online organisation.</span><span class="sxs-lookup"><span data-stu-id="11cfd-184">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) cmdlet to check IRM configuration in the Exchange Online organization.</span></span>

## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="11cfd-185">Hur vet du att den här uppgiften fungerade?</span><span class="sxs-lookup"><span data-stu-id="11cfd-185">How do you know this task worked?</span></span>
<span data-ttu-id="11cfd-186"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="11cfd-186"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="11cfd-187">Så här kontrollerar du att du har importerat TPD och aktiverat IRM:</span><span class="sxs-lookup"><span data-stu-id="11cfd-187">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>

- <span data-ttu-id="11cfd-188">Använd **cmdleten Test-IRMConfiguration** för att testa IRM-funktioner.</span><span class="sxs-lookup"><span data-stu-id="11cfd-188">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality.</span></span> <span data-ttu-id="11cfd-189">Mer information finns i "Exempel 1" i [Test-IRMConfiguration.](/powershell/module/exchange/test-irmconfiguration)</span><span class="sxs-lookup"><span data-stu-id="11cfd-189">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

- <span data-ttu-id="11cfd-190">Skriv ett nytt meddelande i Outlook på webben IRM-skydda  det genom att välja alternativet Ange behörigheter i den utökade menyn ![ (ikonen Fler ](../media/ITPro-EAC-MoreOptionsIcon.gif) alternativ).</span><span class="sxs-lookup"><span data-stu-id="11cfd-190">Compose a new message in Outlook on the web and IRM-protect it by selecting **Set permissions** option from the extended menu (![More Options Icon](../media/ITPro-EAC-MoreOptionsIcon.gif)).</span></span>
