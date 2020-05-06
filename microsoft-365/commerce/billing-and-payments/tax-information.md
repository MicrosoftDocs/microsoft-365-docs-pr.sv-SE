---
title: Skatteinformation
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: 'Ta reda på hur mycket skatt du debiteras för din Microsoft 365 för företag-prenumeration i olika regioner. '
ms.custom: okr_SMB
ms.openlocfilehash: 0aeabd49477bdef856a7ddb9f3b7c39211be2479
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045830"
---
# <a name="tax-information"></a>Momsinformation

Moms för Administrationscenter för Microsoft 365 som du gör via Microsoft bestäms av företagets adress eller om den är annorlunda, via din leveransadress. Om du befinner dig i USA måste du ange ett federalt arbetsgivarregistreringsnummer (FEIN).

Företag i dessa länder kan ange sitt momsregistreringsnummer:

:::row:::
    :::column:::
- Österrike
- Belgien
- Bulgarien
- Kroatien
- Cypern
- Tjeckien
- Danmark
- Estland
- Finland
- Frankrike
- Tyskland
- Grekland
- Ungern
- Irland
- Italien
- Lettland
    :::column-end:::
    :::column:::
- Liechtenstein
- Litauen
- Luxemburg
- Malta
- Monaco
- Nederländerna
- Norge
- Polen
- Portugal
- Rumänien
- Slovakien
- Sydafrika
- Spanien
- Sverige
- Schweiz
- Storbritannien
    :::column-end:::
:::row-end:::

Dessa länder kan ange sitt momsregistreringsnummer eller lokala motsvarighet på sina faktureringskontouppgifter.

|Marknaden| Skatteidentifierare |
|------|----------------|
| Australien | ABN (valfritt) |
| Brasilien | CNPJ (obligatoriskt) |
| Indien | GSTIN (valfritt), PAN-ID (obligatoriskt) |
| Isle of Man | Moms-ID (valfritt) |
| Nya Zeeland | GST-registreringsnummer (valfritt) |
| Monaco | Moms-ID (valfritt) |
| Taiwan | Moms-ID (valfritt) |

> [!Note]
> Om du behöver kontakta supporten ska du ha ditt FEIN, momsregistreringsnummer eller lokala motsvarighet redo att ge till supportagenten.

## <a name="what-tax-will-i-be-charged"></a>Vilka skatter debiteras jag?

