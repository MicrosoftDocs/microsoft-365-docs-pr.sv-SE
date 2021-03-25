---
title: Skapa en aviseringsregel för onboarding eller offboarding
description: Få ett meddelande när ett lokalt onboarding- eller offboarding-skript används.
keywords: onboarding, offboarding, lokal, skript, meddelande, regel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5dfdfc6d14add33154ed4c2370bca458e752125d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187339"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a>Skapa en meddelanderegel när ett lokalt onboarding- eller offboarding-skript används

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Skapa en meddelanderegel så att du får ett meddelande när du använder ett lokalt onboarding- eller offboarding-skript. 

## <a name="before-you-begin"></a>Innan du börjar
Du måste ha åtkomst till:
 - Microsoft Flow (som minst 1 flödesplan). Mer information finns på sidan [Priser för flöde.](https://flow.microsoft.com/pricing/)
 - Azure-tabell eller SharePoint-lista eller -bibliotek/SQL DB

## <a name="create-the-notification-flow"></a>Skapa meddelandeflödet

1. I [flow.microsoft.com](https://flow.microsoft.com/).

2. Gå till **Mina flöden > Ny > – från tom**. 

    ![Bild av flöde](images/new-flow.png)


3. Skapa ett schemalagt flöde.
   1. Ange ett flödesnamn.
   2. Ange starttid och tid.
   3. Ange frekvens. Till exempel var femte minut.

    ![Bild av meddelandeflödet](images/build-flow.png)

4. Välj knappen + för att lägga till en ny åtgärd. Den nya åtgärden kommer att vara en HTTP-begäran till Defender för slutpunktens säkerhetscenter-enheters API. Du kan också ersätta den med den inmatade "WDATP Connector" (åtgärd: "Datorer - hämta lista över datorer"). 

    ![Bild av återkommande och lägg till åtgärd](images/recurrence-add.png)


5. Ange följande HTTP-fält:

   - Metod: "GET" som ett värde för att få listan över enheter.
   - URI: Ange `https://api.securitycenter.microsoft.com/api/machines` .
   - Autentisering: Välj "Active Directory OAuth".
   - Klientorganisation: Logga in på https://portal.azure.com och navigera till Azure Active Directory > för appregistreringar och få värdet klientorganisations-ID. 
   - Målgrupp: `https://securitycenter.onmicrosoft.com/windowsatpservice\`
   - Klient-ID: Logga in på https://portal.azure.com och navigera till Azure Active Directory > **och** få värdet klient-ID.
   - Typ av autentiseringsuppgifter: Välj "Hemligt".
   - Hemligt: Logga in på och https://portal.azure.com navigera till Azure Active Directory > för appregistreringar och få värdet klientorganisations-ID. 

    ![Bild av HTTP-villkor](images/http-conditions.png)


6. Lägg till ett nytt steg genom att **välja Lägg till** ny åtgärd och sedan söka efter **Dataåtgärder** och **välja Parse JSON.**

    ![Bild på dataåtgärder](images/data-operations.png)

7. Lägg till brödtext **i fältet** Innehåll.

    ![Bild på parse JSON](images/parse-json.png)

8. Välj länken **Använd exempel på nyttolast för att generera schema.**

    ![Bild på parse json med nyttolast](images/parse-json-schema.png)

9. Kopiera och klistra in följande JSON-kodstycke:

    ```
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10.  Extrahera värdena från JSON-samtalet och kontrollera om den registrerade enheten/-enheten redan är registrerad på SharePoint-listan som exempel:
- Om ja utlöses inget meddelande
- Om nej registrerar du de nya onboarded-enheten i SharePoint-listan och ett meddelande skickas till Defender för Slutpunktsadministratören

    ![Bild av varje ansökt](images/flow-apply.png)

    ![Bild av ansök för varje objekt med hämta objekt](images/apply-to-each.png)

11. Under **Villkor** lägger du till följande uttryck: "length(body('Get_items')?[' värde'])" och ange att villkoret ska vara lika med 0.

    ![Bild av hur de olika villkoren tillämpas](images/apply-to-each-value.png)  
    ![Bild av villkor1 ](images/conditions-2.png) 
     ![ Bild av villkor2](images/condition3.png)  
    ![Bild av skicka e-post](images/send-email.png)

## <a name="alert-notification"></a>Aviseringsmeddelande
Följande bild är ett exempel på en e-postavisering.

![Bild av e-postavisering](images/alert-notification.png)


## <a name="tips"></a>Tips

- Du kan endast filtrera här med hjälp av lastSeen:
    - Var 60:e min:
      - Ta alla enheter som senast har setts de senaste 7 dagarna. 

- För varje enhet: 
    - Om egenskapen senast sedd är i ett timintervall på [-7 dagar, -7dag + 60 minuter ] -> avisering om offboarding-möjlighet.
    - Om den första har setts är den senaste > aviseringen för registrering.

I den här lösningen får du inte dubblettaviseringar: Det finns klientorganisationen som har flera enheter. Att få alla dessa enheter kan vara mycket dyr och kan kräva sidinring.

Du kan dela upp den i två frågor: 
1.  För offboarding använder du bara det här intervallet med hjälp av OData-$filter och meddelar endast om villkoren är uppfyllda.
2.  Ta alla enheter som senast sågs under den senaste timmen och kontrollera den första sett egenskapen för dem (om den första sett egenskapen finns på den senaste timmen, måste den senast sedd finnas där också). 

