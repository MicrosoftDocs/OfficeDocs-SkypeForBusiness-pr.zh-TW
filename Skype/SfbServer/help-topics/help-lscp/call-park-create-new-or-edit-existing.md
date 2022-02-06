---
title: 通話駐留建立新的或編輯現有
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.lscp.VoiceFeaCallParkEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e834d485-d25a-4eec-9090-2b8534ecf65d
description: 通話駐留號碼範圍定義在有人接聽或下班時，寄存通話保留的臨時號碼。
---

# <a name="call-park-create-new-or-edit-existing"></a>通話駐留：建立新的或編輯現有

通話駐留號碼範圍定義在有人接聽或下班時，寄存通話保留的臨時號碼。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的欄位。

- **名字** 輸入識別號碼範圍的描述性名稱。 在您儲存編號範圍後，就無法變更此名稱。

- **號碼範圍** 在第一個欄位中，輸入號碼範圍的開始號碼。 在第二個欄位中，輸入號碼範圍的結束號碼。

  - 該範圍的起始號碼必須小於或等於範圍的結束號碼。

  - 該範圍的起始號碼值的長度必須等於範圍的結束號碼值長度。

  - 號碼範圍必須是唯一的。 此範圍不得與其他任何範圍重疊。

  - 如果號碼範圍開頭為字元 \* 或 #，則範圍必須大於100。

  - 有效的值：必須符合正則運算式字串 ( [ \\ * | #]？ [1-9] \d {0,7}) | ( [1-9] \d {0,8}) 。 這表示值必須是以字元 \* 或 # 或數位1到9為開頭的字串。 (第一個字元不能是零) 。 如果第一個字元是 \* 或 #，下列字元必須是1到9的數位， (不能是零) 。 後續字元可以是0到9的任何數位，最多可以有七個其他字元 (例如，"#6000"、" \* 92000"、" \* 95551212" 和 "915551212" ) 。 如果第一個字元不 \* 是或 #，則第一個字元必須是1到)  (9 的數位，然後是0到9的數位，都是0到 9 (例如： 915551212; 41212; 300) 。

  - 每個集區不得超過總50000數目。 每個號碼範圍通常會包含100或更少的數位，但是只要包含少於10000數目，就會有很大的增加。 例如，與其指定開頭號碼 7000000 與結束號碼 8000000，請考慮指定開始號碼 7000000 與結束號碼 7000100。

- **目的地伺服器的 FQDN** 選取主控通話駐留應用程式之應用程式服務的完整功能變數名稱 (FQDN) 或服務識別碼。 所有寄存在號碼範圍中的 start 編號和結束編號所指定之範圍內的通話，將會路由傳送至此伺服器或集區。

如需通話駐留功能及功能的詳細資訊，請參閱[Plan for 通話駐留 in 商務用 Skype 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。 如需與通話駐留號碼範圍搭配使用的詳細資訊，請參閱[Configure 電話號碼分機的停車電話](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)。