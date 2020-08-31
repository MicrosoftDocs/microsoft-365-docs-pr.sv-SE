---
title: Konfigurera en team med säkerhetsisolering
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Lär dig hur du skapar ett team med en unik känslighetsetikett för säkerhet.
ms.openlocfilehash: 789e75165339f8a834a73aa3fd0d8a2666285ce9
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308189"
---
# <a name="configure-a-team-with-security-isolation"></a>Konfigurera en team med säkerhetsisolering

I den här artikeln får du rekommendationer och anvisningar om hur du konfigurerar privata team i Microsoft Teams och använder en unik känslighetsetikett för att kryptera filer så att bara teammedlemmarna kan dekryptera dem.

Utöver den privata åtkomst som beskrivs i artikeln hur du konfigurerar den associerade SharePoint-webbplatsen. Den når du via avsnittet **Filer** i en teamkanal så att du får den extra säkerhet som krävs för lagring av strikt reglerade data.

Komponenterna i konfigurationen för en grupp med säkerhets isolering är:

- Ett privat team
- Ytterligare säkerhet på den associerade SharePoint-webbplatsen för teamet som:
  - Hindrar medlemmar i webbplatsen från att dela webbplatsen med andra.
  - Hindrar icke-medlemmar av webbplatsen från att begära åtkomst till webbplatsen.
- En känslighetsetikett särskilt för det här teamet:
    - Hindrar åtkomst till SharePoint-innehåll från ohanterade enheter
    - Tillåter eller nekar gäståtkomst till teamet, beroende på dina behov
    - Krypterar dokument som etikett används för

> [!IMPORTANT]
> Kontrollera att du har aktiverat [känslighetsetiketter för att skydda innehåll i Microsoft Teams, Office 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) innan du fortsätter med stegen i den här artikeln.

<a name="poster"></a> En sammanfattning av 2 sidor av det här scenariot finns i [Microsoft Teams med säkerhets isolering med affisch](../downloads/team-security-isolation-poster.pdf).

