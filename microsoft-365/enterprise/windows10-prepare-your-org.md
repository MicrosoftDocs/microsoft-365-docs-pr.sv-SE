---
title: Förbereda din organisation för Windows 10 Enterprise
description: Ger vägledning på hög nivå om de steg du behöver för att distribuera Windows 10 Enterprise på datorer som en del av Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-dokumentation, Windows 10 Enterprise, distribution
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: josephd
ms.openlocfilehash: 43793a1780542b1825c693030dd9d4dbff4ee3d7
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002349"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>Steg 1: Förbereda din organisation för Windows 10 Enterprise

*Den här artikeln gäller både E3- och E5-versionerna av Microsoft 365 Enterprise*

![Fas 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Innan du uppgraderar dina enheter till Windows 10 Enterprise bör du tänka på följande:

- **Dina domäner måste läggas till och verifieras** <br>
  Med en Microsoft 365-prenumeration får du ett standarddomännamn som slutar onmicrosoft.com (till exempel contoso.onmicrosoft.com). De flesta organisationer föredrar att använda en eller flera av de domäner de äger så att deras e-postadresser slutar i sitt eget domännamn (som username@contoso.com). Om du vill använda din egen domän måste du lägga till den i Microsoft 365 och kontrollera att du äger den. Vi rekommenderar att du lägger till och verifierar dina domäner nu så att de är redo att användas när du konfigurerar Microsoft 365-tjänster, till exempel e-post och Skype för företag.
- **Du behöver inte lägga till användare just nu** <br>
  Om du vill använda Microsoft 365-tjänster eller installera Microsoft 365-produkter behöver användarna konton i Microsoft 365 och de behöver produktlicenser. Hur du lägger till användare i Microsoft 365 beror på antalet användare och om du för närvarande har Active Directory lokalt. Om du inte har Active Directory (eller om du har Active Directory men inte vill synkronisera den med Microsoft 365) kan du lägga till användare direkt i Microsoft 365 och tilldela licenser, antingen enskilt eller i grupp. <br>
  Om du har Active Directory lokalt kan du [synkronisera den med Microsoft 365](identity-add-user-accounts.md#identity-sync) för att skapa användarkonton i Azure AD, molnkatalogen som används av Microsoft 365. Med den här metoden kan du skapa konton för användare och säkerhetsgrupper som du använder för att hantera behörigheter till resurser (till exempel SharePoint Online-webbplatssamlingar eller dokument). Om du synkroniserar Active Directory med Microsoft 365 tilldelas inte licenser till användarna.
- **Du behöver inte licensiera användare just nu** <br>
  Innan användare kan använda Microsoft 365-tjänster eller installera programvara från Microsoft 365-portalen behöver de produktlicenser. Som global administratör eller användarhanteringsadministratör kan du direkt tilldela produktlicenser i Microsoft 365 antingen enskilt eller i grupp. Du kan också använda [gruppbaserad licensiering](identity-use-group-management.md#identity-group-license) för att automatiskt tilldela licenser när användare läggs till i en viss grupp. 
- **Du installerar Microsoft 365 Apps för företag separat** <br>
  Om du skaffar en Microsoft 365-licens installeras inte Microsoft 365 Apps för företag automatiskt på klientdatorerna. Mer information finns i [fas 4: Microsoft 365 Apps för företag.](office365proplus-infrastructure.md) 

## <a name="set-windows-diagnostics-data-level"></a>Ange datanivå för Windows-diagnostik

Microsoft använder diagnostikdata för att skydda Windows-enheter genom att identifiera trender för skadlig programvara och andra hot och för att hjälpa oss att förbättra kvaliteten på Windows- och Microsoft-tjänster. Du måste se till att diagnostiktjänsten är aktiverad på en miniminivå basic på alla slutpunkter i organisationen. *Som standard är den här tjänsten aktiverad och inställd på den förbättrade nivån.* Det är dock god praxis att kontrollera och se till att de tar emot sensordata. Om du ställer in nivåer genom principer åsidosätts inställningar på enhetsnivå. 

**Diagnostikdatanivåer för operativsystemet i Windows 10**

Du kan konfigurera inställningarna för diagnostikdata för operativsystemet med hjälp av de hanteringsverktyg som du redan använder, till exempel Grupprincip, MDM eller Windows-etablering. Du kan också ändra inställningarna manuellt med Registereditorn. Om du ställer in dina diagnostikdatanivåer via en hanteringsprincip åsidosätts alla inställningar på enhetsnivå.

Använd lämpligt värde i tabellen nedan när du konfigurerar hanteringsprincipen.

| Nivå | Uppgifter som samlats in | Value |
|:--- |:--- |:--- |
| Säkerhet | Endast säkerhetsdata. | 0 |
| Grundläggande | Säkerhetsdata och grundläggande system- och kvalitetsdata. | 1 |
| Förbättrad | Säkerhetsdata, grundläggande system- och kvalitetsdata samt förbättrade insikter och avancerade tillförlitlighetsdata. | 2 |
| Full | Säkerhetsdata, grundläggande system- och kvalitetsdata, förbättrade insikter och avancerade tillförlitlighetsdata samt fullständiga diagnostikdata. | 3 |

Du kan aktivera diagnostikdata via någon av dessa metoder:

* **Microsoft Intune** - Om du planerar att använda Intune för att hantera dina enheter kan du skapa en konfigurationsprincip för att aktivera diagnostikdata genom att konfigurera <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">systemprincipen SystemAllowTelemetry.</a>
* **Registereditorn** - Du kan använda Registereditorn för att manuellt aktivera diagnostikdata på varje enhet i organisationen. Alternativt kan du skriva ett skript för att redigera registret. Om det redan finns en hanteringsprincip, till exempel Grupprincip eller MDM, åsidosätts den här registerinställningen.
* **Grupprincip** - Om du inte planerar att registrera enheter i Intune kan du använda ett grupprincipobjekt för att ange organisationens diagnostikdatanivå.
* **Kommandotolken** - Du kan ställa in Windows 10 diagnostikdata och tjänst för att automatiskt börja med kommandotolken. Den här metoden är bäst om du testar tjänsten på endast ett fåtal enheter. Om du aktiverar tjänsten för att starta automatiskt med det här kommandot konfigureras inte diagnostikdatanivån. Om du inte har konfigurerat en diagnostikdatanivå med hjälp av hanteringsverktyg fungerar tjänsten med standardnivån Utökad.

Mer information om Windows-diagnostikdata finns [i Konfigurera Windows-diagnostikdata i organisationen](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) och hur du kan aktivera dem baserat på den metod du väljer.

Som en mellanliggande kontrollpunkt kan du se vilka [avslutsvillkor](windows10-exit-criteria.md#crit-windows10-step1) som motsvarar det här steget.

## <a name="next-step"></a>Nästa steg

|||
|:-------|:-----|
|![Steg 2](../media/stepnumbers/Step2.png)| [Distribuera Windows 10 Enterprise för befintliga enheter som en uppgradering på plats](windows10-deploy-inplaceupgrade.md) |






