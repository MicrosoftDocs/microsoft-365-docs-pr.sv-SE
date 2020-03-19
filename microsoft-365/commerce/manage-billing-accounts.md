---
title: Hantera faktureringskonton
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Läs mer om faktureringskonton och hur du hanterar dem.
ms.openlocfilehash: ce7b9d2a2cc35261c7e6e3f5547574ea9c49e658
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826273"
---
# <a name="manage-billing-accounts"></a>Hantera faktureringskonton

Ett faktureringskonto skapas när du registrerar dig för att prova eller köpa Microsoft-produkter. Du använder ditt faktureringskonto för att hantera dina kontoinställningar, fakturor, betalningsmetoder och inköp. Du kan ha tillgång till flera faktureringskonton. Du har till exempel registrerat dig för Microsoft 365 direkt, eller så har du tillgång till organisationens Enterprise-avtal, Microsoft Product & Services Agreement eller MicrosoftCustomer Agreement. För vart och ett av dessa scenarier skulle du ha ett separat faktureringskonto.

Administrationscentret för Microsoft 365 stöder för närvarande följande typ av faktureringskonton:

- Microsoft Online Services Program: Det här faktureringskontot skapas när du registrerar dig för en Microsoft 365-prenumeration direkt.
- MPSA-program (Microsoft Products & Services Agreement): Det här faktureringskontot skapas när din organisation undertecknar ett MPSA-volymlicensavtal för att köpa programvara och onlinetjänster.
- Microsofts kundavtal: Det här faktureringskontot skapas när din organisation arbetar med en Microsoft-representant, en auktoriserad partner eller köp självständigt.

Sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Faktureringskonton</a> visar dina kommersiella konton hos Microsoft. Som standard har din organisation minst ett faktureringskonto kopplat till ett avtal som accepteras antingen vid tidpunkten för ett direktköp eller genom ett volymlicensieringsarrangemang.

## <a name="understand-billing-account-details"></a>Förstå information om faktureringskonto

Högst upp på detaljsidan **faktureringskonton** är din kontoprofil och innehåller juridisk och skattemässig information om din organisation. Du kan uppdatera din profil för att ändra din juridiska adress och ditt telefonnummer. Det här kontot är den juridiska personen som betalar för de produkter som du köper.

I följande tabell visas de viktiga termer som visas på detaljsidan **faktureringskonton.**

| Fältnamn | Beskrivning |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Såld adress | Den juridiska person som ansvarar för betalningen och identifieras på fakturan. Adressen som anges här används för att bestämma din skattesats om du inte väljer att ange en alternativ leveransadress under ditt köp. Mer information finns i [Skatteinformation](billing-and-payments/tax-information.md). |
| Segment | Ett skrivskyddat fält som identifierar affärssegmentet i din organisation (Kommersiella, utbildningar, myndigheter eller ideella). |
| Kontostatus | Ett skrivskyddat fält som anger status för ditt kommersiella konto hos Microsoft. |
| Skatte-ID | Om du befinner dig utanför USA måste du ange en moms eller lokal motsvarighet. Mer information finns i [Skatteinformation](billing-and-payments/tax-information.md). |
| Avtal | När ett faktureringskonto skapas, antingen genom ett direktköp eller ett volymlicensieringsarrangemang, accepterar en undertecknare för organisationen, eller undertecknar, ett avtal som beskriver villkoren för kontot &. I förekommande fall visar den här vyn en avtalshistorik. Om du måste acceptera uppdaterade villkor visas en länk för **godkännavtal.** |
| Faktureringsprofiler | En faktureringsprofil definierar egenskaperna för fakturan, till exempel vem som tar emot fakturan, hur fakturan levereras, betalningsvillkor och ett inköpsordernummer. Om du vill distribuera fakturering i hela organisationen kan du skapa flera faktureringsprofiler och identifiera lämplig faktureringsprofil vid inköpstillfället. Om du vill ha mer information om faktureringsprofiler och hur du kan använda dem för att skapa mer flexibla faktureringsalternativ för din organisation hanterar [du faktureringsprofiler](billing-and-payments/manage-billing-profiles.md). |

> [!NOTE]
> Om du vill ändra namnet eller adressen **För såld till,** men inte ser en **redigeralänk,** måste du [kontakta supporten](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) för att ändra den. Begäran om en ändring av **sålda namn** kräver en kreditkontroll. När du kontaktar supporten har du något av följande dokument klart:
>
> - Externt meddelandedokument som anger eventuella ändringar i företagets namn eller företagsstruktur
> - Regeringen utfärdade dokument eller registreringsbrev
> - Skriva ut ur det lokala företagets register
>
> Support kan hjälpa till med namn- och adressändringar där endast kundnamnet ändras, men entiteten förblir densamma. Dokumentation som lämnas bör tydligt ange att endast enhetens namn har ändrats. Om ändringen är relaterad till en transaktion, till exempel en försäljning av företag, eller en avyttring eller "spinoff" av en kundaffiliate, vänligen kontakta din Microsoft-säljare.

## <a name="shipping-addresses"></a>Leveransadresser

I det här avsnittet visas de leveransadresser som är kopplade till ditt faktureringskonto. När du gör ett köp kan du använda den här adressen för att identifiera var ditt köp levereras eller används. Leveransadressen kan redigeras. Du kan lägga till en leveransadress eller uppdatera den befintliga adressen. Den här adressen används för att bestämma skattesatsen för ditt köp.

## <a name="understand-access-to-billing-accounts"></a>Förstå åtkomst till faktureringskonton

Du kan ge andra åtkomst till faktureringskontot i administrationscentret för Microsoft 365 genom roller och behörigheter. Endast en faktureringskontoägare kan ge åtkomst till ett faktureringskonto. Du kan tilldela en av följande roller till användarna:

- **Faktureringskontoägare** &mdash; Kan tilldela behörigheter, redigera konton, signera avtal och visa konton.
- **Faktureringskontodeltagare** &mdash; Kan redigera konton, signera avtal och visa konton.
- **Faktureringskontoläsare** &mdash; kan visa konton.

> [!Note]
> Faktureringskontoroller gäller endast faktureringskonton och gäller inte för andra scenarier i Administrationscentret för Microsoft 365.

## <a name="related-articles"></a>Relaterade artiklar

[Skatteinformation](billing-and-payments/tax-information.md)

[Hantera faktureringsprofiler](billing-and-payments/manage-billing-profiles.md)