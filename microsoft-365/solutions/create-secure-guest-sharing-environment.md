---
title: Skapa en säker miljö för gästdelning
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
ms.custom:
- M365solutions
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: I den här artikeln får du lära dig mer om vilka alternativ som finns för att skapa en säker gästdelningsmiljö i Microsoft 365.
ms.openlocfilehash: 848bdef888ab6d6fb20db2a461912f180bfa212c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036130"
---
# <a name="create-a-secure-guest-sharing-environment"></a>Skapa en säker miljö för gästdelning

I den här artikeln går vi igenom en mängd olika alternativ för att skapa en säker gästdelningsmiljö i Microsoft 365. Det här är ett exempel som ger dig en uppfattning om vilka alternativ som är tillgängliga. Du kan använda de här procedurerna i olika kombinationer för att uppfylla organisationens säkerhets- och efterlevnadsbehov. I slutet av artikeln går vi igenom ett testfall för att se hur vissa av dessa alternativ fungerar tillsammans.

I det här scenariot:

- Konfigurera multifaktorautentisering för gäster.
- Konfigurera användarvillkor för gäster.
- Konfigurera kvartalsgranskning av gäståtkomst för att regelbundet verifiera om gästerna fortfarande behöver behörighet till grupper och webbplatser.
- Begränsa gästernas åtkomst till endast på webben för ohanterade enheter.
- Konfigurera en princip för sessionstidsgräns för att säkerställa att gästerna autentiserar sig dagligen.
- Skapa och publicera känslighetsetiketter för att klassificera innehåll.
- Skapa en typ av känslig information för ett strikt känsligt projekt.
- Tilldela automatiskt etiketten *strikt känsligt* till dokument som innehåller den typen av känslig information.
- Ta automatiskt bort gäståtkomst från filer med beteckningen *strikt känsligt*.

Vissa av alternativen som beskrivs i den här artikeln kräver att gästerna har ett konto i Azure Active Directory. Om du vill vara säker på att gästerna ingår i katalogen när du delar filer och mappar med dem, ska du använda [SharePoint- och OneDrive-integrering med förhandsversionen av Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).

