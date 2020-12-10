---
title: Microsoft 365-välinformerad nätverks dirigering
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365-välinformerad nätverks dirigering
ms.openlocfilehash: 40b4345ca80c5e90a07583b83b82368d4a35535a
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611442"
---
# <a name="microsoft-365-informed-network-routing-preview"></a>Microsoft 365-välinformerad nätverks dirigering (för hands version)

Underordnad nätverks dirigering är en funktion som integrerar olika Microsoft 365-program med tredjeparts-specifika (SD-WAN) lösningar för att optimera och förbättra nätverks anslutningen till Microsofts tjänst slut punkter. Optimerad SD-WAN-anslutning kan leda till förbättrad användar upplevelse och prestanda.

>[!IMPORTANT]
>Microsoft 365 informerat nätverks dirigering är för närvarande i förhands granskning. Mer information om den här förhands granskningen inklusive vägledning för att få hjälp kan du läsa i [Microsoft 365 informerad nätverks dirigering](https://go.microsoft.com/fwlink/?linkid=2151565).

## <a name="overview"></a>Översikt

Informerad nätverks dirigering tillhandahåller en dubbelriktad data delnings kanal mellan Microsoft och din SD-WAN-lösning. För varje Office-plats och Internet-krets som du konfigurerar kan Microsoft regelbundet dela med dig av feedback med SD-WAN-lösningen på den valda Microsoft 365-program upplevelsen för nätverks trafik som är kopplad till varje specifik Internet krets. Genom att använda denna feedback kan du då och då vidta åtgärder för Smart återställning genom att routning Microsoft 365 program trafik via alternativa tillgängliga länkar. 

Kvaliteten på tjänstens försämring av sökvägen till en viss Internet krets såsom ökad svars tid eller hög paket förlust är svår att upptäcka fort löp ande. Dessa försämringar kan skada användar upplevelsen för program som Exchange Online, SharePoint, OneDrive och Microsoft Teams. Vanliga symptom är en långsam sökning av Exchange-innehåll, höga överförings tider när det interagerar med SharePoint-eller OneDrive-dokumentbibliotek eller dålig ljud kvalitet i Microsoft Teams.

Med funktionen för feedback och återställning i nätverk med välinformerad routning kan du upptäcka sådana problem dynamiskt i nära real tid och informera den distribuerade SD-WAN-lösningen för att utföra automatiska återställnings åtgärder.

Data delnings kanalen används också för att regelbundet få optisk data trafik från SD-WAN-lösningen, inklusive konfigurations information och användnings statistik som är kopplad till enheten och anslutna kretsar. Ingen personlig information samlas in eller lagras. Alla insamlade uppgifter aggregeras till Office-platser och anslutna Internet kretsar. Den här informationen kan hjälpa Microsoft att effektivt lösa rapporterade problem med användning av Microsoft 365-tjänster och-program.

>[!NOTE]
>Microsoft 365 informerat nätverks dirigering stöder klient organisationer i WW kommersiellt moln men inte GCC medel för måttliga, GCC hög, DoD, Tyskland och Kina.

## <a name="requirements"></a>Krav

### <a name="integrated-sd-wan-solutions"></a>Integrerade SD-WAN-lösningar

Microsoft samarbetar med olika partners för att möjliggöra integrering med Microsoft 365-välinformerade nätverks dirigering. För närvarande aktiverade lösningar:

| Enhets tillverkare | Lösningens namn | Minsta version |
| --- | --- | --- |
| Cisco | [IOS-XO SD – WAN](https://go.microsoft.com/fwlink/?linkid=2151460) | 20.4/17.4 |

### <a name="network-topology"></a>Nätverkstopologi

Med Inlämnad nätverks dirigering identifieras trafik som är kopplad till en viss plats och Internet-kretsen baserat på den offentliga IP-adressen som används för att skicka nätverks trafik till Microsoft. 

Om det inte finns minst en nätverks krets som ger direkt Internet åtkomst på en filial plats kanske inte nätverkets informerade routning ger signifikanta priser.

### <a name="application-usage"></a>Program användning

Program miljö data samlas in genom användning av Microsoft Outlook på enheter med Windows, teams, SharePoint och OneDrive. Annan program trafik beaktas inte vid utvärdering av hälso tillståndet hos en nätverks krets.

## <a name="enabling-informed-network-routing"></a>Aktivera välinformerad nätverks dirigering

För att aktivera informerad nätverks dirigering krävs flera steg som måste utföras i konfigurations gränssnittet för din SD-WAN-lösning. Läs mer om hur du kan använda din lösning för att aktivera nätverk med välinformerad routning i SD-WAN-lösningen innan du fortsätter med konfigurationen i administrations centret för Microsoft 365.

När du är redo att aktivera välinformerad nätverks dirigering i Microsoft 365 Admin Center kontrollerar du att du har nödvändig global administratörs behörighet.

>[!IMPORTANT]
>För att kunna tillhandahålla de behörigheter som krävs för den valda SD-WAN-lösningen för att få åtkomst till den välgrundade data delnings kanalen för nätverks dirigering måste du utföra följande steg som global administratör.


### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Steg 1: öppna konfigurations alternativ för SD-WAN-lösning

I [administrations centret för Microsoft 365](https://admin.microsoft.com/)väljer du **Health > nätverks anslutning** i det vänstra navigerings fönstret.

Den här delen av administrations centret tillhandahåller sammansatta nätverks anslutnings mått för din organisation och vägledning om hur du kan förbättra anslutningen. Se [nätverks anslutningar i Microsoft 365 Admin Center (för hands version)](office-365-network-mac-perf-overview.md) om du vill ha mer information om de här funktionerna i administrations centret.

Välj **inställningar > SD-WAN-lösning** för att öppna den informerade konfigurations fönstret för nätverks dirigering. De andra alternativen som visas under **Inställningar** är tillämpliga för nätverks anslutnings vägledningen i administrations centret och är inte nödvändigt för att aktivera inskriven nätverks dirigering.

I fönstret konfiguration väljer **du Lägg till din SD-WAN-lösning (för hands version)**.

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a>Steg 2: Välj din SD-WAN-lösning och data lagrings plats

I list rutorna väljer du den SD-WAN-lösning som du har distribuerat och den plats där du vill ha de data som är kopplade till nätverksansluten routning. Mer information finns i avsnittet [data lagring](#data-storage) .

Välj **Nästa**.

### <a name="step-3-accept-terms-for-sharing-of-data"></a>Steg 3: acceptera villkor för att dela data

Läs och bekräfta noggrant de angivna villkoren för att dela data mellan Microsoft och din valda SD-WAN-lösning och markera sedan kryss rutan.

Välj **Nästa**.

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a>Steg 4: bevilja behörigheter för SD-WAN-lösningen

I det här steget initieras en begäran om behörighet med Azure Active Directory (Azure AD). Du kommer att tillfrågas om behörigheter på klient organisations nivå som tillåter att din valda SD-WAN-lösning får till gång till det underbyggda nätverks lagrings utrymmet och tjänst hälso informationen som är associerad med din klient organisation. Den här åtgärden kräver globala administratörs behörigheter.

Välj länken **ge behörighet till det här programmet** och följ Azure AD-begäranden.

När du har slutfört behörighets tilldelningen väljer du **Nästa**.

### <a name="step-5-confirm-your-configuration-settings"></a>Steg 5: bekräfta dina konfigurations inställningar

Det sista steget i att aktivera nätverkets informerade routning för din klient organisation är en bekräftelse sida som visar de inställningar du har angett. 

Uppdelad nätverks dirigering är nu aktive rad för din klient organisation.

Välj **klar** och stäng sedan konfigurations fönstret för SD-WAN-lösning.

## <a name="configuring-network-informed-routing"></a>Konfigurera nätverksansluten routning

Du kommer att utföra en mycket av konfigurationen för välinformerad nätverks dirigering i din SD-WAN-lösning, till exempel hur du konfigurerar hur din trafik ska routas under normala omständigheter och vilka alternativa sökvägar som ska användas om problem upptäcks. Mer information om de här konfigurations stegen finns i leverantören för SD-WAN-lösning.

Varje Office-plats måste konfigureras i Microsoft 365 Admin Center så att inringda nätverks dirigeringar kan identifiera trafik som är kopplad till de nätverks kretsar som ger anslutning till dessa platser.

Office-platser kan identifieras automatiskt som en del av Microsofts löpande samling av Nätverksdiagnostik. Därför kan vissa platser vara ifyllda i administrations centret för din klient organisation. 

Om dessa platser är korrekta behöver du bara aktivera den informerade nätverks Dirigerings funktionen för varje plats och konfigurera Internet kretsar och deras offentliga IP-adresser. 

Om de automatiskt upptäckta platserna inte är korrekta, eller om det inte finns någon plats ifyllt i klient organisationen, måste du lägga till eller redigera platserna manuellt för att visa en korrekt topologi i organisationen.

### <a name="updating-locations"></a>Uppdatera platser

Platser för klient organisationen finns på fliken **platser** . Platser kan redige ras direkt i listan eller uppdateras med en CSV-fil.

Kontrol lera att varje Office-plats där du vill aktivera välinformerad nätverks dirigering finns i den här listan.

>[!NOTE]
>Kolumnerna i **plats** listan för insamlade och andra utvärderings uppgifter är inte relaterade till den informerade nätverks dirigeringen.

### <a name="enabling-a-location-for-informed-network-routing"></a>Aktivera en plats för välinformerad nätverks dirigering

1. I listan **platser** väljer du **Redigera** från menyn snabb åtgärder för att öppna fönstret plats konfiguration.

2. Välj **Använd Microsoft 365-välinformerad nätverks dirigering på den här platsen**.

3. Lägg till alla nätverks kretsar som ger Internet anslutningen till den här platsen i det **här avsnittet IP-adressintervall på den här platsen** . Kontrol lera att varje krets är kopplad till de unika offentliga IP-adressundernät som representerar nätverks trafiken.

4. Spara ändringarna genom att välja **Spara** .

## <a name="disabling-network-informed-routing"></a>Inaktivera informerad routning av nätverk

Den informerade nätverks dirigeringen kan vara inaktive rad för hela klient organisationen genom att återställa inställningarna för SD-WAN-lösningen. Det här kommer att stoppa all data behandling i Microsoft 365, men du bör också inaktivera upparbetad routning för nätverk i administrations centret.

### <a name="step-1-open-sd-wan-solution-configuration-options"></a>Steg 1: öppna konfigurations alternativ för SD-WAN-lösning

I [administrations centret för Microsoft 365](https://admin.microsoft.com/) väljer du **hälso > nätverks anslutning** i det vänstra navigerings fönstret.

Välj **inställningar > SD-WAN-lösning** för att öppna den informerade konfigurations fönstret för nätverks dirigering.

I fönstret konfiguration visas en sammanfattning av din konfigurerade SD-WAN-lösning.

### <a name="step-2-reset-your-configuration"></a>Steg 2: återställa din konfiguration

I fönstret konfiguration väljer **du Återställ dina inställningar för SD-WAN-lösning**.

Dina inställningar har nu återställts och ett underskrivet nätverks dirigering har inaktiverats. Du kan återaktivera den när som helst genom att följa anvisningarna i [Aktivera välinformerad nätverks dirigering](#enabling-informed-network-routing).

## <a name="data-storage"></a>Data lagring

Data som utbyts mellan Microsoft och leverantören för SD-WAN-lösning lagras på den data lagrings plats som marker ATS under den första inaktiverade nätverks informerade routning. Alternativen för data lagrings plats representerar geografiska områden som innehåller Microsoft Azure-regioner där data lagras.

>[!NOTE]
>Under för hands versions fasen är den enda tillgängliga data lagrings platsen **Nord Amerika**. Ytterligare data lagrings platser blir tillgängliga innan den allmänna tillgängligheten för utskrivbar nätverks dirigering.

Data behålls på den här platsen i upp till 30 dagar. När den är inaktive rad tas alla återstående data bort inom det här 30-dagars periodiska fönstret.

## <a name="related-topics"></a>Relaterade ämnen

[Nätverks anslutning i Microsoft 365 Admin Center (för hands version)](office-365-network-mac-perf-overview.md)

[Microsoft 365 nätverks anslutningar (för hands version)](office-365-network-mac-location-services.md)
