---
title: Söka efter och släppa meddelanden i karantän som administratör
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: I det här avsnittet beskrivs hur EOP-administratörer (Exchange Online and Exchange Online Protection) kan hitta, släppa och rapportera meddelanden i karantän i Administrationscentret för Exchange (EAC).
ms.openlocfilehash: 7c46ff11b8d08c46c3000232c836af8148c58511
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811847"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>Söka efter och släppa meddelanden i karantän som administratör

I det här avsnittet beskrivs hur EOP-administratörer (Exchange Online and Exchange Online Protection) kan hitta, släppa och rapportera meddelanden i karantän i Administrationscentret för Exchange (EAC). Office 365 dirigerar meddelanden i karantän antingen för att de har identifierats som skräppost eller så matchade de en regel för e-postflöde (kallas även en transportregel).

Du kan använda Security & Compliance Center i stället för EAC för att utföra någon av dessa uppgifter också. Karantänportalen i Administrationscentret för Exchange (EAC) är inställd på att decommisioned. Mer information finns [i E-postmeddelanden i Karantän i Office 365](quarantine-email-messages.md).

Meddelanden i karantän visas på **karantänssidan** i EAC. Som standard sorteras meddelanden från nyaste till äldsta i fältet **MOTTAGET.** **AVSÄNDARE,** **ÄMNE**och **EXPIRES-värden** visas också för varje meddelande. Du kan sortera på något av dessa fält genom att klicka på deras rubriker. Om du klickar på ett kolumnrubrik en andra gång återförsorteringsordningen. **I karantänsidan** visas högst 500 meddelanden.

Du kan visa en lista över alla meddelanden i karantän eller söka efter specifika meddelanden genom att ange filtervillkor (filtrering kan också bidra till att minska resultatuppsättningen om du har fler än 500 meddelanden). När du har sökt efter och hittat ett specifikt meddelande i karantän kan du visa information om meddelandet. Du kan också:

- Släpp meddelandet till en eller flera mottagare och rapportera det som ett falskt positivt (inte skräpmeddelande) till Microsoft Spam Analysis Team, som utvärderar och analyserar meddelandet. Beroende på resultaten av analysen kan reglerna för filterfilter för hela tjänsten justeras så att meddelandet kan gå igenom.

