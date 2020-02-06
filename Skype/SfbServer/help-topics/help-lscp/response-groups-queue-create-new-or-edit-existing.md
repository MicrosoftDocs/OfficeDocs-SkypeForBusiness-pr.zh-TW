---
title: 回應群組佇列建立新的或編輯現有的
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
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
description: 回應群組佇列將呼叫控制到回應群組，直到工程師接聽通話。
ms.openlocfilehash: cd948c145033cf3d4f6a3e79a0c4d0c36f6f70fe
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822376"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>回應群組佇列：建立新的或編輯現有佇列

回應群組佇列將呼叫控制到回應群組，直到工程師接聽通話。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的欄位。

- **名稱**每個佇列必須具有名稱。 輸入佇列的描述性名稱。

- **描述**此為選用欄位。 使用它來提供有關佇列的其他詳細資料。

- **群組**選取您要指派給佇列的代理群組。 按一下 [**選取**]，將代理群組新增至清單。 按一下 [**移除**]，從清單中刪除選取的 [代理] 群組。

    您可以使用向上鍵或向下鍵，在清單中上移或下移您所選取的代理人群組。 代理人群組的順序會影響商務用 Skype 伺服器搜尋可用的代理程式的順序。 也就是說，搜尋可用代理人時，會先搜尋清單中的第一個群組，之後才會搜尋第二個與之後的群組。

- **啟用佇列**超時選取此核取方塊，以指定呼叫者在撥打電話前等候保留的最長時間週期。 如果您選取此選項，您也需要指定下列專案：

  - **超時時間（秒）** 選取或輸入呼叫者在撥打電話前可以等候的最大秒數。

  - **通話動作**選取來電超時時所發生的動作。您的選擇如下：

  - **中斷連線**

  - **轉寄到語音信箱**如果您選取此選項，請在 [ **sip 位址**] 中，輸入 [sip：<username> @ <domainname> sip:bob@contoso.com）] 中的語音信箱位址（例如，）。

  - **轉寄至電話號碼**如果您選取此選項，請在 [ **sip 位址**] 中，輸入 [sip：<number> @ <domainname> ] 的電話號碼（例如，sip:+14255550121@contoso.com）。

  - **轉寄到 SIP 位址**選取此選項可將通話轉寄給其他使用者。 在 [ **sip 位址**] 中，在 [sip 格式] 中輸入使用者<username>@<domainname>的 URI：。

  - **轉寄至另一個佇列**如果您選取此選項，請流覽至通話超時時接收通話的佇列。

- **啟用佇列溢出**選取此核取方塊，以指定佇列可以保留的呼叫數目上限。 如果您選取此選項，您也需要指定下列專案：

  - **最大通話數**選取或輸入佇列可以保留的呼叫數目上限。

  - **轉接來電**選取在達到佇列溢出閾值時，要採取行動的通話。

  - **通話動作**選取符合佇列溢出閾值時所發生的動作。 您的選擇如下：

  - **中斷連線**

  - **轉寄到語音信箱**如果您選取此選項，請在 [ **sip 位址**] 中，輸入 [sip：<username> @ <domainname> sip:bob@contoso.com）] 中的語音信箱位址（例如，）。

  - **轉寄至電話號碼**如果您選取此選項，請在 [ **sip 位址**] 中，輸入 [sip：<number> @ <domainname> ] 的電話號碼（例如，sip:+14255550121@contoso.com）。

  - **轉寄到 SIP 位址**選取此選項可將通話轉寄給其他使用者。 在 [ **sip 位址**] 中，在 [sip 格式] 中輸入使用者<username>@<domainname>的 URI：。

  - **轉寄至另一個佇列**如果您選取此選項，請在達到佇列溢出閾值時，流覽到要接收呼叫的佇列。

如需回應群組功能與功能的詳細資訊，請參閱規劃檔中的[商務用 Skype Server 2015 中的回應群組應用程式規劃](../../plan-your-deployment/enterprise-voice-solution/response-group.md)。 如需使用佇列的詳細資訊，請參閱作業文件中的〈[Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)〉。