[![Microsoft Teams med säkerhets isolering, affisch](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)

Du kan också ladda ned den här affischen i [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf)- eller [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pptx)-format och skriva ut den i pappersstorleken letter, legal eller tabloid (11 x 17).

## <a name="initial-protections"></a>Initiala skydd

Läs följande metodtips för att skydda åtkomst till teamet och dess underliggande SharePoint-webbplats:
- [Principer för identitets- och enhetsåtkomst](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)
- [Åtkomstprinciper för SharePoint Online](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).
- [Distribuera teams med grundläggande skydd](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a>Gästdelning

Beroende på företagets natur kan du kanske inte aktivera gästdelning för det här teamet. Om du tänker samarbeta med personer utanför organisationen i teamet aktiverar du gästdelning. 

Information om hur du delar med gäster säkert finns i följande resurser:

- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [Skapa en säker miljö för gästdelning](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

För att tillåta eller blockera gästdelning använder vi en kombination av känslighetsetiketter för teamet och delning på webbplats nivå för den associerade SharePoint-webbplatsen, som vi ser senare.

## <a name="create-a-private-team"></a>Skapa ett privat team

Eftersom vi skapar en känslighetsetikett för det här teamet är nästa steg att skapa teamet. Om du har ett befintligt team kan du använda det.

Skapa en team för känslig information
1. I Teams klickar du på **Teams** till vänster i programmet och sedan på **gå med i eller skapa en teams** längst ned i grupplistan.
2. Klicka på **Skapa team** (första kortet, övre vänstra hörnet).
3. Välj **Skapa ett team från början**.
4. Behåll standardinställningen i listan **Känslighet**.
5. Under **Sekretess**klickar du på **Privat**.
6. Skriv ett namn för det team som är relaterat till det känsliga projektet. **Projekt Saturn**till exempel.
7. Klicka på **Skapa**.
8. Lägg till användare i teamet och klicka sedan på **Stäng**.

## <a name="private-channel-settings"></a>Inställningar för privata kanaler

Vi rekommenderar att du begränsar skapandet av privata kanaler till teamägare.

För att begränsa skapandet av en privat kanal
1. Klicka på **Fler alternativ**i teamet och klicka sedan på **Hantera team**.
2. På fliken **Inställningar**, expandera **medlemsbehörigheter**.
3. Avmarkera kryssrutan **Tillåt att medlemmar skapar privata kanaler**.

Du kan också använda [teamprinciper](https://docs.microsoft.com/MicrosoftTeams/teams-policies) för att styra vem som kan skapa privata kanaler.

## <a name="create-a-sensitivity-label"></a>Skapa en känslighetsetikett

Om du vill konfigurera ett team för säkerhetsisolering kommer vi att använda en känslighetsetikett som skapats specifikt för det här teamet. Etiketten används på teamnivån för att styra gästdelning och för att blockera åtkomst från ohanterade enheter. Den kan också användas för att klassificera och kryptera enskilda filer i gruppen så att bara teamägare och medlemmar kan öppna dem.

Om du har ett intern partner- eller intresseteam som ska kunna visa krypterade dokument men inte redigera dem, kan du lägga till dem i etiketten med endast visningsbehörigheter. Du kan sedan lägga till dessa personer i teamets SharePoint-webbplats med läsarbehörigheter och de kommer att ha skrivskyddad åtkomst till webbplatsen där dokumenten behålls, men inte själva teamet.

Att skapa en känslighetsetikett
1. Öppna [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com).
2. Under **Lösningar**klickar du på **Informationsskydd**.
3. Klicka på **Skapa en etikett**.
4. Skriv ett namn på etiketten som liknar ditt teamnamn. Till exempel **Mycket känslig – Projekt Saturn**.
5. Lägg till ett knapptips och klicka sedan på **Nästa**.
6. I listrutan **Kryptering** på sidan **Kryptering** väljer du **Använd**. 
7. Så här lägger du till teambehörigheter:<br>
  a. Klicka på **Tilldela behörigheter**.<br>
  b. Klicka på **Lägg till användare eller grupper**, markera det team som du har skapat och klicka sedan **lägga till**<br>
  c. Klicka **Välj behörigheter**.<br>
  d. Välj **Samtidig redigering** från listrutan och klicka sedan på **Spara**.<br>
8. Om du vill lägga till användare eller grupper med skrivskyddad åtkomst till filer med etiketten:<br>
  a. Klicka på **Tilldela behörigheter**.<br>
  b. Klicka på **Lägg till användare eller grupper** och välj de användare eller grupper du vill lägga till och klicka sedan på **Lägg till**.<br>
  c. Klicka **Välj behörigheter**.<br>
  d. Välj **Visningsprogram** i listrutan och klicka sedan på **Spara**.<br>
  e. Klicka på **Spara**.
9. Klicka på **Nästa**.
10. Om du vill lägga till ett sidhuvud, en sidfot eller en vattenstämpel automatiskt i filer som klassificeras med den här etiketten går du till sidan **Markering av innehåll**.
11. På sidan **Inställningar för webbplatser och grupper** ställer du **inställningar för webbplatser och grupper** till **På**.
12. I listrutan **Sekretess för gruppanslutna teamwebbplatser i Office 365** väljer du **Privat – endast användare kan komma åt webbplatsen**.
13. Om du vill tillåta gäståtkomst markerar du kryssrutan **Låt gruppägarna för Office 365 lägga till personer utanför organisationen i gruppen**. 
14. Under **Ohanterade enheter**väljer du **Blockera åtkomst**.
15. Klicka på **Nästa**.
16. På sidan **Auto-etiketting för Office-program** klickar du på **Nästa**.
17. Klicka på **Skicka** och klicka sedan **Klart**.

När du har skapat en etikett måste du publicera den till de användare som ska använda den. I det här fallet gör vi etiketten tillgänglig bara för personer i teamet.

Om du vill publicera en känslighetsetikett
1. I Microsoft 365 Efterlevnadscenter väljer du fliken **Etikettprinciper** på sidan **Informationsskydd**.
2. Klicka på **Publicera etiketter**.
3. På sidan **Välj känslighetsetiketter att publicera** klickar du på **Välj känslighetsetiketter att publicera**.
4. Markera de etiketter som du har skapat och klicka sedan på **Lägg till**.
5. Klicka på **Nästa**.
6. På sidan Publicera till användare och grupper klickar du på **Välja användare och grupper**.
7. Klicka på **Lägg till** och välj sedan det team som du har skapat.
8. Klicka på **Lägg till** och sedan på **Klart**.
9. Klicka på **Nästa**.
10. På sidan Principinställningar väljer du kryssrutan **Användare måste ge anledning till att ta bort en etikett eller lägre klassificeringsetikett** och klickar sedan på **Nästa**.
11. Skriv ett namn för principen och klicka sedan på **Nästa**.
12. Klicka på **Skicka** och klicka sedan på **Klart**.

## <a name="apply-the-label-to-the-team"></a>Använda etiketten i teamet

När etiketten har publicerats måste du använda den i teamet för att inställningarna för gästdelning och hanterade enheter ska börja gälla. Det görs i SharePoint Online Administrationscenter. Obs! Det kan ta lite tid innan etiketten blir tillgänglig när den har publicerats.

Använda känslighetsetiketten
1. Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).
2. Under **Webbplatser**klickar du på **Aktiva webbplatser**.
3. Klicka på den webbplats som är kopplad till teamet.
4. På fliken **Principer** klickar du på **Redigera** under **Känslighet**.
5. Markera den etikett som du har skapat och klicka sedan på **Spara**.

## <a name="sharepoint-settings"></a>SharePoint-inställningar

Det finns tre steg att utföra i SharePoint:

- Uppdatera inställningarna för gästdelning för webbplatsen i SharePoint Online Administrationscenter för att matcha det du valde när du skapade etiketten och uppdatera sedan standard delningslänken till *Personer med befintlig åtkomst*.
- Uppdatera inställningarna för webbplatsdelning på själva webbplatsen och förhindra att medlemmar kan dela filer, mappar eller webbplatsen och inaktivera åtkomstförfrågningar.
- Om du har lagt till personer eller grupper till etiketten med behörighet till visningsprogrammet, kan du lägga till dem på SharePoint-webbplatsen med läsbehörigheter.

### <a name="sharepoint-guest-settings"></a>Gästdelning i SharePoint

Den inställning för gästdelning som du valde när du skapade etiketten (som bara påverkar teammedlemskap) ska matcha inställningarna för gästdelning för den associerade SharePoint-webbplatsen på följande sätt:

|Etikettinställning|Inställning för SharePoint-webbplats|
|:------------|:----------------------|
|**Låt Office 365-gruppägare lägga till personer utanför organisationen i gruppen** markerad|**Nya och befintliga gäster** (standard för nya grupper)|
|**Låt Office 365-gruppägare lägga till personer utanför organisationen i gruppen** inte markerad|**Endast personer i organisationen**|

Vi kommer också att uppdatera standardtypen av delnings ’länk för att minska risken för att filer och mappar delas av misstag.

Uppdatera webbplatsinställningar
1. Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).
2. Under **Webbplatser**klickar du på **Aktiva webbplatser**.
3. Klicka på den webbplats som är kopplad till teamet.
4. Klicka på **Redigera** under **Extern delning** på fliken **Principer**.
5. Om du tillät gästdelning när du skapade känslighetsetiketten ska du kontrollera att **Nya och befintligt gäster** har markerats. Om du inte tillåter delning när du skapade etiketten väljer du **Bara personer i organisationen**.
6. Avmarkera kryssrutan **Samma som organisationsnivå** under standardtyp av delningslänk och välj **Personer med befintlig åtkomst**.
7. Klicka på **Spara**.

#### <a name="private-channels"></a>Privata kanaler

Om du lägger till privata kanaler i teamet skapas en ny SharePoint-webbplats med standard delningsinställningar. De här webbplatserna visas inte i SharePoint Online Administrationscenter. Du måste därför använda Windows PowerShell-cmdleten [set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) med följande parametrar för att uppdatera inställningarna för gästdelning:

- `-SharingCapability Disabled` Inaktivera gästdelning (det är aktiverat som standard)
- `-DefaultSharingLinkType Internal` ändra standard delningslänk till *Vissa personer*

Om du inte planerar att använda privata kanaler med ditt team kan det vara bra att inaktivera möjligheten för teammedlemmarna att skapa dem under **medlemsbehörigheter** i [teaminställningar](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).

### <a name="site-sharing-settings"></a>Inställningar för webbplatsdelning

För att se till att SharePoint-webbplatsen inte delas med personer som inte är medlemmar i teamet kan vi begränsa delning till ägare. Vi begränsar även delning av filer och mappar till teamägare. På så sätt ser du till att ägare känner till när en fil delas med någon utanför teamet.

Konfigurera webbplatsdelning endast för ägare
1. Gå till fliken **Allmänt** i teamet som du vill uppdatera i Teams.
2. I verktygsfältet för teamet klickar du på **Filer**.
3. Klicka på ellipsen och sedan på **Öppna i SharePoint**.
4. Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.
5. I fönstret Webbplatsbehörigheter under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.
6. Under **Delningsbehörigheter** väljer du **Endast webbplatsens ägare kan dela filer, mappar och webbplatsen**. Klicka sedan på **Spara**.

### <a name="custom-site-permissions"></a>Anpassade webbplatsbehörigheter

Om du har lagt till personer med visningsbehörighet till känsliga etiketter kan du lägga till dem på SharePoint-webbplatsen med läsåtkomst så att de enkelt kan komma åt filerna.

Bjuda in användare till webbplatsen
1. På sidan klickar du på inställningsikonen och klickar sedan på **Webbplatsbehörigheter**.
2. Klicka **Bjud in personer**och klicka sedan på **dela bara webbplats**.
3. Skriv namnen på de användare och grupper som du vill bjuda in.
4. Om du vill ändra behörigheten för varje person eller grupp som du lägger till kan du ändra deras behörigheter från **Redigera** att **Läsa**.
5. Välj om du vill skicka ett e-postmeddelande med en länk till webbplatsen.
6. Klicka på **Lägg till**.

## <a name="additional-protections"></a>Ytterligare skydd

Microsoft 365 tillhandahåller fler metoder för att skydda innehållet. Överväg att använda följande alternativ för att förbättra säkerheten för din organisation.

- Låt dina gästanvändare godkänna [användningsvillkor](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).
- Konfigurera en [princip om tidsgräns för sessioner](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) för gäster.
- Skapa [känslig informationstyper](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) och Använd [skydd mot dataförlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) för att ange principer för åtkomst av känslig information.
- Använd [Azure Active Directory Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) granskningar för att regelbundet granska teamåtkomst och medlemskap.

## <a name="drive-user-adoption-for-team-members"></a>Driva på teammedlemmarnas användning

Med teamet på plats är det dags att driva på teamets användning och den extra säkerheten för teammedlemmar.

### <a name="train-your-users"></a>Utbilda dina användare

Teamets medlemmar kan komma åt teamet och alla dess resurser, inklusive chattar, möten och andra appar. När du arbetar med filer från avsnittet **Filer** i en kanal ska medlemmarna i teamet ange känslighetsetikett för filerna de skapar.

När etiketten tillämpas krypteras filen. Teamets medlemmar kan öppna och samarbeta i realtid. Om filen lämnar webbplatsen och vidarebefordras till en illvillig användare måste användaren ange autentiseringsuppgifterna för ett användarkonto som är medlem i teamgruppen för att öppna filen och visa innehållet. 

Utbilda dina teammedlemmar i följande:

- Om vikten av att använda det nya teamet för chattar, möten, filer och andra resurser för SharePoint-webbplatsen och konsekvenserna av en läcka av strikt reglerade data, till exempel juridiska aspekter, tillsynsböter, utpressningstrojaner eller förlust av konkurrensfördelar.
- Hur man får åtkomst till teamet.
- Hur man skapar nya filer på webbplatsen och laddar upp nya filer som lagras lokalt.
- Hur du förser filer med rätt känslighetsetikett för teamet.
- Hur etiketten skyddar filer även när de läcker från webbplatsen.

I den här utbildningen ska det ingå praktiska övningar så att teamets medlemmar kan prova funktionerna och se deras resultat.

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a>Utföra regelbundna granskningar av användning och hantera feedback för teammedlemmar

I veckorna efter utbildningen:

- Snabbt hantera feedback från teammedlemmar och finjustera principer och konfigurationer.
- Analysera teamets användning och jämföra med den förväntade användningen.
- Kontrollera att strikt reglerade filer har etiketterats korrekt med den anpassade känslighetsetiketten. (Du kan se vilka filer som har tilldelats en etikett genom att visa en mapp i SharePoint och lägga till kolumnen **Känslighet** genom alternativet **Visa/dölj kolumner** i **Lägg till kolumn**.

Vidareutbilda dina användare efter behov.

## <a name="see-also"></a>Se även

[Azure Active Directory Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)