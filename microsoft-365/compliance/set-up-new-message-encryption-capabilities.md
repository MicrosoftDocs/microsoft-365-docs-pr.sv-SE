---
title: Konfigurera nya funktioner för meddelandekryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Läs mer om de nya meddelandekrypteringsfunktionerna i Office 365 som skyddar e-postkommunikationen med personer inom och utanför organisationen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9b738c0f93b8958e441b34b458942c2b34c16661
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228585"
---
# <a name="set-up-new-message-encryption-capabilities"></a><span data-ttu-id="22d51-103">Konfigurera nya funktioner för meddelandekryptering</span><span class="sxs-lookup"><span data-stu-id="22d51-103">Set up new Message Encryption capabilities</span></span>

<span data-ttu-id="22d51-104">Med de nya funktionerna för meddelandekryptering i Office 365 (OME) kan organisationer dela skyddad e-post med vem som helst på valfri enhet.</span><span class="sxs-lookup"><span data-stu-id="22d51-104">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="22d51-105">Användarna kan utbyta skyddade meddelanden med andra Microsoft 365-organisationer och icke-kunder med hjälp av Outlook.com, Gmail och andra e-posttjänster.</span><span class="sxs-lookup"><span data-stu-id="22d51-105">Users can exchange protected messages with other Microsoft 365 organizations, as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="22d51-106">Följ stegen nedan för att se till att de nya OME-funktionerna är tillgängliga i din organisation.</span><span class="sxs-lookup"><span data-stu-id="22d51-106">Follow the steps below to ensure that the new OME capabilities are available in your organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="22d51-107">Kontrollera att Azure Rights Management är aktivt</span><span class="sxs-lookup"><span data-stu-id="22d51-107">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="22d51-108">De nya OME-funktionerna utnyttjar säkerhetsfunktionerna i [Azure Rights Management Services (Azure RMS)](/azure/information-protection/what-is-information-protection), vilket är den teknik som används av [Azure Information Protection](/azure/information-protection/what-is-azure-rms) för att skydda e-post och dokument via kryptering och åtkomstkontroller.</span><span class="sxs-lookup"><span data-stu-id="22d51-108">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="22d51-109">Det enda som krävs för att använda de nya OME-funktionerna är att [Azure Rights Management](/azure/information-protection/what-is-azure-rms) är aktiverat i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="22d51-109">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="22d51-110">Om den är det aktiverar Microsoft 365 de nya OME-funktionerna automatiskt och du behöver inte göra någonting.</span><span class="sxs-lookup"><span data-stu-id="22d51-110">If it is, Microsoft 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="22d51-111">Azure RMS aktiveras också automatiskt för de flesta abonnemangen, så du behöver förmodligen inte göra något i det här avseendet heller.</span><span class="sxs-lookup"><span data-stu-id="22d51-111">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="22d51-112">Se [Aktivera Azure Rights Management](/azure/information-protection/activate-service) för mer information.</span><span class="sxs-lookup"><span data-stu-id="22d51-112">See [Activating Azure Rights Management](/azure/information-protection/activate-service) for more information.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22d51-113">Om du använder Active Directory Rights Management Service (AD RMS) med Exchange Online måste du [migrera till Azure Information Protection](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) innan du kan använda de nya OME-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="22d51-113">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="22d51-114">OME är inte kompatibelt med AD RMS.</span><span class="sxs-lookup"><span data-stu-id="22d51-114">OME is not compatible with AD RMS.</span></span>

<span data-ttu-id="22d51-115">Mer information finns i:</span><span class="sxs-lookup"><span data-stu-id="22d51-115">For more information, see:</span></span>

