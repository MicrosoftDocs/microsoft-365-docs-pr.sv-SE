---
title: Microsoft 365 för företag – strategier för distribuering av grundläggande infrastruktur
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Lär dig några av sätten som du kan använda för att distribuera faserna i den grundläggande infrastrukturen för Microsoft 365 för företag.
ms.openlocfilehash: 5eb4851a4c967baae268e04113b4e44023164db4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638158"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-deployment-strategies"></a>Microsoft 365 för företag – strategier för distribuering av grundläggande infrastruktur

Det finns många sätt som du kan använda för att distribuera faserna i [den grundläggande infrastrukturen](deploy-foundation-infrastructure.md) för Microsoft 365 för företag och lansera funktioner, program och tjänster för dina användare. Tänk på följande distributionsstrategier om du vill komma igång med projektledningen av det här jobbet, som kan vara stor och komplicerad beroende på hur stor din organisation är och dess befintliga infrastruktur:

- Seriell distribution
- Parallell distribution med ej överlappande användarlansering
- Parallell distribution med överlappande användarlansering
- Inledande infrastruktur och lansering av slutpunkt till slutpunkt-konfigurationen

Använd de här strategierna för att få förslag på hur du kan hantera det övergripande projektet och hur du snabbare kan använda affärsfördelarna med Microsoft 365 för företag.

>[!Note]
>I den här artikeln beskrivs förutsättningar och förenklingar för att på ett konsekvent sätt beskriva distributionsstrategierna. Dessa distributionsstrategier är allmänna och är inte avsedda att ange vissa tidsramar. De är inte heller avsedda att tillämpas för alla organisationer och situationer.
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a>Element i IT-projektledning för typiska företagsorganisationer

IT-infrastruktur omfattar både serverdelstjänster och lansering av nya eller förbättrade funktioner eller installerad programvara för slutanvändare. IT-avdelningar distribuerar vanligtvis delar av en IT-infrastruktur på ett metodiskt sätt. En metod för framgångsrik distribution av ett element i IT-infrastrukturen består av:

- En pilotlansering 

  Den omfattar en första konfiguration av infrastruktur och lansering av en pilotuppsättning användare, tester och efterföljande ändringar av infrastrukturens konfiguration.

- En användarlansering

  Den omfattar lanseringen till resten av din organisation baserat på regioner, avdelningar, grupper eller andra typer av systematisk spridning av konfiguration eller programvara.

Uppsättningen användare som ingår i pilotlanseringen är inte desamma som ingår i användarlanseringen.

I den här artikeln används följande grafik för att åskådliggöra definitionerna: 

