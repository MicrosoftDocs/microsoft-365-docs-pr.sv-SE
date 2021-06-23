---
title: Utvärdera Microsoft Defender för Office 365
description: Defender för Office 365 i utvärderingsläge skapar Defender för Office 365-e-postprinciper som loggar ut, till exempel skadlig programvara, men inte agerar på meddelanden.
keywords: utvärdera Office 365, Microsoft Defender för Office 365, utvärdering av Office 365, prova Office 365, Microsoft Defender, Microsoft Defender för slutpunkt
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
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
ms.openlocfilehash: 89562a5fd7c2d869f8a060e7ceda1c32a093c175
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083674"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Utvärdera Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Utvärdering av Microsoft Defender Office 365 utvärdering är en offentlig förhandsversion. Den här förhandsversionen tillhandahålls utan ett servicenivåavtal. Vissa funktioner kanske inte stöds eller kan ha begränsade funktioner.

Genom att göra en noggrann utvärdering av säkerhetsprodukter kan du få välgrundade beslut om uppgraderingar och inköp. Det underlättar att prova säkerhetsproduktens funktioner för att bedöma hur den kan hjälpa teamet med säkerhetsåtgärder i sina dagliga uppgifter.

[Utvärderingsupplevelsen i Microsoft Defender Office 365](defender-for-office-365.md) är utformad för att eliminera komplexiteten i konfigurationen av enheter och miljöer så att du kan fokusera på att utvärdera funktionerna i Microsoft Defender för Office 365. Med utvärderingsläget kan alla meddelanden som skickas Exchange Online e-postlådor utvärderas utan att MX-poster pekar på Microsoft. Funktionen gäller endast e-postskydd och inte för Office klienter som Word, SharePoint eller Teams.

Om du inte redan har en licens som stöder Microsoft Defender för Office 365 kan du påbörja en kostnadsfri [30-dagarsutvärdering](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) och testa funktionerna i Microsoft 365 Defender-portalen på <https://security.microsoft.com> . Du kommer att njuta av den snabba uppsättningen och du kan enkelt stänga av den om det behövs.

> [!NOTE]
> Om du är på Microsoft 365 Defender-portalen ( ) kan du starta en Defender för Office 365-utvärdering här: E-& för samarbete & principer för regel hot andra avsnitt <https://security.microsoft.com>  \>  \>  \>  \> **utvärderingsläge.**

## <a name="how-the-evaluation-works"></a>Så här fungerar utvärderingen

Defender för Office 365 i utvärderingsläge skapar Defender för Office 365-e-postprinciper som loggar ut, till exempel skadlig programvara, men inte agerar på meddelanden. Du behöver inte ändra konfigurationen av MX-posten.

Med utvärderingsläge kan [Valv,](safe-attachments.md) [Valv,](safe-links.md)länkar och [postlådebaserade](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) personifieringsprinciper konfigureras åt dig. Alla Defender Office 365 principer skapas i icke-tvingande läge i bakgrunden och visas inte för dig.

