---
title: Komma igång med Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Ange användarbehörigheter och roller för Microsoft Compliance Manager och konfigurera automatisk testning av åtgärder. Hantera användarhistorik och filtrera instrumentpanelsvyn.
ms.openlocfilehash: 8877a9a1e65a624708646c17a2517647c8a72f6a
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "52162632"
---
# <a name="get-started-with-compliance-manager"></a>Kom igång med Compliance Manager

**I den här artikeln:** I den här artikeln får du hjälp att konfigurera Efterlevnadshanteraren. Lär dig hur **du kommer** åt **Efterlevnadshanteraren, ställer in roller och** behörigheter och **konfigurerar automatisk testning av förbättringsåtgärder.** Gå igenom **instrumentpanelen för** Efterlevnadshanteraren och förstå huvudsidorna: sidan för förbättringsåtgärder, sidan lösningar, utvärderingssidan och sidan utvärderingsmallar.

## <a name="who-can-access-compliance-manager"></a>Vem har åtkomst till Efterlevnadshanteraren

Efterlevnadshanteraren är tillgänglig för organisationer med Office 365- och Microsoft 365-licenser samt för amerikanska Government Community Cloud (GCC) måttliga kunder, GCC High-kunder och doD-kunder (Department of Defense). Utvärderingstillgänglighet och hanteringsfunktioner beror på ditt licensavtal.  [Visa information om tjänstbeskrivning](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="before-you-begin"></a>Innan du börjar

Den Microsoft 365 globala administratören för organisationen är antagligen den första användaren som får åtkomst till Efterlevnadshanteraren. Vi rekommenderar att den globala administratören loggar in och anger användarbehörigheter enligt beskrivningen nedan när du besöker Efterlevnadshanteraren för första gången.

## <a name="sign-in"></a>Logga in

1. Gå till [kom Microsoft 365 och](https://compliance.microsoft.com/) logga in med ditt **Microsoft 365** globala administratörskonto.
2. Välj **Efterlevnadshanteraren** i det vänstra navigeringsfönstret. Du kommer till instrumentpanelen [för Efterlevnadshanteraren.](#understand-the-compliance-manager-dashboard)

Den direkta länken för att komma åt Efterlevnadshanteraren är [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager) .

## <a name="set-user-permissions-and-assign-roles"></a>Ange användarbehörigheter och tilldela roller

Efterlevnadshanteraren använder en rollbaserad åtkomstkontroll (RBAC)-behörighetsmodell. Endast användare som har tilldelats en roll kan komma åt Efterlevnadshanteraren och åtgärderna som tillåts av varje användare begränsas av [rolltypen.](#role-types)

### <a name="where-to-set-permissions"></a>Här anger du behörigheter

Den person som har den globala administratörsrollen för organisationen kan ange användarbehörigheter för Efterlevnadshanteraren. Behörigheter kan anges i säkerhets- Office 365 för & och i Azure Active Directory (Azure AD).

> [!NOTE]
> Kunder i amerikanska Government Community (GCC) Hög- och Department of Defense-miljöer (DoD) kan bara ange användarbehörigheter och roller för Efterlevnadshanteraren i Azure AD. Se nedan för Azure AD-instruktioner och definitioner av rolltyper.

Följ stegen nedan för att ange behörigheter Office 365 tilldela roller Office 365 säkerhets- & säkerhets- och efterlevnadscenter:

1. Gå till Office 365 [Säkerhetscenter & och](https://protection.office.com/) välj **Behörigheter i** det vänstra navigeringsfältet.

2. Leta reda på den rollgrupp där du vill lägga till en eller flera användare och markera kryssrutan till vänster om gruppnamnet. (Se listan [över roller och relaterade funktioner nedan.](#role-types) Rollgruppsnamnen efterliknar rollnamnet.)

3. Välj Redigera under rubriken Medlemmar i det **utfällfällade** fönstret **för** den gruppen.

4. Välj **Välj medlemmar**. Ett annat utfällt fönster visas.

5. Välj **+ Lägg till** för att välja en eller flera användare att lägga till i gruppen.

6. Markera kryssrutan bredvid de namn du vill lägga till och välj sedan **knappen Lägg** till längst ned.

7. När du är klar med att tilldela användare väljer **du Klar** och sedan **Spara** och **sedan Stäng.**

##### <a name="more-about-the-office-365-security--compliance-center"></a>Mer om säkerhets- Office 365 säkerhets- & säkerhets- och efterlevnadscenter

Läs mer om [behörigheter i säkerhets- Office 365 säkerhets- & Kompatibilitetscenter.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

Om du inte har tillgång till säkerhets- och efterlevnadscentret för Office 365, eller om du behöver få åtkomst till den klassiska versionen av Efterlevnadshanteraren i Microsoft Service Trust Portal, kan du använda administratörsinställningarna i Service Trust Portal för att tilldela roller[(visningsinstruktioner).](meet-data-protection-and-regulatory-reqs-using-microsoft-cloud.md#assigning-compliance-manager-roles-to-users) Observera att sådana roller är mer begränsade i deras funktioner.

##### <a name="more-about-azure-ad"></a>Mer om Azure AD

Information om hur du tilldelar roller och anger behörigheter i Azure AD finns i [Tilldela administratörsroller och icke-administratörsroller till användare med Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).

Användare med Azure AD-identiteter som inte har Office 365- eller Microsoft 365-prenumerationer kommer inte att kunna komma åt Efterlevnadshanteraren i Microsoft 365 efterlevnadscenter. Om du vill ha hjälp med att komma åt Efterlevnadshanteraren kontaktar [du cmresearch@microsoft.com](mailto:cmresearch@microsoft.com).

### <a name="role-types"></a>Rolltyper

I tabellen nedan visas de funktioner som tillåts av varje roll i Efterlevnadshanteraren. Tabellen visar också hur varje [Azure AD-roll mappar](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) till Efterlevnadshanteraren-roller. Användarna behöver minst läsrollen Efterlevnadshanteraren eller den globala läsaren i Azure AD för att kunna komma åt Efterlevnadshanteraren.


| Användaren kan: | Efterlevnadshanteraren-roll | Azure AD-roll | 
| :------------- | :-------------: | :------------: |
| **Läsa men inte redigera data**| Efterlevnadshanteraren Läsare  | Global läsare i Azure AD, säkerhetsläsare | 
| **Redigera data**| Bidrag till Efterlevnadshanteraren | Efterlevnadsadministratör | 
| **Redigera testresultat**| Utvärderare för efterlevnadshanteraren | Efterlevnadsadministratör | 
| **Hantera utvärderingar samt mall- och klientdata**| Efterlevnadshanteraren – administration | Efterlevnadsadministratör, dataadministratör för efterlevnad, säkerhetsadministratör  | 
| **Tilldela användare**| Global administratör | Global administratör | 

## <a name="settings-for-automated-testing-and-user-history"></a>Inställningar för automatiserad testning och användarhistorik

Med inställningarna för Efterlevnadshanteraren Microsoft 365 kompatibilitetscenter kan du aktivera och inaktivera automatisk testning av förbättringsåtgärder. Med inställningarna kan du också hantera data för användare som är associerade med förbättringsåtgärder, inklusive möjligheten att omtilldela förbättringsåtgärder till en annan användare.  Endast personer med en global administratör eller efterlevnadshanterarens administratörsroll kan komma åt inställningarna för Efterlevnadshanteraren.

> [!NOTE]
> Funktionen för automatisk testning är inte tillgänglig för kunder GCC hög- och doD-miljöer eftersom Secure Score inte är tillgängligt i dessa miljöer. GCC Kunder med hög kvalitet och doD måste manuellt implementera och testa sina förbättringsåtgärder.

### <a name="set-up-automated-testing"></a>Konfigurera automatiska tester

Vissa förbättringsåtgärder i Efterlevnadshanteraren övervakas också [av Microsoft Secure Score.](../security/defender/microsoft-secure-score.md) Du kan ställa in automatisk testning av åtgärder som övervakas gemensamt, vilket innebär att när en åtgärd testas och uppdateras i Secure Score synkroniseras dessa resultat med samma åtgärder i Efterlevnadshanteraren och räknas mot efterlevnadsresultatet.

Automatisk testning är aktiverat som standard för organisationer som inte har efterlevnadshanteraren. När du först distribuerar Microsoft 365 eller Office 365 tar det ungefär sju dagar för Secure Score att helt samla in data och lägga in dem i efterlevnadsresultatet.  När automatisk testning är aktiverad uppdateras inte åtgärdens testdatum, men teststatusen uppdateras. När nya utvärderingar skapas inkluderar poäng automatiskt Microsoft kontrollresultat och Secure Score-integrering.

Den globala administratören för organisationen kan när som helst ändra inställningarna för automatisk testning. Du kan inaktivera automatisk testning för vanliga förbättringsåtgärder eller aktivera det för enskilda åtgärder. Följ anvisningarna nedan om du vill ändra automatiska testinställningar.

#### <a name="to-manage-your-automated-testing-settings"></a>Så här hanterar du dina automatiska testinställningar:

1. Välj **Inställningar** i det vänstra navigeringsfältet var som helst i [Microsoft 365 kompatibilitetscenter.](https://compliance.microsoft.com/)

2. Välj Efterlevnadshanteraren på **inställningssidan.**

3. Välj **Automatiserad testning** i det vänstra navigeringsfältet.

4. Välj den tillämpliga knappen om du vill aktivera automatisk testning för alla förbättringsåtgärder, inaktivera den för alla åtgärder eller aktivera den för enskilda åtgärder.

5. Om du väljer **Aktivera per förbättringsåtgärd** visas alla tillgängliga förbättringsåtgärder att välja bland i en lista.  Markera kryssrutan bredvid den åtgärd som du vill testa automatiskt.

6. Spara **inställningarna** genom att välja Spara. Du får ett bekräftelsemeddelande högst upp på skärmen om att ditt val har sparats. Om du får ett felmeddelande försöker du igen.

**Obs!** Endast den globala administratören kan aktivera eller inaktivera automatiska uppdateringar för alla åtgärder. Efterlevnadshanterarens administratör kan aktivera automatiska uppdateringar för enskilda åtgärder, men inte för alla åtgärder globalt.

### <a name="manage-user-history"></a>Hantera användarhistorik

Med **inställningarna för Hantera användarhistorik** kan du snabbt identifiera vilka användare som har arbetat med förbättringsåtgärder i Efterlevnadshanteraren. Identifierbara användardata som är associerade med förbättringsåtgärder omfattar alla implementerings- och testarbete som utförts, dokument som de laddat upp och eventuella anteckningar som de har skrivit in. Det kan vara nödvändigt att förstå och hämta den här typen av data för organisationens egna efterlevnadsbehov.

Med användarhistorikinställningarna kan du även omtilldela alla förbättringsåtgärder från en användare till en annan.

**Så här hittar du inställningarna för användarhistorik:**

1. Välj Inställningar i det vänstra navigeringsfältet var som helst i [Microsoft 365 kompatibilitetscenter.](https://compliance.microsoft.com/)

2. Välj Efterlevnadshanteraren på **inställningssidan.**

3. Välj **Hantera användarhistorik i** det vänstra navigeringsfältet.

På **sidan Hantera användarhistorik** visas en lista över alla användare efter e-postadress som har tilldelats en förbättringsåtgärd. Använd knappen **Sök för** att snabbt hitta en viss användare genom att skriva in deras e-postadress.

Till höger om varje användares e-postadress finns alternativ i listrutan Välj för att exportera en rapport, omtilldela förbättringsåtgärder eller ta bort historik.  Se respektive avsnitt nedan för mer information om varje alternativ.

#### <a name="export-a-report-of-user-history-data"></a>Exportera en rapport över användarhistorikdata

Du kan exportera en Excel som innehåller en lista över förbättringsåtgärder som tilldelats en användare.  Rapporten listar även alla bevisfiler som laddats upp av användaren. Den här informationen kan hjälpa dig att omtilldela öppna förbättringsåtgärder.

Rapporten återspeglar förbättringsåtgärdens status från och med datumet då den skapades. Det är inte en historisk rapport över alla tidigare ändringar av dess status eller tilldelning (lär dig hur du exporterar en rapport [från sidan för förbättringsåtgärder).](compliance-manager-improvement-actions.md#export-a-report)

**Följ anvisningarna nedan om du vill exportera en rapport efter användare:**

1. Välj **Inställningar** i det vänstra navigeringsfältet var som helst i [Microsoft 365 kompatibilitetscenter.](https://compliance.microsoft.com/)

2. Välj Efterlevnadshanteraren på **inställningssidan.**

3. Välj **Hantera användarhistorik** i navigeringen till vänster.

4. Hitta rätt användare genom att söka i listans e-postadresser eller genom att **välja Sök** och ange användarens e-postadress.

5. Välj **Exportera** rapport i den nedrullningsmenyn **Välj.**

6. När Excel filen med rapporten har skapats kan du öppna den och spara den på din lokala dator.

#### <a name="reassign-improvement-actions-to-another-user"></a>Tilldela om förbättringsåtgärder till en annan användare

Du kan omtilldela förbättringsåtgärder från en användare till en annan. När du omtilldelar en åtgärd ändras inte historiken för dokumentuppladdningen, men namnet på den användare som ursprungligen laddade upp dokumentationen visas inte längre i förbättringsåtgärden.

**Följ stegen nedan för att omtilldela förbättringsåtgärder till en annan användare:**

1. Välj **Inställningar** i det vänstra navigeringsfältet var som helst i [Microsoft 365 kompatibilitetscenter.](https://compliance.microsoft.com/)

2. Välj Efterlevnadshanteraren på **inställningssidan.**

3. Välj **Hantera användarhistorik** i navigeringen till vänster.

4. Hitta en användare genom att söka i listans e-postadresser eller genom att **välja Sök** och ange användarens e-postadress.

5. I **listrutan** Välj väljer du Tilldela om **förbättringsåtgärder**. Det **utfällade fönstret för att tilldela** om förbättringsåtgärder visas.

6. I fältet **Sök efter användare** anger du namnet på eller e-postadressen till den användare som du vill ska tilldela förbättringsåtgärderna *till*.

7. När du ser namnet på den avsedda användaren under **Förbättringsåtgärder** tilldelas , väljer du användaren och väljer **sedan Tilldela åtgärder**.

8. När omtilldelaren är klar visas ett bekräftelsemeddelande i det utfällda fönstret som bekräftar att alla förbättringsåtgärder från den tidigare användaren har tilldelats till den nya användaren. Om du får ett meddelande om omtilldelarfel stänger du fönstret och försöker igen. Om du vill stänga det utfällfällade fönstret väljer du **Klar**.

Den nya mottagaren får ett e-postmeddelande om att han eller hon har tilldelats en förbättringsåtgärd. E-postmeddelandet innehåller en direktlänk till informationssidan för förbättringsåtgärden.
 
 > [!NOTE]
> Om du tilldelar en åtgärd som har en väntande uppdatering bryts direktlänken till åtgärden i e-postmeddelandet för omtilldelaren om uppdateringen godkänns efter omtilldeningen. Du kan åtgärda det genom att tilldela åtgärden till användaren på ny tid när uppdateringen har accepterats. Läs mer om [uppdateringar av förbättringsåtgärder.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

#### <a name="delete-user-history"></a>Ta bort användarhistorik

Om du tar bort en användares historik tas användaren bort som ägare av förbättringsåtgärder, och användarens namn tas bort från alla andra fält i Efterlevnadshanteraren. När du tar bort en användares historik visas  inte värdet Tilldelad till för de förbättringsåtgärder som de ägde förrän en ny användare har tilldelats. Dokument som laddats upp till förbättringsåtgärden **visar att användaren** har tagits bort i stället för den borttagna användarens namn. Borttagning av användarhistorik är permanent.

Om du vill ta bort en användares historik följer du stegen nedan:

1. Välj **Inställningar** i det vänstra navigeringsfältet var som helst i [Microsoft 365 kompatibilitetscenter.](https://compliance.microsoft.com/)

2. Välj Efterlevnadshanteraren på **inställningssidan.**

3. Välj **Hantera användarhistorik** i navigeringen till vänster.

4. Hitta en användare genom att söka i listans e-postadresser eller genom att **välja Sök** och ange användarens e-postadress.

5. Välj **Ta bort** historik på menyn **Välj.**

6. Ett fönster visas där du uppmanas att bekräfta den permanenta borttagningen av användarens historik. Om du vill fortsätta med borttagningen väljer du **Ta bort historik**. Om du vill lämna den utan att ta bort historiken väljer du **Avbryt**.

7. Du kommer tillbaka till sidan **Hantera användarhistorik** med ett bekräftelsemeddelande högst upp om att användarens historik har tagits bort.

## <a name="understand-the-compliance-manager-dashboard"></a>Förstå instrumentpanelen för Efterlevnadshanteraren

Instrumentpanelen för Efterlevnadshanteraren har utformats för att ge dig en överblick över den aktuella efterlevnadsstatusen.

![Efterlevnadshanteraren – instrumentpanel](../media/compliance-manager-dashboard.png "Instrumentpanel för Efterlevnadshanteraren")

### <a name="overall-compliance-score"></a>Övergripande efterlevnadspoäng

Efterlevnadsresultatet visas tydligt högst upp. Den visar en procentandel baserat på punkter som kan nås för att slutföra förbättringsåtgärder som åtgärdar viktiga dataskyddsstandarder och bestämmelser. Pekar på [Microsofts åtgärder](compliance-manager-assessments.md#microsoft-actions-tab), som hanteras av Microsoft, räknas också mot din efterlevnadspoäng.

När du kommer till Efterlevnadshanteraren för första gången baseras ditt första resultat på den [Microsoft 365 dataskyddsbaslinjen](compliance-manager-assessments.md#data-protection-baseline-default-assessment). Den här baslinjeutvärderingen, som är tillgänglig för alla organisationer, är en uppsättning kontroller som innehåller vanliga branschföreskrifter och standarder. Efterlevnadshanteraren söker igenom befintliga Microsoft 365-lösningar och ger dig en första bedömning baserat på dina aktuella sekretess- och säkerhetsinställningar. När du lägger till utvärderingar som är relevanta för organisationen blir resultatet mer beskrivande för dig.

**Läs mer:** [Förstå hur ditt efterlevnadsresultat beräknas.](compliance-score-calculation.md)

### <a name="key-improvement-actions"></a>Viktiga förbättringsåtgärder

Det här avsnittet innehåller de viktigaste förbättringsåtgärder du kan vidta för att få största möjliga positiva inverkan på din övergripande efterlevnadsresultat. Välj **Visa alla förbättringsåtgärder om** du vill gå till sidan för förbättringsåtgärder.

### <a name="solutions-that-affect-your-score"></a>Lösningar som påverkar resultatet

Det här avsnittet visar lösningar som innehåller förbättringsåtgärder som kan påverka ditt resultat positivt och antalet utestående förbättringsåtgärder i dessa lösningar. Välj **Visa alla lösningar om** du vill besöka sidan med lösningar.

### <a name="compliance-score-breakdown"></a>Sammanställning av efterlevnadsresultat

I det här avsnittet får du en mer detaljerad vy av poängen på två olika sätt:

- **Kategorier**: Visar procentandelen av din övergripande poäng i kategorier för dataskydd, till exempel "skydda information" eller "hantera enheter".
- **Utvärderingar:** Visar procentandelen av dina framsteg när det gäller att hantera bedömningar av särskilda standarder, föreskrifter och lagar för dataskydd, t.ex. GDPR eller NIST 800-53.

### <a name="filtering-your-dashboard-view"></a>Filtrera instrumentpanelsvyn

Du kan filtrera instrumentpanelen så att du bara ser de objekt som är relaterade till vissa bestämmelser och standarder, lösningar, åtgärdstyp, utvärderingsgrupper eller kategorier för dataskydd. Om du filtrerar vyn på det här sättet filtreras också poängen på instrumentpanelen, som visar hur många poäng du har uppnått av det totala antalet möjliga poäng baserat på dina filtervillkor.

Så här använder du filter:

1. Välj **Filter** uppe till höger på instrumentpanelen.
2. Välj filtervillkor i det **utfällade** fönstret Filter och välj sedan **Använd**.

När du har tillämpat ett filter kommer du att se poängen justerad i realtid. Procentandelen för efterlevnadsresultatet och detaljerad information, och förbättringsåtgärder och lösningar, gäller nu endast data som omfattas av dina filtervillkor. Om du loggar ut från Compliance Manager finns den filtrerade vyn kvar när du loggar in igen.

Så här tar du bort filter:

- I rubriken **Tillämpade filter** ovanför efterlevnadsresultatet väljer du **X** bredvid det enskilda filter du vill ta bort. eller
- Välj **Filter** uppe till höger på instrumentpanelen och välj sedan Rensa filter i den utfällklara **rutan Filter.** 

## <a name="improvement-actions-page"></a>Sidan Förbättringsåtgärder

[Förbättringsåtgärder](compliance-manager-improvement-actions.md) är åtgärder som hanteras av din organisation. Genom att arbeta med förbättringsåtgärder kan du centralisera efterlevnadsaktiviteterna och anpassa dem till dataskyddsföreskrifter och standarder. Varje förbättringsåtgärd ger detaljerad implementeringsvägledning och en länk så att du kan hitta rätt lösning. Förbättringsåtgärder kan tilldelas till användare i organisationen för att utföra implementerings- och testarbete. Du kan också lagra dokumentation, anteckningar och spela in statusuppdateringar i förbättringsåtgärden.

### <a name="view-your-improvement-actions"></a>Visa förbättringsåtgärder

Instrumentpanelen för Efterlevnadshanteraren visar **dina viktigaste förbättringsåtgärder.** Om du vill visa alla förbättringsåtgärder väljer du fliken Förbättringsåtgärder på instrumentpanelen, som tar dig till sidan förbättringsåtgärder. Du kan också välja Visa alla förbättringsåtgärder under listan med viktiga förbättringsåtgärder på instrumentpanelen för att komma till sidan för förbättringsåtgärder.

På sidan förbättringsåtgärder visas alla förbättringsåtgärder som hanteras av din organisation. Åtgärder som hanteras av Microsoft kan visas i varje bedömning (läs mer om [Microsoft-åtgärder).](compliance-manager-assessments.md#microsoft-actions-tab)

Om du har en lång lista över åtgärder på sidan för förbättringsåtgärder kan det vara bra att filtrera vyn. Välj **Filter** i det övre högra hörnet i åtgärdslistan. När  den utfällbaserade rutan Filter visas väljer du kriterier utifrån föreskrifter och standarder, lösning och grupp. Du kan också anpassa vyn genom att **välja Gruppera** i det övre högra hörnet. I listrutan väljer du för att visa efter grupp, lösning, kategori, åtgärdstyp eller status.

Standardvyn för den här sidan visar inte förbättringsåtgärder med teststatusen **godkänd**. Om du vill visa åtgärder som har testats markerar du **rutan Godkänd** i den utfällade rutan Filter. Endast åtgärder med teststatus godkänd **för antal** godkända i poäng. Vissa åtgärder kan visa en **väntande uppdateringsetikett.** Läs mer om [uppdateringar av förbättringsåtgärder.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

På sidan förbättringsåtgärder visas följande datapunkter för varje förbättringsåtgärd:

- **Poäng som** kan uppnås : antalet poäng som kan uppnås av det totala antalet tillgängliga poäng genom att slutföra åtgärden
- **Föreskrifter:** bestämmelser eller standarder som gäller för åtgärden
- **Grupp**: gruppen som du tilldelade åtgärden till
- **Lösningar:** den lösning där du kan gå för att utföra åtgärden
- **Utvärderingar**: de utvärderingar som innehåller åtgärden
- **Kategorier**: Den relaterade kategorin för dataskydd (till exempel skydda information, hantera enheter osv.)
- **Teststatus:**
    - **Ingen** – ingen statusuppdatering har registrerats
    - **Ej taxering** – testningen har inte startat
    - **Godkänd** – implementering har testats
    - **Misslyckades med låg risk** – testning misslyckades, låg risk
    - **Misslyckade medelrisker** – testning misslyckades, medelrisk
    - **Misslyckades med hög risk** – testning misslyckades, högrisk
    - **Inte omfattning** – åtgärden omfattas inte av utvärderingen och påverkar inte ditt resultat
    - **Identifieras – för manuell** test anger att en åtgärd har implementerats men inte testats. för automatiserat test, anger att en åtgärd väntar på automatiseringsresultat
    - **Kunde inte identifieras –** automatiserad status kan inte fastställas
    - **Testats delvis** – automatiserad poäng som belönar delar av poäng

**Läs mer:** [Se hur du tilldelar och utför arbete med förbättringsåtgärder.](compliance-manager-improvement-actions.md)

## <a name="solutions-page"></a>Sidan Lösningar

På sidan lösningar visas andelen av intjänade och potentiella poäng som ordnade efter lösning. Om du visar återstående punkter och förbättringsåtgärder från den här vyn kan du lättare förstå vilka lösningar som behöver uppmärksammas mer omedelbart.

Hitta sidan lösningar genom att välja fliken **Lösningar på** instrumentpanelen för Efterlevnadshanteraren. Du kan också välja **Visa alla lösningar** under Lösningar som påverkar resultatet **i** det övre högra avsnittet på instrumentpanelen.

### <a name="filtering-your-solutions-view"></a>Filtrera lösningsvyn

Så här filtrerar du vy över lösningar:

1. Välj **Filter** i det övre vänstra hörnet i utvärderingslistan.
2. I den **utfällna** rutan Filter gör du en kontroll bredvid önskade villkor (standarder och föreskrifter, lösning, åtgärdstyp, gruppen Efterlevnadshanteraren, kategori).
3. Välj **knappen** Använd. Filterfönstret stängs och du ser den filtrerade vyn.

Du kan också ändra vyn för att visa utvärderingar efter grupp, produkt  eller regel genom att välja typ av gruppering från gruppmenyn ovanför din utvärderingslista.

### <a name="taking-action-from-the-solution-page"></a>Vidta åtgärder från lösningssidan

På sidan Lösningar visas organisationens lösningar som är anslutna till förbättringsåtgärder. Tabellen visar varje lösnings bidrag till ditt totala resultat, vilka poäng som kan uppnås och möjliga i den lösningen och återstående antalet förbättringsåtgärder grupperade i lösningen som kan öka poängen.

Du kan vidta åtgärder från den här skärmen på två sätt:

1. Markera det hyperlänkade numret i **raden** för den avsedda lösningen under kolumnen Återstående åtgärder. Du ser en filtrerad vy av skärmen för förbättringsåtgärder med oteuterade förbättringsåtgärder för lösningen.

2. På raden för den avsedda lösningen under kolumnen **Öppna lösning** väljer du **Öppna**. Du ser lösningen eller platsen i säkerhets- Microsoft 365- Office 365 säkerhets- och efterlevnadscenter där du kan vidta den rekommenderade åtgärden.

## <a name="assessments-page"></a>Sidan Utvärderingar

På utvärderingssidan visas alla utvärderingar [som](compliance-manager-assessments.md) du har angett för organisationen. Nämnaren för ditt efterlevnadsresultat bestäms av alla dina spårade utvärderingar. När du lägger till fler utvärderingar visas fler förbättringsåtgärder på sidan förbättringsåtgärder, och nämnaren för efterlevnadsresultatet ökar.

I **den aktiva mallräknaren** nästan längst upp på sidan visas antalet aktiva utvärderingsmallar som för närvarande används av det totala antalet tillgängliga mallar som organisationen kan använda. Mer information [finns](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) i Malltyp.

Utvärderingssidan sammanfattar viktig information om varje bedömning:

- **Utvärdering**: namnet på utvärderingen
- **Status**:
    - **Slutförd** – alla kontroller har statusen "godkänd" eller så överförs minst en och resten är "utanför omfattningen"
    - **Ofullständig** – minst en kontroll har statusen "misslyckades"
    - **Ingen** – alla kontroller har inte testats
    - **Pågående** – förbättringsåtgärder har annan status, inklusive "pågår", "delvis kredit" eller "oupptäckta"
- **Utvärderingsstatus:** Procentandel av det arbete som utförts mot slutförande, mätt med antalet kontroller som testats
- **Dina förbättringsåtgärder:** antalet slutförda åtgärder som krävs för att uppfylla implementeringen av dina kontroller
- **Microsoft-åtgärder:** antalet slutförda åtgärder som uppfyller implementering av Microsoft-kontroller
- **Grupp**: namnet på gruppen som utvärderingen tillhör
- **Produkt**: associerad Microsoft 365 tjänst
- **Regel**: den regelstandard, policy eller lag som gäller för utvärderingen

### <a name="filtering-your-assessments-view"></a>Filtrera dina utvärderingsvyer

Så här filtrerar du visningen av utvärderingar:

1. Välj **Filter** i det övre vänstra hörnet i utvärderingslistan.
2. Kontrollera **önskade** villkor i den utfällade rutan Filter.
3. Välj **knappen** Använd. Filterfönstret stängs och du ser den filtrerade vyn.

Du kan också ändra vyn för att visa utvärderingar efter grupp, produkt  eller regel genom att välja typ av gruppering från gruppmenyn ovanför din utvärderingslista.

### <a name="default-assessment"></a>Standardbedömning

Som standard visas utvärderingen av [dataskyddsbaslinjen](compliance-manager-assessments.md#data-protection-baseline-default-assessment) på utvärderingssidan. Efterlevnadshanteraren innehåller också flera färdiga [mallar för](compliance-manager-templates-list.md) att skapa bedömningar.

## <a name="assessment-templates-page"></a>Sidan Utvärderingsmallar

En mall är ett ramverk för att skapa en bedömning i Efterlevnadshanteraren. På sidan utvärderingsmallar visas en lista med mallar och viktig information. Listan innehåller mallar som tillhandahålls av Efterlevnadshanteraren samt alla mallar som din organisation har ändrat eller skapat. Du kan använda filter för att hitta en mall baserat på certifiering, produktomfattning, land, bransch och vem som skapade den.

I **den aktiva mallräknaren** nästan längst upp på sidan visas antalet aktiva utvärderingsmallar som för närvarande används av det totala antalet tillgängliga mallar som organisationen kan använda. Mer information [finns](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) i Malltyp.

Välj en mall på raden så att informationssidan visas, som innehåller en beskrivning av mallen och ytterligare information om certifiering, omfattning och kontroller. På den här sidan kan du välja lämpliga knappar för att skapa en utvärdering, exportera malldata till Excel eller ändra mallen.

**Läs mer:** [Läs mer om hur du arbetar med utvärderingsmallar.](compliance-manager-templates.md)

## <a name="next-step"></a>Nästa steg
Anpassa efterlevnadshanteraren genom [att konfigurera utvärderingar](compliance-manager-assessments.md).