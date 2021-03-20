---
title: Konfigurera team med skydd för mycket känslig data
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Lär dig hur du distribuerar team med skydd för mycket känslig data.
ms.openlocfilehash: fdc3c1ab2c780289b7405623779b8af89da8ba17
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916292"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a>Konfigurera team med skydd för mycket känslig data

I den här artikeln ska vi titta närmare på hur du konfigurerar ett team för en mycket känslig skyddsnivå. Kontrollera att du har slutfört stegen i [Distribuera teams med grundskydd](configure-teams-baseline-protection.md) innan du följer anvisningarna i den här artikeln.

För den här skyddsnivån skapar vi en känslighetsetikett som kan användas i hela organisationen för mycket känsliga team och filer. Endast medlemmar i din organisation och gäster som du har angett kan dekryptera filer som använder den här etiketten. Om du behöver isolera behörigheter ytterligare så att endast medlemmar i ett angivet team kan dekryptera filer kan du läsa [Distribuera ett team med säkerhetsisolering](secure-teams-security-isolation.md).

Den mycket känsliga nivån erbjuder följande ytterligare skydd över grundnivån:

- En känslighetsetikett för teamet som gör att du kan aktivera eller inaktivera gästdelning och begränsar åtkomst till SharePoint-innehåll till webben endast för ostyrda enheter. Du kan också använda den här etiketten för att klassificera och kryptera filer.
- En mer restriktiv länktyp för standarddelning
- Endast teamägare kan skapa privata kanaler.
- Åtkomstförfrågningar för den associerade SharePoint-webbplatsen är inaktiverade.

## <a name="guest-sharing"></a>Gästdelning

Beroende på företagets natur kan du kanske inte aktivera gästdelning för team som innehåller mycket känslig data. Om du tänker samarbeta med personer utanför organisationen i teamet, rekommenderar vi att du aktiverar gästdelning. Microsoft 365 innehåller en mängd olika funktioner för säkerhet och efterlevnad som hjälper dig att dela känsligt innehåll. Det här är vanligtvis ett säkrare alternativ än att skicka innehåll direkt till personer utanför organisationen.

Information om hur du delar med gäster säkert finns i följande resurser:

- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](./share-limit-accidental-exposure.md)
- [Skapa en säker miljö för gästdelning](./create-secure-guest-sharing-environment.md)

För att tillåta eller blockera gästdelning använder vi en kombination av känslighetsetiketter för teamet och delning på webbplats nivå för den associerade SharePoint-webbplatsen, som vi ser senare.

## <a name="sensitivity-labels"></a>Känslighetsetiketter

För den mycket känsliga skyddsnivån använder vi en känslighetsetikett för att klassificera teamet. Den här etiketten kan också användas för att klassificera och kryptera enskilda filer i detta eller andra team eller på andra filplatser som SharePoint eller OneDrive. 

Som ett första steg måste du aktivera känslighetsetiketter för Teams. Mer information finns i [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Office 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md).

Om du redan har känslighetsetiketter distribuerade i din organisation, bör du överväga hur denna etikett passar med din övergripande etikettstrategi. Du kan ändra namn eller inställningar om det behövs för att uppfylla organisationens behov.

När du har aktiverat känslighetsetiketter för Teams är nästa steg att skapa etiketten.

