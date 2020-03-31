---
title: Distribuera team för tre skyddsnivåer för filer
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Skapa och konfigurera team med Microsoft Teams för olika nivåer av informationsskydd för filer.
ms.openlocfilehash: 63a4b6763165f38e1de5331324e5a7b3573ea0f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806486"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a>Distribuera team för tre skyddsnivåer för filer

Använd anvisningarna i den här artikeln för att utforma och distribuera baslinjeteam samt känsliga eller strikt konfidentiella team. Mer information om de här tre nivåerna av skydd finns i [Skydda filer i Microsoft Teams](secure-files-in-teams.md).

## <a name="baseline-teams"></a>Baslinjeteam

Baslinjeskydd omfattar både offentliga och privata team. Offentliga team kan upptäckas och användas av alla i organisationen. Privata webbplatser kan bara upptäckas och användas av medlemmar i den Office 365-grupp som är kopplad till teamet. Medlemmar i båda dessa typer av team kan dela webbplatsen med andra.

### <a name="public"></a>Offentlig

Följ anvisningarna i [den här artikeln](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) om du vill skapa ett baslinjeteam med offentlig åtkomst och behörigheter.

Här är konfigurationsresultatet.

![Skydd på baslinjenivå för ett offentligt team.](../../media/baseline-public-team.png)

### <a name="private"></a>Privat

Följ anvisningarna i [den här artikeln](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) om du vill skapa ett baslinjeteam med privat åtkomst och behörigheter.

Här är konfigurationsresultatet.

![Skydd på baslinjenivå för ett privat team.](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a>Känsliga team

För ett känsligt team börjar du med att [skapa ett privat team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).

Därefter konfigurerar du den underliggande SharePoint-webbplatsen så att teammedlemmar inte kan dela.

1. I verktygsfältet för teamet klickar du på **Filer**.

2. Klicka på ellipsen och sedan på **Öppna i SharePoint**.

3. Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.

4. I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.

5. Under **Delningsbehörigheter** väljer du **Endast webbplatsens ägare kan dela filer, mappar och webbplatsen**. Klicka sedan på **Spara**.

Här är konfigurationsresultatet.

![Känsligt skydd för ett team.](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a>Strikt konfidentiella team

För ett strikt konfidentiellt team börjar du med att [skapa ett privat team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).

Därefter konfigurerar du den underliggande SharePoint-webbplatsen så att teammedlemmar inte kan dela och för att förhindra att personer som inte är medlemmar i teamet kan begära åtkomst.

1. I verktygsfältet för teamet klickar du på **Filer**.

2. Klicka på ellipsen och sedan på **Öppna i SharePoint**.

3. Klicka på inställningsikonen i verktygsfältet på den underliggande SharePoint-webbplatsen och klicka sedan på **Webbplatsbehörigheter**.

4. I fönstret **Webbplatsbehörigheter** under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.

5. Under **Delningsbehörigheter** väljer du **Endast webbplatsens ägare kan dela filer, mappar och webbplatsen**.

6. Inaktivera **Tillåt åtkomstbegäranden** och klicka sedan på **Spara**.

Här är konfigurationsresultatet.

![Strikt konfidentiellt skydd för ett team.](../../media/highly-confidential-team.png)

## <a name="next-step"></a>Nästa steg

[Skydda filer i team med kvarhållningsetiketter och DLP](deploy-teams-retention-DLP.md)

## <a name="see-also"></a>Se även

[Skydda filer i Microsoft Teams](secure-files-in-teams.md)

[Integrering av moln- och hybridlösningar](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
