---
title: Hantera Microsoft Defender för slutpunktsaviseringar
description: Ändra status för aviseringar, skapa regler för att dölja aviseringar, skicka kommentarer och granska ändringshistorik för enskilda aviseringar med hjälp av menyn Hantera avisering.
keywords: hantera aviseringar, hantera, aviseringar, status, ny, pågående, löst, lösa aviseringar, dölja, stänga av, regler, sammanhang, historik, kommentarer, ändringar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187007"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a>Hantera Microsoft Defender för slutpunktsaviseringar

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

Defender för Endpoint meddelar dig om möjliga skadliga händelser, attribut och sammanhangsberoende information via aviseringar. En sammanfattning av nya aviseringar visas i instrumentpanelen **för säkerhetsåtgärder,** och du kan komma åt alla aviseringar i **kön Aviseringar.**

Du kan hantera aviseringar genom att välja en avisering **i kön** Aviseringar eller **fliken** Aviseringar på sidan Enhet för en enskild enhet.

Om du väljer en avisering på någon av dessa platser visas **fönstret Aviseringshantering**.

![Bild på fönstret för aviseringshantering och aviseringskön](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a>Länka till ett annat incident
Du kan skapa en ny händelse utifrån aviseringen eller länka till en befintlig händelse. 

## <a name="assign-alerts"></a>Tilldela aviseringar
Om en avisering ännu inte har tilldelats kan du välja **Tilldela till mig och** tilldela aviseringen till dig själv.


## <a name="suppress-alerts"></a>Utelämna aviseringar
Det kan finnas scenarier där du behöver hindra aviseringar från att visas i Microsoft Defender Säkerhetscenter. Med Defender för slutpunkt kan du skapa regler för särskilda varningar som är kända för att vara obesvarade, till exempel kända verktyg och processer i organisationen.

Regler som måste skapas utifrån en befintlig avisering. De kan inaktiveras och återaktiveras om det behövs.

När en regel för regel skapas börjar den gälla från och med då regeln skapas. Regeln påverkar inte befintliga aviseringar som redan finns i kön, innan regeln skapas. Regeln kommer bara att tillämpas på aviseringar som uppfyller villkoren efter att regeln har skapats.

Det finns två sammanhang för en regel för kontext som du kan välja bland:

- **Varna inte på den här enheten**
- **Hindra aviseringar i min organisation**

Med kontexten för regeln kan du anpassa vad som visas i portalen och se till att bara faktiska säkerhetsvarningar visas i portalen.

Du kan använda exemplen i följande tabell för att hjälpa dig att välja kontext för en regel:

| **Sammanhang**                           | **Definition**                                                                                                                                              | **Exempelscenarier**                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Varna inte på den här enheten**    | Aviseringar med samma aviseringsrubrik och endast på den specifika enheten ignoreras. <br /><br />Alla andra aviseringar på enheten ignoreras inte. | <ul><li>En säkerhetsundersökning undersöker ett skadligt skript som har använts för att attacka andra enheter i organisationen.</li><li>En utvecklare skapar regelbundet PowerShell-skript åt sitt team.</li></ul> |
| **Hindra aviseringar i min organisation** | Aviseringar med samma aviseringstitel på alla enheter kommer att döljas.                                                                                         | <ul><li>Administrativa administratörsverktyg används av alla i organisationen.</li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a>Ignorera en avisering och skapa en ny regel för att ignorera regeln:
Skapa anpassade regler för att styra när aviseringar utelämnas eller matchas. Du kan styra kontexten för när en avisering utelämnas genom att ange aviseringsrubrik, Indikatorn på kompromettering och villkoren. När du har specificerat kontexten kan du konfigurera åtgärden och omfattningen för aviseringen. 

1. Välj den avisering du vill dölja. Detta visar fönstret **Aviseringshantering.**

2.  Välj **Skapa en regel för regel**.

    Du kan skapa ett sådana villkor med hjälp av de här attributen. En OCH-operator tillämpas mellan varje villkor, så att fall endast inträffar om alla villkor uppfylls.
    
    * Fil-SHA1
    * Filnamn – jokertecken stöds
    * Mappsökväg – jokertecken stöds
    * IP-adress
    * URL – jokertecken stöds
    * Kommandorad – jokertecken som stöds

3. Välj **utlösande IOC.**
    
4. Ange åtgärden och omfattningen för aviseringen. <br>
   Du kan automatiskt lösa en avisering eller dölja den från portalen. Aviseringar som matchas automatiskt visas i den lösta delen av aviseringskön, aviseringssidan och enhetens tidslinje och visas som lösta i Defender för slutpunkts-API:er. <br><br> Aviseringar som markeras som dolda döljs från hela systemet, både på enhetens associerade aviseringar och från instrumentpanelen och strömmas inte över Defender för slutpunkts-API:er.


5. Ange ett regelnamn och en kommentar.

6. Klicka på **Spara**.

#### <a name="view-the-list-of-suppression-rules"></a>Visa listan över regler för regler

1. I navigeringsfönstret väljer du **Inställningar**  >  **aviseringsvarning**.

2. Listan med regelregler visar alla regler som användare i organisationen har skapat.

Mer information om hur du hanterar regelsamlingsregler finns i [Hantera regelhantering](manage-suppression-rules.md)

## <a name="change-the-status-of-an-alert"></a>Ändra status för en avisering

Du kan kategorisera aviseringar (som **Ny,** **Pågår** eller **Löst**) genom att ändra deras status allt eftersom din undersökning fortskrider. På så sätt kan du organisera och hantera hur din grupp kan svara på aviseringar.

En gruppledare kan till exempel granska alla **nya** aviseringar och välja att tilldela dem till kön **Pågår** för ytterligare analys.

Gruppledaren kan också tilldela aviseringen  till kön Löst om de vet att aviseringen är från en enhet som är irrelevant (till exempel en som tillhör en säkerhetsadministratör) eller tas itu med via en tidigare avisering.



## <a name="alert-classification"></a>Aviseringsklassificering
Du kan välja att inte ange en klassificering eller om en avisering är en verklig avisering eller en falsk avisering. Det är viktigt att ange klassificeringen sant positiv/falsk positiv. Den här klassificeringen används för att övervaka aviseringskvaliteten och göra aviseringarna mer exakta. Fältet "determination" definierar ytterligare återgivning för en "sant positiv" klassificering. 

## <a name="add-comments-and-view-the-history-of-an-alert"></a>Lägga till kommentarer och visa historiken för en avisering
Du kan lägga till kommentarer och visa historiska händelser om en avisering om du vill se tidigare ändringar i aviseringen.

När en ändring eller kommentar görs i en avisering registreras den i **avsnittet Kommentarer och historik.**

Tillagda kommentarer visas direkt i fönstret.


## <a name="related-topics"></a>Relaterade ämnen
- [Hantera undertryckande regler](manage-suppression-rules.md)
- [Visa och ordna kön Microsoft Defender för slutpunktsaviseringar](alerts-queue.md)
- [Undersöka Microsoft Defender för slutpunktsaviseringar](investigate-alerts.md)
- [Undersöka en fil som är kopplad till en Microsoft Defender för slutpunktsavisering](investigate-files.md)
- [Undersöka enheter i listan Microsoft Defender för slutpunktsenheter](investigate-machines.md)
- [Undersöka en IP-adress som är kopplad till en Microsoft Defender för Slutpunktsavisering](investigate-ip.md)
- [Undersöka en domän som är kopplad till en Microsoft Defender för slutpunktsavisering](investigate-domain.md)
- [Undersöka ett användarkonto i Microsoft Defender för Endpoint](investigate-user.md)
