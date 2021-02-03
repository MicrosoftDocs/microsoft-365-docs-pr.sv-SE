---
title: Uppgradera distributionslistor till Microsoft 365-grupper i Outlook
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
ms.openlocfilehash: 95f887b4386b349dc9d8bb471deab19b5425f6f5
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080533"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Uppgradera distributionslistor till Microsoft 365-grupper i Outlook

Du kan uppgradera distributionslistor till Microsoft 365-grupper med Outlook. Det här är ett bra sätt att ge organisationens distributionslistor alla funktioner som Finns i Microsoft 365-grupper. [Varför du bör uppgradera dina distributionslistor till grupper i Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

Du kan uppgradera dina distributionslistor en i taget eller flera samtidigt.

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Uppgradera en eller flera distributionslistor till Microsoft 365-grupper i Outlook

Du måste vara global administratör eller Exchange-administratör för att uppgradera en distributionslista. Om du vill uppgradera till Microsoft 365-grupper måste en distributionsgrupp ha en ägare med en postlåda.

1. Gå till <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">administrationscentret för Exchange</a>.

2. Gå till Mottagare grupper i **administrationscentret för** \> **Exchange.**<br/>Ett meddelande visas om att du har distributionslistor (kallas även **distributionsgrupper)** som kan uppgraderas till Microsoft 365-grupper.<br/> ![Välj knappen Komma igång](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Välj en eller flera distributionslistor (kallas även för **distributionsgrupp** ) från **gruppsidan**.<br/>![Välj en distributionsgrupp](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. Välj uppgraderingsikonen.<br/>![Ikonen Uppgradera till Microsoft 365-grupper](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. Välj Ja i **informationsdialogrutan för** att bekräfta uppgraderingen. Processen börjar direkt. Beroende på hur många och stora adresser du uppgraderar kan processen ta några minuter eller timmar.<br/>Om det inte går att uppgradera distributionslistan visas en dialogruta som anger det. Se [Vilka distributionslistor kan inte uppgraderas?](#which-distribution-lists-cant-be-upgraded).

6. Om du uppgraderar flera distributionslistor kan du använda listrutan för att filtrera fram vilka distributionslistor som har uppgraderats. Om listan inte är klar väntar du en stund till och väljer **sedan** Uppdatera för att se vad som har uppgraderats.<br/>Du får inget meddelande om att uppgraderingen har slutförts för alla distributionslistor du valde. Det här kan du se genom att visa vad som står under **Tillgängliga för uppgradering** eller **Uppgraderade distributionslistor**.

7. Om du valde en distributionslista för uppgradering, men den fortfarande visas på sidan som Tillgänglig för uppgradering, så gick det inte att uppgradera listan. Läs mer i [Vad gör jag om uppgraderingen inte fungerar](#what-to-do-if-the-upgrade-doesnt-work).

> [!NOTE]
> Om du får e-postsammandrag för grupper kanske du har lagt märke till erbjudandet om att uppgradera de kvalificerade distributionslistor du äger. Mer information om e-postsammandrag finns i [Hålla en gruppkonversation i Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22).

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>Vad gör jag om uppgraderingen inte fungerar

Distributionslistor som inte går att uppgradera förändras inte.

Om du inte kan uppgradera en eller flera **kvalificerade** distributionslistor ska du öppna ett [supportärende](../contact-support-for-business-products.md). Ärendet eskaleras till ingenjörsteamet för grupper som försöker lösa problemet.

Det är möjligt att distributionslistan inte uppgraderades på grund av ett avbrott i tjänsten, men det är ganska osannolikt. Om du vill kan du vänta en stund och sedan försöka uppgradera distributionslistan igen.

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>Använda PowerShell till att uppgradera flera distributionslistor åt gången

Om du är van vid att använda PowerShell kanske du vill göra det i stället för att använda gränssnittet. Vi har en uppsättning cmdlets som hjälper dig att uppgradera distributionslistor. Se nedan.

### <a name="upgrade-a-single-dl"></a>Uppgradera en enda dl

Om du vill uppgradera en enskild DLL kör du följande kommando:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

Om du till exempel vill uppgradera en DLs med SMTP-dl1@contoso.com kör du följande kommando:

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> Du kan också uppgradera en enskild distributionslista till en Microsoft 365-grupp med [PowerShell-cmdleten New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379)

### <a name="upgrade-multiple-dls-in-a-batch"></a>Uppgradera flera adresser i en batch

Du kan även överföra flera DLs som en batch och uppgradera dem tillsammans:

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

Om du till exempel vill uppgradera fem DLs med SMTP-adress och köra `dl1@contoso.com` `dl2@contoso.com` följande `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` kommando:

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>Uppgradera alla kvalificerade adresser

Du kan uppgradera alla kvalificerade adresser på två sätt.

> [!NOTE]
> CmdletUpgrade-DistributionGroup tar inte emot data från pipelinen, av den anledningen är det nödvändigt att använda operatorn "foreach-object " för {} att köras korrekt.

1. Hämta de kvalificerade DLs i klientorganisationen och uppgradera dem med hjälp av uppgraderingskommandot:

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. Hämta listan över alla DLs och uppgradera endast de kvalificerade DLs:

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>Vanliga frågor och svar om uppgradering av distributionslistor till Microsoft 365-grupper i Outlook

### <a name="which-distribution-lists-cant-be-upgraded"></a>Vilka distributionslistor kan inte uppgraderas?

Du kan bara uppgradera enkla distributionslistor som hanteras i molnet och inte är kapslade. I tabellen nedan visas distributionslistor som **INTE** kan uppgraderas.

|**Egenskap**|**Kvalificerad?**|
|:-----|:-----|
|Lokalt hanterad distributionslista  <br/> |Nej  <br/> |
|Kapslade distributionslistor Distributionslistan har antingen underordnade grupper eller är medlem i en annan grupp.  <br/> |Nej  <br/> |
|Distributionslistor med andra **RecipientTypeDetails** för medlemmar än **UserMailbox,** **SharedMailbox,** **TeamMailbox,** **MailUser**  <br/> |Nej  <br/> |
|Distributionslista med fler än 100 ägare  <br/> |Nej  <br/> |
|Distributionslista som endast har medlemmar och ingen ägare  <br/> |Nej  <br/> |
|Distributionslista med ett alias som innehåller specialtecken  <br/> |Nej  <br/> |
|Om distributionslistan är konfigurerad som en adress för vidarebefordran för Delad postlåda  <br/> |Nej  <br/> |
|Om dll-listan ingår i en **avsändarbegränsning** i en annan dll-post.  <br/> |Nej  <br/> |
|Säkerhetsgrupper  <br/> |Nej  <br/> |
|Dynamiska distributionslistor  <br/> |Nej  <br/> |
|Distributionslistor som har konverterats till **RoomLists**  <br/> |Nej  <br/> |
|Distributionslistor där **MemberJoinRestriction** och/eller **MemberDepartRestriction** är **stängt**  <br/> |Nej  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>Kontrollera vilka adresser som är kvalificerade för uppgradering

Om du vill kontrollera om en dll-lista är berättigad eller inte kan du köra följande kommando:

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

Om du vill kontrollera vilka DLs som är kvalificerade för uppgradering kör du följande kommando:

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>Vilka kan köra uppgraderingsskripten?

Användare med global administratör eller Exchange-administratörsrättigheter.

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>Varför visas det fortfarande en distributionslista på kontaktkortet? Hur kan jag förhindra att en uppgraderad distributionslista visas i min lista med automatiska förslag?

- För Outlook: När någon försöker skicka ett e-postmeddelande i Outlook genom att skriva namnet på Microsoft 365-gruppen efter migrering matchas mottagaren som distributionslistan i stället för gruppen. Mottagarens kontaktkort blir distributionslistans kontaktkort. Det här beror på mottagarens cache eller cachen för smeknamn i Outlook. E-postmeddelandet kommer att skickas till gruppen, men det kan vara förvirrande för avsändaren.<br/>Du kan följa instruktionerna i [Information om listan Komplettera automatiskt i Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) om du vill återställa cachen, vilket löser problemet.

- För Outlook på webben: Om du använder Outlook på webben ligger distributionslistan kvar som mottagare i cachen. Du kan följa stegen i Ta bort föreslagna namn eller [e-postadresser](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) från listan Komplettera automatiskt om du vill uppdatera cachen så att gruppkontaktkortet visas.

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>Får nya gruppmedlemmar ett välkomstmeddelande i Inkorgen?

Nej. Inställningen för välkomstmeddelanden är inaktiverad som standard. Den här inställningen påverkar både befintliga och nya gruppmedlemmar som kan ansluta efter migreringen. Om gruppägare senare tillåter gästanvändare får inte heller gästanvändare något välkomstmeddelande i Inkorgen. Gästmedlemmar kan fortsätta att arbeta med gruppen.

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>Vad händer om en eller några av dina E-adresser inte uppgraderas?

Det finns vissa fall där dl är berättigande men inte kunde uppgraderas. Dl uppgraderas inte och blir kvar som en dl.

- Om administratören har **tillämpat** principen för grupp-e-postadress för grupperna i en organisation och de försöker uppgradera dina adresser som inte uppfyller villkoren uppgraderas inte dll-posten

- DLs med **MemberJoinRestriction** eller **MemberDepartRestriction** inställd på **Stängt,** kunde inte uppgraderas

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>Vad händer med distributionslistan om uppgraderingen från EAC misslyckas?

Uppgraderingen utförs bara när anropet skickas till servern. Om uppgraderingen misslyckas förblir distributionslistorna intakta. De fungerar som de brukade.
