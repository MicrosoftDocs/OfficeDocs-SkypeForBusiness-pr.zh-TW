---
title: Lync Server 2013：建立撥號對應表
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
ms.openlocfilehash: f530faa83cb2e924d93abce6f7496c3ef1b82311
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516920"
---
# <a name="create-a-dial-plan-in-lync-server-2013"></a>在 Lync Server 2013 中建立撥號對應表

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-24_

若要建立新的撥號對應表，請執行下列程式中的步驟。 如果您想要編輯撥號對應表，請參閱 [在 Lync Server 2013 中修改撥號](lync-server-2013-modify-a-dial-plan.md)對應表。

<div>

## <a name="to-create-a-dial-plan"></a>建立撥號對應表

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 [語音路由]**** 和 [撥號對應表]****。

4.  在 [ **撥號** 對應表] 頁面上，按一下 [ **新增** ]，然後選取撥號對應表的範圍：
    
      - **網站撥號** 對應表適用于整個網站，但任何指派給使用者撥號對應表的使用者或群組除外。 如果您針對撥號對應表的範圍選取 [ **網站** ]，必須從 [ **選取網站** ] 對話方塊中選擇網站。 如果已為網站建立撥號對應表，該網站不會出現在 [ **選取網站** ] 對話方塊中。
    
      - **集區撥號** 對應表可以套用到公用交換電話網路 (PSTN) 閘道或註冊機構。 如果您選取 [ **集** 區] 作為撥號對應表的範圍，請從 [ **選取服務** ] 對話方塊中選擇 PSTN 閘道或註冊機。 如果已為服務 (PSTN 閘道或註冊機) 建立撥號對應表，則該服務不會出現在清單中。
    
      - **使用者撥號** 對應表可以套用至指定的使用者或群組。
    
    <div>
    

    > [!NOTE]  
    > 在您選取撥號對應表範圍後，就無法變更。

    
    </div>

5.  如果您要建立使用者撥號對應表，請在 [**新增撥號**對應表] 對話方塊的 [**名稱**] 欄位中輸入描述性名稱。 儲存此名稱後，就無法變更。
    
    <div>
    

    > [!NOTE]  
    > 針對網站撥號對應表，[ <STRONG>名稱</STRONG> ] 欄位會預先填入網站名稱，而且無法變更。<BR>針對集區撥號對應表，[ <STRONG>名稱</STRONG> ] 欄位會預先填入 PSTN 閘道或註冊機名稱，而且無法變更。

    
    </div>

6.  [ **簡單名稱** ] 欄位會預先填入 [ **名稱** ] 欄位中顯示的相同名稱。 您可以選擇性地編輯此欄位，以指定更具描述性的名稱，以反映套用撥號對應表的網站、服務或使用者。
    
    <div>
    

    > [!IMPORTANT]  
    > 在 Lync Server 部署內的所有撥號對應表中， <STRONG>簡單名稱</STRONG> 必須是唯一的。 它不得超過256的 Unicode 字元，每個字元可以是字母或數位字元、連字號 ( ) 、句點 ( ) 或底線 (_) 。<BR><STRONG>不支援</STRONG>的字元包括 RFC 3966 (中所定義的空格和保留字元 http://www.ietf.org/rfc/rfc3966.txt) 。 在<STRONG>簡易名稱</STRONG>中<STRONG>不支援</STRONG>的保留字元包括下列各項：<BR>";""/" "?"":" "@" "&amp;" "=" "+" "$" ","

    
    </div>

7.   (選用) 在 [ **描述** ] 欄位中，您可以輸入撥號對應表的其他描述性資訊。

8.   (選用) 若您要使用此撥號對應表作為撥入存取號碼的地區，請指定 **電話撥入式會議區域**。 如果您不想要將此撥號對應表用於撥入存取號碼，請將此欄位保留空白。
    
    <div>
    

    > [!NOTE]  
    > 必須使用電話撥入式會議區域，才能將電話撥入式會議存取號碼與一或多個撥號對應表產生關聯。

    
    </div>

9.   (選用) 在 [ **外部存取前置** 詞] 欄位中，只有在使用者需要撥打一或多個其他前導數位時，才指定值 (例如，9) 以取得外部行。 您可以輸入最多四個字元的前置詞值 (\# ， \* 及 0-9) 。
    
    <div>
    

    > [!NOTE]  
    > 如果您指定了外部存取前置詞，則不需要建立新的正規化規則來容納前置詞。

    
    </div>

10. 建立和設定撥號對應表的正規化規則，如下所示：
    
      - 若要從 Enterprise Voice 部署中所有可用的正規化規則清單中選擇一個或多個規則，請按一下 [ **選取**]。 在 [ **選取正規化規則**] 中，反白顯示您想要與撥號對應表產生關聯的規則，然後按一下 **[確定]**。
    
      - 若要定義新的正規化規則，並將它與撥號對應表產生關聯，請按一下 [ **新增**]。 如需定義新規則的詳細資訊，請參閱 [在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。
    
      - 若要編輯已與撥號對應表相關聯的正規化規則，請反白顯示規則名稱，然後按一下 [ **顯示詳細資料**]。 如需編輯規則的詳細資訊，請參閱 [在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。
    
      - 若要複製現有的正規化規則，以做為定義新規則的起點，請反白顯示規則名稱，然後按一下 [ **複製**]，然後按一下 [ **貼**上]。 如需編輯複本的詳細資訊，請參閱 [在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。
    
      - 若要從撥號對應表中移除正規化規則，請反白顯示規則名稱，然後按一下 [ **移除**]。
    
    <div>
    

    > [!NOTE]  
    > 每個撥號對應表至少必須有一個相關聯的正常化規則。 如需如何判斷撥號對應表所需之所有正規化規則的相關資訊，請參閱規劃檔中的 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的撥號對應表和正常化規則</A> 。

    
    </div>

11. 確認撥號對應表的正規化規則依正確的順序排列。 若要變更規則在清單中的位置，請反白顯示規則名稱，然後按一下向上或向下箭號。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 會從左上部遍歷正規化規則清單，並使用符合撥號號碼的第一個規則。 如果您設定撥號對應表，讓已撥號的號碼可以比對多個正規化規則，請確定限制性以上的規則排序的限制性較低。<BR>預設 <STRONG>保持所有</STRONG> 正規化規則 <STRONG>^ ( \d {11}) $</STRONG> 符合任何11位數的數位。 例如，如果您新增的正規化規則符合11位數的開始1425的數位，請確定 [ <STRONG>全部保留</STRONG> ] 的排序低於較嚴格的 <STRONG>^ (1425 {7}) $</STRONG> rule。

    
    </div>

12.  (選用) 請輸入號碼以測試撥號對應表，然後按一下 [ **移至**]。 測試結果會顯示在 [ **輸入要測試的號碼**] 底下。
    
    <div>
    

    > [!NOTE]  
    > 您可以儲存尚未通過測試的撥號對應表，然後再加以重新設定。 如需詳細資訊，請參閱 <A href="lync-server-2013-test-voice-routing.md">Test voice routing In Lync Server 2013</A>。

    
    </div>

13. 按一下 [確定]****。

14. 在 [ **撥號** 對應表] 頁面上，按一下 [ **認可**]，然後按一下 [ **全部認可**]。
    
    <div>
    

    > [!NOTE]  
    > 每當您建立撥號對應表時，都必須執行「 <STRONG>認可全部</STRONG> 」命令來發佈設定變更。 如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中修改撥號對應表](lync-server-2013-modify-a-dial-plan.md)  
[在 Lync Server 2013 中將擱置的變更發佈至語音路由設定](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

