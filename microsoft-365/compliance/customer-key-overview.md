---
title: Tjänstkryptering med kundnyckel
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: I den här artikeln får du lära dig hur tjänstkryptering fungerar med kundnyckeln i Microsoft 365.
ms.openlocfilehash: 21291dc45cd634cd5b6a88c4e58972c17486724f
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162545"
---
# <a name="service-encryption-with-customer-key"></a>Tjänstkryptering med kundnyckel

Microsoft 365 grundläggande, volymnivåkryptering aktiverad via BitLocker och DKM (Distributed Key Manager). Microsoft 365 erbjuder ett till lager med kryptering i programlagret för innehållet. Det här innehållet omfattar data Exchange Online, Skype för företag, SharePoint Online, OneDrive för företag och Teams filer. Det här extra lagret av kryptering kallas tjänstkryptering.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Så här fungerar tjänstekryptering, BitLocker och kundnyckel tillsammans

Tjänstkryptering säkerställer att innehållet i vila krypteras i tjänstlagret. **Dina data krypteras alltid vilan i Microsoft 365 med BitLocker och DKM.** Mer information finns i "Säkerhet, sekretess och efterlevnadsinformation" och Hur du [kan skydda dina e-Exchange Online.](exchange-online-secures-email-secrets.md) Kundnyckeln ger ytterligare skydd mot visning av data av obehöriga system eller personal, och kompletterar BitLocker av diskkryptering i Microsofts datacenter. Tjänstekryptering är inte avsedd att förhindra Microsoft-personal från att komma åt kunddata. Det primära syftet är att hjälpa kunder att uppfylla regelverks- och efterlevnadsskyldigheter för att kontrollera rotnycklar. Kunder godkänner uttryckligen O365-tjänster att använda sina krypteringsnycklar för att tillhandahålla ytterligare molntjänster, till exempel eDiscovery, skadlig programvara, skydd mot skräppost, sökindexering osv.

