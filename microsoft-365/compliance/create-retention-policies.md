---
title: Spara och konfigurera kvarhållningsprinciper för automatisk kvarhållning eller borttagning av innehåll
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Använd en kvarhållningsprincip för effektiv kontroll över innehåll som användare genererar med e-post, dokument och konversationer. Behåll det du vill ha och ta bort det du inte vill ha.
ms.openlocfilehash: 1faeae5dc145d6f908f9137387b875c890d22e14
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280433"
---
# <a name="create-and-configure-retention-policies"></a>Skapa och konfigurera kvarhållningsprinciper

>*[Vägledning för säkerhet och efterlevnad med licensiering i Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Använd en kvarhållningsprincip för att hantera data för din organisation genom att proaktivt bestämma om du vill behålla innehåll, ta bort innehåll eller behålla och sedan ta bort innehållet.

Med en kvarhållningsprincip kan du göra detta mycket effektivt genom att tilldela samma kvarhållningsinställningar på behållarnivån som automatiskt ärvs av innehåll i den behållaren. Till exempel alla objekt på SharePoint-webbplatser, alla e-postmeddelanden i användarnas Exchange-postlådor, alla kanalmeddelanden för team som används med Microsoft Teams. Om du är osäker på om du ska använda en kvarhållningsprincip på behållarnivån eller en kvarhållningsetikett på objektnivån kan du gå till [Kvarhållningsprinciper och kvarhållningsetiketter](retention.md#retention-policies-and-retention-labels).

Mer information om kvarhållningsprinciper och hur kvarhållning fungerar i Microsoft 365 finns i [Mer information om kvarhållningsprinciper och kvarhållningsetiketter](retention.md).

> [!NOTE]
> Informationen på den här sidan är till för efterlevnadsadministratörer. Om du inte är administratör och vill förstå hur kvarhållningsprinciper har konfigurerats för de program du använder kontaktar du supportavdelningen, IT-avdelningen eller administratören. Om du ser meddelanden om kvarhållningsprinciper i Teams-chattar och kanalmeddelanden kan det vara bra att läsa [Teams-meddelanden om kvarhållningsprinciper](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

## <a name="before-you-begin"></a>Innan du börjar

Den globala administratören för organisationen har fullständig behörighet för att skapa och redigera kvarhållningsprinciper. Om du inte loggar in som global administratör kan du läsa mer i [Behörigheter som krävs för att skapa och hantera kvarhållningsprinciper och kvarhållningsetiketter](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="create-and-configure-a-retention-policy"></a>Skapa och konfigurera en kvarhållningsprincip

Även om en kvarhållningsprincip kan ha stöd för flera tjänster som identifieras som "platser" i kvarhållningsprincipen kan du inte skapa en enskild kvarhållningsprincip som omfattar alla platser som stöds:

- Exchange-e-post
- SharePoint-webbplats
- OneDrive-konton
- Microsoft 365-grupper
- Skype för företag
- Gemensamma Exchange-mappar
- Teams-kanalmeddelanden
- Teams-chattar
- Community-meddelanden i Yammer
- Privata meddelanden i Yammer

Om du väljer Teams- eller Yammer-platserna när du skapar en kvarhållningsprincip exkluderas de andra platserna automatiskt. Det innebär att instruktionerna du ska följa beror på om du behöver inkludera Teams- eller Yammer-platserna:

- [Instruktioner för en kvarhållningsprincip för Teams-platser](#retention-policy-for-teams-locations)
- [Instruktioner för en kvarhållningsprincip för Yammer-platser](#retention-policy-for-yammer-locations)
- [Instruktioner för en kvarhållningsprincip för andra platser än Teams och Yammer](#retention-policy-for-locations-other-than-teams-and-yammer)

Om du har fler än en kvarhållningsprincip och du också använder kvarhållningsetiketter kan du läsa [Principerna för kvarhållning, eller vad som har företräde](retention.md#the-principles-of-retention-or-what-takes-precedence) för att förstå resultatet när flera kvarhållningsinställningar gäller för samma innehåll.

### <a name="retention-policy-for-teams-locations"></a>Kvarhållningsprincip för Teams-platser

1. I [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/) väljer du **Principer** > **Kvarhållning**.

2. Välj **Ny kvarhållningsprincip** för att starta guiden Skapa kvarhållningsprincip, och namnge den nya kvarhållningsprincipen.

3. För sidan **Välj platser där principen ska tillämpas** väljer du en eller båda platserna för Teams: **Teams-kanalmeddelande** och **Teams-chattar**.

   För **Teams-kanalmeddelanden** inkluderas meddelanden från standardkanaler men inte från [privata kanaler](/microsoftteams/private-channels). För närvarande stöds inte privata kanaler av kvarhållningsprinciper.

   Som standard är [alla team och alla användare markerade](#a-policy-that-applies-to-entire-locations), men du kan förfina det genom att välja [alternativen **Välj** och **Exkludera**](#a-policy-with-specific-inclusions-or-exclusions). Innan du ändrar standardinställningen bör du tänka på följande konsekvenser för en kvarhållningsprincip som tar bort meddelanden när den konfigureras för att omfatta eller exkludera:
    
    - För gruppchattar, eftersom en kopia av meddelanden sparas i varje användares postlåda som ingår i chatten, kommer kopior av meddelanden fortfarande att returneras i eDiscovery-resultat från användare som inte har tilldelats principen.
    - För användare som inte har tilldelats principen returneras borttagna meddelanden i sökresultat för Teams, men meddelandets innehåll visas inte som ett resultat av den permanenta borttagningen från principen som är tilldelad till användare.

4. För sidan **Bestäm om du vill bevara innehållet och/eller ta bort det** i guiden anger du konfigurationsalternativ för att behålla eller ta bort innehåll.

   Du kan skapa en kvarhållningsprincip som bara behåller innehåll utan borttagning, som behåller och sedan tar bort efter en angiven tidsperiod eller som bara tar bort innehåll efter en angiven tidsperiod. Mer information finns i [Inställningar för att behålla och ta bort innehåll](#settings-for-retaining-and-deleting-content) på den här sidan.

5. Slutför guiden för att spara inställningarna.

Mer information om när du använder kvarhållningsprinciper för Teams och för att förstå slutanvändarupplevelsen finns i [Hantera kvarhållningsprinciper för Microsoft Teams](/microsoftteams/retention-policies), via Teams-dokumentationen.

Teknisk information om hur kvarhållning fungerar för Teams, inklusive vilka delar av meddelanden som stöds för kvarhållning och tidsinställningar med exempel, finns i [Mer information om kvarhållning för Microsoft Teams](retention-policies-teams.md).

#### <a name="known-configuration-issues"></a>Kända konfigurationsproblem

- Även om du kan välja att starta kvarhållningsperioden när objekten senast ändrades så används alltid värdet **När objekt skapades**. För meddelanden som redigeras sparas en kopia av det ursprungliga meddelandet med sin ursprungliga tidsstämpel för att identifiera när det här förredigerade meddelandet skapades, och det efterredigerade meddelandet har en nyare tidsstämpel.

- När du väljer **Välj team** för platsen **Teams-kanalmeddelanden** kanske du ser Microsoft 365-grupper som inte också är team. Markera inte de här grupperna.

- När du väljer **Välj användare för platsen Teams-chattar** kan du se gäster och användare utan postlåda. Kvarhållningsprinciperna är inte avsedda för de här användarna, så välj dem inte.


#### <a name="additional-retention-policy-needed-to-support-teams"></a>Ytterligare kvarhållningsprincip som behövs för att stödja Teams

Teams är mer än bara chattar och kanalmeddelanden. Om du har team som skapats från en Microsoft 365-grupp (tidigare Office 365-grupp) bör du dessutom konfigurera en kvarhållningsprincip som inkluderar den Microsoft 365-gruppen genom att använda platsen **Microsoft 365-grupper**. Den här kvarhållningsprincipen gäller för innehåll i gruppens postlåda, webbplats och filer.

Om du har gruppwebbplatser som inte är anslutna till en Microsoft 365-grupp behöver du en kvarhållningsprincip som inkluderar platserna **SharePoint-webbplatser** eller **OneDrive-konton** för att behålla och ta bort filer i Teams:

- Filer som delas i chatten lagras på OneDrive-kontot för användaren som delade filen.

- Filer som laddas upp till kanaler lagras på teamets SharePoint-webbplats.

> [!TIP]
> Du kan använda en kvarhållningsprincip på filer för bara ett visst team när det inte är anslutet till en Microsoft 365-grupp genom att välja teamets SharePoint-webbplats och OneDrive-kontona för användare i teamet.

Det är möjligt att en kvarhållningsprincip som används på Microsoft 365-grupper, SharePoint-webbplatser eller OneDrive-konton kan ta bort en fil som refereras i en Teams-chatt eller ett kanalmeddelande innan de meddelandena tas bort. I det här scenariot visas filen fortfarande i Teams-meddelandet, men när användarna väljer filen får de felmeddelandet "Filen hittades inte". Det här beteendet är inte specifikt för kvarhållningsprinciper och kan också inträffa om en användare manuellt tar bort en fil från SharePoint eller OneDrive.

### <a name="retention-policy-for-yammer-locations"></a>Kvarhållningsprincip för Yammer-platser

> [!NOTE]
> Kvarhållningsprinciper för Yammer distribueras som förhandsversion. Om du inte ser de nya platserna för Yammer kan du försöka igen om några veckor.
>
> För att använda den här funktionen måste Yammer-nätverket vara i [enhetligt läge](/yammer/configure-your-yammer-network/overview-native-mode), inte hybridläge.

1. I [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/) väljer du **Principer** > **Kvarhållning**.

2. Välj **Ny kvarhållningsprincip** för att skapa en ny kvarhållningsprincip.

3. För sidan **Bestäm om du vill bevara innehållet och/eller ta bort det** i guiden anger du konfigurationsalternativ för att behålla och ta bort innehåll. 
    
    Du kan skapa en kvarhållningsprincip som bara behåller innehåll utan borttagning, som behåller och sedan tar bort efter en angiven tidsperiod eller som bara tar bort innehåll efter en angiven tidsperiod. Mer information finns i [Inställningar för att behålla och ta bort innehåll](#settings-for-retaining-and-deleting-content) på den här sidan.
    
    Välj inte **Använd avancerade inställningar för kvarhållning** eftersom det här alternativet inte stöds för Yammer-platser. 

4. För sidan **Välj platser** väljer du **Låt mig välja specifika platser**. Aktivera sedan en eller båda platserna för Yammer: **Community-meddelanden i Yammer** och **Privata meddelanden i Yammer**.
    
    Som standard är alla communities och användare markerade, men du kan förfina detta genom att ange communities och användare som ska inkluderas eller exkluderas.
    
    För privata meddelanden i Yammer: 
    - Om du lämnar standardvärdet som **Alla** inkluderas inte Azure B2B-gästanvändare. 
    - Om du väljer **Välj användare** kan du tillämpa en kvarhållningsprincip på externa användare om du känner till deras konto.

5. Slutför guiden och spara inställningarna.

Mer information om hur kvarhållningsprinciper fungerar för Yammer finns i [Mer information om kvarhållning för Yammer](retention-policies-yammer.md).

#### <a name="additional-retention-policies-needed-to-support-yammer"></a>Ytterligare kvarhållningsprinciper som behövs för att stödja Yammer

Yammer är mer än bara community-meddelanden och privata meddelanden. Om du vill behålla och ta bort e-postmeddelanden för Yammer-nätverket konfigurerar du en ytterligare kvarhållningsprincip som omfattar alla Microsoft 365-grupper som används för Yammer genom att använda platsen **Microsoft 365-grupper**. 

Om du vill behålla och ta bort filer som lagras i Yammer behöver du en kvarhållningsprincip som inkluderar platserna **SharePoint-webbplatser** eller **OneDrive-konton**:

- Filer som delas i privata meddelanden lagras på OneDrive-kontot för användaren som delade filen. 

- Filer som laddas upp till communities lagras på SharePoint-webbplatsen för Yammer-communityn.

Det är möjligt att en kvarhållningsprincip som används på SharePoint-webbplatser eller OneDrive-konton kan ta bort en fil som refereras i ett Yammer-meddelande innan de meddelandena tas bort. I det här scenariot visas filen fortfarande i Yammer-meddelandet, men när användarna väljer filen får de felmeddelandet "Filen hittades inte". Det här beteendet är inte specifikt för kvarhållningsprinciper och kan också inträffa om en användare manuellt tar bort en fil från SharePoint eller OneDrive.

### <a name="retention-policy-for-locations-other-than-teams-and-yammer"></a>Kvarhållningsprincip för andra platser än Teams och Yammer

Använd följande instruktioner för kvarhållningsprinciper som gäller för någon av dessa tjänster:

- Exchange: e-post och gemensamma mappar
- SharePoint: webbplatser
- OneDrive: konton
- Microsoft 365-grupper
- Skype för företag

1. I [Microsoft 365 Efterlevnadscenter](https://compliance.microsoft.com/) väljer du **Principer** > **Kvarhållning**.

2. Välj **Ny kvarhållningsprincip** för att starta guiden Skapa kvarhållningsprincip, och namnge den nya kvarhållningsprincipen.

3. För sidan **Välj platser** aktiverar eller inaktiverar du valfria platser förutom platserna för Teams. Du kan för varje plats lämna den på standardvärdet för att [tillämpa principen på hela platsen](#a-policy-that-applies-to-entire-locations), eller så kan du [ange vilka som ska inkluderas eller exkluderas](#a-policy-with-specific-inclusions-or-exclusions).

    Information som är specifik för platser:
    - [Exchange-e-post och gemensamma Exchange-mappar](#configuration-information-for-exchange-email-and-exchange-public-folders)
    - [SharePoint-webbplatser och OneDrive-konton](#configuration-information-for-sharepoint-sites-and-onedrive-accounts)
    - [Microsoft 365-grupper](#configuration-information-for-microsoft-365-groups)
    - [Skype för företag](#configuration-information-for-skype-for-business)

4. För sidan **Bestäm om du vill bevara innehållet och/eller ta bort det** i guiden anger du konfigurationsalternativ för att behålla och ta bort innehåll.

    Du kan skapa en kvarhållningsprincip som bara behåller innehåll utan borttagning, som behåller och sedan tar bort efter en angiven tidsperiod eller som bara tar bort innehåll efter en angiven tidsperiod. Mer information finns i [Inställningar för att behålla och ta bort innehåll](#settings-for-retaining-and-deleting-content) på den här sidan.

5. Slutför guiden och spara inställningarna.

#### <a name="configuration-information-for-exchange-email-and-exchange-public-folders"></a>Konfigurationsinformation för Exchange-e-post och gemensamma Exchange-mappar

Platsen **Exchange-e-post** har stöd för kvarhållning av användares e-post, kalender och andra postlådeobjekt genom att tillämpa kvarhållningsinställningar på nivån för en postlåda.

Detaljerad information om vilka objekt som inkluderas och exkluderas när du konfigurerar kvarhållningsinställningar för Exchange finns i [Vad ingår för kvarhållning och borttagning](retention-policies-exchange.md#whats-included-for-retention-and-deletion)

Även om en Microsoft 365-grupp har en Exchange-postlåda så kommer en kvarhållningsprincip som inkluderar hela platsen **Exchange-e-post** inte att inkludera innehåll i Microsoft 365-gruppostlådor. För att behålla innehåll i dessa postlådor markerar du platsen **Microsoft 365-grupper**.

Platsen **Gemensamma Exchange-mappar** tillämpar kvarhållningsinställningar på alla gemensamma mappar och kan inte tillämpas på mapp- eller postlådenivå.

#### <a name="configuration-information-for-sharepoint-sites-and-onedrive-accounts"></a>Konfigurationsinformation för SharePoint-webbplatser och OneDrive-konton

När du väljer platsen **SharePoint-webbplatser** kan kvarhållningsprincipen behålla och ta bort dokument på SharePoint-kommunikationswebbplatser, gruppwebbplatser som inte är anslutna med Microsoft 365-grupper samt klassiska webbplatser. Gruppwebbplatser som är anslutna med Microsoft 365-grupper stöds inte med det här alternativet, utan använder istället platsen **Microsoft 365-grupper** som gäller för innehåll i gruppens postlåda, webbplats och filer.

Även om kvarhållningsprincipen tillämpas på webbplatsnivå tillämpas kvarhållningsinställningar bara på dokument. Detaljerad information om vad som inkluderas och exkluderas när du konfigurerar kvarhållningsinställningar för SharePoint och OneDrive finns i [Vad ingår för kvarhållning och borttagning](retention-policies-sharepoint.md#whats-included-for-retention-and-deletion). 

När du anger platserna för SharePoint-webbplatser eller OneDrive-konton behöver du inte behörighet för att komma åt webbplatserna och ingen verifiering utförs när du anger URL-adressen på sidan **Redigera platser**. I slutet av guiden kontrolleras däremot att de SharePoint-webbplatser som du anger finns. Om kontrollen misslyckas visas ett meddelande om att verifieringen misslyckades för URL-adressen du angav och guiden skapar inte kvarhållningsprincipen förrän verifieringskontrollen godkänns. Om det här meddelandet visas går du tillbaka i guiden och ändrar URL-adressen eller tar bort webbplatsen från kvarhållningsprincipen.

För att ange enskilda OneDrive-konton som ska inkluderas eller exkluderas har URL-adressen följande format: `https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`

Exempelvis för en användare i Contoso-klientorganisationen som har användarnamnet "rsimone": `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`

Information om hur du verifierar klientorganisationens syntax och identifierar URL-adresser för användare finns i [Få en lista över alla OneDrive-URL:er för användare i organisationen](/onedrive/list-onedrive-urls).

### <a name="configuration-information-for-microsoft-365-groups"></a>Konfigurationsinformation för Microsoft 365-grupper

För att behålla eller ta bort innehåll för en Microsoft 365-grupp (tidigare Office 365-grupp) använder du platsen **Microsoft 365-grupper**. Även om en Microsoft 365-grupp har en Exchange-postlåda så kommer en kvarhållningsprincip som inkluderar hela platsen **Exchange-e-post** inte att inkludera innehåll i Microsoft 365-gruppostlådor. Även om du med platsen **Exchange-e-post** till en början kan ange att en gruppostlåda ska inkluderas eller exkluderas visas ett felmeddelande om att "RemoteGroupMailbox" inte är ett giltigt val för Exchange-platsen när du försöker spara kvarhållningsprincipen.

En kvarhållningsprincip som används för en Microsoft 365-grupp inkluderar som standard gruppostlådan och SharePoint-gruppwebbplatsen. Filer som lagras på SharePoint-gruppwebbplatsen omfattas av den här platsen, men inte Teams-chattar eller Teams-kanalmeddelanden som har sina egna platser för kvarhållningsprinciper.

Om du vill ändra standardvärdet eftersom du vill att kvarhållningsprincipen bara ska gälla för Microsoft 365-postlådorna eller bara de anslutna SharePoint-gruppwebbplatserna använder du PowerShell-cmdleten [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) med parametern *Applications* med något av följande värden:

- `Group:Exchange` för bara Microsoft 365-postlådor som är anslutna till gruppen.
- `Group:SharePoint` för bara SharePoint-webbplatser som är anslutna till gruppen.

Om du vill återgå till standardvärdet för både postlådan och SharePoint-webbplatsen för de valda Microsoft 365-grupperna anger du `Group:Exchange,SharePoint`.

### <a name="configuration-information-for-skype-for-business"></a>Konfigurationsinformation för Skype för företag

Till skillnad från Exchange-e-post kan du inte aktivera status för Skype-platsen så att alla användare automatiskt inkluderas. När du aktiverar den platsen måste du manuellt välja de användare vars konversationer du vill behålla:

![Välj Skype-plats för kvarhållningsprinciper](../media/skype-location-retention-policies.png)

När du väljer **Välj användare** kan du snabbt ta med alla användare genom att markera kryssrutan **Välj alla**. Det är dock viktigt att förstå att varje användare räknas som en specifik inkludering i principen. Så om du inkluderar 1 000 användare genom att markera rutan **Välj alla** är det samma som om du manuellt valde 1 000 användare att inkludera, vilket är det högsta antalet som stöds för Skype för företag.

Observera att **Konversationshistorik**, en mapp i Outlook, är en funktion som inte har något med Skype-arkivering att göra. **Konversationshistorik** kan inaktiveras av slutanvändaren, men arkivering för Skype utförs genom att en kopia av Skype-konversationerna lagras i en dold mapp som inte är tillgänglig för användaren men är tillgänglig för eDiscovery.

## <a name="settings-for-retaining-and-deleting-content"></a>Inställningar för att behålla och ta bort innehåll

När du väljer inställningarna för att behålla och ta bort innehåll i kvarhållningsprincipen får kvarhållningsprincipen en av följande konfigurationer under en angiven tidsperiod:

- Endast behålla

    För den här konfigurationen väljer du **Behålla objekt under en viss tidsperiod** och **I slutet av kvarhållningsperioden: Gör ingenting**. Eller välj **Behåll objekt permanent**.

- Behålla och sedan ta bort

    För den här konfigurationen väljer du **Behålla objekt under en viss tidsperiod** och **I slutet av kvarhållningsperioden: Ta bort objekt automatiskt**.

- Endast ta bort

    För den här konfigurationen väljer du **Ta endast bort objekt när de når en viss ålder**.

### <a name="retaining-content-for-a-specific-period-of-time"></a>Behålla innehåll under en viss tidsperiod

När du konfigurerar en kvarhållningsprincip väljer du att behålla objekt under ett visst antal dagar, månader eller år. Du kan också behålla objekten permanent.

När du konfigurerar en kvarhållningsprincip kan du välja att behålla innehåll permanent eller under ett visst antal dagar, månader eller år. Kvarhållningsperioden beräknas utifrån innehållets ålder, inte från när kvarhållningsprincipen tillämpas.

I början av kvarhållningsperioden kan du också välja när innehållet skapades eller när det senast ändrades, men det senare stöds bara för filer och SharePoint, OneDrive och Microsoft 365-grupper.

Exempel:

- SharePoint: Om du vill behålla objekt i en webbplatssamling i sju år efter att innehållet senast ändrades och ett dokument i webbplatssamlingen inte har ändrats på sex år behålls dokumentet bara i ytterligare ett år om det inte ändras. Om dokumentet redigeras igen beräknas dokumentets ålder från det nya senast ändrade datumet och det behålls i ytterligare sju år.

- Exchange: Om du vill behålla objekt i en postlåda i sju år och ett meddelande skickades för sex år sedan behålls meddelandet i endast ett år. För Exchange-objekt baseras åldern på mottagningsdatumet för inkommande e-post, eller på sändningsdatumet för utgående e-post. Att behålla objekt baserat på när det senast ändrades gäller endast för webbplatsinnehåll i OneDrive och SharePoint.

I slutet av kvarhållningsperioden väljer du om du vill att innehållet ska tas bort permanent:

![Sida för kvarhållningsinställningar](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)

### <a name="deleting-content-thats-older-than-a-specific-age"></a>Ta bort innehåll som är äldre än en viss ålder

En kvarhållningsprincip kan både behålla och sedan ta bort objekt, eller ta bort gamla objekt utan att behålla dem.

Om kvarhållningsprincipen tar bort objekt är det i båda fallen viktigt att förstå att den angivna tidsperioden för en kvarhållningsprincip beräknas från den tid då objektet skapades eller ändrades, och inte tiden sedan principen tilldelades.

Innan du tilldelar en kvarhållningsprincip för första gången, och särskilt när den principen tar bort objekt, bör du först beakta åldern på det befintliga innehållet och hur principen kan påverka innehållet. Du kanske också vill informera användarna om den nya principen innan du tilldelar den, så att de får tid att utvärdera dess eventuella effekt.

### <a name="a-policy-that-applies-to-entire-locations"></a>En princip som gäller för hela platser

När du väljer platser, med undantag för Skype för företag, är standardinställningen **Alla** när statusen för platsen är **På**.

När en kvarhållningsprincip gäller för en kombination av hela platser finns det ingen begränsning för till exempel antalet mottagare, webbplatser, konton eller grupper som principen kan omfatta.

Om en princip till exempel omfattar alla Exchange-e-postmeddelanden och alla SharePoint-webbplatser, inkluderas alla webbplatser och mottagare oavsett hur många de är. För Exchange gäller att alla nya postlådor som skapats efter att principen tillämpats automatiskt ärver principen.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>En princip med specifika inkluderingar eller exkluderingar

Om du använder den valfria konfigurationen för att begränsa dina kvarhållningsinställningar till specifika användare, specifika Microsoft 365-grupper eller specifika webbplatser, finns det några begränsningar per princip som du bör känna till. Mer information finns i [Begränsningar för kvarhållningsprinciper och principer för kvarhållningsetiketter](retention-limits.md). 

Om du vill använda den valfria konfigurationen för att begränsa dina kvarhållningsinställningar kontrollerar du att **Status** för platsen är **På** och använder sedan länkarna för att inkludera eller exkludera vissa användare, Microsoft 365-grupper eller webbplatser.

> [!WARNING]
> Om du konfigurerar inkluderingar och sedan tar bort den sista återgår konfigurationen till **Alla** för platsen.  Kontrollera att det här är den konfiguration du vill använda innan du sparar principen.
>
> Om du till exempel anger en SharePoint-webbplats som ska inkluderas i din kvarhållningsprincip som är konfigurerad för att ta bort data, och sedan tar bort den enda webbplatsen, kommer alla SharePoint-webbplatser som standard att omfattas av kvarhållningsprincipen som tar bort data permanent. Samma gäller för Exchange-mottagare, OneDrive-konton, Teams-chattanvändare osv.
>
> I det här scenariot inaktiverar du platsen om du inte vill att inställningen **Alla** för platsen ska omfattas av kvarhållningsprincipen. Alternativt kan du ange exkluderingar som ska undantas från principen.

## <a name="updating-retention-policies"></a>Uppdatera kvarhållningsprinciper

Vissa inställningar kan inte ändras efter att en kvarhållningsprincip har skapats och sparats, till exempel:
- Kvarhållningsprincipens namn och kvarhållningsinställningarna förutom kvarhållningsperioden och när kvarhållningsperioden ska börja.

Om du redigerar en kvarhållningsprincip och objekt redan omfattas av de ursprungliga inställningarna i kvarhållningsprincipen tillämpas de uppdaterade inställningarna automatiskt på de här objekten utöver objekt som nyligen har identifierats.

Den här uppdateringen är vanligtvis relativt snabb, men kan ta flera dagar. När principreplikeringen för dina Microsoft 365-platser är klar ser du att statusen för kvarhållningsprincipen i Microsoft 365 Efterlevnadscenter ändras från **På (väntar)** till **På (genomförd)**.

## <a name="locking-the-policy-to-prevent-changes"></a>Låsa principen för att förhindra ändringar

Om du behöver se till att ingen kan inaktivera principen, ta bort principen eller göra den mindre restriktiv kan du läsa mer i [Använda bevarandelås för att begränsa ändringar av kvarhållningsprinciper och principer för kvarhållningsetiketter](retention-preservation-lock.md).
