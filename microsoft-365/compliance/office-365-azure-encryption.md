---
title: Kryptering i Azure
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Läs mer om kryptering i Azure, till exempel Azure Disk Encryption
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee4eb2bec814d7e06d418518bb9be272f1bd5aaa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162218"
---
# <a name="encryption-in-azure"></a>Kryptering i Azure

Tekniska säkerhetsåtgärder i Azure, till exempel krypterad kommunikation och driftsprocesser, hjälper till att skydda dina data. Du har också flexibiliteten att implementera ytterligare krypteringsfunktioner och hantera dina egna kryptografiska nycklar. Oavsett kundkonfiguration använder Microsoft kryptering för att skydda kunddata i Azure. Med Microsoft kan du även styra dina data i Azure via en mängd olika avancerade tekniker för att kryptera, kontrollera och hantera kryptografiska nycklar samt kontrollera och granska åtkomst till data. Dessutom innehåller Azure Storage omfattande säkerhetsfunktioner som tillsammans gör det möjligt för utvecklare att skapa säkra program.

Azure erbjuder många mekanismer för att skydda data när de flyttas från en plats till en annan. Microsoft använder TLS för att skydda data när de reser mellan molntjänster och kunder. Microsofts datacenter förhandlar fram en TLS-anslutning med klientsystem som ansluter till Azure-tjänster. Den perfekta forwardskopplingen (PFS) skyddar anslutningar mellan kundernas klientsystem och Microsofts molntjänster med unika nycklar. I Connections används även RSA-baserade krypteringsnyckellängder på 2 048 bitar. Den här kombinationen gör det svårt för någon att snappa upp och komma åt data som överförs.

