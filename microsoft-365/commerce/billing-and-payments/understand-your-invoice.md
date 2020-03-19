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
description: Läs om hur du läser och förstår fakturan för Microsofts företagsprodukter.
keywords: faktureringskonton, organisationsinformation, fakturor
ms.openlocfilehash: 0ccf8484ba5f8badd29e1a8a54e1b570dd1e0548
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2020
ms.locfileid: "42808125"
---
# <a name="understand-your-invoice"></a>Förstå din faktura

Fakturan innehåller en sammanfattning av dina avgifter och instruktioner för betalning. Du kan [visa din onlinefaktura](#view-your-online-invoice) i administrationscentret för Microsoft 365. Du kan också ladda ner den i Portable Document Format (.pdf) för att skicka via e-post.

Om du bara har en Office 365-prenumeration läser du [Visa fakturan för Office 365 för företag](view-your-bill-or-invoice.md).

## <a name="understand-the-invoice-header"></a>Förstå fakturahuvudet

Högst upp på första sidan identifierar vem som är ansvarig för betalning, var räkningen skickas till och en sammanfattning av avgifter.

| Benämna | Beskrivning |
| --- | --- |
| Såld till |Faktureringskontot som identifierar namn och adress på den juridiska person som ansvarar för betalningen. Den här informationen kan hanteras på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Faktureringskonton,</a> där du kan hitta kontoavtalet och hantera roller och behörigheter. |
| Fakturera till |Identifierar vem som tar emot fakturan. Den här informationen kan hanteras på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringsprofiler.</a> Faktureringsprofilen visas också på onlinefakturasidan i avsnittet **Fakturasammanfattning.** Mer information om faktureringsprofiler och hur du kan använda dem för att skapa mer flexibla faktureringsalternativ för din organisation finns i [Hantera faktureringsprofiler](manage-billing-profiles.md). |
| Faktureringsprofil |Namnet på faktureringsprofilen som används för att definiera fakturaegenskaper som Faktureratill, INKÖPSPOSTnummer och betalningsvillkor. Den här informationen kan hanteras på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringsprofiler.</a> Mer information om faktureringsprofiler och hur du kan använda dem för att skapa mer flexibla faktureringsalternativ för din organisation finns i [Hantera faktureringsprofiler](manage-billing-profiles.md). |
| Fakturanummer |Ett unikt, Microsoft-genererat fakturanummer som används för spårning. |
| Fakturadatum |Datum då fakturan genereras, vanligtvis fem till tolv dagar efter faktureringsperiodens. Du kan kontrollera fakturadatumet på sidan information om faktureringsprofilen. Avgifter som uppstår mellan slutet av faktureringsperioden och fakturadatumet inkluderas i fakturan för nästa månad, eftersom de är i nästa faktureringsperiod. Start- och slutdatum för faktureringsperioden för varje faktura visas i fakturaPDF:n ovanför **faktureringssammanfattningen**.|
| Betalningsvillkor |Hur du betalar för din Microsoft-faktura. *Netto 30 dagar* innebär att du betalar genom att följa instruktionerna på din faktura, inom 30 dagar från fakturadatumet. |

## <a name="understand-the-billing-summary"></a>Förstå faktureringssammanfattningen

**Faktureringssammanfattningen** visar sammanfattningen av avgifter sedan föregående faktureringsperiod, eventuella krediter som tillämpades, skatt och det totala förfallna beloppet.

| Benämna | Beskrivning |
| --- | --- |
| Debitering|Totalt antal produkter som köpts för den här faktureringsperioden och deras relaterade avgifter och skatter. Inköp sammanställs för att ge en kortfattad bild av din faktura. |
| Krediter |Krediter du fått från returer |
| Azure-krediter tillämpas |Dina Azure-krediter som automatiskt tillämpas på Azure debiterar varje faktureringsperiod. Om du inte har några Azure-krediter är det här fältet dolt. Mer information om Azure-krediter finns i [Spåra Microsoft Customer Agreement Azure-kreditsaldo](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance). |
| Delsumma |Det belopp före skatt som ska betalas |
| Moms |Vilken typ och ett skattebelopp du betalar, beroende på faktureringsprofilens land. Om du inte behöver betala skatt visas ingen skatt på fakturan. |

### <a name="understand-your-charges"></a>Förstå dina avgifter

Avgiftssidorna visar kostnaden uppdelad efter produkt. För Azure-kunder kan avgifterna ordnas efter fakturaavsnitt. Mer information om hur fakturaavsnitt används med Azure-produkter finns i Fakturaavsnitt i Kom igång med ditt [faktureringskonto](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) för Microsoft Customer [Agreement](https://docs.microsoft.com/azure/billing/billing-mca-overview). I varje produktorder delas kostnaden upp efter servicefamilj.

| Benämna |Beskrivning |
| --- | --- |
| Enhetspris | Det effektiva enhetspriset för tjänsten (i prisvaluta) som används för att beräkna avgiften. Detta pris är unikt för en produkt, servicefamilj, mätare och erbjudande. |
| Ant | Kvantitet som köpts eller förbrukats under faktureringsperioden |
| Avgifter/krediter | Nettoavgiftsbelopp efter krediter/återbetalningar tillämpas |
| Azure-kredit | Mängden Azure-krediter som tillämpas på avgifter/krediter |
| Skattesats | Skattesats, beroende på land |
| Skattebelopp | Skattebelopp som tillämpas på köpet baserat på skattesats |
| Summa | Det totala belopp som ska betalas för köpet |

Information om radobjekt varierar beroende på vilken typ av produkt du debiteras för. För Azure-produkter visas till exempel mängden Azure-krediter som tillämpas. Sätesbaserade produkter visar ett enhetspris och kvantitet. Fakturainformationen beskriver de inköpta produkter, rabatt eller krediter som har tillämpats, skattesats och belopp samt radartikelsummorna.

`Total = Charges - Azure Credit + Tax`

Det totala beloppet för varje tjänstfamilj beräknas genom att subtrahera Azure-krediter från krediter/avgifter och lägga till skatt:

`Total = Charges/Credits - Azure Credit + Tax`

Om det finns Azure-avgifter på din faktura som du vill ha mer information om läser du [Förstå debiteringar på din Faktura för Microsoft-kundavtal](https://docs.microsoft.com/azure/billing/billing-mca-understand-your-bill).

## <a name="understand-the-last-invoice-page"></a>Förstå den senaste fakturasidan

### <a name="payment-instructions"></a>Betalningsinstruktioner

Längst ner på fakturan finns instruktioner om hur du betalar din faktura. Du kan betala via tråd, check eller online.

### <a name="publisher-information"></a>Information om utgivare

Om du har tjänster från tredje part i fakturan visas namnet och adressen för varje utgivare längst ned på fakturan.

## <a name="view-your-online-invoice"></a>Visa din onlinefaktura

Fakturor är tillgängliga online. En länk till din onlinefaktura är tillgänglig från din PDF-faktura och från ett e-postmeddelande. Onlinefakturan kan utökas så att du kan visa avgifterna på fakturan och se mer information för varje artikel. Onlinefakturan innehåller:

- **Prisinformation** &mdash; Ytterligare information inklusive information om rabatter och produktpriser.

- **Onlinebetalning** &mdash; Du kan välja att göra en betalning online från fakturan.

- **Azure kostnadshantering** &mdash; För Azure-kunder innehåller onlinefakturor en länk till Azure kostnadshantering.

### <a name="to-view-your-online-invoice"></a>Så här visar du din onlinefaktura

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.

2. Om du vill hämta PDF-versionen av fakturan väljer du **Hämta faktura PDF** på raden för den faktura du vill se.

3. Om du vill visa din onlinefaktura väljer du en faktura i listan. Du kan också ladda ner PDF-filen från fakturainformationssidan.

## <a name="need-help-contact-support"></a>Behöver du hjälp? Kontakta supporten.

Om du har frågor eller behöver hjälp med dina <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Azure-krediter skapar du en supportbegäran med Azure-supporten</a>.

Om du har frågor eller behöver hjälp med fakturan i Administrationscentret för Microsoft 365 [kontaktar du supporten för företagsprodukter](../../admin/contact-support-for-business-products.md).
