---
title: Microsoft Managed Station ära datorer och övervakning
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8355b1609746abee12e4ca02942a567fec940623
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846222"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft Managed Station ära datorer och övervakning

<!-- Operations and monitoring: -->


## <a name="change-management"></a>Ändrings hantering

I ett tjänst erbjudande flyttas ansvaret för sådant som maskin varu underhåll och säkerhets uppdateringar till tjänste leverantören (Microsoft) i stället för kunden (du). Men du måste ändå kontrol lera att tredje part och anpassade program fortsätter att fungera som förväntat när uppdateringar distribueras.

För lokala produkter tar din organisation allt ansvar för att hantera ändringar.

### <a name="balance-of-responsibility"></a>Ansvar

Ligger | Microsoft Managed Desktop service | Microsoft 365-klientprogram | Lokala klienter och servrar | tredje part och anpassad program vara
----- | ----- | ----- | ----- | -----
Nya funktioner | Microsoft | Microsoft | Varken | Support
Testa nya funktioner för kvalitets kontroll |  Microsoft | Microsoft | Varken | Support
Kommunicera om nya funktioner | Varken | Varken | Varken | Support
Integrera anpassad program vara | Varken | Varken | Support | Support
Tillämpa säkerhets uppdateringar | Microsoft | Microsoft | Support | Support
Underhåll systemprogram | Microsoft | Microsoft | Support | Support
Paket för distribution | Microsoft | Microsoft | Support | Support


### <a name="change-process-overview"></a>Översikt över ändrings processen

Här är en sammanfattning av hur ändrings processen delas mellan Microsoft och kunderna. 



<table>
<tr><th></th><th><p>Microsoft-roll:</p></th><th><p>Kunds roll:</p></th></tr>
<tr><td>Före en ändring</td><td><ul><li>Ange förväntningar för service ändringarna.</li><li>Meddela kunderna fem dagar i förväg för ändringar som kräver administratörs åtgärd.</li><li>För nöd situations ändringar, Använd en åtgärd innan du meddelas.</li></ul></td><td><ul><li>Förstå vad du kan förvänta dig för ändringar och kommunikation.</li><li>Läs Microsoft Managed Desktop meddelande Center regelbundet.</li><li>Granska och uppdatera interna processer för ändrings hantering.</li><li>Förstå och kontrol lera efterlevnaden av Microsofts hanterade Skriv bords krav. </li><li>Bekräfta och godkänn när det behövs.</li></ul></td></tr><tr><td>Under en ändring</td><td><ul><li>Släpp och distribuera månatliga säkerhets-och icke-säkerhetsuppdateringar för Windows 10-och Office 365-klienter.</li><li>Övervaka data signaler och support köer för påverkan.</li></ul></td><td><ul><li>Kontrol lera det Microsoft hanterade Skriv bords meddelande Center och granska eventuell ytterligare information.</li><li>   Vidta alla nödvändiga åtgärder, om tillämpligt och testa program.</li><li>Om det finns ett scenario för att ta bort/åtgärda kan du skapa en supportbegäran.</li></ul></td></tr><tr><td>Efter en ändring</td><td><ul><li>Samla in feedback från kunder för att förbättra distributionen av framtida ändringar.</li><li>Övervaka data signaler och support köer för påverkan.</li></ul></td><td><ul><li>Arbeta med personer i organisationen för att välja ändringen.</li><li>   Granska ändringar och antagande hanterings processer för möjligheter att bli effektiv.</li><li>Ge allmän feedback och specifik feedback i verktyget för administrations feedback.</li><li>Träna användare att erbjuda programspecifik feedback med hjälp av Windows Feedback Hub och knappen leende i Office-appar.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>Ändra typer

Det finns flera typer av ändringar som görs i tjänsten regelbundet. Kommunikations kanalen för dessa ändringar och de åtgärder som kunderna ansvarar för varierar.

Alla ändringar har inte samma betydelse för användarna eller kräver en åtgärd. Vissa är planerade och vissa oplanerade av sina natur (uppdateringar och säkerhets uppdateringar som inte är säkerhetsrelaterade) planeras vanligt vis. Beroende på vilken typ av ändring det gäller kan kommunikations kanalen variera. I följande tabell visas de typer av ändringar du kan förvänta dig för Microsoft Managed Desktop-tjänsten.

