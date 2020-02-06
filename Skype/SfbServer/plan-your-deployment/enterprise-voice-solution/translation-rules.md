---
title: 商務用 Skype Server 中的翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
description: 瞭解商務用 Skype Server Enterprise Voice 中的翻譯規則與撥號字串正常化。
ms.openlocfilehash: c82b925c9ef168d8a5f5e7ac730a93a53a432e2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802393"
---
# <a name="translation-rules-in-skype-for-business-server"></a>商務用 Skype Server 中的翻譯規則

瞭解商務用 Skype Server Enterprise Voice 中的翻譯規則與撥號字串正常化。

 企業語音要求將所有的撥號字串標準化為 E. 164 格式，以執行反向數位查閱（RNL）。 呼叫號碼和電話號碼都支援翻譯規則。 Thetrunk 對等（也就是關聯的閘道、私人分支 exchange （PBX）或 SIP 幹線）可能需要以本機撥號格式表示號碼。 若要將數位（164格式）轉換成本機撥號格式，您可以定義一或多個翻譯規則，在將要求 URI 傳送到幹線對等前，先進行處理。 例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。

透過在伺服器上執行輸出路由轉換，您可以減少每個個別中繼對等的設定需求，以將電話號碼轉譯為本機撥號格式。 當您規劃哪些閘道以及要與特定的中繼伺服器群集建立關聯的閘道數時，可能會對幹線對等進行類似的本機撥號需求群組有所説明。 這樣可以減少所需翻譯規則的數目，以及撰寫它們所需的時間。

> [!IMPORTANT]
> 將一或多個翻譯規則與企業語音幹線設定建立關聯，就應該使用此替代方法，以在幹線對等上設定翻譯規則。 如果您已在幹線對等上設定翻譯規則，請不要將翻譯規則與企業語音幹線配置建立關聯，因為這兩個規則可能會衝突。

## <a name="example-translation-rules"></a>翻譯規則範例

下列翻譯規則範例會示範如何在伺服器上開發規則，將數位從 E.i 格式轉譯為幹線對等的本機格式。

如需如何實現翻譯規則的詳細資料，請參閱在部署檔中[定義翻譯規則](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。

|**說明**|**起始位數**|**全長**|**移除的位數**|**要新增的位數**|**相符的模式**|**翻譯**|**範例**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|美國的傳統長途電話撥號  <br/> （去除 "+"）  <br/> |+ 1  <br/> |恰好12  <br/> |1  <br/> |0  <br/> |^\+（1 \ d{10}） $  <br/> |$1  <br/> |+ 14255551010 變成14255551010  <br/> |
|美國國際長途撥號  <br/> （去除 "+" 並加上011）  <br/> |+  <br/> |至少11  <br/> |1  <br/> |011  <br/> |^\+（\d{9}\d +） $  <br/> |011 $ 1  <br/> |+ 441235551010 變成011441235551010  <br/> |


