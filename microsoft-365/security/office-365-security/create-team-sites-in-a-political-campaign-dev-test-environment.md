---
title: Skapa gruppwebbplatser – politisk kampanj utv miljö
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/21/2018
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.custom: seo-marvel-apr2020
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: 'Sammanfattning: Skapa offentliga, privata, känsliga och strikt konfidentiella SharePoint Online-gruppwebbplatser i utvecklings-/testmiljön för din politiska kampanj.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ba0eb1e3ff0539f9aec6993fb25fe576f08f84d5
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028781"
---
# <a name="create-team-sites-in-a-political-campaign-devtest-environment"></a>Skapa gruppwebbplatser i en utvecklings-/testmiljö för en politisk kampanj

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**

- [Microsoft Defender för Office 365 abonnemang 2](defender-for-office-365.md)

 **Sammanfattning:** Skapa offentliga, privata, känsliga och strikt konfidentiella SharePoint Online-gruppwebbplatser i utvecklings-/testmiljön för din politiska kampanj. 
   
Följ anvisningarna i den här artikeln om du vill skapa en utvecklings-/testmiljö med fyra olika typer av SharePoint Online-gruppwebbplatser för lösningen [Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra snabbrörliga organisationer](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md). De här webbplatserna beskrivs i detalj i avsnitt 10, **SharePoint och OneDrive för företag**.

## <a name="phase-1-create-your-political-campaign-devtest-environment"></a>Fas 1: Skapa en utvecklings-/testmiljö för din politiska kampanj

Börja med att följa anvisningarna i [Konfigurera grupper och användare till en utvecklings-/testmiljö för en politisk kampanj](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md) och skapa prenumerationer, användare och grupper.

## <a name="phase-2-create-labels"></a>Steg 2: Skapa etiketter

I den här fasen skapar du etiketter för dokumentmapparna med olika säkerhetsnivåer för SharePoint Online-gruppwebbplatsen.