Observera att vi inte tar upp inställningarna för gästdelning i den här artikeln. Mer information om hur du aktiverar gästdelning i olika scenarier finns i [Samarbeta med personer utanför organisationen](https://docs.microsoft.com/Office365/Enterprise/collaborate-with-people-outside-your-organization).

## <a name="set-up-multi-factor-authentication-for-guests"></a>Konfigurera multifaktorautentisering för gäster

Multifaktorautentisering minskar kraftigt risken för att ett konto komprometteras. Eftersom gästanvändare kanske använder personliga e-postkonton som inte följer några principer för kontroll eller bästa praxis är det särskilt viktigt att kräva multifaktorautentisering för gäster. Om en gästanvändares användarnamn och lösenord blir stulna, minskar en andra autentiseringsfaktor avsevärt risken för att okända personer ska få åtkomst till webbplatserna och filerna.

I det här exemplet konfigurerar vi multifaktorautentisering för gäster genom att använda en princip för villkorsstyrd åtkomst i Azure Active Directory.

Konfigurera multifaktorautentisering för gäster
1. Sök efter *Villkorsstyrd åtkomst* i Microsoft Azure.
2. På bladet för **Villkorsstyrd åtkomst – Principer** klickar du på **Ny princip**.
3. I fältet **Namn** skriver du *Multifaktorautentisering för gäst*.
4. Under **Tilldelningar** klickar du på **Användare och grupper**.
5. På bladet **Användare och grupper** väljer du **Välj användare och grupper**, markerar kryssrutan **Alla gäster och externa användare** och klickar sedan på **Klar**.
4. Under **Åtkomstkontroller** klickar du på **Bevilja**.
5. På bladet **Bevilja** markerar du kryssrutan **Kräv multifaktorautentisering** och klickar sedan på **Välj**.
6. På bladet **Nytt**, under **Aktivera princip**, klickar du på **På** och sedan på **Skapa**.

Gästen måste då registrera sig för multifaktorautentisering för att de ska kunna komma åt delat innehåll, webbplatser eller team.

### <a name="more-information"></a>Mer information

[Planera en molnbaserad distribution av Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a>Konfigurera användarvillkor för gäster

Vanligtvis kanske gästanvändare inte har undertecknat avtal eller andra juridiska avtal med din organisation. Du kan kräva att gästerna godkänner användningsvillkor innan de kan komma åt filer som delas med dem. Användningsvillkoren kan visas första gången de försöker få åtkomst till en delad fil eller webbplats.

Om du vill skapa användningsvillkor måste du först skapa dokumentet i Word eller något annat redigeringsprogram och sedan spara det som en PDF-fil. Filen kan sedan laddas upp till Azure AD.

Skapa användningsvillkor för Azure AD
1. Logga in på Azure som global administratör, säkerhetsadministratör eller administratör för villkorsstyrd åtkomst.
2. Gå till [Användningsvillkor](https://aka.ms/catou).
3. Klicka på **Nya villkor**.</br>
   ![Skärmbild av inställningar för nya användningsvillkor för Azure AD](../media/azure-ad-guest-terms-of-use.png)
4. I rutorna **Namn** och **Visningsnamn** skriver du *Användningsvillkor för gäster*.
6. För **Dokument med användningsvillkor** bläddrar du till den PDF-fil som du har skapat och väljer den.
7. Välj språk för dokumentet med användningsvillkor.
8. Ange **Kräv att användarna expanderar användningsvillkoren** som **På**.
9. Under **Villkorsstyrd åtkomst**, i listan **Tvinga med mallar för princip för villkorsstyrd åtkomst**, väljer du **Skapa princip för villkorsstyrd åtkomst senare**.
10. Klicka på **Skapa**.

När du har skapat användningsvillkoren är nästa steg att skapa en princip för villkorsstyrd åtkomst som visar användningsvillkoren för gästanvändare.

Skapa princip för villkorsstyrd åtkomst
1. Sök efter *Villkorsstyrd åtkomst* i Microsoft Azure.
2. På bladet för **Villkorsstyrd åtkomst – Principer** klickar du på **Ny princip**.
3. I rutan **Namn** skriver du *Princip för användningsvillkor för gästanvändare*.
4. Under **Tilldelningar** klickar du på **Användare och grupper**.
5. På bladet **Användare och grupper** väljer du **Välj användare och grupper**, markerar kryssrutan **Alla gäster och externa användare** och klickar sedan på **Klar**.
6. Under **Tilldelningar** klickar du på **Molnappar eller åtgärder**.
7. På fliken **Inkludera** väljer du **Välj appar** och klickar sedan på **Välj**.
8. På bladet **Välj** väljer du **Microsoft Teams**, **Office 365 SharePoint Online** och **Outlook Groups** och klickar sedan på **Välj**.
9. På bladet **Molnappar och åtgärder** klickar du på **Klar**.
10. Under **Åtkomstkontroller** klickar du på **Bevilja**.
11. På bladet **Bevilja** väljer du **Användningsvillkor för gäster**och klickar sedan på **Välj**.
12. På bladet **Nytt**, under **Aktivera princip**, klickar du på **På** och sedan på **Skapa**.

Första gången en gästanvändare försöker komma åt innehåll, ett team eller en webbplats i organisationen måste de acceptera villkoren för användning.

### <a name="more-information"></a>Mer information
[Användningsvillkor för Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a>Konfigurera granskning av gäståtkomst

Med åtkomstgranskningar i Azure AD kan du automatisera en återkommande granskning av användaråtkomst till olika team och grupper. Genom att begära åtkomstgranskning specifikt för gäster kan du bidra till att gästanvändare inte behåller åtkomsten till organisationens känsliga information under längre tid än nödvändigt.

Åtkomstgranskningar kan organiseras i program. Ett program är en gruppering av liknande åtkomstgranskningar som kan användas för att organisera åtkomstgranskningar för rapporter och granskningsändamål.

I det här exemplet skapar vi ett program för granskning av gäståtkomst.

Skapa ett program
1. Logga in på Azure-portalen och öppna sidan [Identitetsstyrning](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade).
2. I den vänstra menyn klickar du på **Program**
3. Klicka på **Nytt program**.
4. I rutan **Namn** skriver du *Program för granskning av gäståtkomst*.
5. I rutan **Beskrivning** skriver du *Program för granskning av gäståtkomst*.
6. Klicka på **Skapa**.

När programmet har skapats kan vi skapa en granskning av gäståtkomsten och koppla den till programmet.

Konfigurera åtkomstgranskning av gästanvändare
1. På sidan [Identitetsstyrning](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade) klickar du på **Åtkomstgranskningar** i den vänstra menyn.
2. Klicka på **Ny åtkomstgranskning**.</br>
   ![Skärmbild av inställningar för åtkomstgranskning i Azure AD](../media/azure-ad-create-access-review.png)
3. I rutan **Namn** skriver du *Kvartalsgranskning av gäståtkomst*.
4. För **Frekvens** väljer du **Varje kvartal**.
5. För **Slut**väljer du **Aldrig**.
6. För **Omfång** väljer du **Enbart gästanvändare**.
7. Klicka på **Grupp**, markera de grupper som du vill ska ingå i åtkomstgranskningen och klicka sedan på **Välj**.
8. Under **Program** klickar du på **Länka till program**.
9. På bladet **Välj ett program** väljer du **Program för granskning av gäståtkomst**
10. Klicka på **Start**.

En separat åtkomstgranskning skapas för varje grupp som du anger. Gruppägare för varje grupp kommer att få ett e-postmeddelande varje kvartal för att godkänna eller neka gäståtkomst till sina grupper.

Det är viktigt att du noterar att gäster kan beviljas åtkomst till team eller grupper, eller till enskilda filer och mappar. När de får åtkomst till filer och mappar kanske gästerna inte läggs till i någon särskild grupp. Om du vill göra åtkomstgranskningar för gästanvändare som inte tillhör ett team eller en grupp kan du skapa en dynamisk grupp i Azure AD för alla gäster och sedan skapa en åtkomstgranskning för den gruppen.

### <a name="more-information"></a>Mer information
[Hantera gäståtkomst med åtkomstgranskningar i Azure AD](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[Skapa en åtkomstgranskning av grupper eller program i åtkomstgranskningar i Azure AD](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guest-users"></a>Konfigurera endast webbåtkomst för gästanvändare

Du kan minska din attackyta och underlätta administrationen genom att kräva att gästanvändarna bara får åtkomst till dina team, webbplatser och filer med hjälp av en webbläsare. Det gör du med en princip för villkorsstyrd åtkomst i Azure AD.

Begränsa gäståtkomsten till endast webben
1. Sök efter *Villkorsstyrd åtkomst* i Microsoft Azure.
2. På bladet för **Villkorsstyrd åtkomst – Principer** klickar du på **Ny princip**.
3. I rutan **Namn** skriver du *Webbläsaråtkomst för gästanvändare*.
4. Under **Tilldelningar** klickar du på **Användare och grupper**.
5. På bladet **Användare och grupper** väljer du **Välj användare och grupper**, markerar kryssrutan **Alla gäster och externa användare** och klickar sedan på **Klar**.
6. Under **Tilldelningar** klickar du på **Molnappar eller åtgärder**.
7. På fliken **Inkludera** väljer du **Välj appar** och klickar sedan på **Välj**.
8. På bladet **Välj** väljer du **Microsoft Teams**, **Office 365 SharePoint Online** och **Outlook Groups** och klickar sedan på **Välj**.
9. På bladet **Molnappar och åtgärder** klickar du på **Klar**.
10. Under **Tilldelningar** klickar du på **Villkor**.
11. På bladet **Villkor** klickar du på **Klientappar**.
12. På bladet **Klientappar** klickar du på **Ja** för **Konfigurera** och väljer sedan inställningarna **Mobila appar och skrivbordsklienter** och **Moderna autentiseringsklienter**.</br>
    ![Skärmbild av inställningar för villkorlig åtkomst till klientappar i Azure AD](../media/azure-ad-conditional-access-client-mobile.png)
13. Klicka på **Klar**, och därefter på bladet **Villkor** klickar du på **Klar** igen.
14. Under **Åtkomstkontroller** klickar du på **Bevilja**.
15. På bladet **Bevilja** väljer du **Kräv att enheten är markerad som kompatibel** och **Kräv Hybrid Azure AD-kopplad enhet**.
16. Under **För flera kontroller** väljer du **Begär en av de valda kontrollerna** och klickar sedan på **Välj**.
17. På bladet **Nytt**, under **Aktivera princip**, klickar du på **På** och sedan på **Skapa**.

## <a name="configure-a-session-timeout-for-guest-users"></a>Konfigurera en tidsgräns för sessioner för gästanvändare

Genom att kräva att gästanvändare ska autentiseras med jämna mellanrum kan du minska risken för att okända användare får åtkomst till organisationens innehåll om en gästanvändares enhet inte är skyddad. Du kan konfigurera en princip för villkorsstyrd åtkomst med sessionstidsgräns för gästanvändare i Azure AD.

Konfigurera en princip för sessionstidsgräns för gäster
1. Sök efter *Villkorsstyrd åtkomst* i Microsoft Azure.
2. På bladet för **Villkorsstyrd åtkomst – Principer** klickar du på **Ny princip**.
3. I rutan **Namn** skriver du *Sessionstidsgräns för gäst*.
4. Under **Tilldelningar** klickar du på **Användare och grupper**.
5. På bladet **Användare och grupper** väljer du **Välj användare och grupper**, markerar kryssrutan **Alla gäster och externa användare** och klickar sedan på **Klar**.
6. Under **Tilldelningar** klickar du på **Molnappar eller åtgärder**.
7. På fliken **Inkludera** väljer du **Välj appar** och klickar sedan på **Välj**.
8. På bladet **Välj** väljer du **Microsoft Teams**, **Office 365 SharePoint Online** och **Outlook Groups** och klickar sedan på **Välj**.
9. På bladet **Molnappar och åtgärder** klickar du på **Klar**.
10. Under **Åtkomstkontroller** klickar du på **Session**.
11. På bladet **Session** väljer du **Inloggningsfrekvens**.
12. Välj **1** och **dagar** för tidsperiod och klicka sedan på **Välj**.
13. På bladet **Nytt**, under **Aktivera princip**, klickar du på **På** och sedan på **Skapa**.

## <a name="create-sensitivity-labels"></a>Skapa känslighetsetiketter

Du kan använda känslighetsetiketter på flera olika sätt för att klassificera och skydda organisationens information. I det här exemplet ska vi titta närmare på hur etiketter kan användas för att hantera gäståtkomst till delade filer och mappar.

Först skapar vi tre känslighetsetiketter i Microsoft 365 Efterlevnadscenter:

- Allmänt
- känsligt
- Strikt känsligt

Använd följande procedur för att skapa etiketterna *Allmänt* och *känsligt*.

Skapa en klassificeringsetikett (allmänt och känsligt)
1. I [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com) går du till vänster navigeringsfält och expanderar **Klassificering** och klickar sedan på **Känslighetsetiketter**.
2. Klicka på **Skapa en etikett**.
3. I **Etikettnamn** skriver du *Allmänt* eller *känsligt*.
4. I **Knappbeskrivning** skriver du *Allmän information som kan delas med medarbetare, gäster och partner* eller *känslig information. Dela endast med medarbetare och auktoriserade gäster* och klicka sedan på **Nästa**.
5. Lämna kryptering på **Av** och klicka på **Nästa**.
6. Lämna märkning av innehåll på **Av** och klicka på **Nästa**.
7. Lämna dataförlustskydd för slutpunkt på **Av** och klicka på **Nästa**.
8. Lämna automatiska etiketter på **Av** och klicka på **Nästa**.
9. Klicka på **Skapa**.

Med etiketten *Strikt känsligt* kan vi lägga till automatisk vattenstämpel av dokument med etiketten.

Skapa en klassificeringsetikett (strikt känsligt)
1. Klicka på **Skapa en etikett**.
2. I **Etikettnamn** skriver du *Strikt känsligt*.
3. I **Knappbeskrivning** skriver du *Strikt känslig information. Dela inte med gäster* och klickar sedan på **Nästa**.
4. Lämna kryptering på **Av** och klicka på **Nästa**.
5. Aktivera märkning av innehåll med **På**, markera kryssrutan **Lägg till en rubrik** och klicka sedan på **Anpassa text**.
6. Skriv *Strikt känsligt* som rubriktext och klicka på **Spara**.
7. På sidan **Märkning av innehåll** aktiverar du detta med **På**.
8. Markera kryssrutan **Lägg till en vattenstämpel** och klicka sedan på **Anpassa text**.
9. För **Text för vattenstämpel** skriver du *Strikt känsligt*.
10. Skriv *24* som **Teckenstorlek** och klicka sedan på **Spara**.
11. På sidan **Märkning av innehåll** klickar du på **Nästa**.
12. Lämna dataförlustskydd för slutpunkt på **Av** och klicka på **Nästa**.
13. Lämna automatiska etiketter på **Av** och klicka på **Nästa**.
14. Klicka på **Skapa**.

![Skärmbild av känslighetsetiketter i Microsoft 365 Efterlevnadscenter](../media/microsoft-365-sharing-sensitivity-labels.png)

När du har skapat etiketterna är nästa steg att publicera dem. 

Publicera etiketter
1. På sidan **Känslighetsetiketter** klickar du på **Publicera etiketter**.
2. Klicka på **Välj etiketter att publicera**.
3. Klicka på **Lägg till**, markera de etiketter som du har skapat och klicka sedan på **Lägg till**.
4. Klicka på **Klar**.
5. Klicka på **Nästa**.
6. Lämna de användare och grupper som angetts till **Alla** och klicka på **Nästa**.
7. I listan **Använd den här etiketten som standard för dokument och e-post** väljer du **Allmänt** och sedan **Nästa**.
8. På sidan **Principinställningar** skriver du *Dokumentkänslighet* som namn och klickar sedan på **Nästa**.
9. Klicka på **Publicera**.

När etiketterna är publicerade är de tillgängliga för användare av Office-datorprogram. När användarna använder etiketten **Strikt känsligt** läggs en vattenstämpel automatiskt till i dokumentet.

### <a name="more-information"></a>Mer information
[Översikt över känslighetsetiketter](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a>Skapa en typ av känslig information för ett strikt känsligt projekt.

Olika typer av känsliga uppgifter är fördefinierade strängar som kan användas i policyarbetsflöden för att upprätthålla efterlevnadskraven. Microsoft 365 Efterlevnadscenter levereras med över 100 känsliga informationstyper, inklusive körkortsnummer, kreditkortsnummer, bankkontonummer osv.

Du kan skapa anpassade typer av känslig information som hjälper dig att hantera innehåll som är specifikt för din organisation. I det här exemplet skapar vi en anpassad typ av känslig information för ett strikt känsligt projekt. Vi kan sedan använda den här typen av känslig information för att automatiskt tillämpa en klassificeringsetikett.

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

## <a name="create-a-policy-to-assign-a-label-based-on-a-sensitive-information-type"></a>Skapa en princip för att tilldela en etikett baserat på en typ av känslig information

När typen av känslig information har skapats kan vi skapa en filprincip i Microsoft Cloud App Security för att tillämpa etiketten *Strikt känsligt* på dokument som innehåller strängen *Projekt Saturnus* automatiskt.

> [!NOTE]
> Det finns en replikeringsprocess som gör känslighetsetiketter tillgängliga i Cloud App Security. Du kanske inte ser etiketten som är tillgänglig för en princip direkt.

Skapa en filprincip baserad på typen av känslig information
1. Öppna [Microsoft Cloud App Security](https://portal.cloudappsecurity.com).
2. I det vänstra navigeringsfältet expanderar du **Kontroll** och klickar sedan på **Principer**.
3. Klicka på **Skapa princip** och välj sedan **Filprincip**.
4. Som **Principnamn** skriver du *Etikettering för Projekt Saturnus*.
5. Under **Skapa ett filter för de filer som den här principen ska riktas in på** klickar du på X två gånger för att ta bort standardfiltren.
7. I listan **Välj ett filter** väljer du **App** och sedan **Microsoft SharePoint Online** i listan **Välj appar...**.
8. Under **Inspektionsmetod** väljer du **Dataklassificeringstjänst**.
9. I listan **Välj inspektionstyp** väljer du **Typ av känslig information**.
10. Sök efter och välj känslighetsetiketten *Projekt Saturnus* och klicka sedan på **Klar**.</br>
   ![Skärmbild av inställningar för Cloud App Security-inspektionsmetod](../media/mcas-sensitive-info-type-project-saturn.png)
11. Under **Styrning** expanderar du **Microsoft SharePoint Online**.
12. Markera kryssrutan **Tillämpa klassificeringsetikett** och välj etiketten **Strikt känsligt**.
13. Klicka på **Skapa**.

När principen har skapats och en användare skriver ”Projekt Saturnus” i ett dokument, kommer Cloud App Security att automatiskt tillämpa etiketten *Strikt känsligt* när filen söks igenom.

### <a name="more-information"></a>Mer information
[Filprinciper](https://docs.microsoft.com/cloud-app-security/data-protection-policies)

## <a name="create-a-policy-to-remove-guest-access-to-highly-sensitive-files"></a>Skapa en princip för att ta bort gäståtkomst till strikt känsliga filer

I exemplet i den här artikeln ska filer med etiketten *Strikt känsligt* inte delas med gäster. Vi kan skapa en filprincip i Cloud App Security som automatiskt tar bort gäståtkomst från filer med den etiketten.

Observera att det inte hindrar användarna från att dela eller dela vidare dessa filer. Du är fortfarande beroende av att användarna följer dina styrprinciper för filer som lagras på webbplatser som tillåter gästdelning. Men det kan vara ett användbart verktyg för att ta bort gäståtkomst från filer där känslig information läggs till efter det att de har delats med gäster.

Skapa en etikettbaserad filprincip
1. Öppna [Microsoft Cloud App Security](https://portal.cloudappsecurity.com).
2. I det vänstra navigeringsfältet expanderar du **Kontroll** och klickar sedan på **Principer**.
3. Klicka på **Skapa princip** och välj sedan **Filprincip**.
4. Som **Principnamn** skriver du *Projekt Saturnus – ta bort gäståtkomst*.
5. Under **Skapa ett filter för de filer som den här principen ska riktas in på** klickar du på X två gånger för att ta bort standardfiltren.
6. I listan **Välj ett filter** väljer du **App** och sedan **Microsoft SharePoint Online** i listan **Välj appar...**.
7. Klicka på **Lägg till ett filter**.
8. I listan **Välj ett filter** väljer du **Klassificeringsetikett** och sedan **Azure Information Protection** i listan **Välj filter...**.
9. I listan **Välj klassificeringsetikett** väljer du **Strikt känsligt**.</br>
   ![Skärmbild av filterinställningar för Cloud App Security-princip](../media/mcas-sharepoint-confidential-label-filter.png)
10. Under **Styrning** expanderar du **Microsoft SharePoint Online**.
11. Markera kryssrutorna **Skicka principmatchningssammandrag till filens ägare** och **Ta bort externa användare**.
12. Skriv *Den här filen är strikt känslig. Företagets policy tillåter inte att den delas med gäster* i det anpassade meddelandet.
13. Klicka på **Skapa**.

Det är viktigt att tänka på att principen tar bort åtkomst för filer som delas med hjälp av länken *Specifika personer*. Den tar inte bort åtkomst från oautentiserade länkar (*Alla*). Den tar inte heller bort åtkomst om gästen är medlem på webbplatsen eller i teamet som helhet. Om du planerar att ha strikt känsliga dokument på en webbplats eller i ett team med gästmedlemmar, kan du överväga att använda [privata kanaler i Teams](https://support.office.com/article/60ef929a-4d68-418b-bf4f-5784db184ec9) och bara tillåta medlemmarna i din organisation i de privata kanalerna.

## <a name="test-the-solution"></a>Testa lösningen

Om du vill testa lösningen som beskrivs i den här artikeln kan du skapa ett Word-dokument och spara det i ett dokumentbibliotek. Dela filen med en gästanvändare. När gästen försöker nå dokumentet ska de behöva registrera sig för multifaktorautentisering och sedan acceptera användningsvillkoren.

När gästen har åtkomst till dokumentet skriver du *Projekt Saturnus* i dokumentet och sparar det. När Cloud App Security läser av dokumentet bör etiketten *Strikt känsligt* tillämpas och gästanvändaren bör inte längre ha åtkomst till det.

Du kan använda verktygen som beskrivs i den här artikeln i olika kombinationer för att skapa en produktiv men säker gästdelningsmiljö för din organisation.

## <a name="additional-options"></a>Fler alternativ

Det finns några fler alternativ i Microsoft 365 och Azure Active Directory som kan hjälpa till att skydda gästdelningsmiljön.

- Du kan skapa en lista över tillåtna eller nekade delningsdomäner för att begränsa vilka användarna kan dela med. Mer information finns i [Begränsa delning av SharePoint- och OneDrive-innehåll efter domän](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) och [Tillåta eller blockera inbjudningar för B2B-användare från specifika organisationer](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
- Du kan begränsa vilka andra Azure Active Directory-klientorganisationer som användarna kan ansluta till. Mer information finns i [Använda klientorganisationsbegränsningar för att hantera åtkomst till SaaS-molnprogram](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions).
- Du kan skapa en hanterad miljö där partner kan hjälpa dig att hantera gästkonton. Mer information finns i [Skapa ett B2B-extranät med hanterade gäster](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet).

## <a name="see-also"></a>Se även

[Begränsa oavsiktlig exponering för filer när de delas med gäster](share-limit-accidental-exposure.md)

[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Skapa ett B2B-extranät med hanterade gäster](b2b-extranet.md)
