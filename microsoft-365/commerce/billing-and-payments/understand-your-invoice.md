---
title: Förstå din faktura
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Läs om hur du läser och förstår din faktura för Microsofts affärsprodukter.
keywords: faktureringskonton, organisationsinformation, fakturor
ms.openlocfilehash: 3028b0e8aa952b932e7d56a5ecceaad5931dee30
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634986"
---
# <a name="understand-your-invoice"></a>Förstå din faktura

Fakturan innehåller en sammanfattning av dina avgifter och instruktioner för betalning. Du kan [visa din onlinefaktura](#view-your-online-invoice) i administrationscentret för Microsoft 365. Du kan också ladda ner den i Portable Document Format (.pdf) för att skicka via e-post.

Om du bara har en Microsoft 365-prenumeration läser [du Visa fakturan för Microsoft 365 för företag](view-your-bill-or-invoice.md).

## <a name="understand-the-invoice-header"></a>Förstå fakturahuvudet

Överst på första sidan identifierar vem som är ansvarig för betalning, var fakturan skickas till och en sammanfattning av avgifterna.

| Benämna | Beskrivning |
| --- | --- |
| Såld till |Faktureringskontot som identifierar namn och adress på den juridiska person som ansvarar för betalningen. Den här informationen kan hanteras på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Faktureringskonton,</a> där du kan hitta kontoavtalet och hantera roller och behörigheter. |
| Fakturera till |Identifierar vem som tar emot fakturan. Den här informationen kan hanteras på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringsprofiler.</a> Faktureringsprofilen visas också på sidan onlinefaktura i avsnittet **Fakturasammanfattning.** Mer information om faktureringsprofiler och hur du kan använda dem för att skapa mer flexibla faktureringsalternativ för din organisation finns i [Hantera faktureringsprofiler](manage-billing-profiles.md). |
| Faktureringsprofil |Namnet på faktureringsprofilen som används för att definiera fakturaegenskaper som Faktura till, INKÖPSORDERnummer och betalningsvillkor. Den här informationen kan hanteras på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringsprofiler.</a> Mer information om faktureringsprofiler och hur du kan använda dem för att skapa mer flexibla faktureringsalternativ för din organisation finns i [Hantera faktureringsprofiler](manage-billing-profiles.md). |
| Fakturanummer |Ett unikt, Microsoft-genererat fakturanummer som används för spårning. |
| Fakturadatum |Datum då fakturan genereras, vanligtvis fem till tolv dagar efter faktureringsperiodens. Du kan kontrollera fakturadatumet på sidan för faktureringsprofilinformation. Avgifter som inträffar mellan slutet av faktureringsperioden och fakturadatumet inkluderas i fakturan för nästa månad, eftersom de befinner sig i nästa faktureringsperiod. Start- och slutdatum för faktureringsperioden för varje faktura visas i faktura-PDF-filen ovanför **Faktureringssammanfattning**.|
| Betalningsvillkor |Hur du betalar för din Microsoft-faktura. *Netto 30 dagar* innebär att du betalar genom att följa instruktionerna på din faktura, inom 30 dagar från fakturadatumet. |

## <a name="understand-the-billing-summary"></a>Förstå faktureringssammanfattningen

**Faktureringssammanfattningen** visar sammanfattningen av avgifter sedan föregående faktureringsperiod, eventuella krediter som tillämpats, skatt och det totala förfallna beloppet.

| Benämna | Beskrivning |
| --- | --- |
| Debitering|Totalt antal produkter som köpts för den här faktureringsperioden och deras relaterade avgifter och skatter. Inköp aggregeras för att ge en kortfattad bild av din faktura. |
| Krediter |Krediter du fått från returer |
| Azure-krediter tillämpas |Dina Azure-krediter som automatiskt tillämpas på Azure debiterar varje faktureringsperiod. Om du inte har några Azure-krediter döljs det här fältet. Mer information om Azure-krediter finns i [Spåra Microsoft Kundavtal Azure kreditsaldo](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance). |
| Delsumma |Det förfallna beloppet före skatt |
| Moms |Den typ och det skattebelopp du betalar, beroende på land i din faktureringsprofil. Om du inte behöver betala skatt visas ingen skatt på fakturan. |

### <a name="understand-your-charges"></a>Förstå dina avgifter

Avgiftssidorna visar kostnaden uppdelad efter produkt. För Azure-kunder kan avgifterna ordnas efter fakturaavsnitt. Mer information om hur fakturaavsnitt används med Azure-produkter finns i [Fakturaavsnitt](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) i [Komma igång med ditt faktureringskonto för Microsoft Kundavtal](https://docs.microsoft.com/azure/billing/billing-mca-overview). Inom varje produktorder delas kostnaden upp efter servicefamilj.

| Benämna |Beskrivning |
| --- | --- |
| Enhetspris | Det effektiva enhetspriset för tjänsten (i prissättningsvalutan) som används för att beräkna avgiften. Detta pris är unikt för en produkt, servicefamilj, mätare och erbjudande. |
| Ant | Kvantitet som köpts eller förbrukats under faktureringsperioden |
| Avgifter/krediter | Nettobelopp för avgifter efter krediter/återbetalningar tillämpas |
| Azure-kredit | Mängden Azure-krediter som tillämpas på avgifterna/krediterna |
| Skattesats | Skattesats, beroende på land |
| Skattebelopp | Skattebelopp som tillämpas på köpet baserat på skattesats |
| Summa | Det totala belopp som ska betalas för köpet |

Radartiklars information varierar beroende på vilken typ av produkt du debiteras för. För Azure-produkter visas till exempel mängden Azure-krediter som tillämpas. Seat-baserade produkter visar ett enhetspris och kvantitet. Fakturainformationen beskriver de inköpta produkterna, rabatten eller krediterna som har tillämpats, skattesats och belopp samt radartikelsum summan.

`Total = Charges - Azure Credit + Tax`

Det totala beloppet för varje tjänstefamilj beräknas genom att du subtraherar Azure-krediter från krediter/avgifter och lägger till moms:

`Total = Charges/Credits - Azure Credit + Tax`

Om det finns Azure-avgifter på din faktura som du vill ha mer information om läser du [Förstå debiteringar på din Faktura för Microsoft-kundavtal](https://docs.microsoft.com/azure/billing/billing-mca-understand-your-bill).

## <a name="understand-the-last-invoice-page"></a>Förstå den senaste fakturasidan

### <a name="payment-instructions"></a>Betalningsinstruktioner

Längst ner på fakturan finns instruktioner om hur du betalar din faktura. Du kan betala via tråd, check eller online.

### <a name="publisher-information"></a>Information om Utgivare

Om du har tjänster från tredje part i fakturan visas namnet och adressen för varje utgivare längst ned på fakturan.

## <a name="view-your-online-invoice"></a>Visa din onlinefaktura

Fakturor finns tillgängliga online. En länk till din onlinefaktura finns tillgänglig från din PDF-faktura och från ett e-postmeddelande. Onlinefakturan kan utökas så att du kan visa debiteringarna på fakturan och se mer information för varje artikel. Onlinefakturan innehåller:

- **Prisinformation** &mdash; Ytterligare information inklusive information om rabatter och produktpriser.

- **Onlinebetalning** &mdash; Du kan välja att göra en betalning online från fakturan.

- **Azure kostnadshantering** &mdash; För Azure-kunder innehåller onlinefakturor en länk till Azure kostnadshantering.

### <a name="to-view-your-online-invoice"></a>Så här visar du din onlinefaktura

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.

2. Om du vill hämta PDF-versionen av fakturan väljer du **Hämta faktura-PDF** på raden för den faktura du vill se.

3. Om du vill visa din onlinefaktura väljer du en faktura i listan. Du kan också ladda ner .pdf från sidan med fakturainformation.

## <a name="need-help-contact-support"></a>Behöver du hjälp? Kontakta supporten.

Om du har frågor eller behöver hjälp med dina Azure-krediter <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">skapar du en supportbegäran med Azure-support</a>.

Om du har frågor eller behöver hjälp med fakturan i Microsoft 365 admin center, [kontakta support för affärsprodukter](../../admin/contact-support-for-business-products.md).