1. Om det behövs loggar du in på administrationscentret med autentiseringsuppgifterna för utvärderingsprenumerationens globala administratörskonto. Mer information finns i [Så här loggar du in i Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. På fliken **Microsoft Office Home** klickar du på panelen **Administratör**.

3. På den nya fliken **Administrationscenter för Microsoft 365** i webbläsaren klickar du på **Administrationscenter > Säkerhet  efterlevnad**.

4. Från den nya fliken **Hem – Säkerhet och efterlevnad** i din webbläsare klickar du på **Klassificeringar > Etiketter**.

5. I fönstret **Start > Etiketter** klickar du på **Skapa en etikett**.

6. I fönstret **Namnge din etikett** skriver du **Internt**. Klicka sedan på **Nästa**.

7. I fönstret **Etikettinställningar** klickar du på **Nästa**.

8. I fönstret **Granska inställningarna** klickar du på **Skapa den här etiketten** och sedan på **Stäng**.

9. Upprepa steg 5–8 för följande ytterligare etiketter:

   - Privat
   - Känslig
   - Strikt konfidentiellt

10. I fönstret **Start > Etiketter** klickar du på **Publicera etiketter**.

11. Klicka på **Välj etiketter att publicera** i fönstret **Välj etiketter att publicera**.

12. I fönstret **Välj etiketter** klickar du på **Lägg till** och markerar alla fyra etiketterna.

13. Klicka på **Klar**.

14. I fönstret **Välj etiketter att publicera** klickar du på **Nästa**.

15. Klicka på **Nästa** i fönstret **Välj platser**.

16. I fönstret **Namnge principen** skriver du **Kampanj** i **Namn** och klickar sedan på **Nästa**.

17. I fönstret **Granska inställningarna** klickar du på **Publicera etiketter** och sedan på **Stäng**.

## <a name="phase-3-create-your-sharepoint-online-team-sites"></a>Fas 3: Skapa gruppwebbplatser i SharePoint Online

I den här fasen skapar och konfigurerar du SharePoint Online-gruppwebbplatser för din politiska kampanj som motsvarar de fyra typerna av SharePoint Online-gruppwebbplatser.

### <a name="campaign-wide-team-site"></a>Kampanjens hela gruppwebbplats

Gör så här om du vill skapa en offentlig baslinje för SharePoint Online-gruppwebbplatsen:

1. Om det behövs kan du använda en webbläsare på din lokala dator och logga in på administrationscentret (<https://admin.microsoft.com>) med ditt globala administratörskonto.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.

4. På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.

5. I **Webbplatsnamn** skriver du **Hela kampanjen**.

6. I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för hela kampanjen**.

7. I **Sekretessinställningar** väljer du **Offentlig – alla i organisationen har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.

8. I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.

Därefter konfigurerar du dokumentmappen för kampanjens gruppwebbplats med en intern etikett.

1. På fliken **Hela kampanjen-Start** i webbläsaren klickar du på **Dokument**.

2. Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. 

3. Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. 

4. I **Inställningar-Använd etikett** väljer du **Internt**. Klicka sedan på **Spara**.

### <a name="campaign-project-1-team-site"></a>Gruppwebbplats för kampanjens projekt 1

Om du vill skapa en baslinje för en privat SharePoint Online-gruppwebbplats till ett projekt i kampanjen, gör du så här:

1. Om det behövs kan du använda en webbläsare på din lokala dator och logga in på administrationscentret (<https://admin.microsoft.com>) med ditt globala administratörskonto.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.

4. På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.

5. I **Webbplatsnamn** skriver du **Kampanj, projekt 1**.

6. I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för kampanj, projekt 1**.

7. I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.

8. I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.

Därefter konfigurerar du en privat etikett till dokumentmappen för kampanjens gruppwebbplats för projekt 1.

1. På fliken **Kampanj, projekt 1-Start** i webbläsaren klickar du på **Dokument**.

2. Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. 

3. Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. 

4. I **Inställningar-Använd etikett** väljer du **Privat**. Klicka sedan på **Spara**.

### <a name="campaign-marketing-team-site"></a>Gruppwebbplats för kampanjmarknadsföring

Gör så här om du vill skapa en känslighetsnivå för en isolerad SharePoint Online-gruppwebbplats för kampanjmarknadsföringsresurser:

1. Använd webbläsaren på din lokala dator och logga in på administrationscentret (<https://admin.microsoft.com>) med ditt globala administratörskonto.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.

4. På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.

5. Skriv **Kampanjmarknadsföring** i **Namn på gruppwebbplats**.

6. I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för kampanjmarknadsföring (känslig)**.

7. I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.

8. I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.

9. Gå till den nya fliken **Kampanjmarknadsföring** i webbläsaren. Klicka på inställningsikonen i verktygsfältet och sedan på **Webbplatsbehörigheter**.

10. I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.

11. Klicka på **Inställningar för åtkomstbegäran** på den nya fliken **Behörigheter** i webbläsaren.

12. I dialogrutan **Inställningar för åtkomstbegäran** avmarkerar du kryssrutorna **Tillåt medlemmar att dela webbplats och enskilda filer och mappar** och **Tillåt medlemmar att bjuda in andra till webbplatsens medlemsgrupp**. Skriv **ITAdmin1@**\<your organization name\> **.onmicrosoft.com** i **Skicka alla åtkomstbegäranden** och klicka sedan på **OK**.

13. Klicka på **Kampanjmarknadsföring-Medlemmar** i listan.

14. På sidan **Personer och grupper** klickar du på **Nytt**.

15. I dialogrutan **Dela** skriver du **Seniora och strategisk personal**, markerar den och klickar sedan på **Dela**.

16. Upprepa steg 14 och 15 för gruppen **Analyspersonal** och användarkontot **Regular1**.

17. Klicka på bakåtknappen i webbläsaren.

18. Klicka på **Kampanjmarknadsföring-Ägare** i listan.

19. På sidan **Personer och grupper** klickar du på **Nytt**.

20. I dialogrutan **Dela** skriver du **IT-personal**, markerar det och klickar sedan på **Dela**.

21. Klicka på bakåtknappen i webbläsaren.

22. Stäng fliken **Personer och grupper** i webbläsaren, klicka på fliken **Kampanjmarknadsföring-Start** i webbläsaren och stäng sedan fönstret **Webbplatsbehörigheter**.

Här är resultatet av att konfigurera behörigheter:

- SharePoint-gruppen **Kampanjmarknadsföring-Medlemmar** innehåller bara gruppen **Seniora och strategisk personal** (som innehåller användarkontona Candidate, ChiefOfStaff och Strategic1), gruppen **Kampanjmarknadsföring** (som innehåller det globala administratörsanvändarkontot), gruppen **Analyspersonal** (som innehåller användarkontot DataScientist1) och användarkontot **Regular1**.

- SharePoint-gruppen **Kampanjmarknadsföring-Ägare** innehåller bara gruppen **IT-personal** (som bara innehåller användarkontona ITAdmin1 och ITAdmin2).

- SharePoint-gruppen **Kampanjmarknadsföring-Besökare** innehåller inga grupp- eller användarkonton.

- Medlemmar kan inte ändra behörigheter på webbplatsnivå (detta kan bara utföras av medlemmar i gruppen **Kampanjmarknadsföring-Ägare**).

- Andra användarkonton saknar åtkomst till webbplatsen eller dess resurser, men kan begära åtkomst till webbplatsen. Ett e-postmeddelande skickas då till postlådan för ITAdmin1-användarkontot.

Därefter konfigurerar du dokumentmappen för kampanjmarknadsföringens gruppwebbplats med etiketten Känslig.

1. På fliken **Kampanjmarknadsföring-Start** i webbläsaren klickar du på **Dokument**.

2. Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. 

3. Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. 

4. I **Inställningar-Använd etikett** väljer du **Känslig** och klickar sedan på **Spara**.

Därefter konfigurerar du en princip för dataförlustskydd (DLP) som meddelar användarna när de delar ett dokument med etiketten Känslig på en SharePoint Online-gruppwebbplats utanför organisationen. DLP-principen används för resurser som finns på kampanjmarknadsföringens webbplats.

1. På fliken **Microsoft Office Home** i webbläsaren genom att klicka på **Säkerhet och efterlevnad**.

2. På den nya fliken **Säkerhet och efterlevnad** i din webbläsare klickar du på **dataförlustskydd > Policy**.

3. I fönstret **Dataförlustskydd** klickar du på **+ Skapa en princip**.

4. I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassa** och sedan på **Nästa**.

5. I fönstret **Namnge principen** skriver du **Etiketten Känslig, SharePoint Online-gruppwebbplatser** i **Namn**. Klicka sedan på **Nästa**.

6. I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.

7. Inaktivera platserna **Exchange-e-post** och **OneDrive-konton** i listan med platser och klicka sedan på **Nästa**.

8. I fönstret **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Redigera**.

9. I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och sedan på **Etiketter**.

10. I fönstret **Etikett** klickar du på **+ Lägg till**, väljer etiketten **Känslig**, klickar på **Lägg till** och sedan på **Klar**.

11. I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.

12. I **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Nästa**.

13. I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.

14. I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.

15. I textrutan skriver du eller klistrar in följande:

    - Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den. Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord. Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.

16. Klicka på **OK**.

17. I fönstret **Vad vill du göra om vi identifierar känslig information?** avmarkerar du kryssrutan **Blockera andra från att dela och begränsa åtkomsten till delat innehåll**, och klickar sedan på **Nästa**.

18. I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.

19. I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.

### <a name="campaign-strategy-team-site"></a>Gruppwebbplats för kampanjstrategi

Gör så här om du vill skapa en isolerad SharePoint Online-gruppwebbplats med hög sekretessnivå för kampanjstrategiresurser:

1. Om det behövs kan du använda en webbläsare på din lokala dator och logga in på administrationscentret (<https://admin.microsoft.com>) med ditt globala administratörskonto.

2. Klicka på **SharePoint** i listan med paneler.

3. På den nya fliken **SharePoint** i webbläsaren klickar du på **+ Skapa webbplats**.

4. På sidan **Skapa en webbplats** klickar du på **Gruppwebbplats**.

5. Skriv **Kampanjstrategi** i **Namn på gruppwebbplats**.

6. I **Beskrivning av gruppwebbplats** skriver du **SharePoint-webbplats för kampanjstrategi (strikt konfidentiellt)**.

7. I **Sekretessinställningar** väljer du **Privat – endast medlemmar har åtkomst till webbplatsen**. Klicka sedan på **Nästa**.

8. I fönstret **Vem vill du lägga till?** klickar du på **Slutför**.

9. Gå till den nya fliken **Kampanjstrategi** i webbläsaren. Klicka på inställningsikonen i verktygsfältet och sedan på **Webbplatsbehörigheter**.

10. I fönstret **Webbplatsbehörigheter** klickar du på **Inställningar för avancerade behörigheter**.

11. Klicka på **Inställningar för åtkomstbegäran** på den nya fliken **Behörigheter** i webbläsaren.

12. I dialogrutan **Inställningar för åtkomstbegäran** avmarkerar du **Tillåt medlemmar att dela webbplats och enskilda filer och mappar** och **Tillåt medlemmar att bjuda in andra till webbplatsens medlemsgrupp** (så att alla tre kryssrutorna är avmarkerade). Klicka sedan på **OK**.

13. Klicka på **Kampanjstrategi-Medlemmar** i listan.

14. På sidan **Personer och grupper** klickar du på **Nytt**.

15. I dialogrutan **Dela** skriver du **Seniora och strategisk personal**, markerar den och klickar sedan på **Dela**.

16. Klicka på **Kampanjstrategi-Ägare** i listan.

17. På sidan **Personer och grupper** klickar du på **Nytt**.

18. I dialogrutan **Dela** skriver du **IT-personal**, markerar det och klickar sedan på **Dela**.

19. Klicka på bakåtknappen i webbläsaren.

20. Stäng fliken **Personer och grupper** i webbläsaren, klicka på fliken **Kampanjstrategi-Start** i webbläsaren och stäng sedan fönstret **Webbplatsbehörigheter**.

Här är resultatet av att konfigurera behörigheter:

- SharePoint-gruppen **Kampanjstrategi-Medlemmar** innehåller bara gruppen **Seniora och strategisk personal** (som endast innehåller användarkontona Candidate, ChiefOfStaff och Strategic1) och gruppen **Kampanjstrategi** (som bara innehåller det globala administratörsanvändarkontot).

- SharePoint-gruppen **Kampanjstrategi-Ägare** innehåller bara gruppen **IT-personal** (som endast innehåller användarkontona ITAdmin1 och ITAdmin2).

- SharePoint-gruppen **Kampanjstrategi-Besökare** innehåller inga grupp- eller användarkonton.

- Medlemmar kan inte ändra behörigheter på webbplatsnivå (detta kan bara utföras av medlemmar i gruppen **Kampanjstrategi-Ägare**).

- Andra användarkonton kan inte komma åt webbplatsen eller dess resurser. De kan inte heller begära åtkomst till webbplatsen. Ytterligare behörigheter för webbplatsen måste utföras av en global administratör eller en medlem i gruppen **Kampanjstrategi-Ägare**.

Därefter konfigurerar du dokumentmappen för kampanjstrategins gruppwebbplats med etiketten Strikt konfidentiellt.

1. På fliken **Kampanjstrategi-Start** i webbläsaren klickar du på **Dokument**.

2. Klicka på inställningsikonen och sedan på **Inställningar för bibliotek**. 

3. Under **Behörigheter och hantering** klickar du på **Använd etikett för objekt i det här biblioteket**. 

4. I **Inställningar-Använd etikett** väljer du **Strikt konfidentiellt** och klickar sedan på **Spara**.

Därefter konfigurerar du en DLP-princip som blockerar användare när de delar ett dokument med etiketten Strikt konfidentiellt på en SharePoint Online-gruppwebbplats som finns utanför organisationen. Den här DLP-principen används för resurser på kampanjstrategins webbplats.

1. Om det behövs kan du använda webbläsaren på din lokala dator och logga in på administrationscentret för (<https://admin.microsoft.com>) med ett konto som har rollen som säkerhetsadministratör eller företagsadministratör.

2. På fliken **Microsoft Office Home** i webbläsaren genom att klicka på **Säkerhet och efterlevnad**.

3. På den nya fliken **Säkerhet och efterlevnad** i din webbläsare klickar du på **dataförlustskydd > Policy**.

4. I fönstret **Dataförlustskydd** klickar du på **+ Skapa en princip**.

5. I fönstret **Börja med en mall eller skapa en anpassad princip** klickar du på **Anpassa** och sedan på **Nästa**.

6. I fönstret **Namnge principen** skriver du **Etiketten Strikt konfidentiellt, SharePoint Online-gruppwebbplatser** i **Namn**. Klicka sedan på **Nästa**.

7. I fönstret **Välj platser** klickar du på **Låt mig välja specifika platser**. Klicka sedan på **Nästa**.

8. Inaktivera platserna **Exchange-e-post** och **OneDrive-konton** i listan med platser och klicka sedan på **Nästa**.

9. I fönstret **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Redigera**.

10. I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Lägg till** i listrutan och sedan på **Etiketter**.

11. I rutan **Etiketter** klickar du på **+ Lägg till**, väljer **Strikt konfidentiellt**, klickar på **Lägg till** och sedan på **Klar**.

12. I fönstret **Välj de typer av innehåll som ska skyddas** klickar du på **Spara**.

13. I **Anpassa vilka typer av känslig information som du vill skydda** klickar du på **Nästa**.

14. I fönstret **Vad vill du göra om vi identifierar känslig information?** klickar du på **Anpassa tips och e-post**.

15. I fönstret **Anpassa principtips och e-postmeddelanden** klickar du på **Anpassa principtipsets text**.

16. I textrutan skriver du eller klistrar in följande:

    - Om du vill dela med en användare utanför organisationen, laddar du ned filen och öppnar den. Klicka på Arkiv, Skydda dokument och Kryptera med lösenord och ange sedan ett starkt lösenord. Skicka lösenordet i ett separat e-postmeddelande eller med annat kommunikationssätt.

17. Klicka på **OK**.

18. I fönstret **Vad vill du göra om vi identifierar känslig information?** väljer du **Kräv en affärsrelaterad motivering för att åsidosätta** och klicka sedan på **Nästa**.

19. I fönstret **Vill du aktivera principen eller testa saker först?** klickar du på **Ja, aktivera direkt** och sedan på **Nästa**.

20. I fönstret **Granska inställningarna** klickar du på **Skapa** och sedan på **Stäng**.

Använd instruktionerna i [Aktivera Azure RMS med administrationscentret för Microsoft 365](/information-protection/deploy-use/activate-office365).

Konfigurera sedan Azure Information Protection med en ny begränsad princip och en underetikett för skydd och behörigheter med följande steg:

1. Logga in på administrationscentret med ett konto som har rollen som säkerhetsadministratör eller företagsadministratör. Mer information finns i [Så här loggar du in i Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Gå till Azure-portalen (<https://portal.azure.com>) på en separat flik i webbläsaren.

3. I sökfönstret skriver du **information** och klickar sedan på **Azure Information Protection**.

4. Klicka på **Etiketter**.

5. Högerklicka på etiketten **Strikt konfidentiellt** och klicka sedan på **Lägg till en underetikett**.

6. Skriv **CampaignStrategy** i **Namn** och **Etikett för dokument på kampanjstrategins gruppwebbplats** i **Beskrivning**.

7. I **Ange behörigheter för dokument och e-postmeddelanden som innehåller den här etiketten** klickar du på **Skydda**.

8. I avsnittet **Säkerhet** klickar du på **Azure (molnnyckel)**.

9. På bladet **Säkerhet** klickar du på **+ Lägg till behörigheter** under **Skyddsinställningar**.

10. På bladet **Lägg till behörigheter** klickar du på **+ Bläddra i katalog** under **Ange användare och grupper**.

11. I fönstret **AAD-användare och grupper** väljer du **Seniora och strategisk personal**. Klicka sedan på **Välj**.

12. Under **Välj behörigheter från förinställt eller ange anpassad** klickar du på **Anpassad** och sedan i kryssrutorna **Visa rättigheter**, **Redigera innehåll**, **Spara**, **Svara** och **Svara alla**.

13. Klicka på **OK** två gånger.

14. På bladet **Underetikett** klickar du på **Spara** och sedan på **OK**.

15. Klicka på **Principer > + Lägg till en ny princip** på bladet **Azure Information Protection**.

16. Skriv **CampaignStrategy** i **Namn** och **Dokument på kampanjstrategins gruppwebbplats** i **Beskrivning**.

17. Klicka på **Välj vilka användare eller grupper som får den här principen > Användare/grupper** och välj sedan **Seniora och strategisk personal**.

18. Klicka på **Välj \> OK**.

19. Klicka på **Lägg till eller ta bort etiketter**. I fönstret **Princip: Lägg till eller ta bort etiketter** klickar du på **CampaignStrategy** och sedan på **OK**.

20. Klicka på **Spara** och sedan på **OK**.

Du är nu redo att börja skapa dokument på dessa fyra webbplatser och testa åtkomsten till dem med olika användarkonton.

Om du vill skydda ett dokument med Azure Information Protection och den här nya etiketten, måste du [installera Azure Information Protection-klienten](/information-protection/rms-client/install-client-app) på en testdator, installera Office från administrationscentret och sedan logga in med ett konto i gruppen **Seniora och strategisk personal** i utvärderingsprenumerationen.

## <a name="see-also"></a>Se även

[Microsofts säkerhetsvägledning för politiska kampanjer, ideella föreningar och andra snabbrörliga organisationer](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[Konfigurera grupper och användare i en utvecklings-/testmiljö för en politisk kampanj](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

[Testlabbguider för integrering med molntjänster](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[Microsoft 365-lösning och arkitekturcenter](../../solutions/index.yml)