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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Läs mer om faktureringskonton och hur du hanterar dem.
ms.openlocfilehash: 87cc861ab48b99106a3cbd50d8ded91205ffb0a2
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402612"
---
# <a name="manage-billing-accounts"></a>Hantera faktureringskonton

Ett faktureringskonto skapas när du registrerar dig för att prova eller köpa Microsoft-produkter. Du använder ditt faktureringskonto för att hantera kontoinställningar, fakturor, betalningsmetoder och inköp. Du kan ha tillgång till flera faktureringskonton. Du har till exempel registrerat dig för Microsoft 365 direkt, eller så har du tillgång till organisationens Enterprise Agreement, Microsoft Product & Services Agreement eller Microsoft Customer Agreement. För vart och ett av dessa scenarier skulle du ha ett separat faktureringskonto.

Administrationscentret för Microsoft 365 stöder för närvarande följande typ av faktureringskonton:

- Microsoft Online Services Program: Det här faktureringskontot skapas när du registrerar dig för en Microsoft 365-prenumeration direkt.
- MPSA-program (Microsoft Products & Services Agreement) (Microsoft Products Agreement) (MPSA) Skapas när din organisation undertecknar ett MPSA-volymlicensieringsavtal om att köpa programvara och onlinetjänster.
- Microsofts kundavtal: Det här faktureringskontot skapas när din organisation arbetar med en Microsoft-representant, en auktoriserad partner eller köper oberoende av annat.

Sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Faktureringskonton</a> innehåller en vy över dina kommersiella konton hos Microsoft. Som standard har din organisation minst ett faktureringskonto kopplat till ett avtal som accepteras antingen vid tidpunkten för ett direkt köp eller genom ett volymlicensieringsavtal.

## <a name="understand-billing-account-details"></a>Förstå information om faktureringskonto

Den övre sidan av informationssidan för **faktureringskonton** är din kontoprofil och innehåller juridisk information och skatteinformation om din organisation. Du kan uppdatera din profil för att ändra din juridiska adress och telefonnummer. Det här kontot är den juridiska person som betalar för de produkter som du köper.

I följande tabell visas de viktiga termer som visas på informationssidan **för faktureringskonton.**

| Fältnamn | Beskrivning |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Såld-till-adress | Den juridiska person som ansvarar för betalning och som anges på fakturan. Adressen som anges här används för att bestämma din skattesats om du inte väljer att ange en alternativ leveransadress under ditt köp. Mer information finns i [Skatteinformation](billing-and-payments/tax-information.md). |
| Segment | Ett skrivskyddat fält som identifierar affärssegmentet i din organisation (Commercial, Education, Government eller Non-profit). |
| Kontostatus | Ett skrivskyddat fält som anger status för ditt kommersiella konto hos Microsoft. |
| Skatte-ID | Om du befinner dig utanför USA måste du ange en moms eller lokal motsvarighet. Mer information finns i [Skatteinformation](billing-and-payments/tax-information.md). |
| Avtal | När ett faktureringskonto skapas, antingen genom ett direktköp eller ett volymlicensieringsarrangemang, accepterar eller undertecknar en undertecknare ett avtal som beskriver villkoren & villkoren för kontot. Om tillämpligt visas en avtalshistorik i den här vyn. Om du måste acceptera uppdaterade villkor visas en länk för **Godkänn-avtal.** |
| Faktureringsprofiler | En faktureringsprofil definierar egenskaperna för fakturan, till exempel vem som tar emot fakturan, hur fakturan levereras, betalningsvillkor och ett inköpsordernummer. Om du vill distribuera fakturering över hela organisationen kan du skapa flera faktureringsprofiler och identifiera lämplig faktureringsprofil vid inköpstillfället. Mer information om faktureringsprofiler och hur du kan använda dem för att skapa mer flexibla faktureringsalternativ för din organisation finns [i Hantera faktureringsprofiler](billing-and-payments/manage-billing-profiles.md). |

> [!NOTE]
> Om du vill ändra namnet eller adressen **Som ska säljas,** men inte ser någon **redigera-länk,** måste du [kontakta supporten](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) för att ändra den. Begäran om en **namnändring som ska säljas** kräver en kreditkontroll. När du kontaktar supporten ska du ha något av följande dokument klart:
>
> - Externt meddelandedokument som indikerar eventuella förändringar i företagets namn eller företagsstruktur
> - Regeringen utfärdade dokument eller registreringsbrev
> - Skriv ut från det lokala företagets register
>
> Support kan hjälpa till med namn- och adressändringar där endast kundnamnet ändras, men entiteten förblir densamma. Dokumentation som lämnas bör tydligt ange att endast enhetens namn har ändrats. Om ändringen är relaterad till en transaktion, som en försäljning av verksamheten, eller en avyttring eller "spinoff" av en kundpartner, vänligen kontakta din Microsoft-säljare.

## <a name="shipping-addresses"></a>Leveransadresser

I det här avsnittet visas de leveransadresser som är kopplade till ditt faktureringskonto. När du gör ett köp kan du använda den här adressen för att identifiera var ditt köp levereras eller används. Leveransadressen är redigerbar. Du kan lägga till en leveransadress eller uppdatera den befintliga adressen. Den här adressen används för att bestämma skattesatsen för ditt köp.

## <a name="understand-access-to-billing-accounts"></a>Förstå åtkomst till faktureringskonton

Du kan ge andra åtkomst till faktureringskontot i Microsoft 365-administrationscentret via roller och behörigheter. Endast en ägare av faktureringskontot kan bevilja åtkomst till ett faktureringskonto. Du kan tilldela en av följande roller till användare:

- **Ägare av** &mdash; faktureringskonto Kan tilldela behörigheter, redigera konton, signera avtal och visa konton.
- **Deltagare på faktureringskonto** &mdash; Kan redigera konton, signera avtal och visa konton.
- **Läsare av** &mdash; faktureringskonto Kan visa konton.

> [!Note]
> Faktureringskontoroller gäller bara för faktureringskonton och gäller inte för andra Microsoft 365-administratörscenterscenarier.

## <a name="related-articles"></a>Relaterade artiklar

[Momsinformation](billing-and-payments/tax-information.md)

[Hantera faktureringsprofiler](billing-and-payments/manage-billing-profiles.md)