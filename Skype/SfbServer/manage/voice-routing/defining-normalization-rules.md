---
title: 在商務用 Skype Server 中定義正常化規則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype Server 正規化規則使用 .NET Framework 正則運算式，將撥打的電話號碼轉譯為 e.164 格式;換句話說，正規化規則可讓使用者撥打的電話號碼，並將該號碼轉換為商務用 Skype 伺服器內部所用的格式。 每個撥號對應表都必須被指派一或多個正常化規則。
ms.openlocfilehash: d4e248dc9b814610df544bca9d932a29756a80b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823373"
---
# <a name="defining-normalization-rules-in-skype-for-business-server"></a>在商務用 Skype Server 中定義正常化規則

商務用 Skype Server 正規化規則使用 .NET Framework 正則運算式，將撥打的電話號碼轉譯為 e.164 格式;換句話說，正規化規則可讓使用者撥打的電話號碼，並將該號碼轉換為商務用 Skype 伺服器內部所用的格式。 每個撥號對應表都必須被指派一或多個正常化規則。

如需正規化規則的詳細資訊，請參閱撥號對應表 [和正常化規則](https://technet.microsoft.com/library/gg413082(v=ocs.15).aspx)。

如需如何撰寫正則運算式的詳細資訊，請參閱 [.Net Framework 正則運算式](https://go.microsoft.com/fwlink/p/?linkId=140927)。

您可以使用下列其中一種方法來定義或編輯正規化規則：
- [使用 [ **建立正規化規則** ] 工具](#create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule) 來指定起始數位、長度、要移除的數位和要新增的數位的值，然後讓商務用 Skype Server 控制台產生對應的符合模式和轉譯規則。
- [手動寫入正則運算式](#create-or-modify-a-normalization-rule-manually) ，以定義相符的模式和轉譯規則。 

## <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule"></a>使用組建正常化規則建立或修改正規化規則

如果您想要在商務用 Skype Server [控制台] 中建立或修改正規化規則，請完成下列步驟。 

**使用組建正常化規則定義規則**

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [委派設定許可權](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)。
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。 如需可用於啟動商務用 Skype 控制台之不同方法的詳細資訊，請參閱 [Install and open the 系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3.  (選用) 遵循步驟 11 [建立撥號](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-create-a-dial-plan) 對應表中的步驟，或透過步驟 10 [修改撥號](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-enterprise-voice/dial-plans#to-modify-a-dial-plan) 對應表。 
4. 在 [ **新增正規化規則** ] 或 [編輯正規化 **規則**] 中，輸入描述 [ **名稱** ] 中正規化的號碼模式的名稱 (例如， **5DigitExtension**) 。
5.  (選用) 在 [ **描述**] 中，輸入正規化規則的描述 (例如，「轉譯5位數分機」 ) 。
6. 在 [ **建立正規化規則**] 中，在下欄欄位中輸入值：
    - **開始位數**： (選用) 指定您想要模式符合的撥號號碼的前置位數。 例如，如果您希望模式比對從425開始的撥號號碼，請輸入 **425** 。
    - **Length**：指定比對模式中的位數，並選取是否要讓模式完全符合此長度、符合至少為此長度的撥號號碼，或比對任何長度的撥號號碼。
    - **要移除的位數**： (選用) 指定您想要模式符合的撥號號碼中所要移除的開始位數。
    - **要新增的位數**： (選用) 指定要新增至撥號號碼的數位，使其符合模式。
    
    您在這些欄位中輸入的值會反映在模式中， **以符合** 和 **轉譯規則**。 例如，如果您保留的 **開始位數** 為空，請在 [**長度**] 欄位中輸入 **7** ，然後選取 [**完全**]，並指定 **要移除的位數** 為 **0** ，**模式** 中所產生的正則運算式會比對：

    **^ ( \d {7}) $**

7. 在 [ **轉譯規則**] 中，指定轉譯的 e.164 電話號碼格式的模式，如下所示：
    - 代表匹配模式中指定之位數的值。 例如，如果相符的模式是 **^ ( \d {7}) $**，則轉譯規則中的 $1 會代表7位數的撥號號碼。
    -  (選用) 在 [ **要新增的位數** ] 欄位中輸入值，以指定要附加到已翻譯的號碼的位數 (例如， **+ 1425**) 。
    
    例如，如果 **要比對的模式** 包含 **^ ( \d {7}) $** 做為撥打號碼和 **轉譯規則** 的模式，包含 **+ 1425 $ 1** 做為 e.164 電話號碼的模式，規則會將5550100標準化為 + 14255550100。

8.  (選用) 如果正規化規則會產生您組織內部的電話號碼，請選取 [ **內部分機**]。
9.  (選用) 請輸入號碼以測試正規化規則，然後按一下 [ **移至**]。 測試結果會顯示在 [ **輸入要測試的號碼**] 底下。
    > [!Note] 
    > 您可以儲存尚未通過測試的正規化規則，然後稍後再加以重新設定。 如需詳細資訊，請參閱 [測試語音路由](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)。 

10. 按一下 **[確定]** 儲存正規化規則。
11. 按一下 **[確定]** 儲存撥號對應表。
12. 在 [ **撥號** 對應表] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。 
    > [!Note]
    > 當您建立或變更正規化規則時，您必須執行 [全部認可] 命令來發佈設定變更。 如需詳細資訊，請參閱 [將擱置的變更發佈至語音路由](https://technet.microsoft.com/library/gg413088(v=ocs.15).aspx)設定。 

## <a name="create-or-modify-a-normalization-rule-manually"></a>手動建立或修改正規化規則

若要以手動方式建立或修改正規化規則，請完成下列步驟。

**手動定義正常化規則**

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [委派設定許可權](https://technet.microsoft.com/library/gg412735(v=ocs.15).aspx)。
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟 [控制台]。 如需可用於啟動商務用 Skype 控制台之不同方法的詳細資訊，請參閱 [Install and open the 系統管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3.  (選用) 遵循步驟 11 [建立撥號](GET LINK AFTER MIGRATION) 對應表中的步驟，或透過步驟 10 [修改撥號](GET LINK AFTER MIGRATION) 對應表。  
4. 在 [ **新增正規化規則** ] 或 [編輯正規化 **規則**] 中，輸入描述 [ **名稱** ] 中正規化的號碼模式的名稱 (例如，將正規化規則名稱 **5DigitExtension**) 。
5.  (選用) 在 [ **描述**] 中，輸入正規化規則的描述 (例如，「轉譯5位數分機」 ) 。
6. 在 [ **建立正常化規則**] 中，按一下 [ **編輯**]。
7. 在 [輸入規則運算式] 中輸入下列內容：
    - 在 [ **符合此模式**] 中，指定您要用來比對撥號電話號碼的模式。
    - 在 [ **轉譯規則**] 中，指定轉譯的 e.164 電話號碼格式的模式。

    例如，如果您輸入 **^ ( \d {7}) $** in **符合此模式**，並在 **轉譯規則** 中的 **+ 1425 $ 1** ，則此規則會將5550100標準化為 + 14255550100。

8.  (選用) 如果正規化規則會產生您組織內部的電話號碼，請選取 [ **內部分機**]。
9.  (選用) 請輸入號碼以測試正規化規則，然後按一下 [ **移至**]。 測試結果會顯示在 [ **輸入要測試的號碼**] 底下。

    > [!Note]
    > 您可以儲存尚未通過測試的正規化規則，然後稍後再加以重新設定。 如需詳細資訊，請參閱 [測試語音路由](https://technet.microsoft.com/library/gg398915(v=ocs.15).aspx)。 

10. 按一下 **[確定]** 儲存正規化規則。
11. 按一下 **[確定]** 儲存撥號對應表。
12. 在 [ **撥號** 對應表] 頁面上，按一下 [ **Commi** t]，然後按一下 [ **全部認可**]。 
