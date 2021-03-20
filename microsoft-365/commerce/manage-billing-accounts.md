---
title: Hantera faktureringskonton
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Läs mer om faktureringskonton och hur du hanterar dem.
ms.openlocfilehash: c2cf7584148bb846541328396885d20c00e2712a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911428"
---
# <a name="manage-billing-accounts"></a>Hantera faktureringskonton

Ett faktureringskonto skapas när du registrerar dig för att prova eller köpa Microsoft-produkter. Du använder ditt faktureringskonto för att hantera dina kontoinställningar, fakturor, betalningsmetoder och köp. Du kan ha åtkomst till flera faktureringskonton. Om du till exempel registrerade dig för Microsoft 365 direkt eller om du har åtkomst till din organisations Enterprise-avtal, Microsofts &-tjänstavtal eller Microsofts kundavtal. För var och en av de här scenarierna skulle du ha ett separat faktureringskonto.

Administrationscentret för Microsoft 365 har för närvarande stöd för följande typer av faktureringskonton:

- Microsoft Online Services Program: Det här faktureringskontot skapas när du registrerar dig för en Microsoft 365-prenumeration direkt.
- Microsoft Products & Services Agreement (MPSA) Program: Det här faktureringskontot skapas när din organisation signerar ett MPSA-volymlicensieringsavtal för att köpa programvara och onlinetjänster.
- Microsofts kundavtal: Det här faktureringskontot skapas när din organisation arbetar med en Microsoft-representant, en auktoriserad partner eller köp oberoende av varandra.

Sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Faktureringskonton</a> ger dig en vy av dina kommersiella konton med Microsoft. Som standard har organisationen minst ett faktureringskonto som är kopplat till ett avtal som accepteras antingen vid ett direktköp eller via ett volymlicensieringsarrangemang.

## <a name="understand-billing-account-details"></a>Förstå faktureringskontoinformation

Längst upp på **informationssidan för faktureringskonton** finns din kontoprofil och innehåller juridisk och skatteinformation om din organisation. Du kan uppdatera din profil för att ändra din juridiska adress och ditt telefonnummer. Det här kontot är den juridiska enheten som betalar för produkterna som du köper.

I följande tabell visas de viktiga termer som visas på **informationssidan för** faktureringskonton.

| Fältnamn | Beskrivning |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Såld till-adress | Den juridiska person som ansvarar för betalningen och som identifieras på fakturan. Adressen som anges här används för att fastställa din momssats, såvida du inte väljer att ange en alternativ leveransadress under köpet. Mer information finns i [Momsinformation](billing-and-payments/tax-information.md). |
| Segment | Ett skrivskyddsfält som identifierar affärssegmentet i din organisation (kommersiellt, utbildnings-, myndighets- eller ideellt). |
| Kontostatus | Ett skrivskyddsfält som anger statusen för ditt kommersiella konto hos Microsoft. |
| Skatte-ID | Om du befinner dig utanför USA måste du betala moms eller en lokal motsvarighet. Mer information finns i [Momsinformation](billing-and-payments/tax-information.md). |
| Avtal | När ett faktureringskonto skapas, antingen genom ett direktköp eller genom ett volymlicensieringsarrangemang, accepterar eller signerar en lösning för organisationen ett avtal som beskriver villkoren & för kontot. I den här vyn visas en avtalshistorik, om tillämpligt. Om du måste godkänna uppdaterade villkor visas en länk för **Godkänn** avtal. |
| Faktureringsprofiler | En faktureringsprofil definierar egenskaper för fakturan, till exempel vem som får fakturan, hur fakturan levereras, betalningsvillkor och ett inköpsordernummer. För att distribuera fakturering i hela organisationen kan du skapa flera faktureringsprofiler och identifiera lämplig faktureringsprofil vid köpet. Mer information om faktureringsprofiler och hur du kan använda dem för att skapa mer flexibla faktureringsalternativ för din organisation finns [i Förstå faktureringsprofiler.](billing-and-payments/manage-billing-profiles.md) |

> [!NOTE]
> Om du behöver ändra **Såld till-namnet** eller adressen,  men inte ser länken Redigera, måste du [kontakta support för](../admin/contact-support-for-business-products.md) att ändra den. Begäranden för ändring **av Såld till-namn** kräver en kreditkontroll. Fyll [i det](https://www.microsoft.com/download/details.aspx?id=102732)här formuläret och gör dig redo att dela något av följande dokument med Microsoft när du kontaktar supporten:
>
> - Dokument eller registreringsbrev utfärdat av myndighet
> - Skriva ut från det lokala företagets register
>
> Supporten kan hjälpa dig med namn- och adressändringar där bara kundens namn ändras, men enheten förblir oförändrad. Den dokumentation som tillhandahålls bör tydligt visa att endast enhetens namn har ändrats. Om ändringen är resultatet av en transaktion, inklusive försäljning av företag, ändring av kontroller eller en utförsäljning eller "rotation" av en kundpartner, ska du kontakta din Microsoft-återförsäljare.

## <a name="shipping-addresses"></a>Leveransadresser

Det här avsnittet innehåller leveransadresserna som är kopplade till ditt faktureringskonto. När du gör ett köp kan du använda den här adressen för att identifiera var köpet levererades eller användes. Leveransadressen kan redigeras. Du kan lägga till en leveransadress eller uppdatera den befintliga adressen. Den här adressen används för att fastställa momssatsen för ditt köp.

## <a name="understand-access-to-billing-accounts"></a>Förstå åtkomst till faktureringskonton

Du kan ge andra åtkomst till faktureringskontot i administrationscentret för Microsoft 365 via roller och behörigheter. Endast en faktureringskontoägare kan bevilja åtkomst till ett faktureringskonto. Du kan tilldela en av följande roller till användare:

- **Faktureringskontoägare** &mdash; Kan tilldela behörigheter, redigera konton, signera avtal och visa konton.
- **Deltagare i faktureringskonto** &mdash; Kan redigera konton, signera avtal och visa konton.
- **Läsare av faktureringskonto** &mdash; Kan visa konton.

> [!Note]
> Faktureringskontoroller gäller endast faktureringskonton och gäller inte för andra scenarier i administrationscentret för Microsoft 365.

## <a name="related-content"></a>Relaterat innehåll

[Skatteinformation](billing-and-payments/tax-information.md) (artikel) \
[Förstå faktureringsprofiler](billing-and-payments/manage-billing-profiles.md) (artikel)