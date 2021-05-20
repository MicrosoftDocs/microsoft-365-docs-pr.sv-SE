---
title: Förebyggande av dataförluster och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Du kan nu tillämpa DLP-policyer Microsoft Teams chattar och kanaler. Läs den här artikeln om du vill veta mer om hur den fungerar.
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572471"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Förebyggande av dataförluster och Microsoft Teams

> [!NOTE]
> Funktioner för att förebygga dataförlust lades nyligen till i Microsoft Teams-chatt- och kanalmeddelanden för användare som är licensierade för Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance eller Office 365 Advanced Compliance. Office 365 och Microsoft 365 E3 inkluderar DLP-skydd för SharePoint Online, OneDrive och Exchange Online. Detta inkluderar också filer som delas via Teams eftersom Teams använder SharePoint Online och OneDrive för att dela filer.
Stöd för DLP-skydd Teams Chat kräver E5.
Mer information om licenskrav finns i [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

## <a name="overview-of-dlp-for-microsoft-teams"></a>Översikt över DLP för Microsoft Teams

Nyligen [utökades funktioner för att förhindra](dlp-learn-about-dlp.md) dataförlust till att omfatta Microsoft Teams chatt- och kanalmeddelanden, inklusive privata **kanalmeddelanden**. 

> [!IMPORTANT]
> DLP gäller för närvarande endast för de faktiska meddelandena i chatt- eller kanaltråden. Aktivitetsmeddelanden – som innehåller en kort förhandsgranskning av meddelanden och  visas baserat på en användares meddelandeinställningar – ingår för närvarande inte i Teams DLP. All känslig information som finns i den del av meddelandet som visas i förhandsgranskningen kommer att förbli synlig i meddelandet även efter att DLP-principen har tillämpats och tagit bort känslig information själva meddelandet.

Om din organisation har DLP kan du nu definiera principer som hindrar personer från att dela känslig information i en Microsoft Teams-kanal eller chattsession. Här är några exempel på hur det här skyddet fungerar:

- **Exempel 1: Skydda känslig information i meddelanden**. Anta att någon försöker dela känslig information i en Teams chatt eller kanal med gäster (externa användare). Om du har definierat en DLP-princip för att förhindra detta tas meddelanden med känslig information som skickas till externa användare bort. Detta sker automatiskt och inom några sekunder beroende på hur DLP-principen är konfigurerad.

    > [!NOTE]
    > DLP för Microsoft Teams blockerar känsligt innehåll när det delas med Microsoft Teams användare som har:<br/>- [Gäståtkomst](/MicrosoftTeams/guest-access) i team och kanaler. eller<br/>- [extern åtkomst](/MicrosoftTeams/manage-external-access) i möten och chattsessioner. <p>DLP för externa chattsessioner fungerar bara om både avsändaren och mottagaren är i Teams-läge och [använder Microsoft Teams inbyggd federation](/microsoftteams/manage-external-access). DLP för Teams blockerar inte meddelanden [i interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) med Skype för företag eller icke-inbyggda federerade chattsessioner.

- **Exempel 2: Skydda känslig information i dokument**. Anta att någon försöker dela ett dokument med gäster i en Microsoft Teams eller chatt och att dokumentet innehåller känslig information. Om du har definierat en DLP-princip för att förhindra detta öppnas inte dokumentet för dessa användare. Observera att i det här fallet måste din DLP-policy innehålla SharePoint OneDrive för att skydd ska vara på plats. (Detta är ett exempel på DLP för SharePoint som visas i Microsoft Teams och kräver därför att användare är licensierade för Office 365 DLP (ingår i Office 365 E3), men kräver inte att användare licensieras för Office 365 Advanced Compliance.)

## <a name="policy-tips-help-educate-users"></a>Principtips hjälper till att utbilda användare

På samma sätt som DLP [fungerar i Exchange, Outlook, Outlook på webben](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), SharePoint [Online, OneDrive för företag-webbplatser](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites) [och Office-skrivbordsklienter](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)visas principtips när en åtgärd står i konflikt med en DLP-princip. Här är ett exempel på ett principtips:

![Blockerat meddelandemeddelande i Teams](../media/dlp-teams-blockedmessage-notification.png)

I det här fallet försökte avsändaren dela ett personnummer i en Microsoft Teams kanal. Länken **Vad kan jag göra öppnar** en dialogruta som innehåller alternativ för avsändaren att lösa problemet. Observera att avsändaren i det här fallet kan välja att åsidosätta principen eller meddela en administratör att granska och lösa den.

![Alternativ för att lösa blockerat meddelande](../media/dlp-teams-blockedmessage-possibleactions.png)

I organisationen kan du välja att tillåta användare att åsidosätta en DLP-princip. När du konfigurerar DLP-principerna kan du använda standardprinciptipsen eller [anpassa principtips](#to-customize-policy-tips) för din organisation.

Återgå till vårt exempel, där en avsändare delade ett personnummer i en Teams-kanal, här är vad mottagaren såg:

> [!div class="mx-imgBorder"]
> ![Meddelandet blockerat](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>Så här anpassar du principtips

För att kunna utföra den här uppgiften måste du tilldelas en roll som har behörighet att redigera DLP-principer. Mer information finns i [Behörigheter](data-loss-prevention-policies.md#permissions).

1. Gå till Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) och logga in.

2. Välj **princip för förebyggande av**  >  **dataförlust**.

3. Välj en princip och välj **Redigera bredvid Principinställningar**. 

4. Antingen skapa en ny regel eller redigera en befintlig regel för principen.

    > [!div class="mx-imgBorder"]
    > ![Redigera en regel för en princip](../media/dlp-teams-editrule.png)

5. Välj Anpassa **e-posttexten** **och/eller** Anpassa textalternativen **för principtips på fliken Användaraviseringar.**

    > [!div class="mx-imgBorder"]
    > ![Anpassa användaraviseringar och principtips](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Ange den text som du vill använda för e-postmeddelanden och/eller principtips och välj sedan **Spara**.

7. Välj **Spara på fliken** **Principinställningar.**

Låt dina ändringar arbeta sig igenom ditt datacenter och synkronisera med användarkonton i ungefär en timme.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Lägga Microsoft Teams som plats i befintliga DLP-principer

För att kunna utföra den här uppgiften måste du tilldelas en roll som har behörighet att redigera DLP-principer. Mer information finns i [Behörigheter](data-loss-prevention-policies.md#permissions).

1. Gå till Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) och logga in.

2. Välj **princip för förebyggande av**  >  **dataförlust**.

3. Välj en princip och titta på värdena under **Platser**. Om du **Teams chatt- och kanalmeddelanden** är allt klart. Om du inte gör det klickar du på **Redigera**.

    > [!div class="mx-imgBorder"]
    > ![Platser för befintlig princip](../media/dlp-teams-editexistingpolicy.png)

4. Aktivera **principen för** alla chatt- och kanalmeddelanden **i Teams kolumnen Status.**

    > [!div class="mx-imgBorder"]
    > ![DLP för Teams chattar och kanaler](../media/dlp-teams-addteamschatschannels.png)

5. Behåll **standardinställningen** för alla konton på fliken Välj platser eller välj **Låt mig välja specifika platser**. Du kan ange:

    1. upp till 1000 enskilda konton för att inkludera eller exkludera
    1. distributionslistor och säkerhetsgrupper som ska inkluderas eller uteslutas. 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. Välj sedan **Nästa**.

7. Klicka på **Spara**.

Låt dina ändringar arbeta sig igenom ditt datacenter och synkronisera med användarkonton i ungefär en timme.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definiera en ny DLP-princip för Microsoft Teams

För att kunna utföra den här uppgiften måste du tilldelas en roll som har behörighet att redigera DLP-principer. Mer information finns i [Behörigheter](data-loss-prevention-policies.md#permissions).

1. Gå till Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ) och logga in.

2. Välj **Princip för förebyggande av**  >    >  **dataförlust + Skapa en princip**.

3. Välj en [mall](data-loss-prevention-policies.md#dlp-policy-templates)och välj sedan **Nästa**.

    I vårt exempel valde vi den amerikanska personligt identifierbara informationsdatamallen.

    > [!div class="mx-imgBorder"]
    > ![Sekretessmall för DLP-policy](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. På fliken **Namn på principen** anger du ett namn och en beskrivning för principen och väljer sedan **Nästa**.

5. Behåll **standardinställningen** för alla konton på fliken Välj platser eller välj **Låt mig välja specifika platser**. Du kan ange:

    1. upp till 1000 enskilda konton för att inkludera eller exkludera
    1. distributionslistor och säkerhetsgrupper som ska inkluderas eller uteslutas. **Det här är en offentlig förhandsgranskningsfunktion.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP-principplatser](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > Om du vill se till att dokument som innehåller känslig information inte delas på ett olämpligt sätt i Teams kontrollerar **du att SharePoint-webbplatser** **och OneDrive-konton** är aktiverade, **tillsammans med Teams chatt- och kanalmeddelanden**.

6. Behåll de enkla standardinställningarna under Anpassa vilken **typ av innehåll du vill skydda** på fliken **Principinställningar** eller välj **Använd avancerade inställningar** och välj sedan **Nästa**. Om du väljer avancerade inställningar kan du skapa eller redigera regler för din princip. (För att få hjälp med detta, [se Enkla inställningar kontra avancerade inställningar](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)

7.  Granska **inställningarna** under Vad **vill du göra på fliken Principinställningar?** (Här kan du välja att behålla standardprinciptips och [e-postaviseringar](use-notifications-and-policy-tips.md), eller anpassa dem.)

    > [!div class="mx-imgBorder"]
    > ![DLP-principinställningar med tips och aviseringar](../media/dlp-teams-policysettings-tipsemails.png)

    När du är klar med gransknings- eller redigeringsinställningarna väljer du **Nästa**.

8. På fliken **Principinställningar,** under **Vill du aktivera principen eller testa saker först?** [](dlp-overview-plan-for-dlp.md#policy-deployment) 

    > [!div class="mx-imgBorder"]
    > ![Ange om principen ska aktiveras](../media/dlp-teams-policysettings-turnonnow.png)

9. Granska **inställningarna för** den nya principen på fliken Granska dina inställningar. Välj **Redigera om** du vill göra ändringar. När du är klar väljer du **Skapa**.

Låt ungefär en timme för din nya princip arbeta sig igenom ditt datacenter och synkronisera till användarkonton.

## <a name="prevent-external-access-to-sensitive-documents"></a>Förhindra extern åtkomst till känsliga dokument

Om du vill SharePoint att dokument som innehåller känslig information inte kan nås av externa gäster, antingen från SharePoint eller Teams som standard, väljer du följande:

- Du kan se till att dokument skyddas tills DLP genomsöks och markerar dem som säkra att dela genom [att markera nya filer som känsliga som standard](/sharepoint/sensitive-by-default).

- Rekommenderad DLP-policystruktur

    - **Villkor**
        - Innehållet innehåller någon av dessa känsliga informationstyper: [Välj allt som gäller]
        
        - Innehåll delas från Microsoft 365 personer utanför min organisation
        
          > [!div class="mx-imgBorder"]
          > ![DLP-villkor för att upptäcka extern delning av känsligt innehåll](../media/dlp-teams-external-sharing/external-condition.png)

    - **Åtgärder**
        - Begränsa åtkomsten till innehållet för externa användare
        
        - Meddela användare med tips om e-post och policy
        
        - Skicka incidentrapporter till administratören
        
        > [!div class="mx-imgBorder"]
        > ![DLP-åtgärd för att blockera extern delning av känsligt innehåll](../media/dlp-teams-external-sharing/external-action.png)

DLP-princip som är i funktion när du försöker dela ett dokument i SharePoint som innehåller känslig information med en extern gäst:

> [!div class="mx-imgBorder"]
> ![Extern delning blockerad](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


DLP-princip som gäller när gästen försöker öppna ett dokument i Teams med blockera externt:

> [!div class="mx-imgBorder"]
> ![Extern åtkomst blockerad](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>Relaterade artiklar

[Skapa, testa och justera en DLP-princip](create-test-tune-dlp-policy.md)

[Skicka e-postaviseringar och visa principtips för DLP-principer](use-notifications-and-policy-tips.md)
