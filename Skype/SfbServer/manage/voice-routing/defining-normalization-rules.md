---
title: 在商務用 Skype Server 中定義正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype Server 正常化規則使用 .NET Framework 一般運算式，將撥打的電話號碼轉譯為 e. 164 格式;換句話說，正常化規則會採用使用者所撥的電話號碼，並將該號碼轉換為商務用 Skype Server 在內部使用的格式。 每個撥號對應表都必須被指派一或多個正規化規則。
ms.openlocfilehash: ed9db264dc637251c535f111e419aac9aa0f5e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816993"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>在商務用 Skype Server 中定義正常化規則

商務用 Skype Server 正常化規則使用 .NET Framework 一般運算式，將撥打的電話號碼轉譯為 e. 164 格式;換句話說，正常化規則會採用使用者所撥的電話號碼，並將該號碼轉換為商務用 Skype Server 在內部使用的格式。 每個撥號對應表都必須被指派一或多個正規化規則。

如需正常化規則的詳細資訊，請參閱[撥號方案和正常化規則](https://technet.microsoft.com/en-us/library/gg413082(v=ocs.15).aspx)。

如需如何撰寫正則運算式的詳細資料，請參閱[.Net Framework 正則運算式](http://go.microsoft.com/fwlink/p/?linkId=140927)。

您可以使用下列其中一種方法來定義或編輯正常化規則：
- [使用 [**組建正常化規則**] 工具](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule)來指定起始位數、長度、要移除的數位和要加上的數位的值，然後讓商務用 Skype Server [控制台] 為您產生對應的相符模式與翻譯規則。
- [手動寫入正則運算式](#create-or-modify-a-normalization-rule-manually)，以定義相符的模式與翻譯規則。 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>使用組建正常化規則建立或修改正常化規則

若要在商務用 Skype Server [控制台] 中建立或修改正常化規則，請完成下列步驟。 

**使用組建正常化規則定義規則**

1. 以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[委派設定許可權](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 開啟瀏覽器視窗，然後輸入管理員 URL 來開啟 [控制台]。 如需可用於啟動商務用 Skype 控制台之不同方法的詳細資訊，請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 可選請依照步驟 11[建立撥號計畫](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan)中的步驟，或透過步驟 10[修改撥號計畫](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan)。 
4. 在**新的 [正常化規則**] 或 [**編輯正常化規則**] 中，輸入一個名稱，以在**名稱**中描述正常化的數位模式（例如， **5DigitExtension**）。
5. 可選在 [**描述**] 中，輸入正常化規則的描述（例如，"轉譯5位數的延伸"）。
6. 在 [**建立正常化規則**] 中，于下欄欄位中輸入值：
    - **起始位數**：（選用）指定您想要模式符合的撥號號碼的前導位數。 例如，如果您想要讓模式符合從425開始的撥入號碼，請輸入**425** 。
    - **長度**：指定相符模式中的數位位數，並選取您想要模式符合這個長度、與至少有此長度的撥入號碼相符，或與任何長度的撥入號碼相符。
    - **要移除的位數**：（選用）指定要從撥打的號碼中移除的起始位數，您想要讓模式符合該數位。
    - **要加**上的位數：（選擇性）指定要在撥打的號碼中加上您想要模式相符的數位。
    
    您在這些欄位中輸入的值會反映在模式中，**以符合**與**翻譯規則**。 例如，如果您保留**起始位數**為空白，請在**長度**欄位中輸入 7 **，然後選取**[ **0** ] （**要移除**），並指定要移除的**結果**正則運算式如下： ****

    **^ （\d{7}） $**

7. 在**翻譯規則**中，指定翻譯的 e. 164 電話號碼格式的模式，如下所示：
    - 代表 [相符] 模式中指定之位數的值。 例如，如果 [相符] 模式是 **[^ （{7}\d） $**]，則翻譯規則中的 $1 代表7位數的撥入號碼。
    - 可選在 [位數] 中輸入一個值，以指定要在已翻譯的數位前**加**上的位數（例如 **+ 1425**）。
    
    例如，如果**要搭配的模式**包含 **^ （\d{7}） $** 做為撥入號碼和**翻譯規則**的模式，包含 **+ 1425 $ 1**做為 e.i 電話號碼的模式，規則會將5550100標準化至 + 14255550100。

8. 可選如果正常化規則所產生的是貴組織內部的電話號碼，請選取 [**內部擴充**]。
9. 可選輸入數位以測試正常化規則，**然後按一下 [** 執行]。 測試結果會顯示在 [**輸入要測試的號碼**] 下。
    > [!Note] 
    > 您可以儲存尚未經過測試的正常化規則，稍後再重新設定。 如需詳細資訊，請參閱[測試語音路由](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)。 

10. 按一下 **[確定]** 以儲存正常化規則。
11. 按一下 **[確定]** 儲存撥號計畫。
12. 在 [**撥號方案**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。 
    > [!Note]
    > 每當您建立或變更正常化規則時，您必須執行 [全部提交] 命令才能發佈設定變更。 如需詳細資訊，請參閱[發佈語音路由設定的待處理變更](https://technet.microsoft.com/en-us/library/gg413088(v=ocs.15).aspx)。 

## <a name="create-or-modify-a-normalization-rule-manually"></a>手動建立或修改正規化規則

如果您想要手動建立或修改正常化規則，請完成下列步驟。

**手動定義正常化規則**

1. 以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[委派設定許可權](https://technet.microsoft.com/en-us/library/gg412735(v=ocs.15).aspx)。
2. 開啟瀏覽器視窗，然後輸入管理員 URL 來開啟 [控制台]。 如需可用於啟動商務用 Skype 控制台之不同方法的詳細資訊，請參閱[安裝及開啟 [管理工具](../../management-tools/install-and-open-administrative-tools.md)]。
3. 可選請依照步驟 11[建立撥號計畫](GET LINK AFTER MIGRATION)中的步驟，或透過步驟 10[修改撥號計畫](GET LINK AFTER MIGRATION)。  
4. 在**新的 [正常化規則**] 或 [**編輯正常化規則**] 中，輸入描述**名稱**中要正常化之數位模式的名稱（例如，將 [正常化規則**5DigitExtension**] 命名）。
5. 可選在 [**描述**] 中，輸入正常化規則的描述（例如，"轉譯5位數的延伸"）。
6. 在 [**建立正常化規則**] 中，按一下 [**編輯**]。
7. 在 [輸入正則運算式] 中輸入下列內容：
    - 在 [**符合這個模式**] 中，指定您要用來與撥打的電話號碼相符的模式。
    - 在 [**翻譯規則**] 中，指定翻譯的 e. （164個電話號碼）格式的模式。

    例如，如果您在**翻譯規則**中輸入 **^ （\d{7}） $** 與**此模式搭配** **+ 1425 $ 1** ，規則會將5550100標準化至 + 14255550100。

8. 可選如果正常化規則所產生的是貴組織內部的電話號碼，請選取 [**內部擴充**]。
9. 可選輸入數位以測試正常化規則，**然後按一下 [** 執行]。 測試結果會顯示在 [**輸入要測試的號碼**] 下。

    > [!Note]
    > 您可以儲存尚未經過測試的正常化規則，稍後再重新設定。 如需詳細資訊，請參閱[測試語音路由](https://technet.microsoft.com/en-us/library/gg398915(v=ocs.15).aspx)。 

10. 按一下 **[確定]** 以儲存正常化規則。
11. 按一下 **[確定]** 儲存撥號計畫。
12. 在 [**撥號**對應表] 頁面上，按一下 [ **Commi**t]，然後按一下 [**全部確認**]。 