![Grafiken som visar definitionerna av pilot- och användarlansering](../media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

Skuggan för grafiken som visar användarlanseringen anger procentsatsen i din organisation från 0 % till 100 % som använder en strukturerad eller metodisk metod, t. ex. grupper, avdelningar eller regioner.

## <a name="deployment-strategies"></a>Distributionsstrategier

Överväg följande distributionsstrategier:

- Seriell distribution
- Parallell distribution med ej överlappande användarlansering
- Parallell distribution med överlappande användarlansering
- Inledande infrastruktur och lansering av slutpunkt till slutpunkt-konfigurationen

### <a name="serial-deployment"></a>Seriell distribution

Vid seriell distribution slutför du en fas helt och ser till att fasen distribueras till 100 % till alla dina användare innan du går vidare till nästa fas. Här är några anledningar till varför det kan vara bra att distribuera på det här sättet:

- Riskhantering
- Resursbegränsningar
- Finansieringscykler för IT-avdelningen
- IT-teknikberoenden
- Företagets förändringshantering och slutanvändares resistens

I det här Gantt-schemat visas en förenklad seriell distribution av fas 2–6 av den grundläggande infrastrukturen för Microsoft 365 för företag.

![Seriell distribution av fas 2–6 av den grundläggande infrastrukturen](../media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
För att förenkla diskussionen och exemplet måste samtliga fas- och distributionssegment i varje fas pågå lika länge.

>[!Note]
>Fas 1: Nätverk för den grundläggande infrastrukturen för Microsoft 365 för företag är en fas som endast berör IT-avdelningen. Användare drar nytta av fördelarna med optimerad anslutning till Microsofts molnresurser men de behöver inte göra något för att få den.
>

Här följer en förenklad pilotupplevelse för användare som exempel:

- I december behöver jag använda min smartphone för MFA. (Identitet)
- I mars får jag Windows 10 Enterprise installerat på min dator med Windows 8.1. (Windows 10 Enterprise)
- I juni får jag Microsoft 365-applikationer för företag installerat, som ersätter Office 2013. (Microsoft 365-applikationer för företag)
- I september får jag principer för enhetsregistrering, appar och enheter. (Hantering av mobila enheter)
- I december får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument. (Informationsskydd)

Resultatet är en takt på 90 dagar mellan på varandra följande pilotlanseringar.

Här följer en förenklad upplevelse för slutanvändare som exempel:

- I januari behöver jag använda min smartphone för MFA. (Identitet)
- I april får jag Windows 10 Enterprise installerat på min dator med Windows 8.1. (Windows 10 Enterprise)
- I juli får jag Microsoft 365-applikationer för företag installerat, som ersätter Office 2013. (Microsoft 365-applikationer för företag)
- I oktober får jag principer för enhetsregistrering, appar och enheter. (Hantering av mobila enheter)
- I januari efterföljande år får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument. (Informationsskydd)

Resultatet är en takt på 90 dagar mellan på varandra följande användarlanseringar.

Nackdelen med den här distributionsstrategin är att det kan ta lång tid att helt distribuera den grundläggande infrastrukturen för Microsoft 365 för företag.

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a>Parallell distribution med ej överlappande användarlansering (Parallell 1)

För den här distributionsstrategin startar du pilotlanseringen för nästa fas under sista delen av användarlanseringen för den aktuella fasen.
Här är distributionen av faserna 2–6 när pilotlanseringen inleds då användarlanseringen av föregående fas avslutas.

![Den parallella distributionen av faserna 2–6 med ej överlappande användarlansering](../media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
Slutresultatet är att användarlansering för den aktuella fasen slutförs i hela organisationen innan nästa påbörjas. Användare som inte deltar i pilotlanseringar hanterar inte lanseringar av flera faser samtidigt, men pilotlanseringar görs parallellt med användarlanseringar.

Här följer en förenklad pilotupplevelse för användare som exempel:

- I december behöver jag använda min smartphone för MFA. (Identitet)
- I februari får jag Windows 10 Enterprise installerat på min dator med Windows 8.1. (Windows 10 Enterprise)
- I april får jag Microsoft 365-applikationer för företag installerat, som ersätter Office 2013. (Microsoft 365-applikationer för företag)
- I juni får jag principer för enhetsregistrering, appar och enheter. (Hantering av mobila enheter)
- I augusti får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument. (Informationsskydd)

Resultatet är en takt på 60 dagar mellan på varandra följande pilotlanseringar.

Här följer en förenklad upplevelse för slutanvändare som exempel:

- I januari behöver jag använda min smartphone för MFA. (Identitet)
- I mars får jag Windows 10 Enterprise installerat på min dator med Windows 8.1. (Windows 10 Enterprise)
- I maj får jag Microsoft 365-applikationer för företag installerat, som ersätter Office 2013. (Microsoft 365-applikationer för företag)
- I juli får jag principer för enhetsregistrering, appar och enheter. (Hantering av mobila enheter)
- I september får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument. (Informationsskydd)

Resultatet är en takt på 60 dagar mellan på varandra följande användarlanseringar.

Fördelen med den här distributionsstrategin är att det kan ta kortare tid att helt distribuera den grundläggande infrastrukturen för Microsoft 365 för företag, utan att IT-avdelningen och användare behöver hantera flera lanseringar samtidigt.

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a>Parallell distribution med överlappande användarlansering (Parallell 2)

För den här distributionsstrategin startar du:

- Pilotlanseringen för nästa fas under sista delen av användarlanseringen för den aktuella fasen.
- Användarlansering av nästa fas under användarlanseringen av den aktuella fasen på ett sätt som gör att inga användare hanterar lanseringar av flera faser samtidigt. Det här förutsätter att du lanserar varje fas av den grundläggande infrastrukturen på samma sätt genom att använda regioner, avdelningar eller andra indelningar.

Här är en förenklad jämförelse mellan de olika distributionsstrategierna.

![Den parallella distributionen av faserna 2–6 med överlappande användarlansering](../media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

Slutresultatet är:

- Pilotlanseringar går från en fas till nästa utan pauser.
- Användarlansering för en fas börjar innan användarlanseringen av föregående fas slutförs, men ingen enskild användare får mer än en fas lanserad samtidigt.

Här följer en förenklad pilotupplevelse för användare som exempel:

- I december behöver jag använda min smartphone för MFA. (Identitet)
- I januari får jag Windows 10 Enterprise installerat på min dator med Windows 8.1. (Windows 10 Enterprise)
- I februari får jag Microsoft 365-applikationer för företag installerat, som ersätter Office 2013. (Microsoft 365-applikationer för företag)
- I mars får jag principer för enhetsregistrering, appar och enheter. (Hantering av mobila enheter)
- I april får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument. (Informationsskydd)

Resultatet är en takt på 30 dagar mellan på varandra följande pilotlanseringar.

Här följer en förenklad upplevelse för slutanvändare som exempel:

- I januari behöver jag använda min smartphone för MFA. (Identitet)
- I februari får jag Windows 10 Enterprise installerat på min dator med Windows 8.1. (Windows 10 Enterprise)
- I mars får jag Microsoft 365-applikationer för företag installerat, som ersätter Office 2013. (Microsoft 365-applikationer för företag)
- I april får jag principer för enhetsregistrering, appar och enheter. (Hantering av mobila enheter)
- I maj får jag Azure Information Protection-klienten installerad och får veta hur jag lägger till etiketter i dokument. (Informationsskydd)

Resultatet är en takt på 30 dagar mellan på varandra följande användarlanseringar.

Fördelen med den här distributionsstrategin är att det kan ta ännu kortare tid att helt distribuera den grundläggande infrastrukturen för Microsoft 365 för företag, och slutanvändare behöver fortfarande inte hantera flera lanseringar samtidigt. Användare får dock inte någon paus mellan på varandra följande steg.

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a>Inledande infrastruktur och lansering av slutpunkt till slutpunkt-konfigurationen

För mindre organisationer som kan komprimera faserna 2–6 till ett enda distributionssegment ser den resulterande distributionen ut så här:
 
![Inledande infrastruktur och lansering av slutpunkt till slutpunkt-konfigurationen](../media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

IT-avdelningen konfigurerar infrastrukturen för faserna 2–6 och lanserar sedan för pilotanvändarna för att kontrollera funktioner från slutpunkt till slutpunkt. Pilotanvändare får till exempel alla de här funktionerna på samma gång:

- MFA och andra identitetsfunktioner (Identitet)
- Windows 10 Enterprise på Windows-enheter (Windows 10 Enterprise)
- Microsoft 365-applikationer för företag för Office-paketet (Microsoft 365-applikationer för företag)
- Principer för appar och enheter (hantering av mobila enheter)
- Azure Information Protection-klienten installeras och utbildning sker om hur man lägger till etiketter i dokument (Informationsskydd).

När pilotlanseringen har avslutats inleds användarlanseringen när varje användare får alla funktioner samtidigt.

## <a name="next-step"></a>Nästa steg

Inled din distribution av Microsoft 365 för företag med den [grundläggande infrastrukturen](deploy-foundation-infrastructure.md).
