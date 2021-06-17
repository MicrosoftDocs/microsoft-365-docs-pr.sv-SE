---
title: Konfigurera händelsehubben
description: Lär dig hur du konfigurerar händelsehubben
keywords: händelsenav, konfigurera, insikter
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985666"
---
# <a name="configure-your-event-hub"></a>Konfigurera händelsehubben

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Lär dig hur du konfigurerar händelsehubben så att det kan mata in händelser från Microsoft 365 Defender.


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a>Konfigurera den nödvändiga resursleverantören i prenumerationen på Händelsehubben


1. Logga in på [Azure-portalen](https://portal.azure.com).
1. Välj **Prenumerationer { Välj den prenumeration som \> ***händelsehubben ska distribueras till***} \> Resursleverantörer**.
1. Kontrollera att **Microsoft.Insights** providern är registrerad. Registrera det annars.

![Bild av resursleverantörer i Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a>Konfigurera Azure Active Directory för appar


>! [OBS] Du måste ha administratörsroll eller Azure Active Directory (AAD) måste vara inställd på att tillåta icke-administratörer att registrera appar. Du måste också ha rollen Ägare eller Administratör för användaråtkomst för att tilldela tjänstens huvudroll.  
>Mer information finns i Skapa [en Azure AD-app & tjänstens huvudnamn i portalen – Microsofts identitetsplattform \| Microsoft Docs.](/azure/active-directory/develop/howto-create-service-principal-portal)

1. Skapa en ny registrering (som på ett sätt skapar ett tjänsthuvudnamn) **Azure Active Directory \> appregistreringar \> Ny registrering.**

1. Fyll i formuläret med bara namnet (ingen Omdirigerings-URI krävs).

    ![Bild på att registrera en ansökan](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Bild av översiktsinformation](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. Skapa en hemlig genom att klicka på **Certifikat & hemligheter Ny \> klienthemlighet:**

    ![Bild av certifikat och hemligheter](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
>**Du kommer inte att kunna komma åt klienthemligheten igen, så se till att spara den**.

## <a name="setup-event-hub-namespace"></a>Namnområde för konfigurationshändelsehubben


1. Skapa ett namnområde i händelsehubben:

    Gå **till Händelsehubben \> Lägg** till och välj prissättningsnivå, dataflödesenheter och automatisk härdning (kräver standardpris och under funktioner) som är lämpliga för den belastning du förväntar dig.  
    Mer information finns i [Priser – evenemangshubben \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)

    >[!NOTE]
    > Du kan använda ett befintligt händelsenav, men dataflödet och skalningen är inställda på namnområdesnivå, så vi rekommenderar att placera ett händelsenav i dess namnområde.

   ![Bild av namnutrymmet i händelsehubben](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. Du behöver också resurs-ID för namnområdet i händelsehubben. Gå till namnområdessidan i Azure Event \> Hubs. Kopiera texten under Resurs-ID och registrera den för användning i avsnittet M365-konfiguration nedan. 

    ![Bild av egenskaper](../../media/759498162a4e93cbf17c4130d704d164.png)

1. När namnområdet för händelsehubben har skapats måste du lägga till Tjänstens huvudnamn för appregistrering som läsare, Azure Event Hubs Data Receiver och användaren som ska logga in på Microsoft 365 Defender som deltagare (detta kan också göras på resursgrupp- eller prenumerationsnivå).

    Detta görs i **IAM (Namespace Access Control) i Event \> Hubs Namespace Access Control (IAM) \> Add** and verify under **Role assignments:**

    ![Bild på åtkomstkontroll](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a>Konfigurera händelsehubben


**Alternativ 1:**

Du kan skapa ett händelsenav  i namnområdet och alla händelsetyper (tabeller) du väljer att exportera skrivs till det **här händelsehubben.**

**Alternativ 2:**

I stället för att exportera alla händelsetyper (tabeller) till ett händelsenav kan du exportera varje tabell till ett annat händelsenav i namnområdet i händelsehubben (ett händelsenav per händelsetyp).  

Med det här alternativet Microsoft 365 Defender händelsehubben åt dig.  
>[!NOTE]
> Om du använder ett namnområde  för händelsehubben som inte ingår i ett händelsenavskluster kan du bara välja upp till 10 händelsetyper (tabeller) att exportera i varje export-Inställningar som du definierar, på grund av en Azure-begränsning på 10 händelsehubben per namnområde i händelsehubben.

Till exempel:

![Bild av exempel på händelsehubben](../../media/005c1f6c10c34420d387f594987f9ffe.png)

Om du väljer det här alternativet kan du gå till avsnittet Konfigurera [e-Microsoft 365 Defender ska skicka e-posttabeller.](#configure-microsoft-365-defender-to-send-email-tables)

Skapa ett händelsehubben i namnområdet genom att välja **Händelsehubben \> + Händelsehubben.**

Partition Count tillåter ytterligare dataflöde via parallellitet, så vi rekommenderar att öka detta tal baserat på den belastning du förväntar dig.  
Standardvärdena För lagring av meddelanden och Spara med värdena 1 och Av rekommenderas.

![Bild av Skapa händelsehubben](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

För det här händelsehubben (inte namnområde) måste du konfigurera en princip för delad åtkomst med Skicka, lyssna på anspråk. Klicka på principer för delad åtkomst i händelsehubben **\> \> +** Lägg till och ge den sedan ett principnamn (används inte någon annanstans) och markera **Skicka** och **lyssna**.

![Bild av principer för delad åtkomst](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>Konfigurera e Microsoft 365 Defender att skicka e-posttabeller


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub


1. Logga in Microsoft 365 Defender logga <https://security.microsoft.com> in på med ett konto som uppfyller alla följande rollkrav:

    - Deltagarroll på *namnområdets resursnivå* i händelsehubben eller högre för händelsehubben som du ska exportera till. Utan detta får du ett exportfel när du försöker spara inställningarna.

    - Global administratör eller säkerhetsadministratörsroll i klientorganisationens knutna till Microsoft 365 Defender och Azure.

    ![Bild på säkerhetsportalen](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. Klicka på **Raw Data Export \> +Add.**

    Nu kommer du att använda de data som du har spelat in ovan.

    **Namn:** Det här är lokalt och ska vara det som fungerar i din miljö.

    **Vidarebefordra händelser till händelsehubben**: Markera den här kryssrutan.

    **Händelse-Hubbens resurs-ID:** Det här är namnområdets namnområdes-ID för händelsehubben som du registrerade ovan när du konfigurerade händelsehubben.

    **Event-Hub-namn:** Om du har skapat ett händelsenav i namnområdet för händelsehubben klistrar du in namnet på händelsehubben som du spelade in ovan.

    Om du väljer att låta Microsoft 365 Defender skapa händelsehubben per händelsetyper (tabeller) lämnar du det här fältet tomt.

    **Händelsetyper:** Välj de tabeller för avancerad sökning som du vill vidarebefordra till Händelsehubben och sedan vidare till den anpassade appen. Aviseringstabellerna är Microsoft 365 Defender, Enheter-tabeller är från Microsoft Defender för Slutpunkt (Identifiering och åtgärd på slutpunkt) och E-posttabeller är från Microsoft Defender för Office 365. E-posthändelser registrerar alla e-posttransaktioner. URL-adressen (SafeLinks), Attachment (Valv Attachments) och POST Delivery Events (ZAP) registreras också och kan kopplas till e-posthändelser i fältet NetworkMessageId.

    ![Bild på inställningar för direktuppspelnings-API](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. Se till att klicka på **Skicka**.

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>Kontrollera att händelserna exporteras till händelsehubben


Du kan kontrollera att händelser skickas till Händelsehubben genom att köra en grundläggande avancerad fråga för sökning. Välj **Söka avancerad fråga \> \> för** sökning och ange följande fråga:

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

Det visar hur många e-postmeddelanden som togs emot den senaste timmen sammanfogade i alla andra tabeller. Du ser även om du ser händelser som kan exporteras till händelsehubben. Om antalet visar 0 ser du inga data som kommer till händelsehubben.

![Bild på avancerad sökning](../../media/c305e57dc6f72fa9eb035943f244738e.png)

När du har kontrollerat att det finns data att exportera kan du visa Händelsehubben för att verifiera att meddelandena är inkommande. Det kan ta upp till en timme. 
 
1. I Azure går du till **Händelsehubben \> Klicka på \> namnområdeshändelsehubben \> Klicka på händelsehubben.**  
1. Rulla **nedåt** under Översikt och i diagrammet Meddelanden bör du se Inkommande meddelanden. Om du inte ser några resultat visas inga meddelanden för att mata in den anpassade appen.

    ![Bild på fliken Översikt med meddelanden](../../media/e88060e315d76e74269a3fc866df047f.png)
