---
title: 在商務用 Skype Server 中定義翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 商務用 Skype Server 企業版語音路由呼叫依據以正常化為 E. 164 格式的電話號碼。 這表示, 所有撥號字串都必須正常化為 E.i 格式, 才能執行反向數位查閱 (RNL), 因此可以將它們轉換成相符的 SIP URI。 商務用 Skype 伺服器提供操縱呼叫 ID 與本機號碼簡報的功能。
ms.openlocfilehash: 633b0c16fefb66d1ea44f96b5f32c2ca91f357f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187036"
---
# <a name="defining-translation-rules-in-skype-for-business-server"></a>在商務用 Skype Server 中定義翻譯規則

商務用 Skype Server 企業版語音路由呼叫依據以正常化為 E. 164 格式的電話號碼。 這表示, 所有撥號字串都必須正常化為 E.i 格式, 才能執行反向數位查閱 (RNL), 因此可以將它們轉換成相符的 SIP URI。 商務用 Skype 伺服器提供操縱呼叫 ID 與本機號碼簡報的功能。

在商務用 Skype Server 中, 呼叫方的電話號碼 (也就是呼叫的電話號碼) 可以從. 164 格式翻譯成幹線對等所需的本機撥號格式 (也就是關聯的閘道、私人分支 exchange (PBX) 或 SIP幹線)。 若要這樣做, 您必須先定義一或多個翻譯規則, 才能轉換要求 URI, 然後再將它傳送到幹線對等。

## <a name="caller-id-presentation"></a>本機號碼

商務用 Skype 伺服器提供選項, 可將呼叫參與方的電話號碼 (也就是呼叫者撥打的電話號碼) 從 E-164 格式轉換為幹線對等所需的本機撥號格式。 例如, 您可以撰寫翻譯規則, 以從撥號字串開頭移除 + 44, 然後將它取代為0144。

**使用商務用 Skype Server 的 [控制台] 設定本機號碼**

