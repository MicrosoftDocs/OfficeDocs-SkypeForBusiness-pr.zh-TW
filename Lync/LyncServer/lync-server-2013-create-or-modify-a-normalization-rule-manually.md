---
title: Lync Server 2013：手動建立或修改正規化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e4bff312dda32aea118f91c1e5e54f2c8334698
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a>在 Lync Server 2013 中手動建立或修改正規化規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

如果您想要手動建立或修改正常化規則，請完成下列步驟。 如果您想要使用在 Lync Server [控制台] 中建立正常化規則來建立或修改正常化規則，請參閱[使用 Lync server 2013 中的 [建立正常化規則] 來建立或修改正常化](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)規則。

<div>

## <a name="to-define-a-normalization-rule-manually"></a>手動定義正常化規則

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  可選遵循在[Lync server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)中的步驟，或在[lync Server 2013 中修改撥號計畫](lync-server-2013-modify-a-dial-plan.md)。

4.  在**新的 [正常化規則**] 或 [**編輯正常化規則**] 中，輸入描述**名稱**中要正常化之數位模式的名稱（例如，將 [正常化規則**5DigitExtension**] 命名）。

5.  可選在 [**描述**] 欄位中，輸入正常化規則的描述（例如，「轉譯5位數的延伸」）。

6.  在 [**建立正常化規則**] 中，按一下 [**編輯**]。

7.  在 [輸入**正則運算式**] 中輸入下列內容：
    
      - 在 [**符合這個模式**] 中，指定您要用來與撥打的電話號碼相符的模式。
    
      - 在 [**翻譯規則**] 中，指定翻譯的 e. （164個電話號碼）格式的模式。
    
    例如，如果您在**翻譯規則****中輸入** **^\\（d{7}） $** 和 **+ 1425 $ 1** ，規則會將5550100標準化至 + 14255550100。

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


[在 Lync Server 2013 中使用組建正常化規則來建立或修改正常化規則](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
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

