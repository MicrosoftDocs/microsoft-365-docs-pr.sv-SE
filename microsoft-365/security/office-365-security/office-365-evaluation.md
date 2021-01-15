---
title: Utvärdera Microsoft Defender för Office 365
description: Defender för Office 365 i utvärderingsprogrammet skapar principer för e-post för Defender för Office 365 som loggar verdicts, till exempel skadlig program vara, men fungerar inte på meddelanden.
keywords: utvärdera Office 365, Microsoft Defender för Office 365, Office 365-utvärdering, testa Office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8f105215b23ec49318c133714e758e2a2a9c1df
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870927"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Utvärdera Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Utvärderings versionen av Microsoft Defender för Office 365 är i offentlig för hands version. Denna för hands version tillhandahålls utan service nivå avtal. Vissa funktioner kanske inte stöds eller så har de begränsad kapacitet.

Genom att utföra en omfattande utvärdering av en säkerhets produkt kan du få ett välinformerade beslut om uppgraderingar och köp. Det hjälper till att pröva säkerhets produktens kapacitet för att bedöma hur den kan hjälpa din säkerhets åtgärd i sina dagliga uppgifter.

Utvärderings versionen av [Microsoft Defender för Office 365](office-365-atp.md) är utformad för att eliminera komplexa enheter och miljö konfiguration så att du kan fokusera på att utvärdera funktionerna i säkerhets lösningen. Det gäller endast för e-postskydd och inte SharePoint, Office-klienter eller team.

Om du inte redan har en licens som stöder Microsoft Defender för Office 365 kan du starta en [kostnads fri utvärderings version i 30 dagar](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) och testa funktionerna i säkerhets & för Office 365 https://protection.office.com/homepage) . Du kommer att använda snabb installationen och du kan enkelt stänga av den om det behövs.

## <a name="how-the-evaluation-works"></a>Så här fungerar utvärderingen

Defender för Office 365 i utvärderingsprogrammet skapar principer för e-post för Defender för Office 365 som loggar verdicts, till exempel skadlig program vara, men fungerar inte på meddelanden. Du behöver inte ändra din MX-postkonfiguration.

Utvärderings läget, [säkra bifogade filer](atp-safe-attachments.md), [säkra länkar](atp-safe-links.md)och konfigurations [principer för nätfiske](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) är inställda för din räkning. Alla principer för Defender för Office 365 skapas i läget ej tvingande i bakgrunden och syns inte för dig.

Som en del av inställningen konfigurerar utvärderings läget också [utökad filtrering för kopplingar](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors). Den förbättrar filtreringen genom att bevara information om IP-adresser och avsändare, som annars försvinner när e-post skickas via en e-postsäker Gateway (ESG) framför Defender för Office 365. Förbättrad filtrering förbättrar också filtrerings precisionen för skydd mot skräp post och nätfiske för Exchange Online Protection (EOP).

