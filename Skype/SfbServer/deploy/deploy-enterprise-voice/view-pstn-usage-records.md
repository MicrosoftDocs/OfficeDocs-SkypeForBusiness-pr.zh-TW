---
title: 在商務用 Skype 中查看 PSTN 使用方式記錄
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 摘要：瞭解如何使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面來查看 PSTN 使用方式記錄。
---

# <a name="view-pstn-usage-records-in-skype-for-business"></a>在商務用 Skype 中查看 PSTN 使用方式記錄

**總結：** 瞭解如何使用商務用 Skype Server 控制台] 或「商務用 Skype Server 管理命令介面來查看 PSTN 使用方式記錄。

公用交換電話網路 (PSTN) 使用方式記錄會指定呼叫類別 (例如內部、本機或長途) ，可由組織中的各種使用者或使用者群組進行。 如需詳細資訊，請參閱規劃文件中的 [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records)。

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台來查看 PSTN 使用方式記錄

1. 開啟商務用 Skype Server 控制台]。

2. 在左導覽列中，按一下 **[語音路由]**，然後按一下 **[PSTN 使用方式]**。

3. 在 **[PSTN 使用方式]** 頁面上，反白想要檢視的 PSTN 使用方式記錄，並按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。

    > [!NOTE]
    > 所選取 PSTN 使用方式記錄的唯讀頁面顯示相關聯的路由及相關聯的語音原則。

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>使用商務用 Skype Server 管理命令介面 Cmdlet 來查看 PSTN 使用狀況資訊

- 若要查看所有 PSTN 使用方式的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 enter：

  ```powershell
  Get-CsPstnUsage
  ```

    此命令會傳回與下列相似的資訊：

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>另請參閱

[在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用方式記錄](voice-policy-and-pstn-usage-records.md)