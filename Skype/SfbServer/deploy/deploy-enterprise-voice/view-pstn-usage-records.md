---
title: 在商務用 Skype 中查看 PSTN 使用狀況記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 摘要：瞭解如何使用商務用 Skype Server [控制台] 或商務用 Skype Server 管理命令介面來查看 PSTN 使用記錄。
ms.openlocfilehash: 96a96898bf728b4f05ba473bc750635e41be19fa
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002723"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>在商務用 Skype 中查看 PSTN 使用狀況記錄

**摘要：** 瞭解如何使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面來查看 PSTN 使用記錄。

公用交換電話網絡（PSTN）使用記錄會指定呼叫類別（例如內部、當地或長途），這些使用者可以由不同的使用者或組織中的使用者群組進行。 如需詳細資訊，請參閱規劃檔中的[PSTN 使用記錄](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)。

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 來查看 PSTN 使用記錄

1. 開啟商務用 Skype Server 的 [控制台]。

2. 在左側導覽列中，按一下 [**語音路由**]，然後按一下 [ **PSTN 使用狀況**]。

3. 在 [ **Pstn 使用狀況**] 頁面上，醒目提示您要查看的 PSTN 使用記錄，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

    > [!NOTE]
    > 所選 PSTN 使用記錄的唯讀頁面會顯示關聯的路線及相關的語音原則。

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>使用商務用 Skype Server Management Shell Cmdlet 來查看 PSTN 使用狀況資訊

- 若要查看所有 PSTN 用法的相關資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 ENTER：

  ```powershell
  Get-CsPstnUsage
  ```

    這個命令會傳回如下所示的資訊：

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>另請參閱

[在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用記錄](voice-policy-and-pstn-usage-records.md)

