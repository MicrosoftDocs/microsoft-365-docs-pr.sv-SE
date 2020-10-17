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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Skapa miljöer för demonstrationer, funktionstest och utveckling/testning för Microsoft 365 för företag med hjälp av testlabbguider.
ms.openlocfilehash: fefbb18fd108dceba6f387fb8244619c4bb1c167
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487476"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="94954-103">Testlabbguider för Microsoft 365 för företag</span><span class="sxs-lookup"><span data-stu-id="94954-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="94954-104">*Detta gäller för både Microsoft 365 för företag och Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="94954-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="94954-105">Med testlabbguider kan du snabbt lära dig mer om Microsofts produkter.</span><span class="sxs-lookup"><span data-stu-id="94954-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span></span> <span data-ttu-id="94954-106">De innehåller instruktioner för hur du konfigurerar enkla men representativa testmiljöer.</span><span class="sxs-lookup"><span data-stu-id="94954-106">They provide prescriptive instructions to configure simplified but representative test environments.</span></span> <span data-ttu-id="94954-107">Du kan använda dessa miljöer för demonstrationer, anpassningar eller skapa komplexa funktionstester under giltighetstiden för en utvärderingsversion eller med en betald prenumeration.</span><span class="sxs-lookup"><span data-stu-id="94954-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span>

<span data-ttu-id="94954-108">Testlabbguiderna är modulära.</span><span class="sxs-lookup"><span data-stu-id="94954-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="94954-109">De bygger på varandra, vilket innebär att du kan skapa flera konfigurationer som matchar dina utbildnings- eller testkonfigurationsbehov.</span><span class="sxs-lookup"><span data-stu-id="94954-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="94954-110">Den "Jag har byggt det själv och det fungerar" praktisk upplevelse hjälper dig att förstå distributions kraven för en ny produkt eller ett scenario, så att du bättre kan planera för att vara med i produktionen.</span><span class="sxs-lookup"><span data-stu-id="94954-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario, so that you can better plan for hosting it in production.</span></span>

<span data-ttu-id="94954-111">Du kan också använda Molntjänsterhttps://aka.MS/k53sfj för att skapa representativa miljöer för att utveckla och testa program, även kallat utvecklings-och test miljöer.</span><span class="sxs-lookup"><span data-stu-id="94954-111">You can also use TLGs to create representative environments to develop and test applications, also known as dev/test environments.</span></span>
  
