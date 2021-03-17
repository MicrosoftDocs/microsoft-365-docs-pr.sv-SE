---
title: Utvärdera Microsoft Defender för Office 365
description: Defender för Office 365 i utvärderingsläge skapar Defender för Office 365-e-postprinciper som loggar in utvärderingsbedömningar, till exempel skadlig programvara, men inte agerar på meddelanden.
keywords: utvärdera Office 365, Microsoft Defender för Office 365, utvärdering av Office 365, prova Office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce17f413b23ef9ef6abf79a2710a5cec9b05206c
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838537"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Utvärdera Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Utvärdering av Microsoft Defender för Office 365 är en offentlig förhandsversion. Den här förhandsversionen tillhandahålls utan ett servicenivåavtal. Vissa funktioner kanske inte stöds eller kan ha begränsade funktioner.

Om du genomför en omfattande utvärdering av säkerhetsprodukter kan det vara bra att fatta välgrundade beslut om uppgraderingar och inköp. Det underlättar att prova säkerhetsproduktens funktioner för att bedöma hur den kan hjälpa teamet med säkerhetsåtgärder i sina dagliga uppgifter.

Utvärderingsupplevelsen i Microsoft Defender för [Office 365](office-365-atp.md) är utformad för att eliminera komplexiteten hos enhets- och miljökonfigurationen så att du kan fokusera på att utvärdera funktionerna i Microsoft Defender för Office 365. Med utvärderingsläget kan alla meddelanden som skickas till Exchange Online-postlådor utvärderas utan att MX-poster pekar på Microsoft. Funktionen gäller endast e-postskydd och inte Office-klienter som Word, SharePoint eller Teams.

