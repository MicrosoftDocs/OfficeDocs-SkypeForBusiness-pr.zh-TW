---
title: Lync Server 2013：修改撥號對應表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a dial plan
ms:assetid: a91f02df-cf60-40cf-82fe-e0342c118b91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412797(v=OCS.15)
ms:contentKeyID: 48185099
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd4c007933eb7186e412ada1a3f4c35b241f5eff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-dial-plan-in-lync-server-2013"></a>在 Lync Server 2013 中修改撥號對應表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

若要修改現有的撥號方案，請執行下列程式中的步驟。 如果您想要建立新的撥號方案，請參閱[在 Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)。

<div>

## <a name="to-modify-a-dial-plan"></a>修改撥號方案

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**撥號計畫**]。

4.  在 [**撥號方案**] 頁面上，按兩下撥號方案名稱。
    
    <div>
    

    > [!NOTE]  
    > 在建立撥號對應表時設定撥號計畫範圍和名稱。 它們無法變更。

    
    </div>

5.  可選在 [**編輯撥號**對應表] 中，編輯 [簡稱] 欄位中預先填入相同名稱的 [ **Simple name** ] **（名稱）** 欄位，以指定更具描述性的名稱，以反映要套用撥號方案的網站、服務或使用者。
    
    <div>
    

    > [!IMPORTANT]  
    > <STRONG>簡單名稱</STRONG>在 Lync Server 2013 部署中的所有撥號方案中都必須是唯一的。 它不能超過 256 Unicode 字元，每個字元都可以是字母或數位字元、連字號（-）、句點（.）、加號（+）或底線（_）。<BR>[<STRONG>簡易名稱</STRONG>] 欄位中不允許有空格。

    
    </div>

6.  可選在 [**描述**] 欄位中，輸入撥號方案的說明資訊。

7.  可選如果您想要使用此撥號方案作為撥入號碼的地區，請指定**電話撥入式會議區域**。 如果您不想將這個撥號方案用於撥入存取電話號碼，請將此欄位留白。
    
    <div>
    

    > [!NOTE]  
    > 電話撥入式會議區域需要將電話撥入式會議存取號碼與一或多個撥號方案建立關聯。

    
    </div>

8.  可選在 [**外部存取前置**詞] 欄位中，只有在使用者需要撥一或多個額外的前導數位來取得外部線路時，才指定值（例如9）。 您可以輸入最多四個字元的前置詞值（也就是\# \*、、及0-9）。
    
    <div>
    

    > [!NOTE]  
    > 如果您指定外部存取前置詞，就不需要建立新的正常化規則來容納該前置詞。

    
    </div>

9.  針對撥號方案建立並設定正常化規則：
    
      - 若要從企業語音部署中所有可用的正常化規則清單中選擇一或多個規則，請按一下 [**選取**]。 在 [**選取正常化規則**] 對話方塊中，醒目提示您要與撥號計畫建立關聯的規則，然後按一下 **[確定]**。
    
      - 若要定義新的正常化規則，並將它與撥號方案建立關聯，請按一下 [**新增**]。 如需有關定義新規則的詳細資料，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。
    
      - 若要編輯已經與撥號方案相關聯的正常化規則，請醒目提示 [規則名稱]，然後按一下 [**顯示詳細資料**]。 如需有關編輯規則的詳細資訊，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。
    
      - 若要複製現有的正常化規則，以做為定義新規則的起點，請醒目提示規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。 如需編輯複本的詳細資料，請參閱[在 Lync Server 2013 中定義正常化規則](lync-server-2013-defining-normalization-rules.md)。
    
      - 若要從撥號方案中移除正常化規則，請醒目提示規則名稱，然後按一下 [**移除**]。
    
    <div>
    

    > [!NOTE]  
    > 每個撥號方案都必須至少有一個相關聯的正常化規則。 如需如何判斷撥號方案所需的所有正常化規則的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync Server 2013 中的撥號方案和正常化規則</A>。

    
    </div>

10. 確認撥號方案的正常化規則依正確順序排列。 若要變更規則在清單中的位置，請醒目提示 [規則名稱]，然後按一下向上或向下箭號。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 會從上到下遍歷正常化規則清單，並使用與撥號號碼相符的第一個規則。 如果您設定撥號方案，讓撥入的號碼可以符合多個正常化規則，請確定更嚴格的規則排序在限制性較低的規則上方。<BR>預設 [<STRONG>保留所有</STRONG>正常化規則<STRONG>^ （\d{11}）] $</STRONG>符合任何11位數的數位。 例如，如果您要新增的正常化規則與從1425開始的11位數數位相符，請確定 [<STRONG>全部保留</STRONG>] 的排序次序低於較強的<STRONG>^ （1425 \ d{7}） $</STRONG>規則。

    
    </div>

11. 可選輸入數位以測試撥號計畫，**然後按一下 [** 執行]。 測試結果會顯示在 [**輸入要測試的號碼**] 下。
    
    <div>
    

    > [!NOTE]  
    > 您可以儲存尚未經過測試的撥號方案，稍後再重新設定。 如需詳細資訊，請參閱<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中測試語音路由</A>。

    
    </div>

12. 按一下 [確定]****。

13. 在 [**撥號方案**] 頁面上，按一下 [**認可**]，然後按一下 [**全部提交**]。
    
    <div>
    

    > [!NOTE]  
    > 每當您建立或修改撥號方案時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。 如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中發佈語音路由設定的擱置變更](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[在 Lync Server 2013 中定義正規化規則](lync-server-2013-defining-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

