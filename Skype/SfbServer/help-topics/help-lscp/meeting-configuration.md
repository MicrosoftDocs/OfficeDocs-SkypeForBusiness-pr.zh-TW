---
title: 會議組態
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
description: 會議設定設定會定義會議類型 (也是 calledmeetings) 使用者可以建立，並 (控制) 匿名使用者和電話撥入式會議使用者是否可以加入這些會議。 這些設定只適用于排程的會議。 在用戶端中按一下 [立即開會] 選項，不會套用至所建立的特定會議。
ms.openlocfilehash: a0b5f10cbf76e90e58723be3ec05a918a2e2e6fc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610930"
---
# <a name="meeting-configuration"></a>會議組態

會議設定設定會定義使用者可以建立的會議 (類型 ) ，也可以 (控制) 匿名使用者和電話撥入式會議使用者是否可以加入這些會議。 這些設定只適用于排程的會議。 在用戶端中按一下 [立即開會] 選項，不會套用至所建立的特定會議。

會議設定會套用在全域、網站或集區層級：

- **全域會議設定：** 預設會建立全域會議設定。 您只可編輯全域會議設定，而無法加以刪除。 如果您嘗試移除全域會議設定，所有設定皆會重設為預設值。

- **網站會議設定 (選用) ：** 您可以建立一或多個網站會議設定，每個設定會套用至特定網站。 網站設定優先於全域設定。

- **集區會議設定 (選用) ：** 您可以建立一或多個集區會議設定，每個設定會套用至特定集區。 集區設定優先於全域設定。

「會議設定」頁面會顯示為組織所定義之所有會議設定的清單。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「會議設定」頁面上執行下列工作：

- 建立新的網站會議設定或集區會議設定

- 變更全域設定或現有的網站設定或集區設定

- 刪除網站設定或集區設定

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的命令。

- **新** 啟動新的網站會議設定或集區會議設定。

- **編輯** 開啟選取的會議設定進行編輯、選取清單中所有的會議設定，或刪除選取的網站設定或集區設定。

    > [!NOTE]
    > **刪除** 會將全域會議設定的設定重設為預設值。

- **Refresh** 重新整理會議設定清單。

下列清單說明頁面上的欄位。

- **名稱** 識別會議設定。

- **範圍** 識別會議設定的範圍：全域、網站或集區。

如需使用會議設定的詳細資訊，請參閱作業文件中的＜[Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings)＞。