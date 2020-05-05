---
title: Konfigurera team med skydd för känslig data
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
description: Lär dig hur du distribuerar team med skydd för känslig data.
ms.openlocfilehash: 6c3d79e212a1a0333a7262b72ae0f1db8597096f
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003414"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a>Konfigurera team med skydd för känslig data

I den här artikeln ska vi titta närmare på hur du konfigurerar ett team för en känslig skyddsnivå. Kontrollera att du har slutfört stegen i [distribuera teams med grundskydd](configure-teams-baseline-protection.md) innan du följer anvisningarna i den här artikeln. Den känsliga nivån erbjuder följande ytterligare skydd över grundnivån:

- En känslighetsetikett för teamet som gör att du kan aktivera eller inaktivera gästdelning och begränsar åtkomst till SharePoint-innehåll till webben endast för ostyrda enheter. Du kan också använda den här etiketten för att klassificera filer.
- En mer restriktiv länktyp för standarddelning
- Endast teamägare kan skapa privata kanaler.

## <a name="guest-sharing"></a>Gästdelning

Beroende på företagets natur kan du kanske inte aktivera gästdelning för team som innehåller känsliga data. Om du tänker samarbeta med personer utanför organisationen i teamet, rekommenderar vi att du aktiverar gästdelning. Microsoft 365 innehåller en mängd olika funktioner för säkerhet och efterlevnad som hjälper dig att dela känsligt innehåll. Det här är vanligtvis ett säkrare alternativ än att skicka innehåll direkt till personer utanför organisationen.

Information om hur du delar med gäster säkert finns i följande resurser:

- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [Skapa en säker miljö för gästdelning](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

För att tillåta eller blockera gästdelning använder vi en kombination av känslighetsetiketter för teamet och delning på webbplats nivå för den associerade SharePoint-webbplatsen, som vi ser senare.

## <a name="sensitivity-labels"></a>Känslighetsetiketter

För den känsliga skyddsnivån använder vi en känslighetsetikett för att klassificera teamet. Den här etiketten kan också användas för att klassificera enskilda filer i detta eller andra team, eller på andra filplatser som SharePoint eller OneDrive. 

Som ett första steg måste du aktivera känslighetsetiketter för Teams. Mer information finns i [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Office 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Om du redan har känslighetsetiketter distribuerade i din organisation, bör du överväga hur denna etikett passar med din övergripande etikettstrategi. Du kan ändra namn eller inställningar om det behövs för att uppfylla organisationens behov.

När du har aktiverat känslighetsetiketter för Teams är nästa steg att skapa etiketten.

Att skapa en känslighetsetikett
1. Öppna [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com).
2. Under **Lösningar**klickar du på **Informationsskydd**.
3. Klicka på **Skapa en etikett**.
4. Namnge etiketten. Vi föreslår **känslig**, men du kan välja ett annat namn om denna redan används.
5. Lägg till ett knapptips och klicka sedan på **Nästa**.
6. På sidan **kryptering** klickar du på **nästa**.
7. Om du vill lägga till ett sidhuvud, en sidfot eller en vattenstämpel automatiskt i filer som klassificeras med den här etiketten går du till sidan **Markering av innehåll**.
8. På sidan **Inställningar för webbplatser och grupper** ställer du **inställningar för webbplatser och grupper** till **På**.
9. I listrutan **Sekretess för gruppanslutna teamwebbplatser i Office 365** väljer du **Privat – endast användare kan komma åt webbplatsen**.
10. Om du vill tillåta gäståtkomst markerar du kryssrutan **Låt gruppägarna för Office 365 lägga till personer utanför organisationen i gruppen**. 
11. Under **ohanterade enheter**väljer du **tillåta begränsad åtkomst**via webben.
12. Klicka på **Nästa**.
13. På sidan **Auto-etiketting för Office-program** klickar du på **Nästa**.
14. Klicka på **Skicka** och klicka sedan **Klart**.

När du har skapat en etikett måste du publicera den till de användare som ska använda den. För känsligt skydd gör vi etiketterna tillgängliga för alla användare. Du publicerar etiketten i Microsoft 365 Efterlevnadscenter på fliken **Etikettprinciper** på sidan **Informationskydd**. Om du har en befintlig princip som gäller för alla användare kan du lägga till den här etiketten i principen. Om du behöver skapa en ny princip kan du läsa [Publicera känsliga etiketter genom att skapa en etikettpolicy](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).

## <a name="create-a-team"></a>Skapa ett team

Ytterligare konfiguration av det känsliga scenariot görs på SharePoint-webbplatsen som är kopplad till teamet, så nästa steg är att skapa ett team.

Skapa en team för känslig information
1. I Teams klickar du på **Teams** till vänster i programmet och sedan på **gå med i eller skapa en teams** längst ned i grupplistan.
2. Klicka på **Skapa team** (första kortet, övre vänstra hörnet).
3. Välj **Skapa ett team från början**.
4. I listan **känslighet** väljer du **känslighetsetiketten** som du precis har skapat.
5. Under **Sekretess**klickar du på **Privat**.
6. Skriv in ett namn på teamet och klicka sedan på **Skapa**.
7. Lägg till användare i teamet och klicka sedan på **Stäng**.

## <a name="private-channel-settings"></a>Inställningar för privata kanaler

På denna nivå begränsar vi skapandet av privata kanaler till teamägare.

För att begränsa skapandet av en privat kanal
1. Klicka på **Fler alternativ**i teamet och klicka sedan på **Hantera team**.
2. På fliken **Inställningar**, expandera **medlemsbehörigheter**.
3. Avmarkera kryssrutan **Tillåt att medlemmar skapar privata kanaler**.

Du kan också använda [teamprinciper](https://docs.microsoft.com/MicrosoftTeams/teams-policies) för att styra vem som kan skapa privata kanaler.

## <a name="sharepoint-settings"></a>SharePoint-inställningar

Varje gång du skapar ett ny team med känslighetsetiketten finns det två steg att utföra i SharePoint:

- Uppdatera inställningarna för gästdelning för webbplatsen i SharePoint Online Administrationscenter för att matcha det du valde när du skapade etiketten och uppdatera sedan standard delningslänken till *Vissa personer*.
- Uppdatera inställningarna för webbplatsdelning på själva webbplatsen och förhindra att medlemmar kan webbplatsen.

### <a name="site-guest-sharing-settings"></a>Inställningar för gästdelning av webbplatsen

Den inställning för gästdelning som du valde när du skapade etiketten (som bara påverkar teammedlemskap) ska matcha inställningarna för gästdelning för den associerade SharePoint-webbplatsen på följande sätt:

|Etikettinställning|Inställning för SharePoint-webbplats|
|:------------|:----------------------|
|**Låt Office 365-gruppägare lägga till personer utanför organisationen i gruppen** markerad|**Nya och befintliga gäster** (standard för nya grupper)|
|**Låt Office 365-gruppägare lägga till personer utanför organisationen i gruppen** inte markerad|**Endast personer i organisationen**|

Uppdatera webbplatsinställningar
1. Öppna [SharePoint Online Administrationscenter](https://admin.microsoft.com/sharepoint).
2. Under **Webbplatser**klickar du på **Aktiva webbplatser**.
3. Klicka på den webbplats som är kopplad till teamet.
4. Klicka på **Redigera** under **Extern delning** på fliken **Principer**.
5. Om du tillät gästdelning när du skapade känslighetsetiketten ska du kontrollera att **Nya och befintligt gäster** har markerats. Om du inte tillåter delning när du skapade etiketten väljer du **Bara personer i organisationen**.
6. Avmarkera kryssrutan **Samma som organisationsnivå** under standardtyp av delningslänk och välj **Vissa personer 8endast de personer som användaren anger**.
7. Klicka på **Spara**.

Om du vill skapa ett skript som en del av processen för att skapa ett team kan du använda [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) med följande parametrar:

- `-SharingCapability Disabled` Inaktivera gästdelning (det är aktiverat som standard)
- `-DefaultSharingLinkType Internal` ändra standard delningslänk till *Vissa personer*

#### <a name="private-channels"></a>Privata kanaler

Om du lägger till privata kanaler i teamet skapas en ny SharePoint-webbplats med standard delningsinställningar. De här webbplatserna visas inte i SharePoint Online Administrationscenter. Du måste därför använda Windows PowerShell-cmdleten set-SPOSite för att uppdatera inställningarna för gästdelning.

### <a name="site-sharing-settings"></a>Inställningar för webbplatsdelning

För att se till att SharePoint-webbplatsen inte delas med personer som inte är medlemmar i teamet kan vi begränsa delning till ägare.

Konfigurera webbplatsdelning endast för ägare
1. Gå till fliken **Allmänt** i teamet som du vill uppdatera i Teams.
2. I verktygsfältet för teamet klickar du på **Filer**.
3. Klicka på ellipsen och sedan på **Öppna i SharePoint**.
4. Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.
5. I fönstret Webbplatsbehörigheter under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.
6. Under **Delningsbehörigheter** väljer du **Webbplatsägare och medlemmar, och personer med redigeringsbehörighet kan dela filer och mappar, men endast webbplatsägare kan dela webbplatsen** och klicka sedan på **Spara**.


## <a name="see-also"></a>Se även

[Skapa och konfigurera känslighetsetiketter och deras principer](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)


