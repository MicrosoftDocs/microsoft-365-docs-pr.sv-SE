---
title: BitLocker för kryptering
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
description: Lär dig mer Office 365 hur BitLocker kryptering, vilket minskar risken för datastöld på grund av förlorade eller stulna datorer och diskar.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "52161559"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker och DKM (Distributed Key Manager) för kryptering

Microsoft-servrar BitLocker kryptera diskenheter som innehåller kunddata i vila på volymnivå. BitLocker kryptering är en funktion för dataskydd som är inbyggd i Windows. BitLocker är en av de tekniker som används för att skydda mot hot om det skulle upphöra att gälla i andra processer eller kontroller (t.ex. åtkomstkontroll eller återanvändning av maskinvara) som kan leda till att någon får fysisk åtkomst till diskar som innehåller kunddata. I det här BitLocker bort risken för datastöld eller exponering på grund av förlorade, stulna eller olämpligt inaktiverade datorer och diskar.

BitLocker har distribuerats med AES-kryptering (Advanced Encryption Standard) på 256-bitars kryptering på diskar som innehåller kunddata i Exchange Online, SharePoint Online och Skype för företag. Diskarverna är krypterade med en FVEK-nyckel (Full Volume Encryption Key), som är krypterad med VMK (Volume Master Key), som i sin tur är bunden till TPM (Trusted Platform Module) på servern. VMK skyddar FVEK direkt och skyddar därför VMK:n kritiskt. Följande bild illustrerar ett exempel på en BitLocker nyckelskyddskedja för en viss server (i det här fallet en Exchange Online server).

I följande tabell beskrivs BitLocker nyckelskyddskedjan för en viss server (i det här fallet en Exchange Online server).

| KEYTANGENTTANGENTEN | GRANULARITY | HUR GENERERAS DETTA? | VAR LAGRAS DEN? | PROTECTION |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256-bitars extern nyckel | Per Server | BitLocker API:er | TPM eller Valv | Lockbox/åtkomstkontroll |
|  |  |  | Mailbox Server Registry | TPM krypterat |
| Numeriskt lösenord med 48 siffror | Per Disk | BitLocker API:er | Active Directory | Lockbox/åtkomstkontroll |
| X.509-certifikat som dataåterställningsagent (DRA) kallas även Public Key Engström | Miljö (t.ex. Exchange Online multitenant) | Microsoft CA | Versionssystem | Ingen användare har hela lösenordet till den privata nyckeln. Lösenordet är under fysiskt skydd. |


BitLocker nyckelhantering omfattar hantering av återställningsnycklar som används för att låsa upp/återställa krypterade diskar i ett Microsoft-datacenter. Microsoft 365 lagras huvudnycklarna i en säker delning, endast tillgängliga för personer som har gått igenom och godkänts. Autentiseringsuppgifterna för nycklarna lagras i en säker lagringsplats för åtkomstkontrolldata (det som vi kallar en "hemlig lagring"), vilket kräver en hög nivå av godkännanden för höjd och hantering för åtkomst med hjälp av ett snabbåtkomstverktyg.

BitLocker som hanterar nycklar, indela i två hanteringskategorier:

- BitLocker kort hanterade nycklar, som i allmänhet är kortare och knutna till livslängden för en operativsystemsinstans som är installerad på en server eller på en viss disk. De här nycklarna tas bort och återställs vid serverinstallation eller diskformatering.

- BitLocker återställningsnycklar som hanteras utanför BitLocker men används för diskkryptering. BitLocker använder återställningsnycklar för det scenario där ett operativsystem installeras om och krypterade datadiskar redan finns. Återställningsnycklar används också av avsökningsnycklar för hanterad tillgänglighet i Exchange Online där en svarare kan behöva låsa upp en disk.

BitLocker krypteras med en fullständig volymkrypteringsnyckel, som i sin tur krypteras med en volymhanterare. BitLocker använder FIPS-kompatibla algoritmer för att säkerställa att krypteringsnycklar aldrig lagras eller skickas via wire i klar. Implementeringen Microsoft 365 av kundens data-i-vilskydd avviker inte från standardimplementering av BitLocker data.
