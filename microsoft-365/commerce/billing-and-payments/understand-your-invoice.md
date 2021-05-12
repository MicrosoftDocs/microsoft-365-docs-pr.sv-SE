---
title: Förstå din faktura
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Lär dig att läsa och förstå fakturan för Microsoft företagsprodukter.
keywords: faktureringskonton, organisationsinformation, fakturor
ms.date: 05/04/2021
ms.openlocfilehash: dc83db458d1d91942352795c9b67578e9f1a2fc2
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331949"
---
# <a name="understand-your-bill-or-invoice"></a>Förstå din faktura

Fakturan innehåller en sammanfattning av dina avgifter och instruktioner för betalning. Du kan [Visa din faktura online](#view-your-online-invoice) i Administrationscenter för Microsoft 365. Du kan också ladda ned den i Portable Document Format (.pdf) för att skicka via e-post.

Så här visar och skriver du ut fakturan:

1. På sidan **Fakturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">fakturor och betalningar</a> väljer du ett datumintervall för fakturan.
2. Om du vill skriva ut eller spara en PDF-kopia av fakturan väljer du **Ladda ned PDF-faktura** och skriver sedan ut PDF-filen.

Om du vill veta mer kan du läsa [Visa din faktura](view-your-bill-or-invoice.md).

Om du bara har en Microsoft 365-prenumeration läser du [Förstår fakturan för Microsoft 365 för företag](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Förstå fakturahuvudet

Längst upp på den första sidan ser du vilka som är ansvariga för betalning, dit fakturan skickas och en sammanfattning av avgifter.

| Term | Beskrivning |
| --- | --- |
| Såld till |Det faktureringskonto som anger namn och adress för den juridiska organisation som ansvarar för betalning. Den här informationen kan hanteras på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Faktureringskonton</a>, där du hittar kontoavtalet och hanterar roller och behörigheter. |
| Faktureras till |Identifierar vem som får fakturan. Den här informationen kan hanteras på sidan för <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringsprofiler</a>. Din faktureringsprofil visas också på sidan onlinefaktura i avsnittet **Fakturasammanfattning**. Om du vill ha mer information om faktureringsprofiler och hur du kan använda dem för att skapa mer flexibla faktureringsalternativ för din organisation kan du läsa [Hantera faktureringsprofiler](manage-billing-profiles.md). |
| Faktureringsprofil |Namnet på faktureringsprofilen som används för att definiera fakturaegenskaper, t. ex. **faktura till**, **Inköpsordernummer** och betalningsvillkor. Den här informationen kan hanteras på sidan för <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Faktureringsprofiler</a>. Mer information om faktureringsprofiler och hur du kan använda dem för att skapa mer flexibla faktureringsalternativ för din organisation finns i [Hantera faktureringsprofiler](manage-billing-profiles.md). |
| Fakturanummer |Ett unikt, Microsoft-skapat fakturanummer som används i spårningssyfte. |
| Fakturadatum |Datum då fakturan genereras, vanligtvis fem till 12 dagar efter slutet av faktureringsperioden. Du kan kontrollera fakturadatumet på sidan faktureringsprofil information. Kostnader som uppstår mellan slutet av faktureringsperioden och fakturadatumet ingår i fakturan för nästa månad, eftersom de är i nästa faktureringsperiod. Start- och slutdatumen för faktureringsperioden för varje faktura listas i PDF-fakturan ovanför **Fakturasammanfattning**.|
| Betalningsvillkor |Hur du betalar för din Microsoft-faktura. *30 dagar netto* innebär att du betalar genom att följa anvisningarna på din faktura, inom 30 dagar efter fakturadatumet. |

## <a name="understand-the-billing-summary"></a>Förstå fakturasammanfattningen

**Fakturasammanfattningen** visar en sammanfattning av debiteringar sedan föregående faktureringsperiod, alla krediter som har tillämpats, moms och det totala beloppet som ska betalas.

| Term | Beskrivning |
| --- | --- |
| Debitering|Det totala antalet produkter som köpts för denna faktureringsperiod och deras kostnader och moms. Köpet aggregeras för att ge en kortfattad översikt över fakturan. |
| Krediter |Krediter som du fått från returer |
| Tillämpade Azure-kredit |Dina Azure-krediter tillämpas automatiskt på Azure avgifter varje faktureringsperiod. Om du inte har några Azure-krediter är det här fältet dolt. Mer information om Azure-krediter finns i [Spåra Azure kreditbalans för Microsoft-kundavtal](/azure/billing/billing-mca-check-azure-credits-balance). |
| Delsumma |Totala beloppet före moms |
| Moms |Typen av och beloppet för den moms som du betalar, beroende på landet i din faktureringsprofil. Om du inte behöver betala moms visas ingen moms på fakturan. |

### <a name="understand-your-charges"></a>Förstå dina avgifter

Avgiftssidorna visar kostnaden uppdelad efter produkt. För Azure-kunder kan avgifterna vara ordnade efter fakturaavsnitten. Mer information om hur fakturaavsnitt används med Azure-produkter finns i avsnittet [Fakturaavsnitt](/azure/billing/billing-mca-overview#invoice-sections) i [Komma igång med ditt faktureringskonto för Microsoft-kundavtal](/azure/billing/billing-mca-overview). Inom varje produktordning delas kostnaden upp efter tjänstefamilj.

| Term |Beskrivning |
| --- | --- |
| Enhetspris | Det faktiska enhetspriset för tjänsten (i prisvalutan) som används för att beräkna avgiften. Priset är unikt för en produkt, tjänstefamilj, mätare och erbjudande. |
| Antal | Kvantitet som köpts eller förbrukats under faktureringsperioden |
| Avgifter/kredit | Nettobeloppet för avgifter efter avdrag och återbetalning |
| Azure-kredit | Hur mycket Azure-krediter som används för avgifterna/krediterna |
| Momssats | Momssats, beroende på land |
| Momsbelopp | Momsbelopp kopplat till inköp baserat på momssats |
| Summa | Det totala beloppet som ska betalas för köpet |

Information om radobjekt varierar beroende på vilken typ av produkt du debiteras för. Till exempel visas hur mycket Azure-krediter som tillämpas för Azure-produkter. Platsbaserade produkter visar enhetspris och kvantitet. Fakturainformationen visar köpta produkter, rabatter och kreditbelopp som har tillämpats, momssats och belopp samt radartikelsummor.

> Summa = avgifter – Azure kredit + moms

Det totala beloppet som ska betalas för varje tjänstefamilj beräknas genom att dra ifrån Azure-krediter från kredit/avgifter och lägga till moms:

> Summa = avgifter/kredit – Azure kredit + moms

Om du vill ha mer information om din Azure-avgifter på din faktura går du till [Granska faktura för Microsoft-kundavtal](/azure/cost-management-billing/understand/review-customer-agreement-bill).

## <a name="understand-the-last-invoice-page"></a>Förstå den sista fakturasidan

### <a name="payment-instructions"></a>Betalningsinstruktioner

Längst ned på fakturan finns anvisningar om hur du betalar din faktura. Du kan betala via överföring, check eller online.

### <a name="publisher-information"></a>Utgivarinformation

Om du har tjänster från tredje part i din faktura visas namnet och adressen till varje utgivare längst ned i fakturan.

## <a name="view-your-online-invoice"></a>Visa din faktura online

Fakturor är tillgängliga online. En länk till din online-faktura är tillgänglig via din PDF-faktura och från ett e-postmeddelande. Online-fakturan är utbyggbar så att du kan visa avgifterna på fakturan och visa mer information om varje objekt. Online-fakturan innehåller:

- **Prisinformation**&mdash;Ytterligare information inklusive information om rabatter och produktpriser.
- **Online-betalning**&mdash;Du kan välja att göra en betalning online i fakturan.
- **Azure Cost Management**&mdash;För Azure-kunder innehåller online-fakturan en länk till Azure Cost Management.

### <a name="to-view-your-online-invoice"></a>Visa din online-faktura

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.
2. Om du vill ladda ned PDF-versionen av fakturan väljer du **laddar ned PDF-faktura** på raden för den faktura som du vill visa.
3. Om du vill visa din online-faktura väljer du en faktura i listan. Du kan också ladda ned PDF-filen från sidan fakturadetaljer.

## <a name="invoice-faq"></a>Vanliga frågor och svar

### <a name="when-is-my-invoice-available"></a>När finns min faktura tillgänglig?

Vissa fakturor skapas inom 24 timmar efter köpet. Andra fakturor skapas i slutet av faktureringsperioden och inkluderar alla poster från den perioden.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Hur betalar jag det belopp som ska betalas på min faktura?

Betalningsanvisningarna beror på din betalningsmetod och finns längst ned i fakturan PDF. Om din betalningsmetod är ett kreditkort debiteras det automatiskt inom 10 dagar efter fakturadatumet. Om din betalningsmetod är av check eller överföring läser du informationen under **Betalningsinstruktioner** i PDF-filen.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Vad är skillnaden mellan "såld till" och "faktura till"-adresser?

- **Såldes till:** den juridiska organisation som ansvarar för betalning och som identifieras på fakturan. Adressen som anges här används för att fastställa din momssats, såvida du inte väljer att ange en alternativ leveransadress under köpet. Mer information finns i [Momsinformation](tax-information.md).
- **Fakturera till:** adressen där den fysiska fakturan ska skickas, om det är tillämpligt. Det kan finnas flera **Faktureras till**-adresser per juridisk enhet, men bara en **faktura till**-adress per faktureringsprofil.

### <a name="what-are-billed-amount-and-amount-due"></a>Vad är “fakturerat belopp” och “belopp att betala”?

- **Fakturerat belopp:** det totala beloppet för det inköp som du har gjort.
- **Belopp att betala:** återstående saldo för vad du är skyldig.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Vad är skillnaden mellan "tjänsteperiod" och "faktureringsperiod"?

- **Tjänstperiod:** Tidsperioden då du debiteras för att använda tjänsten.
- **Faktureringsperiod:** Tidsperioden sedan datumet för den senaste fakturan.

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Varför ser jag inte Azure-förbetalning som betalningsmetod?

Azure-förbetalning är tillgänglig som betalningsmetod endast för kvalificerade Azure-produkter och -tjänster.

## <a name="need-help-contact-support"></a>Behöver du hjälp? Kontakta support

Om du har frågor eller behöver hjälp med dina Azure-krediter <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">skapar du en supportförfrågan med Azure support</a>.

Om du har frågor eller behöver hjälp med fakturan i Administrationscenter för Microsoft 365 [kontaktar du supporten för företagsprodukter](../../business-video/get-help-support.md).
