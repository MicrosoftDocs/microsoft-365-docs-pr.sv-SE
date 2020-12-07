---
title: Skapa en säker miljö för gästdelning
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: Få reda på mer om tillgängliga alternativ för att skapa en säker delningsmiljö för gäster i Microsoft 365 och ge gäståtkomst för bättre samarbete.
ms.openlocfilehash: 4e2045113a6c98e2b3839a3a2cdd83105be94023
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558194"
---
# <a name="create-a-secure-guest-sharing-environment"></a>Skapa en säker miljö för gästdelning

I den här artikeln går vi igenom en mängd olika alternativ för att skapa en säker gästdelningsmiljö i Microsoft 365. De här är exempel som ger dig en uppfattning om vilka alternativ som är tillgängliga. Du kan använda de här procedurerna i olika kombinationer för att uppfylla organisationens säkerhets- och efterlevnadsbehov.

Den här artikeln innehåller:

- Konfigurera multifaktorautentisering för gäster.
- Konfigurera användarvillkor för gäster.
- Konfigurera kvartalsgranskning av gäståtkomst för att regelbundet verifiera om gästerna fortfarande behöver behörighet till grupper och webbplatser.
- Begränsa gästernas åtkomst till endast på webben för ohanterade enheter.
- Konfigurera en princip för sessionstidsgräns för att säkerställa att gästerna autentiserar sig dagligen.
- Skapa en typ av känslig information för ett strikt känsligt projekt.
- Tilldela automatiskt en känslighetsetikett till dokument som innehåller den typen av känslig information.
- Ta automatiskt bort gäståtkomst från filer med beteckningen med en känslighetsetikett.

Vissa av alternativen som beskrivs i den här artikeln kräver att gästerna har ett konto i Azure Active Directory. Om du vill vara säker på att gästerna ingår i katalogen när du delar filer och mappar med dem, ska du använda [SharePoint- och OneDrive-integrering med förhandsversionen av Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).

Observera att vi inte tar upp inställningarna för gästdelning i den här artikeln. Mer information om hur du aktiverar gästdelning i olika scenarier finns i [Samarbeta med personer utanför organisationen](collaborate-with-people-outside-your-organization.md).

## <a name="set-up-multi-factor-authentication-for-guests"></a>Konfigurera multifaktorautentisering för gäster

Multifaktorautentisering minskar kraftigt risken för att ett konto komprometteras. Eftersom gästanvändare kanske använder personliga e-postkonton som inte följer några principer för kontroll eller bästa praxis är det särskilt viktigt att kräva multifaktorautentisering för gäster. Om en gästanvändares användarnamn och lösenord blir stulna, minskar en andra autentiseringsfaktor avsevärt risken för att okända personer ska få åtkomst till webbplatserna och filerna.

I det här exemplet konfigurerar vi multifaktorautentisering för gäster genom att använda en princip för villkorsstyrd åtkomst i Azure Active Directory.

Konfigurera multifaktorautentisering för gäster