|   | Användas |   Uppdateringar som inte är säkerhetsrelaterade |  Säkerhet
--- | --- | --- | ---
**Ändrings typ** | -Funktions uppdateringar<br>-Nya funktioner eller program<br>-Föråldrade funktioner | Klient snabb korrigeringar för problem | Säkerhets korrigeringar
**Förhands meddelande** | 5 dagars meddelande för ändringar som kräver en åtgärd |    Nej, de är inkluderade i månads versionen   | Nej, de är inkluderade i månads versionen 
**Kommunikations kanal** | – Meddelande Center<br>-E-postavisering | – Meddelande Center<br>-E-postavisering | – Meddelande Center<br>-E-postavisering
**Kräver global administratörs åtgärd** | Hända |  Sällsynta |    Sällsynta 
**Typ av åtgärd** | Ändra inställningar | Informera användarna om ändringar | Ändra administratörs inställningar     
**Kräver testning** | Kontrol lera affärs program, inklusive Remote Access Services |  Ibland-testa korrigeringen mot processer eller anpassningar |   Sällsynta 
**Exempel på ändring** | -Funktions uppdateringar: IT-administratörs portalen förenklade support ärenden och översyn<br>-Nya funktioner eller program: Semi-Annual version av en funktions uppdatering för Windows 10 | Snabb korrigeringar baserade på rapporterade program för rapporter |  


## <a name="standard-operating-procedures"></a>Vanliga rutiner

Microsoft Managed Desktop-tjänsten implementeras och drivs av Microsoft i Microsoft Cloud-instanser där du kan utföra andra administrativa aktiviteter. Microsoft är endast ansvarigt för Microsoft Managed Desktop-specifik installation, konfiguration och användning. 

För lokala produkter tar din organisation över ansvaret för att hantera inställningar och konfiguration och drifts aktiviteter.