Kundnyckel bygger på tjänstkryptering och låter dig tillhandahålla och kontrollera krypteringsnycklar. Microsoft 365 sedan dessa nycklar för att kryptera data vilan enligt beskrivningen i [villkor för onlinetjänster (OST).](https://www.microsoft.com/licensing/product-licensing/products.aspx) Kundnyckeln hjälper dig att uppfylla efterlevnadsskyldigheter eftersom du kontrollerar krypteringsnycklarna som Microsoft 365 använder för att kryptera och dekryptera data.
  
Kundnyckel förbättrar organisationens förmåga att uppfylla kraven på efterlevnad som anger viktiga arrangemang med molntjänstleverantören. Med kundnyckeln tillhandahåller och kontrollerar du rotkrypteringsnycklarna för Microsoft 365 data i vila på programnivå. Därför kan du ta kontroll över organisationens nycklar. Om du bestämmer dig för att avsluta tjänsten återkallar du åtkomsten till organisationens rotnycklar. För alla Microsoft 365 tjänster är att återkalla åtkomsten till nycklarna det första steget på vägen mot databorttagning. Genom att återkalla åtkomsten till nycklarna är data oläsliga för tjänsten.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>Kundnyckel krypterar data i vila i Office 365

Med nycklar som du anger krypterar kundnyckeln på programnivå:

- SharePoint Online-, OneDrive för företag- och Teams filer.
- Filer som laddats upp OneDrive för företag.
- Exchange Online innehåll i postlådan, t.ex. innehåll i e-postmeddelanden, kalenderposter och innehåll i bifogade filer i e-postmeddelanden.
- Skicka sms-konversationer Skype för företag.

Vi erbjuder för närvarande inte kundkontroll över krypteringsnycklarna för Skype mötessändning och uppladdning Skype mötesinnehåll. Istället krypteras innehållet tillsammans med allt annat innehåll i Office 365.

### <a name="customer-key-with-hybrid-deployments"></a>Kundnyckel med hybriddistributioner

Kundnyckel krypterar bara data i vila i molnet. Kundnyckeln fungerar inte för att skydda dina lokala postlådor och filer. Du kan kryptera lokala data med en annan metod, till exempel genom att BitLocker.

## <a name="about-the-data-encryption-policy-dep"></a>Om datakrypteringsprincipen (DEP)

En datakrypteringsprincip definierar krypteringshierarkin för att kryptera data med hjälp av de nycklar du anger samt den tillgänglighetsnyckel som skyddas av Microsoft. Du skapar DEP:er med PowerShell-cmdlets, som är olika för varje tjänst, och tilldelar de här DEP:erna för att kryptera programdata. Till exempel:

**Exchange Online och Skype för företag** Du kan skapa upp till 50 DEP per klientorganisation. Du kopplar DEP:er till kundnycklarna i Azure-nyckelvalvet och tilldelar sedan DEPs till enskilda postlådor. När du tilldelar en dep till en postlåda:

- postlådan är markerad för en postlådeflyttning. Baserat på prioriteringar i Microsoft 365 som beskrivs här [Flyttningsförfrågningar Microsoft 365 tjänsten](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).

- Krypteringen sker medan postlådan flyttas. Det kan ta 72 timmar för postlådan att krypteras med den nya dataleverantören. Om postlådorna inte krypteras efter att du har väntat 72 timmar från den tid du tilldelade deP kontaktar du Microsoft.

Senare kan du antingen uppdatera DEP eller tilldela en annan DEP till postlådan enligt beskrivningen i Hantera [kundnyckel för Office 365.](customer-key-manage.md) Varje postlåda måste ha lämpliga licenser för att kunna tilldela en dep. Mer information om licensiering finns i [Innan du konfigurerar kundnyckel.](customer-key-set-up.md#before-you-set-up-customer-key)

> [!NOTE]
> DEP kan tillämpas på en delad postlåda, en gemensam mapppostlåda och Microsoft 365-grupppostlåda för klientorganisationen som uppfyller licensieringskravet för användarpostlådor, även om vissa av de här postlådetyperna inte kan vara en tilldelad licens (postlåda för offentlig mapp och Microsoft 365-grupppostlåda) eller behöver en licens för att öka lagringsutrymmet (delad postlåda).

**SharePoint online-, OneDrive för företag- och Teams filer** Om du använder multi geofunktionen kan du skapa upp till en dep per geo för organisationen. Du kan använda olika kundnycklar för varje geo. Om du inte använder multi-geofunktionen kan du bara skapa en DEP per klientorganisation. När du tilldelar DEP påbörjas krypteringen automatiskt men kan ta lite tid att slutföra. Mer information finns i [Konfigurera kundnyckel.](customer-key-set-up.md)

## <a name="leaving-the-service"></a>Lämna tjänsten

Kundnyckel hjälper dig att uppfylla efterlevnadsskyldigheter genom att tillåta dig att återkalla dina nycklar när du lämnar Microsoft 365 tjänst. När du återkallar dina nycklar när du lämnar tjänsten tas tillgänglighetsnyckeln bort, vilket resulterar i att dina data tas bort av kryptografik. Cryptographic deletion mitigates the risk of data remanence which is important for meeting both security and compliance obligations. Mer information om datarensningsprocessen och återkallelse av nycklar finns i Återkalla dina nycklar och starta [en datarensningssökväg.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

### <a name="encryption-ciphers-used-by-customer-key"></a>Krypteringschiffrer som används av kundnyckeln

Kundnyckel använder en mängd olika krypterings-chiffer för att kryptera nycklar, som visas på följande bilder.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Krypteringschiffrar som används för att kryptera nycklar Exchange Online och Skype för företag

![Krypterings-chiffer för Exchange Online-kundnyckel](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Krypteringskrypteringar som används för att kryptera nycklar SharePoint online-, OneDrive för företag- och Teams filer

![Krypterings-chiffer för SharePoint online-kundnyckel](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera kundnyckel](customer-key-set-up.md)

- [Hantera kundnyckel](customer-key-manage.md)

- [Rulla eller rotera Customer Key eller en tillgänglighetsnyckel](customer-key-availability-key-roll.md)

- [Läs mer om tillgänglighetsnyckeln](customer-key-availability-key-understand.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Tjänstkryptering](office-365-service-encryption.md)