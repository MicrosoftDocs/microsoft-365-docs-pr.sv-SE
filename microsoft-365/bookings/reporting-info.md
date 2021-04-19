---
title: Rapportera information för Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: Läs om hur du kan se en vy på 4 månader av din Bookings-aktivitet
ms.openlocfilehash: ad0a21454cfe28cec521e545e587105e8f8a7454
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887247"
---
# <a name="reporting-info-for-bookings"></a>Rapportera information för Bookings

Nu kan du se en fyra månadsvy av bookingskalendern i en TSV-fil. I TSV-filen visas fyra månader med data, men du kan välja olika fyra månader under ett år.

Den här informationen på avtalad tidsnivå kan användas för att visualisera kundaktiviteten runt din Bookings-kalender. TSV-filer är tabbavgränsade värdefiler. Du kan visa eller redigera en sådan fil med valfri textredigerare eller ett kalkylprogram, till exempel Excel.

## <a name="see-four-months-of-booking-activity"></a>Se fyra månaders bokningsaktivitet

1. På instrumentpanelen för kalendern i Bookings väljer **du Exportera mer data som TSV.**

:::image type="content" source="../media/bookings-activities.png" alt-text="Skärmbild: 4 månader med Bookings-aktivitet":::

1. Spara filen med ett nytt namn och ange formatet .xls eller xlsx.

1. Öppna filen för att visa den fyra månadsvy i kalendern i Bookings.

1. Välj rapportdatum och välj **Exportera**.

:::image type="content" source="../media/bookings-reporting-dates.png" alt-text="Skärmbild: Välj ett tidsintervall och exportera data till TSV-fil.":::

1. Den nedladdade rapporten innehåller en ny uppsättning fält utöver de befintliga fälten.

Rapporten innehåller följande fält.

 - **Datum & tid**
- **Kundnamn**
- **Kund-e-post**
- **Kundtelefon**
- **Kundadress**
- **Personal**
- **Tjänst**
- **Plats**
- **Varaktighet (minuter)**
- **Händelsetyp**

Den förbättrade rapporten innehåller nu följande fält.

- **Pristyp**   Standardpristyp som angetts för en tjänst när tjänsten skapas.
- **Pris**   Pris som motsvarar den valda pristypen.
- **Valuta**   Valutatyp inställd för ett företag.
- **Cc-deltagare**   De mottagare som kommer att få e-postaviseringar för en bokning. Detta kan anges från Teams-appen när du skapar en bokning.
- **Registrerade deltagare Count**   Hur många kunder har bokat en gruppbokningstjänst.
- **Sms-aviseringar aktiverat**   Om kunder kan ta emot SMS-sms-relaterade aviseringar.
- **Anpassade fält**   Alla frågor och svar som rör en enskild bokning kombineras i det här fältet.
- **Boknings-ID**   Det här är användbart för att identifiera samma bokningar för en grupptjänst.