1. Gå till [Principer för villkorstyrd åtkomst i Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. På bladet för **Villkorsstyrd åtkomst | Principer** klickar du på **Ny princip**.
3. I fältet **Namn** skriver du ett namn.
4. Under **Tilldelningar** klickar du på **Användare och grupper**.
5. I bladet **Användare och grupper** markerar du **Välj användare och grupper**, markerar kryssrutan **Alla gäster och externa användare**.
6. Under **Tilldelningar** klickar du på **Molnappar eller åtgärder**.
7. Välj **alla program i molnet** på fliken **inkluderar** fliken **moln program eller-åtgärder** blad.
8. Under **Åtkomstkontroller** klickar du på **Bevilja**.
9. På bladet **Bevilja** markerar du kryssrutan **Kräv multifaktorautentisering** och klickar sedan på **Välj**.
10. På bladet **Nytt**, under **Aktivera princip**, klickar du på **På** och sedan på **Skapa**.

Gästen måste då registrera sig för multifaktorautentisering för att de ska kunna komma åt delat innehåll, webbplatser eller team.

### <a name="more-information"></a>Mer information

[Planerar en Azure AD Multi-Factor Authentication-distribution](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a>Konfigurera användarvillkor för gäster

I vissa fall kanske gästanvändare inte har undertecknat avtal eller andra juridiska avtal med din organisation. Du kan kräva att gästerna godkänner användningsvillkor innan de kan komma åt filer som delas med dem. Användningsvillkoren kan visas första gången de försöker få åtkomst till en delad fil eller webbplats.

Om du vill skapa användningsvillkor måste du först skapa dokumentet i Word eller något annat redigeringsprogram och sedan spara det som en PDF-fil. Filen kan sedan laddas upp till Azure AD.

Skapa användningsvillkor för Azure AD

1. Logga in på Azure som global administratör, säkerhetsadministratör eller administratör för villkorsstyrd åtkomst.
2. Gå till [Användningsvillkor](https://aka.ms/catou).
3. Klicka på **Nya villkor**.

   ![Skärmbild av inställningar för nya användningsvillkor för Azure AD](../media/azure-ad-guest-terms-of-use.png)

4. Skriv ett **namn** och **visningsnamn**.
6. För **Dokument med användningsvillkor** bläddrar du till den PDF-fil som du har skapat och väljer den.
7. Välj språk för dokumentet med användningsvillkor.
8. Ange **Kräv att användarna expanderar användningsvillkoren** som **På**.
9. Under **Villkorsstyrd åtkomst**, i listan **Tvinga med mallar för princip för villkorsstyrd åtkomst**, väljer du **Skapa princip för villkorsstyrd åtkomst senare**.
10. Klicka på **Skapa**.

När du har skapat användningsvillkoren är nästa steg att skapa en princip för villkorsstyrd åtkomst som visar användningsvillkoren för gästanvändare.

Skapa princip för villkorsstyrd åtkomst

1. Gå till [Principer för villkorstyrd åtkomst i Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. På bladet för **Villkorsstyrd åtkomst | Principer** klickar du på **Ny princip**.
3. Skriv ett namn i rutan **Namn**.
4. Under **Tilldelningar** klickar du på **Användare och grupper**.
5. I bladet **Användare och grupper** markerar du **Välj användare och grupper**, markerar kryssrutan **Alla gäster och externa användare**.
6. Under **Tilldelningar** klickar du på **Molnappar eller åtgärder**.
7. På fliken **Inkludera** väljer du **Välj appar** och klickar sedan på **Välj**.
8. På bladet **Välj** väljer du **Microsoft Teams**, **Office 365 SharePoint Online** och **Outlook Groups** och klickar sedan på **Välj**.
9. Under **Åtkomstkontroller** klickar du på **Bevilja**.
10. På bladet **Bevilja** väljer du **Användningsvillkor för gäster** och klickar sedan på **Välj**.
11. På bladet **Nytt**, under **Aktivera princip**, klickar du på **På** och sedan på **Skapa**.

Första gången en gästanvändare försöker komma åt innehåll, ett team eller en webbplats i organisationen måste de acceptera villkoren för användning.

> [!NOTE]
> Användningen av villkorstyrd åtkomst kräver en Azure Active Directory Premium P1-licens. Mer information finns i [Vad är villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

### <a name="more-information"></a>Mer information

[Användningsvillkor för Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a>Konfigurera granskning av gäståtkomst

Med åtkomstgranskningar i Azure AD kan du automatisera en återkommande granskning av användaråtkomst till olika team och grupper. Genom att begära åtkomstgranskning specifikt för gäster kan du bidra till att gästanvändare inte behåller åtkomsten till organisationens känsliga information under längre tid än nödvändigt.

Åtkomstgranskningar kan organiseras i program. Ett program är en gruppering av liknande åtkomstgranskningar som kan användas för att organisera åtkomstgranskningar för rapporter och granskningsändamål.

Skapa ett program

1. Logga in på Azure-portalen och öppna sidan [Identitetsstyrning](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade).
2. I den vänstra menyn klickar du på **Program**
3. Klicka på **Nytt program**.
4. Skriv ett **namn**  och **Beskrivning**.
5. Klicka på **Skapa**.

När programmet har skapats kan vi skapa en granskning av gäståtkomsten och koppla den till programmet.

Konfigurera åtkomstgranskning av gästanvändare

1. På sidan [Identitetsstyrning](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade) klickar du på **Åtkomstgranskningar** i den vänstra menyn.
2. Klicka på **Ny åtkomstgranskning**.

   ![Skärmbild av inställningar för åtkomstgranskning i Azure AD](../media/azure-ad-create-access-review.png)

3. Skriv ett namn i rutan **Namn**.
4. För **Frekvens** väljer du **Varje kvartal**.
5. För **Slut** väljer du **Aldrig**.
6. För **Omfång** väljer du **Enbart gästanvändare**.
7. Klicka på **Grupp**, markera de grupper som du vill ska ingå i åtkomstgranskningen och klicka sedan på **Välj**.
8. Under **Program** klickar du på **Länka till program**.
9. På bladet **Välj ett program** väljer du **Program för granskning av gäståtkomst**
10. Klicka på **Start**.

En separat åtkomstgranskning skapas för varje grupp som du anger. Gruppägare för varje grupp kommer att få ett e-postmeddelande varje kvartal för att godkänna eller neka gäståtkomst till sina grupper.

Det är viktigt att du noterar att gäster kan beviljas åtkomst till team eller grupper, eller till enskilda filer och mappar. När de får åtkomst till filer och mappar kanske gästerna inte läggs till i någon särskild grupp. Om du vill göra åtkomstgranskningar för gästanvändare som inte tillhör ett team eller en grupp kan du skapa en dynamisk grupp i Azure AD för alla gäster och sedan skapa en åtkomstgranskning för den gruppen. Webbplatsägaren kan även hantera [förfallodatum för gäster för webbplatsen](https://support.microsoft.com/office/25bee24f-42ad-4ee8-8402-4186eed74dea)

### <a name="more-information"></a>Mer information

[Hantera gäståtkomst med åtkomstgranskningar i Azure AD](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[Skapa en åtkomstgranskning av grupper eller program i åtkomstgranskningar i Azure AD](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guest-users"></a>Konfigurera endast webbåtkomst för gästanvändare

Du kan minska din attackyta och underlätta administrationen genom att kräva att gästanvändarna bara får åtkomst till dina team, webbplatser och filer med hjälp av en webbläsare.

För Microsoft 365 Grupper och Team gör du det med en princip för villkorsstyrd åtkomst i Azure AD. För SharePoint är detta konfigurerat i administrationscentret för SharePoint. (Du kan också [använda känslighetsetiketter för att tillåta begränsad endast webb-åtkomst för gäster](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)

Tillåta begränsad endast webb-åtkomst för grupper och team

1. Gå till [Principer för villkorstyrd åtkomst i Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. På bladet för **Villkorsstyrd åtkomst – Principer** klickar du på **Ny princip**.
3. Skriv ett namn i rutan **Namn**.
4. Under **Tilldelningar** klickar du på **Användare och grupper**.
5. I bladet **Användare och grupper** markerar du **Välj användare och grupper**, markerar kryssrutan **Alla gäster och externa användare**.
6. Under **Tilldelningar** klickar du på **Molnappar eller åtgärder**.
7. På fliken **Inkludera** väljer du **Välj appar** och klickar sedan på **Välj**.
8. På bladet **Välj** väljer du **Microsoft Teams** och **Outlook Groups** och klickar sedan på **Välj**.
9. Under **Tilldelningar** klickar du på **Villkor**.
10. På bladet **Villkor** klickar du på **Klientappar**.
11. På bladet **Klientappar** klickar du på **Ja** för **Konfigurera** och väljer sedan inställningarna **Mobila appar och skrivbordsklienter**.**Exchange ActiveSync-klienter** och **Andra klienter**. Avmarkera kryssrutan **Webbläsare**.

    ![Skärmbild av inställningar för villkorstyrd åtkomst till klientappar i Azure AD](../media/azure-ad-conditional-access-client-mobile.png)

12. Klicka på **Klar**.
13. Under **Åtkomstkontroller** klickar du på **Bevilja**.
14. På bladet **Bevilja** väljer du **Kräv att enheten är markerad som kompatibel** och **Kräv Hybrid Azure AD-kopplad enhet**.
15. Under **För flera kontroller** väljer du **Begär en av de valda kontrollerna** och klickar sedan på **Välj**.
16. På bladet **Nytt**, under **Aktivera princip**, klickar du på **På** och sedan på **Skapa**.

Begränsa gäståtkomsten till endast SharePoint

1. I [Administrationscenter för SharePoint](https://admin.microsoft.com/sharepoint) visar du **Principer** och klickar på **Behörighets kontroll**.
2. Klicka på **Ohanterade enheter**.
3. Markera kryssrutan **Tillåt begränsad åtkomst** bara för webbplatser, och klicka sedan på **Spara**.

Observera att den här inställningen i administrationscentret för SharePoint skapar en princip med stöd för villkorstyrd åtkomst i Azure AD.

## <a name="configure-a-session-timeout-for-guest-users"></a>Konfigurera en tidsgräns för sessioner för gästanvändare

Genom att kräva att gästanvändare ska autentiseras med jämna mellanrum kan du minska risken för att okända användare får åtkomst till organisationens innehåll om en gästanvändares enhet inte är skyddad. Du kan konfigurera en princip för villkorsstyrd åtkomst med sessionstidsgräns för gästanvändare i Azure AD.

Konfigurera en princip för sessionstidsgräns för gäster

1. Gå till [Principer för villkorstyrd åtkomst i Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade).
2. På bladet för **Villkorsstyrd åtkomst – Principer** klickar du på **Ny princip**.
3. I rutan **Namn** skriver du *Sessionstidsgräns för gäst*.
4. Under **Tilldelningar** klickar du på **Användare och grupper**.
5. I bladet **Användare och grupper** markerar du **Välj användare och grupper**, markerar kryssrutan **Alla gäster och externa användare**.
6. Under **Tilldelningar** klickar du på **Molnappar eller åtgärder**.
7. På fliken **Inkludera** väljer du **Välj appar** och klickar sedan på **Välj**.
8. På bladet **Välj** väljer du **Microsoft Teams**, **Office 365 SharePoint Online** och **Outlook Groups** och klickar sedan på **Välj**.
9. Under **Åtkomstkontroller** klickar du på **Session**.
10. På bladet **Session** väljer du **Inloggningsfrekvens**.
11. Välj **1** och **dagar** för tidsperiod och klicka sedan på **Välj**.
12. På bladet **Nytt**, under **Aktivera princip**, klickar du på **På** och sedan på **Skapa**.

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a>Skapa en typ av känslig information för ett strikt känsligt projekt.

Olika typer av känsliga uppgifter är fördefinierade strängar som kan användas i policyarbetsflöden för att upprätthålla efterlevnadskraven. Microsoft 365 Efterlevnadscenter levereras med över 100 känsliga informationstyper, inklusive körkortsnummer, kreditkortsnummer, bankkontonummer osv.

Du kan skapa anpassade typer av känslig information som hjälper dig att hantera innehåll som är specifikt för din organisation. I det här exemplet skapar vi en anpassad typ av känslig information för ett strikt känsligt projekt. Vi kan sedan använda den här typen av känslig information för att automatiskt tillämpa en kanslighetsetikett.

Skapa en typ av känslig information

1. I [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com) går du till vänster navigeringsfält och expanderar **Klassificering** och klickar sedan på **Typer av känslig information**.
2. Klicka på **Skapa**.
3. För **Namn** och **Beskrivning** skriver du **Projekt Saturnus** och klickar sedan på **Nästa**.
4. Klicka på **Lägg till ett element**.
5. I listan **Identifiera innehåll som innehåller** väljer du **Nyckelord** och skriver *Projekt Saturnus* i rutan sökordsrutan.
6. Klicka på **Nästa** och sedan på **Slutför**.
7. Om du tillfrågas om du vill testa typen av känslig information klickar du på **Nej**.

### <a name="more-information"></a>Mer information

[Vanliga typer av känslig information](https://docs.microsoft.com/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-an-auto-labeling-policy-to-assign-a-sensitivity-label-based-on-a-sensitive-information-type"></a>Skapa en princip för automatisk etikettmärkning för att tilldela en känslighetsetikett baserat på en typ av känslig information

Om du använder känslighetsetiketter i din organisation kan du automatiskt använda en etikett på filer som innehåller definierade typer av känsliga uppgifter. 

Skapa en princip för automatisk etikettmärkning

1. Öppna [administrationscentret för Microsoft 365 Efterlevnad](https://compliance.microsoft.com).
2. I det vänstra navigeringsfältet klickar du på **Informationsskydd**.
3. I fliken **Automatisk etikettmärkning** klickar du på **Skapa princip för automatisk etikettmärkning**.
4. På sidan **väljer du den information som du vill att etiketten ska tillämpas på** väljer du **Anpassad** och klickar på **Nästa**.
5. Skriv ett namn och en beskrivning för principen och klicka på **Nästa**.
6. På sidan **Välj platser där du vill använda etikett** aktiverar du **SharePoint-webbplatser** och klickar på **Välj webbplatser**.
7. Lägg till URL: erna för de webbplatser där du vill aktivera Automatisk etikettmärkning och klickar på **Klar**.
8. Klicka på **Nästa**.
9. Välj **Vanliga regler** på sidan **Konfigurera vanliga eller avancerade regler** och klicka på **Nästa**.
10. På sidan **Definiera regler för innehåll på alla platser** klickar du på **Ny regel**.
11. Ge regeln ett namn på sidan **Ny regel** klicka på **Lägg till villkor** och klicka sedan på **Innehållet har typer av känslig information**.
12. Klicka på **Lägg till**, klicka på **Typer av känslig information**, välj vilka typer av känslig information du vill använda, klicka på **Lägg till** och klicka sedan på **Spara**.
13. Klicka på **Nästa**.
14. Klicka på **Välj en etikett**, välj etiketten som du vill använda och klicka sedan **Lägg till**.
15. Klicka på **Nästa**.
16. Lämna principen i simuleringsläge och klicka på **Nästa**.
17. Klicka på **Skapa princip** och välj sedan **Klar**.

När principen har skapats och en användare skriver ”Projekt Saturnus” i ett dokument, kommer principen för automatisk etikettmärkning att automatiskt tillämpa den specificerade etiketten när filen söks igenom.

### <a name="more-information"></a>Mer information

[Använda en känslighetsetikett för innehåll automatiskt](https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically)

## <a name="create-a-dlp-policy-to-remove-guest-access-to-highly-sensitive-files"></a>Skapa en DLP-princip för att ta bort gäståtkomst till strikt känsliga filer

Du kan använda [Dataförlustskydd (DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)) för att förhindra att oönskade gäster delar känsligt innehåll. Dataförlustskydd kan utföra åtgärder baserat på en fils känslighetsetikett och ta bort gäståtkomst.

Skapa en DLP-regel

1. I Microsoft 365 Efterlevnadscenter, gå till sidan [Dataförlustskydd](https://compliance.microsoft.com/datalossprevention).
2. Klicka på **Skapa princip**.
3. Välj **Anpassad** och klicka på **Nästa**.
4. Skriv ett namn för principen och klicka på **Nästa**.
5. På **Platser för att tillämpa principen** Stäng av alla inställningar utom **SharePoint-webbplatser** och **OneDrive-konton** och klicka sedan på **Nästa**.
6. På sidan **Definiera principinställningar** klickar du på **Nästa**.
7. På sidan **Anpassa avancerade DLP-regler** klickar du på **Skapa regel** och anger ett namn på regeln.
8. Under **Villkor** klickar du på **Lägg till villkor** och väljer **Innehållet har**.
9. Om du klickar på **Lägg till** väljer du **Känslighetsetiketter** väljer de etiketter du vill använda och klickar på **Lägg till**.

   ![Skärmbild av alternativ för villkor, typer av känsliga information, känslighetsetiketter och kvarhållningsetiketter.](../media/limit-accidental-exposure-dlp-conditions.png)

10. Under **Åtgärder** klickar du på **Lägg till en åtgärd** och väljer **Begränsa åtkomst eller kryptera innehållet i Microsoft 365 platser**.
11. Välj kryssrutan **Begränsa åtkomst eller kryptera innehållet på Microsoft 365 platser** och välj sedan alternativet **Bara personer utanför din organisation**.

      ![Skärmbild av åtgärdsalternativ för DLP-regler](../media/dlp-remove-guest-access-sensitive-files.png)

12. Klicka på **Spara** och sedan på **Nästa**.
13. Välj testalternativ och klicka på **Nästa**.
14. Klicka på **Skicka** och klicka sedan på **Klart**.

Det är viktigt att tänka på att principen inte tar bort åtkomst om gästen är medlem på webbplatsen eller i teamet som helhet. Om du planerar att ha strikt känsliga dokument på en webbplats eller i ett team med gästmedlemmar, kan du överväga att använda [privata kanaler i Teams](https://support.microsoft.com/office/de3e20b0-7494-439c-b7e5-75899ebe6a0e) och bara tillåta medlemmarna i din organisation i de privata kanalerna.

## <a name="additional-options"></a>Fler alternativ

Det finns några fler alternativ i Microsoft 365 och Azure Active Directory som kan hjälpa till att skydda gästdelningsmiljön.

- Du kan skapa en lista över tillåtna eller nekade delningsdomäner för att begränsa vilka användarna kan dela med. Mer information finns i [Begränsa delning av SharePoint- och OneDrive-innehåll efter domän](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) och [Tillåta eller blockera inbjudningar för B2B-användare från specifika organisationer](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
- Du kan begränsa vilka andra Azure Active Directory-klientorganisationer som användarna kan ansluta till. Mer information finns i [Använda klientorganisationsbegränsningar för att hantera åtkomst till SaaS-molnprogram](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions).
- Du kan skapa en hanterad miljö där partner kan hjälpa dig att hantera gästkonton. Mer information finns i [Skapa ett B2B-extranät med hanterade gäster](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet).

## <a name="see-also"></a>Se även

[Begränsa oavsiktlig exponering för filer när de delas med gäster](share-limit-accidental-exposure.md)

[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Skapa ett B2B-extranät med hanterade gäster](b2b-extranet.md)
