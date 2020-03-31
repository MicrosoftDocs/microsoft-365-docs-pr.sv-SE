---
title: Testlabbguider för Microsoft 365 för företag
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Skapa miljöer för demonstrationer, funktionstest och utveckling/testning för Microsoft 365 för företag med hjälp av testlabbguider.
ms.openlocfilehash: 4190eb4619f4732310786b5a7dde6bb590a969c1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805849"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="60ebd-103">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="60ebd-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="60ebd-104">*Detta gäller för både Microsoft 365 för företag och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="60ebd-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="60ebd-105">Med testlabbguider kan du snabbt lära dig mer om Microsofts produkter.</span><span class="sxs-lookup"><span data-stu-id="60ebd-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span></span> <span data-ttu-id="60ebd-106">De innehåller instruktioner för hur du konfigurerar enkla men representativa testmiljöer.</span><span class="sxs-lookup"><span data-stu-id="60ebd-106">They provide prescriptive instructions to configure simplified but representative test environments.</span></span> <span data-ttu-id="60ebd-107">Du kan använda dessa miljöer för demonstrationer, anpassningar eller skapa komplexa funktionstester under giltighetstiden för en utvärderingsversion eller med en betald prenumeration.</span><span class="sxs-lookup"><span data-stu-id="60ebd-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="60ebd-108">Testlabbguiderna är modulära.</span><span class="sxs-lookup"><span data-stu-id="60ebd-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="60ebd-109">De bygger på varandra, vilket innebär att du kan skapa flera konfigurationer som matchar dina utbildnings- eller testkonfigurationsbehov.</span><span class="sxs-lookup"><span data-stu-id="60ebd-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="60ebd-110">”Jag skapade det själv och det fungerar” är känslan man får med sig efter de praktiska övningarna. Guiderna hjälper dig att förstå distributionskraven för en ny produkt eller ett nytt scenario, så att du kan planera bättre för distributionen i produktion.</span><span class="sxs-lookup"><span data-stu-id="60ebd-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="60ebd-111">Du kan också skapa representativa miljöer för utveckling och testning av program med hjälp av testlabbguiderna.</span><span class="sxs-lookup"><span data-stu-id="60ebd-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="60ebd-113">Klicka [här](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) om du vill se en översikt över alla artiklar i samlingen med testlabbguider för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="60ebd-113">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="60ebd-114">[![Samlingen med testlabbguider för Microsoft 365 för företag](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="60ebd-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="60ebd-115">Grundläggande konfiguration</span><span class="sxs-lookup"><span data-stu-id="60ebd-115">Base configuration</span></span>

