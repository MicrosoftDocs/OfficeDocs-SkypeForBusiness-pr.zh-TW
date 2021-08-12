---
title: 在商務用 Skype Server 中建立或修改呼叫識別碼簡報的轉譯規則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 摘要：瞭解如何使用商務用 Skype Server 中的組建轉譯規則工具來定義轉譯規則。
ms.openlocfilehash: 0f8f511996c8d3a578087c9f4252492fa03ef4237688bcaf68a04f09ed944116
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281286"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或修改呼叫識別碼簡報的轉譯規則

**摘要：** 瞭解如何使用商務用 Skype Server 中的組建轉譯規則工具來定義轉譯規則。

若要定義轉譯規則，請在 [**組建轉譯規則**] 工具中輸入一組值，並啟用商務用 Skype Server 控制台，為您產生對應的相符模式和轉譯規則，以執行下列步驟。 或者，您可以手動寫入正則運算式，以定義符合的模式和轉譯規則。 如需詳細資訊，請參閱 [手動建立或修改轉譯規則](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually)。

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>使用組建轉譯規則工具定義規則

1. 開啟商務用 Skype Server 控制台]。

2. 若要開始定義轉譯規則，請遵循在商務用 Skype Server 到步驟10中[設定具有媒體旁路的主幹](configure-trunk-with-media-bypass.md)中的步驟，或在商務用 Skype Server 透過步驟9中[設定沒有媒體旁路的主幹](configure-trunk-without-media-bypass.md)。

3. 在 [**新增轉譯規則**] 或 [**編輯轉譯規則**] 頁面的 [**名稱**] 下，輸入描述所轉譯之號碼模式的名稱。

4.  (選用) 在 [ **描述**] 底下，輸入轉譯規則的描述，例如美國國際長途撥號。

5. 在對話方塊的 [ **組建轉譯規則** ] 區段中，于下欄欄位中輸入值：

   - **開始位數**： (選用) 指定您想要模式比對的數位前置位數。 例如，在此欄位中輸入 [+]，以比對以 +) 開頭的 (164 格式的數位。

   - **Length**：指定比對模式中的位數，並選取是否要讓模式比對此長度的數位完全一致、至少此長度或任何長度。 例如，在下拉式清單中輸入11和 selectAt，以比對長度至少為11位數的數位。

   - **要移除的位數**： (選用) 指定要移除的開始數位的數目。 例如，輸入1以從號碼的開頭去掉 +。

   - **要新增的位數**： (選用) 指定要預先編號為已轉譯之數位的位數。 例如，如果您希望在套用規則時，將011預先加入翻譯的編號，請輸入011。

     您在這些欄位中輸入的值，會反映在 [ **要搭配的模式** ] 和 [ **轉譯規則** ] 欄位中。 例如，如果您指定前面的範例值，就會在 [ **要搭配的模式** ] 欄位中產生正則運算式：

     ^\+ ( \d {9} \d +) $

     **轉譯規則** 欄位會指定轉譯後的數位格式的模式。 這種模式分為兩個部分：

   - 值 (例如，$1) ，代表比對模式中的數位數目

   -  (選用) 您可以在 [ **要加入的數位** ] 欄位中輸入值，以進行前置計算

     使用上述範例值，011 $ 1 會出現在 **轉譯規則** 欄位中。

     套用此轉譯規則時，+ 441235551010 會變成011441235551010。

6. 按一下 **[確定]** 儲存轉譯規則。

7. 按一下 **[確定]** 儲存主幹組態。

8. 在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。

   > [!NOTE]
   > 當您建立或修改轉譯規則時，您都必須執行 [全部認可] 命令才能發行組態變更。 如需詳細資訊，請參閱操作檔中的[商務用 Skype 發佈擱置變更至語音路由](voice-route-config-changes.md)設定。

### <a name="to-define-a-translation-rule-manually"></a>若要手動定義轉譯規則

1. 開啟商務用 Skype Server 控制台

2. 若要開始定義轉譯規則，請遵循在商務用 Skype Server 到步驟10中[設定具有媒體旁路的主幹](configure-trunk-with-media-bypass.md)中的步驟，或在商務用 Skype Server 透過步驟9中[設定沒有媒體旁路的主幹](configure-trunk-without-media-bypass.md)。

3. 在 **[新增轉譯規則]** 或 **[編輯轉譯規則]** 頁面的 **[名稱]** 欄位中，輸入可描述所轉譯號碼模式的名稱。

4.  (選用) 在 [ **描述**] 中，輸入轉譯規則的描述，例如美國國際長途撥號。

5. 按一下 **[建置轉譯規則]** 區段底部的 **[編輯]**。

6. 在 [輸入規則運算式] 中輸入下列內容：

   - 在 [符合此模式] 中，指定用來比對要轉譯之號碼的模式。

   - 在 [轉譯規則] 中，指定轉譯號碼的格式模式。

     例如，如果您輸入 ^ \+ ( \d {9} \d +) $ In 符合 **轉譯規則** 中的 **此模式** and011 $ 1，則規則會將 + 441235551010 轉譯為011441235551010。

7. 按一下 **[確定]** 儲存轉譯規則。

8. 按一下 **[確定]** 儲存主幹組態。

9. 在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。

    > [!NOTE]
    > 當您建立或修改轉譯規則時，您都必須執行 [全部認可] 命令才能發行組態變更。 如需詳細資訊，請參閱操作檔中的[商務用 Skype 發佈擱置變更至語音路由](voice-route-config-changes.md)設定。

## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中設定具有媒體旁路的主幹](configure-trunk-with-media-bypass.md)

[在商務用 Skype Server 中設定不含媒體旁路的主幹](configure-trunk-without-media-bypass.md)

[在商務用 Skype 中發佈語音路由設定的擱置變更](voice-route-config-changes.md)

[在商務用 Skype Server 中部署媒體旁路](deploy-media-bypass.md)