---
title: Microsoft 365 Säkerhetscenter översikt
description: Fördelar i Microsoft 365 säkerhetscenter, att kombinera Microsoft Defender för Office 365 (MDO) och Microsoft Defender för slutpunkt (MDE) med Microsoft Defender för identitet (MDI) och Microsoft Cloud App Security (MCAS). I den här artikeln beskrivs utvecklingen av Säkerhetscenter för Microsoft 365 för administratörer.
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, identiteter, data, enheter, appar
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 89e72d703bd70647d6c2b00732315b8e5f015cc7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167220"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Översikt över det enhetliga säkerhetscentret i Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gäller för:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender för Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en labbmiljö](https://aka.ms/mtp-trial-lab) eller köra [pilotprojektet i produktion.](https://aka.ms/m365d-pilotplaybook)

Det förbättrade säkerhetscentret för **Microsoft 365** () kombinerar skydd, identifiering, undersökning och svar på e-post, samarbete, identitet och enhetshot [https://security.microsoft.com](https://security.microsoft.com) i en central portal.    

Microsoft 365 säkerhetscenter samlar funktioner från befintliga Microsoft-säkerhetsportaler som Microsoft Defender Säkerhetscenter och Office 365 Säkerhets- & efterlevnadscenter. Säkerhetscenter framhäver snabb åtkomst till information, enklare layouter och att sammanföra relaterad information för enklare användning. I det här mitten finns:

- **[Microsoft Defender för Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender för Office 365 hjälper organisationer att skydda sitt företag med en uppsättning funktioner för skydd, identifiering, undersökning och eftersökning för att skydda e-post och Office 365-resurser.
- **[Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** ger skydd mot intrång, identifiering efter intrång, automatisk undersökning och svar för enheter i din organisation.
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** är en del av Microsofts XDR-lösning *(Extended Detection and Response)* som utnyttjar Microsoft 365-säkerhetsportföljen för att automatiskt analysera hotdata över domäner och skapa en bild av ett angrepp på en enskild instrumentpanel.

Om du behöver information om vad som har ändrats från Säkerhets- och efterlevnadscenter för Office 365 & eller Microsoft Defender Säkerhetscenter kan du läsa:

- [Defender för Office 365 i Microsoft 365 Säkerhetscenter](microsoft-365-security-center-mdo.md)
- [Defender för Endpoint i Microsoft 365 Säkerhetscenter](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Vad du kan förvänta dig

Allt säkerhetsinnehåll som du använder i Säkerhets- och efterlevnadscenter för Office 365 (protection.office.com) och Microsoft Defender säkerhetscenter (securitycenter.microsoft.com) finns nu i Säkerhetscenter för *Microsoft 365.*

Microsoft 365 säkerhetscenter hjälper säkerhetsteam att undersöka och reagera på attacker genom att använda signaler från olika arbetsbelastningar i en enda enhetlig upplevelse:

- Incidenter & aviseringar
- Jägning
- Åtgärdscenter
- Analys av hot

Microsoft 365 Säkerhetscenter framhäver *enhet, tydlighet* och gemensamma mål när Microsoft Defender för Office 365 och Microsoft Defender för Slutpunkt sammanfogas. Kopplingen baseras på de prioriteringar som anges nedan och skapade utan att ha tagit över de funktioner som respektive säkerhetssvit hade i kombination:

- vanliga byggblock
- vanlig terminologi
- vanliga enheter
- funktionsparitet med andra arbetsbelastningar

## <a name="unified-investigations"></a>Enhetliga undersökningar

Genom att effektivisera säkerhetscenter skapas ett enda fönster för att undersöka alla incidenter i en Microsoft 365-organisation. Ett primärt exempel är **noden Incidenter** i snabbstarten för Säkerhetscenter i Microsoft 365.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Sidan Incidenter i MDO.":::

Om du till exempel dubbelklickar på  ett incidentnamn med hög allvarlighetsgrad kommer du till en sida som visar fördelen med konvergerande center.

![Incident i flera steg som innefattar eskalering av behörigheter på flera slutpunkter, som visar se 16 påverkade enheter och 9 påverkade användare.](../../media/converged-incident-info-3.png)

> [!TIP]
> Fliken Konvergerade **användare** är en bra plats att påbörja dina förfrågningar på. Den här sidan visar information för användare från konvergerade arbetsbelastningar (Microsoft Defender för slutpunkt, Microsoft Defender för identitet och MCAS om du använder det) och ett antal källor, till exempel lokal Active Directory, Azure Active Directory, synkroniserade användare, lokala användare och tredjepartsanvändare. Läs mer om [den nya användarupplevelsen.](investigate-users.md)

Incidentinformation visar användar-/identitetsspecifik information och enheter för at-risk, bredvid berörda postlådor. Den relaterar även eventuell **undersökningsinformation och** insamlade **bevis.** Det gör det enklare för administratörer och säkerhetsåtgärdsteam att pivotera från en högriskavisering till berörda användare och postlådor. Om vi tittar **på incidentflikarna** längst upp på den här sidan finns det andra viktiga säkerhetspivoter tillgängliga från den här platsen.

> [!IMPORTANT]
> Längst upp på sidan för en specifik händelse visas flikarna **Sammanfattning,** **Aviseringar,**  **Enheter,** **Användare,** Postlådor, Undersökningar och **Bevis.**

Om **du** väljer Undersökningar öppnas en sida med en bild av den analys som sker och en lista över en status (t.ex. väntar på **godkännande)** för åtgärd. Ta dig tid att välja specifika incidenter i din miljö, gå in på de här flikarna och öva på att skapa en profil för olika typer av hot. Då är det bra om du känner igen dig i alla senare undersökningar.

## <a name="improved-processes"></a>Förbättrade processer

Vanliga kontroller och innehåll visas antingen på samma plats eller komprimeras till en feed med data som gör det lättare att hitta. Till exempel enhetliga inställningar.

### <a name="unified-settings"></a>Enhetliga inställningar

![klickade på "Roller" och öppnade sidan Inställningar, som innehåller Allmänna inställningar, Behörigheter, API:er och regler. Öppna Behörigheter och sedan Roller. Visar alla roller](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Behörigheter & roller

![Sidan & Roller som visar slutpunktsroller & grupper, roller och enhetsgrupper.](../../media/converged-roles-5.png)

 Access säkerhetscentret i Microsoft 365 är konfigurerat med globala azure Active Directory-roller eller med anpassade roller. Information om Defender för slutpunkt finns [i Tilldela användaråtkomst till Microsoft Defender Säkerhetscenter.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access) Mer information om Defender för Office 365 finns i Behörigheter i Efterlevnadscenter för [Microsoft 365 och Säkerhetscenter för Microsoft 365.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Läs mer om hur du [hanterar åtkomst till Microsoft 365 Defender](mtp-permissions.md)
- Läs mer om hur du [skapar anpassade roller](custom-roles.md) i Microsoft 365 säkerhetscenter

### <a name="integrated-reports"></a>Integrerade rapporter

Rapporter är även enhetliga i Säkerhetscenter för Microsoft 365. Administratörer kan börja med en allmän säkerhetsrapport och förgrena till specifika rapporter om slutpunkter, skicka e-& samarbete. Länkarna här genereras dynamiskt utifrån konfigurationen av arbetsbelastningen.

### <a name="quickly-view-your-microsoft-365-environment"></a>Visa din Microsoft 365-miljö snabbt

På **startsidan** visas många av de vanliga korten som säkerhetsteam behöver. Sammansättning av kort och data är beroende av användarrollen. Eftersom Säkerhetscenter i Microsoft 365 använder rollbaserad åtkomstkontroll kommer olika roller att se kort som är mer meningsfulla för de dagliga jobben.  

Med den här snabb översiktsinformationen kan du hålla dig informerad om de senaste aktiviteterna i organisationen. Säkerhetscentret i Microsoft 365 samlar signaler från olika källor för att presentera en vy över Microsoft 365-miljön.

Korten delas in i följande kategorier:

- **Identiteter**– Övervaka identiteterna i organisationen och håll reda på misstänkta eller riskfyllda beteenden. [Läs mer om identitetsskydd.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)
- **Data** – Hjälper till att spåra användaraktivitet som kan leda till obehörig information.
- **Enheter** – få uppdaterad information om aviseringar, intrångsaktivitet och andra hot på dina enheter.
- **Appar** – få insyn i hur molnappar används i organisationen. [Läs mer om Cloud App Security-identifierade appar.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>Hotanalyser med bättre datatäckning
Spåra och svara på nya hot med följande integrerade miljö för hotanalyser i Microsoft 365 Defender:

- Bättre datatäckning mellan Microsoft Defender för Endpoint och Microsoft Defender för Office 365, vilket gör kombinerad incidenthantering, automatisk undersökning, åtgärd och proaktiv eller reaktiv hotande på hela domänen möjligt. 
- E-postrelaterade identifieringar och åtgärder från Microsoft Defender för Office 365, utöver de slutpunktsdata som redan är tillgängliga från Microsoft Defender för Slutpunkt.
- En vy över hotrelaterade incidenter som sammanställer varningar i hela attackberättelser från Microsoft Defender för Endpoint och Microsoft Defender för Office 365 för att minska arbetskön, samt förenkla och snabba på undersökningen.
- Attackförsök som upptäckts och blockerats av Microsoft 365 Defender-lösningar. Det finns även data som du kan använda för att vidta förebyggande åtgärder som minskar risken för ytterligare exponering och ökar motståndskraften. 
- Förbättrad design som placerar användbar information i spotlight så att du snabbt kan identifiera data för att brådskande fokusera på, undersöka och dra nytta av rapporterna.

## <a name="a-centralized-learning-hub"></a>Ett centraliserat utbildningsnav

Säkerhetscentret i Microsoft 365 innehåller ett utbildningsnav som tar upp officiell vägledning från resurser som Microsofts säkerhetsblogg, Microsofts säkerhets community på YouTube och den officiella dokumentationen på docs.microsoft.com.

I utbildningshubben finns vägledning för e-&-samarbete (Microsoft Defender för Office 365 eller MDO) sida vid sida med slutpunkt (Microsoft Defender för slutpunkt eller MDE) och utbildningsresurser för Microsoft 365 Defender.

Utbildningshubben öppnas med utbildningsvägar ordnade kring ämnen som "Så här undersöker du med Microsoft 365 Defender?" och "Metodtips för Microsoft Defender för Office 365". Det här avsnittet omfattas för närvarande av säkerhetsproduktgruppen i Microsoft. Varje utbildningsväg återspeglar en projekterad tid som behövs för att gå igenom begreppen. Till exempel beräknas "Åtgärder att vidta när ett Microsoft Defender för Office 365-användarkonto har komprometterats" ta 8 minuter, och är värdefull utbildning direkt.

När du har klickat till innehållet kan det vara bra att bokmärka den här webbplatsen och ordna bokmärken i mappen Säkerhet eller Kritisk. Om du vill se alla Utbildningsvägar klickar du på länken Visa alla i huvudpanelen.

> [!NOTE]
> Det finns  användbara filter högst upp i utbildningshubben för Microsoft 365 säkerhetscenter där du kan välja mellan produkter (för närvarande Microsoft 365 Defender, Microsoft Defender för slutpunkt och Microsoft Defender för Office 365). Observera att antalet utbildningsresurser för varje avsnitt visas, vilket kan hjälpa eleverna att hålla reda på hur många resurser de har till hands för utbildning och inlärning.
>
> Tillsammans med produktfiltret visas aktuella ämnen, typer av resurser (från videoklipp till webbs vete) nivå av bekanthet eller erfarenhet med säkerhetsområden, säkerhetsroller och produktfunktioner.

## <a name="send-us-your-feedback"></a>Skicka oss dina synpunkter

Vi behöver din feedback. Vi vill alltid bli bättre, så om det är något du skulle vilja se kan du skicka oss feedback från [Microsoft 365 Defender.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

Du kan också lämna feedback från den här artikeln. I avsnittet Feedback i slutet under "Skicka och visa feedback om" är alternativen Den *här produkten* eller Den *här sidan.*

Använd knappen **Den här produkten** för *produktfeedback:*

1. Välj *den här* produkten längst ned i artikeln.
    1. Högerklicka på knappen och öppna i en ny flik om du vill fortsätta läsa anvisningarna.
2. Detta navigerar till **UserVoice-forumet.**
3. Du har två alternativ:
    1. Rulla ned till textrutan Hur kan vi förbättra efterlevnad eller skydda dina användare bättre i *Office 365?* och klistra in i *Microsoft 365 säkerhetscenter.* Du kan söka i resultaten efter en idé som din och rösta om den, eller använda knappen för **att publicera en ny idé.**
    1. Om du anser att det här problemet redan har rapporterats och vill höja upp sin profil med en röst (eller röster) använder du rutan Ge *feedback* på höger sida av UserVoice. Sök efter *Microsoft 365 säkerhetscenter,* **hitta problemet och** använd röstknappen för att höja dess status.

Använd *den här sidan* för feedback om själva artikeln. Tack för din feedback. Din röst hjälper oss att förbättra våra produkter.

### <a name="explore-what-the-security-center-has-to-offer"></a>Utforska vad säkerhetscentret har att erbjuda

Fortsätt utforska funktionerna i Microsoft 365 säkerhetscenter:

- [Hantera incidenter och aviseringar](manage-incidents.md)
- [Spåra och svara på nya hot med hotanalyser](threat-analytics.md)
- [Åtgärdscentret](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Leta efter hot på olika enheter, e-postmeddelanden, appar och identiteter](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [Anpassade identifieringsregler](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [E-& om samarbete](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [Skapa en nätfiskeattack och](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) [skapa en nyttolast för att utbilda dina team](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Relaterad information
- [Microsoft 365 Säkerhetscenter](overview-security-center.md)
- [Microsoft Defender för Office 365 i Säkerhetscenter för Microsoft 365](microsoft-365-security-center-mdo.md)
- [Microsoft Defender för slutpunkt i Säkerhetscenter för Microsoft 365](microsoft-365-security-center-mde.md)
- [Omdirigera konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365](microsoft-365-security-mde-redirection.md)
