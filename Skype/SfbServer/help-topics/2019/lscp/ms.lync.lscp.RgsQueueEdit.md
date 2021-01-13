---
title: 回應群組佇列建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 回應群組佇列會將呼叫保留到回應群組，直到代理接聽來電為止。
ms.openlocfilehash: 097c28db7f2ae52d7ab0b362e828c8f05e132481
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808193"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a>回應群組佇列：建立新的或編輯現有

回應群組佇列會將呼叫保留到回應群組，直到代理接聽來電為止。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的欄位。

- **名稱** 每個佇列都必須有名稱。 輸入佇列的描述性名稱。

- **描述** 此欄位是選用的。 使用它提供有關佇列的其他詳細資料。

- **群組** 選取您要指派給佇列的代理人群組。 按一下 [ **選取** ]，將代理群組新增至清單。 按一下 [ **移除** ]，從清單中刪除選取的代理人群組。

    向上及向中箭號會在清單中上下移動選取的代理群組。 代理人群組的順序會影響商務用 Skype 伺服器搜尋可用之代理人的順序。 也就是說，會先搜尋清單中的第一個群組，以取得可用的代理程式，後面接著第二個群組，依此類推。

- **啟用佇列** 超時選取此核取方塊可指定來電者等候通話之前等候保留的時間上限。 如果您選取此選項，您也必須指定下列專案：

  - **(秒的超時時間)** 選取或輸入來電者可以等候代理接聽通話的最長秒數。

  - **通話動作** 選取來電超時時所發生的動作。您可以選擇：

  - **中斷連線**

  - **轉寄至語音信箱** 如果您選取此選項，請在 [ **sip 位址**] 的 [sip： (格式] 中輸入語音信箱位址， <username> @ <domainname> 例如，sip:bob@contoso.com) 。

  - **轉寄至電話號碼** 如果您選取此選項，請在 [ **sip 位址**] 中，輸入 [sip： (格式的電話號碼] <number> @ <domainname> 例如，sip:+14255550121@contoso.com) 。

  - **轉寄至 SIP 位址** 選取這個選項，將來電轉寄給另一個使用者。 在 [ **sip 位址**] 中，以 [sip：] 的格式輸入使用者的 URI <username> @ <domainname> 。

  - **轉寄到另一個佇列** 如果您選取此選項，請流覽至通話超時時要接聽通話的佇列。

- **啟用佇列溢出** 選取此核取方塊可指定佇列可以保留的通話數目上限。 如果您選取此選項，您也必須指定下列專案：

  - **呼叫數目上限** 選取或輸入佇列可以保留的通話數目上限。

  - **轉寄通話** 選擇符合佇列溢出臨界值時，要採取行動的呼叫。

  - **通話動作** 選取達到佇列溢出閾值時所發生的動作。 您可以選擇：

  - **中斷連線**

  - **轉寄至語音信箱** 如果您選取此選項，請在 [ **sip 位址**] 的 [sip： (格式] 中輸入語音信箱位址， <username> @ <domainname> 例如，sip:bob@contoso.com) 。

  - **轉寄至電話號碼** 如果您選取此選項，請在 [ **sip 位址**] 中，輸入 [sip： (格式的電話號碼] <number> @ <domainname> 例如，sip:+14255550121@contoso.com) 。

  - **轉寄至 SIP 位址** 選取這個選項，將來電轉寄給另一個使用者。 在 [ **sip 位址**] 中，以 [sip：] 的格式輸入使用者的 URI <username> @ <domainname> 。

  - **轉寄到另一個佇列** 如果您選取此選項，請流覽至滿足佇列溢出閾值時要接聽通話的佇列。

如需有關回應群組功能及功能的詳細資訊，請參閱規劃檔中的在 [商務用 Skype Server 中規劃回應群組應用程式](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) 。 如需使用佇列的詳細資訊，請參閱 Operations 檔中的 [管理回應群組佇列](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) 。


