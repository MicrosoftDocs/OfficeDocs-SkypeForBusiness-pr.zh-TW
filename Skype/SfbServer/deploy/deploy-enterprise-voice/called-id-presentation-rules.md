---
title: 在商務用 Skype Server 中建立或修改呼叫 ID 簡報的翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '摘要: 瞭解如何使用商務用 Skype Server 中的 [建立翻譯規則] 工具來定義翻譯規則。'
ms.openlocfilehash: 3c72e53044abe44660423bbd9bc1adbbeed2a3ed
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234000"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或修改呼叫 ID 簡報的翻譯規則

**摘要:** 瞭解如何使用商務用 Skype Server 中的 [建立翻譯規則] 工具來定義翻譯規則。

如果您想要定義翻譯規則, 請在 [**建立翻譯規則**] 工具中輸入一組值, 並啟用商務用 Skype Server [控制台], 為您產生對應的相符模式與翻譯規則, 以執行下列步驟。 或者, 您也可以手動寫入正則運算式, 以定義相符的模式和轉換規則。 如需詳細資訊, 請參閱[手動建立或修改翻譯規則](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)。

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>使用 [建立翻譯規則] 工具定義規則

1. 開啟商務用 Skype Server 的 [控制台]。

2. 若要開始定義翻譯規則, 請遵循在[商務用 Skype server 中的 [透過媒體旁路媒體來設定主幹](configure-trunk-with-media-bypass.md)] 中的步驟, 或在 [商務用 skype 伺服器] 中的 [透過步驟 9][設定主幹, 不需媒體旁路](configure-trunk-without-media-bypass.md)。

3. 在 [**新增翻譯規則**] 或 [**編輯翻譯規則**] 頁面上的 [**名稱**] 底下, 輸入描述所翻譯之數位模式的名稱。

4. 可選在 [**描述**] 底下, 輸入翻譯規則的描述, 例如美國國際長途撥號。

5. 在對話方塊的 [**建立翻譯規則**] 區段中, 于下欄欄位中輸入值:

   - **起始位數**: (選擇性) 指定您想要模式符合的前置數位數位。 例如, 在這個欄位中輸入 [+], 就會以 E. 164 格式 (開頭為 +) 來相符數位。

   - **長度**: 指定 [相符] 模式中的位數, 並選取您想要模式與此長度完全相同、至少為此長度或任何長度。 例如, 在下拉式清單中輸入11及 selectAt, 以符合長度至少為11位數的數位。

   - **要移除的位數**: (選用) 指定要移除的起始位數數。 例如, 輸入1來去掉數位開頭的 +。

   - **要加上的位數**: (選擇性) 指定要在已翻譯數位前加上的數位。 例如, 如果您想要在套用規則時將011附加到已翻譯的編號中, 請輸入011。

     您在這些欄位中輸入的值會反映在 [相符] 與 [**翻譯規則**] 欄位的**模式**中。 例如, 如果您指定前面的範例值, 則在 [模式] 中產生的正則運算式會與 field**相符**:

     ^\+(\d{9}\d +) $

     [**翻譯規則**] 欄位會指定已翻譯數位格式的模式。 此模式有兩個部分:

   - 代表 [相符] 模式中之位數的值 (例如, $1)

   - 可選您可以在 [**要新增的數位**] 欄位中輸入的值。

     使用上述範例值, 011 $ 1 會出現在 [**翻譯規則**] 欄位中。

     套用此翻譯規則時, + 441235551010 會變成011441235551010。

6. 按一下 **[確定]** 儲存翻譯規則。

7. 按一下 **[確定]** 以儲存幹線設定。

8. 在 [**幹線**設定] 頁面上, 按一下 [**認可**], 然後按一下 [**全部確認**]。

   > [!NOTE]
   > 每當您建立或修改翻譯規則時, 您必須執行 [**全部提交**] 命令才能發佈設定變更。 如需詳細資訊, 請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。

### <a name="to-define-a-translation-rule-manually"></a>手動定義翻譯規則

1. 開啟商務用 Skype Server 的 [控制台]

2. 若要開始定義翻譯規則, 請遵循在[商務用 Skype server 中的 [透過媒體旁路媒體來設定主幹](configure-trunk-with-media-bypass.md)] 中的步驟, 或在 [商務用 skype 伺服器] 中的 [透過步驟 9][設定主幹, 不需媒體旁路](configure-trunk-without-media-bypass.md)。

3. 在 [**新增翻譯規則**] 或 [**編輯翻譯規則**] 頁面上的 [**名稱**] 欄位中, 輸入描述所翻譯之數位模式的名稱。

4. 可選在 [**描述**] 中, 輸入翻譯規則的描述, 例如美國國際長途撥號。

5. 按一下 [**組建翻譯規則**] 區段底部的 [**編輯**]。

6. 在 [輸入**正則運算式**] 中輸入下列內容:

   - 在 [**符合這個模式**] 中, 指定將用來符合要翻譯之數位的模式。

   - 在**翻譯規則**中, 指定翻譯數位格式的模式。

     例如,\+如果您在**翻譯規則**中輸入{9}^ (\d \d +) $**與此模式**and011 $ 1, 規則會將 + 441235551010 轉換為011441235551010。

7. 按一下 **[確定]** 儲存翻譯規則。

8. 按一下 **[確定]** 以儲存幹線設定。

9. 在 [**幹線**設定] 頁面上, 按一下 [**認可**], 然後按一下 [**全部確認**]。

    > [!NOTE]
    > 每當您建立或修改翻譯規則時, 您必須執行 [**全部提交**] 命令才能發佈設定變更。 如需詳細資訊, 請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中使用 [旁路媒體] 設定主幹](configure-trunk-with-media-bypass.md)

[在商務用 Skype Server 中設定不使用媒體的主幹](configure-trunk-without-media-bypass.md)

[在商務用 Skype 中發佈 [語音路由設定] 的擱置變更](voice-route-config-changes.md)

[在商務用 Skype Server 中部署媒體旁路](deploy-media-bypass.md)

