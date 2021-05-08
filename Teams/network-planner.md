---
title: 使用網路規劃工具Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: 系統管理員可以瞭解如何使用網路規劃器來判斷網路Microsoft Teams。
localization_priority: Normal
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
ms.openlocfilehash: 1f05be30158cf934459f26965d7cef2dafbc708f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240476"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>使用網路規劃工具Microsoft Teams

網路規劃工具是可在系統管理中心Teams工具。 您可以到規劃網路規劃工具  >  **找到它**。 在幾個步驟中，網路規劃工具可協助您判斷及組織連接Microsoft Teams使用者的網路需求。 提供網路詳細資料和 Teams 使用狀況時，網路規劃中心會計算在組織的實體位置間部署 Teams 與雲端語音的網路需求。

![網路規劃工具的螢幕擷取畫面](media/network-planner.png)

網路規劃工具可讓您：

- 使用網站和 Microsoft 建議角色建立貴組織的 (辦公室工作人員、遠端工作人員，Teams會議室) 。

    > [!NOTE]
    > 建議的人物角色是根據最佳使用Teams和一般使用模式的資料所開發。 不過，除了三個建議角色之外，您最多可以建立三個自訂角色。

- 產生報告並計算使用量Teams頻寬需求。

若要使用網路規劃工具，您必須是全域系統管理員、Teams管理員，或Teams管理員。

## <a name="create-a-custom-persona"></a>建立自訂角色

請遵循下列步驟建立自訂角色：

1. 請前往系統管理中心Microsoft Teams規劃工具。

2. 在 [**角色」 選項卡** 上，按一下 **[ + 自訂角色。** 

3. 在新增 **自訂角色窗格中** ，新增新角色的名稱和描述。

4. 選取此角色在組織中使用的許可權。

5. 按一下 [儲存]。

## <a name="build-your-plan"></a>建立您的計畫

請遵循下列步驟開始建立您的網路計畫：

1. 請前往系統管理中心Microsoft Teams規劃工具。

2. 在 [ **網路計畫」** 選項卡上，按一下 **[新增網路方案**> 。

3. 輸入您的網路方案名稱和描述。 網路方案會顯示在可用方案清單中。

4. 按一下計畫名稱以選取新計畫。

5. 新增網站以建立貴組織的網路設定表示。

    視貴組織的網路，您可能會想要使用網站來代表建築物、辦公室位置或其他專案。 網站可能由 WAN 連結，以允許共用網際網路和/或 PSTN 連接。 為了獲得最佳結果，在建立遠端連線到網際網路或 PSTN 的網站之前，先建立具有本地連結的網站。

    若要建立網站：

    1. 為您的網站新增名稱和描述。

    2. 在 **網路設定** 下，將該網站的網路使用者數目 () 。

    3. 新增網路詳細資料：啟用 WAN、WAN 容量、網際網路出口 (本地或遠端 **) ，** 以及 PSTN 出口 (無、本地或遠端) 。

      > [!NOTE]
      > 您必須新增 WAN 和網際網路容量號碼，以在產生報表時查看特定的頻寬建議。

    4. 按一下 [儲存]。

## <a name="create-a-report"></a>建立報表

新增所有網站之後，您可以建立報表，如下所示。

1. 在 [ **報表>** 選項卡上，按一下 **[開始報表>**。

2. 針對您建立的每個網站，將使用者人數分散到可用的角色。 如果您使用 Microsoft 建議的人物角色，系統會自動 (80% 的 office 員工和 20% 的遠端) 。

3. 完成發佈後，按一下 [ **產生報表**> 。

    產生的報表會以數種不同的視圖顯示頻寬需求，以便清楚瞭解輸出：
    - 包含個別計算的表格會顯示每個允許活動的頻寬需求。
    - 另一個視圖會顯示整體頻寬需求與建議。

4. 按一下 [儲存]。 您的報表會列于報表清單上，以便日後檢視。

## <a name="example-scenario"></a>範例案例

若要瞭解如何使用網路規劃工具設定網路計畫，並使用這些步驟產生報表的範例，請下載網路規劃工具How-To PowerPoint組 (英文[](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true)) 。
