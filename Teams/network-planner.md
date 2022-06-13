---
title: 使用網路規劃工具進行Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 系統管理員可以瞭解如何使用網路規劃工具來判斷Microsoft Teams的網路需求。
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fba570bdd7a83c26d68d10e65f631a0d028d7408
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045552"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>使用網路規劃工具進行Microsoft Teams

網路規劃工具是可在系統管理中心Teams的新工具。 您可以移至 **規劃**  >  **網路規劃工具** 來找到它。 只要幾個步驟，[網路規劃工具] 就能協助您判斷並組織網路需求，以連線貴組織Microsoft Teams使用者。 提供網路詳細資料和 Teams 使用狀況時，網路規劃中心會計算在組織的實體位置間部署 Teams 與雲端語音的網路需求。

![網路規劃工具的螢幕擷取畫面。](media/network-planner.png)

網路規劃工具可讓您：

- 使用網站和 Microsoft 建議的人員角色， (辦公室工作人員、遠端工作者，以及Teams會議室系統) 來建立貴組織的表示。

    > [!NOTE]
    > 建議的角色是根據Teams最佳使用案例和一般使用模式中的資料所開發。 不過，除了三個建議的角色之外，您最多還可以建立三個自訂角色。

- 產生報告並計算Teams使用量的頻寬需求。

若要使用網路規劃工具，您必須是全域系統管理員、Teams系統管理員或Teams通訊系統管理員。

## <a name="create-a-custom-persona"></a>建立自訂角色

請依照下列步驟建立自訂角色：

1. 移至 Microsoft Teams 系統管理中心的網路規劃工具。

2. 在 [ **角色] 索引卷** 標上，按一下 **[+ 自訂角色]**。 

3. 在 [ **新增自訂角色]** 窗格中，新增新角色的名稱和描述。

4. 選取此角色將在組織內使用的許可權。

5. 按一下 [儲存]。

## <a name="build-your-plan"></a>建立您的計畫

請依照下列步驟開始建立您的網路計畫：

1. 移至 Microsoft Teams 系統管理中心的網路規劃工具。

2. 在 [ **網路規劃] 索引卷** 標上，按一下 [ **新增網路計畫]**。

3. 輸入網路計畫的名稱和描述。 網路計畫會顯示在可用方案清單中。

4. 按一下計畫名稱以選取新計畫。

5. 新增網站以建立組織網路設定的呈現。

    視您組織的網路而定，您可能會想要使用網站來代表建築物、辦公室位置或其他專案。 網站可能透過 WAN 連線，以允許共用網際網路和/或 PSTN 連線。 為了獲得最佳結果，請先建立具有本機連線的網站，然後再建立遠端連線到網際網路或 PSTN 的網站。

    若要建立網站：

    1. 為您的網站新增名稱和描述。

    2. 在 [ **網路設定] 底** 下，將該網站的網路使用者數 (必要) 。

    3. 新增網路詳細資料：啟用 WAN、WAN 容量、網際網路出口 (**本** 機或 **遠端**) ，以及 PSTN 出口 (無本機或遠端) 。

      > [!NOTE]
      > 您必須新增 WAN 和網際網路容量號碼，才能在產生報告時查看特定頻寬建議。

    4. 按一下 [儲存]。

## <a name="create-a-report"></a>建立報表

新增所有網站之後，您可以建立下列報表。

1. 在 [ **報表] 索** 引標籤上，按一下 [ **開始報表]**。

2. 針對您所建立的每個網站，將使用者數目分散到可用角色。 如果您使用 Microsoft 建議的角色，號碼會自動分配 (80% 的上班族和 20% 的遠端工作者) 。

3. 完成發佈後，按一下 [ **產生報表]**。

    產生的報表會在數種不同的檢視中顯示頻寬需求，讓您可以清楚瞭解輸出：
    - 具有個別計算的資料表會顯示每個允許活動的頻寬需求。
    - 另一個檢視會顯示整體頻寬需求，並提供建議。

4. 按一下 [儲存]。 您的報表會顯示在報表清單中，供日後檢視。

## <a name="example-scenario"></a>範例案例

如需如何使用網路規劃工具來設定網路計畫，以及使用這些步驟產生報告的範例，請下載[網路規劃工具How-To PowerPoint投影片](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true)組 (僅提供英文版) 。
