---
title: Uppgradera distributionslistor till Office 365-grupper i Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Lär dig hur du uppgraderar en eller flera distributionslistor till Office 365-grupper i Outlook och hur du använder PowerShell för att uppgradera flera distributionslistor samtidigt.
ms.openlocfilehash: 7337d450cf1e9b249b2b9dc2ab66f32f5b1577e0
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807557"
---
# <a name="upgrade-distribution-lists-to-office-365-groups-in-outlook"></a>Uppgradera distributionslistor till Office 365-grupper i Outlook

Du kan uppgradera distributionslistor till Office 365-grupper med Outlook. Det här är ett bra sätt att ge organisationens distributionslistor alla funktioner som finns för Office 365-grupper. [Varför du bör uppgradera dina distributionslistor till grupper i Outlook](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)

Du kan uppgradera dina distributionslistor en i taget eller flera samtidigt.

## <a name="upgrade-one-or-many-distribution-lists-to-office-365-groups-in-outlook"></a>Uppgradera en eller flera distributionslistor till Office 365-grupper i Outlook

Du måste vara en global office 365-administratör eller Exchange-administratör för att kunna uppgradera en distributionslista. Om du vill uppgradera till Office 365-grupper måste en distributionsgrupp ha en ägare med en postlåda. 

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

2. Gå till **mottagargrupper**i **administrationscentret** \> för Exchange.<br/>Du ser ett meddelande om att du har distributionslistor (kallas även **distributionsgrupper** ) som är kvalificerade för uppgradering till Office 365-grupper.<br/> ![Välj knappen Kom igång](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Välj en eller flera distributionslistor (kallas även för **distributionsgrupp** ) från **gruppsidan**.<br/>![Välj en distributionsgrupp](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Välj uppgraderingsikonen.<br/>![Ikonen Uppgradera till Office 365-grupper](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Välj **Ja** för att bekräfta uppgraderingen i informationsdialogrutan. Processen börjar omedelbart. Beroende på storleken och antalet DLs som du uppgraderar kan processen ta minuter eller timmar.<br/>Om det inte går att uppgradera distributionslistan visas en dialogruta som anger det. Se [Vilka distributionslistor kan inte uppgraderas?](#which-distribution-lists-cannot-be-upgraded).

6. Om du uppgraderar flera distributionslistor använder du listrutan för att filtrera vilka distributionslistor som har uppgraderats. Om listan inte är klar väntar du en stund längre och väljer sedan **Uppdatera** för att se vad som har uppgraderats.<br/>Du får inget meddelande om att uppgraderingen har slutförts för alla distributionslistor du valde. Det här kan du se genom att visa vad som står under **Tillgängliga för uppgradering** eller **Uppgraderade distributionslistor**.

7. Om du valde en distributionslista för uppgradering, men den fortfarande visas på sidan som Tillgänglig för uppgradering, så gick det inte att uppgradera listan. Läs mer i [Vad gör jag om uppgraderingen inte fungerar](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> Om du får e-postsammandrag för grupper kanske du har lagt märke till erbjudandet om att uppgradera de kvalificerade distributionslistor du äger. Mer information om e-postsammandrag finns i [Hålla en gruppkonversation i Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx).


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Vad gör jag om uppgraderingen inte fungerar

Distributionslistor som inte går att uppgradera förändras inte.

Om du inte kan uppgradera en eller flera **kvalificerade** distributionslistor ska du öppna ett [supportärende](../contact-support-for-business-products.md). Ärendet eskaleras till ingenjörsteamet för grupper som försöker lösa problemet.

Det är möjligt att distributionslistan inte uppgraderades på grund av ett avbrott i tjänsten, men det är ganska osannolikt. Om du vill kan du vänta en stund och sedan försöka uppgradera distributionslistan igen.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Använda PowerShell till att uppgradera flera distributionslistor åt gången

Om du är van vid att använda PowerShell kanske du vill göra det i stället för att använda gränssnittet. Vi har en uppsättning cmdlets som hjälper dig att uppgradera distributionslistor. Se nedan.

### <a name="upgrade-a-single-dl"></a>Uppgradera en enda DL

Så här uppgraderar du ett enda DL-kommando följande kommando:

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

Om du till exempel vill uppgradera en DLs med SMTP-adress dl1@contoso.com kör du följande kommando:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> Du kan också uppgradera en enda distributionslista till en Office 365-grupp med den [nya PowerShell-cmdleten](https://go.microsoft.com/fwlink/?LinkID=786379)

### <a name="upgrade-multiple-dls-in-a-batch"></a>Uppgradera flera DLs i en batch

Du kan också skicka flera DLs som en batch och uppgradera dem tillsammans:

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Om du till exempel vill uppgradera fem DLs `dl1@contoso.com` med `dl2@contoso.com` `dl3@contoso.com`SMTP-adress och , `dl4@contoso.com` och `dl5@contoso.com`kör följande kommando:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Uppgradera alla kvalificerade DLs

Det finns två sätt på vilka du kan uppgradera alla kvalificerade DLs.

> [!NOTE]
> Cmdlet en uppgraderingsdistributiongrupp tar inte emot data från pipelinen, därför krävs det{}att operatorn "foreach-object" körs för att köras.

1. Hämta de kvalificerade DLs i klienten och uppgradera dem med kommandot uppgradera:

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Hämta listan över alla DLs och uppgradera endast de kvalificerade DLs:

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-office-365-groups-in-outlook"></a>Vanliga frågor och svar om uppgradering av distributionslistor till Office 365-grupper i Outlook

### <a name="which-distribution-lists-cannot-be-upgraded"></a>Vilka distributionslistor kan inte uppgraderas?

Du kan bara uppgradera enkla distributionslistor som hanteras i molnet och inte är kapslade. I tabellen nedan visas distributionslistor som **inte kan** uppgraderas.

|**Egenskap**|**Kvalificerad?**|
|:-----|:-----|
|Lokalt hanterad distributionslista  <br/> |Nej  <br/> |
|Kapslade distributionslistor Distributionslistan har antingen underordnade grupper eller är medlem i en annan grupp.  <br/> |Nej  <br/> |
|Distributionslistor med medlem **MottagareTypDetaljer** annat än **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**  <br/> |Nej  <br/> |
|Distributionslista som har mer än 100 ägare  <br/> |Nej  <br/> |
|Distributionslista som endast har medlemmar och ingen ägare  <br/> |Nej  <br/> |
|Distributionslista med ett alias som innehåller specialtecken  <br/> |Nej  <br/> |
|Om distributionslistan är konfigurerad som en adress för vidarebefordran för Delad postlåda  <br/> |Nej  <br/> |
|Om DL är en del av **Avsändarens begränsning** i en annan DL.  <br/> |Nej  <br/> |
|Säkerhetsgrupper  <br/> |Nej  <br/> |
|Dynamiska distributionslistor  <br/> |Nej  <br/> |
|Distributionslistor som konverterades till **RoomLists**  <br/> |Nej  <br/> |
|Distributionslistor där **MemberJoinRestriction** och/eller **MemberDepartRestriction** **är stängd**  <br/> |Nej  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a>Hur kontrollerar jag vilka DLs som är kvalificerade för uppgradering?

Om du vill kontrollera om en DL är kvalificerad eller inte kan du köra nedanstående kommando:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Om du vill kontrollera vilka DLs är berättigade till uppgradering kör du bara följande kommando:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Vilka kan köra uppgraderingsskripten?

Personer med Office 365 globala administratörs- eller Exchange-administratörsrättigheter.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Varför visas det fortfarande en distributionslista på kontaktkortet? Hur kan jag förhindra att en uppgraderad distributionslista visas i min lista med automatiska förslag?

- För Outlook: När någon försöker skicka ett e-postmeddelande i Outlook genom att skriva Office 365-gruppnamnet efter migreringen, matchas mottagaren som distributionslista i stället för gruppen. Mottagarens kontaktkort blir distributionslistans kontaktkort. Det här beror på mottagarens cache eller cachen för smeknamn i Outlook. E-postmeddelandet skickas framgångsrikt till gruppen, men kan orsaka förvirring för avsändaren.<br/>Du kan följa instruktionerna i [Information om listan Komplettera automatiskt i Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) om du vill återställa cachen, vilket löser problemet.

- För Outlook på webben: I händelse av Outlook på webben finns mottagaren av distributionslistan fortfarande kvar i cacheminnet. Du kan följa stegen i [Ta bort föreslagen namn eller e-postadress från listan Komplettera automatiskt](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) för att uppdatera cacheminnet för att se gruppkontaktkortet.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Får nya gruppmedlemmar ett välkomstmeddelande i Inkorgen?

Nej. Inställningen för välkomstmeddelanden är inaktiverad som standard. Den här inställningen påverkar både befintliga och nya gruppmedlemmar som kan ansluta efter migreringen. Om gruppägare senare tillåter gästanvändare får inte heller gästanvändare något välkomstmeddelande i Inkorgen. Gästmedlemmar kan fortsätta att arbeta med gruppen.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Vad händer om en eller några av DLs inte uppgraderas?

Det finns vissa fall där även om DL är kvalificerat men inte kunde uppgraderas. DL uppgraderas inte och förblir som dl.

- Om administratören har tillämpat **grupadressprincip** för grupperna i en organisation och de försöker uppgradera DLs som inte uppfyller kriterierna, uppgraderas inte DL-kortsystemet

- DLs med **MemberJoinRestriction** eller **MemberDepartRestriction** inställd på **Stängd**, kunde inte uppgraderas

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Vad händer med distributionslistan om uppgraderingen från EAC misslyckas?

Uppgraderingen utförs bara när anropet skickas till servern. Om uppgraderingen misslyckas förblir distributionslistorna intakta. De fungerar som de brukade.


