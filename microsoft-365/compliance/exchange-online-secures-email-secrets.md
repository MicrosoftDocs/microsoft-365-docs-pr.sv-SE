---
title: Så säkrar Exchange Online dina e-posthemligheter
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Förutom säkerhetscentret i Office 365 som tillhandahåller information om säkerhet, sekretess och efterlevnad för Microsoft 365 kan det vara bra att veta hur Microsoft skyddar hemligheterna som du lagrar i dess datacenter. Vi använder en teknik som kallas DKM (Distributed Key Manager).
ms.openlocfilehash: 2f6e51b7fe9cd75cbd265c3135050a08130f34d8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161935"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="ccafd-104">Så säkrar Exchange Online dina e-posthemligheter</span><span class="sxs-lookup"><span data-stu-id="ccafd-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="ccafd-105">I den här artikeln beskrivs hur Microsoft skyddar dina e-posthemligheter i sina datacenter.</span><span class="sxs-lookup"><span data-stu-id="ccafd-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="ccafd-106">Hur skyddar vi hemlig information som tillhandahålls av dig?</span><span class="sxs-lookup"><span data-stu-id="ccafd-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="ccafd-107">Förutom säkerhetscentret i Office 365 som tillhandahåller information om [säkerhet,](./get-started-with-service-trust-portal.md)sekretess och efterlevnad för Office 365 vill du kanske veta hur Microsoft hjälper till att skydda de hemligheter som du ger i sina datacenter.</span><span class="sxs-lookup"><span data-stu-id="ccafd-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](./get-started-with-service-trust-portal.md), you might want to know how Microsoft helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="ccafd-108">Vi använder en teknik som kallas DKM (Distributed Key Manager).</span><span class="sxs-lookup"><span data-stu-id="ccafd-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="ccafd-109">[DKM (Distributed Key Manager)](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) är en klientfunktion som använder en uppsättning hemliga nycklar för att kryptera och dekryptera information.</span><span class="sxs-lookup"><span data-stu-id="ccafd-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="ccafd-110">Endast medlemmar i en viss säkerhetsgrupp i Active Directory Domain Services kan komma åt dessa nycklar för att dekryptera data som krypteras med DKM.</span><span class="sxs-lookup"><span data-stu-id="ccafd-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="ccafd-111">I Exchange Online är endast vissa tjänstkonton där Exchange-processerna körs en del av den säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="ccafd-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="ccafd-112">Som en del av standardoperativsystemet i datacentret får ingen användare autentiseringsuppgifter som ingår i den här säkerhetsgruppen och därför har ingen person tillgång till de nycklar som kan dekryptera dessa hemligheter.</span><span class="sxs-lookup"><span data-stu-id="ccafd-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="ccafd-113">För felsökning, felsökning eller granskning måste en datacenteradministratör begära utökad åtkomst för att få tillfälliga autentiseringsuppgifter som ingår i säkerhetsgruppen.</span><span class="sxs-lookup"><span data-stu-id="ccafd-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="ccafd-114">För den här processen krävs flera nivåer av juridiskt godkännande.</span><span class="sxs-lookup"><span data-stu-id="ccafd-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="ccafd-115">Om åtkomst beviljas loggas alla aktiviteter och granskas.</span><span class="sxs-lookup"><span data-stu-id="ccafd-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="ccafd-116">Dessutom beviljas åtkomst endast för ett tidsintervall efter vilket den automatiskt förfaller.</span><span class="sxs-lookup"><span data-stu-id="ccafd-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="ccafd-117">För extra skydd inkluderar DKM-tekniken automatiserad nyckelrullning och arkivering.</span><span class="sxs-lookup"><span data-stu-id="ccafd-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="ccafd-118">Det här säkerställer också att du kan fortsätta att komma åt ditt äldre innehåll utan att behöva förlita dig på samma nyckel ett obestämt säkert sätt.</span><span class="sxs-lookup"><span data-stu-id="ccafd-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="ccafd-119">Var använder Exchange Online av DKM?</span><span class="sxs-lookup"><span data-stu-id="ccafd-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="ccafd-120">Microsoft använder [Distributed Key Manager för](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) att kryptera dina hemligheter Exchange Online datacenter.</span><span class="sxs-lookup"><span data-stu-id="ccafd-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="ccafd-121">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="ccafd-121">For example:</span></span>
  
- <span data-ttu-id="ccafd-122">Autentiseringsuppgifter för e-postkonto för anslutna konton.</span><span class="sxs-lookup"><span data-stu-id="ccafd-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="ccafd-123">Anslutna konton är konton från tredje part, till exempel Hotmail, Gmail och Yahoo!</span><span class="sxs-lookup"><span data-stu-id="ccafd-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="ccafd-124">e-postkonton.</span><span class="sxs-lookup"><span data-stu-id="ccafd-124">mail accounts.</span></span>

- <span data-ttu-id="ccafd-125">Kundnyckel.</span><span class="sxs-lookup"><span data-stu-id="ccafd-125">Customer key.</span></span> <span data-ttu-id="ccafd-126">Om du använder [Tjänstkryptering med Kundnyckel](customer-key-overview.md)använder du [Azure-nyckelvalvet för](/azure/key-vault/key-vault-whatis) att skydda dina hemligheter.</span><span class="sxs-lookup"><span data-stu-id="ccafd-126">If you are using [Service encryption with Customer Key](customer-key-overview.md), you'll use [Azure Key Vault](/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ccafd-127">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="ccafd-127">Related topics</span></span>

[<span data-ttu-id="ccafd-128">Kryptering i Office 365</span><span class="sxs-lookup"><span data-stu-id="ccafd-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="ccafd-129">Teknisk referensinformation om kryptering</span><span class="sxs-lookup"><span data-stu-id="ccafd-129">Technical reference details about encryption</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="ccafd-130">Tjänstgranskning i &amp; Säkerhetsefterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="ccafd-130">Service assurance in the Security &amp; Compliance Center</span></span>](./service-assurance.md)