Att skapa en känslighetsetikett
1. Öppna [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com).
2. Under **Lösningar** klickar du på **Informationsskydd**.
3. Klicka på **Skapa en etikett**.
4. Namnge etiketten. Vi föreslår **Mycket känslig**, men du kan välja ett annat namn om denna redan används.
5. Lägg till ett visningsnamn och en beskrivning och klicka på **Nästa**.
6. På sidan **Definiera omfång för etikett** väljer du **filer och e-postmeddelanden** samt **grupper och webbplatser** och klickar på **Nästa**.
7. På sidan **Välj säkerhetsinställningar för filer och e-postmeddelanden** väljer du **Kryptera filer och e-postmeddelande** och klickar på **Nästa**.
8. På sidan **Kryptering** väljer du **Konfigurera krypteringsinställningar**.
9. Under **Tilldela behörigheter för vissa användare och grupper** klickar du på **Tilldela behörigheter**.
10. Klicka på **Lägga till alla användare och grupper i organisationen**.
11. Om det finns gästanvändare som ska ha behörighet att dekryptera filer klickar du på **Lägga till användare eller grupper** och lägger till dem.
12.  Klicka på **Spara** och sedan på **Nästa**.
13. På sidan *Auto-etiketting för filer och e-postmeddelanden** klickar du på **Nästa**.
14. På sidan **Definiera säkerhetsinställningar för grupper och webbplatser** väljer du **Inställningar för sekretess och extern användaråtkomst** samt **Inställningar för enhetsåtkomst och extern delning** och klickar på **Nästa**.
15. Välj alternativet **Privat** under **Sekretess** på sidan **Definiera inställningar för sekretess och extern användaråtkomst**.
16. Om du vill tillåta gäståtkomst väljer du **Låt Microsoft 365-gruppägare lägga till personer utanför organisationen i gruppen som gäster** under **Extern användaråtkomst**.
17. Klicka på **Nästa**.
18. På sidan **Definiera inställningar för extern delning och enhetsåtkomst** väljer du **Styra extern delning från etiketterade SharePoint-webbplatser**.
19. Under **Innehåll kan delas med** väljer du **Nya och befintliga gäster** om du vill tillåta gäståtkomst eller **Endast personer i organisationen**.
20. Under **Åtkomst från ohanterade enheter** väljer du **Blockera åtkomst**. (Om du tillåter gäster och de har inte hanterade enheter vill du kanske välja **Tillåt begränsad åtkomst på webben**.)
21. Klicka på **Nästa**.
22. På sidan **Auto-etiketting för databaskolumner** klickar du på **Nästa**.
23. Klicka på **Skapa etikett** och sedan på **Klart**.

