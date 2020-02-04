---
title: Lync Server 2013：建立撥號方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a dial plan
ms:assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398909(v=OCS.15)
ms:contentKeyID: 48185424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d4647f374fd65c0be52da111b7ef2d41c0faae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dial-plan-in-lync-server-2013"></a>在 Lync Server 2013 中建立撥號方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-24_

若要建立新的撥號方案，請執行下列程式中的步驟。 如果您想要編輯撥號方案，請參閱[在 Lync Server 2013 中修改撥號計畫](lync-server-2013-modify-a-dial-plan.md)。

<div>

## <a name="to-create-a-dial-plan"></a>建立撥號方案

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**撥號計畫**]。

4.  在 [**撥號方案**] 頁面上，按一下 [**新增**]，然後選取撥號方案的範圍：
    
      - 除了任何指派給使用者撥號方案的使用者或群組之外，**網站撥號計畫**也適用于整個網站。 如果您選取 [**網站**] 作為撥號方案的範圍，則必須從 [**選取網站**] 對話方塊中選擇網站。 如果已為網站建立撥號方案，該網站不會出現在 [**選取網站**] 對話方塊中。
    
      - 您可以將**池撥號方案**套用至公用的交換式電話網絡（PSTN）閘道或註冊機構。 如果您為撥號方案的範圍選取 [**泳池**]，請從 [**選取服務**] 對話方塊中選擇 PSTN 閘道或註冊機構。 如果已為服務（PSTN 閘道或註冊機構）建立撥號方案，該服務不會出現在清單中。
    
      - 您可以將**使用者撥號方案**套用至指定的使用者或群組。
    
    <div>
    

    > [!NOTE]  
    > 在您選取撥號方案範圍之後，就無法變更它。

    
    </div>

5.  如果您要建立使用者撥號方案，請在 [**新增撥號方案**] 對話方塊上的 [**名稱**] 欄位中，輸入描述性的名稱。 儲存此名稱之後，就無法變更。
    
    <div>
    

    > [!NOTE]  
    > 針對網站撥號方案，[<STRONG>名稱</STRONG>] 欄位會預先填入網站名稱，且無法變更。<BR>針對池撥號方案，使用 PSTN 閘道或註冊機構名稱預先填入<STRONG>name</STRONG>欄位，且無法變更。

    
    </div>

6.  [**簡稱] 欄位會**預先填入與 [**名稱**] 欄位中相同的名稱。 您可以選擇性地編輯此欄位，以指定更具描述性的名稱，以反映要套用撥號方案的網站、服務或使用者。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>簡單名稱</STRONG>在 Lync Server 部署中的所有撥號方案中都必須是唯一的。 它不能超過 256 Unicode 字元，每個字元都可以是字母或數位字元、連字號（-）、句號（.）或底線（_）。<BR><STRONG>不支援</STRONG>的字元包括 RFC 3966 （http://www.ietf.org/rfc/rfc3966.txt).）中定義的空格和保留字元。 <STRONG>簡單名稱</STRONG>中<STRONG>不支援</STRONG>的保留字元包括下列各項：<BR>";""/" "?"":" "@" "&amp;" "=" "+" "$" ","

    
    </div>

7.  可選在 [**描述**] 欄位中，您可以輸入撥號方案的其他描述性資訊。

8.  可選如果您想要使用此撥號方案作為撥入號碼的地區，請指定**電話撥入式會議區域**。 如果您不想將這個撥號方案用於撥入存取電話號碼，請將此欄位留白。
    
    <div>
    

    > [!NOTE]  
    > 電話撥入式會議區域需要將電話撥入式會議存取號碼與一或多個撥號方案建立關聯。

    
    </div>

9.  可選在 [**外部存取前置**詞] 欄位中，只有在使用者需要撥一或多個額外的前導數位（例如9）來取得外部線路時，才指定值。 您可以輸入最多四個字元（\#、 \*和0-9）的前置詞值。
    
    <div>
    

    > [!NOTE]  
    > 如果您指定外部存取前置詞，就不需要建立新的正常化規則來容納該前置詞。

    
    </div>

10. 針對撥號方案建立並設定正常化規則，如下所示：
    
      - 若要從企業語音部署中所有可用的正常化規則清單中選擇一或多個規則，請按一下 [**選取**]。 在 [**選取正常化規則**] 中，醒目提示您要與撥號計畫建立關聯的規則，然後按一下 **[確定]**。
    
      - 若要定義新的正常化規則，並將它與撥號方案建立關聯，請按一下 [**新增**]。 如需有關定義新規則的詳細資料，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。
    
      - 若要編輯已經與撥號方案相關聯的正常化規則，請醒目提示 [規則名稱]，然後按一下 [**顯示詳細資料**]。 如需有關編輯規則的詳細資訊，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。
    
      - 若要複製現有的正常化規則，以做為定義新規則的起點，請醒目提示規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。 如需編輯複本的詳細資料，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。
    
      - 若要從撥號方案中移除正常化規則，請醒目提示規則名稱，然後按一下 [**移除**]。
    
    <div>
    

    > [!NOTE]  
    > 每個撥號方案都必須至少有一個相關聯的正常化規則。 如需如何判斷撥號方案所需的所有正常化規則的相關資訊，請參閱規劃檔中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的撥號方案和正常化規則</A>。

    
    </div>

11. 確認撥號方案的正常化規則依正確順序排列。 若要變更規則在清單中的位置，請醒目提示 [規則名稱]，然後按一下向上或向下箭號。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 會從上到下遍歷正常化規則清單，並使用與撥號號碼相符的第一個規則。 如果您設定撥號方案，讓撥入的號碼可以符合多個正常化規則，請確定更嚴格的規則排序在限制性較低的規則上方。<BR>預設 [<STRONG>保留所有</STRONG>正常化規則<STRONG>^ （\d{11}）] $</STRONG>符合任何11位數的數位。 例如，如果您要新增的正常化規則與從1425開始的11位數數位相符，請確定 [<STRONG>全部保留</STRONG>] 的排序次序低於較強的<STRONG>^ （1425 \{7}d） $</STRONG>規則。

    
    </div>

12. 可選輸入數位以測試撥號計畫，**然後按一下 [** 執行]。 測試結果會顯示在 [**輸入要測試的號碼**] 下。
    
    <div>
    

    > [!NOTE]  
    > 您可以儲存尚未經過測試的撥號方案，稍後再重新設定。 如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</A>。

    
    </div>

13. 按一下 [確定]****。

14. 在 [**撥號方案**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。
    
    <div>
    

    > [!NOTE]  
    > 每當您建立撥號方案時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令來發佈設定變更。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中修改撥號對應表](lync-server-2013-modify-a-dial-plan.md)  
[在 Lync Server 2013 中發佈語音路由設定的擱置變更](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[在 Lync Server 2013 中定義正規化規則](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

