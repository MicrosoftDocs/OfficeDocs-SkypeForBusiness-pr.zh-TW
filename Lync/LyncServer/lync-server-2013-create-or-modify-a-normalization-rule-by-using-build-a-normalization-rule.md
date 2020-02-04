---
title: 使用組建正常化規則建立或修改正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 519d4d8ee00e0922d40155c541b0f869df095ab1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>在 Lync Server 2013 中使用組建正常化規則來建立或修改正常化規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果您想要在 Lync Server [控制台] 中建立或修改正常化規則，請完成下列步驟。 或者，如果您想要手動建立或修改正常化規則，請參閱[在 Lync Server 2013 中手動建立或修改正常化規則](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)。

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>使用組建正常化規則定義規則

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  可選請遵循在[Lync server 2013](lync-server-2013-create-a-dial-plan.md)至步驟11中建立撥號計畫中的步驟，或透過步驟 10[修改 lync server 2013 中的撥號方案](lync-server-2013-modify-a-dial-plan.md)。

4.  在**新的 [正常化規則**] 或 [**編輯正常化規則**] 中，輸入一個名稱，以在**名稱**中描述正常化的數位模式（例如， **5DigitExtension**）。

5.  可選在 [**描述**] 中，輸入正常化規則的描述（例如，"轉譯5位數的延伸"）。

6.  在 [**建立正常化規則**] 中，于下欄欄位中輸入值：
    
      - **起始位數**   （選用）指定您想要模式符合的撥號號碼的前導位數。 例如，如果您想要讓模式符合從425開始的撥入號碼，請輸入**425** 。
    
      - **[長度**   ]：指定相符模式中的數位位數，並選取您想要模式符合這個長度、與至少有此長度的撥號號碼相符，或與任何長度的撥入號碼相符。
    
      - **要移除**   的數位（選擇性）指定要從撥打的號碼中移除的起始位數，您想要讓模式符合該數位。
    
      - **要加**   上的位數（選擇性）指定要在撥打的號碼中加上您想要模式相符的數位。
    
    您在這些欄位中輸入的值會反映在模式中，**以符合**與**翻譯規則**。 例如，如果您保留的**起始位數**為空白，請在**長度**欄位中輸入**7** ，然後選取 [**精確**]，然後指定要**移除**的 [ **0** ]，即**要與之相符**的正則運算式如下：
    
    **^ （\\d{7}） $**

7.  在**翻譯規則**中，指定翻譯的 e. 164 電話號碼格式的模式，如下所示：
    
      - 代表 [相符] 模式中指定之位數的值。 例如，如果 [相符] 模式是 **[^\\（{7}d）** ]，則翻譯規則中的 **$1**代表7位數的撥入號碼。
    
      - 可選在 [位數] 中輸入一個值，以指定要在已翻譯的數位前**加**上的位數（例如 **+ 1425**）。
    
    例如，如果**要符合的模式**包含 **^ （\\d{7}） $** 做為撥打電話號碼和**翻譯規則**的模式，包含 **+ 1425 $ 1**做為 e.i 電話號碼的模式，規則會將5550100標準化至 + 14255550100。

8.  可選如果正常化規則所產生的是貴組織內部的電話號碼，請選取 [**內部擴充**]。

9.  可選輸入數位以測試正常化規則，**然後按一下 [** 執行]。 測試結果會顯示在 [**輸入要測試的號碼**] 下。
    
    <div>
    

    > [!NOTE]
    > 您可以儲存尚未經過測試的正常化規則，稍後再重新設定。 如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</A>。

    
    </div>

10. 按一下 **[確定]** 以儲存正常化規則。

11. 按一下 **[確定]** 儲存撥號計畫。

12. 在 [**撥號方案**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。
    
    <div>
    

    > [!NOTE]
    > 每當您建立或變更正常化規則時，您必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中手動建立或修改正規化規則](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[在 Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中修改撥號對應表](lync-server-2013-modify-a-dial-plan.md)  
[在 Lync Server 2013 中發佈語音路由設定的擱置變更](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

