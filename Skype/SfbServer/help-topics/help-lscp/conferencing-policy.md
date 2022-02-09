---
title: 會議原則
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: 會議原則定義使用者可以在會議中使用的特性與功能。
ms.openlocfilehash: 1f8104a988a821e5a993d8279fefe9c891193bb2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416906"
---
# <a name="conferencing-policy"></a>會議原則

會議原則定義使用者可以在會議中使用的特性與功能。

會議原則包含全域原則，並選擇性地包含一或多個網站與使用者原則：

- **全域原則：** 預設會建立全域原則。 您可以編輯全域原則，但無法加以刪除。 如果您嘗試移除全域原則，則所有設定都會重設為預設值。

- **網站原則 (選用) ：** 您可以建立一或多個網站會議原則，每個原則都適用于特定網站。 網站原則會覆寫全域原則。

- **使用者原則 (選用) ：** 您可以建立一或多個使用者會議原則，每個都適用于特定的使用者或使用者群組。 使用者原則會覆寫全域原則及網站原則。

[ **會議原則** ] 頁面會顯示針對您組織所定義之所有會議原則的清單。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可從「位置原則」頁面執行下列工作：

- 建立新的網站會議原則或使用者會議原則

- 變更全域原則或現有的網站原則或使用者原則

- 刪除網站原則或使用者原則

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的命令。

- **新增功能** 啟動新的網站會議原則或使用者會議原則。

- **編輯** 開啟選取的會議原則進行編輯、選取清單中的所有會議原則，或刪除選取的網站原則或使用者原則。

    > [!NOTE]
    > **刪除** 會將全域原則的設定重設為預設值。

- **刷新** 重新整理會議原則清單。

下列清單說明頁面上的欄位。

- **名字** 識別會議原則。

- **範圍** 識別會議原則的範圍：全域、網站或使用者。

- **資料** 共同作業檢查會議原則是否指定允許在會議中進行資料協同作業。

- **應用程式共用** 檢查會議原則是否指定允許在會議中進行應用程式共用。

- **音訊** 檢查會議原則是否指定允許在會議中使用音訊。

- **視頻** 檢查會議原則是否指定允許在會議中使用影片。

- **PSTN** 檢查會議原則是否指定允許 PSTN 電話撥入式會議。

- **記錄** 檢查會議原則是否指定允許在會議中錄製。

如需會議功能及功能的詳細資訊，請參閱規劃檔中的 [會議綜述](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) 。 如需使用會議原則的詳細資訊，請參閱 Operations 檔中的 [會議原則](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) 。