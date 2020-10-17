---
title: Lync Server 2013：執行非正式語音路由測試
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Run informal voice routing tests
ms:assetid: ea0e6059-bf04-4b03-b6d3-8f5534b731e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399049(v=OCS.15)
ms:contentKeyID: 48185904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fd8c20adfa98a10bd0b9a89ad31dda37e4510e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511160"
---
# <a name="run-informal-voice-routing-tests-in-lync-server-2013"></a>在 Lync Server 2013 中執行非正式語音路由測試

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-07_

您可以使用 [ **建立語音路由測試案例資訊** ] 對話方塊來執行非正式測試，然後再建立實際的測試案例。 當您對測試結果滿意時，您可以選擇將其儲存為正式的測試案例。

<div>

## <a name="to-run-an-informal-voice-routing-test"></a>執行非正式語音路由測試

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **語音路由**]，然後按一下 [ **測試語音路由**]。

4.  在 [ **測試語音路由** ] 頁面上，按一下 [ **建立語音路由測試案例資訊**]。

5.  在 [ **撥打號碼** ] 欄位中，輸入您要用於此測試的電話號碼。 這個數目會正規化並顯示在 [**結果**] 窗格的 [**正規化數位**] 欄位中。

6.  在 [ **撥號** 對應表] 清單中，選取要用來測試撥號對應表的撥號對應表。 預設是 [全域] 撥號對應表。
    
    當您執行測試時，此撥號對應表中符合撥號號碼的第一個正規化規則會顯示在 [**結果**] 窗格的 [正規化**規則**] 欄位中。

7.  在 [ **語音原則** ] 清單中，選取用來測試撥號號碼的語音原則。 預設是通用語音原則。
    
    當您執行測試時，這個語音原則中第一個相符的 PSTN 使用方式記錄會顯示在 [**結果**] 窗格的 [**第一個 PSTN 使用狀況**] 欄位中。 此外，與此 PSTN 使用方式記錄相關聯的第一個相符語音路由會顯示在 **第一個路由** 欄位中。

8.   (選用) 若您想要依據指派給特定使用者的語音原則來測試撥號號碼，請選取 [ **從使用者填入** ] 核取方塊。
    
    1.  按一下 **[流覽]** 以顯示 [ **選取企業語音使用者** ] 對話方塊。
    
    2.  按一下 [ **尋找** ]，顯示已啟用 Enterprise Voice 之使用者的清單。
    
    3.  按兩下您要用於此測試的指派語音原則的使用者名稱。 [ **原則** ] 欄位現在會填入指派給選取之使用者的語音原則。
    
    當您執行測試時，這個語音原則中第一個相符的公用交換電話網路 (PSTN) 使用方式記錄會顯示在 [**結果**] 窗格的 [**第一個 PSTN 使用狀況**] 欄位中。 此外，與此 PSTN 使用方式記錄相關聯的第一個相符語音路由會顯示在 **第一個路由** 欄位中。

9.  按一下 [ **執行** ] 以執行測試案例。 結果會顯示在對話方塊的右窗格中。

10.  (選用) 按一下 [ **另存** 新檔]，即可將此測試設定儲存為正式測試案例。
    
    1.  在 [**儲存語音路由測試案例資訊**] 對話方塊的 [**名稱**] 欄位中，輸入測試案例的唯一名稱。
        
        在您的企業語音部署中，所有語音路由測試案例的名稱都必須是唯一的。 它的長度最多為32個字元，而且可以包含任何字母元字元，除了反斜線 (\\) 、句點 ( ) 或底線 (\_) 。
    
    2.  請注意，[ **儲存語音路由測試案例資訊** ] 對話方塊中的其餘欄位是唯讀的，而且會從非正式測試設定 *和* 結果中預先填入。 請確認這是您要為測試案例儲存的設定。
        
        <div>
        

        > [!NOTE]  
        > 測試結果中的值可用於預先填入 [ <STRONG>儲存語音路由測試案例資訊</STRONG> ] 對話方塊上的欄位，如下所示： 
        > <UL>
        > <LI>
        > <P><STRONG>預期的轉譯</STRONG> 會預先填入 [ <STRONG>正規化數位</STRONG> ] 欄位中的值。</P>
        > <LI>
        > <P><STRONG>預期的路由</STRONG> 會預先填入 <STRONG>第一個路由</STRONG> 欄位中的值。</P>
        > <LI>
        > <P><STRONG>預期的 pstn 使用方式記錄</STRONG> 已預先填入 <STRONG>第一個 PSTN 使用狀況</STRONG> 欄位中的值。</P></LI></UL>如果在測試執行期間找不到任何這些值的相符專案，則 [ <STRONG>儲存語音路由測試案例資訊</STRONG> ] 對話方塊上的對應欄位會是空的。

        
        </div>
    
    3.  按一下 **[確定]** 儲存測試案例，或按一下 [ **取消** ] 回到 [ **查看語音路由測試案例資訊** ] 對話方塊，以在儲存之前進一步開發測試。

11. 依序按一下 **[認可]** 和 **[全部認可]**。
    
    <div>
    

    > [!NOTE]  
    > 每當您建立語音路由測試案例時，都必須執行「 <STRONG>認可所有</STRONG> 」命令來發佈測試案例。 如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立語音路由測試案例](lync-server-2013-create-a-voice-routing-test-case.md)  
[在 Lync Server 2013 中執行語音路由測試案例](lync-server-2013-run-voice-routing-test-cases.md)  
[在 Lync Server 2013 中匯出語音路由測試案例](lync-server-2013-export-voice-routing-test-cases.md)  
[在 Lync Server 2013 中匯入語音路由測試案例](lync-server-2013-import-voice-routing-test-cases.md)  


[在 Lync Server 2013 中設定撥號對應表](lync-server-2013-configuring-dial-plans.md)  
[在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

