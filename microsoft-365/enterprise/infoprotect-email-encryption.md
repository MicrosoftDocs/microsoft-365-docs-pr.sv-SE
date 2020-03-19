---
title: 'Steg 6: Konfigurera e-postkryptering'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Förstå och konfigurera hantering av privilegierad åtkomst för Office 365.
ms.openlocfilehash: d678c109f42901be2413c2b33e362d6796be96b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42805644"
---
# <a name="step-6-configure-email-encryption"></a>Steg 6: Konfigurera e-postkryptering

*Det här steget är valfritt och gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![Fas 6: Informationsskydd](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Det finns tre typer av e-postkryptering i Microsoft 365.

|||
|:-------|:-----|
| Kryptering av Office-meddelanden (OME) | Kryptering för Exchange Online-e-post som skickas utanför organisationen. |
| Hantering av informationsrättigheter (IRM) | Kryptering och behörigheter som reser med e-postmeddelandet. |
| Säkra/multifunktionella Internet-e-posttillägg (S/MIME) | E-postskydd med kryptering och digitala signaturer. |
|||

## <a name="office-365-message-encryption"></a>Kryptering av Office 365-meddelanden

Med OME kan din organisation skicka och ta emot krypterade e-postmeddelanden mellan personer inom och utanför organisationen. OME fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster. Kryptering av e-postmeddelanden säkerställer att endast avsedda mottagare kan visa meddelandet.

![OME-kryptering av e-postmeddelanden](../media/infoprotect-email-encryption/ome-encryption.png)

Du ställer in transportregler som definierar villkoren för kryptering. När en användare skickar ett meddelande som matchar en regel tillämpas kryptering automatiskt.

Om du vill visa krypterade meddelanden kan mottagarna antingen få en engångslösenkod, logga in med ett Microsoft-konto eller logga in med ett arbets- eller skolkonto som är kopplat till Microsoft 365. Mottagarna kan också skicka krypterade svar. De behöver inte en egen Microsoft 365-prenumeration för att visa krypterade meddelanden eller skicka krypterade svar.

Mer information finns i [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).

## <a name="irm"></a>Irm

IRM i Microsoft 365 hjälper dig att skydda din information med ytterligare kryptering och genom att tillämpa en intelligent princip som anger vem som har åtkomst till vad de kan göra. För e-postmeddelanden kan du använda IRM för kryptering och tillämpa användningsbegränsningar. Du kan till exempel ange att vissa mottagare har alla funktioner för att hantera e-postmeddelandet och vissa inte har möjlighet att skriva ut eller vidarebefordra e-postmeddelandet. 

IRM-principer konfigureras i Microsoft 365 och kan tillämpas på dokument i SharePoint Online och e-postmeddelanden. Ett IRM-skyddat e-postmeddelande innehåller de tillämpade principinställningarna som tillämpas och reser med det. 

![IRM-skydd av e-postmeddelanden](../media/infoprotect-email-encryption/irm-protection.png)

När mottagaren öppnar e-postmeddelandet med den medföljande principen används principinställningarna för att dekryptera meddelandet och bestämma vad mottagaren kan göra med det. 

Mer information finns [i Information Rights Management i Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).

## <a name="smime"></a>S/MIME

S/MIME är en digital certifikatbaserad e-postbaserad skyddslösning som gör att du både kan kryptera och signera ett meddelande digitalt. Meddelandekrypteringen säkerställer att endast den avsedda mottagaren kan öppna och läsa meddelandet. En digital signatur hjälper mottagaren att verifiera avsändarens identitet och fastställa att endast avsändaren kan ha skickat den.

![S/MIME-skydd av e-postmeddelanden](../media/infoprotect-email-encryption/smime-protection.png)

S/MIME kan användas för e-post till andra postlådor i din Microsoft 365-prenumeration eller till externa användare.
Både meddelandekryptering och digitala signaturer möjliggörs med hjälp av digitala certifikat som innehåller offentliga och privata nycklar för att kryptera eller dekryptera meddelanden och skapa och verifiera digitala signaturer.
Om du vill använda S/MIME måste du ha de offentliga nycklarna för varje mottagare. Mottagarna behåller sina egna privata nycklar, som måste förbli säkra. Om din privata nyckel äventyras måste du skaffa ett nytt digitalt certifikat och distribuera offentliga nycklar till alla potentiella avsändare.

Mer information finns i [S/MIME för meddelandesignering och kryptering](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).


Som en interimskontrollpunkt, se [exitkriterier som](infoprotect-exit-criteria.md#crit-infoprotect-step6) motsvarar detta steg.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 7](../media/stepnumbers/Step7.png)|[Konfigurera hantering av privilegierad åtkomst för Office 365](infoprotect-configure-privileged-access-management.md)|