- Släpp meddelandet och tillåt alla framtida meddelanden från avsändaren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Om du vill se vilka behörigheter du behöver läser du posten "Karantän" i [avsnittet Funktionsbehörigheter i Exchange Online.](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

- Du kan släppa eller rapportera flera **quarantine** meddelanden samtidigt på karantänssidan. Du kan också skapa ett fjärrskript i Windows PowerShell för att utföra den här uppgiften. Använd [cmdleten Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) för att söka efter meddelanden och cmdleten [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) för att frigöra dem.

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i [exchange onlineskydd](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.

## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>Använd avancerad sökning för att filtrera och hitta meddelanden i karantän

I Administrationscentret för Exchange (EAC) kan du filtrera objekt i karantän baserat på flera olika villkor med avancerad sökning. Du kan använda dessa villkor separat eller i kombination med varandra. Sökningen innehåller en lista med meddelanden som uppfyller alla filtervillkor.

1. Navigera till \> **Skyddskarantän**i EAC och klicka sedan på **Avancerad sökning**. **Protection**

2. I fönstret **Avancerat sã¶rsÃ¶rsÃ¶rsã¶r** sÃ¶rsÃ¶rsÃ¶rsÃ¶rsÃ¶rsã¶rs Markera den associerade kryssrutan om du vill aktivera varje villkor. Jokertecken stöds inte.

   1. **Meddelande-ID**: Du kan använda den här parametern för att utföra en riktad sökning efter ett visst meddelande. Om ett visst meddelande till exempel skickas av eller är avsett för en användare i organisationen, men aldrig når sitt mål, kan du söka efter meddelandet med hjälp av meddelandespårningsfunktionen. Mer information finns i [Kör ett meddelande spårning och visa resultat](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/run-a-message-trace-and-view-results). Om du upptäcker att meddelandet skickades till karantänen, kanske för att det matchade en regel eller identifierades som skräppost, kan du enkelt hitta det här meddelandet i karantänen genom att ange dess meddelande-ID. Var noga med att inkludera hela meddelande-ID-strängen. Detta kan omfatta vinkelfästen (\<\>).

   2. **E-postadress**för avsändaren: Ange e-postadressen till den person som skickade meddelandet.

   3. **Mottagarens e-postadress**: Ange e-postadressen till den avsedda mottagaren av meddelandet.

   4. **Ämne**: Ange meddelandets ämnesrad.

   5. **Mottaget**: Du kan välja att meddelandet togs emot i karantän inom de senaste 24 timmarna ( **Idag**), inom de senaste 48 timmarna ( **Senaste 2 dagarna**), inom den senaste veckan ( Senaste 7 **dagarna),** eller så kan du välja ett anpassat tidsintervall under vilket meddelandet togs emot av karantänen.

   6. **Upphör att gälla:** Du kan välja att meddelandet kommer att tas bort från karantän inom de närmaste 24 timmarna **(Idag**), inom de närmaste 48 timmarna **(Nästa 2 dagar**), inom nästa vecka ( **Nästa 7 dagar),** eller så kan du välja ett anpassat tidsintervall under vilket meddelandet kommer att tas bort från karantän.

      > [!IMPORTANT]
      > Som standard hålls meddelanden i skräppostkarantän i karantän i 30 dagar, medan meddelanden i karantän som matchade en regel för e-postflöde hålls i karantän i upp till 30 dagar baserat på den kvarhållningsperiod som angetts i standardprincipen för innehållsfilter. Efter denna tidsperiod tar Office 365 bort meddelandena och de kan inte hämtas. Kvarhållningsperioden för meddelanden i karantän som matchade en regel för e-postflöde kan inte konfigureras. Lagringsperioden för meddelanden i skräppost karantän kan dock sänkas via inställningen **Bespara skräppost i (dagar)** i innehållsfilterprinciperna. Mer information finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).

   7. **Typ** Du kan ange om meddelanden som har identifierats som **skräppost**ska sökaefters i karantän eller om du vill söka efter meddelanden som matchade en regel för e-postflöde (**Transport-regeln**).

3. Klicka på **OK** för att börja köra den avancerade sökningen.

   > [!NOTE]
   > Om du vill ta bort sökvillkoren och visa alla meddelanden i karantänen avmarkerar du alla kryssrutor i fönstret **Avancerat och** klickar sedan på **OK**.

När du har sökt efter meddelanden visas de resultat som matchar de angivna villkoren i användargränssnittet. Högst 500 meddelanden kan visas i EAC.

## <a name="view-details-about-a-specific-quarantined-message"></a>Visa information om ett visst meddelande i karantän

När du har hittat ett visst meddelande i karantän på **karantänssidan** kan du visa information om det.

1. På **karantänssidan** väljer du ett visst meddelande och en sammanfattning av egenskaperna för meddelandet visas i informationsfönstret till höger på skärmen.

   Statusvärdena **meddelande** är följande:

   - **Typ**: Anger om meddelandet har identifierats som **skräppost** eller matchat en regel för e-postflöde (**Transportregel**).

   - **Upphör att gälla:** Det datum då meddelandet tas bort från karantänen.

   Värdena **för meddelandeinformation** är följande:

   - **Avsändare**: E-postadressen till den person som skickade meddelandet.

   - **Ämne**: Meddelandets ämnesrad.

   - **Mottaget**: Det datum då meddelandet togs emot av karantänen.

   - **Storlek**: Storleken på meddelandet, i kilobyte (KB) eller, om meddelandestorleken är större än 999 KBs, i megabyte (MB).

   - **Visa meddelanderubrik:** Klicka på den här länken om du vill öppna dialogrutan **meddelandehuvud,** där du kan visa texten i meddelandehuvudet. Du kan också kopiera texten i meddelandehuvudet till Urklipp och klistra in den i [analysrutan för meddelandehuvudet](https://testconnectivity.microsoft.com/?tabid=mha). En gång i verktyget Analys av meddelandehuvudet klickar du på **Analysera rubriker** för att hämta information om huvudet.

    > [!TIP]
    > Information om specifika rubrikfält för skräppostmeddelanden som infogats av tjänsten finns i [Anti-spam-meddelanderubriker](anti-spam-message-headers.md).

   - **Förhandsgranska e-postmeddelande** Klicka på den här länken om du vill granska texten i meddelandet.

2. Om du dubbelklickar på ett meddelande i karantän öppnas meddelandefönstret **i karantän** och visar följande information:

   - **Släppt till**: En lista över alla e-postadresser som meddelandet har släppts till, om någon.

   - **Ännu inte släppt till**: En lista över alla e-postadresser som meddelandet inte har släppts, om någon. Du kan klicka på **länken Släpp för att** släppa meddelandet. Mer information om hur du släpper ett meddelande finns i nästa avsnitt.

   - **Meddelande-ID:** Internetmeddelande-ID (även kallat klient-ID) som finns i meddelandets rubrik.

   Klicka på **Stäng** om du vill gå tillbaka till huvudkarantänsfönstret.

## <a name="release-messages-from-quarantine"></a>Frigöra meddelanden från karantän

Om du vill släppa meddelanden till mottagare är dina alternativ:

- [Släpp ett meddelande i karantän och tillåta framtida meddelanden från avsändaren](#release-a-quarantined-message-and-allow-future-messages-from-the-sender)

- [Släpp ett meddelande i karantän till specifika mottagare utan att rapportera det som ett falskt positivt](#release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive)

- [Släpp ett eller flera meddelanden i karantän till alla mottagare](#release-one-or-more-quarantined-messages-to-all-recipients)

- [Släpp ett eller flera meddelanden i karantän till alla mottagare och rapportera falska positiva](#release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives)

### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>Släpp ett meddelande i karantän och tillåta framtida meddelanden från avsändaren

1. I EAC navigerar du till \> **Skyddskarantän**. **Protection**

2. Klicka på ett meddelande för att markera det och klicka sedan på **ikonen Släpp meddelande** som visas i följande skärmbild.

   ![Visar karantänsidan med ikonen för utgivningsmeddelande markerad och utgivningsalternativen visas](../../media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)

   Klicka på **Släpp markerat meddelande och tillåt avsändare** i listrutan.

3. Dialogrutan **Släpp och tillåt avsändare** öppnas. Du kan också välja att rapportera meddelandet till Microsoft och sedan klicka på **Släpp och tillåta**. Meddelandet kommer att släppas till alla mottagare som det är adresserat till och alla framtida meddelanden från den här avsändaren tillåts. Om det här meddelandet sattes i karantän på grund av en regel för e-postflöde eller blockerad avsändare fortsätter avsändaren att blockeras för framtida meddelanden.

### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>Släpp ett meddelande i karantän till specifika mottagare utan att rapportera det som ett falskt positivt

1. I EAC navigerar du till \> **Skyddskarantän**. **Protection**

2. Markera ett meddelande, klicka på ikonen **Släpp meddelande** och klicka sedan på Släpp meddelande till **specifika mottagare** i listrutan.

3. I dialogrutan **Släppmeddelande** väljer du något av följande alternativ:

   - **Släpp meddelande till alla mottagare** När du väljer det här alternativet bör du vara medveten om att ett meddelande inte kan släppas mer än en gång till samma mottagare. Om en mottagare tidigare har tagit emot meddelandet kommer det inte att släppas igen till mottagaren.

   - **Släpp meddelande till angivna mottagare** Välj de mottagare som meddelandet kan släppas till. Eftersom ett meddelande bara kan släppas en gång till varje mottagare visas endast mottagare som det kan släppas till i den här listan. Flervalsval stöds. När du har gjort mottagarnas val klickar du på **Lägg till**.

4. Klicka på **släpp**.

Om du **Refresh** ![klickar](../../media/ITPro-EAC-RefreshIcon.gif) på Uppdatera uppdateringsikonen för att uppdatera data och sedan dubbelklickar på meddelandet bör du se att det har släppts till de avsedda mottagarna.

### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>Släpp ett eller flera meddelanden i karantän till alla mottagare

1. I EAC navigerar du till \> **Skyddskarantän**. **Protection**

2. Klicka på ett meddelande för att markera det eller använd skifttangenten för att markera flera meddelanden. Klicka sedan på ikonen **Släpp meddelande.**

3. Klicka på **Släpp markerade meddelanden till alla mottagare** i listrutan.

4. Varningsdialogrutan öppnas. Läs varningen och välj **Ja** om du vill fortsätta. När du väljer det här alternativet bör du vara medveten om att ett meddelande inte kan släppas mer än en gång till samma mottagare. Om en mottagare tidigare har tagit emot meddelandet kommer det inte att släppas igen till mottagaren.

### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>Släpp ett eller flera meddelanden i karantän till alla mottagare och rapportera falska positiva

1. I EAC navigerar du till \> **Skyddskarantän**. **Protection**

2. Klicka på ett meddelande för att markera det eller använd skifttangenten för att markera flera meddelanden. Klicka sedan på ikonen **Släpp meddelande.**

3. Klicka på **Släpp markerade meddelanden och rapportera som falskt positivt** i listrutan.

4. Varningsdialogrutan öppnas. Läs varningen och välj **Ja** om du vill fortsätta. När du väljer det här alternativet bör du vara medveten om att ett meddelande inte kan släppas mer än en gång till samma mottagare. Om en mottagare tidigare har tagit emot meddelandet kommer det inte att släppas igen till mottagaren.

   När du väljer det här alternativet kommer meddelandet att släppas till alla mottagare som ännu inte har fått det. Om det är ett meddelande om skräppost i karantän rapporteras det också till Microsoft Spam Analysis Team, som utvärderar och analyserar meddelandet. Beroende på resultaten av analysen kan reglerna för filterfilter för hela tjänsten justeras så att meddelandet kan gå igenom.

> [!TIP]
> Se till att ett meddelande inte markeras som skräppost genom att följa stegen i [Så här ser du till att ett meddelande inte markeras som skräppost](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md).

Om du **Refresh**![klickar på](../../media/ITPro-EAC-RefreshIcon.gif) ikonen Uppdatera uppdateringsikonen för att uppdatera dina data och sedan dubbelklickar på meddelandet bör du se att det har släppts till de avsedda mottagarna.

## <a name="for-more-information"></a>Mer information

[Vanliga frågor om karantän i karantän](quarantine-faq.md)
