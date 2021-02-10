---
title: 在 Microsoft 團隊中建立自訂團隊範本
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中建立自訂團隊範本。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e017ac0795d2fdd65d89c0532469e8e269ee0e58
ms.sourcegitcommit: e9f8e1a085cbcd2592d3386fdbcfca8a6e032b10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2021
ms.locfileid: "50173089"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>在 Microsoft 團隊中建立自訂團隊範本

**EDU 客戶尚不支援自訂範本。**

自訂團隊範本是預先定義的小組結構，其中包含一組通道、索引標籤和應用程式。 您可以開發可協助您快速建立正確共同作業空間的範本。 您的自訂團隊範本會使用您的偏好設定。  

若要開始使用：

1. 登入 [小組] 管理中心。

2. 在左側導覽中，展開 [**團隊**  >  **小組範本**]。

3. 按一下 [新增 **]**。

![[團隊範本] 對話方塊的影像，其中醒目提示 [新增]。](media/team-templates-new.png)

4. 在 [ **小組範本** ] 區段中，選取 [ **建立全新的範本**]。

5. 在 [ **範本設定** ] 區段中，填寫下欄欄位，然後按 **[下一步]**：
    - 範本名稱
    - 範本簡要與詳細描述
    - 地區可視性  

![[團隊範本設定命名] 對話方塊的影像。](media/template-add-a-name.png)

6. 在 [ **頻道]、[索引標籤] 和 [應用程式]** 區段中，新增您團隊所需的任何通道和 app。

    1. 在 [ **頻道** ] 區段中，按一下 [ **新增**]。
    2. 在 [ **新增** ] 對話方塊中，命名頻道。
    3. 新增描述。
    4. 決定是否要依預設顯示頻道。
    5. 搜尋您要新增至頻道的 app 名稱。
    6. 完成 **後，按一下 [** 套用]。

![[小組範本] 通道、[索引標籤] 和 [應用程式] 畫面的影像。](media/template-channels-tabs-apps.png)

8. 完成後，按一下 [ **提交** ]。

您的新範本會顯示在 [ **團隊範本** ] 清單中。 範本可用於在團隊中建立團隊。

> [!Note]
> 團隊使用者可能需要長達24小時的時間，才能看到圖庫中的自訂範本。

## <a name="known-issues"></a>已知問題 

**問題**：如果您已從自訂範本建立一個含有其他自訂索引標籤的小組，您可能會看到空白索引標籤代替您的自訂索引標籤 app。 您的預設索引標籤 **(（例如****文章**、檔案和 **Wiki**) 會如預期所示。

**解決方案**：若要修正此問題，請移除 [自訂] 索引標籤，然後使用相同的應用程式新增一個新索引標籤。 我們目前正在針對所有未來的自訂範本（02/08/2021）進行修正。

## <a name="related-topics"></a>相關主題

- [在系統管理中心開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)
- [從現有團隊建立範本](create-template-from-existing-team.md)
- [從現有的小組範本建立小組範本](create-template-from-existing-template.md)