Om du vill minska eventuell produktions påverkan för vissa scenarier som inte stöds, kan du kringgå all EOP-filtrering genom att skapa en transport regel för att ange nivån för skräp post (SCL) till-1. Mer information finns i [använda UK för att skapa en regel för e-postflöde som anger SCL för ett meddelande](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   .

När du har konfigurerat utvärderings läget kommer du att få en rapport uppdaterad varje dag med upp till 90 dagar med data som kvantifierar de meddelanden som skulle ha blockerats om principerna har implementerats (till exempel ta bort, skicka till skräp post, karantän). Rapporter skapas för alla Defender för Office 365 och EOP-identifieringar. De aggregeras per identifierings teknik (till exempel personifiering) och kan filtreras efter tidsintervall. Dessutom kan meddelande rapporter skapas på begäran för att skapa anpassade pivottabeller eller för djupa spelmeddelanden med hjälp av Threat Explorer.

Med den förenklade inställnings upplevelsen kan du fokusera på:

- Köra utvärderingen
- Få en detaljerad rapport
- Analyserar rapporten för åtgärden
- Visar resultatet från utvärderingen

## <a name="before-you-begin"></a>Innan du börjar

### <a name="licensing"></a>Licensiering

För att få åtkomst till utvärderingen måste du uppfylla licens kraven. Följande licenser fungerar:

- Microsoft Defender för Office 365 Abonnemang 1
- Microsoft Defender för Office 365 abonnemang 2
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

Om du inte har någon av dessa licenser måste du skaffa en utvärderings licens.

#### <a name="trial"></a>Kostnads

För att få en utvärderings licens för Microsoft Defender för Office 365 måste du ha **rollen fakturerings administratör** eller **Global administratör**. Begära tillstånd från någon som har rollen som global administratör. [Lär dig mer om prenumerationer och licenser](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

När du har rätt roll är den rekommenderade sökvägen att få en utvärderings version av Microsoft Defender för Office 365 (abonnemang 2) i Microsoft 365 Admin Center genom att gå till fakturerings > Köp tjänster. Test versionen inkluderar en gratis prov period på 30 dagar för 25 licenser. [Skaffa en utvärderings version av Microsoft Defender för Office 365 (abonnemang 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Du får ett 30 dagars fönster med utvärderingen för att övervaka och rapportera avancerade hot. Du kan också köpa ett betalt abonnemang om du vill ha fullständig Defender för Office 365-funktioner.

### <a name="roles"></a>Role

Exchange Online-roller krävs för att konfigurera Defender för Office 365 i utvärderings läge.

- [Lär dig mer om behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [Lär dig mer om hur du tilldelar administratörs roller](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

Följande roller behövs:

|Uppgift|Roll|
|---|---|
|Skaffa en gratis prov period eller Köp Microsoft Defender för Office 365 (abonnemang 2)|Rollen fakturerings administratör eller rollen global administratör|
|Skapa utvärderings princip|Rollen fjärrsamt godkända domäner; Rollen säkerhets administratör|
|Redigera utvärderings policy|Rollen fjärrsamt godkända domäner; Rollen säkerhets administratör|
|Ta bort utvärderings policy|Rollen fjärrsamt godkända domäner; Rollen säkerhets administratör |
|Visa utvärderings rapport|Rollen säkerhets administratör eller rollen säkerhets läsare|
|


### <a name="enhanced-filtering"></a>Förbättrad filtrering

Dina Exchange Online Protection-principer, till exempel Mass-och skräp post skydd, förblir desamma. Meddelande leveransen förblir också likadan. Utvärderingen aktiverar emellertid utökad filtrering för kopplingar, som påverkar dina e-postflöden och Exchange Online Protection-principer om de inte kringgås.

Förbättrad filtrering för kopplingar gör att klient organisationer kan använda skydd mot förfalskning. Skydd mot förfalskning stöds inte om du använder en e-postsäker Gateway (ESG) utan att aktivera utökad filtrering för kopplingar.

### <a name="urls"></a>Garanteras

URL-adresser kommer att sprängas under e-postflöde. Om du inte vill att vissa URL-adresser sprängade kan du hantera listan över tillåtna URL: er. Se [hantera URL-adresser i listan Tillåt/begränsa klient organisation](tenant-allow-block-list.md) för mer information.

URL-länkar i e-postmeddelandenas delar kommer inte att radbrytas, för att minska kund påverkan.

### <a name="email-routing"></a>E-postdirigering

Förbered motsvarande uppgifter som du behöver för att konfigurera e-postmeddelandet för närvarande, inklusive namnet på den inkommande kopplingen som dirigerar din e-post. Om du bara använder Exchange Online Protection har du ingen koppling.  [Lär dig mer om e-postflöde och e-postdirigering](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Scenarion för e-postdirigering som stöds:

- **Partner från tredje part och/eller lokal tjänst**: den inkommande koppling som du vill utvärdera använder en tredjepartsleverantör och/eller du använder en lösning för e-postsäkerhet.
- **Endast Microsoft Exchange Online Protection**: den klient organisation som du vill utvärdera använder Office 365 för e-postsäkerhet och Mail Exchange-posten pekar på Microsoft.

### <a name="email-security-gateway"></a>E-postsäker Gateway

Om du använder en tredjeparts e-mail Security Gateway (ESG) måste du känna till leverantörens namn. Om du använder en ESG-lokal eller icke-stödED leverantör måste du känna till de offentliga IP-adresserna för enheterna.

Partner som stöds tredje part inkluderar:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Omfattningen

Du kan omfånget med utvärderingen till en inkommande koppling. Om det inte finns någon anslutning konfigurerad tillåter utvärderings omfattningen administratören att samla in data från alla användare i klient organisationen för att utvärdera Defender för Office 365.

## <a name="get-started-with-the-evaluation"></a>Komma igång med utvärderingen

Leta reda på utvärderings versionen av Microsoft Defender för Office 365 i Office 365 Security & Compliance Center ( https://protection.office.com/homepage) från tre åtkomst punkter:

- Instrument panel för Threat Management >
- Policy för Threat Management >
- > instrument panel för rapporter

## <a name="setting-up-the-evaluation"></a>Ställa in utvärderingen

När du har startat inställnings flödet för utvärderingen får du två alternativ för routning. Beroende på konfigurationen och utvärderings behoven i din organisation kan du välja om du vill använda en tredje part och/eller lokal tjänst leverantör eller bara Microsoft Exchange Online.

- Om du använder en tredjeparts partner och/eller lokal tjänst leverantör måste du välja namnet på leverantören i den nedrullningsbara menyn. Ange andra kopplings uppgifter.

- Välj Microsoft Exchange Online om MX-posten pekar på Microsoft och du har en Exchange Online-postlåda.

Granska inställningarna och redigera dem om det behövs. Välj sedan **Skapa utvärdering**. Du får ett bekräftelse meddelande om att din inställning är färdig.

Utvärderings rapporten för Microsoft Defender för Office 365 genereras en gång per dag. Det kan ta upp till 24 timmar innan informationen fylls.

### <a name="exchange-rules-optional"></a>Exchange-regler (valfritt)

Om du har en befintlig gateway kanske du vill kringgå filtreringen eftersom den aktiverar utökade filtreringar för kopplingar och ändrar inkommande IP-adress för avsändare. Gå till administrations centret för Exchange och skapa en princip för SCL-1 (om du inte redan har ett). Mer information om regel komponenterna och hur de fungerar finns i regler för e-postflöde (transport regler) i Exchange Online.

## <a name="evaluate-capabilities"></a>Utvärdera funktioner

När utvärderings rapporten har genererats kan du se hur många avancerade hot länkar, avancerade hot bilagor och potentiella personer som kan identifieras i din organisation.

När utvärderings versionen har gått ut kan du fortsätta att få till gång till rapporten i 90 dagar. Men samlar inte in mer information. Om du vill fortsätta att använda Microsoft Defender för Office 365 när utvärderings versionen har upphört, se till att du [köper ett betalt abonnemang för Microsoft Defender för office 365 (abonnemang 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Du kan gå till **Inställningar** för att uppdatera din routning eller stänga av utvärderingen när som helst. Men du måste gå igenom samma inställning igen om du vill fortsätta med utvärderingen när du har inaktiverat den.

## <a name="provide-feedback"></a>Ge feedback

Din feedback hjälper oss att bli bättre när du skyddar din miljö från avancerade attacker. Dela med dig av produkten och exponeringarna samt utvärderings resultaten.

Välj **ge feedback** för att berätta vad du tycker.
