---
title: 商務用 Skype Server 中的轉譯規則
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 瞭解商務用 Skype Server 企業語音中的轉譯規則和撥號字串正常化。
---

# <a name="translation-rules-in-skype-for-business-server"></a>商務用 Skype Server 中的轉譯規則

瞭解商務用 Skype Server 企業語音中的轉譯規則和撥號字串正常化。

 企業語音需要將所有撥號字串正常化為 e.164 格式，以執行反向號碼查閱 (RNL) 。 同時支援呼叫的號碼和電話號碼的轉譯規則。 Thetrunk 對等 (也就是說，關聯的閘道、專用分支 exchange (PBX) 或 SIP 主幹) 可能要求號碼採用本機撥號格式。 若要將號碼從 E.164 格式轉譯為本地撥號格式，則可以先定義一或多個轉譯規則來操作要求 URI，再將其路由傳送至主幹對等。 例如，您可以撰寫轉譯規則，移除撥號字串開頭的 +44，並改為 0144。

在伺服器上執行輸出路由轉譯，則可以減少在每個個別主幹對等上的設定需求，以將電話號碼轉譯為區域撥號格式。 當您規劃要與特定的轉送伺服器叢集產生關聯的閘道和數目的閘道時，群組主幹對等的功能可能會非常實用，具有類似的本機撥號需求。 如此，可減少所需的轉譯規則數目以及寫入它們所需的時間。

> [!IMPORTANT]
> 若要將一個或多個轉譯規則與企業語音主幹設定相關聯，則應該使用此替代方法來設定主幹對等的轉譯規則。 如果您已在主幹對等上設定轉譯規則，請勿將轉譯規則與企業語音主幹設定產生關聯，因為這兩個規則可能會衝突。

## <a name="example-translation-rules"></a>範例轉譯規則

下列轉譯規則範例顯示如何在伺服器上開發規則，以將號碼從 E.164 格式轉譯為主幹對等的區域格式。

如需如何實作轉譯規則的詳細資訊，請參閱部署文件中的＜[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)＞。

|**描述**|**開頭數字**|**Length**|**要移除的數字**|**要加入的數字**|**比對模式**|**轉換**|**範例**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美國的傳統長途撥號  <br/>  (抽出 ' + ' )   <br/> |+ 1  <br/> |剛好 12 個  <br/> |1  <br/> |0  <br/> |^\+ (1 維 {10}) $  <br/> |$1  <br/> |+14255551010 變成 14255551010  <br/> |
|美國國際長途撥號  <br/>  (拆除 ' + ' 並新增 011)   <br/> |+  <br/> |至少 11 個  <br/> |1  <br/> |011  <br/> |^\+ ( \d {9} \d +) $  <br/> |011 $ 1  <br/> |+441235551010 變成 011441235551010  <br/> |