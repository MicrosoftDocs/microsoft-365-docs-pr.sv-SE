---
title: Förstå din faktura
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Lär dig att läsa och förstå din faktura för Microsoft Business-produkter.
keywords: fakturerings konton, organisationsinformation, fakturor
ms.openlocfilehash: 80b7e4f14390e2f695dc753358f9e5bebe055bd0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638417"
---
# <a name="understand-your-bill-or-invoice"></a>Förstå din faktura

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Fakturan ger en översikt över dina avgifter och betalnings anvisningar. Du kan [Visa din faktura online](#view-your-online-invoice) i administrations centret för Microsoft 365. Du kan också ladda ner det i Portable Document Format (. pdf) för att skicka via e-post.

Om du bara har en Microsoft 365-prenumeration kan du läsa [förstå din faktura för microsoft 365 för företag](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Förstå faktura huvudet

Den övre delen av första sidan visar vem som är debiterbar för betalning, där fakturan skickas till och en sammanfattning av kostnaderna.

| Term | Beskrivning |
| --- | --- |
| Såld till |Det fakturerings konto som anger namn och adress för den juridiska organisation som är ansvarig för betalning. Den här informationen kan hanteras på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">fakturerings konton</a> där du hittar konto avtalet och hanterar roller och behörigheter. |
| Faktura till |Identifierar vem som får fakturan. Den här informationen kan hanteras på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">fakturerings profiler</a> . Fakturerings profilen visas också på sidan online-faktura i avsnittet **faktura sammanfattning** . Mer information om fakturerings profiler och hur du kan använda dem för att skapa mer flexibla fakturerings alternativ för organisationen finns i [hantera fakturerings profiler](manage-billing-profiles.md). |
| Fakturerings profil |Namnet på fakturerings profilen som används för att definiera faktura egenskaper som **fakturerings**-, **inköps order**-och betalnings villkor. Den här informationen kan hanteras på sidan <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">fakturerings profiler</a> . Mer information om fakturerings profiler och hur du kan använda dem för att skapa mer flexibla fakturerings alternativ för organisationen finns i [hantera fakturerings profiler](manage-billing-profiles.md). |
| Faktura nummer |Ett unikt, Microsoft-genererat faktura nummer som används för att spåra. |
| Faktura datum |Det datum då fakturan genereras, vanligt vis fem till 12 dagar efter fakturerings cykelns slut. Du kan kontrol lera faktura datumet på sidan information om fakturerings profil. Avgifter som sker mellan slutet av fakturerings perioden och faktura datumet är inkluderade i fakturan för nästa månad, sedan de är under nästa fakturerings period. Fakturerings periodernas start-och slutdatum för varje faktura visas i PDF-filen för **fakturering ovan.**|
| Betalnings villkor |Hur du betalar för din Microsoft-räkning. *30 dagar* innebär att du betalar genom att följa instruktionerna på fakturan, inom 30 dagar efter faktura datumet. |

## <a name="understand-the-billing-summary"></a>Förstå fakturerings sammanfattningen

I **fakturerings sammanfattningen** visas en sammanfattning av avgifterna efter den föregående fakturerings perioden, eventuell kredit som har begärts, skatt och total beloppet.

| Term | Beskrivning |
| --- | --- |
| Debitering|Totalt antal köpta produkter för denna fakturerings period samt tillhörda avgifter och skatter. Köp är sammansatta för att ge en kortfattad översikt över din räkning. |
| Krediter |Tillgodohavanden som du fått från returer |
| Använda Azure-kredit |Ditt Azure-tillgodohavande som automatiskt tillämpas på Azure debiterar varje fakturerings period. Om du inte har något Azure-tillgodohavande är det här fältet dolt. Mer information om Azure-kredit finns i [spåra Microsoft-kundavtal med Azure-saldo](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance). |
| Räkna |Förfallet före moms |
| Moms |Typen och beloppet för den skatt du betalar, beroende på vilket land du har i din betalnings profil. Om du inte behöver betala skatt visas ingen moms på fakturan. |

### <a name="understand-your-charges"></a>Förstå dina avgifter

Avgifts sidorna visar kostnaden uppdelad efter produkt. För Azure-kunder kan kostnaderna vara organiserade efter faktura avsnitt. Mer information om hur faktura avsnitt används med Azure-produkter finns i avsnittet [faktura avsnitt](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) i [komma igång med ditt fakturerings konto för Microsoft-kundavtal](https://docs.microsoft.com/azure/billing/billing-mca-overview). Inom varje produkt beställning är kostnaden uppdelad per tjänste familj.

| Term |Beskrivning |
| --- | --- |
| Enhets pris | Det faktiska enhets priset för tjänsten (i pris valutan) som används för att beräkna avgiften. Priset är unikt för en produkt, service familj, mätare och ett utbud. |
| Fakturera | Köpt eller förbrukad kvantitet under fakturerings perioden |
| Avgifter/kredit | Netto beloppet för avgifter efter betalning |
| Azure-kredit | Beloppet för Azure-kredit som tillämpas på avgifterna/krediterna |
| Momssats | Momssats, beroende på landet |
| Moms belopp | Moms belopp kopplat till inköp baserat på momssats |
| Summa | Det totala beloppet som förfaller till köpet |

Information om rad objekt varierar beroende på vilken typ av produkt du debiterar. För Azure-produkter visas till exempel hur många Azure-krediter som används. Klientbaserade produkter visar enhets pris och antal. Faktura detaljerna visar vilka produkter som köpts in, rabatt eller kredit som har betalats, momssats och belopp samt rad artikel summorna.

> Totalt = avgifter-Azure-kredit + skatt

Total beloppet som ska betalas för varje service familj beräknas genom att subtrahera Azure-kredit från tillgodohavanden/avgifter och lägga till skatt:

> Totalt = avgifter/kredit-Azure-kredit + skatt

Om det finns Azure-avgifter på fakturan som du vill ha mer information om kan du läsa [Granska din Microsoft-faktura för kund avtal](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill).

## <a name="understand-the-last-invoice-page"></a>Förstå den senaste faktura Sidan

### <a name="payment-instructions"></a>Betalnings anvisningar

Längst ned på fakturan finns instruktioner för hur du betalar din faktura. Du kan betala per tråd, check eller online.

### <a name="publisher-information"></a>Information om Publisher

Om du har tjänster från tredje part i din faktura visas namn och adress för varje förläggare längst ned på fakturan.

## <a name="view-your-online-invoice"></a>Visa din online-faktura

Fakturor är tillgängliga online. En länk till din online-faktura är tillgänglig från din PDF-faktura och från ett e-postmeddelande. Online-fakturan är utbyggbar så att du kan se kostnaderna på fakturan och se mer information för varje objekt. Online-fakturan innehåller:

- **Pris uppgifter** &mdash; Ytterligare information om rabatter och produkt prissättning.

- **Online-betalning** &mdash; Du kan välja att göra en betalning online från fakturan.

- **Azure Cost Management** &mdash; För Azure-kunder inkluderar online-fakturor en länk till en Azure Cost Management.

### <a name="to-view-your-online-invoice"></a>Så här visar du din online-faktura

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fakturor och betalningar</a>.

2. Om du vill ladda ned PDF-versionen av din faktura väljer du **Ladda ned faktura-PDF** i raden för den faktura som du vill visa.

3. Om du vill visa din online-faktura väljer du en faktura i listan. Du kan också ladda ned PDF-filen från sidan faktura information.

## <a name="invoice-faq"></a>Vanliga frågor om faktura

### <a name="when-is-my-invoice-available"></a>När finns min faktura tillgänglig?

Vissa fakturor skapas inom 24 timmar efter köpet. Andra fakturor skapas i slutet av fakturerings perioden och inkluderar alla artiklar under den perioden.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Hur betalar jag beloppet på fakturan?

Betalnings anvisningarna beror på din betalnings metod och tillhandahålls längst ned i PDF-filen. Om betalnings metoden är ett kredit kort debiteras den automatiskt inom 10 dagar efter faktura datumet. Om betalnings metoden är av kontroll eller överföring kan du läsa informationen under **betalnings anvisningarna** i PDF-filen.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Vad är skillnaden mellan "säljs till" och "fakturerings adresser"?

- **Såldes till:** Juridisk person som ansvarar för betalning och som identifieras på fakturan. Den adress som tillhandahålls här används för att bestämma din momssats såvida du inte väljer att ange en alternativ leverans adress under köpet. Mer information finns i [skatte information](tax-information.md).
- **Fakturera till:** Adressen där den fysiska fakturan skickas, om tillämpligt. Det kan finnas flera **fakturor till** adresser per juridisk person, men bara en **fakturerings** adress per fakturerings profil.

### <a name="what-are-billed-amount-and-amount-due"></a>Vad är "fakturerat belopp" och "förfallet belopp?"

- **Fakturerat belopp:** Det totala beloppet för det inköp du gjort.
- **Förfallet belopp:** Det återstående saldot för det du är skyldig.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Vad är skillnaden mellan "" service period "och" fakturerings period ".

- **Service period:** Den tids period som du debiteras för att använda tjänsten.
- **Fakturerings period:** Tids perioden sedan senaste faktura datum.

### <a name="how-do-i-view-and-print-my-bill"></a>Hur visar jag och skriver ut fakturan?

1. På sidan **fakturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">fakturor &-betalningar</a> väljer du ett datum intervall för faktura.
2. Om du vill skriva ut eller spara en PDF-kopia av fakturan väljer du **Ladda ned PDF**och sedan skriva ut PDF-filen.

Mer information finns i [Visa din faktura](view-your-bill-or-invoice.md).

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Varför ser jag inte Azure förskotts betalning som betalnings metod?

Azure-förskotts betalning är endast tillgänglig som betalnings metod för kvalificerade Azure-produkter och-tjänster.

## <a name="need-help-contact-support"></a>Behöver du hjälp? Kontakta supporten.

Om du har frågor eller behöver hjälp med din Azure-kredit, kan du <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">skapa en supportbegäran med Azure-support</a>.

Om du har frågor eller behöver hjälp med din faktura i Microsoft 365 Admin Center kan du [kontakta supporten för företags produkter](../../admin/contact-support-for-business-products.md).