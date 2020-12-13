---
title: Anslut din domän till Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Lär dig verifiera din domän och skapa DNS-poster på vilken DNS-värd som helst för Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 206b435130e8e77ed1540432e3bbeff7f16463bf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658221"
---
# <a name="connect-your-domain-to-microsoft-365"></a>Anslut din domän till Microsoft 365

> [!NOTE]
> Om du inte lägger till en domän kommer personer i organisationen att använda domänen onmicrosoft.com för sina e-postadresser tills du gör det. Det är viktigt att lägga till domänen innan du lägger till användare, så att du inte behöver konfigurera dem två gånger.

[Läs frågor och svar om domäner](../setup/domains-faq.yml) om du inte hittar det du letar efter nedan.

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Lägga till en MX-post så att e-post för din domän kommer till Microsoft.

Du får information om MX-posten från administrationscentrets konfigurationsguide.

Lägg till en ny MX-post på värdens webbplats.
Kontrollera att fälten är inställda på följande värden:

- Posttyp: `MX`
- Prioritet: Ange det högsta värdet, vanligtvis `0`.
- Värdnamn: `@`
- Pekar på adress: Kopiera värdet från administrationscentret och klistra in det här.
- TTL: `3600‎` (eller din leverantörs standard)

Spara posten och ta bort eventuella andra MX-poster.

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>Lägg till en CNAME-post för att ansluta användare till deras brevlådor
Du får information om CNAME-posterna från administrationscentrets konfigurationsguide.

Lägg till följande CNAME-post på din webbhotellleverantörs webbplats. Kontrollera att fälten är inställda på följande värden för varje:

- Posttyp: `CNAME (Alias)`
- Värd: Klistra in värdena som du kopierar från administrationscentret här.
- Pekar på adress: Kopiera värdet från administrationscentret och klistra in det här.
- TTL: `3600‎` (eller din leverantörs standard)

## <a name="add-a-txt-record-to-help-prevent-spam"></a>Lägga till en TXT-post för SPF för att förhindra skräppost
**Innan du börjar:** Om du redan har en SPF-post för domänen ska du inte skapa en ny för Microsoft 365. Lägg istället till de obligatoriska Microsoft 365-värdena i den aktuella posten på din värds webbplats så att du har en *enda* SPF-post som innehåller båda uppsättningarna med värden.

Redigera den befintliga SPF-posten eller skapa en SPF-post på värdens webbplats.
Kontrollera att fälten är inställda på följande värden:

- Posttyp: `TXT (Text)`
- Värd: `@`
- TXT Value: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (eller din leverantörs standard)

Spara posten.

Använd något av följande [SPF-verifieringsverktyg](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) för att verifiera SPF-posten

SPF har utformats för att hjälpa till att förhindra förfalskning men det finns förfalskningsmetoder som SPF inte skyddar mot. För att skydda mot dessa ska du, efter att ha konfigurerat SPF, även konfigurera DKIM och DMARC för Microsoft 365.

Information om hur du kommer igång finns i [Använda DKIM för att validera utgående e-post som skickas från din domän i Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) och [Använda DMARC för att validera e-post i Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

Slutligen, gå tillbaka till administratörscentrets domäninställningsguide för att slutföra installationen.
