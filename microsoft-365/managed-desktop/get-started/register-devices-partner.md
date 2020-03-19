---
title: Steg för partners att registrera enheter
description: Hur partner kan registrera enheter så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: dc446281e8a791b59a9ac97592ff6a53dcde310c
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42805441"
---
# <a name="steps-for-partners-to-register-devices"></a>Steg för partners att registrera enheter


I det här avsnittet beskrivs stegen för partners att följa för att registrera enheter. Processen för att registrera enheter själv dokumenteras själv i [Registrera enheter i Microsoft Managed Desktop själv](register-devices-self.md).



## <a name="prepare-for-registration"></a>Förbered för registrering 
Innan du slutför registreringen för en kund måste du först upprätta en relation med dem på [Partnercenter.](https://partner.microsoft.com/dashboard) Var noga med att välja **Inkludera delegerade administrationsbehörigheter för Azure Active Directory och Office 365**. Läs mer på [Hjälp till PartnerCenter](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).

Om du vill slutföra registreringen för kunden skapar du först en CSV-fil.

>[!NOTE]
>För din bekvämlighet kan du ladda ner en [exempel CSV-fil](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) för den här *partnerversionen*.

Filen måste innehålla **exakt samma kolumnrubriker** som exempelrubriken (tillverkare, modell osv.), men dina egna data för de andra raderna. Om du använder mallen öppnar du den i ett textredigeringsverktyg som Anteckningar och överväg att lämna alla data på rad 1 ensam, och ange bara data i rad 2 och nedan. 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
>Det här formatet är bara för partnerprocessen. Processen för självregistrering dokumenteras själv i [Registrera enheter i Microsoft Managed Desktop själv](register-devices-self.md).

>[!IMPORTANT]
>Dessa värden måste matcha tillverkarens värden från SMBIOS exakt, inklusive versaler och specialtecken. 

- Enhetstillverkare (exempel: SpiralOrbit) 
- Enhetsmodell (exempel: ContosoABC)
- Serienummer för enhet

## <a name="register-devices-by-using-the-azure-portal"></a>Registrera enheter med hjälp av Azure Portal

Registrering med hjälp av Azure Portal är samma som för självbetjäning, förutom att du kommer åt portalen på olika sätt. Följ anvisningarna nedan:

1. Navigera till [Partnercenter](https://partner.microsoft.com/dashboard)
2. Välj **kunder**.
3. Välj den kund som du vill hantera.
4. Välj **Serviceadministration**.
5. Välj **Intune**.
6. Sök efter "mmd" i den övre sökrutan på Azure-portalen.
7. Välj **enheter**.
8. Ange en sökväg till den CSV-fil som du skapade tidigare i **Filuppladdning.**
9. Du kan också lägga till ett **order-ID** eller **inköps-ID** för dina egna spårningsändamål. Det finns inga formatkrav för dessa värden.
10. Välj **Registrera enheter**. Systemet lägger till enheterna i listan över enheter på **bladet Enheter**, markerat som **Registreringsväntande**. Registreringen tar vanligtvis mindre än 10 minuter, och när enheten lyckas visas som **klar för användaren,** vilket innebär att den är klar och väntar på att en slutanvändare ska börja använda.


Du kan övervaka förloppet för enhetsregistrering på sidan **Microsoft Managed Desktop – Enheter.** Möjliga tillstånd som rapporteras där inkluderar:

| Statligt | Beskrivning |
|---------------|-------------|
| Väntande registrering | Registreringen är inte klar än. Kom tillbaka senare. |
| Registreringen misslyckades | Det gick inte att slutföra registreringen. Mer information finns i [Felsöka enhetsregistrering.](register-devices-self.md#troubleshooting-device-registration) |
| Redo för användare | Registreringen lyckades och enheten är nu redo att levereras till slutanvändaren. Microsoft Managed Desktop guidar dem genom första gången set-up, så det finns ingen anledning för dig att göra några ytterligare förberedelser. |
| Aktiva | Enheten har levererats till slutanvändaren och de har registrerat sig hos din klientorganisation. Detta indikerar också att de regelbundet använder enheten. |
| Inaktiva | Enheten har levererats till slutanvändaren och de har registrerat sig hos din klientorganisation. De har dock inte använt enheten nyligen (under de senaste 7 dagarna).  |



## <a name="troubleshooting"></a>Felsökning

| Felmeddelande | Information |
|---------------|-------------|
| Enheten hittades inte | Vi kunde inte registrera den här enheten eftersom vi inte kunde hitta en matchning för den medföljande tillverkaren, modellen eller serienumret. Bekräfta dessa värden med din enhetsleverantör. |
| Maskinvaruhash är ogiltigt | Maskinvaruhash som du angav för den här enheten har inte formaterats korrekt. Dubbelkolla maskinvaruhash och skicka sedan in igen. |
| Enheten har redan registrerats | Den här enheten är redan registrerad i din organisation. Inga ytterligare åtgärder krävs. |
| Enhet som en annan organisation har gjort anspråk på | Den här enheten har redan hävdats av en annan organisation. Kontrollera med din enhetsleverantör. |
| Oväntat fel | Det gick inte att behandla din begäran automatiskt. Kontakta supporten (<support link>) och ange begärande-ID:<requestId> |
