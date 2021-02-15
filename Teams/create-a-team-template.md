---
title: 在 Microsoft Teams 中建立自訂團隊範本
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中建立自訂團隊範本。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f22b2c53ab6f3c3c90e1720313c135c2106b1a49
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196527"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>在 Microsoft Teams 中建立自訂團隊範本

**EDU 客戶尚未支援自訂範本。**

自訂團隊範本是預先定義的團隊結構，包含一組頻道、定位字元和應用程式。 您可以開發範本，説明您快速建立正確的共同合作空間。 您的自訂小組範本會使用您偏好的設定。  

若要開始使用：

1. 登入 Teams 系統管理中心。

2. 在左側流覽中，展開 **Teams**  >  **團隊範本**。

3. 按一下 [新增 **]**。

![[小組範本> 對話方塊的影像，畫面上已加上 [新增功能。](media/team-templates-new.png)

4. 在小組 **範本區** 段，選取 **建立全新的範本**。

5. 在範本 **設定區** 段，完成下欄欄位，然後按一下 [下 **一步：**
    - 範本名稱
    - 範本簡短與長描述
    - 地區設置可見度  

![小組範本設定命名對話方塊的影像。](media/template-add-a-name.png)

6. 在 **頻道、定位字元** 和應用程式區段，新增小組需要的任何頻道和應用程式。

    1. 在頻道 **區段** ，按一下 [ **新增**。
    2. 在 [ **新增功能** 對話方塊上，為頻道命名。
    3. 新增描述。
    4. 決定是否要顯示頻道。
    5. 搜尋您想要新增到頻道的應用程式名稱。
    6. 完成 **時** 按一下 [申請。

![團隊範本頻道、選項卡和應用程式畫面的影像。](media/template-channels-tabs-apps.png)

8. 完成 **時** 按一下 [提交。

您的新範本會顯示在小組 **範本** 清單中。 範本可用來在 Teams 中建立團隊。

> [!Note]
> 團隊使用者最多可能需要 24 小時，才能在圖庫中查看自訂範本。

## <a name="known-issues"></a>已知問題 

**問題**：如果您從包含其他自訂定位字元的自訂範本建立團隊，您可能會在自訂的選項卡應用程式中看到空白的定位停駐點。 您的預設 (例如文章、檔案和 **Wiki**) 會顯示如預期。 

**解決方案**：如果您從包含其他自訂定位字元的自訂範本建立團隊，您可能會在自訂的選項卡應用程式中看到空白的定位停駐點。 您的預設 (例如文章、檔案和 Wiki) 會顯示如預期。

若要修正此問題，請移除自訂的定位點，然後使用相同的應用程式新增新的定位點。 如果您沒有許可權移除自訂的 Tab 並新增新的定位停駐點，請聯繫團隊擁有者要求他們這麼做。

我們目前正在開發自訂範本所建立之未來團隊的修正程式。

## <a name="related-topics"></a>相關主題

- [在系統管理中心開始使用小組範本](get-started-with-teams-templates-in-the-admin-console.md)
- [從現有小組建立範本](create-template-from-existing-team.md)
- [從現有的小組範本建立小組範本](create-template-from-existing-template.md)
