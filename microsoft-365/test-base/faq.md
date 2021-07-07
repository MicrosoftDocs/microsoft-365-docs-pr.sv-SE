---
title: Vanliga frågor och svar om testbas
description: Gå igenom vanliga frågor och svar
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9d24ecb807e60733471be60353d12789f19be1b4
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323385"
---
# <a name="test-base-faq"></a>Vanliga frågor och svar om testbas

**F: Hur skickar vi in våra paket till Test Base-teamet?**

**S:** Skicka paketen direkt till Test Base-miljön med vår självbetjäningsportal.

Skicka programpaketet genom att gå till [Azure-portalen](https://www.aka.ms/testbaseportal "Startsida för testbas") och ladda upp en zippad mapp som innehåller programmets binärfiler, beroenden och testskript via instrumentpanelen Test Base-självbetjäning för portalen. 

Mer information finns i introduktionsguiden eller kontakta vårt team för <testbasepreview@microsoft.com> att få hjälp och mer information.

**F: Vad är OOB-tester (in-box)**

**S:** OOB-tester (out-of-box) är standardiserade, standardtestet körs där programpaket installeras, startas och stängs trettio (30) gånger och avinstalleras sedan. 

Paketen som skapas för Test Base har följande testskript: installera, starta, stäng och eventuellt avinstallationsskriptet. 

OOB-testerna (Out-box) ger dig standardiserade telemetri för programmet att jämföra mellan olika Windows byggen.

**F: Kan vi skicka in tester utanför de inramade testerna (installation, start, stängning, avinstallation av testskript)?**

**S:** Ja, kunder kan även ladda upp programpaket för **funktionstester** via instrumentpanelen på portalen.
**Funktionstester** är tester som gör att kunderna kan köra sina skript för att köra anpassade funktioner på programmet.


## <a name="testing"></a>Testning

**F: Stöder ni funktionstester?**

**S:** Ja, testbas har stöd för funktionstester. Funktionstester är tester som gör att våra kunder kan köra sina skript för att köra anpassade funktioner i programmet. 

Om du vill skicka in ditt programpaket för funktionstestning behöver du bara ladda upp den zippade mappen som innehåller programmets binärfiler, beroenden och testskript via vår självbetjäningsportalinstrumentpanel. 

Mer information finns i introduktionsguiden eller kontakta vårt team för <testbasepreview@microsoft.com> att få hjälp och mer information.

**F: Hur hanterar Test Base våra testdata?**

**S:** Test Base samlar in och hanterar testdata på ett säkert sätt i Azure-miljön. 

**F: Kan testbasen stödja våra automatiska tester?**

Ja, Test Base stöder automatiska tester men vi stöder inte manuella tester just nu på grund av tjänstefunktioner.

**F: Vilka språk och ramverk för automatiska tester stöder du?**

**S:** Vi stöder alla språk och ramverk. Vi anropar alla skript via PowerShell. 

Du måste också tillhandahålla (ladda upp) de beroende binärfilerna för det nödvändiga ramverket.

**F: Hur snart tillhandahåller Test Base testresultat?**

**S:** För varje test vi kör mot förhands versionerna kommer vi att tillhandahålla resultat inom 48 timmar på din [Azure Portal-instrumentpanel.](https://www.aka.ms/testbaseportal "Startsida för testbas")

**F: Kan du starta om efter installationen?**

**S:** Ja, vår process har stöd för att starta om efter installationen. Se till att välja det här alternativet i listrutan "Valfria inställningar" när du anger **Dina** uppgifter på introduktionsportalen.

För OOB-tester (Out-of-box) kan du ange om en omstart krävs för _installationsskriptet._

![Starta om bild](Media/reboot.png)

När du ska köra funktionstester kan du ange om en omstart krävs för varje skript som läggs till.

![Välja funktionstest](Media/functionalreboot.png)

**F: Vilka Windows versioner stöder du?**

**S:** Vi har för närvarande Windows 10 för klienter, Windows Server 2016, Windows Server 2016 Core-version, Windows Server 2019 och Windows Server 2019 Core-versionen.

**F: Vad är skillnaden mellan säkerhetsuppdateringstester och funktionsuppdateringstester?**

**S:** För tester av säkerhetsuppdateringar **<ins></ins>** testar vi mot de månatliga säkerhetsuppdateringarna den Windows som fokuserar på att se till att våra användare alltid är skyddade och skyddade. För funktionsuppdateringstesterna testar vi mot de **<ins>bi-årliga</ins>** förhandsuppdateringarna som introducerar nya funktioner på Windows.

## <a name="debugging-options"></a>Felsökningsalternativ

**F: Får vi tillgång till virtuella maskiner vid fel? Vad delar Testbas?**

**S:** För att tjänsten ska vara kompatibel och förhandsuppdateringarna är säkra är det bara Microsoft som har åtkomst till de virtuella maskinerna. Kunderna kan dock visa testresultat och andra testmått på portalens instrumentpanel, inklusive krasch- och hang-signaler, tillförlitlighetsmått, minnes- och cpu-användning osv. Vi skapar och tillhandahåller även loggar av test som körs på instrumentpanelen för nedladdning och vidare analys. 

Vi kan också lägga till minnesdumpor för felsökning av kraschar vid behov.

**F: Om det finns problem under testningen, vilka är nästa steg för att lösa problemen?**

**S:** Test Base-teamet utför en inledande triageprocess för att fastställa orsaken till felet, och sedan, beroende på våra resultat, kommer vi att dirigeras till kunden eller interna team i Microsoft för felsökning. 

Vi samarbetar alltid tillsammans med våra kunder för att lösa eventuella problem. 

**F: Håller Microsoft kvar utgivningen av säkerhetskorrigeringen tills problemet är löst? Vilka alternativa upplösningar finns tillgängliga?**

**S:** Syftet med Test Base är att säkerställa att våra kunder inte har några problem. Vi arbetar hårt med programvaruleverantörer för att lösa eventuella problem före versionen, men om korrigeringen inte är möjlig har vi andra lösningar, till exempel shims och block.

## <a name="miscellaneous"></a>Diverse

**F: Hur fungerar tjänsten med en on-prem-server?**

**S:** Vi tillhandahåller för närvarande inte stöd för on-prem-servrar. Men om servern visar HTTP-slutpunkten kan vi ansluta till den via Internet.

**F: Vem värd för virtuella maskinerna?**

**S:** Microsoft tillhandahåller den virtuella maskinerna för den här tjänsten och tar i så fall hand om detta från kunden.

**F: Stöder den här tjänsten webb-, mobil- eller skrivbordsappar?**

**S:** För närvarande fokuserar vi på skrivbordsprogram, men vi planerar att introducera webbappar i framtiden, men vi stöder inte mobila program för närvarande.

**F: Vad är skillnaden mellan Testbas och TIDP?**

**S:** Den största skillnaden mellan TestBas och SÅP är att våra partner för in deras program på Test base Azure-miljön för validering körs mot förhandsuppdateringar i stället för att själva utföra testerna. 

Förutom förhandstestning av säkerhetsuppdateringar har vi stöd för förhandsuppdateringar av funktionsuppdateringar på vår plattform. Vi har många andra typer av uppdateringar och OS-tester på vår översikt.

**F: Är det någon kostnad kopplad till tjänsten?**

**S:** Testbastjänsten kommer att vara tillgänglig för användarna fram till den allmänna tillgängligheten (GA). Då kommer vi att presentera en kostnadsstruktur som ska gälla för alla kunder. 

**F: Hur kan jag ge feedback om Test Base?**

**S:** Om du vill dela med dig av din feedback om Test Base väljer **du feedbackikonen** längst ned till vänster i portalen. Ta med en skärmbild i ditt inskickade material så att Microsoft förstår din feedback bättre. 

Du kan också skicka produktförslag och hålla med andra idéer på <testbasepreview@microsoft.com> .