Data kan skyddas under överföring mellan ett program och Azure med hjälp av [klientkryptering](/azure/storage/storage-client-side-encryption), HTTPS eller SMB 3.0. Du kan aktivera kryptering av trafik mellan dina egna virtuella maskiner och dina användare. Med [virtuella Azure-nätverk](https://azure.microsoft.com/services/virtual-network/)kan du använda IPsec-protokollet med branschstandard för att kryptera trafik mellan företagets VPN-gateway och Azure samt mellan de virtuella maskinerna som finns på ditt virtuella nätverk.

För data i vila erbjuder Azure många krypteringsalternativ, till exempel stöd för AES-256, vilket ger dig möjlighet att välja det scenario för datalagring som bäst uppfyller dina behov. Data kan krypteras automatiskt när de skrivs Azure Storage med [Storage tjänstkryptering](/azure/storage/storage-service-encryption)och operativsystems- och datadiskar som används av virtuella maskiner kan krypteras. Mer information finns i [Säkerhetsrekommendationer för Windows virtuella datorer i Azure.](/azure/security/azure-security-disk-encryption) Delegerad åtkomst till dataobjekt i Azure Storage med signaturer [för delad åtkomst.](/azure/storage/storage-dotnet-shared-access-signature-part-1) Azure tillhandahåller också kryptering för data i vila med hjälp [transparent datakryptering för Azure SQL Database och Data Warehouse.](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql)

Mer information om kryptering i Azure finns i [Översikt över Azure-kryptering](/azure/security/security-azure-encryption-overview) och [Azure Data Encryption-at-Rest.](/azure/security/azure-security-encryption-atrest)

## <a name="azure-disk-encryption"></a>Azure Disk Encryption

Azure Disk Encryption kryptera dina virtuella Windows och Linux Infrastructure as a Service (IaaS) VM-diskar. Azure Disk Encryption utnyttjar BitLocker-funktionen i Windows och DM-Crypt-funktionen i Linux för att tillhandahålla volymkryptering för operativsystem och datadiskar. Det säkerställer också att alla data på VM-diskar är krypterade i vila i din Azure-lagring. Azure Disk Encryption är integrerat med Azure-nyckelvalvet för att hjälpa dig att styra, hantera och granska användningen av krypteringsnycklar och hemligheter.

Mer information finns i [Säkerhetsrekommendationer för Windows virtuella datorer i Azure.](/azure/virtual-machines/windows/security-recommendations)

## <a name="azure-storage-service-encryption"></a>Azure Storage Tjänstkryptering

Med [Azure Storage tjänstkryptering](/azure/storage/storage-service-encryption)krypteras Azure Storage automatiskt data innan de sparas i lagringen och dekrypteras data innan de hämtas. Processerna för kryptering, dekryptering och nyckelhantering är helt transparenta för användarna. Azure Storage Tjänstkryptering kan användas för [Azure Blob Storage](https://azure.microsoft.com/services/storage/blobs/) och [Azure-filer.](https://azure.microsoft.com/services/storage/files/) Du kan också använda Microsoft-hanterade krypteringsnycklar Azure Storage eller använda dina egna krypteringsnycklar. (Information om hur du använder egna nycklar finns i Storage [tjänstkryptering med kund hanterade nycklar i Azure Key Vault.](/azure/storage/common/storage-service-encryption-customer-managed-keys) Information om hur du använder Microsoft-hanterade nycklar finns [Storage tjänstkryptering för data i vila.)](/azure/storage/storage-service-encryption) Dessutom kan du automatisera användningen av kryptering. Exempelvis kan du programmässigt aktivera eller inaktivera Storage-tjänstkryptering på ett lagringskonto med REST API för [Azure Storage-resursleverantör](/rest/api/storagerp/), [Storage Resource Provider Client Library för .NET,](/dotnet/api/overview/azure/storage) [Azure PowerShell](/powershell/azureps-cmdlets-docs)eller [Azure CLI.](/azure/storage/storage-azure-cli)

Vissa Microsoft 365 tjänster använder Azure för att lagra data. Exempel: SharePoint Online OneDrive för företag lagra data i Azure Blob Storage, och Microsoft Teams lagrar data för sin chatttjänst i tabeller, blobbar och köer. Dessutom lagrar funktionen [Efterlevnadshanteraren i kompatibilitetscentret](/azure/cosmos-db/database-encryption-at-rest)för Microsoft 365 kunddata som lagras i krypterad form i Azure Azures DB , en PaaS -plattform (Platform as a Service), en global distribuerad flermodellsdatabas. Azure Storage Tjänstekryptering krypterar data som lagras i Blob-lagring i Azure och i tabeller, och i Azure Disk Encryption krypteras data i köer samt Windows- och IaaS-virtuella maskindiskar för att ge volymkryptering för operativsystemet och datadisken. Lösningen säkerställer att alla data på den virtuella datorns diskar är krypterade i vila i din Azure-lagring. [Kryptering i vila i Azure Azure Azures DB implementeras](/azure/cosmos-db/database-encryption-at-rest) med hjälp av flera säkerhetstekniker, inklusive säkra nyckellagringssystem, krypterade nätverk och kryptografiska API:er.

## <a name="azure-key-vault"></a>Azure-nyckelvalv

Säker nyckelhantering är inte bara grundläggande för metodtips för kryptering. det är också viktigt för att skydda data i molnet. [Med Azure-nyckelvalv](/azure/key-vault/key-vault-whatis) kan du kryptera nycklar och små hemligheter som lösenord som använder nycklar som lagras i maskinvarusäkerhetsmoduler (HSMs). Azure Key Vault är Microsofts rekommenderade lösning för att hantera och kontrollera åtkomst till krypteringsnycklar som används av molntjänster. Behörigheter för snabbtangenter kan tilldelas tjänster eller till användare med Azure Active Directory konton. Med Azure Key Vault kan man lätta upp organisationer när de behöver konfigurera, korrigera och underhålla HSMs och nyckelhanteringsprogram. Med Azure-nyckelvalv ser Microsoft aldrig dina nycklar och program som inte har direkt åtkomst till dem. har du kontroll. Du kan också importera eller generera nycklar i snabbmeddelanden. Organisationer som har en prenumeration som innehåller Azure Information Protection kan konfigurera sin Azure Information Protection-klientorganisation att använda en kund hanterad nyckel Bring [Your Own Key](/information-protection/plan-design/byok-price-restrictions) (BYOK)) och logga användningen av [den.](/information-protection/deploy-use/log-analyze-usage)