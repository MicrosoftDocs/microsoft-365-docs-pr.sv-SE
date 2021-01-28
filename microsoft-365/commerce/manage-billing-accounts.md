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
description: Lär dig mer om fakturerings konton och hur du hanterar dem.
ms.openlocfilehash: 2382396c348fab0b24a269e9678193041ac2c19e
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032639"
---
# <a name="manage-billing-accounts"></a>Hantera faktureringskonton

Ett fakturerings konto skapas när du registrerar dig för att försöka köpa Microsoft-produkter. Du använder ditt fakturerings konto för att hantera dina konto inställningar, fakturor, betalnings metoder och inköp. Du kan ha till gång till flera fakturerings konton. Du registrerade dig för Microsoft 365 direkt, eller så har du till gång till organisationens företags avtal för Microsoft Product & Services eller Microsoft Customer Agreement. För varje scenario har du ett separat fakturerings konto.

Administrations Center för Microsoft 365 stöder för närvarande följande typ av fakturerings konto:

- Microsoft Online Services-program: detta konto skapas när du registrerar dig för en Microsoft 365-prenumeration direkt.
- Programmet Microsoft Product & Services Agreement (MPSA): detta fakturerings konto skapas när organisationen signerar ett MPSA volym licens avtal för att köpa program vara och online tjänster.
- Microsoft-kundavtal: detta konto skapas när din organisation samarbetar med en Microsoft-representant, en godkänd partner eller köp oberoende.

På sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">fakturerings konton</a> får du en översikt över dina kommersiella konton hos Microsoft. Som standard har din organisation minst ett fakturerings konto som är kopplat till ett avtal som accepteras antingen vid direkt köpet, eller genom ett avtal för volym licensiering.

## <a name="understand-billing-account-details"></a>Förstå konto uppgifter för fakturering

Den övre delen av sidan **fakturerings konto** information är din konto profil och innehåller juridisk information om din organisation. Du kan uppdatera din profil för att ändra din juridiska adress och telefonnummer. Det här kontot är den juridiska personen som betalar för produkterna du köper.

I följande tabell visas de viktiga villkor som visas på sidan **fakturerings konton** .

| Fält namn | Beskrivning |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Såld adress | Juridisk person som ansvarar för betalning och som identifieras på fakturan. Adressen som anges här används för att fastställa din momssats, såvida du inte väljer att ange en alternativ leveransadress under köpet. Mer information finns i [Momsinformation](billing-and-payments/tax-information.md). |
| Delen | Ett skrivskyddat fält som identifierar företags segmentet för din organisation (kommersiell, utbildning, myndighets eller ideellt). |
| Konto status | Ett skrivskyddat fält som anger statusen för ditt kommersiella konto hos Microsoft. |
| Skatte-ID | Om du befinner dig utanför USA måste du ange en VAT eller lokal motsvarighet. Mer information finns i [Momsinformation](billing-and-payments/tax-information.md). |
| Enighet | När ett fakturerings konto skapas, antingen via direkt inköp eller med ett avtal för volym licensiering, godkänner en undertecknare för organisationen eller loggar en överenskommelse som beskriver villkoren & villkoren för kontot. I tillämpliga fall visas en avtals historik i den här vyn. Om du måste acceptera uppdaterade villkor visas en länk för godkännande av **avtalet** . |
| Fakturerings profiler | En fakturerings profil definierar egenskaperna för din faktura, till exempel vem som tar emot räkningen, hur fakturan levereras, betalnings villkor och ett inköps order nummer. Om du vill distribuera fakturering i organisationen kan du skapa flera fakturerings profiler och identifiera lämplig fakturerings profil vid inköps tillfället. Mer information om fakturerings profiler och hur du kan använda dem för att skapa flexibla fakturerings alternativ för din organisation genom att [hantera fakturerings profiler](billing-and-payments/manage-billing-profiles.md). |

> [!NOTE]
> Om du vill ändra namnet eller adressen som **sålts** , men inte ser en **redigerings** länk, måste du  [kontakta supporten](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) för att ändra den. Begäran om en ändring av en **säljare till** namn kräver en kredit kontroll. Du kan dela med dig av ett av följande dokument med Microsoft när du kontaktar supporten: 
>
> - Statlig utfärdad handling eller registrerings brev
> - Skriva ut från det lokala företagets register
>
> Support kan hjälpa med namn-och adress ändringar där bara kundens namn ändras, men enheten är oförändrad. Dokumentationen bör tydligt visa att endast enhetens namn har ändrats. Om ändringen är resultatet av en transaktion, inklusive försäljning av affärer, ändringar av kontroller eller en Divestiture eller "spinoff" för en kunds dotter bolag, kontaktar du din Microsoft-säljare.

## <a name="shipping-addresses"></a>Leverans adresser

I det här avsnittet visas de leverans adresser som är kopplade till ditt fakturerings konto. När du köper ett inköp kan du använda den här adressen för att identifiera var köpet levereras eller används. Leverans adressen är redigerbar. Du kan lägga till en leverans adress eller uppdatera den befintliga adressen. Denna adress används för att bestämma moms satsen för köpet.

## <a name="understand-access-to-billing-accounts"></a>Förstå åtkomst till fakturerings konton

Du kan ge andra åtkomst till fakturerings kontot i administrations centret för Microsoft 365 via roller och behörigheter. Endast ett fakturerings konto får ge åtkomst till ett fakturerings konto. Du kan tilldela användarna en av följande roller:

- Ägare till fakturerings **konto** &mdash; Kan tilldela behörigheter, redigera konton, signera avtal och Visa konton.
- Deltagare i fakturerings **konto** &mdash; Kan redigera konton, signera avtal och Visa konton.
- Läsare för fakturerings **konto** &mdash; Kan visa konton.

> [!Note]
> Fakturerings konto roller gäller endast för fakturerings konton och gäller inte andra Microsoft 365 Admin Center-scenarier.

## <a name="related-articles"></a>Relaterade artiklar

[Momsinformation](billing-and-payments/tax-information.md)

[Hantera faktureringsprofiler](billing-and-payments/manage-billing-profiles.md)