- <span data-ttu-id="22d51-116">[Vilka prenumerationer behöver jag för att kunna använda de nya OME-funktionerna?](ome-faq.yml#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities-) för att kontrollera om ditt abonnemang innehåller Azure Information Protection (som innehåller Azure RMS-funktionen).</span><span class="sxs-lookup"><span data-stu-id="22d51-116">[What subscriptions do I need to use the new OME capabilities?](ome-faq.yml#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities-) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="22d51-117">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) för information om hur du köper en prenumeration.</span><span class="sxs-lookup"><span data-stu-id="22d51-117">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) for information about purchasing an eligible subscription.</span></span>

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="22d51-118">Aktivera Azure Rights Management manuellt</span><span class="sxs-lookup"><span data-stu-id="22d51-118">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="22d51-119">Om du inaktiverade Azure RMS, eller om det av någon anledning inte aktiverades automatiskt, kan du aktivera det manuellt i:</span><span class="sxs-lookup"><span data-stu-id="22d51-119">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="22d51-120">**Administrationscenter för Microsoft 365:**: [Aktivera Azure Rights Management från administrationscentret](/azure/information-protection/activate-office365) för anvisningar.</span><span class="sxs-lookup"><span data-stu-id="22d51-120">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="22d51-121">**Azure-portal**: Se [Aktivera Azure Rights Management från Azure-portalen](/azure/information-protection/activate-azure) för anvisningar.</span><span class="sxs-lookup"><span data-stu-id="22d51-121">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="22d51-122">Konfigurera hantering av klientnyckeln för Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="22d51-122">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="22d51-123">Det här är ett valfritt steg.</span><span class="sxs-lookup"><span data-stu-id="22d51-123">This is an optional step.</span></span> <span data-ttu-id="22d51-124">Standardinställningen och rekommenderad metod för de flesta organisationer är att låta Microsoft hantera rotnyckeln för Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="22d51-124">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most organizations.</span></span> <span data-ttu-id="22d51-125">I detta fall behöver du inte göra något.</span><span class="sxs-lookup"><span data-stu-id="22d51-125">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="22d51-126">Det finns många orsaker, till exempel krav på efterlevnad, som kan innebära att du måste generera och hantera din egen rotnyckel (kallas även BYOK).</span><span class="sxs-lookup"><span data-stu-id="22d51-126">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="22d51-127">Om så är fallet rekommenderar vi att du slutför de steg som krävs innan du konfigurerar de nya OME-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="22d51-127">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="22d51-128">Se [Planera och implementera klientnyckeln för Azure Information Protection](/information-protection/plan-design/plan-implement-tenant-key) för mer information.</span><span class="sxs-lookup"><span data-stu-id="22d51-128">See [Planning and implementing your Azure Information Protection tenant key](/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="22d51-129">Verifiera den nya OME-konfigurationen i Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="22d51-129">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="22d51-130">Du kan kontrollera att Microsoft 365-klientorganisationen är korrekt konfigurerad för att använda de nya OME-funktionerna i [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="22d51-130">You can verify that your Microsoft 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

1. <span data-ttu-id="22d51-131">[Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) med ett konto med behörighet som global administratör i Microsoft 365-klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="22d51-131">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Microsoft 365 tenant.</span></span>

2. <span data-ttu-id="22d51-132">Kör cmdleten Get-IRMConfiguration.</span><span class="sxs-lookup"><span data-stu-id="22d51-132">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="22d51-133">Du bör se värdet $True för parametern AzureRMSLicensingEnabled, vilket visar att OME har konfigurerats i klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="22d51-133">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="22d51-134">Om inte, använder du Set-IRMConfiguration för att ange värdet för AzureRMSLicensingEnabled till $True och aktivera OME.</span><span class="sxs-lookup"><span data-stu-id="22d51-134">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="22d51-135">Kör cmdleten Test-IRMConfiguration med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="22d51-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```

   <span data-ttu-id="22d51-136">**Exempel**:</span><span class="sxs-lookup"><span data-stu-id="22d51-136">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="22d51-137">Att tillhandahålla avsändarens e-postadress är valfritt, men det tvingar systemet att utföra ytterligare kontroller.</span><span class="sxs-lookup"><span data-stu-id="22d51-137">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="22d51-138">Använd e-postadressen till en användare i din Microsoft 365-klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="22d51-138">Use the email address of any user in your Microsoft 365 tenant.</span></span>

     <span data-ttu-id="22d51-139">Resultatet bör likna detta:</span><span class="sxs-lookup"><span data-stu-id="22d51-139">Your results should be similar to:</span></span>

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - <span data-ttu-id="22d51-140">Ditt organisationsnamn ersätter *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="22d51-140">Your organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="22d51-141">Namnen på standardmallarna kan skilja sig från de som visas ovan.</span><span class="sxs-lookup"><span data-stu-id="22d51-141">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="22d51-142">Se [Konfigurera och hantera mallar för Azure Information Protection](/azure/information-protection/configure-policy-templates) för mer information.</span><span class="sxs-lookup"><span data-stu-id="22d51-142">See [Configuring and managing templates for Azure Information Protection](/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="22d51-143">Kör cmdleten Remove-PSSession för att koppla från Rights Management-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="22d51-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="22d51-144">Nästa steg: Definiera e-postflödesregler som använder nya OME-funktioner</span><span class="sxs-lookup"><span data-stu-id="22d51-144">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="22d51-p110">Om det finns tidigare konfigurerade e-postflödesregler för att kryptera e-post i organisationen, måste du uppdatera de befintliga reglerna för att kunna använda de nya OME-funktionerna. För nya distributioner måste du skapa nya e-postflödesregler.</span><span class="sxs-lookup"><span data-stu-id="22d51-p110">If there are previously configured mail flow rules to encrypt email in your organization, you need to update the existing rules to use the new OME capabilities. For new deployments, you need to create new mail flow rules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22d51-147">Om du inte uppdaterar befintliga e-postflödesregler fortsätter användarna att ta emot krypterad e-post med det tidigare HTML-formatet för bilagor i stället för det nya smidiga OME-formatet.</span><span class="sxs-lookup"><span data-stu-id="22d51-147">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="22d51-148">E-postflödesreglerna avgör när e-postmeddelanden ska krypteras och villkoren för att ta bort krypteringen.</span><span class="sxs-lookup"><span data-stu-id="22d51-148">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="22d51-149">När du anger en åtgärd för en regel krypteras alla meddelanden som matchar regelvillkoren när de skickas.</span><span class="sxs-lookup"><span data-stu-id="22d51-149">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>

<span data-ttu-id="22d51-150">Anvisningar om hur du skapar e-postflödesregler för OME finns i [Definiera e-postflödesregler för att kryptera e-postmeddelanden i Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="22d51-150">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="22d51-151">Uppdatera befintliga regler till att använda de nya OME-funktionerna:</span><span class="sxs-lookup"><span data-stu-id="22d51-151">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="22d51-152">I administrationscentret för Microsoft 365 går du till **Administrationscenter > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="22d51-152">In the Microsoft 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="22d51-153">Gå till **E-postflöde > Regler** i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="22d51-153">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="22d51-154">För varje regel i **Gör följande**:</span><span class="sxs-lookup"><span data-stu-id="22d51-154">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="22d51-155">Välj **Ändra meddelandesäkerheten**.</span><span class="sxs-lookup"><span data-stu-id="22d51-155">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="22d51-156">Välj **Använd Meddelandekryptering i Office 365 och rättighetsskydd**.</span><span class="sxs-lookup"><span data-stu-id="22d51-156">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="22d51-157">Välj en RMS-mall i listan.</span><span class="sxs-lookup"><span data-stu-id="22d51-157">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="22d51-158">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="22d51-158">Select **Save**.</span></span>
    - <span data-ttu-id="22d51-159">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="22d51-159">Select **OK**.</span></span>