Ta reda på vilken moms du måste betala i följande regioner. Du kan också [ansöka om undantag från beskattning](tax-information.md#apply-for-tax-exempt-status) genom att skicka nödvändig dokumentation till supporten.
  
### <a name="europe-the-middle-east-and-africa-emea"></a>Europa, Mellanöstern och Afrika (EMEA)

När du köper Microsoft 365-tjänster i EU omfattas detta köp av moms.
  
- Om du befinner dig i en av EU:s medlemsstater och inte anger ett giltigt lokalt momsregistreringsnummer tillämpar Microsoft Ireland Operations Ltd. den aktuella lokala momssatsen, baserat på det faktureringsland som angetts i ditt konto.

- Om du befinner dig i Schweiz eller Liechtenstein används den aktuella schweiziska momssatsen, oavsett om du anger momsregistreringsnummer eller inte.

- Om du befinner dig i ett EMEA-land utanför EU och Schweiz/Liechtenstein debiteras moms i allmänhet inte av Microsoft Ireland Operations Ltd.

- Innan vi kan verifiera ditt momsregistreringsnummer måste det finnas tillgänglig i VAT Information Exchange System (VIES). Kontakta ditt lokala skattekontor om ditt momsregistreringsnummer inte kan verifieras.

Du kan vara berättigad till momsbefrielse:
  
- **Om du är i en EU-medlemsstat utanför Irland:** Du kan ange ditt giltiga lokala moms-ID. Detta ger Microsoft Ireland Operations Ltd. rätt till nollskattesats för transaktionen. Du kan dock ha en lokal momsredovisningsskyldighet, så kontrollera med dina skatterådgivare om du har några problem. Instruktioner finns i "Lägg till ditt moms-ID (endast EU-länder)" nedan.

- **Om du befinner dig i Irland och har ett relevant giltigt certifikat för momsbefrielse:** Microsoft Ireland Operations Ltd. kan ha rätt att undanta transaktionen från moms. Om du inte har det tillämpar Microsoft Ireland Operations Ltd. den aktuella irländska momssatsen, oavsett om du anger ett momsregistreringsnummer eller inte.

::: moniker range="o365-worldwide"

#### <a name="add-your-vat-id-eu-countries-only"></a>Så här anger du ditt momsregistreringsnummer (endast EU-länder)

1. Gå till sidan \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter</a> i administrationscentret. **Billing**

2. Hitta prenumerationskortet för den prenumeration som du vill uppdatera.

3. I avsnittet **Inställningar & Åtgärder** väljer du Redigera **tjänstanvändningsadress**.

4. På sidan **Redigera tjänstens användningsadress** anger du ditt moms-ID i rutan **Momsnummer** och väljer sedan **Spara**.

::: moniker-end

::: moniker range="o365-germany"

#### <a name="add-your-vat-id-eu-countries-only"></a>Så här anger du ditt momsregistreringsnummer (endast EU-länder)
  
1. Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.

2. Välj prenumerationsnamnet och välj sedan **Fler åtgärder** \> **Redigera momsregistreringsnummer**.
  
3. På sidan **Redigera tjänstens användningsadress** anger du ditt moms-ID i rutan **Momsnummer** och väljer sedan **Skicka**.

::: moniker-end

### <a name="asia-pacific-countries-apac"></a>Länder i Asien/Stillahavsområdet (APAC)

Om du faktureras av Microsofts regionala försäljningskontor visas "Microsoft Regional Sales" på fakturan och du debiteras vanligtvis inte konsumtionsskatt eller mervärdesskatt (moms) såvida det inte är en inhemsk försäljning.
  
Om du faktureras från en annan plats tillämpas den aktuella lokala skattesatsen. Du ser följande [på fakturan](view-your-bill-or-invoice.md):
  
- Singapore för Singapore

- Korea för Korea

- Japan för Japan

- Taiwan för Taiwan

### <a name="north-central-and-south-america"></a>Nord-, Central- och Sydamerika

I USA och Kanada gäller olika momssatser beroende på kundens ort. Om du befinner dig i Puerto Rico gäller de lokala momsavgifterna.
  
Om din fakturering utförs av Microsoft Corporation ([se din faktura](view-your-bill-or-invoice.md)), och du har registrerat dig för Microsoft 365 utanför USA, Kanada och Puerto Rico, då skatt i allmänhet inte debiteras.

## <a name="how-taxes-are-calculated"></a>Hur skatter beräknas

Moms beräknas mot a-priset och aggregeras sedan.

Till exempel:

>*(skattesats för enhetspris X) X kvantitet = total moms*

-eller...

>($1.29 X 0.095) X 100 = $12.25

## <a name="apply-for-tax-exempt-status"></a>Ansök om status som skattebefriad

Om du är berättigad till status som skattebefriad på din marknad [startar du en tjänstbegäran för](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) att fastställa status som skattebefriad för din organisation.

Ha följande dokumentation klar:

|Land eller språk | Dokumentation |
|------------------|----------------|
| USA | Intyg om momsbefrielse |
| Kanada | Intyg om befrielse (eller motsvarande fullmakt) |
| Irland | 13B/56A Intyg om skattebefrielse|
| Internationella organisationer som har skattebefrielse | Certifiering / brevbekräftelse från lokala skattemyndigheter |
| Puerto Rico | Certificado de Compras Exentas |
  
## <a name="related-articles"></a>Relaterade artiklar
  
[Visa din faktura](view-your-bill-or-invoice.md)
  
[Förstå din faktura](understand-your-invoice.md)