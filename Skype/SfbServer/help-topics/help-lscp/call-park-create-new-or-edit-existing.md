---
title: 通話駐留建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 通話駐留數位範圍定義將暫停通話一直留在他人取得或超時的暫時號碼。
ms.openlocfilehash: 0403411f6d6b1b084f6766b2620718aa99d77f13
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823106"
---
# <a name="call-park-create-new-or-edit-existing"></a>通話駐留：建立新的或編輯現有

通話駐留數位範圍定義將暫停通話一直留在他人取得或超時的暫時號碼。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的欄位。

- **名稱**輸入識別數位範圍的描述性名稱。 在您儲存編號範圍之後，此名稱就無法變更。

- **數位範圍**在第一個欄位中，輸入數位範圍的起始編號。 在第二個欄位中，輸入數位範圍的結束數位。

  - 該範圍的起始號碼必須小於或等於範圍的結束號碼。

  - 該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。

  - 號碼範圍必須是唯一的。此範圍不得與其他任何範圍重疊。

  - 如果數位範圍是以字元\*或 # 開頭，則範圍必須大於100。

  - 有效值：必須符合正則運算式字串（[\\* | #]？ [1-9] \d{0,7}） |（[1-9] \d{0,8}）。 這表示值必須是以字元\*或 # 或數位1到9（第一個字元不能是零）開頭的字串。 如果第一個字元是\*或 #，則下列字元必須是1到9的數位（不能是零）。 後續字元可以是從0到9的任何數位，最多可達七個其他字元（例如，\*"#6000"、\*"92000"、"95551212" 和 "915551212"）。 如果第一個字元不\*是或 #，則第一個字元必須是數位1到9（不能是零），然後再加上最多八個字元（例如： 915551212; 41212; 300）。

  - 每個集區的號碼總數不得超過 50,000 個。每個號碼範圍通常會涵蓋 100 個以下的號碼，但只要總數不超過 10,000 個號碼，則範圍可以大一些。例如，與其指定起始號碼 7000000 與結束號碼 8000000，請考慮指定起始號碼 7000000 與結束號碼 7000100。

- **目的地伺服器的 FQDN**選取託管通話駐留應用程式之應用程式服務的完整功能變數名稱（FQDN）或服務識別碼。 在數位範圍內，由 start 編號和結束號碼所指定範圍內的所有來電都會路由到這個伺服器或池子。

如需通話寄存功能與功能的詳細資料，請參閱[在商務用 Skype 2015 中規劃通話寄存](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。 如需使用通話駐留編號範圍的詳細資料，請參閱[設定停用通話的電話號碼延伸](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。


