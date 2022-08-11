---
title: Microsoft 應用程式認證概觀
description: 了解適用於協力廠商應用程式安全性、合規性和隱私權的 Microsoft 365 應用程式合規性計畫。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9918c1ce81464f2fbe9a0c16bc0373e54858d79b
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299082"
---
# <a name="microsoft-365-app-compliance-program-for-security-compliance-and-privacy-of-third-party-apps"></a>適用於第三方應用程式安全性、合規性和隱私權的 Microsoft 365 應用程式合規性計畫

Microsoft 合規性計畫會針對衍生自領先業界標準架構的控制措施，檢查和稽核應用程式。 此計畫示範了強大的安全性與合規性做法，以保護客戶資料。 計畫有下列階段:

* 發行者驗證。
* 發行者證明。
* Microsoft 365 認證。

## <a name="publisher-verification"></a>發行者驗證

應用程式開發人員必須先經過驗證，才能將應用程式提交給 Microsoft。 開發人員使用其 Microsoft 合作夥伴網路 (MPN) 帳戶驗證其身分識別，並將此 MPN 帳戶與其應用程式註冊建立關聯。 發行者驗證可協助系統管理員和使用者了解應用程式開發人員的真實性。 發行者驗證具有下列優點：

* 提高客戶的透明度和降低風險 - 這項功能可協助客戶瞭解其組織中使用的應用程式是由他們信任的開發人員所發佈。
* 改良的商標 - `verified` 徽章會顯示在 Azure Active Directory 同意提示、企業應用程式頁面，以及使用者和系統管理員使用的其他使用者介面上。
* 更順暢的企業採用 - 系統管理員可以設定使用者同意原則，並以發行者驗證狀態做為主要原則準則。

## <a name="publisher-attestation"></a>發行者證明

發行者證明是應用程式合規性計畫的下一層。 發行者證明的應用程式為系統管理員提供有關應用程式安全性與合規性措施的信賴。 它也可以協助縮短查看應用程式此資訊的時間。 此證明會針對 [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security) 識別的 超過 80 個風險因素，反映應用程式的安全性、資料處理和合規性做法。 發行者證明流程可以在發行者驗證完成之前啟動。

系統會要求應用程式開發人員完成自我評估，其中包含客戶和 IT 系統管理員經常詢問的問題，以評估應用程式的安全性與合規性。 Microsoft 接著發佈此資訊，以便更容易且更及時地進行評估。 若要深入了解，請參閱 [證明指南](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)。

系統管理員可以使用三種不同的方式快速檢查已發佈的證明應用程式。