Om du inte redan har en licens som stöder Microsoft Defender för Office 365 kan du påbörja en kostnadsfri utvärdering under [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) dagar och testa funktionerna i Säkerhets- och efterlevnadscenter för Office 365 & ( https://protection.office.com/homepage) . Du kommer att njuta av den snabba uppsättningen och du kan enkelt stänga av den om det behövs.

## <a name="how-the-evaluation-works"></a>Så här fungerar utvärderingen

Defender för Office 365 i utvärderingsläge skapar Defender för Office 365-e-postprinciper som loggar in utvärderingsbedömningar, till exempel skadlig programvara, men inte agerar på meddelanden. Du behöver inte ändra konfigurationen av MX-posten.

Med utvärderingsläge [konfigureras felsäkert](atp-safe-attachments.md) [bifogade](atp-safe-links.md)filer, säkra länkar och postlådebaserade [personifieringsprinciper](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) för din räkning. Alla Defender för Office 365-principer skapas i icke-tvingande läge i bakgrunden och visas inte för dig.

Som en del av konfigurationen konfigurerar utvärderingsläget även [Utökad filtrering för kopplingar.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Filtreringen förbättrar filtreringsprecisionen genom att bevara IP-adress och avsändarinformation, som annars försvinner när e-post passerar genom en e-postsäkerhetsgateway (ESG) framför Defender för Office 365. Förbättrad filtrering för kopplingar förbättrar också filtreringsprecisionen för ditt befintliga EOP-skydd (Exchange Online Protection) mot skräppost och skydd mot nätfiske.

Förbättrad filtrering för kopplingar har förbättrats filtreringsprecisionen men kan ändra slutbarheten för vissa meddelanden om du har en ESG framför Defender för Office 365 och för närvarande inte kringgår EOP-filtrering. Effekterna är begränsade till EOP-principer. Konfiguration av MDO-principer som en del av utvärderingen skapas i icke-verkställande läge. Om du vill minimera potentiell produktionsrisk kan du kringgå all EOP-filtrering genom att skapa en transportregel som anger SCL (Spam Confidence Level) till -1. Mer [information finns i Använda EAC för att skapa](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)en e-postflödesregel som anger SCL för ett   meddelande.

När utvärderingsläget har ställts in får du en rapport som uppdateras dagligen med upp till 90 dagars data om de meddelanden som skulle ha blockerats om principerna implementerats (till exempel ta bort, skicka till skräppost, karantän). Rapporter skapas för alla Defender för Office 365- och EOP-identifieringar. De aggregeras per identifieringsteknik (till exempel personifiering) och kan filtreras efter tidsperiod. Dessutom kan du skapa meddelanderapporter på begäran för att skapa anpassade pivoter eller för att djupdykning av meddelanden med hjälp av Threat Explorer.

Med den förenklade uppsättningen kan du fokusera på:

- Köra utvärderingen
- Hämta en detaljerad rapport
- Analysera rapporten för åtgärd
- Presentera utvärderingsresultatet

## <a name="before-you-begin"></a>Innan du börjar

### <a name="licensing"></a>Licensiering

För att få åtkomst till utvärderingen måste du uppfylla licenskraven. Någon av följande licenser fungerar:

- Microsoft Defender för Office 365 Abonnemang 1
- Microsoft Defender för Office 365 abonnemang 2
- Microsoft 365 E5, Microsoft 365 E5 Säkerhet
- Office 365 E5

Om du inte har någon av dessa licenser måste du skaffa en utvärderingslicens.

#### <a name="trial"></a>Utvärderingsversion

Om du vill ha en utvärderingsversionslicens för Microsoft Defender för Office 365 måste du ha rollen Faktureringsadministratör **eller** **Global administratör.** Begära behörighet från någon som har rollen Global administratör. [Läs mer om prenumerationer och licenser](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

När du har rätt roll är den rekommenderade vägen att skaffa en utvärderingslicens för Microsoft Defender för Office 365 (abonnemang 2) i administrationscentret för Microsoft 365 genom att gå till Fakturering > Köptjänster. Utvärderingsversionen omfattar en kostnadsfri provperiod på 30 dagar för 25 licenser. [Hämta en utvärderingsversion av Microsoft Defender för Office 365 (abonnemang 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Du har ett 30-dagarsfönster med utvärdering för att övervaka och rapportera avancerade hot. Du kan också köpa en betald prenumeration om du vill ha hela Defender för Office 365-funktioner.

### <a name="roles"></a>Roller

Exchange Online-roller krävs för att konfigurera Defender för Office 365 i utvärderingsläge.

- [Läs mer om behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [Läs mer om hur du tilldelar administratörsroller](../../admin/add-users/assign-admin-roles.md)

Följande roller krävs:

|Uppgift|Roll|
|---|---|
|Skaffa en kostnadsfri utvärderingsversion eller köp Microsoft Defender för Office 365 (abonnemang 2)|Rollen Faktureringsadministratör ELLER Global administratör|
|Skapa utvärderingsprincip|Roll för fjärr- och godkända domäner. Säkerhetsadministratörsroll|
|Redigera utvärderingsprincip|Roll för fjärr- och godkända domäner. Säkerhetsadministratörsroll|
|Ta bort utvärderingsprincip|Roll för fjärr- och godkända domäner. Säkerhetsadministratörsroll |
|Visa utvärderingsrapport|Rollen Säkerhetsadministratör ELLER Säkerhetsläsare|
|


### <a name="enhanced-filtering"></a>Förbättrad filtrering

Dina Exchange Online Protection-principer, till exempel skydd för massutskick och skräppost, förblir desamma. Men utvärderingen aktiverar förbättrad filtrering för kopplingar, vilket kan påverka e-postflödet och Exchange Online Protection-principerna om de inte kringgås.

Förbättrad filtrering för kopplingar gör att klientorganisationen kan använda skydd mot förfalskning. Förfalskning stöds inte om du använder en ESG (E-postsäkerhetsgateway) utan att ha aktiverat Utökad filtrering för kopplingar.

### <a name="urls"></a>URL:er

URL:er löses upp under e-postflödet. Om du inte vill att specifika URL:er ska detoneras kan du hantera listan med tillåtna URL:er på rätt sätt. Mer [information finns i Hantera listan över tillåtna/blockerade klientorganisationen.](tenant-allow-block-list.md)

URL-länkar i e-postmeddelandeorganen radbryts inte för att minska kundinslag.

### <a name="email-routing"></a>E-postdirigering

Förbered motsvarande information som du behöver för att ställa in hur din e-post dirigeras, inklusive namnet på den inkommande kopplingen som dirigerar din e-post. Om du bara använder Exchange Online Protection har du ingen koppling.  [Läs mer om e-postflöde och e-postdirigering](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Exempel på e-postdirigeringsscenarier som stöds:

- **Tredjepartspartner och/eller** lokal tjänsteleverantör: Den inkommande anslutningen du vill utvärdera använder en tredjepartsleverantör och/eller så använder du en lösning för e-postsäkerhet lokalt.
- **Endast Microsoft Exchange Online Protection:** Den klientorganisation som du vill utvärdera använder Office 365 för e-postsäkerhet och MX-posten (Mail Exchange) pekar på Microsoft.

### <a name="email-security-gateway"></a>E-postsäkerhetsgateway

Om du använder en e-postsäkerhetsgateway från tredje part (ESG) måste du känna till leverantörens namn. Om du använder en lokal eller icke-stödd ESG-leverantör måste du känna till de offentliga IP-adresserna för enheterna.

Tredjepartspartner som stöds är:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Scoping

Du kan begränsa utvärderingen till en inkommande koppling. Om det inte finns någon konfigurerad anslutning kan administratörerna med utvärderingsomfånget samla in data från en användare i klientorganisationen för att utvärdera Defender för Office 365.

## <a name="get-started-with-the-evaluation"></a>Komma igång med utvärderingen

Leta reda på kortet för utvärderingsuppsättningen Microsoft Defender för Office 365 i Säkerhets- och & Office 365 (från https://protection.office.com/homepage) tre åtkomstpunkter:

- Hothantering > Instrumentpanel
- Policy för > hot
- Rapporter > Instrumentpanel

## <a name="setting-up-the-evaluation"></a>Konfigurera utvärderingen

När du startar set-up-flödet för din utvärdering får du två alternativ för dirigering. Beroende på organisationens behov av e-postdirigering och utvärdering kan du välja om du använder en tredjepartsleverantör och/eller en lokal tjänsteleverantör eller endast Microsoft Exchange Online.

- Om du använder en tredjepartspartner och/eller en lokal tjänsteleverantör måste du välja namnet på leverantören i listrutan. Ange annan kopplingsrelaterad information.

- Välj Microsoft Exchange Online om MX-posten pekar på Microsoft och du har en Exchange Online-postlåda.

Granska inställningarna och redigera dem om det behövs. Välj sedan **Skapa utvärdering.** Du bör få ett bekräftelsemeddelande som anger att kon set-up är klar.

Utvärderingsrapporten för Microsoft Defender för Office 365 genereras en gång per dag. Det kan ta upp till 24 timmar innan data fylls i.

### <a name="exchange-rules-optional"></a>Exchange-regler (valfritt)

Om du har en befintlig gateway aktiverar aktivering av utvärderingsläge utökad filtrering för kopplingar. Filtreringsprecisionen förbättras genom att IP-adressen för inkommande avsändare ändras. Detta kan ändra filtrets bedömningar och om du inte kringgår Exchange Online Protection kan detta ändra slutbarheten för vissa meddelanden. I det här fallet kanske du tillfälligt vill kringgå filtrering för att analysera påverkan. Om du vill kringgå detta går du till administrationscentret för Exchange och skapar en princip för SCL -1 (om du inte redan har en). Mer information om regelkomponenter och hur de fungerar finns i E-postflödesregler (transportregler) i Exchange Online.

## <a name="evaluate-capabilities"></a>Utvärdera funktioner

När utvärderingsrapporten har skapats kan du se hur många avancerade länkar till hot, avancerade hotbilagor och möjliga personifieringar som har identifierats i e-postmeddelanden och samarbetsarbetsytor i organisationen.

När utvärderingsversionen har upphört att gälla kan du fortsätta att komma åt rapporten i 90 dagar. Men det samlar inte in mer information. Om du vill fortsätta använda Microsoft Defender för Office 365 när utvärderingsversionen har gått ut bör du köpa en betalprenumeration på Microsoft Defender för [Office 365 (abonnemang 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Du kan när som **helst** gå till Inställningar och uppdatera routningen eller inaktivera utvärderingen. Du måste dock gå igenom samma process igen om du bestämmer dig för att fortsätta utvärderingen när du har inaktiverat den.

## <a name="provide-feedback"></a>Ge feedback

Din feedback hjälper oss att bli bättre på att skydda miljön mot avancerade attacker. Dela din upplevelse och intryck av produktfunktioner och utvärderingsresultat.

Välj **Lämna feedback** och berätta vad du tycker.
