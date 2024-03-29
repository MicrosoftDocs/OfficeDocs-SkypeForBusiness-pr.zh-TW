---
title: 回應群組建立新的代理人群組或編輯現有的代理人群組
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
ROBOTS: NOINDEX, NOFOLLOW
description: 代理群組會定義接聽回應群組 (稱為代理) 電話的人選，以及要套用至群組中所有代理的設定。
ms.openlocfilehash: b17a8db2541d10abfc46b8d7e1be2990b82f598b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385091"
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a>回應群組：建立新代理群組或編輯現有代理群組

代理群組會定義接聽回應群組 (稱為代理) 電話的人選，以及要套用至群組中所有代理的設定。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的欄位。

- **名字** 每個代理人群組都需要唯一的名稱。 請使用識別群組功能的描述性名稱。 例如，問訊台。

- **描述** 此欄位是選用的。 使用它來提供群組的其他詳細資料。

- **參與原則** 指定代理程式簽入回應群組的方式：

  - 選取 [ **非正式** ]，以指定群組中的代理程式不需要登入和登出。非正式代理會在登入時自動登入。 [非正式] 為預設設定。

  - 選取 [ **正式** ]，以指定群組中的代理人必須登入和登出。當您選取此選項時，代理程式會按一下用戶端中的功能表項目以開啟瀏覽器，並顯示網頁主控台以供登入和登出。

- **(秒的提醒時間)** 指定在向下一個可用的代理程式提供呼叫之前，要撥打代理程式的秒數。 該值必須至少10秒且小於180秒。 預設值為20秒。

- **路由方法** 選取判斷代理人接收通話順序的方法：

  - 選取 [最長閒置時間] 將新的電話清單提供給已閒置 (目前狀態已是 [線上] 或 [非使用中]) 最長時間的代理。

  - 選取 [平行] 同時提供新電話給所有線上代理。電話會傳送給第一個接聽的代理。

  - 選取 [循環配置資源] 以輪流提供新電話給每位代理。

  - 選取 [循序] 一律依照 [代理] 清單中所列出的順序，將新電話提供給代理。

  - 選取 [語音應答]， **可對所有** 已登入的代理和回應群組應用程式同時提供新呼叫，不論其目前目前狀態為何。 設定為代理人的語音應答和用戶端使用者可以查看所有等待的來電，並可依任何順序接聽等候通話。 通話會傳送給第一個接受此通話的代理商，另一個語音應答和使用者將不會再看到此通話。

- **代理** 以下列其中一種方式，選取要成為回應群組之代理人的使用者：

  - 選取 [**使用現有的電子郵件通訊群組清單**] 以使用 Exchange 通訊群組清單。 請在 [通訊群組清單位址] 中輸入通訊群組清單的電子郵件地址。

    > [!NOTE]
    > 您可以僅選取一個代理群組的通訊群組清單。若通訊群組清單包含巢狀通訊群組清單，那些巢狀通訊群組清單將不會包含在代理群組中。

    > [!NOTE]
    > 代理列在通訊群組清單中的順序，會影響代理接聽循環配置資源電話及循序路由電話的順序。

    > [!NOTE]
    > 回應群組管理員或使用者可能會看到隱藏的成員資格或隱藏的清單。 如需詳細資訊，請參閱[Create or modify agent group in 商務用 Skype](../../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)。

  - 選取 [定義代理自訂群組] 以選取您要指派作為回應群組代理的使用者。按一下 [選取] 將代理新增至清單。按一下 [移除] 可從清單刪除選取的代理。

    使用向上鍵及向下鍵可在代理清單中移動選取的代理。代理在清單中的順序，會影響代理接聽循環配置資源電話及循序路由電話的順序。

如需有關回應群組功能及功能的詳細資訊，請參閱規劃檔[中商務用 Skype Server 的回應群組應用程式](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)。 如需使用代理群組的詳細資訊，請參閱作業文件中的＜[Managing Agent Groups](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-agent-groups)＞。