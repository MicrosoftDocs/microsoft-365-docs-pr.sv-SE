---
title: Customer Lockbox-begäranden
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: Få mer information om Customer Lockbox-begäranden där du kan styra hur Microsofts supporttekniker kan komma åt dina data när du stöter på ett problem.
ms.openlocfilehash: 6a6a1d45bfbc8b7c65d9ac8d58eb246643505c4f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162188"
---
# <a name="customer-lockbox-in-office-365"></a>Customer Lockbox i Office 365

Den här artikeln innehåller distributions- och konfigurationsvägledning för Customer Lockbox. Customer Lockbox har stöd för förfrågningar om åtkomst till data Exchange Online, SharePoint Online och OneDrive för företag. Om du vill rekommendera support för andra tjänster kan du skicka en förfrågan [Office 365 UserVoice.](https://office365.uservoice.com/)

Om du vill se alternativen för att licensiera dina användare att dra nytta av Microsoft 365 efterlevnadserbjudanden, inklusive detta, från och med den 1 april 2020, se vägledningen för Microsoft 365-licensiering för [& efterlevnad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

Customer Lockbox ser till att Microsoft inte kan komma åt ditt innehåll för att utföra en tjänståtgärd utan ditt uttryckliga godkännande. Med Customer Lockbox kommer du till arbetsflödet för godkännande för förfrågningar om åtkomst till innehållet.

Ibland kan Microsoft-tekniker hjälpa till att felsöka och åtgärda problem som rapporterats av kunder i supportprocessen. Vanligtvis åtgärdas problem genom omfattande telemetri- och felsökningsverktyg som Microsoft har för sina tjänster. I vissa fall krävs dock en Microsoft-tekniker för att få åtkomst till kundinnehåll för att fastställa orsaken och åtgärda problemet. Customer Lockbox kräver att teknikern begär åtkomst från kunden som ett sista steg i arbetsflödet för godkännande. Detta ger organisationer möjlighet att godkänna eller neka dessa begäranden och ge direkt åtkomstkontroll till kunden.

### <a name="customer-lockbox-overview-video"></a>Video med översikt över Customer Lockbox

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

## <a name="customer-lockbox-workflow"></a>Customer Lockbox-arbetsflöde

I följande steg beskrivs det vanliga arbetsflödet när en Microsoft-tekniker inleder en Customer Lockbox-begäran:

1. Någon på en organisation får problem med sin egen Microsoft 365 postlåda.

2. När användaren har felsökt problemet, men inte kan åtgärda det, öppnar de en supportbegäran med Microsoft Support.

3. En Microsoft-supporttekniker granskar tjänstbegäran och fastställer ett behov av åtkomst till organisationens klientorganisation för att reparera problemet i Exchange Online.

4. Microsofts supporttekniker loggar in i verktyget för Customer Lockbox-begäran och gör en dataåtkomstbegäran som innehåller organisationens klientnamn, serviceförfrågans nummer och den beräknade tid teknikern behöver åtkomst till data.

5. När en Microsoft Support Manager har godkänt begäran skickar Customer Lockbox ett e-postmeddelande till den utsedda godkännaren till organisationen om den väntande åtkomstbegäran från Microsoft.

    ![Exempel på ett e-postmeddelande i Customer Lockbox](../media/CustomerLockbox1.png)

   Alla som har tilldelats rollen [Godkännare av Customer Lockbox-åtkomst](/office365/admin/add-users/about-admin-roles) i Microsoft 365 kan godkänna Customer Lockbox-begäranden.

6. Godkännaren loggar in Microsoft 365 administrationscentret och godkänner begäran. Det här steget utlöser skapandet av en granskningspost som är tillgänglig genom att söka i granskningsloggen. Mer information finns i Granska [Customer Lockbox-begäranden](#auditing-customer-lockbox-requests).

   Om kunden avvisar begäran eller inte godkänner den inom 12 timmar upphör den att gälla och ingen åtkomst ges till Microsoft-teknikern.

   > [!IMPORTANT]
   > Microsoft har inga länkar i Customer Lockbox-e-postaviseringar som kräver att du loggar in på Office 365.

7. När godkännaren från organisationen godkänt begäran får Microsoft-teknikern meddelandet om godkännande, loggar in i klientorganisationen i Exchange Online och åtgärdar kundens problem. Microsoft-tekniker har den begärda varaktigheten för att åtgärda problemet efter vilket åtkomsten automatiskt återkallas.

> [!NOTE]
> Alla åtgärder som utförs av en Microsoft-tekniker loggas i granskningsloggen. Du kan söka efter och granska dessa granskningsposter.

## <a name="turn-customer-lockbox-requests-on-or-off"></a>Aktivera eller inaktivera Customer Lockbox-begäranden

Du kan aktivera Customer Lockbox-kontroller i Microsoft 365 administrationscentret. När du aktiverar Customer Lockbox måste Microsoft godkännas av din organisation innan du kan komma åt innehållet i din klientorganisation.

1. Använd ett arbets- eller skolkonto som har tilldelats rollen som global administratör eller **Customer Lockbox-godkännare** för åtkomst, gå till [https://admin.microsoft.com](https://admin.microsoft.com) och logga in.

2. Välj **Inställningar > Organisations Inställningar**.

3. Välj **Säkerhet & Redigera Customer** Lockbox för Sekretess och flytta sedan växlingsknappen till På eller Av för att aktivera eller inaktivera  >    >  funktionen.  

    ![Require approval for Customer Lockbox](../media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a>Godkänna eller neka en Customer Lockbox-begäran

1. Använd ett arbets- eller skolkonto som har tilldelats rollen som global administratör eller **Customer Lockbox-godkännare** för åtkomst, gå till [https://admin.microsoft.com](https://admin.microsoft.com) och logga in.

2. Välj **Support > Customer Lockbox-begäranden**.

    ![Klicka på Support och sedan på Customer Lockbox-begäranden](../media/CustomerLockbox5.png)

    En lista med Customer Lockbox-begäranden visas.

    ![Lista över Customer Lockbox-begäranden](../media/CustomerLockbox6.png)

3. Välj en Customer Lockbox-begäran och välj **sedan Godkänn** eller **Neka**.

    ![Godkänna eller neka Customer Lockbox-begäranden](../media/CustomerLockbox7.png)

    Ett bekräftelsemeddelande om att Customer Lockbox-begäran har godkänts visas.

    ![Godkänna eller neka Customer Lockbox-begäranden](../media/CustomerLockbox8.png)

> [!NOTE]
> Använd Set-AccessToCustomerDataRequest-cmdleten för att godkänna, neka eller avbryta Microsoft 365 Customer Lockbox-begäranden som Microsoft-supporttekniker kan ge åtkomst till dina data. Mer information finns i [Set-AccessToCustomerDataRequest](/powershell/module/exchange/set-accesstocustomerdatarequest).


## <a name="auditing-customer-lockbox-requests"></a>Granska Customer Lockbox-begäranden

Granskningsposter som motsvarar Customer Lockbox-begäranden loggas i granskningsloggen. Du kan komma åt dessa loggar med hjälp [av verktyget för granskningsloggsökning](search-the-audit-log-in-security-and-compliance.md) i Säkerhets- & Efterlevnadscenter. Åtgärder som är relaterade till att acceptera eller neka en Customer Lockbox-begäran och åtgärder som utförs av Microsoft-tekniker (när åtkomstbegäranden godkänns) loggas också i granskningsloggen. Du kan söka efter och granska dessa granskningsposter.

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a>Söka i granskningsloggen efter aktivitet relaterad till Customer Lockbox-begäranden

Innan du kan använda granskningsloggen för att spåra förfrågningar om Customer Lockbox finns det några åtgärder du måste vidta för att konfigurera granskningsloggning. Mer information finns i [Söka i granskningsloggen i Säkerhets- & efterlevnadscenter.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin) När du har slutfört konfigurationen kan du använda de här stegen för att skapa en granskningsloggsökningsfråga för att returnera granskningsposter som är relaterade till Customer Lockbox:

1. Gå till [https://protection.office.com](https://protection.office.com).
  
2. Logga in med ditt arbets- eller skolkonto.

3. I den vänstra rutan i säkerhets- & efterlevnadscenter väljer du **Sökning och undersökning &**  >  **Granskningsloggsökning**.

    Sidan **Granskningsloggsökning** visas.

    ![Sidan Granskningsloggsökning](../media/auditlogsearch1.png)
  
4. Konfigurera följande sökvillkor:

    1. **Aktiviteter** – Lämna det här fältet tomt så att sökningen returnerar granskningsposter för alla aktiviteter. Detta är nödvändigt för att returnera alla granskningsposter som är relaterade till Customer Lockbox-begäranden och motsvarande aktivitet som utförts av Microsoft-tekniker.

    1. **Startdatum och** **Slutdatum – Välj** ett datum- och tidsintervall för att visa händelser som inträffat under perioden.

    1. **Användare** – Lämna fältet tomt.

    1. **Fil, mapp eller webbplats –** Lämna fältet tomt.

5. Klicka **på Sök** för att köra sökningen med dina sökvillkor.

    Sökresultaten läses in och efter en liten stund visas de under **Resultat på** sidan **Granskningsloggsökning.**

6. Klicka **på Filtrera** resultat på sidan med sökresultat och gör något av följande:

   - Om du vill visa granskningsposter som är relaterade till en godkännare i organisationen  som ska godkänna eller neka en Customer Lockbox-begäran: Skriv **Set-AccessToCustomerDataRequest** i rutan under kolumnen Aktivitet.

   - Om du vill visa granskningsposter som är relaterade till en Microsoft-tekniker  som utför åtgärder som svar på en godkänd Customer Lockbox-begäran: I rutan under användarkolumnen skriver du **Microsoft-operator.** I **kolumnen** Aktivitet visas åtgärden som utförts av teknikern.

      ![Filtrera efter "Microsoft Operator" för att visa granskningsposter](../media/CustomerLockbox10.png)

7. Klicka på en granskningspost i resultatlistan för att visa den.

### <a name="audit-record-for-a-customer-lockbox-access-request"></a>Granskningspost för en Customer Lockbox-åtkomstbegäran

När en person i organisationen godkänner eller nekar en Customer Lockbox-begäran loggas en granskningspost i granskningsloggen. Den här posten innehåller följande information.

| Egenskapen Granskningspost| Beskrivning|
|:---------- |:----------|
| Datum       | Datum och tid då Customer Lockbox-begäran godkänts eller nekats.
| IP-adress | IP-adressen för den dator som godkännaren använde för att godkänna eller neka en begäran. |
| Användare       | Tjänstkontot utgör BOXServiceAccount@ \[ \] .prod.outlook.com.            |
| Aktivitet   | Set-AccessToCustomerDataRequest; detta är granskningsaktiviteten som loggas när du godkänner eller nekar en Customer Lockbox-begäran.                                |
| Objekt       | Guid för Customer Lockbox-begäran                             |

Följande skärmbild visar ett exempel på en granskningsloggpost som motsvarar en godkänd Customer Lockbox-begäran. Om en Customer Lockbox-begäran nekades är värdet för parametern **ApprovalDecision** **Neka**.

![Granskningspost för en godkänd Customer Lockbox-begäran](../media/CustomerLockbox9.png)

> [!TIP]
> Om du vill visa mer detaljerad information i en granskningspost klickar du **på Mer information.**

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a>Granskningspost för en åtgärd som utförs av en Microsoft-tekniker

De åtgärder som utförs av en Microsoft-tekniker efter att en Customer Lockbox-begäran har godkänts (och som kan resultera i åtkomst till kundinnehåll) loggas i granskningsloggen. Dessa poster innehåller följande information.

| Egenskapen Granskningspost| Beskrivning|
|:---------- |:----------|
| Datum       | Datum när åtgärden utfördes. Observera att tiden som åtgärden utfördes kommer att ske inom 4 timmar från det att Customer Lockbox-begäran godkänts.              |
| IP-adress | IP-adressen för den Microsoft-tekniker som används. |
| Användare       | Microsoft-operator; det här värdet anger att den här posten är relaterad till en Customer Lockbox-begäran.                                  |
| Aktivitet   | Namn på aktiviteten som utförts av Microsoft-teknikern.|
| Objekt       | \<empty\>                                             |

## <a name="frequently-asked-questions"></a>Vanliga frågor och svar

#### <a name="which-microsoft-365-services-does-customer-lockbox-apply-to"></a>Vilka Microsoft 365 tjänster gäller Customer Lockbox för?

Customer Lockbox stöds för närvarande i Exchange Online, SharePoint Online och OneDrive för företag.

#### <a name="is-customer-lockbox-available-to-all-customers"></a>Är Customer Lockbox tillgängligt för alla kunder?

Customer Lockbox ingår i Microsoft 365- eller Office 365 E5-prenumerationer och kan läggas till i andra abonnemang med ett tillägg för Informationsskydd och efterlevnad eller en tilläggsprenumeration på Avancerad efterlevnad. Mer information [finns i Abonnemang](https://products.office.com/business/office-365-enterprise-e5-business-software) och priser.

#### <a name="what-is-customer-content"></a>Vad är kundinnehåll?

Kundinnehåll är data som skapas av användare av Microsoft 365 och program. Exempel på kundinnehåll är:

- E-post, brödtext och e-postbilagor

- SharePoint webbplatsinnehåll

- Information i brödtexten i en SharePoint fil

- Skype för företag brödtext i presentationsfilen

- Snabbmeddelanden och röstkonversationer

- Kundgenererade blob-data eller strukturerade lagringsdata (till exempel SQL behållare)

- Kundägd säkerhetsinformation (till exempel certifikat, krypteringsnycklar och lösenord)

- Slutledningar och alla efterföljande slutledningar, om kundinnehållet finns kvar

Mer information om kundinnehåll i Office 365 finns i [Office 365 Säkerhetscenter.](https://products.office.com/business/office-365-trust-center-privacy/)

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a>Vem meddelas när det finns en begäran om åtkomst till mitt innehåll?

Globala administratörer och alla som har tilldelats rollen godkännare för Customer Lockbox-åtkomst meddelas. Det här är också samma användare som kan godkänna Customer Lockbox-begäranden.

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a>Vem kan godkänna eller avvisa dessa förfrågningar i min organisation?

Globala administratörer och alla som har tilldelats rollen godkännare av Customer Lockbox-åtkomst kan godkänna Customer Lockbox-begäranden. Kunder styr de här rolltilldelningarna i sina organisationer.

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a>Hur anmäler jag mig till Customer Lockbox?

En global administratör kan aktivera och konfigurera Customer Lockbox i Microsoft 365 eller Microsoft 365 administrationscentret.

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a>Vad kan teknikern göra och hur vet jag vad Microsoft-teknikern gjorde om jag godkänner en Customer Lockbox-begäran?

När du godkänt en Customer Lockbox-begäran gav Microsoft-teknikern dessa behörigheter för att få åtkomst till kundinnehåll genom att använda förgodkända cmdlets. Åtgärder som vidtas av Microsoft-tekniker som svar på Customer Lockbox-begäranden loggas och är tillgängliga i granskningsloggen i säkerhets- & efterlevnadscenter.

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a>Hur vet jag att Microsoft följer godkännandeprocessen?

Du kan korsreferenser till meddelanden om e-postgodkännande som skickas till administratörer och godkännare i organisationen med historiken för Customer Lockbox-begäran Microsoft 365 administrationscentret.

Customer Lockbox ingår i den senaste [granskningsrapporten för SOC 1 SSAE 16.](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports) Du hittar mer information i de senaste rapporterna på [Microsoft Service Trust Portal.](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a>Kan Microsoft ändra listan över godkännare för min klientorganisation? Om inte, hur förhindras det?

Endast en global administratör i organisationen kan ange vem som kan godkänna Customer Lockbox-begäranden. Det innebär att endast medlemmar i gruppen Global administratör i gruppen Azure Active Directory ange vem som kan godkänna begäran. Medlemskap i gruppen Global administratör i Azure Active Directory hanteras endast av organisationen.

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a>Vad händer om jag behöver mer information om en begäran om innehållsåtkomst för att godkänna den?

Varje Customer Lockbox-begäran innehåller Microsoft 365 för din servicebegäran. Du kan kontakta Microsoft Support och hänvisa till det här servicenumret för att få mer information om begäran.

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a>När en Customer Lockbox-begäran godkänns, hur länge är behörigheterna giltiga?

För närvarande är den maximala perioden för åtkomstbehörigheter som beviljats Microsoft-teknikern 4 timmar. Microsoft-teknikern kan också begära en kortare tidsperiod.

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a>Hur får jag en historik över alla Customer Lockbox-begäranden?

Alla Customer Lockbox-begäranden visas i Microsoft 365 administrationscentret.

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a>Hur korrelerar jag begäranden om innehållsåtkomst till relaterade granskningsloggar?

Aktivitetsfeeden för efterlevnadscenter innehåller loggaktiviteter i Customer Lockbox. Kunder kan korsreferenser för Customer Lockbox-loggaktiviteterna från aktivitetsflödet mot den e-postförfrågan de får.

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a>Vad händer när en kund inte svarar på en Customer Lockbox-begäran?

Customer Lockbox-begäranden varar som standard 12 timmar. Om du inte svarar på en begäran inom 12 timmar förfaller begäran.

#### <a name="what-does-microsoft-do-when-a-customer-rejects-a-customer-lockbox-request"></a>Vad gör Microsoft när en kund avvisar en Customer Lockbox-begäran?

Om en kund avvisar en Customer Lockbox-begäran görs ingen åtkomst till kundinnehållet. Om en användare i organisationen fortsätter att ha problem med tjänsten som kräver att Microsoft får åtkomst till kundinnehåll för att lösa problemet kan tjänstproblemet kvarstå och Microsoft informerar användaren om problemet.

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a>Skyddar Customer Lockbox mot dataförfrågningar från myndigheter och andra tredje parter?

Nej. Microsoft ser allvarligt på förfrågningar från tredje part om kunddata. Som molntjänstleverantör arbetar Microsoft alltid för att se till att kunddata är privata. Om vi får en undergrupp försöker Microsoft alltid dirigera om tredje part till kunden för att få informationen. (Läs Brad Smiths blogg: [Skydda kunddata från myndigheters snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Vi publicerar regelbundet [detaljerad information om](https://www.microsoft.com/corporate-responsibility/lerr) de förfrågningar om verkställande av lag som Microsoft får.

Mer information [finns i Microsoft Säkerhetscenter](https://www.microsoft.com/trustcenter/default.aspx) om dataförfrågningar från tredje part och avsnittet "Avslöjande av kunddata" i [villkoren](https://www.microsoft.com/Licensing/product-licensing/products.aspx) för onlinetjänster.

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a>Hur ser Microsoft till att en anställd inte har stående åtkomst till kundinnehåll i Office 365 program?

Microsoft implementerar omfattande förebyggande åtgärder genom åtkomstkontrollsystem och åtgärder för att identifiera och åtgärda försök att kringgå dessa åtkomstkontrollsystem. Microsoft 365 med principerna för minsta behörighet och direktåtkomst. Därför har ingen Microsoft-personal kontinuerlig åtkomst till kundinnehåll. Om behörighet beviljas, gäller den under en begränsad tid. 

Microsoft 365 använder ett åtkomstkontrollsystem som kallas *Lockbox* för att bearbeta begäranden om behörigheter som ger möjlighet att utföra drift- och administrativa funktioner i tjänsten. En operatör måste begära åtkomst till kundinnehåll med hjälp av Lockbox, vilket innebär att en andra person måste vidta åtgärder på begäran (t.ex. godkänna den) innan åtkomst beviljas. Den andra personen kan inte vara beställare och måste godkänna åtkomst till kundinnehåll. Endast om begäran godkänns får operatören tillfällig åtkomst till kundinnehållet. Efter att ökningsperioden gått ut återkallar Lockbox åtkomsten.

Mer information om [Microsofts allmänna säkerhetsmetoder](https://www.microsoft.com/licensing/product-licensing/products) finns i villkoren för onlinetjänster.

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a>Under vilka omständigheter behöver Microsoft-tekniker åtkomst till mitt innehåll?

Det vanligaste scenariot där Microsoft-tekniker behöver åtkomst till kundinnehåll är när kunden gör en supportbegäran som kräver åtkomst för felsökning. En grundprincip i Microsoft 365 är att tjänsten fungerar utan Microsofts åtkomst till kundinnehåll. Nästan alla tjänsteåtgärder som utförs av Microsoft är helt automatiska och den mänskliga engagemanget styrs i mycket hög grad av kundinnehållet. Målet för Microsoft 365 är åtkomst till kundinnehåll för att stödja tjänsten behövs inte förrän kunden godkänt en särskild begäran om Microsoft-åtkomst.

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a>Jag trodde redan att mina data var säkra med Microsoft-molnet, så varför behöver jag Customer Lockbox?

Customer Lockbox ger en extra kontrollnivå genom att ge kunderna möjlighet att ge explicit åtkomstauktorisering för tjänståtgärder. Genom att visa att det finns procedurer för uttrycklig autentisering av dataåtkomst hjälper Customer Lockbox även kunderna att uppfylla vissa efterlevnadsskyldigheter, till exempel HIPAA och FEDRAMP.