* 收集有關應用程式的詳細資訊時，在 [Microsoft Teams 應用程式安全性與合規性](/microsoft-365-app-certification/teams/teams-apps) 的連結中查看特定應用程式的詳細資訊。 或者，在 [Teams 系統管理中心](https://admin.teams.microsoft.com/)選取 `Publisher attestation` 連結。

  :::image type="content" source="media/attested-app-tac3.png" alt-text="在 Teams 系統管理中心，選取 [發行者證明連結] 以檢視應用程式證明的詳細資料。":::

* 在 Teams 系統管理中心，從 **[[管理應用程式]](https://admin.teams.microsoft.com/policies/manage-apps)** 頁面查看應用程式的詳細資料時，請參閱應用程式詳細資料頁面中橫幅上的發行者證明圖示。

  :::image type="content" source="media/attested-app-tac1.png" alt-text="在 Teams 系統管理中心，所有已證明的應用程式上都會顯示發行者證明圖示。":::

* 在 Teams 系統管理中心，在[授與應用程式權限時](app-permissions-admin-center.md)，應用程式名稱前面的藍色核取記號表示它是發行者證明的應用程式或 Microsoft 365 認證的應用程式。

   :::image type="content" source="media/attested-app-tac2.png" alt-text="在 Teams 系統管理中心內，在授予權限的對話方塊中，藍色勾選記號表示發行者證明的應用程式。":::

證明或認證應用程式的 [證明詳細資料] 頁面會列出下列詳細資料。

:::image type="content" source="media/attested-app-doc-details.png" alt-text="證明應用程式的詳細資訊。":::

## <a name="microsoft-365-certification"></a>Microsoft 365 認證

應用程式認證的封存是透過:

* 合格的分析師檢閱。
* 核准以應用程式的安全性與合規性架構、處理程式和程序為完整的評估中心。

我們根據來自領先業界標準架構的一系列安全性控制檢查應用程式。

此憑證示範了在組織啟用應用程式時，用來保護客戶資料的強大安全性與合規性做法。 有關系統管理員和使用者如何從認證獲益的資訊，請參閱 [Microsoft 365 應用程式合規性計畫概觀](/microsoft-365-app-certification/docs/enterprise-app-certification-guide)。

系統管理員可透過下列方式快速檢查 Microsoft 365 認證的應用程式。

* 收集關於 Web 上應用程式的詳細資訊時，請參閱 [Microsoft 文件有關該應用程式](/microsoft-365-app-certification/teams/teams-apps)的盾牌圖示。

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="在關於應用程式的安全性與合規性的詳細說明文章中檢視 Microsoft 365 認證資訊":::

* 在 [Teams 系統管理中心](https://admin.teams.microsoft.com/policies/manage-apps)檢查應用程式時，使用認證資料行來排序應用程式的清單。 查看圖示，並選擇性地選取連結以存取以上提及的應用程式特定頁面。

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="在 Teams 系統管理中心檢視應用程式的 Microsoft 365 認證狀態。" lightbox="media/m365cert-apps-list2.png":::

* 檢視應用程式的詳細資料時，請查看應用程式橫幅中的 Microsoft 365 認證圖示。

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="在 Teams 系統管理中心管理特定應用程式時，於應用程式橫幅中檢視 Microsoft 365 認證資訊":::

* 在 Teams 系統管理中心，在[授與應用程式權限時](app-permissions-admin-center.md)，應用程式名稱前面的藍色核取記號表示它是發行者證明的應用程式或 Microsoft 365 認證的應用程式。

   :::image type="content" source="media/attested-app-tac2.png" alt-text="在 Teams 系統管理中心，系統管理員可以於授與權限的對話方塊中檢查藍色核取記號，以確保應用程式已通過 Microsoft 365 認證":::

## <a name="view-security-compliance-and-privacy-information"></a>檢視安全性、合規性和隱私權資訊

您可以在 [Microsoft 文件](/microsoft-365-app-certification/teams/teams-apps)和 [Teams 系統管理中心](https://admin.teams.microsoft.com/policies/manage-apps)找到已證明或認證應用程式的安全性、隱私權、合規性和行為相關資訊。

### <a name="microsoft-documentation"></a>Microsoft 文件

您可找到有關每個應用程式的安全性、隱私權、合規性等詳細資料，會列在從 [Microsoft Teams 應用程式安全性與合規性](/microsoft-365-app-certification/teams/teams-apps)連結的應用程式特定說明文章中。

:::image type="content" source="media/attested-app-doc-details.png" alt-text="針對經歷 Microsoft 合規性計畫的應用程式提供詳細資訊。":::

### <a name="teams-admin-center"></a>Teams 系統管理中心

評估應用程式時，您可以使用獨立的雲端存取安全性代理人 (CASB)，例如 Microsoft Cloud App Security (MCAS)，來尋找應用程式安全性和行為的資訊。 Teams 系統管理中心包含來自 MCAS 的 Microsoft 365 認證應用程式安全性和合規性資訊。 在應用程式詳細資料頁面中檢查此資訊，以確認應用程式是否符合您的安全性需求。

> [!NOTE]
> 此功能可供所有系統管理員使用，不論您的組織是否擁有支援 MCAS 授權。

若要存取應用程式的 MCAS 資訊:

1. 在 Teams 系統管理中心選取 **Teams 應用程式** > **[管理應用程式](https://admin.teams.microsoft.com/policies/manage-apps)**。

1. 選取 **[認證]** 來排序應用程式，並推播所有 Microsoft 365 認證應用程式至表格頂端。

1. 選擇 Microsoft 365 認證應用程式。

1. 選取 **[安全性與合規性]** 索引標籤。

   :::image type="content" source="media/mcas.png" alt-text="Teams 系統管理中心安全性與合規性索引標籤的螢幕擷取畫面。":::

   若要取得應用程式支援功能的詳細資訊，請選取每個類別的下拉清單。

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>檢視應用程式的隱私權原則和使用規定

在 Teams 系統管理中心，每個應用程式頁面會連結到隱私權聲明和應用程式的使用條款。

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="從 Teams 系統管理中心，系統管理員可以存取每個應用程式的隱私權原則和使用規定的連結。" lightbox="media/tac-app-tou-privacy-info2.png":::

## <a name="related-articles"></a>相關文章

* [檢視應用程式權限並授與系統管理員同意](app-permissions-admin-center.md)。
