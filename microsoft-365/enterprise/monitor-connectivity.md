---
title: Övervaka Microsoft 365-anslutning
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: I den här artikeln får du lära dig mer om verktygen och teknikerna som du kan använda för att övervaka och underhålla Microsoft 365-anslutningar.
ms.openlocfilehash: 7e62bcaae24f9e42fd0514c34c3d7dee764bc271
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694336"
---
# <a name="monitor-microsoft-365-connectivity"></a>Övervaka Microsoft 365-anslutning

När du har distribuerat Microsoft 365 kan du upprätthålla Microsoft 365-anslutningen med några av verktygen och teknikerna nedan. Du vill förstå de offentliga rikt linjerna för [tjänster och kontinuitet](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) samt vår [bästa praxis för att använda Microsoft 365 på ett långsamt nätverk](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166). Du vill också skaffa [microsoft 365-administratörs programmet](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) och bok märke vår [support för Microsoft 365 för företag – hjälp för administratörer](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).
  
## <a name="monitoring-microsoft-365-connectivity"></a>Övervaka Microsoft 365-anslutningar

|||
|:-----|:-----|
|**Få meddelanden om nya slut punkter för Microsoft 365** <br/> |Om du [hanterar Microsoft 365-slutpunkter](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), vill du få aviseringar när vi publicerar nya slut punkter, kan du prenumerera på RSS-feeden med din RSS-läsare. Så här [abonnerar](https://go.microsoft.com/fwlink/p/?LinkId=532416) du på Outlook eller så kan du [få en RSS-feed uppdaterats via e-post](https://go.microsoft.com/fwlink/p/?LinkId=532417).  <br/> |
|**Använda System Center för att övervaka Microsoft 365** <br/> |Om du använder Microsoft System Center kan du hämta [System Center Management Pack för Office 365](https://www.microsoft.com/download/details.aspx?id=43708) för att börja övervaka Microsoft 365 idag. Mer detaljerad information finns i hanterings paketet Operations Guide eller det här blogg inlägget [Office365 övervakning med System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) <br/> |
|**Övervaka hälsa för Azure ExpressRoute** <br/> |Om du ansluter till Microsoft 365 med Azure ExpressRoute för Microsoft 365 bör du kontrol lera att du använder både Microsoft 365 tjänste instrument panel och Azure [Degressiv problemlösnings tid med Azure Resource Health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) <br/> |
|**Använda Azure AD Connect-hälsa med AD FS** <br/> |Om du använder AD FS för enkel inloggning med Microsoft 365 ska du börja [använda Azure AD Connect-tillståndet för att övervaka din AD FS-infrastruktur](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/).  <br/> |
|**Övervaka Microsoft 365 programmatiskt** <br/> |Läs vår vägledning om [Microsoft 365 Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).  <br/> |

Här är en kort länk som du kan använda för att komma tillbaka: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)
  
## <a name="related-topics"></a>Relaterade ämnen

[Konfigurera Microsoft 365 Enterprise Services och-program](configure-services-and-applications.md)
  
[Förbered din organisation för Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Nätverks planering och prestanda justering för Microsoft 365](network-planning-and-performance.md)
  
[Microsoft 365-integrering med lokala miljöer](microsoft-365-integration.md)
  
[Hantera slut punkter för Microsoft 365](managing-office-365-endpoints.md)
