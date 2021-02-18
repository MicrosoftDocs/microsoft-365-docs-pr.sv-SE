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
ms.openlocfilehash: 6c90bdd9087a67cc3639cfb06644a5587273dc35
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279304"
---
# <a name="manage-billing-accounts"></a>Hantera faktureringskonton

Ett faktureringskonto skapas när du registrerar dig för att prova eller köpa Microsoft-produkter. Du använder ditt faktureringskonto för att hantera dina kontoinställningar, fakturor, betalningsmetoder och köp. Du kan ha åtkomst till flera faktureringskonton. Du registrerade dig till exempel för Microsoft 365 direkt eller så har du åtkomst till din organisations Enterprise-avtal, Microsofts &-tjänstavtal eller Microsofts kundavtal. För var och en av de här scenarierna skulle du ha ett separat faktureringskonto.

Administrationscentret för Microsoft 365 har för närvarande stöd för följande typer av faktureringskonton:

- Microsoft Online Services Program: Det här faktureringskontot skapas när du registrerar dig för en Microsoft 365-prenumeration direkt.
- Microsoft Products & Services Agreement (MPSA) Program: Det här faktureringskontot skapas när din organisation signerar ett MPSA-volymlicensieringsavtal för att köpa programvara och onlinetjänster.
- Microsofts kundavtal: Det här faktureringskontot skapas när din organisation arbetar med en Microsoft-representant, en auktoriserad partner eller köp oberoende av varandra.

På <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">sidan Faktureringskonton</a> visas microsoft för dina kommersiella konton. Som standard har organisationen minst ett faktureringskonto kopplat till ett avtal som accepteras antingen vid ett direktköp eller genom ett volymlicensieringsarrangemang.

## <a name="understand-billing-account-details"></a>Förstå faktureringskontoinformation

Den översta delen av **informationssidan för faktureringskonton** är din kontoprofil och innehåller juridisk och skatteinformation om din organisation. Du kan uppdatera din profil för att ändra din juridiska adress och ditt telefonnummer. Det här kontot är den juridiska person som betalar för de produkter som du köper.

I följande tabell visas de viktiga termer som visas på **informationssidan för faktureringskonton.**

| Fältnamn | Beskrivning |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Såld till-adress | Den juridiska person som ansvarar för betalningen och som identifieras på fakturan. Adressen som anges här används för att fastställa din momssats, såvida du inte väljer att ange en alternativ leveransadress under köpet. Mer information finns i [Momsinformation](billing-and-payments/tax-information.md). |
| Segment | Ett skrivskyddsfält som identifierar affärssegmentet i organisationen (kommersiell, utbildnings-, myndighets- eller ideell). |
| Kontostatus | Ett skrivskyddsfält som anger statusen för ditt kommersiella konto hos Microsoft. |
| Skatte-ID | Om du befinner dig utanför USA måste du ange en moms eller lokal motsvarighet. Mer information finns i [Momsinformation](billing-and-payments/tax-information.md). |
| Avtal | När ett faktureringskonto skapas, antingen genom ett direkt köp eller genom ett volymlicensieringsarrangemang, accepterar eller signerar en avtal som beskriver villkoren för & för kontot. I den här vyn finns en avtalshistorik, om tillämpligt. Om du måste godkänna uppdaterade villkor visas en länk för **att godkänna** avtalet. |
| Faktureringsprofiler | En faktureringsprofil definierar egenskaper för fakturan, till exempel vem som får fakturan, hur fakturan levereras, betalningsvillkor och ett inköpsordernummer. Om du vill distribuera fakturering i hela organisationen kan du skapa flera faktureringsprofiler och identifiera lämplig faktureringsprofil vid köpet. Mer information om faktureringsprofiler och hur du kan använda dem för att skapa mer flexibla faktureringsalternativ för din organisation finns i [Förstå faktureringsprofiler.](billing-and-payments/manage-billing-profiles.md) |

> [!NOTE]
> Om du behöver ändra namn **eller** adress för Såld  till, men inte ser en redigeringslänk, måste du kontakta [supporten för](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products) att ändra den. Begäranden om ändring **av Såld** till-namn kräver en kreditkontroll. Fyll [i det här](https://www.microsoft.com/download/details.aspx?id=102732)formuläret och var redo att dela något av följande dokument med Microsoft när du kontaktar supporten:
>
> - Myndighets utfärdat dokument eller registreringsbrev
> - Skriva ut från det lokala företagets register
>
> Supporten kan hjälpa dig med namn- och adressändringar där bara kundnamnet ändras, men enheten förblir oförändrad. Dokumentation som ges bör tydligt visa att endast enhetens namn har ändrats. Kontakta din Microsoft-återförsäljare om ändringen är resultatet av en transaktion, inklusive försäljning av verksamhet, ändring av kontroller eller en omslutning eller "rotation"av en kundpartner.

## <a name="shipping-addresses"></a>Leveransadresser

Det här avsnittet innehåller leveransadresserna som är kopplade till ditt faktureringskonto. När du gör ett köp kan du använda den här adressen för att identifiera var köpet levererades eller används. Leveransadressen kan redigeras. Du kan lägga till en leveransadress eller uppdatera den befintliga adressen. Den här adressen används för att fastställa momssatsen för ditt köp.

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