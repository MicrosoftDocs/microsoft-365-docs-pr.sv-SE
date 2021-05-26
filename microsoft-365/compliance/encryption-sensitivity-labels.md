---
title: Begränsa åtkomst till innehåll med hjälp av känslighetsetiketter för att tillämpa kryptering
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Konfigurera känslighetsetiketter för kryptering som skyddar dina data genom att begränsa åtkomst och användning.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6fff2bc595e9317ef037929a8a6828935b15bbf
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624687"
---
# <a name="restrict-access-to-content-by-using-sensitivity-labels-to-apply-encryption"></a>Begränsa åtkomst till innehåll med hjälp av känslighetsetiketter för att tillämpa kryptering

>*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

När du skapar en känslighetsetikett kan du begränsa åtkomsten till innehåll som etiketten ska tillämpas på. Med krypteringsinställningarna för en känslighetsetikett kan du till exempel skydda innehåll så att:

- Endast användare inom organisationen kan öppna ett konfidentiellt dokument eller e-postmeddelande.
- Endast användare på marknadsföringsavdelningen kan redigera och skriva ut dokumentet eller e-postmeddelandet för marknadsföringsmeddelanden, medan alla andra användare i organisationen bara kan läsa det.
- Användare kan inte vidarebefordra ett e-postmeddelande eller kopiera information från meddelandet som innehåller nyheter om en intern omorganisation.
- Den aktuella prislistan som skickas till affärspartner kan inte öppnas efter ett angivet datum.

När ett dokument eller e-postmeddelande krypteras begränsas åtkomsten till innehållet, så att det:

- Endast kan dekrypteras av användare som är godkända enligt etikettens krypteringsinställningar.
- Förblir krypterat oavsett var det finns, inom eller utanför organisationen, även om filen får ett nytt namn.
- Är krypterat både i vila (t.ex. i ett OneDrive-konto) och under överföring (t.ex. när e-post överförs via Internet).

När du konfigurerar en känslighetsetikett för användning av kryptering kan du som administratör även välja att antingen:

- **Tilldela behörigheter nu**, så att du bestämmer exakt vilka behörigheter olika användare får till innehåll med den etiketten.
- **Låta användare tilldela behörigheter** när de använder etiketten för innehåll. På så sätt kan du ge personer i organisationen en viss flexibilitet som de kan behöva för att samarbeta och få arbetet gjort.

Krypteringsinställningarna är tillgängliga när du [skapar en känslighetsetikett](create-sensitivity-labels.md) i Microsoft 365 Efterlevnadscenter. Du kan också använda den äldre portalen, Säkerhets- och efterlevnadscenter.

## <a name="understand-how-the-encryption-works"></a>Förstå hur kryptering fungerar

Kryptering använder Azure Rights Management-tjänsten (Azure RMS) från Azure Information Protection. Den här säkerhetslösningen använder krypterings-, identitets- och auktoriseringsprinciper. Mer information finns i [Vad är Azure Rights Management?](/azure/information-protection/what-is-azure-rms) i dokumentationen för Azure Information Protection. 

När du använder den här krypteringslösningen är det funktionen **superanvändare** som gör att behöriga personer och tjänster alltid kan läsa och kontrollera de data som har krypterats för din organisation. Om det behövs kan krypteringen sedan tas bort eller ändras. Mer information finns i [Konfigurera superanvändare för Azure Information Protection och identifieringstjänster eller dataåterställning](/azure/information-protection/configure-super-users).

## <a name="how-to-configure-a-label-for-encryption"></a>Konfigurera en etikett för kryptering