![Testlabbguider för Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="94954-113">Om du vill visa en visuell karta till alla artiklar i gruppen Microsoft 365 för Enterprise-testlabbet expanderar du följande bild eller går till [Microsoft 365 för Enterprise prov Lab-guide](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="94954-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, expand the following graphic or go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

<span data-ttu-id="94954-114">[![Samlingen med testlabbguider för Microsoft 365 för företag](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="94954-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="94954-115">Grundläggande konfiguration</span><span class="sxs-lookup"><span data-stu-id="94954-115">Base configuration</span></span>

<span data-ttu-id="94954-116">Börja med att skapa en test miljö för [Microsoft 365 för företag](https://docs.microsoft.com/microsoft-365-enterprise/).</span><span class="sxs-lookup"><span data-stu-id="94954-116">First, create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/).</span></span> <span data-ttu-id="94954-117">Du kan skapa två olika typer av grundläggande konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="94954-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="94954-118">[Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md) – Använd det här alternativet om du vill konfigurera och demonstrera Microsoft 365 för Enterprise-funktioner och-funktioner i en moln miljö, som inte innehåller några lokala komponenter.</span><span class="sxs-lookup"><span data-stu-id="94954-118">[Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="94954-119">[Simulerad företags bas konfiguration](simulated-ent-base-configuration-microsoft-365-enterprise.md) – Använd det här alternativet om du vill konfigurera och bevisa Microsoft 365 för Enterprise-funktioner och-funktioner i en hybrid moln miljö, som använder lokala komponenter, till exempel AD DS-domän (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="94954-119">[Simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="94954-120">Du kan också skapa testmiljöer för Office 365 E5 genom att inte lägga till Microsoft 365 E5-licensen i utvärderings- eller produktionstestmiljön.</span><span class="sxs-lookup"><span data-stu-id="94954-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="94954-121">Identitet</span><span class="sxs-lookup"><span data-stu-id="94954-121">Identity</span></span>

<span data-ttu-id="94954-122">För en demonstration av identitetsrelaterade funktioner, se:</span><span class="sxs-lookup"><span data-stu-id="94954-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="94954-123">Synkronisering av lösenordshash</span><span class="sxs-lookup"><span data-stu-id="94954-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="94954-124">Aktivera och testa lösenordshash-baserad katalogsynkronisering från en AD DS-domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="94954-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="94954-125">Direktautentisering</span><span class="sxs-lookup"><span data-stu-id="94954-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="94954-126">Aktivera och testa direktautentisering till en AD DS-domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="94954-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="94954-127">Federerad autentisering</span><span class="sxs-lookup"><span data-stu-id="94954-127">Federated authentication</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   <span data-ttu-id="94954-128">Aktivera och testa federerad autentisering till en AD DS-domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="94954-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="94954-129">Enkel inloggning med Azure AD</span><span class="sxs-lookup"><span data-stu-id="94954-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="94954-130">Aktivera och testa Azure AD-sömlös enkel inloggning (sömlös SSO) med en AD DS-domänkontrollant.</span><span class="sxs-lookup"><span data-stu-id="94954-130">Enable and test Azure AD Seamless Single Sign-on (Seamless SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="94954-131">Multifaktorautentisering</span><span class="sxs-lookup"><span data-stu-id="94954-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="94954-132">Aktivera och testa multifaktorautentisering via telefon för ett specifikt användarkonto.</span><span class="sxs-lookup"><span data-stu-id="94954-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="94954-133">Skydda globala administratörskonton</span><span class="sxs-lookup"><span data-stu-id="94954-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   <span data-ttu-id="94954-134">Lås dina globala administratörskonton med principer för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="94954-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="94954-135">Tillbakaskrivning av lösenord</span><span class="sxs-lookup"><span data-stu-id="94954-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="94954-136">Använd tillbakaskrivning av lösenord när du ändrar lösenordet för ditt AD DS-användarkonto från Azure AD.</span><span class="sxs-lookup"><span data-stu-id="94954-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="94954-137">Återställning av lösenord</span><span class="sxs-lookup"><span data-stu-id="94954-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="94954-138">Använd självbetjäning för återställning av lösen ord för att återställa ditt lösen ord.</span><span class="sxs-lookup"><span data-stu-id="94954-138">Use self-service password reset to reset your password.</span></span>

- [<span data-ttu-id="94954-139">Automatisk licensiering och gruppmedlemskap</span><span class="sxs-lookup"><span data-stu-id="94954-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="94954-140">Administrera nya konton enklare än någonsin med automatisk licensiering och medlemskap i dynamiska grupper.</span><span class="sxs-lookup"><span data-stu-id="94954-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="94954-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="94954-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="94954-142">Sök igenom dina aktuella användarkonton efter säkerhetsrisker.</span><span class="sxs-lookup"><span data-stu-id="94954-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="94954-143">Identitet och enhetsåtkomst</span><span class="sxs-lookup"><span data-stu-id="94954-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="94954-144">Skapa en miljö för att testa rekommenderade konfigurationer för identitet och enhetsåtkomst och principer för villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="94954-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="94954-145">Hantering av mobila enheter</span><span class="sxs-lookup"><span data-stu-id="94954-145">Mobile device management</span></span>

<span data-ttu-id="94954-146">För en demonstration av funktioner för hantering av mobila enheter, se:</span><span class="sxs-lookup"><span data-stu-id="94954-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="94954-147">Principer för enhetsefterlevnad</span><span class="sxs-lookup"><span data-stu-id="94954-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="94954-148">Skapa en användargrupp och en princip för enhetsefterlevnad för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="94954-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="94954-149">Registrera iOS- och Android-enheter</span><span class="sxs-lookup"><span data-stu-id="94954-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="94954-150">Registrera iOS-och Android-enheter och hantera dem på distans.</span><span class="sxs-lookup"><span data-stu-id="94954-150">Enroll iOS or Android devices and manage them remotely.</span></span>

## <a name="information-protection"></a><span data-ttu-id="94954-151">Informationsskydd</span><span class="sxs-lookup"><span data-stu-id="94954-151">Information protection</span></span>

<span data-ttu-id="94954-152">För en demonstration av informationsskyddsrelaterade funktioner, se:</span><span class="sxs-lookup"><span data-stu-id="94954-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="94954-153">Ökad säkerhet i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="94954-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="94954-154">Konfigurera inställningar för ökad säkerhet i Microsoft 365 och utforska inbyggda säkerhetsverktyg.</span><span class="sxs-lookup"><span data-stu-id="94954-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="94954-155">Dataklassificering</span><span class="sxs-lookup"><span data-stu-id="94954-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="94954-156">Konfigurera och använd etiketter i ett dokument på en SharePoint Online-gruppwebbplats.</span><span class="sxs-lookup"><span data-stu-id="94954-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="94954-157">Privilegierad åtkomsthantering</span><span class="sxs-lookup"><span data-stu-id="94954-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="94954-158">Konfigurera privilegierad åtkomsthantering för just-in-time-åtkomst till upphöjda och privilegierade uppgifter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="94954-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>
