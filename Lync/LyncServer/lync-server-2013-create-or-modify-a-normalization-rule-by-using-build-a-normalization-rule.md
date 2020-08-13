---
title: 使用組建正常化規則建立或修改正規化規則
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
ms.openlocfilehash: 02bbebae55504fcc27550bae3b90d7fca662a487
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a>在 Lync Server 2013 中使用組建標準化規則來建立或修改正規化規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

如果您想要在 Lync Server [控制台] 中建立或修改正規化規則，請完成下列步驟。 或者，如果您想要手動建立或修改正規化規則，請參閱[在 Lync Server 2013 中手動建立或修改正規化規則](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)。

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a>使用組建正常化規則定義規則

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.   (選用) 請遵循在[lync server 2013 中建立撥號](lync-server-2013-create-a-dial-plan.md)對應表中的步驟，在[lync server 2013](lync-server-2013-modify-a-dial-plan.md)中透過步驟10修改撥號對應表。

4.  在 [**新增正規化規則**] 或 [編輯正規化**規則**] 中，輸入描述 [**名稱**] 中正規化的號碼模式的名稱 (例如， **5DigitExtension**) 。

5.   (選用) 在 [**描述**] 中，輸入正規化規則的描述 (例如，「轉譯5位數分機」 ) 。

6.  在 [**建立正規化規則**] 中，在下欄欄位中輸入值：
    
      - **起始位數**     (選用) 指定您想要模式符合的撥號號碼的前置位數。 例如，如果您希望模式比對從425開始的撥號號碼，請輸入**425** 。
    
      - **長度**    指定比對模式中的位數，然後選取是否要讓模式完全符合此長度、比對至少一個長度的撥號號碼，或比對任何長度的撥號號碼。
    
      - **要移除**     的位數 (選用) 指定您想要與模式相符的撥號號碼中所要移除的開始數位數位。
    
      - **要新增**     的位數 (選用) 指定要新增至您想要模式符合的撥號號碼的數位。
    
    您在這些欄位中輸入的值會反映在模式中，**以符合**和**轉譯規則**。 例如，如果您保留空白的**開始數位**，請在**長度**欄位中輸入**7** ，然後選取 [**完全相同**]，並指定**要移除的數位** **0** ，在**模式**中所產生的正則運算式會比對：
    
    **^ (\\ d {7}) $**

7.  在 [**轉譯規則**] 中，指定轉譯的 e.164 電話號碼格式的模式，如下所示：
    
      - 代表匹配模式中指定之位數的值。 例如，如果相符的模式是 **^ (\\ d {7}) $** 後 **$1**的轉譯規則代表7位數撥號碼。
    
      -  (選用) 在 [**要新增的位數**] 欄位中輸入值，以指定要附加到已翻譯的號碼的位數 (例如， **+ 1425**) 。
    
    例如，如果**要比對的模式**包含 **^ (\\ d {7}) $** ，表示撥號號碼和**轉譯規則**的模式包含 **+ 1425 $ 1**做為 e.164 電話號碼的模式，該規則會將5550100標準化為 + 14255550100。

8.   (選用) 如果正規化規則會產生您組織內部的電話號碼，請選取 [**內部分機**]。

9.   (選用) 請輸入號碼以測試正規化規則，然後按一下 [**移至**]。 測試結果會顯示在 [**輸入要測試的號碼**] 底下。
    
    <div>
    

    > [!NOTE]
    > 您可以儲存尚未通過測試的正規化規則，然後稍後再加以重新設定。 如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">Test voice routing In Lync Server 2013</A>。

    
    </div>

10. 按一下 **[確定]** 儲存正規化規則。

11. 按一下 **[確定]** 儲存撥號對應表。

12. 在 [**撥號**對應表] 頁面上，按一下 [**認可**]，然後按一下 [**全部認可**]。
    
    <div>
    

    > [!NOTE]
    > 當您建立或變更正規化規則時，您必須執行 [<STRONG>全部認可</STRONG>] 命令來發佈設定變更。 如需詳細資訊，請參閱 Operations 檔中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A>設定。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中手動建立或修改正規化規則](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[在 Lync Server 2013 中建立撥號對應表](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中修改撥號對應表](lync-server-2013-modify-a-dial-plan.md)  
[在 Lync Server 2013 中將擱置的變更發佈至語音路由設定](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