1. Följ de allmänna anvisningarna för att [skapa eller redigera en känslighetsetikett](create-sensitivity-labels.md#create-and-configure-sensitivity-labels) och se till att **Filer och e-postmeddelanden** är valt som etikettens omfång: 
    
    ![Omfångsalternativ för känslighetsetiketter för filer och e-postmeddelanden](../media/filesandemails-scope-options-sensitivity-label.png)

2. På sidan **Välj skyddsinställningar för filer och e-postmeddelanden** väljer du **Kryptera filer och e-postmeddelanden**.
    
    ![Skyddsalternativ för känslighetsetiketter för filer och e-postmeddelanden](../media/protection-options-sensitivity-label.png)

4.  Välj något av följande alternativ på sidan **Kryptering**.:
    
    - **Ta bort kryptering om filen är krypterad**: Det här alternativet stöds endast av klienten för enhetlig etikettering i Azure Information Protection. När du väljer det här alternativet och använder inbyggd etikettering kan det hända att etiketten inte visas i appar, eller visas och inte gör några krypteringsändringar.
        
        Mer information om det här scenariot finns i [Vad händer med befintlig kryptering när en etikett används](#what-happens-to-existing-encryption-when-a-labels-applied) avsnittet. Det är viktigt att förstå att den här inställningen kan resultera i en känslighetsetikett som användarna kanske inte kan använda om de inte har tillräckliga behörigheter.
    
    - **Konfigurera krypteringsinställningar**: Aktiverar kryptering och gör krypteringsinställningarna synliga:
        
        ![Alternativ för känslighetsetiketter för kryptering](../media/encrytion-options-sensitivity-label.png)
        
        Anvisningarna för de här inställningarna finns i avsnittet [Konfigurera krypteringsinställningar](#configure-encryption-settings).

### <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a>Vad händer med befintlig kryptering när en etikett används

Om en känslighetsetikett används för okrypterat innehåll framgår resultatet genom de krypteringsalternativ du kan välja. Om du till exempel inte markerar **Kryptera filer och e-postmeddelanden** förblir innehållet okrypterat.

Innehållet kan dock redan vara krypterat. En annan användare kan till exempel ha använt:

- Sina egna behörigheter, som omfattar användardefinierade behörigheter vid uppmaning via en etikett, anpassade behörigheter från Azure Information Protection-klienten och dokumentskyddet **Begränsad åtkomst** från ett Office-program.
- En Azure Rights Management-skyddsmall som krypterar innehållet oberoende av en etikett. Den här kategorin innehåller e-postflödesregler som tillämpar kryptering med hjälp av rättighetsskydd.
- En etikett som tillämpar kryptering med behörigheter som tilldelats av administratören.

I följande tabell ser du vad som händer med befintlig kryptering när en känslighetsetikett tillämpas på det innehållet:

| | Kryptering: Inte vald | Kryptering: Konfigurerad | Kryptering: Ta bort <sup>\*</sup> |
|:-----|:-----|:-----|:-----|
|**Behörigheter som anges av en användare**|Ursprunglig kryptering bevaras|Ny etikettkryptering används|Ursprunglig kryptering tas bort|
|**Skyddsmall**|Ursprunglig kryptering bevaras|Ny etikettkryptering används|Ursprunglig kryptering tas bort|
|**Etikett med administratörsdefinierade behörigheter**|Ursprunglig kryptering tas bort|Ny etikettkryptering används|Ursprunglig kryptering tas bort|

**Fotnot:**

<sup>\*</sup> Stöds endast av klienten för enhetlig etikettering i Azure Information Protection.

I de fall då den nya etikettkrypteringen tillämpas eller den ursprungliga krypteringen tas bort, händer detta bara om användaren som tillämpar etiketten har en användningsrättighet eller roll som stöder den här åtgärden:

- [Användningsrättigheten](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Exportera eller Fullständig behörighet.
- Rollen [Rights Management-utfärdare eller Rights Management-ägare](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner), eller [superanvändare](/azure/information-protection/configure-super-users).

Om användaren inte har någon av dessa rättigheter eller roller kan etiketten inte tillämpas och den ursprungliga krypteringen bevaras. Användaren får följande meddelande: **Du har inte behörighet att göra den här ändringen av känslighetsetiketten. Kontakta innehållsägaren.**

Den person som tillämpar Vidarebefordra inte för ett e-postmeddelande kan till exempel etikettera om tråden för att ersätta krypteringen eller ta bort den, eftersom denne är Rights Management-ägare för e-postmeddelandet. Men med undantag för superanvändare kan mottagarna av det här e-postmeddelandet inte etikettera om det eftersom de inte har de rättigheter som krävs.

#### <a name="email-attachments-for-encrypted-email-messages"></a>Bifogade filer i krypterade e-postmeddelanden

När ett e-postmeddelande krypteras med valfri metod ärver alla okrypterade Office-dokument som bifogas i e-postmeddelandet automatiskt samma krypteringsinställningar.

Dokument som redan är krypterade och sedan läggs till som bifogade filer bevarar alltid sin ursprungliga kryptering.

## <a name="configure-encryption-settings"></a>Konfigurera krypteringsinställningar

När du väljer **Konfigurera krypteringsinställningar** på sidan **Kryptering** i guiden för att skapa eller redigera en känslighetsetikett, väljer du något av följande alternativ:

- **Tilldela behörigheter nu**, så att du kan bestämma exakt vilka behörigheter olika användare får till innehåll som har den här etiketten. Mer information finns i nästföljande avsnitt [Tilldela behörigheter nu](#assign-permissions-now).
- **Låt användare tilldela behörigheter** när de använder etiketten för innehåll. Med det här alternativet kan du ge personer i organisationen en viss flexibilitet som de kan behöva för att samarbeta och få arbetet gjort. Mer information finns i avsnittet [Låt användare tilldela behörigheter ](#let-users-assign-permissions) på den här sidan.

Om du till exempel har en känslighetsetikett med namnet **Strikt konfidentiellt** som ska tillämpas på ditt mest känsliga innehåll kan det vara bra att bestämma nu vem som får behörighet för innehållet och vilken typ.

Om du har en känslighetsetikett med namnet **Affärsavtal** och organisationens arbetsflöde kräver att användarna tillfälligt samarbetar med olika personer om innehållet, kan det även vara bra att låta användarna bestämma vilka som får behörigheter när de tilldelar etiketten. Den här flexibiliteten bidrar både till användarnas produktivitet och minskar begäranden om att administratörerna ska uppdatera eller skapa nya känslighetsetiketter för att hantera specifika scenarier.

Välja om du vill tilldela behörigheter nu eller låta användare tilldela behörigheter:

![Alternativ för att lägga till användar- eller administratörsdefinierade behörigheter](../media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a>Tilldela behörigheter nu

Använd följande alternativ för att styra vem som kan komma åt e-post eller dokument för vilka den här etiketten används:

- **Tillåt att åtkomst till etiketterat innehåll upphör**, antingen på ett visst datum eller efter ett visst antal dagar efter det att etiketten tillämpats. Efter den här tiden kan användare inte öppna det etiketterade objektet. Om du anger ett datum gäller det från och med midnatt i din aktuella tidszon. (Observera att vissa e-postklienter kanske inte tillämpar förfallodatum och visar e-postmeddelanden efter det datumet på grund av en cachelagringsmetod.)

- **Tillåt offlineåtkomst**: aldrig, alltid eller under ett visst antal dagar efter att etiketten tillämpats. Om offlineåtkomst begränsas till aldrig eller ett antal dagar måste användarna, när tröskelvärdet nås, omautentiseras och deras åtkomst loggas. Mer information finns i nästa avsnitt om Rights Management-användningslicensen.

Inställningar för åtkomstkontroll för krypterat innehåll:

![Inställningar för administratörsdefinierade behörigheter](../media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a>Rights Management-användningslicens för offlineåtkomst

När en användare öppnar ett dokument eller e-postmeddelande som skyddas av kryptering från Azure Rights Management-tjänsten, tilldelas användaren en Azure Rights Management-användningslicens för det innehållet. Användningslicensen är ett certifikat som innehåller användarens användningsrättigheter för dokumentet eller e-postmeddelandet, och krypteringsnyckeln som användes för att kryptera innehållet. Användningslicensen innehåller också ett utgångsdatum om detta har angetts, och hur länge licensen är giltig.

Om inget utgångsdatum har angetts är standardgiltighetsperioden för användningslicensen för en klientorganisation 30 dagar. Under hela användningslicensens varaktighet behöver inte användaren autentiseras eller auktoriseras på nytt för innehållet. Med den här processen kan användaren fortsätta öppna det skyddade dokumentet eller e-postmeddelandet utan Internetanslutning. När licensens giltighetsperiod upphör måste användaren autentiseras eller auktoriseras på nytt nästa gång denne vill få åtkomst till det skyddade dokumentet eller e-postmeddelandet.

Förutom att det ska vara en omautentisering, omvärderas krypteringsinställningarna och användargruppsmedlemskap. Det innebär att användare kan få olika åtkomstresultat för samma dokument eller e-post om det finns ändringar i krypteringsinställningarna eller gruppmedlemskap från när de senast kom åt innehållet.

Information om hur du ändrar standardinställningen på 30 dagar finns i avsnittet om [Rights Management-användningslicens](/azure/information-protection/configure-usage-rights#rights-management-use-license).

### <a name="assign-permissions-to-specific-users-or-groups"></a>Tilldela behörigheter för vissa användare eller grupper

Du kan tilldela behörigheter till specifika personer så att bara de kan interagera med det etiketterade innehållet:

1. Lägg först till användare eller grupper som ska tilldelas behörigheter till det etiketterade innehållet.

2. Välj sedan vilka behörigheter användarna ska ha för det etiketterade innehållet.

Tilldela behörigheter:

![Alternativ för att tilldela behörigheter till användare](../media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a>Lägga till användare eller grupper

När du tilldelar behörigheter kan du välja:

- Alla i organisationen (medlemmar i klientorganisationen). Den här inställningen exkluderar gästkonton.

- Alla autentiserade användare. Kontrollera att du förstår [krav och begränsningar](#requirements-and-limitations-for-add-any-authenticated-users) för den här inställningen innan du väljer den.

- En specifik användare eller e-postaktiverad säkerhetsgrupp, distributionsgrupp eller Microsoft 365-grupp ([tidigare Office 365-grupp](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) i Azure AD. Microsoft 365-gruppen kan ha statiskt eller [dynamiskt medlemskap](/azure/active-directory/users-groups-roles/groups-create-rule). Observera att du inte kan använda en [dynamisk distributionsgrupp från Exchange](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups) eftersom den grupptypen inte synkroniseras till Azure AD, och du kan inte använda en säkerhetsgrupp som inte är e-postaktiverad.

- Valfri e-postadress eller domän. Använd det här alternativet om du vill ange alla användare i en annan organisation som använder Azure AD, genom att ange ett domännamn från den organisationen. Du kan också använda det här alternativet för kommunikationsplattformar genom att ange deras domännamn, till exempel **gmail.com**, **hotmail.com** eller **outlook.com**.

    > [!NOTE]
    > Om du anger en domän från en organisation som använder Azure AD kan du inte begränsa åtkomsten till den specifika domänen. I stället ingår alla verifierade domäner i Azure AD automatiskt för den klientorganisation som äger det domännamn du anger.

När du väljer alla användare och grupper i organisationen, eller bläddrar i katalogen, måste användarna eller grupperna ha en e-postadress.

Det är bäst att använda grupper i stället för användare. Den här strategin gör konfigurationen enklare.

##### <a name="requirements-and-limitations-for-add-any-authenticated-users"></a>Krav och begränsningar för ”Lägg till autentiserade användare”

Den här inställningen begränsar inte vem som kan komma åt det innehåll som etiketten krypterar, samtidigt som innehållet ändå krypteras och alternativ ges för att begränsa hur innehållet kan användas (behörigheter) och om det går att komma åt (förfallodatum och offlineåtkomst). Men programmet som öppnar det krypterade innehållet måste ha stöd för den autentisering som används. Därför fungerar federerade sociala plattformar som Google, och autentisering med engångslösenord, endast för e-post och endast när du använder Exchange Online. Microsoft-konton kan användas med Office 365-appar och [visningsprogrammet för Azure Information Protection](https://portal.azurerms.com/#/download).

> [!NOTE]
> Överväg att använda den här inställningen med [SharePoint- och OneDrive-integrering med Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) när känslighetsetiketter [aktiverats för Office-filer i SharePoint och OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

Några vanliga scenarier för inställningen alla autentiserade användare:

- Du bryr dig inte om vem som visar innehållet, men du vill begränsa hur det används. Du vill till exempel inte att innehållet ska redigeras, kopieras eller skrivas ut.
- Du behöver inte begränsa vem som har åtkomst till innehållet, men du vill kunna bekräfta vem som öppnar det.
- Du har ett krav på att innehållet måste vara krypterat i vila och under överföring, men det kräver inte åtkomstkontroller.

#### <a name="choose-permissions"></a>Välj behörigheter

När du väljer vilka behörigheter som ska tillåtas för dessa användare eller grupper kan du välja antingen:

- En [fördefinierad behörighetsnivå](/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) med en förinställd grupp rättigheter, till exempel Medförfattare eller Granskare.
- Anpassade behörigheter, där du väljer en eller flera användningsbehörigheter.

Mer information som hjälper dig att välja rätt behörigheter finns i [Användningsrättigheter och beskrivningar](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).  

![Alternativ för att välja förinställda eller anpassade behörigheter](../media/Sensitivity-Choose-permissions-settings.png)

Observera att samma etikett kan ge olika behörigheter till olika användare. En enstaka etikett kan till exempel tilldela vissa användare som Granskare och en annan användare som Medförfattare, enligt följande skärmbild.

Det gör du genom att lägga till användare eller grupper, tilldela dem behörigheter och spara inställningarna. Upprepa sedan stegen med att lägga till användare och tilldela dem behörigheter och spara inställningarna varje gång. Du kan upprepa den här konfigurationen så många gånger det behövs för att definiera olika behörigheter för olika användare.

![Olika behörigheter för olika användare](../media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a>Rights Management-utfärdare (användare som tillämpar känslighetsetiketten) har alltid Fullständig behörighet

Kryptering för en känslighetsetikett använder Azure Rights Management-tjänsten från Azure Information Protection. När en användare tillämpar en känslighetsetikett för att skydda ett dokument eller e-postmeddelande med hjälp av kryptering, blir den användaren Rights Management-utfärdare för det innehållet.

Rights Management-utfärdare tilldelas alltid Fullständig behörighet för dokumentet eller e-postmeddelandet, och dessutom:

- Om krypteringsinställningarna innehåller ett utgångsdatum kan Rights Management-utfärdaren fortfarande öppna och redigera dokumentet eller e-postmeddelandet efter det datumet.
- Rights Management-utfärdare kan alltid komma åt dokumentet eller e-post offline.
- Rights Management-utfärdare kan fortfarande öppna ett dokument efter att det återkallats.

Mer information finns i [Rights Management-utfärdare och Rights Management-ägare](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).

### <a name="double-key-encryption"></a>Kryptering med dubbla nycklar

> [!NOTE]
> Den här funktionen stöds för närvarande endast av klienten för enhetlig etikettering i Azure Information Protection.

Välj det här alternativet först när du har konfigurerat tjänsten för kryptering med dubbla nycklar och du behöver använda krypteringen med dubbla nycklar för filer som ska tilldelas den här etiketten.

Mer information, förutsättningar och konfigurationsanvisningar finns i [Kryptering med dubbla nycklar (DKE)](double-key-encryption.md).

## <a name="let-users-assign-permissions"></a>Låt användare tilldela behörigheter

> [!IMPORTANT]
> Alla etiketteringsklienter stöder inte alla alternativ som tillåter att användare tilldelar sina egna behörigheter. Mer information finns i det här avsnittet.

Du kan använda följande alternativ för att låta användare tilldela behörigheter när de manuellt tillämpar en känslighetsetikett på innehåll:

- I Outlook kan en användare välja begränsningar som motsvarar alternativet [Vidarebefordra inte](/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails) eller [Endast kryptering](/azure/information-protection/configure-usage-rights#encrypt-only-option-for-emails) för de valda mottagarna.
    
    Alternativet Vidarebefordra inte stöds av alla e-postklienter som har stöd för känslighetsetiketter. Användning av alternativet **Endast kryptering** med en känslighetsetikett är dock en nyligen släppt version som endast stöds av inbyggd etikettering och inte klienten för enhetlig etikettering i Azure Information Protection. För e-postklienter som inte stöder den här funktionen visas inte etiketten.
    
    Använd [funktionstabellen för Outlook](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-outlook) och raden **Låt användare tilldela behörigheter: – Endast kryptering** om du vill kontrollera de lägsta versionerna av Outlook-appar som använder inbyggd etikettering för stöd för användning av alternativet Endast kryptering med en känslighetsetikett.

- I Word, PowerPoint och Excel uppmanas en användare att välja egna behörigheter för specifika användare, grupper eller organisationer.

    Det här alternativet stöds av klienten för enhetlig etikettering i Azure Information Protection och av vissa appar som använder inbyggd etikettering. För program som inte stöder den här funktionen visas etiketten antingen inte för användarna, eller så visas etiketten för konsekvens, men den kan inte användas med ett förklaringsmeddelande till användarna.
    
    Om du vill kontrollera vilka appar som använder inbyggd etikettering som har stöd för det här alternativet, använder du [funktionstabellen för Word, Excel och PowerPoint](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint) och raden **Låt användare tilldela behörigheter: – Uppmana användarna**.

När alternativen stöds använder du följande tabell för att identifiera när användarna ser känslighetsetiketten:

|Inställning |Etikett som visas i Outlook|Etikett som visas i Word, Excel, PowerPoint|
|:-----|:-----|:-----|:-----|
|**Tillämpa begränsningar i Outlook med alternativet Vidarebefordra inte eller Endast kryptering**|Ja |Nej |
|**Uppmana användare att ange behörigheter i Word, PowerPoint och Excel**|Nej |Ja|

När båda inställningarna är markerade visas etiketten därför i både Outlook och i Word, Excel och PowerPoint.

En känslighetsetikett som gör att användare kan tilldela behörigheter måste tillämpas på innehåll manuellt av användarna. Den kan inte tillämpas automatiskt eller användas som en rekommenderad etikett.

Konfigurera användartilldelade behörigheter:

![Krypteringsinställningar för användardefinierade behörigheter](../media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a>Begränsningar i Outlook

När en användare använder en känslighetsetikett i Outlook som tillåter att användaren tilldelar behörigheter till ett meddelande, kan du välja alternativet **Vidarebefordra inte** eller **Endast kryptering**. Användaren ser etikettnamnet och beskrivningen längst upp i meddelandet, vilket anger att innehållet skyddas. Till skillnad från Word, PowerPoint och Excel (se [nästa avsnitt](#word-powerpoint-and-excel-permissions)) uppmanas inte användarna att välja specifika behörigheter.

![Känslighetsetikett som används för ett meddelande i Outlook](../media/sensitivity-label-outlook-protection-applied.png)

När något av de här alternativen används för ett e-postmeddelande krypteras e-postmeddelandet och mottagarna måste autentiseras. Sedan har mottagarna automatiskt begränsade användningsrättigheter:

- **Vidarebefordra inte**: Mottagarna kan inte vidarebefordra e-postmeddelandet, skriva ut det eller kopiera från det. I Outlook-klienten är till exempel knappen Vidarebefordra inte otillgänglig, menyalternativen Spara som och Skriv ut är inte tillgängliga och du kan inte lägga till eller ändra mottagare i rutorna Till, Kopia eller Hemlig kopia.
    
    Mer information om hur det här alternativet fungerar finns i [Alternativet Vidarebefordra inte för e-postmeddelanden](/azure/information-protection/configure-usage-rights#do-not-forward-option-for-emails).

- **Endast kryptering**: Mottagarna har alla användningsrättigheter utom Spara som, Exportera och Fullständig behörighet. Den här kombinationen av användningsrättigheter innebär att mottagarna inte har några begränsningar förutom att de inte kan ta bort skyddet. En mottagare kan till exempel kopiera från e-postmeddelandet, skriva ut det och vidarebefordra det.
    
    Mer information om hur det här alternativet fungerar finns i [Alternativet Endast kryptering för e-postmeddelanden](/azure/information-protection/configure-usage-rights#encrypt-only-option-for-emails).

Okrypterade Office-dokument som bifogas i e-postmeddelandet ärver automatiskt samma begränsningar. För Vidarebefordra inte är de användningsrättigheter som används för dessa dokument Redigera innehåll, Redigera, Spara, Visa, Öppna, Läsa och Tillåt makron. Om användaren önskar andra användningsrättigheter för en bifogad fil, eller om den bifogade filen inte är ett Office-dokument som har stöd för det ärvda skyddet, måste användaren kryptera filen innan den bifogas i e-postmeddelandet.

### <a name="word-powerpoint-and-excel-permissions"></a>Behörigheter för Word, PowerPoint och Excel

När en användare använder en känslighetsetikett i Word, PowerPoint och Excel som tillåter att de tilldelar behörigheter till ett dokument, uppmanas de att ange val av användare och behörigheter när krypteringen tillämpas.

Med klienten för enhetlig etikettering för Azure Information Protection kan användarna till exempel:

- Välja en behörighetsnivå, till exempel Läsare (som tilldelar behörigheten Endast visa) eller Medförfattare (som tilldelar behörigheterna Visa, Redigera, Kopiera och Skriv ut).
- Välja användare, grupper eller organisationer. Det kan omfatta personer både inom och utanför organisationen.
- Ange ett utgångsdatum efter vilket de valda användarna inte kan komma åt innehållet. Mer information finns i avsnittet ovan om hur [Rights Management använder licens för offlineåtkomst](#rights-management-use-license-for-offline-access).

![Alternativ när användaren vill skydda med anpassade behörigheter](../media/sensitivity-aip-custom-permissions-dialog.png)

För inbyggd etikettering ser användarna samma dialogruta om de väljer följande:

- Windows: Fliken **Arkiv** > **Information** > **Skydda dokument** > **Begränsa åtkomst** > **Begränsad åtkomst**

- macOS: Fliken **Granska** > **Skydd** > **Behörigheter** > **Begränsad åtkomst**

## <a name="example-configurations-for-the-encryption-settings"></a>Exempelkonfigurationer för krypteringsinställningar

För varje exempel som följer utför du konfigurationen från sidan **Kryptering** i guiden när **Konfigurera krypteringsinställningar** har valts:

![Använda krypteringsalternativet i guiden för känslighetsetiketter](../media/apply-encryption-option.png)

### <a name="example-1-label-that-applies-do-not-forward-to-send-an-encrypted-email-to-a-gmail-account"></a>Exempel 1: Etikett som tillämpar Vidarebefordra inte för att skicka ett krypterat e-postmeddelande till ett Gmail-konto

Den här etiketten visas endast i Outlook och Outlook på webben, och du måste använda Exchange Online. Instruera användarna att välja den här etiketten när de behöver skicka ett krypterat e-postmeddelande till personer som använder ett Gmail-konto (eller något annat e-postkonto utanför organisationen).

Användarna anger Gmail-e-postadressen i rutan **Till**.  Därefter väljer de etiketten så att alternativet Vidarebefordra inte läggs till automatiskt i e-postmeddelandet. Resultatet är att mottagarna inte kan vidarebefordra e-postmeddelandet eller skriva ut det, kopiera från det eller spara e-postmeddelandet utanför postlådan med hjälp av alternativet **Spara som**.

1. På sidan **Kryptering**: För **Tilldela behörigheter nu eller låt användarna bestämma?** väljer du **Låt användare tilldela behörigheter när de använder etiketten**.

2. Markera kryssrutan: **Tillämpa begränsningar i Outlook som motsvarar alternativet Vidarebefordra inte**.

3. Avmarkera kryssrutan om den är vald: **Uppmana användare att ange behörigheter i Word, PowerPoint och Excel**.

4. Välj **Nästa** och slutför guiden.

### <a name="example-2-label-that-restricts-read-only-permission-to-all-users-in-another-organization"></a>Exempel 2: Etikett som begränsar skrivskyddsbehörighet till alla användare i en annan organisation

Den här etiketten är lämplig för delning av mycket känsliga dokument som skrivskyddade, och dokumenten kräver alltid en Internetanslutning för att visas.

Den här etiketten är inte lämplig för e-postmeddelanden.

1. På sidan **Kryptering**: För **Tilldela behörigheter nu eller låt användarna bestämma?** väljer du **Tilldela behörigheter nu**.

2. För **Tillåt offlineåtkomst** väljer du **Aldrig**.

3. Välj **Tilldela behörigheter**.

4. I fönstret **Tilldela behörigheter** väljer du **Lägg till specifika e-postadresser eller domäner**.

5. I textrutan anger du namnet på en domän från den andra organisationen, till exempel **fabrikam.com**. Välj sedan **Lägg till**.

6. Välj **Välj behörigheter**.

7. I fönstret **Välj behörigheter** väljer du listrutan, väljer **Läsare** och sedan **Spara**.

8. I fönstret **Tilldela behörigheter** väljer du **Spara**.

9. På sidan **Kryptering** väljer du **Nästa** och slutför guiden.

### <a name="example-3-add-external-users-to-an-existing-label-that-encrypts-content"></a>Exempel 3: Lägga till externa användare för en befintlig etikett som krypterar innehåll

Nya användare som du lägger till kan öppna dokument och e-postmeddelanden som redan har skyddats med den här etiketten. Behörigheterna du tilldelar de här användarna kan skilja sig från de behörigheter som de befintliga användarna har.

1. På sidan **Kryptering**: För **Tilldela behörigheter nu eller låt användarna bestämma?** kontrollerar du att **Tilldela behörigheter nu** är valt.

2. Välj **Tilldela behörigheter**.

3. I fönstret **Tilldela behörigheter** väljer du **Lägg till specifika e-postadresser eller domäner**.

4. I textrutan anger du e-postadressen till den första användaren (eller gruppen) som ska läggas till och väljer sedan **Lägg till**.

5. Välj **Välj behörigheter**.

6. I fönstret **Välj behörigheter** väljer du behörigheter för användaren (eller gruppen) och sedan **Spara**.

7. Tillbaka i fönstret **Tilldela behörigheter** upprepar du steg 3 till 6 för varje användare (eller grupp) som du vill lägga till i den här etiketten. Klicka sedan på **Spara**.

8. På sidan **Kryptering** väljer du **Nästa** och slutför guiden.

### <a name="example-4-label-that-encrypts-content-but-doesnt-restrict-who-can-access-it"></a>Exempel 4: Etikett som krypterar innehåll men inte begränsar vem som kan komma åt det

Den här konfigurationen har fördelen att du inte behöver ange användare, grupper eller domäner för att kryptera ett e-postmeddelande eller dokument. Innehållet krypteras fortfarande och du kan fortfarande ange användningsrättigheter, ett utgångsdatum och offlineåtkomst.

Använd bara den här konfigurationen när du inte behöver begränsa vem som kan öppna det skyddade dokumentet eller e-postmeddelandet. [Mer information om den här inställningen](#requirements-and-limitations-for-add-any-authenticated-users)

1. På sidan **Kryptering**: För **Tilldela behörigheter nu eller låt användarna bestämma?** kontrollerar du att **Tilldela behörigheter nu** är valt.

2. Konfigurera inställningar för **Användaråtkomst till innehåll upphör** och **Tillåt offlineåtkomst** efter behov.

3. Välj **Tilldela behörigheter**.

4. I fönstret **Tilldela behörigheter** väljer du **Lägg till autentiserade användare**.

    För **Användare och grupper** ser du **Autentiserade användare** som lagts till automatiskt. Du kan inte ändra det här värdet, bara ta bort det, vilket avbryter valet **Lägg till autentiserade användare**.

5. Välj **Välj behörigheter**.

6. I fönstret **Välj behörigheter** väljer du listrutan, väljer de behörigheter du önskar och sedan **Spara**.

7. I fönstret **Tilldela behörigheter** väljer du **Spara**.

8. På sidan **Kryptering** väljer du **Nästa** och slutför guiden.

## <a name="considerations-for-encrypted-content"></a>Att tänka på för krypterat innehåll

Genom att kryptera dina känsliga dokument och e-postmeddelanden kan endast behöriga personer komma åt dessa data. Det finns dock några överväganden att ta hänsyn till:

- Om din organisation inte har [aktiverat känslighetsetiketter för Office-filer i SharePoint och OneDrive](sensitivity-labels-sharepoint-onedrive-files.md):

  - Sökning, eDiscovery och Delve fungerar inte för krypterade filer.
  - DLP-principer fungerar för metadata för dessa krypterade filer (inklusive information om kvarhållningsetiketter), men inte innehållet i de filerna (t.ex. kreditkortsnummer i filer).
  - Användare kan inte öppna krypterade filer med Office på webben. När känslighetsetiketter för Office-filer i SharePoint och OneDrive är aktiverade kan användare använda Office på webben för att öppna krypterade filer, med vissa [-begränsningar](sensitivity-labels-sharepoint-onedrive-files.md#limitations) som omfattar kryptering som har tillämpats med en lokal nyckel (kallas även HYOK eller egen nyckel), [kryptering med dubbla nycklar](#double-key-encryption) och kryptering som har tillämpats oberoende av en känslighetsetikett.

- Om du delar krypterade dokument med personer utanför organisationen kan du behöva skapa gästkonton och ändra principer för villkorsstyrd åtkomst. Mer information finns i [Dela krypterade dokument med externa användare](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content).

- För att flera användare ska kunna redigera en krypterad fil samtidigt måste alla använda Office för webben. Om så inte är fallet och filen redan är öppen:

  - I Office-appar (Windows, Mac, Android och iOS) visas meddelandet **Filen används** med namnet på den person som har checkat ut filen. De kan sedan visa en skrivskyddad kopia eller spara och redigera en kopia av filen, och få ett meddelande när filen är tillgänglig.
  - I Office på webben får användarna ett felmeddelande om att de inte kan redigera dokumentet tillsammans med andra. De kan sedan välja **Öppna i läsvyn**.

- Funktionen [Spara automatiskt](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) i Office-appar (Windows, Mac, Android och iOS) är inaktiverad för krypterade filer. Användarna får ett meddelande om att filen har begränsade behörigheter som måste tas bort innan Spara automatiskt kan aktiveras.

- Det kan ta längre tid att öppna krypterade filer i Office-program (Windows, Mac, Android och iOS).

- Om en etikett som tillämpar kryptering läggs till med hjälp av en Office-app när dokumentet är [utcheckat i SharePoint](https://support.microsoft.com/office/check-out-check-in-or-discard-changes-to-files-in-a-library-7e2c12a9-a874-4393-9511-1378a700f6de), och användaren sedan ignorerar utcheckningen, förblir dokumentet etiketterat och krypterat.

- Följande åtgärder för krypterade filer stöds inte från Office-appar (Windows, Mac, Android och iOS) och användarna ser ett felmeddelande om att något gick fel. SharePoint-funktioner kan dock användas som ett alternativ:

  - Visa, återställa och spara kopior av tidigare versioner. Alternativt kan användare utföra de här åtgärderna med Office på webben om du [aktiverar och konfigurerar versionshantering för en lista eller ett bibliotek](https://support.office.com/article/enable-and-configure-versioning-for-a-list-or-library-1555d642-23ee-446a-990a-bcab618c7a37).
  - Ändra namn eller plats för filer. Alternativt kan användare [byta namn på en fil, mapp eller länk i ett dokumentbibliotek](https://support.microsoft.com/office/rename-a-file-folder-or-link-in-a-document-library-bc493c1a-921f-4bc1-a7f6-985ce11bb185) i SharePoint.

För bästa funktion vid samarbete med filer som är krypterade med en känslighetsetikett, rekommenderar vi att du använder [känslighetsetiketter för Office-filer i SharePoint och OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) samt Office för webben.


## <a name="important-prerequisites"></a>Viktiga förutsättningar

Innan du kan använda kryptering kan du behöva utföra vissa konfigurationsuppgifter.

- Aktivera skydd från Azure Information Protection
    
    För att känslighetsetiketter ska tillämpa kryptering måste skyddstjänsten (Azure Rights Management) från Azure Information Protection vara aktiverad för klientorganisationen. I nyare klientorganisationer är det här standardinställningen, men du kan behöva aktivera tjänsten manuellt. Mer information finns i [Aktivera skyddstjänsten från Azure Information Protection](/azure/information-protection/activate-service).

- Kontrollera nätverkskrav
    
    Du kan behöva göra några ändringar på dina nätverksenheter, till exempel brandväggar. Mer information finns i [Brandväggar och nätverksinfrastruktur](/azure/information-protection/requirements#firewalls-and-network-infrastructure) från Azure Information Protection-dokumentationen.

- Konfigurera Exchange för Azure Information Protection
    
    Exchange behöver inte konfigureras för Azure Information Protection innan användarna kan använda etiketter i Outlook för att kryptera sina e-postmeddelanden. Tills Exchange har konfigurerats för Azure Information Protection får du dock inte tillgång till alla funktioner för användning av Azure Rights Management Protection med Exchange.
    
    Användarna kan till exempel inte visa krypterade e-postmeddelanden på mobiltelefoner eller med Outlook på webben. Krypterade e-postmeddelanden kan inte indexeras för sökning och du kan inte konfigurera Exchange Online DLP för Rights Management Protection. 
    
    Se till att Exchange har stöd för dessa ytterligare scenarier genom att göra följande:
    
    - Läs anvisningarna för Exchange Online i [Exchange Online: IRM-konfiguration](/azure/information-protection/configure-office365#exchangeonline-irm-configuration).
    - För Exchange lokalt måste du distribuera [RMS-anslutningsprogrammet och konfigurera Exchange-servrarna](/azure/information-protection/deploy-rms-connector). 

## <a name="next-steps"></a>Nästa steg

Behöver du dela dina etiketterade och krypterade dokument med personer utanför organisationen?  Se [Dela krypterade dokument med externa användare](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).