<span data-ttu-id="60ebd-116">Först skapar du en testmiljö för [Microsoft 365 för företag](https://docs.microsoft.com/microsoft-365-enterprise/) som innehåller Office 365 E5, Enterprise Mobility + Security (EMS) E5 och Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="60ebd-116">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise.</span></span> <span data-ttu-id="60ebd-117">Du kan skapa två olika typer av grundläggande konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="60ebd-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="60ebd-118">Använd den [enkla grundläggande konfigurationen](lightweight-base-configuration-microsoft-365-enterprise.md) när du vill konfigurera och demonstrera funktioner för Microsoft 365 för företag i en molnmiljö, som inte omfattar några lokala komponenter.</span><span class="sxs-lookup"><span data-stu-id="60ebd-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="60ebd-119">Använd [grundläggande konfiguration för simulerat företag](simulated-ent-base-configuration-microsoft-365-enterprise.md) när du vill konfigurera och demonstrera funktioner för Microsoft 365 för företag i en hybridmolnmiljö, som omfattar lokala komponenter som en AD DS-domän (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="60ebd-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="60ebd-120">Du kan också skapa testmiljöer för Office 365 E5 genom att inte lägga till Microsoft 365 E5-licensen i utvärderings- eller produktionstestmiljön.</span><span class="sxs-lookup"><span data-stu-id="60ebd-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="60ebd-121">Identitet</span><span class="sxs-lookup"><span data-stu-id="60ebd-121">Identity</span></span>

<span data-ttu-id="60ebd-122">För en demonstration av identitetsrelaterade funktioner, se:</span><span class="sxs-lookup"><span data-stu-id="60ebd-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="60ebd-123">Synkronisering av lösenordshash</span><span class="sxs-lookup"><span data-stu-id="60ebd-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="60ebd-124">Aktivera och testa lösenordshash-baserad katalogsynkronisering från en AD DS-domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="60ebd-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="60ebd-125">Direktautentisering</span><span class="sxs-lookup"><span data-stu-id="60ebd-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="60ebd-126">Aktivera och testa direktautentisering till en AD DS-domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="60ebd-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="60ebd-127">Federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="60ebd-127">Federated authentication</span></span>](federated-identity-for-your-office-365-dev-test-environment.md)
  
   <span data-ttu-id="60ebd-128">Aktivera och testa federerad autentisering till en AD DS-domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="60ebd-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="60ebd-129">Enkel inloggning med Azure AD</span><span class="sxs-lookup"><span data-stu-id="60ebd-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="60ebd-130">Aktivera och testa enkel inloggning med Azure AD med en AD DS-domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="60ebd-130">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="60ebd-131">Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="60ebd-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="60ebd-132">Aktivera och testa multifaktorautentisering via telefon för ett specifikt användarkonto.</span><span class="sxs-lookup"><span data-stu-id="60ebd-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="60ebd-133">Skydda globala administratörskonton</span><span class="sxs-lookup"><span data-stu-id="60ebd-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="60ebd-134">Lås dina globala administratörskonton med principer för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="60ebd-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="60ebd-135">Tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="60ebd-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="60ebd-136">Använd tillbakaskrivning av lösenord när du ändrar lösenordet för ditt AD DS-användarkonto från Azure AD.</span><span class="sxs-lookup"><span data-stu-id="60ebd-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="60ebd-137">Återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="60ebd-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="60ebd-138">Använd självbetjäning av lösenordsåterställning (SSPR) för att återställa ditt lösenord.</span><span class="sxs-lookup"><span data-stu-id="60ebd-138">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="60ebd-139">Automatisk licensiering och gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="60ebd-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="60ebd-140">Administrera nya konton enklare än någonsin med automatisk licensiering och medlemskap i dynamiska grupper.</span><span class="sxs-lookup"><span data-stu-id="60ebd-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="60ebd-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="60ebd-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="60ebd-142">Sök igenom dina aktuella användarkonton efter säkerhetsrisker.</span><span class="sxs-lookup"><span data-stu-id="60ebd-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="60ebd-143">Identitet och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="60ebd-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="60ebd-144">Skapa en miljö för att testa rekommenderade konfigurationer för identitet och enhetsåtkomst och principer för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="60ebd-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="60ebd-145">Hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="60ebd-145">Mobile device management</span></span>

<span data-ttu-id="60ebd-146">För en demonstration av funktioner för hantering av mobila enheter, se:</span><span class="sxs-lookup"><span data-stu-id="60ebd-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="60ebd-147">Principer för enhetsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="60ebd-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="60ebd-148">Skapa en användargrupp och en princip för enhetsefterlevnad för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="60ebd-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="60ebd-149">Registrera iOS- och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="60ebd-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="60ebd-150">Registrera iOS-och Android-enheter och hantera dem på distans.</span><span class="sxs-lookup"><span data-stu-id="60ebd-150">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="60ebd-151">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="60ebd-151">Information protection</span></span>

<span data-ttu-id="60ebd-152">För en demonstration av informationsskyddsrelaterade funktioner, se:</span><span class="sxs-lookup"><span data-stu-id="60ebd-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="60ebd-153">Ökad säkerhet för Office 365</span><span class="sxs-lookup"><span data-stu-id="60ebd-153">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="60ebd-154">Konfigurera inställningar för ökad säkerhet i Office 365 och utforska inbyggda säkerhetsverktyg.</span><span class="sxs-lookup"><span data-stu-id="60ebd-154">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="60ebd-155">Dataklassificering</span><span class="sxs-lookup"><span data-stu-id="60ebd-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="60ebd-156">Konfigurera och använd Office 365-etiketter i ett dokument på en SharePoint Online-gruppwebbplats.</span><span class="sxs-lookup"><span data-stu-id="60ebd-156">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="60ebd-157">Privilegierad åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="60ebd-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="60ebd-158">Konfigurera privilegierad åtkomsthantering för just-in-time-åtkomst till upphöjda och privilegierade uppgifter i din Office 365-organisation.</span><span class="sxs-lookup"><span data-stu-id="60ebd-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>


