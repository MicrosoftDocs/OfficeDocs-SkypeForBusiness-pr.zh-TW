---
title: 通話駐留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: 當通話停用時, 會將來電轉接到暫時的號碼中, 讓通話一直留在有人將它取出或超時。您必須使用您為寄存通話保留的延伸編號範圍來設定表格。 這些分機必須是虛擬分機 (也就是，沒有為分機指派任何使用者或電話)。 每個執行通話駐留應用程式的池都可以有一或多個延伸範圍。 在您的部署中，這些範圍必須是全域唯一的。
ms.openlocfilehash: d325b1dd2066bd35f6dc9003de4c026a7f925a72
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191686"
---
# <a name="call-park"></a>通話駐留

當通話停用時, 會將來電轉接到暫時的號碼中, 讓通話一直留在有人將它取出或超時。您必須使用您為寄存通話保留的延伸編號範圍來設定表格。 這些分機必須是虛擬分機 (也就是，沒有為分機指派任何使用者或電話)。 每個執行通話駐留應用程式的池都可以有一或多個延伸範圍。 在您的部署中，這些範圍必須是全域唯一的。

[**通話駐留**] 頁面會顯示針對您的組織定義的所有電話寄存編號範圍清單。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以從「通話駐留」**** 頁面執行下列工作：

- 建立新號碼範圍

- 變更現有號碼範圍

- 刪除號碼範圍

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的命令。

- **新增**開始新的通話公園編號範圍。

- [**編輯**]開啟選取的數位範圍進行編輯、選取清單中的所有數位範圍, 或刪除選取的數位範圍。

- **更新**刷新數位範圍清單。

下列清單說明頁面上的欄位。

- **名稱**識別數位範圍的唯一名稱。

- **起始範圍**範圍的起始編號。

- **結束範圍**範圍的結束數位。

- **目的地**寄存電話號碼範圍之通話駐留應用程式之應用程式服務的完整功能變數名稱 (FQDN) 或服務識別碼。

如需通話寄存功能與功能的詳細資料, 請參閱[在商務用 Skype 中規劃通話寄存](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)。 如需使用通話駐留編號範圍的詳細資料, 請參閱[設定停用通話的電話號碼延伸](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。


