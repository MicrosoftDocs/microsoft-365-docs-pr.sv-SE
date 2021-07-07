---
title: Integrera Microsoft Teams klasser med Blackboard Learn Ultra
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrera Microsoft Teams klasser med Blackboard Learn Ultra
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314501"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a>Använda Microsoft Teams-klasser med Blackboard Learn Ultra

Samarbete är kärnan i alla moderna organisationer. Genom att främja samarbete är det ett definierande kännetecken för varje framgångsrik institution. Du kan förbättra alla funktioner i Blackboard Learn Ultra genom att koppla ihop dem med Microsoft Teams klasser.

Kurserna kan innehålla realtidskonversationer, videomöten eller asynkrona interaktioner. Du kan lägga till fildelning och samskapning för eleverna på ett och samma ställe. Microsoft Teams klassen med Lär dig Ultra omdefiniera hur dynamics det finns att lära ut och vad effektivt lärande innebär.

> [!IMPORTANT]
> Kontrollera att du har ställt in fältet Institution Email i SIS (Student Information System) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`
>
>Integreringen Microsoft Teams klasser använder institutionens e-postfält i SIS för att mappa till rätt UPN (User Principal Name) för Microsoft Azure Active Directory (Microsoft Azure Active Directory). Om inga institutions-e-postmeddelanden har etablerats används den befintliga e-postadressen som standard. Vi rekommenderar att det här fältet ställs in för alla användare för att säkerställa att deras data synkroniseras korrekt och att det inte finns någon konflikt mellan e-postdata mellan Microsoft AAD och Blackboard Learn Ultra.
>
> Om du inte har angett det här fältet på rätt sätt i SIS-mappningen kommer integreringen fortsätta att fungera, men användare kanske inte visas i Teams-klasserna som skapats och fel kan uppstå.

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a>Stöd för institutionsdatamappning – SIS-fältet institution-e-post

Som en del av utvecklingen med molnleverantörsintegrationer har  Blackboard Learn Ultra skapat ett nytt institution-e-postfält, både i integreringen av Student Information System Framework och offentliga REST API:er, så att institutioner kan hantera datasynkroniseringsprocessen effektivt mellan Blackboard Learn Ultra och Microsoft AAD.

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a>Vad innebär institutionens e-post och vad har det stöd för?

Fältet **Institution Email** tillåter anpassade fältmappningar mellan en klients externt stödda datakällor och Blackboard Learn Ultra. Om datakällor är molntjänster, till exempel Microsoft, är UPN (User Principle Name) en primär unik identifierare för varje användare som består av ett UPN-prefix (användarens kontonamn) och ett UPN-suffix (ett DNS-domännamn) samman med en @-symbol. Då skapas en unik e-postadress för varje enskild användare i Microsoft Azure Active Directory.

För att säkerställa att data är korrekta och registreringar eller medlemskap mellan Blackboard Learn Ultra och Microsoft Teams-klasser kan uppnås korrekt måste en användares e-postadress matcha mellan båda systemen. I Blackboard Learn Ultra kan användare ändra eller åsidosätta sin befintliga e-postadress i användargränssnittet, vilket kan leda till synkroniseringsfel som uppstår och användaren inte läggs till i ett klassteam. Med **fältmappningen** Avbildning av institution-e-post säkerställer du att den här nivån av säkerhets- och valideringskontroll kan hanteras korrekt, oavsett om användarna har ändrat sin e-post i Blackboard Learn Ultra eller inte.

 När två e-postadresser skiljer sig åt, antingen:

- Ett beslut måste fattas om vilken källa som har företräde och kommer att tas som både person- och institution-e-post.
  Eller
- En institution kan ange en anpassad fältmappning i sin institution-e-post, vilket kan lösa en möjlig konflikt.

**Fältmappningen för** institution-e-post är nu tillgänglig för alla befintliga SIS-integreringstyper **i Avancerad konfiguration Inställningar** Användare lär  >  **sig fältmappning av**  >  **objekttyp.**

> [!NOTE]
> Det är viktigt att observera att  Som standard har e-postadressen för institutionen angetts till Person-e-post för alla SIS-format och måste vara unik för varje person.  Alla befintliga integreringar som har ställts in och körs har den här datamappningen på plats eftersom SIS misslyckas med att importera användare om deras e-post dupliceras. Om en institution kräver att institutionen ska kunna ändra e-post för institutionen till anpassad måste den hantera detta via den avancerade **Inställningar** i SIS.

## <a name="requirements"></a>Krav

Integrering Microsoft Teams de här klasserna är endast tillgängligt **för Ultra Course View-kurser.** Institutionen måste uppfylla följande krav för att kunna använda den:

- Ha Blackboard Lär dig Ultra SaaS med Ultra Base-navigering aktiverad

- Aktivera LTI för användning i kurser.

  a. Gå till **Administratörspanelens**  >  **LTI-verktygsleverantörer**  >  **för att hantera globala egenskaper.**

  b. Välj **LTI aktiverat i kurser** och om du vill väljer du Aktiverad i **organisationer.**

  c. Välj **Skicka**.

- LTI måste vara konfigurerat

- Lägga till Blackboard Learn Ultra Teams Classes LTI-integrering

- Lägga Microsoft Teams klasserna LTI 1.3-verktyget

- Lägga till REST API-verktyget och resursdelning mellan ursprung

- Konfigurera och godkänna Microsoft Teams klassintegrering

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a>Lägg till Blackboard Learn Ultra Teams Classes LTI 1.3-verktyget

1. I **administratörspanelen väljer** du **LTI-verktygsproviders**.

2. Välj **registrera LTI 1.3 Tool**.

3. I fältet **Klient-ID** skriver du in, eller kopierar och klistrar in, detta ID:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. Granska alla inställningar som har fyllts i på förhand och i **Verktygsstatus** och välj sedan **Aktiverad.**

5. Välj **Roll i** **Kurs, Namn och E-postadress** i **Institutionsprinciper** och välj sedan **Ja för** båda.

6. Välj **Tillåt betygstjänståtkomst och** Tillåt åtkomst till **medlemskapstjänst.**

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a>Lägga till Microsoft Teams Classes LTI 1.3 Tool

1. I **administratörspanelen väljer** du **LTI-verktygsproviders**.

2. Välj **registrera LTI 1.3 Tool**.

3. I fältet **Klient-ID** skriver du in, eller kopierar och klistrar in, detta ID:

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. Granska alla inställningar som har redan fyllts i och välj *Aktiverad* i *Verktygsstatus.*

5. I **Principer för institutionen** väljer du Roll i **Kurs, Namn och** **E-postadress.** Välj **Ja** för båda.

6. Välj **Tillåt betygstjänståtkomst och** Tillåt åtkomst till **medlemskapstjänst.**

## <a name="add-the-rest-api-tool"></a>Lägga till REST API-verktyget

1. Från **administratörspanelen** går du till **Integrationer** och väljer **Rest API-integrationer.**

2. Välj **Skapa integration.**

3. I fältet **Program-ID** skriver du in, eller kopierar och klistrar in, detta ID:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. Skriv en användare för den här integreringen.

   Den här användaren är den med home API-åtkomst som programmet är kopplat till.

5. Välj **Skicka**.

## <a name="add-the-cross-origin-resource-sharing"></a>Lägga till resursdelning mellan ursprung

1. Från **administratörspanelen** går du till **Integrationer** och väljer **Resursdelning mellan ursprung.*

2. Välj **Skapa konfiguration**.

3. I fältet **Ursprung skriver** du kopiera och klistra in url:en:

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. I fältet **Tillåtna rubriker** skriver du **Auktorisering**.

5. Ange **Tillgänglig** till **Ja.**

6. Välj **Skicka**.

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a>Konfigurera och godkänna Microsoft Teams klassintegrering

Om du vill integrera din Blackboard Learn Ultra-instans med Microsoft Teams-klasser måste du se till att programmet Blackboard Learn Ultra har godkänts för åtkomst inom Microsoft Azure klientorganisationen. Det här är en process som måste slutföras av institutionens globala Microsoft 365 administratör.

Den här processen kan göras antingen före eller efter att du har konfigurerat LTI-programmen i din Blackboard Learn Ultra Instance.

### <a name="before-configuring-the-lti-applications"></a>Innan du konfigurerar LTI-programmen

Om du väljer att godkänna Blackboard Learn Ultra Teams Classes Azure-appen innan du konfigurerar LTI-integrationerna måste du omdirigera till slutpunkten för administratörsmedgivande för **Microsoft-identitetsplattformen.** URL:en visas:

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> Du ersätter **{Tenant} med ditt** specifika institutions- Microsoft Azure-ID.

### <a name="after-configuring-the-lti-applications"></a>När du har konfigurerat LTI-programmen

1. På **administratörspanelen** går du till **Verktyg och verktyg och** väljer Sedan Microsoft Teams Integration **Admin.**

2. Välj **Aktivera Microsoft Teams**.

3. Lägg till ditt **Klientorganisations-ID** för Microsoft i det tillgängliga textfältet.

4. Välj något av följande alternativ:

   - Om appen har förmedgivande visas en liten bockmarkering. Om bockmarkeringen visas väljer du **Skicka**.

   - Om medgivandet inte har godkänts följer du anvisningarna som beskrivs för att generera webbadressen för medgivande och skicka den till den globala Microsoft 365 för godkännande.

5. När du har bekräftat att du godkänner väljer **du Försök igen** för att bekräfta och väljer sedan **Skicka**.
