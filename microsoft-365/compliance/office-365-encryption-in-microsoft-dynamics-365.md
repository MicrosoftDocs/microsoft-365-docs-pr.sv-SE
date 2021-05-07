---
title: Kryptering i Microsoft Dynamics 365
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
ms.collection: Strat_O365_Enterprise
description: Lär dig hur Microsoft använder krypteringsteknik för att skydda kunddata i Microsoft Dynamics 365 medan de är vilade i en Microsoft-databas och under överföringen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1c55c4ac233c61f7a583f4f1a94222133f1d7c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162216"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Kryptering i Microsoft Dynamics 365

Microsoft använder krypteringsteknik för att skydda kunddata i Dynamics 365 medan de är vilan i en Microsoft-databas och medan den överförs mellan användarenheter och våra datacenter. Anslutningar som upprättas mellan kunder och Microsoft-datacenter krypteras och alla offentliga slutpunkter skyddas med TLS med branschstandard TLS. TLS upprättar effektivt en säkerhetsbaserad anslutning mellan webbläsare och server för att säkerställa datahemligheter och integritet mellan skrivbord och datacenter. När datakryptering har aktiverats kan det inte inaktiveras. Mer information finns i [Datakryptering på fältnivå.](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8))

I Dynamics 365 används Microsoft SQL Server standardkryptering på cellnivå för en uppsättning standardattribut som innehåller känslig information, till exempel användarnamn och e-postlösenord. Den här funktionen kan hjälpa organisationer att uppfylla efterlevnadskraven som är kopplade till FIPS 140-2. Datakryptering på fältnivå är särskilt [](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8))viktigt i scenarier som utnyttjar Microsoft Dynamics CRM-e-postroutern , som måste lagra användarnamn och lösenord för att aktivera integrering mellan en Dynamics 365-instans och en e-posttjänst. 

Alla instanser av Dynamics 365 använder [Microsoft SQL Server transparent datakryptering](/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) (TDE) för att utföra realtidskryptering av data när de skrivs till disken (i vila). TDE krypterar SQL Server, Azure SQL Database och Azure SQL Data Warehouse-datafiler. Som standard lagrar och hanterar Microsoft databaskrypteringsnycklarna för dina instanser av Dynamics 365. (De nycklar som används av Dynamics 365 for Financials genereras av .NET Framework Data Protection API.) 

Funktionen Hantera nycklar i Dynamics 365 Administrationscenter ger administratörer möjlighet att själv hantera de databaskrypteringsnycklar som är associerade med instanser av Dynamics 365. (Själv hanterade databaskrypteringsnycklar är bara tillgängliga i uppdateringen för januari 2017 för Microsoft Dynamics 365 och kan inte göras tillgängliga för senare versioner. Mer information finns i [Hantera krypteringsnycklar för din Dynamics 365-instans (online).)](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance) Nyckelhanteringsfunktionen stöder både PFX- och BYOK-krypteringsnyckelfiler, till exempel filer som lagras i en HSM. (Mer information om att generera och överföra en HSM-skyddad nyckel via Internet finns i Skapa och överföra [HSM-skyddade](/azure/key-vault/key-vault-hsm-protected-keys)nycklar för Azure Key Vault .) 

Om du vill använda alternativet för uppladdningskryptering behöver du både den offentliga och privata krypteringsnyckeln.

Nyckelhanteringsfunktionen gör att krypteringsnyckelhanteringen blir mer komplex genom att använda Azure-nyckelvalvet för att lagra krypteringsnycklar på ett säkert sätt. Azure Key Vault bidrar till att skydda kryptografiska nycklar och hemligheter som används av molnprogram och tjänster. Nyckelhanteringsfunktionen kräver inte att du har en Prenumeration på Azure-nyckelvalv och i de flesta situationer behöver du inte komma åt krypteringsnycklar som används för Dynamics 365 i valvet.