1. 以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊, 請參閱[委派設定許可權](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 開啟瀏覽器視窗, 然後輸入管理員 URL 來開啟 [控制台]。 如需可用於啟動商務用 Skype 控制台之不同方法的詳細資訊, 請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 在左側導覽列中, 按一下 [**語音路由**], 然後按一下 [**幹線**設定]。
4. 在 [幹線設定] 頁面上, 按兩下現有的主幹 (例如 [**全域**幹線]), 以顯示 [**編輯主幹**設定] 對話方塊。
5. 若要設定本機號碼方式:
    - 若要從企業語音部署中所有可用的翻譯規則清單中選擇一或多個規則, 請按一下 [**選取**]。 在 [**呼叫編號翻譯規則**] 中, 按一下您要與主幹建立關聯的規則, 然後按一下 **[確定]**。
    - 若要定義新的翻譯規則, 並將其與骨幹建立關聯, 請按一下 [**新增**]。 
    - 若要編輯已經與主幹建立關聯的翻譯規則, 請按一下規則名稱, 然後按一下 [**顯示詳細資料**]。
    - 若要複製現有的翻譯規則, 以做為定義新規則的起點, 請按一下規則名稱, 按一下 [**複製**], 然後按一下 [**貼**上]。
    - 若要從主幹中移除翻譯規則, 請將規則名稱醒目提示, 然後按一下 [**移除**]。

> [!Warning] 
> 如果您已在關聯的中繼對等上設定翻譯規則, 請不要將翻譯規則與幹線建立關聯, 因為這兩個規則可能會衝突。 

## <a name="called-id-presentation"></a>名為「識別碼簡報」

> [!Important]
> 將一或多個翻譯規則與企業語音幹線設定關聯的能力, 旨在代替在幹線對等上設定翻譯規則的*替代方案*。 如果您已在中繼對等上設定翻譯規則, 則不要將翻譯規則與企業語音幹線配置建立關聯, 因為這兩個規則可能會衝突。 

您可以使用下列其中一種方法來建立或修改翻譯規則:

- [使用 [組建翻譯規則] 工具](#create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool), 來指定起始位數、長度、要移除的數位和要加上的數位的值, 然後讓商務用 Skype Server 的 [控制台] 為您產生對應的相符模式與翻譯規則。
- [手動寫入正則運算式](#create-or-modify-a-translation-rule-manually), 以定義相符的模式與翻譯規則。

> [!Note]
> 如需如何撰寫正則運算式的相關資訊, 請參閱[.Net Framework 正則運算式](http://go.microsoft.com/fwlink/p/?linkId=140927)。 

### <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool"></a>使用 [建立翻譯規則] 工具建立或修改翻譯規則

如果您想要定義翻譯規則, 請在 [建立翻譯規則] 工具中輸入一組值, 並啟用商務用 Skype Server 的 [控制台], 為您產生對應的相符模式與翻譯規則, 以執行下列步驟。 

**使用 [建立翻譯規則] 工具定義規則**

1. 以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊, 請參閱[委派設定許可權](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 開啟瀏覽器視窗, 然後輸入管理員 URL 來開啟 [控制台]。 如需可用於啟動商務用 Skype 控制台之不同方法的詳細資訊, 請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 若要開始定義翻譯規則, 請遵循使用 [透過[媒體旁路媒體設定幹線](GET LINK AFTER MIGRATION)] 中的步驟, 或在步驟 9[無媒體旁路的情況下設定幹線](GET LINK AFTER MIGRATION)。
4. 在 [**新增翻譯規則**] 或 [**編輯翻譯規則**] 頁面上的 [**名稱**] 底下, 輸入描述所翻譯之數位模式的名稱。
5. 可選在 [**描述**] 底下, 輸入翻譯規則的描述 (例如,**美國國際長途**長途電話)。
6. 在對話方塊的 [**建立翻譯規則**] 區段中, 于下欄欄位中輸入值:
    - **起始位數**: (選擇性) 指定您想要模式符合的前置數位數位。 例如, 在這個欄位中輸入 [+], 就會以 E. 164 格式 (開頭為 +) 來相符數位。
    - **長度**: 指定 [相符] 模式中的位數, 並選取您想要模式與此長度完全相同、至少為此長度或任何長度。 例如, 輸入**11** , 然後在下拉式清單中選取 [**至少**], 以符合長度至少為11位數的數位。
    - **要移除的位數**: (選用) 指定要移除的起始位數數。 例如, 輸入**1**來去掉數位開頭的 +。
    - **要加上的位數**: (選擇性) 指定要在已翻譯數位前加上的數位。 例如, 如果您想要在套用規則時將011附加到已翻譯的編號中, 請輸入**011** 。
    
    您在這些欄位中輸入的值會反映在 [相符] 與 [**翻譯**規則] 欄位的**模式**中。 例如, 如果您指定前面的範例值, 則在 matc h 欄位的 [**模式**] 中產生的正則運算式為:
    
    **^\+(\d{9}\d +) $** 

    [**翻譯規則**] 欄位會指定已翻譯數位格式的模式。 此模式有兩個部分:
    - 代表 [相符] 模式中之位數的值 (例如, **$1**)
    - 可選您可以在 [**要新增的數位**] 欄位中輸入的值。

    使用上述範例值, **011 $ 1**會出現在 [**翻譯規則**] 欄位中。
    
    套用此翻譯規則時, + 441235551010 會變成011441235551010。
7. 按一下 **[確定]** 儲存翻譯規則。
8. 按一下 **[確定]** 以儲存幹線設定。
9. 在 [**幹線 Configuratio**n] 頁面上, 按一下 [**認可**], 然後按一下 [**全部確認**]。 

> [!Note]
> 每當您建立或修改翻譯規則時, 您必須執行 [**全部提交**] 命令才能發佈設定變更。 如需詳細資訊, 請參閱[發佈語音路由設定的待處理變更](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)。 

### <a name="create-or-modify-a-translation-rule-manually"></a>手動建立或修改翻譯規則

如果您想要定義翻譯規則, 方法是撰寫相符模式與翻譯規則的正則運算式, 請遵循下列步驟。 

**手動定義翻譯規則**

1. 以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊, 請參閱[委派設定許可權](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 開啟瀏覽器視窗, 然後輸入管理員 URL 來開啟 [控制台]。 如需可用於啟動商務用 Skype 控制台之不同方法的詳細資訊, 請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 若要開始定義翻譯規則, 請遵循使用 [透過[媒體旁路媒體設定幹線](GET LINK AFTER MIGRATION)] 中的步驟, 或在步驟 9[無媒體旁路的情況下設定幹線](GET LINK AFTER MIGRATION)。
4. 在 [**新增翻譯規則**] 或 [**編輯翻譯規則**] 頁面上的 [**名稱**] 欄位中, 輸入描述所翻譯之數位模式的名稱。
5. 可選在 [**描述**] 中, 輸入翻譯規則的描述;例如,**美國國際長途撥號**。
6. 按一下 [**組建翻譯規則**] 區段底部的 [**編輯**]。
7. 在 [輸入**正則運算式**] 中輸入下列內容:
    - 在 [**符合這個模式**] 中, 指定將用來符合要翻譯之數位的模式。
    - 在**翻譯規則**中, 指定翻譯數位格式的模式。

    例如, 如果您在**翻譯規則**中輸入** ^ \+({9}\d \d +) $** **與此模式**和**011 $ 1**相符, 規則會將 + 441235551010 轉換為011441235551010。
8. 按一下 **[確定]** 儲存翻譯規則。
9. 按一下 **[確定]** 以儲存幹線設定。
10. 在 [**幹線**設定] 頁面上, 按一下 [**認可**], 然後按一下 [**全部確認**]。 

> [!Note] 
> 每當您建立或修改翻譯規則時, 您必須執行 [**全部提交**] 命令才能發佈設定變更。 如需詳細資訊, 請參閱[發佈語音路由設定的待處理變更](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)。 
