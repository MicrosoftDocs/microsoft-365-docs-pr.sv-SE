---
title: Granskning och rapportering i Microsofts moln tjänster
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- M365-analytics
- SPO_Content
f1.keywords:
- NOCSH
description: En översikt över funktionerna för granskning och rapportering inom Office 365, Microsoft 365 och service Assurance.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 11dbf29faf028ec9ed0274c806fc8c8979a6f1fd
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332586"
---
# <a name="auditing-and-reporting-in-microsoft-cloud-services"></a>Granskning och rapportering i Microsofts moln tjänster

Microsofts moln tjänster innehåller flera gransknings-och rapporterings funktioner som du kan använda för att spåra användar-och administratörs aktiviteter inom sina klient organisationer, som innehåller ändringar gjorda i konfigurations inställningar för Exchange Online och SharePoint Online och ändringar som görs av användare för dokument och andra objekt. Du kan använda gransknings information och rapporter som är tillgängliga i Microsofts moln tjänster för att hantera användar upplevelsen på ett effektivare sätt, minska riskerna och uppfylla efterlevnadar.

## <a name="security--compliance-centers"></a>Säkerhets & efterlevnad

[Microsoft 365 security & Compliance Center](https://protection.office.com), [Microsoft 365 säkerhets Center](https://security.microsoft.com)och [Microsoft 365 Compliance Center](https://compliance.microsoft.com) är en-stoppbit för att skydda data i organisationen och de innehåller många funktioner för granskning och rapportering. De här centrerna hjälper dig med data skydd eller överensstämmelse behov samt funktionerna för användar-och administratörs aktivitet. Du kan komma åt dessa Center med ditt administratörs konto för prenumerationer.

Dessa centra innehåller navigerings fönster för till gång till flera funktioner:

- **Aviseringar:** Gör det möjligt att hantera aviseringar, Visa säkerhetsrelaterade aviseringar och hantera avancerade aviseringar med hjälp av [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).
- **Behörigheter:** Med detta alternativ kan du [Ange behörigheter](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center) som efterlevnad administratör, EDiscovery-hanterare och andra personer i organisationen så att de ska kunna utföra uppgifter i dessa Center. Du kan tilldela behörigheter för de flesta funktioner i varje Center, men andra behörigheter måste konfigureras med administrations centret för Exchange och administrations centret för SharePoint.
- **Threat Management:** Gör att du kan skapa och använda enhets hanterings principer med hjälp av [Microsoft 365-hantering av mobila enheter](https://support.microsoft.com/office/overview-of-mobile-device-management-mdm-for-microsoft-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a), för att konfigurera [data förlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) (DLP)-principer för din organisation, för konfigurering av e-postfiltrering, skadlig program vara (DKIM), säkra bifogade filer, säkra länkar och OAuth-appar.
- **Data styrning:** Gör att du kan [Importera e-post-eller SharePoint-data från andra system till Microsoft 365](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84), [Konfigurera Arkiv post lådor](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)och ange [lagrings principer](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) för e-post och annat innehåll i organisationen.
- **& undersökning:** Innehåller verktyg för [innehålls sökning](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a), [Gransknings logg](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c), karantän och [hantering av eDiscovery-ärenden](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) för att snabbt öka detalj nivån för aktivitet i Exchange Online-postlådor, grupper och gemensamma mappar, SharePoint Online och OneDrive för företag.
- **Rapporter:** Gör det möjligt att snabbt komma åt [rapporter](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a) för SharePoint Online, OneDrive för företag, Exchange Online och Azure AD.
- **Tjänste granskning:** Innehåller information om hur Microsoft hanterar säkerhet, sekretess och efterlevnad av globala standarder för Microsoft 365, Azure, Microsoft Dynamics CRM Online, Microsoft Intune och andra moln tjänster. Inkluderar även åtkomst till tredje parts ISO, SOC och andra gransknings rapporter, samt granskade kontroller, som innehåller information om de olika kontroller som har testats och verifierats av tredje parts granskare i Microsoft 365.

## <a name="service-assurance"></a>Tjänst garanti

Många organisationer i reglerade branscher har omfattande krav på efterlevnad. För att kunna genomföra sina egna riskbedömningar behöver kunderna ofta mer ingående information om hur Microsoft 365 hanterar säkerheten och integriteten hos sina data. Microsoft värnar om säkerheten och integriteten hos kunddata i dess moln tjänster och för att tjäna kund förtroende genom att tillhandahålla en transparent vy av dess verksamheter och enkel åtkomst till oberoende rapporter och utvärderingar.

Tjänste garantin ger insyn i åtgärder och information om hur Microsoft hanterar säkerhet, sekretess och efterlevnad av kunddata i Microsoft 365. Det inkluderar gransknings rapporter från tredje part tillsammans med ett bibliotek med fakta blad, frågor och andra material i Microsoft 365-ämnen som data kryptering, data återhämtning, hantering av säkerhets tillbud och mer. Kunderna kan använda den här informationen för att genomföra sina egna regler för riskbedömning. Efterföljandekrav kan tilldela rollen "tjänst garanti användare" för att ge användarna åtkomst till tjänst kontroll. Klient organisations administratören kan även tillhandahålla externa användare, till exempel oberoende granskare, med åtkomst till information på instrument panelen för tjänste säkring via [Microsofts moln tjänst förtroende Portal](https://aka.ms/STP) (STP).

## <a name="onedrive-for-business-admin-center"></a>Administrations Center för OneDrive för företag

Med administrations centret för Microsoft OneDrive kan du snabbt och enkelt hantera organisationens OneDrive för företag-inställningar på ett och samma ställe. Om du vill använda administrations centret för OneDrive måste du ha till gång till onedrive.com. Du måste också vara global administratör för organisationen eller en anpassad administratör med administratörs rollen för SharePoint. Gå till administrations centret för OneDrive för företag på [https://admin.onedrive.com](https://admin.onedrive.com/) .

Viktiga funktioner innehåller ett kompatibilitetstillstånd som ger administratörer med länkar till lämpligt Management Center för viktiga scenarier som att söka i gransknings loggen, arbeta med DLP, Kvarhållning, eDiscovery och aviseringar.

## <a name="related-links"></a>Relaterade länkar

- [eDiscovery-och Sök funktioner](microsoft-365-ediscovery-and-search-features.md)
- [Rapporterings funktioner i Microsoft 365](microsoft-365-reporting-features.md)
- [API för hanterings aktivitet i Microsoft 365](microsoft-365-management-activity-api.md)
- [Microsoft 365 Mailbox-migreringar](microsoft-365-mailbox-migrations.md)
- [Intern loggning för Microsoft 365-teknik](microsoft-365-internal-logging.md)