När du har skapat en etikett måste du publicera den till de användare som ska använda den. För känsligt skydd gör vi etiketterna tillgängliga för alla användare. Du publicerar etiketten i Microsoft 365 Efterlevnadscenter på fliken **Etikettprinciper** på sidan **Informationskydd**. Om du har en befintlig princip som gäller för alla användare kan du lägga till den här etiketten i principen. Om du behöver skapa en ny princip kan du läsa [Publicera känsliga etiketter genom att skapa en etikettpolicy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Skapa ett team

Ytterligare konfiguration av det mycket känsliga scenariot görs på SharePoint-webbplatsen som är kopplad till teamet, så nästa steg är att skapa ett team.

Skapa en team för mycket känslig information
1. I Teams klickar du på **Teams** till vänster i programmet och sedan på **gå med i eller skapa en teams** längst ned i grupplistan.
2. Klicka på **Skapa team** (första kortet, övre vänstra hörnet).
3. Välj **Skapa ett team från början**.
4. I listan **Känslighet** väljer du etiketten **Mycket känslig** som du precis har skapat.
5. Under **Sekretess** klickar du på **Privat**.
6. Skriv in ett namn på teamet och klicka sedan på **Skapa**.
7. Lägg till användare i teamet och klicka sedan på **Stäng**.

## <a name="private-channel-settings"></a>Inställningar för privata kanaler

På denna nivå begränsar vi skapandet av privata kanaler till teamägare.

För att begränsa skapandet av en privat kanal
1. Klicka på **Fler alternativ** i teamet och klicka sedan på **Hantera team**.
2. På fliken **Inställningar**, expandera **medlemsbehörigheter**.
3. Avmarkera kryssrutan **Tillåt att medlemmar skapar privata kanaler**.

Du kan också använda [teamprinciper](/MicrosoftTeams/teams-policies) för att styra vem som kan skapa privata kanaler.

## <a name="sharepoint-settings"></a>SharePoint-inställningar

Varje gång du skapar ett ny team med etiketten mycket känslig finns det två steg att utföra i SharePoint:

- Uppdatera inställningarna för gästdelning för webbplatsen i SharePoint Online Administrationscenter för att matcha det du valde när du skapade etiketten och uppdatera sedan standard delningslänken till *Personer med befintlig åtkomst*.
- Uppdatera inställningarna för webbplatsdelning på själva webbplatsen och förhindra att medlemmar kan dela filer, mappar eller webbplatsen och inaktivera åtkomstförfrågningar.

### <a name="site-guest-sharing-settings"></a>Inställningar för gästdelning av webbplatsen

Den inställning för gästdelning som du valde när du skapade etiketten (som bara påverkar teammedlemskap) ska matcha inställningarna för gästdelning för den associerade SharePoint-webbplatsen på följande sätt:

|Etikettinställning|Inställning för SharePoint-webbplats|
|:------------|:----------------------|
|**Låt Office 365-gruppägare lägga till personer utanför organisationen i gruppen** markerad|**Nya och befintliga gäster** (standard för nya grupper)|
|**Låt Office 365-gruppägare lägga till personer utanför organisationen i gruppen** inte markerad|**Endast personer i organisationen**|

Uppdatera webbplatsinställningar
1. Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).
2. Under **Webbplatser** klickar du på **Aktiva webbplatser**.
3. Klicka på den webbplats som är kopplad till teamet.
4. Klicka på **Redigera** under **Extern delning** på fliken **Principer**.
5. Om du tillät gästdelning när du skapade etiketten för mycket känslig ska du kontrollera att **Nya och befintligt gäster** har markerats. Om du inte tillåter delning när du skapade etiketten väljer du **Bara personer i organisationen**.
6. Avmarkera kryssrutan **Samma som organisationsnivå** under standardtyp av delningslänk och välj **Personer med befintlig åtkomst**.
7. Klicka på **Spara**.

Om du vill skapa ett skript som en del av processen för att skapa ett team kan du använda [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) med följande parametrar:

- `-SharingCapability Disabled` Inaktivera gästdelning (det är aktiverat som standard)
- `-DefaultSharingLinkType Internal` ändra standard delningslänk till *Vissa personer*

#### <a name="private-channels"></a>Privata kanaler

Om du lägger till privata kanaler i teamet skapas en ny SharePoint-webbplats med standard delningsinställningar. De här webbplatserna visas inte i SharePoint Online Administrationscenter. Du måste därför använda Windows PowerShell-cmdleten set-SPOSite för att uppdatera inställningarna för gästdelning.

### <a name="site-sharing-settings"></a>Inställningar för webbplatsdelning

För att se till att SharePoint-webbplatsen inte delas med personer som inte är medlemmar i teamet kan vi begränsa delning till ägare. Vi begränsar även delning av filer och mappar till teamägare. På så sätt ser du till att ägare känner till när en fil delas med någon utanför teamet.

Konfigurera webbplatsdelning endast för ägare
1. Gå till fliken **Allmänt** i teamet som du vill uppdatera i Teams.
2. I verktygsfältet för teamet klickar du på **Filer**.
3. Klicka på ellipsen och sedan på **Öppna i SharePoint**.
4. Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.
5. I fönstret **Webbplatsbehörigheter**, under **webbplatsdelning**, klickar du på **Ändra hur medlemmar kan dela**.
6. Under **Delningsbehörigheter** väljer du **Endast webbplatsägare kan dela filer, mappar och webbplats**.
7. Ställ **Tillåt åtkomstbegäranden** till **Av** och klicka sedan på **Spara**.

## <a name="see-also"></a>Se även

[Skapa och konfigurera känslighetsetiketter och deras principer](../compliance/create-sensitivity-labels.md)