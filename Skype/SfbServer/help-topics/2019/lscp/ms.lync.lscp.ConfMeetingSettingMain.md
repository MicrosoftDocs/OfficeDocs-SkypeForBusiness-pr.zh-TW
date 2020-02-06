---
title: 會議組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: '[會議設定設定] 定義使用者可以建立的會議類型（也就是 calledmeetings），並控制匿名使用者和電話撥入式會議使用者可以加入這些會議的方式（或是否有）。 這些設定僅適用于排程的會議。 它們不適用於在用戶端中按一下 [立即開會] 選項所建立的即席會議。'
ms.openlocfilehash: 66a1ff8134eec701cd3bd11b305c4e04e18ef99a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798580"
---
# <a name="meeting-configuration"></a>會議組態

會議組態設定定義使用者所能建立的會議類型，並控制匿名使用者與電話撥入式會議使用者是否可以加入這些會議及其加入方式。這些設定僅適用於排程的會議，而不適用於透過按一下在用戶端中的 [立即開會] 選項所建立的臨時會議。

會議設定會套用在全域、網站或集區層級：

- **全域會議設定：** 預設會建立全域會議設定。 您只可編輯全域會議設定，但無法加以刪除。 如果您嘗試移除全域會議設定，所有設定皆會重設為預設值。

- **網站會議配置（選用）：** 您可以建立一或多個網站會議設定，每個設定都適用于特定網站。 網站設定優先於全域設定。

- **[泳池會議設定] （選用）：** 您可以建立一個或多個 [池會議] 設定，每個設定都適用于特定的文件庫。 集區設定優先於全域設定和網站設定。

「會議設定」**** 頁面會顯示針對組織所定義的所有會議設定的清單。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「會議設定」**** 頁面上執行下列工作：

- 建立新的網站會議設定或集區會議設定

- 變更全域設定或現有的網站設定或集區設定

- 刪除網站設定或集區設定

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的命令。

- **新增**啟動新的網站會議設定或 [池會議] 設定。

- [**編輯**]開啟選取的會議設定以進行編輯、選取清單中的所有會議設定，或刪除選取的網站設定或文件庫設定。

    > [!NOTE]
    > **刪除** 會將全域會議設定重設為預設值。

- **更新**刷新會議配置清單。

下列清單說明頁面上的欄位。

- **名稱**識別會議配置。

- **範圍**識別會議設定的範圍： [全域]、[網站] 或 [文件庫]。

如需使用會議設定的詳細資訊，請參閱作業文件中的〈[Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)〉。


