---
title: Tjänstkryptering
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Sammanfattning Förstå dataåter motståndskraft i Microsoft Office 365.
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "52161789"
---
# <a name="service-encryption"></a><span data-ttu-id="b6afd-103">Tjänstkryptering</span><span class="sxs-lookup"><span data-stu-id="b6afd-103">Service Encryption</span></span>

<span data-ttu-id="b6afd-104">Utöver kryptering på volymnivå använder du Exchange Online, Microsoft Teams, SharePoint Online och OneDrive för företag också Tjänstkryptering för att kryptera kunddata.</span><span class="sxs-lookup"><span data-stu-id="b6afd-104">In addition to using volume-level encryption, Exchange Online, Microsoft Teams, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="b6afd-105">Tjänstekryptering ger två alternativ för nyckelhantering:</span><span class="sxs-lookup"><span data-stu-id="b6afd-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="b6afd-106">Microsoft-hanterade nycklar</span><span class="sxs-lookup"><span data-stu-id="b6afd-106">Microsoft-managed keys</span></span>
<span data-ttu-id="b6afd-107">Microsoft hanterar alla kryptografiska nycklar, inklusive rotnycklar för tjänstekryptering.</span><span class="sxs-lookup"><span data-stu-id="b6afd-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="b6afd-108">Det här alternativet är för närvarande aktiverat som standard Exchange Online, SharePoint Online OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="b6afd-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="b6afd-109">Microsoft-hanterade nycklar tillhandahåller standardkryptering av tjänster om du inte bestämmer dig för att börja använda kundnyckeln.</span><span class="sxs-lookup"><span data-stu-id="b6afd-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="b6afd-110">Om du vid ett senare tillfälle bestämmer dig för att sluta använda kundnyckeln utan att följa datarensningssökvägen förblir dina data krypterade med de Microsoft-hanterade nycklarna.</span><span class="sxs-lookup"><span data-stu-id="b6afd-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="b6afd-111">Dina data krypteras alltid på den här standardnivån som minst.</span><span class="sxs-lookup"><span data-stu-id="b6afd-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="b6afd-112">Customer Key</span><span class="sxs-lookup"><span data-stu-id="b6afd-112">Customer Key</span></span>
<span data-ttu-id="b6afd-113">Du tillhandahåller rotnycklar som används med tjänstkryptering och hanterar dessa nycklar med Azure-nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="b6afd-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="b6afd-114">Microsoft hanterar alla andra nycklar.</span><span class="sxs-lookup"><span data-stu-id="b6afd-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="b6afd-115">Det här alternativet kallas kundnyckel och är för närvarande tillgängligt för Exchange Online, SharePoint Online och OneDrive för företag.</span><span class="sxs-lookup"><span data-stu-id="b6afd-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="b6afd-116">(Tidigare kallat Avancerad kryptering med BYOK.</span><span class="sxs-lookup"><span data-stu-id="b6afd-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="b6afd-117">Läs [Förbättra transparensen och kontrollen för Office 365 kunder](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) för det ursprungliga tillkännagivandet.)</span><span class="sxs-lookup"><span data-stu-id="b6afd-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="b6afd-118">Tjänstkryptering ger flera fördelar:</span><span class="sxs-lookup"><span data-stu-id="b6afd-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="b6afd-119">Ger ytterligare ett skyddslager ovanpå BitLocker.</span><span class="sxs-lookup"><span data-stu-id="b6afd-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="b6afd-120">Det här gör att Windows från åtkomsten till programdata som lagras eller bearbetas av operativsystemet.</span><span class="sxs-lookup"><span data-stu-id="b6afd-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="b6afd-121">Innehåller ett alternativ för kundnyckel som gör det möjligt för tjänster med flera innehavare att tillhandahålla nyckelhantering per klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="b6afd-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="b6afd-122">Förbättrar möjligheten Microsoft 365 att uppfylla kraven från kunder som har specifika efterlevnadskrav för kryptering.</span><span class="sxs-lookup"><span data-stu-id="b6afd-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="b6afd-123">Med kundnyckel kan du generera egna kryptografiska nycklar med hjälp av en lokal maskinvarutjänstmodul (HSM) eller Azure-nyckelvalv (AKV).</span><span class="sxs-lookup"><span data-stu-id="b6afd-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="b6afd-124">Oavsett hur du skapar nyckeln använder du AKV för att styra och hantera de kryptografiska nycklar som används av Office 365.</span><span class="sxs-lookup"><span data-stu-id="b6afd-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="b6afd-125">När dina nycklar lagras i AKV kan de användas som roten till en av nyckelringarna som krypterar postlådedata eller filer.</span><span class="sxs-lookup"><span data-stu-id="b6afd-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="b6afd-126">En annan fördel med kundnyckel är den kontroll du har över möjligheten för Microsoft att bearbeta dina data.</span><span class="sxs-lookup"><span data-stu-id="b6afd-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="b6afd-127">Om du vill ta bort data från Office 365, till exempel om du vill avsluta tjänsten hos Microsoft eller ta bort en del av dina data som lagras i molnet, kan du göra det och använda kundnyckel som teknisk kontroll.</span><span class="sxs-lookup"><span data-stu-id="b6afd-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="b6afd-128">Genom att ta bort data säkerställer du att ingen, inklusive Microsoft, kan komma åt eller bearbeta data.</span><span class="sxs-lookup"><span data-stu-id="b6afd-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="b6afd-129">Kundnyckeln kompletterar och kompletterar Microsofts Lockbox som du använder för att styra Microsofts åtkomst till dina data.</span><span class="sxs-lookup"><span data-stu-id="b6afd-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="b6afd-130">Mer information om hur du ställr in kundnyckel för Microsoft 365 för Exchange Online, Microsoft Teams, SharePoint Online, inklusive gruppwebbplatser och OneDrive för företag, finns i följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="b6afd-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Microsoft Teams, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="b6afd-131">Tjänst kryptering med kundnyckel</span><span class="sxs-lookup"><span data-stu-id="b6afd-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="b6afd-132">Konfigurera kundnyckel</span><span class="sxs-lookup"><span data-stu-id="b6afd-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="b6afd-133">Hantera kundnyckel</span><span class="sxs-lookup"><span data-stu-id="b6afd-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="b6afd-134">Rulla eller rotera en kundnyckel eller en tillgänglighetsnyckel</span><span class="sxs-lookup"><span data-stu-id="b6afd-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="b6afd-135">Förstå tillgänglighetsnyckeln</span><span class="sxs-lookup"><span data-stu-id="b6afd-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
