---
title: Microsoft 365 Säkerhetscenter översikt
description: Fördelar i Microsoft 365 säkerhetscenter, att kombinera Microsoft Defender för Office 365 (MDO) och Microsoft Defender för slutpunkt (MDE) med Microsoft Defender för identitet (MDI) och Microsoft Cloud App Security (MCAS). I den här artikeln beskrivs hur säkerhetscentret för Microsoft 365 avancerar för administratörer.
keywords: säkerhet, skadlig programvara, Microsoft 365, M365, säkerhetscenter, bildskärm, rapport, identiteter, data, enheter, appar
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.date: 04/07/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: d89e5dc29bfe7f980d40a9a5b139884750a966bc
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760020"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>Översikt över det enhetliga säkerhetscentret för Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).

Det förbättrade säkerhetscentret för **Microsoft 365** () kombinerar skydd, identifiering, undersökning och svar på e-post, samarbete, identitet och enhetshot i [https://security.microsoft.com](https://security.microsoft.com) en central portal.    

Microsoft 365 säkerhetscenter samlar funktioner från befintliga Microsoft-säkerhetsportaler, som Microsoft Defender Säkerhetscenter och Office 365 säkerhets- & efterlevnadscenter. Säkerhetscenter betonar snabb åtkomst till information, enklare layouter och att sammanföra relaterad information för enklare användning. Detta center omfattar:

- **[Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Med Microsoft Defender för Office 365 kan organisationer skydda sitt företag med en uppsättning funktioner för skydd mot identifiering, undersökning och spårning för att skydda e-post och Office 365-resurser.
- **[Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** tillhandahåller förebyggande skydd, identifiering efter intrång, automatisk undersökning och svar för enheter i organisationen.
- **[Microsoft 365 Defender](microsoft-365-defender.md)** är en del av Microsofts XDR-lösning *(Extended Detection and Response)* som utnyttjar Microsoft 365-säkerhetsportföljen för att automatiskt analysera hotdata över domäner och skapa en bild av en attack på en enskild instrumentpanel.

Om du behöver information om vad som har ändrats från Säkerhets- och efterlevnadscentret för Office 365 & eller Microsoft Defender Säkerhetscenter kan du läsa:

- [Defender för Office 365 i Microsoft 365 Säkerhetscenter](microsoft-365-security-center-mdo.md)
- [Defender för Endpoint i Microsoft 365 Säkerhetscenter](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>Vad du kan förvänta dig

Allt säkerhetsinnehåll som du använder i Säkerhets- och efterlevnadscenter för Office 365 (protection.office.com) och Microsoft Defender säkerhetscenter (securitycenter.microsoft.com) finns nu i Säkerhetscenter för *Microsoft 365.*

Microsoft 365 säkerhetscenter hjälper säkerhetsteam att undersöka och svara på attacker genom att ta in signaler från olika arbetsbelastningar i en uppsättning enhetliga upplevelser för:

- Incidenter & aviseringar
- Jakt
- Åtgärdscenter
- Analys av hot

Säkerhetscentret i Microsoft 365 framhäver *enhet, tydlighet* och gemensamma mål när Microsoft Defender för Office 365 och Microsoft Defender för Slutpunkt sammanfogas. Kopplingen gjordes utifrån de prioriteringar som anges nedan och skapade utan att ha tagit av de funktioner som respektive säkerhetssvit hade i kombination av:

- Vanliga byggblock
- Vanlig terminologi
- Vanliga enheter
- Funktionsparitet med andra arbetsbelastningar

## <a name="unified-investigations"></a>Enhetliga undersökningar

Konvergerande säkerhetscenter skapar en enda plats för att undersöka säkerhetstillbud i Microsoft 365. Ett primärt exempel är **Incidenter** under **& aviseringar** i snabbstarten av Microsoft 365 Säkerhetscenter.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Sidan Incidenter i Säkerhetscenter för Microsoft 365.":::

När du väljer ett incidentnamn visas en sida som visar värdet på konvergerande säkerhetscenter.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Exempel på sidan Sammanfattning för en incident i säkerhetscentret i Microsoft 365":::

<!--
![Example of the Summary page for an incident in the Microsoft 365 security center](../../media/converged-incident-info-3.png)
--> 

Längst upp på en incidentsida visas flikarna Sammanfattning **,** Aviseringar **,** Enheter **,** Användare **,** **Postlådor,** Undersökningar **och** Bevis. Välj de här flikarna om du vill ha mer detaljerad information. På fliken  Användare visas till exempel information om användare från konvergerade arbetsbelastningar (Microsoft Defender för slutpunkt, Microsoft Defender för identitet och Microsoft Cloud App Security) och ett antal källor, till exempel AD DS (Active Directory Domain Services), Azure Active Directory (Azure AD) och tredjepartsidentitetsproviders. Mer information finns i [undersöka användare](investigate-users.md).

Ta dig tid att granska alla incidenter i din miljö, gå in på följande flikar och öva på att bygga upp en förståelse för hur du får åtkomst till informationen för incidenter för olika typer av hot.

Mer information finns i [incidenter i Säkerhetscenter för Microsoft 365.](incidents-overview.md)

## <a name="improved-processes"></a>Förbättrade processer

Vanliga kontroller och innehåll visas antingen på samma plats eller komprimeras till en feed med data som gör det lättare att hitta. Till exempel enhetliga inställningar.

### <a name="unified-settings"></a>Enhetliga inställningar

![Klickade på "Roller" och öppnade sidan Inställningar, som innehåller Allmänna inställningar, Behörigheter, API:er och Regler. Öppna Behörigheter och sedan Roller. Visar alla roller](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>Behörigheter & roller

![Behörighet & Roller med Slutpunkter-roller &, Roller och Enhetsgrupper.](../../media/converged-roles-5.png)

 Access Microsoft 365 Säkerhetscenter är konfigurerat med globala Azure Active Directory-roller eller med hjälp av anpassade roller. Information om Defender för slutpunkt finns [i Tilldela användaråtkomst till Microsoft Defender Säkerhetscenter.](/microsoft-365/security/defender-endpoint/assign-portal-access) Mer information om Defender för Office 365 finns i Behörigheter i Efterlevnadscenter för [Microsoft 365 och Säkerhetscenter för Microsoft 365.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- Läs mer om hur du [hanterar åtkomst till Microsoft 365 Defender](m365d-permissions.md)
- Läs mer om hur du [skapar anpassade roller](custom-roles.md) i Säkerhetscenter för Microsoft 365

> [!NOTE]
> Microsoft Defender för slutpunkt i Säkerhetscenter i Microsoft 365 har stöd för att bevilja åtkomst till tjänstleverantörer av hanterade säkerhetstjänster [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) på samma sätt som åtkomst beviljas i [Microsoft Defender säkerhetscenter.](./mssp-access.md)

### <a name="integrated-reports"></a>Integrerade rapporter

Rapporter är även enhetliga i Säkerhetscenter för Microsoft 365. Administratörer kan börja med en allmän säkerhetsrapport och förgrena till specifika rapporter om slutpunkter, skicka e-& samarbete. Länkarna här genereras dynamiskt utifrån konfigurationen av arbetsbelastningen.

### <a name="quickly-view-your-microsoft-365-environment"></a>Visa din Microsoft 365-miljö snabbt

På **startsidan** visas många av de vanliga korten som säkerhetsteam behöver. Sammansättning av kort och data är beroende av användarrollen. Eftersom Säkerhetscenter för Microsoft 365 använder rollbaserad åtkomstkontroll kommer olika roller att se kort som är mer relevanta för deras dagliga jobb.  

Med den här snabb översiktsinformationen kan du hålla dig informerad om de senaste aktiviteterna i organisationen. I Microsoft 365 säkerhetscenter samlas signaler från olika källor för att presentera en vy över din Microsoft 365-miljö.

Korten delas in i följande kategorier:

- **Identiteter**– övervaka identiteterna i organisationen och håll reda på misstänkta eller riskfyllda beteenden. [Läs mer om identitetsskydd](/azure/active-directory/identity-protection/overview-identity-protection).
- **Data** – Hjälper till att spåra användaraktivitet som kan leda till obehörig information.
- **Enheter** – få uppdaterad information om aviseringar, intrångsaktivitet och andra hot på dina enheter.
- **Appar** – få insyn i hur molnappar används i organisationen. [Läs mer om Cloud App Security- identifierade appar](/cloud-app-security/discovered-apps).

## <a name="threat-analytics-with-better-data-coverage"></a>Hotanalyser med bättre datatäckning
Spåra och svara på nya hot med hjälp av följande integrerade funktioner för hotanalys i Microsoft 365 Defender:

- Bättre datatäckning mellan Microsoft Defender för Endpoint och Microsoft Defender för Office 365, vilket gör kombinerad incidenthantering, automatisk undersökning, åtgärder och proaktiv eller reaktiv hotering över hela domänen möjlig. 
- E-postrelaterade identifieringar och åtgärder från Microsoft Defender för Office 365, utöver de slutpunktsdata som redan är tillgängliga från Microsoft Defender för Slutpunkt.
- En vy över hotrelaterade incidenter som sammanställer aviseringar i hela attackberättelser om Microsoft Defender för Endpoint och Microsoft Defender för Office 365 för att minska arbetskön, samt förenkla och snabba upp din undersökning.
- Attackförsök som upptäckts och blockerats av Microsoft 365 Defender-lösningar. Det finns även data som du kan använda för att vidta förebyggande åtgärder som minimerar risken för ytterligare exponering och ökar motståndskraft. 
- Förbättrad design som placerar åtgärdbar information i spotlight så att du snabbt kan identifiera data och brådskande fokusera på, undersöka och dra nytta av rapporterna.

## <a name="a-centralized-learning-hub"></a>Ett centraliserat utbildningsnav

I Microsoft 365 säkerhetscenter finns ett utbildningsnav som tar upp officiell vägledning från resurser som Microsofts säkerhetsblogg, Microsofts säkerhets community på YouTube och den officiella dokumentationen på docs.microsoft.com.

I utbildningshubben finns vägledning för e-&-samarbete (Microsoft Defender för Office 365 eller MDO) sida vid sida med Slutpunkt (Microsoft Defender för slutpunkt eller MDE) och Utbildningsresurser för Microsoft 365 Defender.

Utbildningshubben öppnas med utbildningsvägar ordnade kring ämnen som "Så här undersöker du användning av Microsoft 365 Defender?" och "Metodtips för Microsoft Defender för Office 365". Det här avsnittet används för närvarande av säkerhetsproduktgruppen i Microsoft. Varje utbildningsväg återspeglar den tid det tar att gå igenom begreppen. Till exempel beräknas "Åtgärder att vidta när ett Microsoft Defender för Office 365-användarkonto har komprometterats" ta 8 minuter, och är värdefull inlärning i farten.

När du har klickat till innehållet kan det vara bra att bokmärka den här webbplatsen och ordna bokmärken i en "Säkerhetsmapp" eller "Kritisk"-mapp. Om du vill se alla utbildningsvägar klickar du på länken Visa alla i huvudpanelen.

> [!NOTE]
> Det finns användbara **filter** högst upp på utbildningshubben för Microsoft 365 Säkerhetscenter som gör att du kan välja mellan produkter (för närvarande Microsoft 365 Defender, Microsoft Defender för slutpunkt och Microsoft Defender för Office 365). Observera att antalet utbildningsresurser för varje avsnitt visas, vilket kan hjälpa eleverna att hålla reda på hur många resurser de har till hands för utbildning och inlärning.
>
> Tillsammans med produktfiltret visas aktuella ämnen, typer av resurser (från videoklipp till webbsportaler), kunskapsnivåer eller erfarenhet inom säkerhetsområden, säkerhetsroller och produktfunktioner.

## <a name="send-us-your-feedback"></a>Skicka oss dina synpunkter

Vi behöver din feedback. Vi vill alltid bli bättre, så om du skulle vilja se något kan du skicka oss feedback om [Microsoft 365 Defender.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

Du kan också lämna feedback från den här artikeln. I avsnittet "Feedback" i slutet under "Skicka och visa feedback om" är alternativen Den *här* produkten eller *Den här sidan*.

Använd knappen **Den här produkten** för *produktfeedback:*

1. Välj *Den här* produkten längst ned i artikeln.
    1. Högerklicka på knappen och "Öppna i en ny flik" om du vill fortsätta läsa de här anvisningarna.
2. Detta navigerar till **UserVoice-forumet**.
3. Du har två alternativ:
    1. Rulla ned till textrutan Hur kan vi förbättra efterlevnad eller skydda dina användare bättre i *Office 365?* och klistra in i *Säkerhetscenter för Microsoft 365.* Du kan söka i resultaten efter en idé som din och rösta om den, eller använda knappen för **Publicera en ny idé**.
    1. Om du känner att det här problemet redan har rapporterats och vill höja sin profil med en röst (eller röster) använder du rutan Ge *feedback* på höger sida uservoice. Sök efter *Microsoft 365 Säkerhetscenter*, hitta problemet och använd **röstknappen för att** höja dess status.

Använd *den här* sidan för feedback om själva artikeln. Tack för din feedback. Din röst hjälper oss att förbättra produkterna.

### <a name="explore-what-the-security-center-has-to-offer"></a>Se vad säkerhetscentret har att erbjuda

Utforska funktionerna i Säkerhetscenter för Microsoft 365:

- [Hantera incidenter och aviseringar](manage-incidents.md)
- [Spåra och svara på nya hot med hotanalyser](threat-analytics.md)
- [Åtgärdscentret](m365d-action-center.md)
- [Jaga efter hot på olika enheter, e-postmeddelanden, appar och identiteter](./advanced-hunting-query-emails-devices.md)
- [Anpassade regler för identifiering](./custom-detection-rules.md)
- [E-post- och samarbetsaviseringar](../../compliance/alert-policies.md#default-alert-policies)
- [Skapa en simulering av nätfiskeattacker](../office-365-security/attack-simulation-training.md) [och skapa en nyttolast för utbildning av dina team](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>Relaterad information
- [Microsoft 365 Säkerhetscenter](overview-security-center.md)
- [Microsoft Defender för Office 365 i Microsoft 365 Säkerhetscenter](microsoft-365-security-center-mdo.md)
- [Microsoft Defender för Slutpunkt i Säkerhetscenter för Microsoft 365](microsoft-365-security-center-mde.md)
- [Omdirigera konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365](microsoft-365-security-mde-redirection.md)