Klasser |    Microsoft kommer | Kund kommer
--- | --- | ---
Nätverk (proxy, paket kontroll, VPN)  | Råd och planera med kunderna för att minimera riskerna för företags användare. | -Skapa en support förfrågan som begär information om en planerad konfigurations ändring, inklusive konfigurations information, omfattning, tids linje och annan relevant information som Microsoft kan granska.<br>-Använd en ändring när Microsoft Managed Station ära datorer har bedömt och tillrådligt.
Tjänst konton |-Implementera och hantera autentiseringsuppgifterna säkert.<br> -Kommunicera obehörig åtkomst eller Använd dessa autentiseringsuppgifter för säkerhets åtgärds gruppen. | -Skapa en support förfrågan som begär information om en planerad konfigurations ändring, inklusive konfigurations information, omfattning, tids linje och annan relevant information som Microsoft kan granska.<br>-Använd en ändring när Microsoft Managed Station ära datorer har bedömt och tillrådligt.<br>-Inte tilldela princip, multifaktorautentisering, villkorlig åtkomst eller program distribution till Microsoft Managed Desktop Service-konton.<br>-Inte Återställ lösen ordet eller Använd autentiseringsuppgifterna.<br>-Öppna en SEV C-supportbegäran till Microsoft Managed Desktop-operationer om misstänkt aktivitet observeras i Intune-eller Azure audit-loggar, relaterat till dessa tjänst konton.
Enhets grupper | -Implementera och hantera medlemskap i enheter inom Microsoft Managed Desktop Groups.<br>-Använd Microsoft Managed Desktop Groups för att hantera tilldelning och utgivning av konfiguration och uppdateringar av enheter. | -Skapa en support förfrågan som begär information om en planerad konfigurations ändring, inklusive konfigurations information, omfattning, tids linje och annan relevant information som Microsoft kan granska.<br>-Använd en ändring när Microsoft Managed Station ära datorer har bedömt och tillrådligt.<br>-Ändra inte medlemskap för en Microsoft-hanterad stationär dator grupp.<br>-Använd bara grupperna för att tilldela företags certifikat för tjänster som VPN, Windows Hello för företag eller e-postkryptering eller för företags Wi-Fi profil.<br>-Där Co-Management finns, undanta alla Microsoft Managed Station ära datorer när du distribuerar Configuration Manager-klienten.
Principerna |  -Implementera och hantera de Microsoft Managed Desktop-principer som styr konfigurations tillståndet för enheter inom tjänst.<br>-Distribuera uppdateringar, till princip eller fönster, inkrementellt med enhets grupper.<br> -Uteslut uttryckligen mål grupper som inte hanteras med Microsoft. | -Skapa en support förfrågan som begär information om en planerad konfigurations ändring, inklusive konfigurations information, omfattning, tids linje och annan relevant information som Microsoft kan granska.<br>-Använd en ändring när Microsoft Managed Station ära datorer har bedömt och tillrådligt.<br>-Inte redigera eller tilldela Microsoft Managed Desktop-principer till enheter eller användare som inte hanteras av Microsoft Managed Desktop-tjänsten.
Microsoft Defender för slut punkt | Övervaka och undersöka enheter inom omfattningen för Microsoft Managed Desktop-tjänsten. | -Skapa en support förfrågan som begär information om en planerad konfigurations ändring, inklusive konfigurations information, omfattning, tids linje och annan relevant information som Microsoft kan granska.<br>-Använd en ändring när Microsoft Managed Station ära datorer har bedömt och tillrådligt
Microsoft Store för företag |  Konfigurera och underhåll Windows autopilot-profilen för Microsoft Managed Desktop-tjänsten. | -Skapa en support förfrågan som begär information om en planerad konfigurations ändring, inklusive konfigurations information, omfattning, tids linje och annan relevant information som Microsoft kan granska.<br>-Använd en ändring när Microsoft Managed Station ära datorer har bedömt och tillrådligt.<br>-Inte ändra konfigurationen för Microsoft Managed Desktop Windows autopilot-profilen eller lägga till/ta bort tilldelade enheter.
Exportcertifikat | | -Skapa en supportbegäran 60 dagar innan ett certifikat går ut, begär information för en planerad konfigurations ändring, inklusive konfigurations information, omfattning, tids linje och annan relevant information som Microsoft kan granska.<br>-Använd en ändring när Microsoft Managed Station ära datorer har bedömt och tillrådligt.<br>-Uppdatera alla certifikat som krävs för att konfigurera certifikat profiler, VPN-profiler och Wi-Fi profiler.




## <a name="device-wipe-with-factory-reset"></a>Enhets rensning med fabriks återställning

Microsoft Managed Desktop Operations team kan utföra en fabriks återställning av enheter som registrerats i tjänsten när det behövs. Det här är praktiskt om du vill ge en enhet till en annan anställd eller om en anställd lämnar företaget. 

Det finns några krav:

- Den globala administratören måste skicka en tjänst förfrågan.
- Ta med enhetens dator namn i begäran.
- Användar kontot måste vara i Azure AD innan vi återställer enheten.

Hanterat Skriv bords grupp gör följande:

- Sök efter enhetens namn i Intune
- Skicka kommandot Factory-Återställ till enheten

>[!NOTE]
>Ta inte bort användar kontot från Azure AD innan enheten återställs. Om användaren inte är i Azure AD kan Intune inte skicka kommandot Factory-reset till enheten. 

Enheten startas om i "slut på kartong", och alla förinstallerade program och inställningar tillämpas igen. Användaren av enheten måste ange den första installationen. 

När enheten har återställts kan du ge den till en annan person i organisationen. Ingen av de föregående användarens data eller företags data finns på enheten. Nästa användare kommer att gå igenom samma process som föregående person använde med en ny Microsoft-hanterad stationär enhet.

BitLocker är en nyckel komponent med data säkerhet i den här processen. Med BitLocker-kryptering på Microsoft Managed Station ära enheter förblir data på enheten säkra även efter det att enheten har återställts. Alla data på enheten är inte tillgängliga för nästa användare av enheten. Mer information finns i [Översikt över BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).

Mer information finns i [återställa en enhet](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device). 