Som en del av konfigurationen konfigurerar utvärderingsläget även [Utökad filtrering för kopplingar.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Filtreringen förbättrar filtreringsprecisionen genom att bevara IP-adress och avsändarinformation, som annars försvinner när e-post passerar genom en e-postsäkerhetsgateway (ESG) framför Defender för Office 365. Förbättrad filtrering för kopplingar förbättrar också filtreringsprecisionen för din Exchange Online Protection (EOP) skydd mot skräppost och nätfiske.

Förbättrad filtrering för kopplingar förbättrar filtreringsprecisionen men kan ändra slutbarheten för vissa meddelanden om du har en ESG framför Defender för Office 365 och för närvarande inte kringgår EOP-filtrering. Effekterna är begränsade till EOP-principer. MDO-principer som har ställts in som en del av utvärderingen skapas i icke-verkställande läge. Om du vill minimera potentiell produktionsrisk kan du kringgå all EOP-filtrering genom att skapa en e-postflödesregel (kallas även transportregel) för att ange SCL (Spam Confidence Level) för meddelanden till -1. Mer information finns i Använda e-postflödesregler för att ange [SCL (Spam Confidence Level) i](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)Exchange Online postmeddelanden.  

När utvärderingsläget har ställts in får du en rapport som uppdateras dagligen med upp till 90 dagars data om de meddelanden som skulle ha blockerats om principerna implementerats (till exempel ta bort, skicka till skräppost, karantän). Rapporter skapas för alla Defender för identifiering Office 365 och EOP. De aggregeras per identifieringsteknik (till exempel personifiering) och kan filtreras efter tidsperiod. Dessutom kan du skapa meddelanderapporter på begäran för att skapa anpassade pivoter eller för att djupdykar meddelanden med hjälp av Utforskaren.

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
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

Om du inte har någon av dessa licenser måste du skaffa en utvärderingslicens.

#### <a name="trial"></a>Utvärderingsversion

Om du vill ha en utvärderingslicens för Microsoft Defender för Office 365 måste du ha rollen **Faktureringsadministratör** eller **Global administratör.** Begära behörighet från någon som har rollen Global administratör. [Läs mer om prenumerationer och licenser](../../commerce/licenses/subscriptions-and-licenses.md)

När du har rätt roll är den rekommenderade sökvägen till att skaffa en utvärderingslicens för Microsoft Defender för Office 365 (abonnemang 2) i Administrationscenter för Microsoft 365 genom att gå till Fakturering > Köptjänster. Utvärderingsversionen omfattar en kostnadsfri provperiod på 30 dagar för 25 licenser. [Hämta en utvärderingsversion av Microsoft Defender för Office 365 (abonnemang 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Du har ett 30-dagarsfönster med utvärdering för att övervaka och rapportera avancerade hot. Du kan också köpa en betald prenumeration om du vill ha hela Defender för Office 365 prenumeration.

### <a name="roles"></a>Roller

**Exchange Online rollerna krävs** för att konfigurera Defender för Office 365 i utvärderingsläge. Att tilldela en Microsoft 365- eller säkerhetsadministratörsroll kommer inte att fungera.

- [Läs mer om behörigheter i Exchange Online](/exchange/permissions-exo/permissions-exo)
- [Läs mer om hur du tilldelar administratörsroller](../../admin/add-users/assign-admin-roles.md)

Följande roller krävs:

|Uppgift|Roll (i Exchange Online)|
|---|---|
|Skaffa en kostnadsfri utvärderingsversion eller köp Microsoft Defender för Office 365 (abonnemang 2)|Rollen Faktureringsadministratör ELLER Global administratör|
|Skapa utvärderingsprincip|Roll för fjärr- och godkända domäner. Säkerhetsadministratörsroll|
|Redigera utvärderingsprincip|Roll för fjärr- och godkända domäner. Säkerhetsadministratörsroll|
|Ta bort utvärderingsprincip|Roll för fjärr- och godkända domäner. Säkerhetsadministratörsroll |
|Visa utvärderingsrapport|Rollen Säkerhetsadministratör ELLER Säkerhetsläsare|
|

### <a name="enhanced-filtering"></a>Förbättrad filtrering

Dina Exchange Online Protection principer, till exempel skydd mot massutskick och skräppost, förblir desamma. Men utvärderingen aktiverar förbättrad filtrering för kopplingar, vilket kan påverka ditt e-postflöde och Exchange Online Protection principer om de inte kringgås.

Förbättrad filtrering för kopplingar gör att klientorganisationen kan använda skydd mot förfalskning. Förfalskning stöds inte om du använder en ESG (E-postsäkerhetsgateway) utan att ha aktiverat Utökad filtrering för kopplingar.

### <a name="urls"></a>URL:er

URL:er löses upp under e-postflödet. Om du inte vill att specifika URL:er ska detoneras kan du hantera listan med tillåtna URL:er på rätt sätt. Mer [information finns i Hantera listan över tillåtna/blockerade klientorganisationen.](tenant-allow-block-list.md)

URL-länkar i e-postmeddelandeorganen radbryts inte för att minska kundinslag.

### <a name="email-routing"></a>E-postdirigering

Förbered motsvarande information som du behöver för att ställa in hur din e-post dirigeras, inklusive namnet på den inkommande kopplingen som dirigerar din e-post. Om du bara använder Exchange Online Protection har du ingen koppling.  [Läs mer om e-postflöde och e-postdirigering](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Exempel på e-postdirigeringsscenarier som stöds:

- **Tredjepartspartner och/eller** lokal tjänsteleverantör: Den inkommande anslutningen du vill utvärdera använder en tredjepartsleverantör och/eller så använder du en lösning för e-postsäkerhet lokalt.
- **Microsoft Exchange Online skydd:** Den klientorganisation som du vill utvärdera använder Office 365 för e-postsäkerhet och MX-Exchange (Mail) pekar på Microsoft.

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

Du hittar kortet för Office 365 för utvärdering i e-Microsoft 365 Defender <https://security.microsoft.com> () från tre åtkomstpunkter:

- **Slutpunkter** \> **Sårbarhetshantering** \> **Instrumentpanel** ( <https://security.microsoft.com/tvm_dashboard> )
- **Skicka e& och samarbete** \> **Principer & regler** \> **Hotprinciper** ( <https://security.microsoft.com/threatpolicy> )
- **Rapporter** \> **Skicka e& och samarbete** \> **Skicka e& och samarbetsrapporter** ( <https://security.microsoft.com/emailandcollabreport> )

## <a name="setting-up-the-evaluation"></a>Konfigurera utvärderingen

När du startar set-up-flödet för din utvärdering får du två alternativ för dirigering. Beroende på organisationens behov av e-postdirigering och utvärdering kan du välja om du använder en tredjepartsleverantör och/eller en lokal tjänsteleverantör eller bara Microsoft Exchange Online.

- Om du använder en tredjepartspartner och/eller en lokal tjänsteleverantör måste du välja namnet på leverantören i listrutan. Ange annan kopplingsrelaterad information.

- Välj Microsoft Exchange Online om MX-posten pekar på Microsoft och du har en Exchange Online postlåda.

Granska inställningarna och redigera dem om det behövs. Välj sedan **Skapa utvärdering.** Du bör få ett bekräftelsemeddelande som anger att kon set-up är klar.

Utvärderingsrapporten i Microsoft Defender Office 365 genereras en gång per dag. Det kan ta upp till 24 timmar innan data fylls i.

### <a name="exchange-mail-flow-rules-optional"></a>Exchange för e-postflöde (valfritt)

Om du har en befintlig gateway aktiverar aktivering av utvärderingsläge Utökad filtrering för kopplingar. Den här funktionen förbättrar filtreringsprecisionen genom att ändra IP-adressen för inkommande avsändare. Den här funktionen kan ändra filtrets bedömningar, och om du inte kringgår Exchange Online Protection kan detta ändra slutbarheten för vissa meddelanden. I det här fallet kanske du tillfälligt vill kringgå filtrering för att analysera påverkan. Om du vill kringgå filtrering öppnar du Exchange admin center (EAC) vid och skapar en e-postflödesregel som anger SCL för meddelanden till -1 (om du inte redan har <https://admin.exchange.microsoft.com> ett). Instruktioner finns i Använda [e-postflödesregler för att ange SCL (Spam Confidence Level) i meddelanden i Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

## <a name="evaluate-capabilities"></a>Utvärdera funktioner

När utvärderingsrapporten har skapats kan du se hur många avancerade länkar till hot, avancerade hotbilagor och möjliga personifieringar som har identifierats i e-postmeddelanden och samarbetsarbetsytor i organisationen.

När utvärderingsversionen har upphört att gälla kan du fortsätta att komma åt rapporten i 90 dagar. Men det samlar inte in mer information. Om du vill fortsätta använda Microsoft Defender för Office 365 när utvärderingsversionen har upphört kontrollerar du att du köper en betalprenumeration på Microsoft Defender för [Office 365 (abonnemang 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Du kan när **Inställningar** ändra dirigeringen eller inaktivera utvärderingen. Du måste dock gå igenom samma process igen om du bestämmer dig för att fortsätta utvärderingen när du har inaktiverat den.

## <a name="provide-feedback"></a>Ge feedback

Din feedback hjälper oss att bli bättre på att skydda miljön mot avancerade attacker. Dela din upplevelse och intryck av produktfunktioner och utvärderingsresultat.

Välj **Lämna feedback** och berätta vad du tycker.
