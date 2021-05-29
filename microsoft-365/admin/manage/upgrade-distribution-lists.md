---
title: Uppgradera distributionslistor till Microsoft 365 grupper i Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Lär dig hur du uppgraderar en eller flera distributionslistor till Microsoft 365-grupper i Outlook och hur du använder PowerShell för att uppgradera flera distributionslistor samtidigt.
ms.openlocfilehash: d4686e7f2ec305194130b60fbacab24c9cf7f4e9
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698946"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Uppgradera distributionslistor till Microsoft 365 grupper i Outlook

Du kan uppgradera distributionslistor till Microsoft 365 grupper i Outlook. Det här är ett bra sätt att ge organisationens distributionslistor alla funktioner som finns i Microsoft 365 Groups. [Varför du bör uppgradera dina distributionslistor till grupper i Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

Du kan uppgradera dina distributionslistor en i taget eller flera samtidigt.

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Uppgradera en eller flera distributionsgrupper till Microsoft 365 grupper i Outlook

Du måste vara global administratör Exchange administratör för att uppgradera en distributionsgrupp. Om du vill Microsoft 365 till en e-postgrupp måste distributionsgruppen ha en ägare med en postlåda.

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Använd den nya EAC för att uppgradera en eller flera distributionsgrupper till att Microsoft 365 grupper i Outlook

1. Gå till det [Exchange administrationscentret](https://admin.exchange.microsoft.com)och gå till **Mottagare** \> **grupper**.

2. Välj den distributionsgrupp (även kallad **distributionsgrupp)** som du vill uppgradera Microsoft 365 gruppen från **sidan** Grupper.

3. Välj **distributionsgruppen Uppgradera** i verktygsfältet.

4. I dialogrutan Är du **redo att uppgradera? klickar** du på **Uppgradera.** Processen börjar direkt. Beroende på storleken på och antalet distributionsgrupper som du uppgraderar kan processen ta några minuter eller timmar.

> [!NOTE]
> En banderoll högst upp anger uppgraderingen, till exempel *att distributionsgrupp(er) har uppgraderats. Det tar 5 minuter att återspegla ändringarna. Filtrera Microsoft 365 grupper för att se de uppgraderade gruppernas distruering.*

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>Använd den klassiska versionen av EAC för att uppgradera en eller flera distributionsgrupper till Microsoft 365 grupper i Outlook

1. Gå till det klassiska <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange administrationscentret</a>.

2. Gå till Exchange i klassiska versionen **av** \> **administrationscentret.**<br/>Du ser ett meddelande om att du har distributionslistor (kallas även **distributionsgrupper)** som är kvalificerade för uppgradering till Microsoft 365 Grupper.<br/> ![Välj knappen Komma igång](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Välj en eller flera distributionslistor (kallas även **distributionsgrupp)** på **gruppsidan.**<br/>![Välj en distributionsgrupp](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Välj uppgraderingsikonen.<br/>![Ikonen Uppgradera Microsoft 365 grupper](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. I dialogrutan väljer du Ja **för att** bekräfta uppgraderingen. Processen börjar direkt. Processen kan ta några minuter eller timmar, beroende på hur stora och hur många adresser du uppgraderar.<br/>Om det inte går att uppgradera distributionslistan visas en dialogruta som anger det. Se [Vilka distributionslistor kan inte uppgraderas?](#which-distribution-lists-cant-be-upgraded).

6. Om du uppgraderar flera distributionslistor använder du listrutan för att filtrera fram vilka distributionslistor som har uppgraderats. Om listan inte är färdig väntar du lite till och väljer Uppdatera **för** att se vad som har uppgraderats.<br/>Du får inget meddelande om att uppgraderingen har slutförts för alla distributionslistor du valde. Det här kan du se genom att visa vad som står under **Tillgängliga för uppgradering** eller **Uppgraderade distributionslistor**.

7. Om du valde en dl för uppgradering, men den fortfarande visas på sidan som Tillgänglig för uppgradering, gick det inte att uppgradera den. Läs mer i [Vad gör jag om uppgraderingen inte fungerar](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> Om du får e-postsammandrag för grupper kanske du har lagt märke till erbjudandet om att uppgradera de kvalificerade distributionslistor du äger. Mer information om e-postsammandrag finns i [Hålla en gruppkonversation i Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Vad gör jag om uppgraderingen inte fungerar

Distributionslistor som inte går att uppgradera förändras inte.

Om du inte kan uppgradera en eller flera **kvalificerade** distributionslistor ska du öppna ett [supportärende](../../business-video/get-help-support.md). Ärendet eskaleras till ingenjörsteamet för grupper som försöker lösa problemet.

Det är möjligt att distributionslistan inte uppgraderades på grund av ett avbrott i tjänsten, men osannolikt. Om du vill kan du vänta en stund och sedan försöka uppgradera distributionslistan igen.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Använda PowerShell till att uppgradera flera distributionslistor åt gången

Om du är van vid att använda PowerShell kanske du vill göra det i stället för att använda gränssnittet. Vi har en uppsättning cmdlets som hjälper dig att uppgradera distributionslistor. Se nedan.

### <a name="upgrade-a-single-dl"></a>Uppgradera en enstaka dl

Om du vill uppgradera en enda DLL-lista kör du följande kommando:

```PowerShell
Upgrade-DistributionGroup -DlIdentities <Dl SMTP address>
```

Om du till exempel vill uppgradera en dl med SMTP-dl1@contoso.com kör du följande kommando:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> Du kan också uppgradera en enskild distributionslista till en Microsoft 365 grupp med [PowerShell-cmdleten New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup)

### <a name="upgrade-multiple-dls-in-a-batch"></a>Uppgradera flera E-adresser i en batch

Du kan också överföra flera DLs som en batch och uppgradera dem tillsammans:

```PowerShell
Upgrade-DistributionGroup -DlIdentities <DL SMTP address1>, <DL SMTP address2>,
<DL SMTP address3>, <DL SMTP address4>
```

Om du till exempel vill uppgradera fem DLs med SMTP-adress `dl1@contoso.com` och , och kör du följande `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` kommando:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Uppgradera alla kvalificerade adresser

Du kan uppgradera alla kvalificerade adresser på två sätt.

> [!NOTE]
> Cmdleten Upgrade-DistributionGroup inte tar emot data från pipelinen, av den anledningen är det nödvändigt att använda operatorn "foreach-object {} " för att kunna köras.

1. Hämta de kvalificerade DL:erna i klientorganisationen och uppgradera dem med hjälp av uppgraderingskommandot:

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Hämta listan över alla DLs och uppgradera bara de kvalificerade webbadresserna:

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Vanliga frågor och svar om uppgradering av distributionslistor till Microsoft 365 grupper i Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>Vilka distributionslistor kan inte uppgraderas?

Du kan bara uppgradera enkla distributionslistor som hanteras i molnet och inte är kapslade. I tabellen nedan visas distributionslistor som **INTE** kan uppgraderas.

|**Egenskap**|**Kvalificerad?**|
|:-----|:-----|
|Lokalt hanterad distributionslista  <br/> |Nej  <br/> |
|Kapslade distributionslistor Distributionslistan har antingen underordnade grupper eller är medlem i en annan grupp.  <br/> |Nej  <br/> |
|Distributionslistor med en **annan RecipientTypeDetails** för medlemmar än **UserMailbox,** **SharedMailbox,** **TeamMailbox** och **MailUser**  <br/> |Nej  <br/> |
|Distributionslista med fler än 100 ägare  <br/> |Nej  <br/> |
|Distributionslista som bara har medlemmar men ingen ägare  <br/> |Nej  <br/> |
|Distributionslista med alias som innehåller specialtecken  <br/> |Nej  <br/> |
|Om distributionslistan är konfigurerad som en adress för vidarebefordran för Delad postlåda  <br/> |Nej  <br/> |
|Om dl är en del av **avsändarbegränsningen** i en annan dl.  <br/> |Nej  <br/> |
|Säkerhetsgrupper  <br/> |Nej  <br/> |
|Dynamiska distributionslistor  <br/> |Nej  <br/> |
|Distributionslistor som har konverterats till **RoomLists**  <br/> |Nej  <br/> |
|Distributionslistor där **MemberJoinRestriction** och/eller **MemberDepartRestriction** är **stängt**  <br/> |Nej  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>Kontrollera vilka adresser som är kvalificerade för uppgradering

Om du vill kontrollera om en dll-lista är berättigad eller inte kan du köra följande kommando:

`Get-DistributionGroup <DL SMTP address> | Get-EligibleDistributionGroupForMigration`

Om du vill kontrollera vilka adresser som är kvalificerade för uppgradering kör du följande kommando:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Vilka kan köra uppgraderingsskripten?

Personer med global administratör Exchange administratörsrättigheter.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Varför visas det fortfarande en distributionslista på kontaktkortet? Hur kan jag förhindra att en uppgraderad distributionslista visas i min lista med automatiska förslag?

- För Outlook: När någon försöker skicka ett e-postmeddelande i Outlook genom att skriva namnet på Microsoft 365-gruppen efter migrering matchas mottagaren som distributionslistan i stället för gruppen. Mottagarens kontaktkort blir distributionslistans kontaktkort. Det här beror på mottagarens cache eller cachen för smeknamn i Outlook. E-postmeddelandet kommer att skickas till gruppen, men det kan vara förvirrande för avsändaren.<br/>Du kan utföra stegen i den här artikeln Information om listan [Outlook för](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) att återställa cachen, vilket löser problemet.

- För Outlook på webben: Om du har Outlook på webben ligger distributionslistan kvar som mottagare i cachen. Du kan följa stegen i Ta bort föreslagna namn eller [e-postadresser](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) från listan Komplettera automatiskt om du vill uppdatera cachen så att gruppkontaktkortet visas.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Får nya gruppmedlemmar ett välkomstmeddelande i Inkorgen?

Nej. Inställningen för välkomstmeddelanden är inaktiverad som standard. Den här inställningen påverkar både befintliga och nya gruppmedlemmar som kan ansluta efter migreringen. Om gruppägare senare tillåter gästanvändare får inte heller gästanvändare något välkomstmeddelande i Inkorgen. Gästmedlemmar kan fortsätta att arbeta med gruppen.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Vad händer om en eller några av de utl:erna inte uppgraderas?

Det finns vissa fall där dl är berättigad men inte kan uppgraderas. Dl uppgraderas inte och finns kvar som en dl.

- Där administratören har **tillämpat** principen för grupp-e-postadress för grupper i en organisation och de försöker uppgradera dll-adresser som inte uppfyller villkoren, uppgraderas inte dll-posten

- DLs med **MemberJoinRestriction eller** **MemberDepartRestriction** inställd **på Stängd**, kunde inte uppgraderas

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Vad händer med distributionslistan om uppgraderingen från EAC misslyckas?

Uppgraderingen utförs bara när anropet skickas till servern. Om uppgraderingen misslyckas förblir distributionslistorna intakta. De fungerar som de brukade.

## <a name="related-content"></a>Relaterat innehåll

[Jämför grupper](../create-groups/compare-groups.md) (artikel)\
[Förklara Microsoft 365 grupper för användarna](../create-groups/explain-groups-knowledge-worker.md) (artikel)\
[Lägga till eller ta bort medlemmar Microsoft 365 grupper i administrationscentret](../create-groups/add-or-remove-members-from-groups.md)
